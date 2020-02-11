---
title: Solucionar problemas do módulo de política do Microsoft Intune Certificate Connector | Microsoft Docs
description: Solucione problemas na operação do módulo de política do NDES quando o módulo processa uma solicitação de certificado devido ao uso de perfis de certificado SCEP para implantar certificados com o Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be53f6102226b004cab2bd953357e8c360a00f67
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915831"
---
# <a name="troubleshoot-the-ndes-policy-module-in-microsoft-intune"></a>Solucionar problemas do módulo de política do NDES no Microsoft Intune

As informações neste artigo podem ajudar a validar a operação do módulo de política do NDES (Serviço de Registro de Dispositivo de Rede) instalado com o Microsoft Intune Certificate Connector. Quando o NDES recebe solicitação de um certificado, ele encaminha a solicitação para o módulo de política, que valida a solicitação para o dispositivo. Após a validação, o NDES entra em contato com a CA (autoridade de certificação) para solicitar o certificado em nome do dispositivo.

Este artigo se aplica às etapas 3 e 4 do [fluxo de trabalho de comunicações do protocolo SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="ndes-communication-to-the-policy-module"></a>Comunicações do NDES com o módulo de política

Depois de receber a solicitação de certificado de um dispositivo, o NDES valida essa solicitação com o Intune por meio do módulo de política instalado com o Microsoft Intune Certificate Connector. Essas entradas se referem ao *ponto de registro do certificado*.

**Entradas de log que indicam êxito**:

Para confirmar se a solicitação de validação foi enviada ao módulo, procure uma entrada que se assemelha aos seguintes exemplos em logs no servidor do NDES:

- **Logs do IIS**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 - 
  fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 201 0 0 341 875
  ```

- **Log do NDESPlugin**:

  ```
  Calling VerifyRequest ...  
  Sending request to certificate registration point.
  ```

  O exemplo a seguir indica uma validação bem-sucedida da solicitação de desafio de dispositivos e que agora o NDES pode entrar em contato com a CA:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`


**Quando os indicadores de êxito não estão presentes**:

Se você não encontrar essas entradas, comece revisando as diretrizes de solução de problemas para o [dispositivo de comunicações com o servidor do NDES](troubleshoot-scep-certificate-device-to-ndes.md#troubleshoot-common-errors).

Se as informações neste artigo não ajudarem a resolver o problema, veja a seguir entradas adicionais que podem indicar problemas.

### <a name="ndespluginlog-contains-an-error-12175"></a>NDESPlugin.log contém um erro 12175

Quando o log contiver um erro 12175 semelhante ao seguinte, pode haver um problema com o certificado SSL:

```
WINHTTP_CALLBACK_STATUS_FLAG_CERT_CN_INVALID
Failed to send http request /CertificateRegistrationSvc/Certificate/VerifyRequest. Error 12175
```

Navegadores comuns e modernos em dispositivos móveis ignorarão o *Nome Comum* de um certificado SSL se houver *Nomes Alternativos de Entidade*.

**Resolução**:  emita o certificado SSL do servidor Web com os seguintes atributos para *Nome Comum* e *Nome Alternativo da Entidade* para depois associá-lo à porta 443 no IIS:

  - **Nome da entidade**  
    CN = nome do servidor externo
  - **Nome Alternativo da Entidade**  
     Name = nome do servidor externo  
     DNS Name = nome do servidor interno

### <a name="ndespluginlog-contains-an-error-403--forbidden-access-is-denied"></a>NDESPlugin.log contém um erro 403 – Proibido: Acesso negado"

Quando os logs a seguir contêm um erro 403 semelhante ao seguinte, o certificado do cliente pode ser não confiável ou pode ser inválido:

**NDESPlugin.log**:

```
Sending request to certificate registration point.
Verify challenge returns <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"> <html xmlns="http://www.w3.org/1999/xhtml"> <head><meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"/>
<title>403 - Forbidden: Access is denied.</title>
```

**Log do IIS**:

```
POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 -<IP_address>
NDES_Plugin - 403 16 2148204809 453  
```

esse problema ocorrerá se houver certificados intermediários da CA no repositório de certificados de Autoridades de Certificação Raiz Confiáveis do servidor do NDES.

Caso um certificado tenha os mesmos valores para *Emitido para* e *Emitido por*, ele é um certificado raiz. Caso contrário, é um certificado intermediário.

**Resolução**: para corrigir o problema, identifique e remova os certificados de CA intermediários do repositório de certificados de Autoridades de Certificação Raiz Confiáveis.

### <a name="ndespluginlog-indicates-the-challenge-returns-false"></a>NDESPlugin.log indica que o desafio retornou falso

Quando o resultado do desafio retornar **falso**, verifique se *CertificateRegistrationPoint.svclog* apresenta erros. Por exemplo, você pode ver o erro "Não foi possível recuperar o certificado de autenticação", semelhante à seguinte entrada:

```
Signing certificate could not be retrieved. System.Security.Cryptography.CryptographicException: m_safeCertContext is an invalid handle. at System.Security.Cryptography.X509Certificates.X509Certificate.ThrowIfContextInvalid() at System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString() at Microsoft.ConfigurationManager.CertRegPoint.CRPCertificate.RetrieveSigningCert(String certThumbprint
```

**Resolução**: no servidor em que o conector está instalado, abra o Editor do Registro, localize a chave do registro `HKLM\SOFTWARE\Microsoft\MicrosoftIntune\NDESConnector` e verifique se há o valor SigningCertificate.

Se esse valor não estiver presente, reinicie o serviço do Conector do Intune em services.msc e verifique se o valor aparece no registro. Caso o valor ainda esteja ausente, geralmente isso ocorre devido a problemas de conectividade de rede entre o servidor do NDES e o serviço do Intune.

## <a name="ndes-passes-the-request-to-issue-the-certificate"></a>O NDES transmite a solicitação para emitir o certificado

Após uma validação bem-sucedida pelo ponto de registro de certificado (o módulo de política), o NDES transmite a solicitação de certificado para a CA em nome do dispositivo.

**Entradas de log que indicam êxito**:

- **Log do NDESPlugin**:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **Logs do IIS**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe ... 80 - 
  fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 2713 1296
  ```

- **CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`

**Quando os indicadores de êxito não estão presentes**:

Se você não encontrar as entradas que indicam êxito, siga estas etapas:

1. Procure por problemas registrados em *CertificateRegistrationPoint.svclog* quando o ponto de registro de certificado verificar o desafio. Procure as entradas entre as seguintes linhas:

   - VerifyRequest Started.
   - VerifyRequest Finished with status False

2. Abra o MMC na Autoridade de Certificação e selecione **Solicitações com Falha** para procurar erros que ajudem a identificar um problema. A imagem a seguir é um exemplo:

   ![Exemplo de uma solicitação com falha](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/failed-requests.png)

3. Examine se o log de eventos do aplicativo na CA apresenta erros. Normalmente, é possível ver os erros que correspondem ao que você viu em **Solicitações com Falha** da etapa anterior. A imagem a seguir é um exemplo:

   ![Examinar o log do aplicativo](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/application-log-errors.png)

## <a name="next-steps"></a>Próximas etapas

Se o módulo de política do NDES validar a solicitação, e essa solicitação for encaminhada para a autoridade de certificação, a próxima etapa será examinar a [entrega de certificado para o dispositivo](troubleshoot-scep-certificate-delivery.md).
