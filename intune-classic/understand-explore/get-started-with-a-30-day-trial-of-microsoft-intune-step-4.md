---
title: "Criar políticas e publicar um aplicativo em usuários | Microsoft Docs"
description: "Como criar políticas e publicar um aplicativo quando você se inscrever para uma avaliação gratuita de 30 dias do Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 0e836571b869e7a32b19968da1d78035a6bae7f2
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---


# <a name="create-policies-and-publish-an-app-to-evaluation-users"></a>Criar políticas e publicar um aplicativo para usuários de avaliação

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos. Se você estiver planejando usar o Intune em dispositivos que configura para uso em produção após a avaliação, será absolutamente essencial que você siga as instruções em [Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Você pode executar dois tipos de instalações de aplicativos usando o Intune. A primeira é uma **instalação obrigatória**, que implanta automaticamente o aplicativo em dispositivos gerenciados. A outra é uma **instalação disponível**, que implanta o aplicativo ou um link para o aplicativo, no Portal da Empresa do Intune para que os usuários possam optar por instalá-lo em seus computadores ou em seus dispositivos móveis.

Antes de usar o Intune para implantar aplicativos, certifique-se de ter as licenças apropriadas para publicar, distribuir e usar o aplicativo. O espaço de trabalho **Licenças** permite adicionar e gerenciar informações de contrato de licença para aplicativos ou software adquiridos por meio de contratos de Licenciamento por Volume da Microsoft e para aplicativos e softwares, da Microsoft ou não, que tenham sido adquiridos por outros meios. Você pode criar relatórios de licenças que exibam informações de uso de licença gerenciado em toda a empresa para se manter informado sobre a atividade de uso da licença.

Nestas etapas, você vai configurar uma política de configuração de dispositivo móvel e uma política de firewall de computador do Windows, além de configurar o Skype como uma instalação disponível para dispositivos móveis depois de eles serem registrados. Depois de você adicionar e implantar uma nova política, todos os usuários ou dispositivos do grupo no qual você implantou a política herdam as configurações como sua política de linha de base. Você poderá sempre examinar e editar os detalhes dessas políticas posteriormente usando o espaço de trabalho **Política** no console de administração.

## <a name="create-and-deploy-a-mobile-device-configuration-policy"></a>Criar e implantar uma política de segurança de dispositivo móvel

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com/).

2.  No painel à esquerda, escolha o ícone **Política**.

3.  Na lista **Tarefas**, na página **Visão Geral de Políticas**, escolha **Adicionar Política**.

4.  Na lista de políticas, expanda a plataforma para a qual deseja criar uma política, selecione **Configuração Geral**, escolha **Criar e Implantar uma Política Personalizada** e escolha **Criar Política**.

5.  Quando for solicitado para **Selecionar os grupos aos quais você deseja implantar essa política**, selecione **Meus Usuários de Avaliação** na lista e escolha **Adicionar** &gt; **OK**.

Sua política aparece na lista de políticas de configuração e foi implantada no grupo **Meus usuários de avaliação**. Clique duas vezes na política para exibir suas configurações.

## <a name="publish-the-skype-app-for-mobile-devices"></a>Publicar o aplicativo do Skype para dispositivos móveis

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha o ícone **Aplicativos** e, em seguida, escolha **Aplicativos** &gt; **Adicionar Aplicativo**. Quando solicitado, insira suas credenciais do Intune.

    > [!NOTE]
    > Ao iniciar o **Intune Software Publisher** pela primeira vez, um pequeno atraso ocorrerá durante a instalação do aplicativo.

2.  Examine o aviso de segurança e selecione **Executar**.

3.  Na página **Antes de começar**, clique em **Avançar**.

4.  Na página **Configuração de software**, em **Selecionar como esse software será disponibilizado para os dispositivos**, selecione **Link externo**.

5.  Insira o link externo para o software em **Especificar a URL** e clique em **Avançar**. Certifique-se de iniciar a URL com **https://**. Para o aplicativo do Skype, use o link abaixo que corresponda à plataforma de dispositivo móvel que você está usando:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8.1:** [http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Na página **Descrição do software**, forneça as informações que deseja que os usuários vejam no Portal da Empresa para o software e clique em **Avançar**. As configurações a seguir estão disponíveis (este exemplo refere-se ao Skype):

    -   **Editor:** insira o nome do editor, **Microsoft**

    -   **Nome:** Insira **Skype**

    -   **Descrição:** Insira uma descrição para o software, como **Aplicativo de comunicação do Skype**

    -   **Categoria:** Selecione a categoria mais adequada a esse software, como **Colaboração**

    -   **Exibir isto como um aplicativo em destaque e realçá-lo no portal da empresa:** selecione esta opção para exibir o aplicativo em destaque no Portal da Empresa em dispositivos móveis.

    -   **Ícone:** (Opcional) Escolha se deseja associar um ícone ao software. O tamanho máximo do ícone é de 250 x 250 pixels, mas o tamanho do ícone recomendado é 32 x 32 pixels.

7.  Na página **Resumo**, verifique as informações do software e, em seguida, escolha **Carregar**. Selecione **Fechar** para sair do assistente.

8.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Aplicativos** &gt; **Aplicativos** &gt; **Skype** &gt; **Gerenciar Implantação**.

9. Na página **Selecionar grupos**, selecione **Meus Usuários de Avaliação** para implantar o software a esse grupo de usuários e escolha **Adicionar** &gt; **Avançar**.

10. Na página **Ação de implantação**, selecione **Instalação disponível** na coluna **Aprovação** de seu grupo.

11. Escolha **Concluir**.

## <a name="install-the-skype-app"></a>Instalar o aplicativo do Skype
Abra o Portal da Empresa no dispositivo móvel, escolha **Aplicativos**e, em seguida, instale o Microsoft Skype.

Isso conclui o guia de gerenciamento de dispositivos móveis do Intune, mas você pode aprender mais sobre o Intune seguindo os links na seção Próximas etapas.
## <a name="next-steps"></a>Próximas etapas
Saber mais sobre outros [recursos do Intune](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)

Ler sobre as [formas comuns para usar o Intune](common-ways-to-use-intune.md)

Converter em uma [assinatura paga](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md)

