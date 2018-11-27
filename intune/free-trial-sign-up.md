---
title: Início Rápido – Experimente o Microsoft Intune gratuitamente
titlesuffix: ''
description: Neste início rápido você criará uma assinatura de avaliação gratuita, entenderá as configurações compatíveis e os requisitos de rede e, opcionalmente, configurará seu nome de domínio.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 827766d76a66ea7d69ebbd3ba77efe785689e7e2
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189173"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Início Rápido: experimente o Microsoft Intune gratuitamente 

O Microsoft Intune ajuda você a proteger os dados corporativos da sua força de trabalho por meio do gerenciamento de dispositivos e aplicativos. Neste início rápido, você criará uma assinatura gratuita para experimentar o Intune em um ambiente de teste.

O Intune fornece MDM (gerenciamento de dispositivo móvel) e o MAM (gerenciamento de aplicativo móvel) de um serviço seguro baseado em nuvem que é administrado usando o portal do Microsoft Azure. Usando o Intune, você garante que os recursos corporativos da sua força de trabalho (dados, dispositivos e aplicativos) estejam devidamente configurados, acessados e atualizados, cumprindo os requisitos e as políticas de conformidade da sua empresa. 

## <a name="prerequisites"></a>Pré-requisitos
Antes de configurar o Microsoft Intune, examine os requisitos a seguir:

   - [Navegadores e sistemas operacionais compatíveis](supported-devices-browsers.md) 
   - [Largura de banda e requisitos de configuração de rede](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Inscrever-se para uma avaliação gratuita do Microsoft Intune

Experimentar o Intune gratuitamente por 30 dias. Se você já tem uma conta corporativa ou de estudante, **entre** com essa conta e adicione o Intune à sua assinatura. Caso contrário, você pode **inscrever-se** para uma nova conta a fim de usar o Intune para sua organização.

> [!IMPORTANT]
> Você não pode combinar uma conta corporativa ou de estudante depois de se inscrever para uma nova conta.

1. Acesse a página [Avaliação do Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2019088) e preencha o formulário.

    ![Captura de tela da página da Web de inscrição de conta de Avaliação do Microsoft Intune](./media/account-sign-up-site-full-browser.png)

    Se a maioria das suas operações de TI e usuários estiver em uma localidade diferente da sua, poderá ser útil selecionar essa localidade em **País ou região**. O Azure usa as informações regionais para fornecer os serviços adequados. Não é possível alterar essa configuração posteriormente.

2. Crie uma conta usando o nome da sua empresa seguido de **.onmicrosoft.com**. 

    ![Captura de tela da página da Web de inscrição de conta de Avaliação do Microsoft Intune](./media/account-sign-up-site-user-id.png)

    Se a organização tiver seu próprio domínio personalizado que deseja usar sem **.onmicrosoft.com**, você poderá alterá-lo no Portal de Administração do Office 365 descrito posteriormente neste artigo.

3. Veja suas novas informações de conta no fim do processo de criação de conta.

    ![Imagem das suas informações de conta](./media/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Entrar no Portal do Azure

1. Abra uma nova janela do navegador e digite **https://portal.azure.com** na barra de endereços. 
2. Use as credenciais fornecidas nas etapas acima para entrar.

    ![Imagem da página de entrada do Portal do Azure](./media/azure-portal-signin.png)

3. Para ver o Microsoft Intune no portal do Azure, selecione **Todos os serviços** na barra lateral no lado esquerdo da página.
4. Pesquise **Microsoft Intune** na caixa de filtro e selecione-o.
5. Selecione a **estrela** para adicionar o Intune ao final da lista de serviços favoritos e abra o painel do Intune.

Ao inscrever-se para uma avaliação, você receberá uma mensagem de email contendo suas informações de conta e o endereço de email fornecido durante o processo de inscrição. Isso confirma que sua avaliação está ativa.

> [!TIP]
> Ao trabalhar com o portal do Azure, você pode obter resultados melhores trabalhando com um navegador no modo normal, em vez de modo privado.

## <a name="set-the-mdm-authority-to-intune"></a>Definir a autoridade de MDM para o Intune

Depois de entrar no portal do Azure e selecionar o Intune, você poderá ver uma faixa laranja indicando que você ainda não definiu a autoridade de MDM. A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. A autoridade de MDM deve ser definida antes que os usuários possam registrar dispositivos para gerenciamento.

Para definir a autoridade de MDM para o Intune, siga estas etapas.

1. Abra uma nova janela do navegador e digite **https://portal.azure.com** na barra de endereços. 
2. Escolha **Todos os serviços** > **Microsoft Intune**.
3. Selecione a faixa que indica que você não habilitou o gerenciamento de dispositivo ou, se você não localizar a faixa imediatamente, selecione **Registro de dispositivo**. A folha **Escolher Autoridade de MDM** será exibida se você ainda não tiver habilitado o gerenciamento de dispositivo.

    > [!NOTE]
    > A faixa laranja somente será exibida se você ainda não tiver definido a autoridade de MDM.

    ![Imagem da folha Escolher Autoridade de MDM](./media/choose-mdm-authority.png) 

4. Em **Escolher Autoridade de MDM**, defina sua autoridade MDM como **Autoridade de MDM do Intune**.

Para obter mais informações sobre a autoridade de MDM, confira [Definir autoridade de gerenciamento de dispositivo móvel](mdm-authority-set.md).

## <a name="configure-your-custom-domain-name-optional"></a>Configurar o nome de domínio personalizado (opcional)

Como mencionado acima, se sua organização tiver seu próprio domínio personalizado que deseja usar sem **.onmicrosoft.com**, você poderá alterá-lo no Portal de Administração do Office 365. Você adicionará, confirmará e configurará seu nome de domínio personalizado.  

> [!IMPORTANT]
> Não será possível renomear ou remover o nome de domínio **onmicrosoft.com** inicial. Você pode adicionar, verificar ou remover os nomes de domínio personalizados usados com o Intune para manter sua identidade de empresa limpa.

1. Acesse o [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) e entre usando sua conta de administrador.

2. No painel de navegação, escolha **Configuração** > **Domínios** > **Adicionar domínio**.

3. Digite seu nome de domínio personalizado. Em seguida, selecione **Avançar**.

   ![Captura de tela do Centro de Administração do Office 365 com a opção Configurações > Domínios selecionada e um novo nome de domínio sendo adicionado](./media/domain-custom-add.png)

4. Verifique se que você é o proprietário do domínio inserido anteriormente. 
    
    Selecionar **enviar código por email** enviará um email para o contato registrado do seu domínio. Depois de receber o email, copie o código e insira-o no campo de rotulado **Digite seu código de verificação aqui**. Se o código de verificação for correspondente, o domínio será adicionado ao seu locatário. O email exibido pode não parecer familiar. Alguns registradores ocultam o endereço de email real que foi fornecido quando o domínio foi registrado.

   ![Captura de tela do Centro de Administração do Office 365 – Confirmar o nome de domínio que está sendo adicionado](./media/domain-custom-verify.png)

   > [!NOTE]
   > Para obter os detalhes de verificação de registro TXT, consulte [Criar registros DNS em qualquer provedor de hospedagem de DNS para o Office 365](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Experiências de administrador

Há dois portais de que você pode usar:
- O painel do Intune no Azure ([portal.azure.com](https://portal.azure.com)) é o local onde você poderá explorar as [funcionalidades do Intune](what-is-intune.md). Normalmente, você fará seu trabalho no painel do Intune.
- O Centro de Administração do Office 365 ([portal.office.com](https://portal.office.com)) é o local onde você poderá adicionar e gerenciar usuários se não estiver usando o Azure Active Directory para isso. Você também pode gerenciar outros aspectos da sua conta, incluindo cobrança e suporte.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou uma assinatura gratuita para experimentar o Intune em um ambiente de teste. Para obter mais informações sobre a configuração do Intune, confira [Configurar o Intune](setup-steps.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início Rápido: criar um usuário e atribuir uma licença a ele](quickstart-create-user.md)
