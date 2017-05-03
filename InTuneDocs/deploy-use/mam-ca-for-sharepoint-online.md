---
title: Configurar o acesso do aplicativo ao SharePoint Online
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Crie uma política de acesso condicional para o SharePoint Online para permitir apenas aplicativos com suporte para MAM
Este tópico fornece instruções passo a passo sobre como configurar o acesso condicional para o Exchange Online para permitir apenas aplicativos móveis com suporte para políticas de gerenciamento de aplicativos móveis (MAM) do Intune.

## <a name="configure-a-sharepoint-online-policy"></a>Configurar uma política do SharePoint Online
**Etapa 1:** entre no [Portal do Azure](https://portal.azure.com) que inclui o recurso de acesso do aplicativo. Caso você seja novo na experiência do portal do Azure, leia o tópico [Portal do Azure para políticas de MAM](azure-portal-for-microsoft-intune-mam-policies.md).

**Etapa 2:** acesse **Procurar > Intune > folha Gerenciamento de aplicativos móveis do Intune > Configurações** e na seção **acesso condicional**, escolha **SharePoint Online**.

![Captura de tela da folha de configurações mostrando a seção de acesso condicional e a folha do SharePoint Online aberta](../media/mam-ca-settings-spo.png)

**Etapa 3:** Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir que somente aplicativos com suporte para as políticas de MAM do Intune acessem o SharePoint Online. Quando você seleciona a opção para permitir somente aplicativos com suporte das políticas do Intune MAM, a lista dos aplicativos com suporte é exibida.

![Captura de tela da folha de aplicativos permitidos mostrando a lista de aplicativos](../media/mam-ca-spo-allowed-apps.png)

**Etapa 4:** para aplicar essa política aos usuários, abra a folha **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuário**. Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.

![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](../media/mam-ca-spo-restricted-groups.png)


**Etapa 5:** Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política. Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos. Na folha **SharePoint Online**, escolha **Grupos de usuários isentos**. Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários. Selecione os grupos que você deseja isentar dessa política.  

## <a name="modifying-an-existing-policy"></a>Modificar uma política existente
### <a name="adding-or-deleting-user-groups"></a>Adicionar ou excluir grupos de usuários
Para **excluir um grupo de usuários** da lista de **grupos de usuários com restrições**, abra a folha Grupos de usuários com restrições, realce o grupo de usuários que você deseja excluir e, em seguida, clique em … para ver a opção de exclusão. Escolha **Excluir** para remover o grupo de usuários da lista. Você pode seguir o mesmo procedimento para remover um grupo de usuários da lista do **grupo de usuários isentos**.


## <a name="next-steps"></a>Próximas etapas
[Configurar o acesso do aplicativo ao Exchange Online](mam-ca-for-exchange-online.md)

[Bloquear aplicativos que não têm autenticação moderna](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Consulte também

[Proteger dados de aplicativos com políticas de MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

