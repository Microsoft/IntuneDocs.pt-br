---
title: "Portal do Azure para políticas de MAM | Microsoft Docs"
description: "Crie políticas de gerenciamento de aplicativo móvel usando o Portal do Azure. As políticas que você criar aqui podem ser aplicadas a dispositivos com ou sem registro no Intune."
keywords: 
author: andredm7
ms.author: andredm
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
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: fa8d839da1cf0b2d207edc0b28de8a714ba0df02


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Portal do Azure para políticas de MAM do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Portal do Azure é usado para criar e gerenciar políticas de MAM (gerenciamento de aplicativo móvel) para:

- Aplicativos executados em dispositivos **registrados e gerenciados no Intune**.

- Aplicativos que são executados em dispositivos que **não são registrados** em nenhuma solução de MDM.
- Aplicativos executados em dispositivos que são **registrados em uma solução de MDM de terceiros**.

>[!IMPORTANT]
> O Portal do Azure é o novo console de administração para criar políticas de MAM, mas você também pode criar uma política de MAM que dá suporte a aplicativos para dispositivos registrados no Intune usando o [console do administrador do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) para cenários de MDM.

> Você poderá não ver todas as configurações de política de MAM disponíveis no console de administrador do Intune. Além disso, se você criar políticas de MAM no console do administrador do Intune e no portal do Azure, as políticas criadas no Portal do Azure substituirão aquelas criadas no console do administrador do Intune. Nesse cenário, as políticas de MAM do Portal do Azure serão aplicadas aos aplicativos e implantadas para os usuários.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Entre no portal do Azure e personalize sua página inicial

1.  Acesse o [portal do Azure](https://portal.azure.com) e entre com suas credenciais do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Captura de tela da página de credenciais do portal do Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Quando entrar com êxito, você verá o **Painel**. A página **Painel** pode ser personalizada.

    ![Captura de tela do painel do portal do Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  No menu **Procurar**, encontre o **Intune**.

    ![Captura de tela do menu Procurar com o Intune realçado](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Escolha **Intune** > **Gerenciamento de aplicativos móveis do Intune** > **Configurações**.

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Opcional): para fixar uma folha **Página Inicial**, você pode usar a opção **fixar** na folha. Clique no ícone de alfinete na **folha de gerenciamento de aplicativo móvel do Intune** para fixá-la à página **Inicial**.

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune com o ícone de pino realçado](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Captura de tela do painel com o bloco Intune fixado](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Próximas etapas
[Preparar-se para configurar políticas de gerenciamento de aplicativo móvel](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


