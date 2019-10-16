---
title: Usar autoridades de certificação (CAs) de terceiros com o SCEP no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, você pode adicionar uma AC (autoridade de certificação) de terceiros ou de fornecedor para emitir certificados para dispositivos móveis usando o protocolo SCEP. Nesta visão geral, um aplicativo do Azure AD (Azure Active Directory) concede permissões ao Microsoft Intune para validar certificados. Em seguida, use a ID do aplicativo, a chave de autenticação e a ID do locatário do aplicativo do AAD na configuração do servidor do SCEP para emitir certificados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b82124fe8f6da7116c8333e293f219d7c667f9c
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310922"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Adicionar autoridade de certificação de parceiro no Intune usando o SCEP

Use ACs (autoridades de certificação) de terceiros com o Intune. As ACs de terceiros podem provisionar dispositivos móveis com certificados novos ou renovados usando o protocolo SCEP e podem dar suporte a dispositivos Windows, iOS, Android e macOS.

Há duas partes para o uso desse recurso: API de software livre e as tarefas de administrador do Intune.

**Parte 1 – Usar uma API de software livre**  
A Microsoft criou uma API que é integrada ao Intune. Com essa API, é possível validar certificados, enviar notificações de sucesso ou falha e usar o SSL, especificamente, o alocador de soquete SSL, para se comunicar com o Intune.

A API está disponível no [repositório GitHub público de API do SCEP no Intune](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) para que você possa baixá-la e usá-la em suas soluções. Use essa API com servidores do SCEP de terceiros para executar uma validação de desafio personalizada no Intune antes do SCEP fornecer um certificado para um dispositivo.

[Integrar a solução de gerenciamento do SCEP no Intune](scep-libraries-apis.md) fornece mais detalhes sobre como usar a API, seus métodos e o teste da solução criada.

**Parte 2 – Criar o aplicativo e o perfil**  
Usando um aplicativo do Azure AD (Azure Active Directory), você pode delegar direitos para o Intune para manipular solicitações do SCEP provenientes de dispositivos. O aplicativo Azure AD inclui a ID do aplicativo e os valores de chave de autenticação usados na solução de API criada pelo desenvolvedor. Em seguida, os administradores criam e implantam perfis de certificados SCEP usando o Intune e podem exibir relatórios sobre o status da implantação nos dispositivos.

Este artigo fornece uma visão geral desse recurso de uma perspectiva do Administrador, incluindo a criação do aplicativo Azure AD.

## <a name="overview"></a>Visão geral

As seguintes etapas fornecem uma visão geral do uso do SCEP para certificados no Intune:

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

![Como o SCEP da autoridade de certificação de terceiros é integrado ao Microsoft Intune](./media/certificate-authority-add-scep-overview/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Configurar a integração de AC de terceiros

### <a name="validate-third-party-certification-authority"></a>Validar a autoridade de certificação de terceiros

Antes de integrar as autoridades de certificação de terceiros ao Intune, confirme se a AC que você está usando dá suporte ao Intune. [Parceiros de AC de terceiros](#third-party-certification-authority-partners) (neste artigo) inclui uma lista. Verifique também as diretrizes da autoridade de certificação para obter mais informações. A AC pode incluir instruções de instalação específicas à sua implementação.

### <a name="authorize-communication-between-ca-and-intune"></a>Autorizar a comunicação entre a AC e o Intune

Para permitir que um servidor SCEP de terceiros execute uma validação de desafio personalizada com o Intune, crie um aplicativo no Azure AD. Esse aplicativo concede direitos delegados para o Intune para validar solicitações do SCEP.

Verifique se você tem as permissões necessárias para registrar um aplicativo Azure AD. Confira [Permissões necessárias](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) na documentação do Azure AD.

#### <a name="create-an-application-in-azure-active-directory"></a>Crie um aplicativo no Azure Active Directory  

1. No [portal do Microsoft Azure](https://portal.azure.com), acesse **Azure Active Directory** > **Registros de aplicativo** e escolha **Novo registro**.  

2. Na página **Registrar um aplicativo**, especifique os detalhes a seguir:  
   - Na seção **Nome**, digite um nome significativo para o aplicativo.  
   - Na seção **Tipos de conta com suporte**, escolha **Contas em qualquer diretório organizacional**.  
   - Para a **URI de redirecionamento**, deixe o valor padrão da Web e especifique a URL de logon para o servidor SCEP de terceiros.  

3. Escolha **Registrar** para criar o aplicativo e abrir a página de visão geral para o novo aplicativo.  

4. Na página **Visão geral** do aplicativo, copie o valor de **ID Cliente do aplicativo** e registre-o para uso posterior. Você precisará desse valor mais tarde.  

5. No painel de navegação para o aplicativo, acesse **Certificados e segredos** em **Gerenciar**. Selecione o botão **Novo segredo do cliente**. Insira um valor em Descrição, escolha uma opção para **Expira** e escolha **Adicionar** para gerar um *valor* para o segredo do cliente. 
   > [!IMPORTANT]  
   > Antes de sair desta página, copie o valor do segredo do cliente e registre-o para ser usado posteriormente durante a implementação da CA de terceiros. Esse valor não é mostrado novamente. Lembre-se de examinar as diretrizes da CA terceirizada sobre como ela deseja configurar a ID do aplicativo, a chave de autenticação e a ID de locatário.  

6. Registre sua **ID de Locatário**. A ID de locatário é o texto do domínio após o sinal @ na conta. Por exemplo, caso sua conta seja *admin@name.onmicrosoft.com* , a ID do locatário será **name.onmicrosoft.com**.  

7. No painel de navegação do aplicativo, acesse **Permissões de APIs** em **Gerenciar** e escolha **Adicionar uma permissão**.  

8. Na página **Solicitar permissões de API**, escolha **Intune** e **Permissões do Aplicativo**. Marque a caixa de seleção **scep_challenge_provider** (validação de desafio do protocolo SCEP).  

   Escolha **Adicionar permissões** para salvar esta configuração.  

9. Permaneça na página **Permissões de APIs**, escolha **Conceder consentimento de administração para Microsoft** e escolha **Sim**.  
   
   O processo de registro do aplicativo no Azure AD foi concluído.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Configurar e implantar um perfil de certificado SCEP
Como administrador, crie um perfil de certificado SCEP a ser direcionado a usuários ou dispositivos. Em seguida, atribua o perfil.

- [Criar um perfil de certificado SCEP](certificates-profile-scep.md#create-a-scep-certificate-profile)

- [Atribuir o perfil de certificado](certificates-profile-scep.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Removendo certificados

Quando você cancela o registro ou apaga o dispositivo, os certificados são removidos. Os certificados não são revogados.

## <a name="third-party-certification-authority-partners"></a>Parceiros de autoridade de certificação de terceiros
As seguintes autoridades de certificação de terceiros dão suporte ao Intune:

- [Entrust Datacard](https://info.entrustdatacard.com/pki-eval-tool)
- [Versão de software livre do GitHub EJBCA](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [IDnomic](https://www.idnomic.com/)
- [Sectigo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)
- [Venafi](https://www.venafi.com/platform/enterprise-mobility)
- [SCEPman](https://azuremarketplace.microsoft.com/marketplace/apps/gluckkanja.scepman)

Caso você tenha uma AC de terceiros interessada em integrar seu produto ao Intune, examine as diretrizes da API:

- [Repositório GitHub da API do SCEP para o Intune](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Diretrizes da API do SCEP para o Intune para ACs de terceiros](scep-libraries-apis.md)

## <a name="see-also"></a>Consulte também

- [Configurar perfis de certificado](certificates-scep-configure.md)
- [Repositório GitHub da API do SCEP para o Intune](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Diretrizes da API do SCEP para o Intune para ACs de terceiros](scep-libraries-apis.md)
