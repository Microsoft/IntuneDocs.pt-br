---
title: "Portal do Azure para políticas de MAM | Microsoft Intune"
description: "Crie políticas de gerenciamento de aplicativo móvel usando o Portal do Azure. As políticas que você criar aqui podem ser aplicadas a dispositivos com ou sem registro no Intune."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 03410d1e82cfeb8d354ee1d010ada07ca86191bc
ms.openlocfilehash: e9d917401a8927099bdf8558e9f7e7185351f709


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Portal do Azure para políticas de MAM do Microsoft Intune

## <a name="use-the-azure-portal"></a>Usar o portal do Azure
O portal do Azure permite criar e gerenciar políticas de MAM (gerenciamento de aplicativo móvel).

O portal do Azure dá suporte à criação de políticas de MAM para:
- Aplicativos executados em dispositivos **registrados e gerenciados no Intune**.

- Aplicativos que são executados em dispositivos que **não são registrados** em nenhuma solução de MDM.
- Aplicativos executados em dispositivos que são **registrados em uma solução de MDM de terceiros**.

>[!IMPORTANT]


> Se estiver usando o console de administração do Intune para gerenciar seus dispositivos, você poderá criar uma política de MAM que dá suporte a aplicativos para dispositivos registrados no Intune usando o [console de administração do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> Você poderá não ver todas as configurações de política de MAM no console de administração do Intune. O portal do Azure é o novo console de administração para criar políticas de MAM. Se você criar políticas de MAM no console de administração do Intune e no portal do Azure, a política no portal do Azure será aplicada aos aplicativos e implantada para usuários.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Entre no portal do Azure e personalize sua página inicial

1.  Acesse o [portal do Azure](https://portal.azure.com) e entre com suas credenciais do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Captura de tela da página de credenciais do portal do Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Quando entrar com êxito, você verá o **Painel**. A página **Painel** pode ser personalizada.

    ![Captura de tela do painel do portal do Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  No menu **Procurar**, encontre **Intune**.![Captura de tela do menu Procurar com o Intune realçado](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Escolha **Intune** > **Gerenciamento de aplicativos móveis do Intune** > **Configurações**.

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]

    > Para fixar uma folha na **Tela inicial** , você pode usar a opção **Fixar** na folha. Clique no ícone de alfinete na **folha de gerenciamento de aplicativo móvel do Intune** para fixá-la à página **Inicial**.

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune com o ícone de pino realçado](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Captura de tela do painel com o bloco Intune fixado](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## <a name="next-steps"></a>Próximas etapas
[Preparar-se para configurar políticas de gerenciamento de aplicativo móvel](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


