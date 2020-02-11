---
title: Solucionar problemas em dispositivo gerenciado para comunicação do NDES no Microsoft Intune | Microsoft Docs
description: Solucione problemas em dispositivo gerenciado para comunicação com o servidor do NDES ao usar perfis de certificado SCEP para implantar certificados com o Intune.
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
ms.openlocfilehash: 8c81fa9b521b0d950fb69c29f7625981e709863d
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916104"
---
# <a name="troubleshoot-device-to-ndes-server-communication-for-scep-certificate-profiles-in-microsoft-intune"></a>Solucionar problemas em dispositivo para a comunicação com o servidor do NDES para perfis de certificado SCEP no Microsoft Intune

Use as informações a seguir para determinar se um dispositivo que recebeu e processou um perfil de certificado do protocolo SCEP do Intune consegue contatar com êxito o NDES (Serviço de registro de dispositivo de rede) para apresentar um desafio. No dispositivo, uma chave privada é gerada, e o CSR (Solicitação de assinatura de certificado) e o desafio são passados do dispositivo para o servidor do NDES. Para entrar em contato com o servidor do NDES, o dispositivo usa o URI do perfil do certificado SCEP.

Este artigo faz referência à Etapa 2 da [Visão geral do fluxo de comunicação do SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="review-iis-logs-for-a-connection-from-the-device"></a>Examinar os logs do IIS em busca de uma conexão do dispositivo

Os logs do IIS incluem o mesmo tipo de entradas para todas as plataformas.


1. No servidor do NDES, abra o arquivo de log do IIS mais recente que se encontra na seguinte pasta:   *%SystemDrive%\inetpub\logs\logfiles\w3svc1*

2. Pesquise o log em busca de entradas semelhantes aos exemplos a seguir. Ambos os exemplos contêm um status **200** que aparece próximo ao final:

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACaps&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 186 0.`

   E

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACert&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 3567 0`

3. Quando o dispositivo entra em contato com o IIS, é registrada uma solicitação HTTP GET para mscep.dll.

   Examine o código de status próximo ao final desta solicitação:
   - **Código de status 200**: esse status indica que a conexão com o servidor do NDES foi bem-sucedida.
   - **Código de status 500**: o grupo IIS_IURS pode não ter as permissões corretas. Confira o [Código de status 500](#status-code-500) mais adiante neste artigo.
   - Se o código de status não for 200 ou 500:

     - Confira [Testar a URL do servidor SCEP](#test-the-scep-server-url) mais adiante neste artigo para ajudar a validar a configuração.

     - Confira [O código de status HTTP no IIS 7 e versões posteriores](https://support.microsoft.com/help/943891) para obter informações sobre os códigos de erros menos comuns.

   Se a solicitação de conexão não for registrada, o contato do dispositivo pode estar bloqueado na rede entre o dispositivo e o servidor do NDES.

## <a name="review-device-logs-for-connections-to-ndes"></a>Examinar os logs de dispositivo para buscar conexões com o NDES

### <a name="android-devices"></a>Dispositivos Android

Examine o [log do OMADM dos dispositivos](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Procure entradas semelhantes ao seguinte, que são registradas quando o dispositivo se conecta ao NDES:

```
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  There are 1 requests
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  Trying to enroll certificate request: ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c;Hash=1677525787
2018-02-27T05:16:09.5530000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:14.6440000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Received '200 OK' when sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.8220000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10 Encoding message: org.jscep.message.PkcsReq@2b06f45f[messageData=org.<server>.pkcs.PKCS10CertificationRequest@699b3cd,messageType=PKCS_REQ,senderNonce=Nonce [D447AE9955E624A56A09D64E2B3AE76E],transId=251E592A777C82996C7CF96F3AAADCF996FC31FF]
2018-02-27T05:16:21.8790000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10  Signing pkiMessage using key belonging to [dn=CN=<uesrname>; serial=1]
2018-02-27T05:16:21.9580000  VERB  Event  org.jscep.transaction.EnrollmentTransaction  18327     10  Sending org.<server>.cms.CMSSignedData@ad57775
```

As principais entradas incluem as seguintes cadeias de texto de exemplo:

- Há 1 solicitação
- Recebeu '200 OK' ao enviar GetCACaps(ca) para https://\<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
- Ao assinar o pkiMessage usando a chave que pertence a [DN = CN =\<nome de usuário >; serial = 1]


A conexão também é registrada pelo IIS na pasta %SystemDrive%\inetpub\logs\LogFiles\W3SVC1\ do servidor do NDES. Veja um exemplo a seguir:

```
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACert&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 3909 0
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACaps&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 421 
```

### <a name="ios-and-ipados-devices"></a>dispositivos iOS e iPadOS

Examine o [log de depuração dos dispositivos](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Procure entradas semelhantes ao seguinte, que são registradas quando o dispositivo se conecta ao NDES:

```
debug    18:30:53.691033 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\ 
debug    18:30:54.640644 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
default    18:30:55.483977 -0500    profiled    Attempting to retrieve issued certificate...\ 
debug    18:30:55.487798 -0500    profiled    Sending CSR via GET.\  
debug    18:30:55.487908 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQGZwmPoqFMbX3g85CJT8khPaqFW05yGDTPSX9YpuEE0Bmtht9EwOpOZe6O7sd77IhfFZVmHmwy5mIYN7K6mpx/4Cb5zcNmY3wmTBlKEkDQpZDRf5PpVQ3bmQ3we9XxeK1S4UsAXHVdYGD+bg/bCafMIAGCSqGSIb3DQEHATAUBggqhkiG9w0DBwQI5D5J2lwZS5OggASCF6jSG9iZA/EJ93fEvZYLV0v7GVo3JAsR11O7DlmkIqvkAg5iC6DQvXO1j88T/MS3wV+rqUbEhktr8Xyf4sAAPI4M6HMfVENCJTStJw1PzaGwUJHEasq39793nw4k268UV5XHXvzZoF3Os2OxUHSfHECOj
```

As principais entradas incluem as seguintes cadeias de texto de exemplo:

- operation=GetCACert
- Tenta recuperar o certificado emitido
- Envia o CSR por meio de GET
- operation=PKIOperation

### <a name="windows-devices"></a>Dispositivos Windows

Em um dispositivo Windows com uma conexão com o NDES, você pode exibir os dispositivos no Visualizador de Eventos do Windows e procurar indicações de uma conexão bem-sucedida. As conexões são registradas com a ID de evento **36** no log de dispositivos *DeviceManagement-Enterprise-Diagnostics-Provide* > **Admin**.

Para abrir o log:

1. No dispositivo, execute **eventvwr.msc** para abrir o Visualizador de Eventos do Windows.

2. Expanda os menus de **Logs de Aplicativos e Serviços** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Admin**.

3. Procure o Evento **36**, semelhante ao exemplo a seguir, com a linha de chave **SCEP: Solicitação de certificado gerada com sucesso**:

   ```
   Event ID:      36
   Task Category: None
   Level:         Information
   Keywords:
   User:          <UserSid>
   Computer:      <Computer Name>
   Description:
   SCEP: Certificate request generated successfully. Enhanced Key Usage: (1.3.6.1.5.5.7.3.2), NDES URL: (https://<server>/certsrv/mscep/mscep.dll/pkiclient.exe), Container Name: (), KSP Setting: (0x2), Store Location: (0x1).
   ```

## <a name="troubleshoot-common-errors"></a>Solucionar erros comuns

As seções a seguir podem ajudar em problemas comuns de conexão com o NDES de todas as plataformas de dispositivo.

### <a name="status-code-500"></a>Código de status 500

Conexões semelhantes ao exemplo a seguir, com um código de status 500, indicam que o direito de usuário *Representar um cliente após a autenticação* não foi atribuído ao grupo IIS_IURS no servidor do NDES. O valor **500** do status é exibido no final:

```
2017-08-08 20:22:16 IP_address GET /certsrv/mscep/mscep.dll operation=GetCACert&message=SCEP%20Authority 443 - 10.5.14.22 profiled/1.0+CFNetwork/811.5.4+Darwin/16.6.0 - 500 0 1346 31
```

**Para corrigir esse problema**:

1. No servidor do NDES, execute **secpol.msc** para abrir a Política de Segurança Local.

2. Expanda as **Políticas Locais** e clique em **Atribuição de Direitos de Usuário**.

3. Clique duas vezes em **Representar um cliente após a autenticação** no painel direito.

4. Clique em **Adicionar Usuário ou Grupo...** , digite **IIS_IURS** em **Digite os nomes de objeto a serem selecionados** e clique em **OK**.

5. Clique em **OK**.

6. Reinicie o computador e tente novamente a conexão do dispositivo.

### <a name="test-the-scep-server-url"></a>Testar a URL do servidor do protocolo SCEP

Use as etapas a seguir para testar a URL especificada no perfil de certificado SCEP.

1. No Intune, edite seu perfil de certificado SCEP e copie a URL do Servidor. A URL deve ser semelhante a *https://contoso.com/certsrv/mscep/msecp.dll* .

2. Abra um navegador e navegue até a URL do servidor SCEP. O resultado deve ser: **Erro de HTTP 403.0 – Proibido**. Esse resultado indica que a URL está funcionando corretamente.

   Se você não receber esse erro, selecione o link semelhante ao erro encontrado para exibir as diretrizes específicas do problema:
   - [Recebo uma mensagem geral do Serviço de Registro de Dispositivo de Rede](#general-ndes-message)
   - [Recebo "Erro de HTTP 503. Serviço Não Disponível"](#http-error-503)
   - [Recebo o erro "GatewayTimeout"](#gatewaytimeout)
   - [Recebo "HTTP 414 – URI de Solicitação Muito Longo"](#http-414-request-uri-too-long)
   - [Recebo "Esta página não pode ser exibida"](#this-page-cant-be-displayed)
   - [Recebo "500 – Erro Interno do Servidor"](#internal-server-error)

#### <a name="general-ndes-message"></a>Mensagem geral do NDES

Ao navegar até a URL do servidor SCEP, você receberá a seguinte mensagem do Serviço de Registro de Dispositivo de Rede:

![URL do servidor do protocolo SCEP](../protect/media/troubleshoot-scep-certificate-device-to-ndes/ndes-server-url-message.png)

- **Causa**: Esse geralmente é um problema relacionado à instalação do Conector do Microsoft Intune.

  Mscep.dll é uma extensão ISAPI que intercepta a solicitação de entrada e exibe o erro HTTP 403 caso esteja instalada corretamente.
  
  **Resolução**: examine o arquivo *SetupMsi.log* para determinar se o Conector do Microsoft Intune foi instalado com êxito. No exemplo a seguir, *Instalação concluída com êxito* e *Status de êxito ou erro da instalação: 0* indicam uma instalação bem-sucedida:

  ```
  MSI (c) (28:54) [16:13:11:905]: Product: Microsoft Intune Connector -- Installation completed successfully.
  MSI (c) (28:54) [16:13:11:999]: Windows Installer installed the product. Product Name: Microsoft Intune Connector. Product Version: 6.1711.4.0. Product Language: 1033. Manufacturer: Microsoft Corporation. Installation success or error status: 0.
  ```

  Se a instalação falhar, remova e reinstale o conector do Microsoft Intune.

#### <a name="http-error-503"></a>Erro de HTTP 503

Ao navegar até a URL do servidor SCEP, você receberá o seguinte erro:

![Erro HTTP 503. O serviço está indisponível](../protect/media/troubleshoot-scep-certificate-device-to-ndes/service-unavailable.png)

Geralmente, esse problema ocorre porque o pool de aplicativos **SCEP** no IIS não foi iniciado. No servidor do NDES, abra **Gerenciador do IIS** e vá até **Pools de aplicativos**. Localize o pool de aplicativos **SCEP** e confirme se ele foi iniciado.

Se o pool de aplicativos SCEP não tiver iniciado, verifique o log de eventos do aplicativo no servidor:

1. No dispositivo, execute **eventvwr.msc** para abrir o **Visualizador de Eventos** e vá para **Logs do Windows** > **Aplicativo**.

2. Procure um evento semelhante ao exemplo a seguir, o que significa que o pool de aplicativos falhou ao receber uma solicitação:

   ```
   Log Name:      Application
   Source:        Application Error
   Event ID:      1000
   Task Category: Application Crashing Events
   Level:         Error
   Keywords:      Classic
   Description: Faulting application name: w3wp.exe, version: 8.5.9600.16384, time stamp: 0x5215df96
   Faulting module name: ntdll.dll, version: 6.3.9600.18821, time stamp: 0x59ba86db
   Exception code: 0xc0000005
   ```

**Causas comuns para a falha de um pool de aplicativos**:

- **Causa 1**: há certificados de CA (autoridade de certificação) intermediários (não autoassinados) no repositório de certificados de Autoridades de Certificação Raiz Confiáveis do servidor do NDES.

  **Resolução**: remova os certificados intermediários do repositório de certificados de Autoridades de Certificação Raiz Confiáveis e reinicie o servidor do NDES.
  
  Para identificar todos os certificados intermediários no repositório de certificados de Autoridades de Certificação Raiz Confiáveis, execute o seguinte cmdlet do PowerShell: `Get-Childitem -Path cert:\LocalMachine\root -Recurse | Where-Object {$_.Issuer -ne $_.Subject}`

  Um certificado que tenha os mesmos valores em **Emitido para** e **Emitido por** é um certificado raiz. Caso contrário, é um certificado intermediário.

  Depois de remover os certificados e reiniciar o servidor, execute novamente o cmdlet do PowerShell para confirmar que não há certificados intermediários. Se houver, verifique se uma Política de Grupo envia os certificados intermediários para o servidor do NDES. Nesse caso, exclua o servidor do NDES da Política de Grupo e remova novamente os certificados intermediários.

- **Causa 2**: as URLs na CRL (Lista de Certificados Revogados) estão bloqueadas ou inacessíveis para os certificados usados pelo Intune Certificate Connector.

  **Resolução**: habilite o log adicional para coletar mais informações:
  1. Abra o Visualizador de Eventos, clique em **Exibir**, confirme se a opção **Mostrar Logs Analíticos e de Depuração** está marcada.
  2. Acesse **Logs de Aplicativos e Serviços** > **Microsoft** > **Windows** > **CAPI2** > **Operacional**, clique com o botão direito do mouse em **Operacional** e clique em **Habilitar Log**.
  3. Depois que o registro em log do CAPI2 estiver habilitado, reproduza o problema e examine o log de eventos para solucionar a questão.

- **Causa 3**: a permissão do IIS em **CertificateRegistrationSvc** está com a **Autenticação do Windows** habilitada.

  **Resolução**: habilite a **Autenticação Anônima**, desabilite a **Autenticação do Windows** e reinicie o servidor do NDES.

  ![Permissões de IIS](../protect/media/troubleshoot-scep-certificate-device-to-ndes/iis-permissions.png)

#### <a name="gatewaytimeout"></a>GatewayTimeout

Ao navegar até a URL do servidor SCEP, você receberá o seguinte erro:

![erro de Gatewaytimeout](../protect/media/troubleshoot-scep-certificate-device-to-ndes/gateway-timeout.png)

- **Causa**: o serviço do **Conector de Proxy de Aplicativo do Microsoft AAD** não foi iniciado.

  **Resolução**:  execute **services.msc** e verifique se o serviço do **Conector de Proxy de Aplicativo do Microsoft AAD** está em execução e se o **Tipo de Inicialização** está definido como **Automático**.

#### <a name="http-414-request-uri-too-long"></a>HTTP 414 – URI de Solicitação Muito Longo

Ao navegar até a URL do servidor SCEP, você receberá o seguinte erro: `HTTP 414 Request-URI Too Long`

- **Causa**: a filtragem de solicitações do IIS não está configurada para dar suporte a URLs longas (consultas) recebidas pelo serviço do NDES. Esse suporte é configurado quando você [configura o serviço do NDES](certificates-scep-configure.md#configure-the-ndes-service) para uso com a infraestrutura do SCEP.

- **Resolução**: configure o suporte para URLs longas.

  1. No servidor do NDES, selecione **Site Padrão** > **Filtragem de Solicitações** > **Editar Configuração do Recurso** para abrir a página **Editar Configurações da Filtragem de Solicitações**.

  2. Defina as seguintes configurações:
     - **Tamanho máximo da URL (bytes)** = 65.534
     - **Tamanho máximo da cadeia de caracteres de consulta (bytes)** = 65.534

  3. Selecione **OK** para salvar essa configuração e fechar o Gerenciador do IIS.

  4. Valide essa configuração localizando a seguinte chave do Registro para confirmar se ela tem os valores indicados:

     HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters

     Os seguintes valores são definidos como entradas DWORD:
     - Nome: **MaxFieldLength**, com um valor decimal de **65534**
     - Nome: **MaxRequestBytes**, com um valor decimal de **65534**

  5. Reinicie o servidor do NDES.

#### <a name="this-page-cant-be-displayed"></a>Esta página não pode ser exibida

Você configurou o Proxy de Aplicativo do Azure AD. Ao navegar até a URL do servidor SCEP, você receberá o seguinte erro:

`This page can't be displayed`

- **Causa**: esse problema ocorre quando a URL externa do SCEP está incorreta na configuração do Proxy de Aplicativo. Um exemplo dessa URL é https://contoso.com/certsrv/mscep/mscep.dll.

  **Resolução**: use o domínio padrão *yourtenant.msappproxy.net* como a URL externa do SCEP na configuração do Proxy de Aplicativo.

#### <a name="internal-server-error"></a> 500 – Erro interno do servidor

Ao navegar até a URL do servidor SCEP, você receberá o seguinte erro:

![500 – Erro interno do servidor](../protect/media/troubleshoot-scep-certificate-device-to-ndes/500-internal-server-error.png)

- **Causa 1**: a conta de serviço do NDES está bloqueada ou sua senha expirou.

  **Resolução**: desbloqueie a conta ou redefina a senha.

- **Causa 2**: os certificados MSCEP-RA expiraram.

  **Resolução**: se os certificados MSCEP-RA estiverem expirados, reinstale a função NDES ou solicite novos certificados do Agente de Inscrição do Exchange (solicitação offline) e da Criptografia CEP.

  Para solicitar novos certificados, siga estas etapas:

  1. Na CA ou CA emissora, abra os Modelos de Certificados no MMC. Verifique se o usuário conectado e o servidor do NDES têm permissões de **Leitura** e **Inscrição** para os modelos de certificados do Agente de Inscrição do Exchange (solicitação offline) e da Criptografia CEP.

  2. Verifique os certificados expirados no servidor do NDES, copie as informações da **Entidade** do certificado.

  3. Abra os Certificados do MMC da **Conta do computador**.

  4. Expanda **Pessoal**, clique com o botão direito do mouse em **Certificados** e selecione **Todas as tarefas** > **Solicitar Novo Certificado**.

  5. Na página **Solicitar Certificado**, selecione **Criptografia CEP** e clique em **Mais informações são necessárias para se registrar neste certificado. Clique aqui para definir as configurações**.

     ![Selecionar Criptografia CEP](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-scep-encryption.png)

  6. Em **Propriedades do Certificado**, clique na guia **Entidade**, preencha o **Nome da entidade** com as informações coletadas durante a etapa 2, clique em **Adicionar** e em **OK**.

  7. Complete o registro de certificado.

  8. Abra os Certificados do MMC da **Minha conta de usuário**.

     O registro no certificado do Agente de Registro do Exchange (solicitação offline) deve ser feito no contexto do usuário. Isso porque o **Tipo de Entidade** desse modelo de certificado é definido como **Usuário**.

  9. Expanda **Pessoal**, clique com o botão direito do mouse em **Certificados** e selecione **Todas as tarefas** > **Solicitar Novo Certificado**.

  10. Na página **Solicitar Certificado**, selecione **Agente de Registro do Exchange (solicitação offline)** e clique em **Mais informações são necessárias para se registrar neste certificado. Clique aqui para definir as configurações**.

      ![Selecionar Agente de Registro do Exchange](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-exchange-enrollment-agent.png)

  11. Em **Propriedades do Certificado**, clique na guia **Entidade**, preencha o **Nome da entidade** com as informações coletadas durante a etapa 2 e clique em **Adicionar**.

      ![Propriedades do certificado](../protect/media/troubleshoot-scep-certificate-device-to-ndes/certificate-properties.png)

      Selecione a guia **Chave Privada**, **Tornar a chave privada exportável** e clique em **OK**.

      ![Chave privada](../protect/media/troubleshoot-scep-certificate-device-to-ndes/private-key.png)

  12. Complete o registro de certificado.

  13. Exporte o certificado do Agente de Registro do Exchange (solicitação offline) do repositório atual de certificados do usuário. No Assistente para Exportação de Certificados, selecione **Sim, exportar a chave privada**.

  14. Importe o certificado para o repositório de certificados do computador local.

  15. Nos certificados do MMC, execute a seguinte ação para cada um dos novos certificados:

      Clique com o botão direito do mouse no certificado, clique em **Todas as Tarefas** > **Gerenciar Chaves Privadas**, adicione a permissão de **Leitura** à conta de serviço do NDES.

  16. Execute o comando **iisreset** para reiniciar o IIS.

## <a name="next-steps"></a>Próximas etapas

Se o dispositivo atingir o servidor do NDES com êxito para apresentar a solicitação de certificado, a próxima etapa será examinar o [módulo de política dos Intune Certificate Connectors](troubleshoot-scep-certificate-ndes-policy-module.md).
