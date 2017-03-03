---
title: "Inscrever-se para uma avaliação gratuita de 30 dias"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: como se inscrever para o Intune no Azure."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 29b33341b136c8e8d76b666f94a9f620212944c5
ms.lasthandoff: 02/18/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Inscreva-se para uma avaliação gratuita do Microsoft Intune para a versão prévia do Portal do Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Este artigo explica a inscrição para uma avaliação do Intune autônomo para a versão prévia do Portal do Azure. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. Visite a página [Inscrição do Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) e preencha o formulário para se inscrever para uma assinatura de avaliação.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Imagem da página de inscrição](./media/1-clicking-try.png)

 > [!TIP]
> Se a maioria de suas operações de TI e os usuários estiverem em uma localidade diferente que você, poderá ser útil selecionar essa localidade em **Onde sua empresa está localizada?**.

2. No final do processo de inscrição, você receberá uma mensagem com seu novos dados da conta. <br/> ![Imagem das informações de conta](./media/2-end-of-sign-up-process.png) <br/>Neste ponto, se você clicar em **Você estará pronto para começar**, será levado para o Centro de administração do Office 365, no qual poderá adicionar usuários ao seu ambiente de teste. <br/><br/>No entanto, se você desejar ir diretamente para a versão prévia do Portal do Intune Azure, abra uma nova janela do navegador e insira **https://portal.azure.com** na barra de endereços. Você será levado para a página de entrada do Azure, na qual poderá usar as credenciais fornecidas para entrar. Use esse endereço sempre que você desejar entrar em sua avaliação do Intune. <br/> ![Imagem da página de entrada do Portal do Azure](./media/azure-portal-signin.png)

Na primeira vez que entrar na versão prévia do Intune Azure, talvez você não o veja no painel do Azure. Para adicionar o serviço Intune ao painel do Azure:
1. Escolha **Mais serviços >** na lista de serviços do Azure à esquerda do painel e insira o **Intune** na caixa de pesquisa.
2. Escolha **Intune** na lista e selecione a estrela para adicionar o serviço à lista de serviços.<br/> ![Imagem da seleção do Intune na lista de serviços](./media/azure-add-intune1.png)
3. Escolha **Intune** na lista de serviços para abrir o painel do Intune.

Caso se inscreva para uma avaliação, você receberá uma mensagem de email com seus dados da conta no endereço de email fornecido durante o processo de inscrição. Isso confirma que sua avaliação está ativa.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Mantendo as experiências do administrador objetivas
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Há três portais que serão usados para a visualização do Intune Azure:
- O painel do Intune no Azure ([portal.azure.com](https://portal.azure.com)), no qual você pode explorar o [recursos do Intune no Portal do Azure](what-is-microsoft-intune.md).
- O Centro de administração do Office 365 ([portal.office.com](https://portal.office.com)), no qual você poderá adicionar e gerenciar usuários se não estiver usando o Azure Active Directory para isso. Você também pode gerenciar outros aspectos da sua conta, incluindo cobrança e suporte.
- O console de administração do Intune clássico ([manage.microsoft.com](https://manage.microsoft.com)), no qual você pode explorar os recursos que ainda não foram adicionados ao Azure.

Normalmente, você fará seu trabalho no painel do Intune, mostrado abaixo. Esse é o site no qual você pode configurar e gerenciar grupos, políticas, dispositivos e aplicativos.

É possível acessar o console de administração do Intune clássico por meio do painel, escolhendo o bloco **Abrir portal do Intune clássico**.

Para retornar à visualização do Intune Azure, insira https://portal.azure.com na barra de endereços do navegador e escolha **Intune** novamente na lista de serviços.

 ![Imagem do painel do Intune](./media/intune-azure-dashboard.png)


No entanto, você usará o Centro de administração do Office 365, mostrado abaixo, para adicionar e gerenciar os usuários e outros aspectos da sua conta, incluindo cobrança e suporte.

![Imagem do centro de administração do Office 365](./media/office-admin-center.png)

Para ir do Centro de administração do Office 365 para o painel do Intune, insira https://portal.azure.com na barra de endereços do navegador. Escolha **Intune** na lista de serviços.

Para voltar do Intune ao Centro de administração do Office 365, insira https://portal.office.com na barra de endereços do navegador. Se você já estiver conectado ao Intune, será levado diretamente para o Centro de administração do Office 365.

## <a name="next-steps"></a>Próximas etapas

### <a name="intune-azure-preview"></a>Visualização do Intune no Azure
Saiba mais sobre o Intune em [Introduction to Microsoft Intune in the Azure portal preview](what-is-microsoft-intune.md) (Introdução ao Microsoft Intune na visualização do Portal do Azure)
### <a name="classic-intune"></a>Intune clássico
Cenário de avaliação: [Avaliar o gerenciamento de dispositivo móvel no Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integração com outros produtos
Saiba mais sobre como usar as contas de usuário do Azure Active Directory com o Intune:
- [Requisitos de identidade](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Requisitos de sincronização de diretórios](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Requisitos da autenticação multifator](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Saiba mais sobre como usar o [Intune com System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)

