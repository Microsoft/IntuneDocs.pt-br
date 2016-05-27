---
# required metadata

title: Portal do Azure para políticas de MAM | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Portal do Azure para políticas de MAM do Microsoft Intune
## Acessando o portal do Azure
O **portal do Azure** permite criar e gerenciar políticas de gerenciamento de aplicativos móveis.

O portal do Azure dá suporte à criação de políticas de MAM para:
- Aplicativos que são executados em dispositivos **registrados e gerenciados pelo Intune**.
- Aplicativos que são executados em dispositivos que **não são registrados** em nenhuma solução de MDM.
- Aplicativos que são executados em dispositivos que são **registrados em uma solução de MDM de terceiros**.

Se no momento você estiver usando o **console de administração do Intune** para gerenciar seus dispositivos, poderá criar uma política de MAM que dê suporte a aplicativos para dispositivos registrados no Intune usando o [console de administração do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
>[!IMPORTANT]
> Você não poderá ver todas as configurações de política de MAM no console de administração do Intune. O portal do Azure é o novo console de administração para criar políticas de MAM.

## Faça logon no portal do Azure e personalize sua página inicial

1.  Acesse o [portal do Azure](https://portal.azure.com) e entre com suas credenciais do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Captura de tela da página de logon do portal do Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Quando você estiver entrado com êxito, verá o **Painel**. A página **Painel** vem com um conjunto de blocos padrão que você pode remover e adicionar para personalizar a página.

    ![Captura de tela do painel do portal do Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  No menu **Procurar**, localize **Intune**.![Captura de tela do menu Procurar com Intune realçado](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Clique em **Intune > Gerenciamento de aplicativos móveis do Intune > Configurações**.

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Para fixar uma folha na **Tela inicial** , você pode usar a opção **Fixar** na folha.  Clique no ícone de pino na **folha de gerenciamento de aplicativos móveis do Intune**, para fixá-la na **Tela inicial** .

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune com o ícone de pino realçado](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Captura de tela do painel com o bloco Intune fixado](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Próximas etapas
[Preparar-se para configurar políticas de gerenciamento de aplicativos móveis](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


