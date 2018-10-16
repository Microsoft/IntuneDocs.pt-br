---
title: Usar a AC de terceiros com o SCEP no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, você pode adicionar uma AC (autoridade de certificação) de terceiros ou de fornecedor para emitir certificados para dispositivos móveis usando o protocolo SCEP. Nesta visão geral, um aplicativo do Azure AD (Azure Active Directory) concede permissões ao Microsoft Intune para validar certificados. Em seguida, use a ID do aplicativo, a chave de autenticação e a ID do locatário do aplicativo do AAD na configuração do servidor do SCEP para emitir certificados.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e088dbf4080cb6092ff506519b81438a0d5ce64c
ms.sourcegitcommit: ab08dd841f16ae11f958c43b6262a9f6a0cabdd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49102099"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Adicionar autoridade de certificação de parceiro no Intune usando o SCEP

No Microsoft Intune, as ACs (autoridades de certificação) de terceiros podem ser adicionadas. Essas ACs podem fornecer certificados a dispositivos móveis usando o protocolo SCEP. Esse recurso pode emitir novos certificados e renovar certificados em dispositivos Windows, iOS, Android e macOS.

Há duas partes para o uso desse recurso: API de software livre e as tarefas de administrador do Intune.

**Parte 1 – Usar uma API de software livre**  
A Microsoft criou uma API que é integrada ao Intune para validar certificados, enviar notificações de sucesso ou falha e usar o SSL, especificamente, o alocador de soquete SSL, para se comunicar com o Intune.

A API está disponível no [repositório GitHub público de API do SCEP no Intune](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) para que você possa baixá-la e usá-la em suas soluções. Use essa API com servidores do SCEP de terceiros para executar uma validação de desafio personalizada no Intune antes de fornecer um certificado para um dispositivo.

[Integrar a solução de gerenciamento do SCEP no Intune](scep-libraries-apis.md) fornece mais detalhes sobre como usar a API, seus métodos e o teste da solução criada.

**Parte 2 – Criar o aplicativo e o perfil**  
Usando um aplicativo do Azure AD (Azure Active Directory), você pode delegar direitos para o Intune para manipular solicitações do SCEP provenientes de dispositivos. O aplicativo Azure AD inclui a ID do aplicativo e os valores de chave de autenticação usados na solução de API criada pelo desenvolvedor. Em seguida, os administradores podem criar e implantar perfis de certificados SCEP usando o Intune. Você também pode exibir relatórios sobre o status de implantação nos dispositivos.

Este artigo fornece uma visão geral desse recurso de uma perspectiva do Administrador, incluindo a criação do aplicativo Azure AD.

## <a name="overview"></a>Visão geral

As seguintes etapas fornecem uma visão geral da emissão de certificados SCEP no Intune:

1. No Intune, um administrador cria um perfil de certificado SCEP e, em seguida, direciona o perfil a usuários ou dispositivos.
2. O dispositivo faz check-in no Intune.
3. O Intune cria um desafio exclusivo do SCEP. Ele também adiciona outras informações de verificação de integridade, como a estimativa da entidade e da SAN esperadas.
4. O Intune criptografa e assina as informações de desafio e de verificação de integridade e, em seguida, envia essas informações para o dispositivo com a solicitação do SCEP.
5. O dispositivo gera um CSR (solicitação de autenticação de certificado) e o par de chaves pública/privada no dispositivo com base no perfil de certificado SCEP enviado por push do Intune.
6. O CSR e o desafio criptografado/autenticado são enviados ao ponto de extremidade do servidor SCEP de terceiros.
7. O servidor SCEP envia o CSR e o desafio para o Intune. Em seguida, o Intune valida a assinatura, descriptografa o conteúdo e compara o CSR com as informações de verificação de integridade.
8. O Intune envia uma resposta de volta ao servidor do SCEP e informa se a validação de desafio foi bem-sucedida ou não.  
9. Se o desafio for verificado com êxito, o servidor do SCEP emitirá o certificado para o dispositivo.

O seguinte diagrama mostra um fluxo detalhado da integração do SCEP de terceiros com o Intune:

![Como o SCEP da autoridade de certificação de terceiros é integrado ao Microsoft Intune](./media/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Configurar a integração de AC de terceiros

### <a name="validate-third-party-certification-authority"></a>Validar a autoridade de certificação de terceiros

Antes de integrar as autoridades de certificação de terceiros ao Intune, confirme se a AC que você está usando dá suporte ao Intune. [Parceiros de AC de terceiros](#third-party-certification-authority-partners) (neste artigo) inclui uma lista. Verifique também as diretrizes da autoridade de certificação para obter mais informações. A AC pode incluir instruções de instalação específicas à sua implementação.

### <a name="authorize-communication-between-ca-and-intune"></a>Autorizar a comunicação entre a AC e o Intune

Para permitir que um servidor SCEP de terceiros execute uma validação de desafio personalizada com o Intune, crie um aplicativo no Azure AD. Esse aplicativo concede direitos delegados para o Intune para validar solicitações do SCEP.

Verifique se você tem as permissões necessárias para registrar um aplicativo Azure AD. A seção [Permissões necessárias](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) lista as etapas.

**Etapa 1: Criar um aplicativo Azure AD**

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Azure Active Directory** > **Registros do aplicativo** > **Novo registro de aplicativo**.
3. Insira um nome e a URL de logon. Selecione **Aplicativo Web/API** para o tipo de aplicativo.
4. Selecione **Criar**.

[Integrar aplicativos com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) inclui algumas diretrizes sobre como criar um aplicativo, incluindo dicas sobre a URL e o nome.

**Etapa 2: Conceder permissões**

Depois de criar o aplicativo, forneça à API do Microsoft Intune as permissões necessárias:

1. No aplicativo Azure AD, abra **Configurações** > **Permissões Necessárias**.  
2. Selecione **Adicionar** > **Selecionar uma API** > selecione **API do Microsoft Intune** > **Selecionar**.
3. Em **Selecionar permissões**, escolha **Validação de desafio do SCEP** > **Selecionar**.
4. Selecione **Concluído** para salvar suas alterações.

**Etapa 3: Obter a ID do aplicativo e a chave de autenticação**

Em seguida, obtenha a ID e os valores de chave do aplicativo Azure AD. Os seguintes valores são necessários:

- ID do Aplicativo
- Chave de autenticação
- ID do locatário

**Para obter a ID do aplicativo e a chave de autenticação**:

1. No Azure AD, selecione o novo aplicativo (**Registros do aplicativo**).
2. Copie a **ID do Aplicativo** e armazene-a no código do aplicativo.
3. Em seguida, gere uma chave de autenticação. No aplicativo Azure AD, abra **Configurações** > **Chaves**.
4. Em **Senhas**, insira uma descrição e escolha a duração da chave. **Salve** suas alterações. Copie e salve o valor mostrado.

    > [!IMPORTANT]
    > Copie e salve essa chave imediatamente, pois ela não será exibida novamente. Esse valor de chave é necessário com a implementação de AC de terceiros. Examine as diretrizes sobre como ela deseja configurar a ID do Aplicativo, a Chave de Autenticação e a ID do Locatário.

A **ID do Locatário** é o texto de domínio após o sinal @ na conta. Por exemplo, caso sua conta seja `admin@name.onmicrosoft.com`, a ID do locatário será **name.onmicrosoft.com**.

[Obter a ID do aplicativo e a chave de autenticação](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key) lista as etapas para obter esses valores e fornece mais detalhes sobre aplicativos Azure AD.

### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Configurar e implantar um perfil de certificado SCEP
Como administrador, crie um perfil de certificado SCEP a ser direcionado a usuários ou dispositivos. Em seguida, atribua o perfil.

- [Criar um perfil de certificado SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Atribuir o perfil de certificado](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Removendo certificados

Quando você cancela o registro ou apaga o dispositivo, os certificados são removidos. Os certificados não são revogados.

## <a name="third-party-certification-authority-partners"></a>Parceiros de autoridade de certificação de terceiros
As seguintes autoridades de certificação de terceiros dão suporte ao Intune:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)
- [Versão de software livre do GitHub EJBCA](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)

Caso você tenha uma AC de terceiros interessada em integrar seu produto ao Intune, examine as diretrizes da API:

- [Repositório GitHub da API do SCEP para o Intune](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Diretrizes da API do SCEP para o Intune para ACs de terceiros](scep-libraries-apis.md)

## <a name="see-also"></a>Consulte também

- [Configurar perfis de certificado](certificates-scep-configure.md)
- [Repositório GitHub da API do SCEP para o Intune](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Diretrizes da API do SCEP para o Intune para ACs de terceiros](scep-libraries-apis.md)
