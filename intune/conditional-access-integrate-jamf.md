---
title: Integrar o Jamf Pro ao Microsoft Intune para fins de conformidade
titleSuffix: Microsoft Intune
description: Use políticas de conformidade do Microsoft Intune com Acesso Condicional do Azure Active Directory para ajudar a proteger dispositivos gerenciados pelo Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d25012790322491a9038f0bcf9349434d5a45b8d
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251089"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrar o Jamf Pro ao Intune para fins de conformidade

Aplica-se a: Intune no portal do Azure

Caso sua organização use o [Jamf Pro](https://www.jamf.com) para gerenciar dispositivos Mac dos usuários finais, use as políticas de conformidade do Microsoft Intune com o Acesso Condicional do Azure Active Directory para garantir que os dispositivos em sua organização estejam em conformidade.

## <a name="prerequisites"></a>Pré-requisitos

Você precisa do seguinte para configurar o Acesso Condicional com o Jamf Pro:

- Jamf Pro 10.1.0 ou mais recente
- [Aplicativo Portal da Empresa para macOS](https://aka.ms/macoscompanyportal)
- Dispositivos macOS com OS X 10.11 Yosemite ou mais recente

## <a name="connecting-intune-to-jamf-pro"></a>Conectar o Intune ao Jamf Pro

Para conectar o Intune ao Jamf Pro:

1. Crie um aplicativo no Azure
2. Permitir a integração do Intune ao Jamf Pro
3. Configurar o Acesso Condicional no Jamf Pro

## <a name="create-an-application-in-azure-active-directory"></a>Crie um aplicativo no Azure Active Directory

1. No [portal do Microsoft Azure](https://portal.azure.com), acesse **Azure Active Directory** > **Registros de aplicativo** e escolha **Novo registro**. 

2. Na página **Registrar um aplicativo**, especifique os detalhes a seguir:
   - Na seção **Nome**, insira um nome significativo para o aplicativo, por exemplo **Acesso condicional Jamf**.
   - Na seção **Tipos de conta com suporte**, escolha **Contas em qualquer diretório organizacional**. 
   - Para a **URI de Redirecionamento**, deixe o valor padrão da Web e especifique a URL para sua instância do Jamf Pro.  

3. Escolha **Registrar** para criar o aplicativo e abrir a página de visão geral para o novo aplicativo.  

4. Na página **Visão geral** do aplicativo, copie o valor de **ID Cliente do aplicativo** e registre-o para uso posterior. Você precisará desse valor em procedimentos futuros.  

5. Escolha **Certificados e segredos** em **Gerenciar**. Selecione o botão **Novo segredo do cliente**. Insira um valor em **Descrição**, escolha uma opção para **Expira** e escolha **Adicionar**.

   > [!IMPORTANT]  
   > Antes de sair desta página, copie o valor do segredo do cliente e guarde-o para uso posterior. Você precisará desse valor em procedimentos futuros. Esse valor só ficará disponível novamente caso você refaça o registro do aplicativo.  

6. Escolha **Permissões de APIs** em Gerenciar.  Escolha as permissões existentes e depois **Remover Permissão** para excluir essas permissões. É preciso remover todas as permissões existentes, já que você adicionará uma nova permissão e o aplicativo funciona apenas com a permissão exata necessária.  

7. Para atribuir uma nova permissão, escolha **Adicionar uma permissão**. Na página **Solicitar permissões de API**, escolha **Intune** e **Permissões do Aplicativo**. Marque a caixa de seleção **update_device_attributes**.  

   Escolha **Adicionar Permissão** para salvar esta configuração.  

8. Na página **Permissões de APIs**, escolha **Conceder consentimento de administrador para Microsoft** e, em seguida, escolha Sim.  

   O processo de registro do aplicativo no Azure AD foi concluído.


    > [!NOTE]
    > Se o segredo do cliente expirar, você deverá criar um novo segredo do cliente no Azure e, depois, atualizar os dados do Acesso Condicional no Jamf Pro. O Azure permite que você tenha o segredo antigo e a nova chave ativos para evitar interrupções no serviço.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Permitir a integração do Intune ao Jamf Pro

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e vá para **Microsoft Intune** > **Conformidade do Dispositivo** > **Gerenciamento de dispositivos do parceiro**.

2. Habilite o Conector de Conformidade para o Jamf colando a ID do Aplicativo salva no procedimento anterior no campo **ID do Aplicativo do Azure Active Directory para o Jamf**.

3. Selecione **Salvar**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Configurar a Integração do Microsoft Intune no Jamf Pro

1. No Jamf Pro, navegue até **Gerenciamento Global** > **Acesso Condicional**. Clique no botão **Editar** na guia **Integração do Microsoft Intune**.

2. Marque a caixa de seleção **Habilitar a Integração do Microsoft Intune**.

3. Forneça as informações necessárias sobre seu locatário do Azure, incluindo **Local**, **Nome de domínio**, a **Identificação do Aplicativo** e o *segredo do cliente* salvo durante a criação do aplicativo no Azure AD.  

4. Selecione **Salvar**. O Jamf Pro testará suas configurações e verificará o êxito.

## <a name="set-up-compliance-policies-and-register-devices"></a>Configurar políticas de conformidade e registrar dispositivos

Depois de configurar a integração entre o Intune e o Jamf, você precisará [aplicar políticas de conformidade aos dispositivos gerenciados pelo Jamf](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Próximas etapas

- [Aplicar políticas de conformidade aos dispositivos gerenciados por Jamf](conditional-access-assign-jamf.md)
- [Dados enviados pelo Jamf ao Intune](data-jamf-sends-to-intune.md)
