---
title: APIs para integrar autoridades de certificação de terceiros
titleSuffix: Microsoft Intune
description: Adicione ou integre a solução do SCEP no GitHub a ACs (autoridades de certificação) de terceiros para emitir certificados SCEP para dispositivos no Microsoft Intune. Essa solução inclui APIs Java e C# que validam, enviam notificações de sucesso e falha para o Intune e usam o alocador de soquete SSL ao se comunicarem com o Intune. Exiba também uma visão geral das etapas para testar a configuração de AC do SCEP.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/06/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0a888e2087b98eeec82aeeb555677dddcb3eff4e
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74058235"
---
# <a name="use-apis-to-add-third-party-cas-for-scep-to-intune"></a>Usar APIs para adicionar ACs de terceiros para SCEP ao Intune

No Microsoft Intune, você pode adicionar ACs (autoridades de certificação) de terceiros e fazer com que essas ACs emitam e validem certificados usando o protocolo SCEP. [Adicionar autoridade de certificação de terceiros](certificate-authority-add-scep-overview.md) fornece uma visão geral desse recurso e descreve as tarefas de Administrador do Intune.

Também há algumas tarefas de desenvolvedor que usam uma biblioteca de software livre publicada pela Microsoft em GitHub.com. A biblioteca inclui uma API que:

- Valida a senha do SCEP gerada dinamicamente pelo Intune
- Notifica o Intune dos certificados criados em dispositivos que enviam solicitações do SCEP

Com essa API, o servidor do SCEP de terceiros é integrado à solução de gerenciamento do SCEP no Intune para dispositivos MDM. A biblioteca abstrai aspectos, como autenticação, local do serviço e a API do Serviço do Intune de ODATA de seus usuários.

## <a name="scep-management-solution"></a>Solução de gerenciamento do SCEP

![Como o SCEP da autoridade de certificação de terceiros é integrado ao Microsoft Intune](./media/scep-libraries-apis/scep-certificate-vendor-integration.png)

Usando o Intune, os administradores criam perfis do SCEP e, em seguida, atribuem esses perfis aos dispositivos de MDM. Os perfis do SCEP incluem parâmetros, como:

- A URL do servidor do SCEP
- O Certificado Raiz Confiável da Autoridade de Certificação
- Atributos de certificado e muito mais

Os dispositivos que fazem check-in no Intune recebem o perfil do SCEP e são configurados com esses parâmetros. Uma senha de desafio do protocolo SCEP gerada dinamicamente é criada pelo Intune e, em seguida, atribuída ao dispositivo.

Esse desafio contém:

- A senha de desafio gerada dinamicamente
- Os detalhes sobre os parâmetros esperados na CSR (solicitação de assinatura de certificado) que o dispositivo emite para o servidor SCEP
- A hora da expiração do desafio

O Intune criptografa essas informações, assina o blob criptografado e, em seguida, empacota esses detalhes como a senha de desafio do protocolo SCEP.

Em seguida, os dispositivos que contatam o servidor SCEP para solicitar um certificado fornecem essa senha de desafio do SCEP. O servidor SCEP envia a CSR e a senha de desafio do SCEP criptografada para o Intune para validação.  Essa senha de desafio e a CSR precisam ser aprovadas na validação para que o servidor SCEP emita um certificado para o dispositivo. Quando um desafio do SCEP é validado, ocorrem as seguintes verificações:


- Valida a assinatura de um blob criptografado
- Valida se o desafio não expirou
- Valida se o perfil ainda é direcionado ao dispositivo
- Valida se as propriedades do certificado solicitadas pelo dispositivo no CSR correspondem aos valores esperados

A solução de gerenciamento do SCEP também inclui relatórios. Um administrador pode obter informações sobre o status da implantação do perfil SCEP e sobre os certificados emitidos para os dispositivos.

## <a name="integrate-with-intune"></a>Integrar com o Intune

O código para que a biblioteca seja integrada ao SCEP no Intune está disponível para download no [repositório GitHub Microsoft/Intune-Resource-Access](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation).

A integração da biblioteca aos produtos inclui as etapas a seguir. Essas etapas exigem conhecimento sobre como trabalhar com repositórios GitHub e criar soluções e projetos no Visual Studio.

1. Registrar-se para receber notificações do repositório
2. Clonar ou baixar o repositório
3. Acessar a implementação de biblioteca necessária na pasta `\src\CsrValidation` (https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
4. Compilar a biblioteca usando as instruções do arquivo LEIAME
5. Incluir a biblioteca no projeto que compila o servidor do SCEP
6. Conclua as seguintes tarefas no Servidor do SCEP:

    - Permita que o administrador configure o [Identificador de Aplicativo do Azure, a Chave de Aplicativo do Azure e a ID do Locatário](#onboard-scep-server-in-azure) (neste artigo) usados pela biblioteca para autenticação. Os administradores devem ter permissão para atualizar a Chave de Aplicativo do Azure.
    - Identificar as solicitações do SCEP que incluem uma senha do SCEP gerada pelo Intune
    - Use a biblioteca **Validar API de Solicitação** para validar as senhas do SCEP geradas pelo Intune
    - Use a APIs de notificação de biblioteca para notificar o Intune sobre os certificados emitidos para solicitações do SCEP que têm as senhas do SCEP geradas pelo Intune. Notifique também o Intune sobre erros que podem ocorrer ao processar essas solicitações do SCEP.
    - Confirmar se o servidor registra em log informações suficientes para ajudar os administradores a solucionar problemas

7. Conclua os [testes de integração](#integration-testing) (neste artigo) e resolva os problemas
8. Forneça diretrizes por escrito para o cliente que explique:

    - Como o Servidor do SCEP precisa ser integrado no portal do Azure
    - Como obter o Identificador do Aplicativo do Azure e a Chave de Aplicativo do Azure necessários para configurar a biblioteca

### <a name="onboard-scep-server-in-azure"></a>Integrar o servidor do SCEP no Azure

Para se autenticar no Intune, o servidor do SCEP exige uma ID do Aplicativo do Azure, uma Chave de Aplicativo do Azure e uma ID de Locatário. O Servidor do SCEP também precisa ser autorizado a acessar a API do Intune.

Para obter esses dados, o administrador do servidor do SCEP entra no portal do Azure, registra o aplicativo, concede ao aplicativo a permissão **Validação de desafio da API do Microsoft Intune\do SCEP**, cria uma chave para o aplicativo e, em seguida, baixa a ID do aplicativo, sua chave e a ID do locatário.

Para obter diretrizes sobre como registrar um aplicativo e obter as IDs e as chaves, confira [Usar o portal para criar uma entidade de serviço e de aplicativo do AAD para acessar os recursos](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).

### <a name="java-library-api"></a>API da Biblioteca Java

A biblioteca Java é implementada como um projeto Maven que efetua pull de suas dependências quando compilada. A API é implementada no namespace `com.microsoft.intune.scepvalidation` pela classe `IntuneScepServiceClient`.

#### <a name="intunescepserviceclient-class"></a>Classe IntuneScepServiceClient

A classe `IntuneScepServiceClient` inclui os métodos usados pelo serviço do SCEP para validar as senhas do SCEP, para notificar o Intune sobre os certificados que são criados e para listar os erros.

##### <a name="intunescepserviceclient-constructor"></a>Construtor IntuneScepServiceClient

Assinatura:

```java
IntuneScepServiceClient(
    Properties configProperties)
```

Descrição:

Cria uma instância e configura um objeto `IntuneScepServiceClient`.

Parâmetros:

    - configProperties    Objeto de propriedades que contém informações de configuração do cliente

A configuração precisa incluir as seguintes propriedades:

    - AAD_APP_ID="A ID de Aplicativo do Azure obtida durante o processo de integração"
    - AAD_APP_KEY="A Chave de Aplicativo do Azure obtida durante o processo de integração"
    - TENANT="A ID do locatário obtida durante o processo de integração"
    - PROVIDER_NAME_AND_VERSION="Informações usadas para identificar o produto e a versão"
    
Se a solução exigir um proxy com autenticação ou sem autenticação, você poderá adicionar as seguintes propriedades:

    - PROXY_HOST = "O host em que o proxy está hospedado."
    - PROXY_PORT = "A porta em que o proxy está escutando."
    - PROXY_USER = "O nome de usuário a ser usado se o proxy usar autenticação Básica."
    - PROXY_PASS = "A senha a ser usada se o proxy usar a autenticação Básica."

Gera:

    - IllegalArgumentException     Gerada se o construtor é executado sem um objeto de propriedade adequado.

> [!IMPORTANT]
> É melhor criar uma instância dessa classe e usá-la para processar várias solicitações do SCEP. Fazer isso reduz a sobrecarga, pois ela armazena em cache os tokens de autenticação e as informações de local do serviço.

**Observações de segurança**  
O implementador do servidor SCEP precisa proteger os dados inseridos nas propriedades de configuração persistidas no armazenamento contra adulteração e divulgação. É recomendável usar as ACLs apropriadas e a criptografia para proteger as informações.

##### <a name="validaterequest-method"></a>Método ValidateRequest

Assinatura:

```java
void ValidateRequest(
    String transactionId,
    String certificateRequest)
```

Descrição:

Valida uma solicitação de certificado SCEP.

Parâmetros:

    - transactionId         A ID de transação do SCEP
    - certificateRequest      Solicitação de certificado PKCS nº 10 codificado por DER e em Base64 como uma cadeia de caracteres

Gera:

    - IllegalArgumentException      Gerada se for chamada com um parâmetro inválido
    - IntuneScepServiceException Gerada se a solicitação de certificado for considerada inválida
    - Exception                     Gerada se um erro inesperado for encontrado

> [!IMPORTANT]
> As exceções geradas por esse método devem ser registradas em log pelo servidor. Observe que as propriedades de `IntuneScepServiceException` contêm informações detalhadas sobre o motivo da falha da validação de solicitação de certificado.

**Observações de segurança**  

- Se esse método gerar uma exceção, o servidor do SCEP **não deverá** emitir um certificado para o cliente.
- As falhas da validação de solicitação de certificado SCEP podem indicar um problema na infraestrutura do Intune. Ou podem indicar que um invasor está tentando obter um certificado.

##### <a name="sendsuccessnotification-method"></a>Método SendSuccessNotification

Assinatura:

```java
void SendSuccessNotification(
    String transactionId,
    String certificateRequest,
    String certThumbprint,
    String certSerialNumber,
    String certExpirationDate,
    String certIssuingAuthority)
```

Descrição:

Notifica o Intune de que um certificado é criado como parte do processamento de uma solicitação do SCEP.

Parâmetros:

    - transactionId           A ID de transação do SCEP
    - certificateRequest      Solicitação de certificado PKCS nº 10 codificado por DER e em Base64 como uma cadeia de caracteres
    - certThumprint           Impressão digital do certificado provisionado
    - certSerialNumber        O número de série do certificado provisionado
    - certExpirationDate      Data de expiração do certificado provisionado. A cadeia de caracteres de data e hora deve ser formatada como a hora UTC da Web (YYYY-MM-DDThh:mm:ss.sssTZD) ISO 8601.
    - certIssuingAuthority    Nome da autoridade que emitiu o certificado

Gera:

    - IllegalArgumentException      Gerada se for chamada com um parâmetro inválido
    - IntuneScepServiceException Gerada se a solicitação de certificado for considerada inválida
    - Exception                     Gerada se um erro inesperado for encontrado

> [!IMPORTANT]
> As exceções geradas por esse método devem ser registradas em log pelo servidor. Observe que as propriedades de `IntuneScepServiceException` contêm informações detalhadas sobre o motivo da falha da validação de solicitação de certificado.

**Observações de segurança**

- Se esse método gerar uma exceção, o servidor do SCEP **não deverá** emitir um certificado para o cliente.
- As falhas da validação de solicitação de certificado SCEP podem indicar um problema na infraestrutura do Intune. Ou podem indicar que um invasor está tentando obter um certificado.

##### <a name="sendfailurenotification-method"></a>Método SendFailureNotification

Assinatura:

```java
void SendFailureNotification(
    String transactionId,
    String certificateRequest,
    long  hResult,
    String errorDescription)
```

Descrição:

Notifica o Intune de que ocorreu um erro ao processar uma solicitação do SCEP. Esse método não deve ser invocado para exceções geradas pelos métodos dessa classe.

Parâmetros:

    - transactionId         A ID de transação do SCEP
    - certificateRequest      Solicitação de certificado PKCS nº 10 codificado por DER e em Base64 como uma cadeia de caracteres
    - hResult               Código de erro hResult Win32 que melhor descreve o erro encontrado. Confira [Códigos de erro do Win32](https://msdn.microsoft.com/library/cc231199.aspx)
    - errorDescription      Descrição do erro encontrado

Gera:

    - IllegalArgumentException      Gerada se for chamada com um parâmetro inválido
    - IntuneScepServiceException Gerada se a solicitação de certificado for considerada inválida
    - Exception                     Gerada se um erro inesperado for encontrado

> [!IMPORTANT]
> As exceções geradas por esse método devem ser registradas em log pelo servidor. Observe que as propriedades de `IntuneScepServiceException` contêm informações detalhadas sobre o motivo da falha da validação de solicitação de certificado.

**Observações de segurança**

- Se esse método gerar uma exceção, o servidor do SCEP **não deverá** emitir um certificado para o cliente.
- As falhas da validação de solicitação de certificado SCEP podem indicar um problema na infraestrutura do Intune. Ou podem indicar que um invasor está tentando obter um certificado.

##### <a name="setsslsocketfactory-method"></a>Método SetSslSocketFactory

Assinatura:

```java
void SetSslSocketFactory(
    SSLSocketFactory factory)
```

Descrição:

Use esse método para informar ao cliente de que ele precisa usar o alocador de soquete SSL especificado (em vez do padrão) ao se comunicar com o Intune.

Parâmetros:

    - factory    O alocador de soquete SSL que o cliente deve usar para solicitações HTTPS

Gera:

    - IllegalArgumentException    Gerada se for chamada com um parâmetro inválido

> [!NOTE]
> O alocador de Soquete SSL precisa ser definido, se necessário, antes de executar os outros métodos dessa classe.

## <a name="integration-testing"></a>Teste de integração

É imperativo validar e testar se a solução está corretamente integrada ao Intune. Esta é uma lista de visão geral das etapas:

1. Configurar uma [conta de avaliação do Intune](../fundamentals/account-sign-up.md).
2. Integrar o [Servidor do SCEP no portal do Azure](#onboard-scep-server-in-azure) (neste artigo).
3. [Configurar o Servidor do SCEP](certificates-scep-configure.md) com as IDs e a chave criadas durante a integração do servidor do SCEP.
4. [Registrar dispositivos](../enrollment/device-enrollment.md) para testar os cenários na [matriz de teste de cenários](https://github.com/Microsoft/Intune-Resource-Access/blob/develop/src/CsrValidation/doc/TestMatrix.csv).
5. [Criar um perfil de Certificado Raiz Confiável](certificates-scep-configure.md) para a Autoridade de Certificação do teste.
6. Criar perfis do SCEP para testar os cenários listados na [matriz de teste de cenários](https://github.com/Microsoft/Intune-Resource-Access/blob/develop/src/CsrValidation/doc/TestMatrix.csv).
7. [Atribuir os perfis](../configuration/device-profile-assign.md) aos usuários que registraram seus dispositivos.
8. Aguardar a sincronização dos dispositivos com o Intune. Ou [sincronizar os dispositivos](../remote-actions/device-sync.md) manualmente.
9. Confirmar se o Certificado Raiz Confiável e os [perfis SCEP são implantados nos dispositivos](../configuration/device-profile-monitor.md).
10. Confirmar se o Certificado Raiz Confiável está instalado em todos os dispositivos.
11. Confirmar se os Certificados SCEP para os perfis atribuídos estão instalados em todos os dispositivos.
12. Confirmar se as propriedades dos certificados instalados correspondem às propriedades definidas no perfil do SCEP.
13. Confirmar se os certificados emitidos estão listados corretamente no console do Intune

## <a name="see-also"></a>Consulte também

- [Visão geral da adição de uma AC de terceiros](certificate-authority-add-scep-overview.md)
- [Configurar o Intune](../fundamentals/setup-steps.md)
- [Registro de dispositivo](../enrollment/device-enrollment.md)
- [Configurar perfis de certificado SCEP](certificates-profile-scep.md) (a instalação do Servidor NDES\Conector da Microsoft não é usada nesse cenário)
