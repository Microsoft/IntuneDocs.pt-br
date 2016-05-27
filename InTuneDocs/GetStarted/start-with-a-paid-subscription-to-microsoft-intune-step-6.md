---
# required metadata

title: Criar políticas e publicar um aplicativo | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Criar políticas e publicar um aplicativo
As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos. Você pode aprender mais em [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) e [Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Você pode executar dois tipos de instalações de aplicativos usando o Intune. A primeira é uma **instalação requerida**, que implanta o aplicativo automaticamente em computadores gerenciados. A outra é uma **instalação disponível**, que implanta o aplicativo ou um link para o aplicativo, o portal da empresa do Intune para que os usuários possam optar por instalá-lo em seus computadores ou em seus dispositivos móveis.

<!-- this section really isn't necessary and confuses a lot of people because most mobile device apps aren't licensed this way (and our licensing/reporting features aren't super helpful). I think it's best to avoid this during a quick start guide.

Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app. The Licenses workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft software that was purchased by other means. You can then create license reports that display managed license usage information throughout your company to stay informed of license usage activity.
-->

As seguintes etapas ajudam você a configurar uma política de configuração de dispositivo móvel e uma política de firewall de computador Windows, além de configurar o Skype como uma instalação disponível para dispositivos móveis depois de eles serem registrados.

> [!TIP]
> Depois de você adicionar e implantar uma nova política, todos os usuários ou dispositivos do grupo no qual você implantou a política herdam as configurações como sua política de linha de base. Você poderá sempre analisar e editar os detalhes dessas políticas posteriormente usando o espaço de trabalho de política.


## Criar e implantar uma política de segurança de dispositivo móvel

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com/).

2.  No painel à esquerda, escolha o ícone **Política**.

    ![admin-console-policy-workspace](./media/policy.png)

3.  Na lista **Tarefas**, na página **Visão Geral de Políticas**, escolha **Adicionar Política**.

4.  Na lista de políticas, expanda a plataforma para a qual você deseja criar uma política e selecione **Configuração Geral** > **Criar e Implantar uma Política com as Configurações Recomendadas** > **Criar Política**.

5.  Quando solicitado, **Selecione os grupos nos quais você deseja implantar essa política**, selecione **Usuários do Intune** (o grupo criado na etapa anterior) na lista de grupos disponíveis, escolha **Adicionar** > **OK**.

Sua política aparece na lista de políticas de configuração e foi implantada no grupo **Usuários do Intune**. Clique duas vezes na política para exibir suas configurações.

## Publicar o aplicativo do Skype para dispositivos móveis

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha o ícone **Aplicativos** e, em seguida, escolha **Aplicativos** > **Adicionar Aplicativo**. Quando solicitado, insira as credenciais da sua conta do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > Ao iniciar o **Intune Software Publisher** pela primeira vez, um pequeno atraso ocorrerá durante a instalação do aplicativo.

2.  Examine o aviso de segurança e selecione **Executar**.

3.  Na página **Antes de começar**, clique em **Avançar**.

4.  Na página **Configuração de software**, em **Selecionar como esse software será disponibilizado para os dispositivos**, escolha **Link externo**.

5.  Insira o link externo para o software em **Especificar a URL** e clique em **Avançar**. Certifique-se de iniciar a URL com **http://**. Para o aplicativo do Skype, use o link abaixo que corresponda à plataforma de dispositivo móvel que você está usando:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 ou Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Na página **Descrição do software**, forneça as informações que deseja que os usuários vejam no portal da empresa para o software e clique em **Avançar**. As configurações a seguir estão disponíveis (este exemplo refere-se ao Skype):

    -   **Editor:** Insira o nome do editor, "Microsoft"

    -   **Nome:** Insira **Skype**

    -   **Descrição:** Insira uma descrição para o software, como **Aplicativo de comunicação do Skype**

    -   **Categoria:** Selecione a categoria mais adequada a esse software, como **Colaboração**

    -   **Exibir como um aplicativo em destaque e salientá-lo no portal de empresa:** Selecione esta opção para exibir o aplicativo em destaque no portal da empresa em dispositivos móveis.

    -   **Ícone:** defina se deseja associar um ícone ao software. O tamanho máximo do ícone opcional é de 250 x 250 pixels e o tamanho recomendado é de 32 x 32 pixels.

7.  Na página **Resumo**, verifique as informações do software e, em seguida, escolha **Carregar**. Selecione **Fechar** para sair do assistente.

8.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Aplicativos** > **Aplicativos** > **Skype** > **Gerenciar Implantação**.

9. Na página **Selecionar Grupos**, selecione **Usuários do Intune** para implantar o software nesse grupo de usuários e clique em **Adicionar** > **Avançar**.

10. Na página **Ação de implantação** , selecione **Instalação disponível** na coluna **Aprovação** de seu grupo.

11. Escolha **Concluir**.

O aplicativo do Skype agora está disponível para instalação em dispositivos móveis por meio do portal da empresa, mas primeiro você precisa instalar o software [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] em computadores e dispositivos móveis.


### Próximas etapas
Parabéns! Você acabou de concluir a etapa 6 do *Guia de início rápido do Intune*.

>[!div class="step-by-step"]

>[&larr; **Organizar usuários e dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personalizar o Portal da Empresa** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  


<!--HONumber=May16_HO1-->


