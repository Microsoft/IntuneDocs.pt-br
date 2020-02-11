---
title: Início Rápido – Experimente o Microsoft Intune gratuitamente
titleSuffix: ''
description: Neste início rápido você criará uma assinatura de avaliação gratuita, entenderá as configurações compatíveis e os requisitos de rede e, opcionalmente, configurará seu nome de domínio.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/16/2020
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e1baf0b4273a9074ac7172c08240a8e3c3a9d7fa
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76541108"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Início Rápido: Experimente o Microsoft Intune gratuitamente

O Microsoft Intune ajuda você a proteger os dados corporativos da sua força de trabalho por meio do gerenciamento de dispositivos e aplicativos. Neste início rápido, você criará uma assinatura gratuita para experimentar o Intune em um ambiente de teste.

O Intune fornece o MDM (gerenciamento de dispositivo móvel) e o MAM (gerenciamento de aplicativo móvel) por um serviço seguro baseado em nuvem e administrado no Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft. Usando o Intune, você garante que os recursos corporativos da sua força de trabalho (dados, dispositivos e aplicativos) estejam devidamente configurados, acessados e atualizados, cumprindo os requisitos e as políticas de conformidade da sua empresa.

## <a name="prerequisites"></a>Pré-requisitos
Antes de configurar o Microsoft Intune, examine os requisitos a seguir:

- [Navegadores e sistemas operacionais compatíveis](supported-devices-browsers.md)
- [Largura de banda e requisitos de configuração de rede](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Inscrever-se para uma avaliação gratuita do Microsoft Intune

Experimentar o Intune gratuitamente por 30 dias. Se você já tem uma conta corporativa ou de estudante, **entre** com essa conta e adicione o Intune à sua assinatura. Caso contrário, você pode **inscrever-se** para uma nova conta a fim de usar o Intune para sua organização.

> [!IMPORTANT]
> Você não pode combinar uma conta corporativa ou de estudante depois de se inscrever para uma nova conta.

1. Acesse a página [Avaliação do Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2019088) e preencha o formulário.

    ![Captura de tela da página da Web de inscrição de conta de Avaliação do Microsoft Intune](./media/free-trial-sign-up/account-sign-up-site-full-browser.png)

    Se a maioria das suas operações de TI e usuários estiver em uma localidade diferente da sua, poderá ser útil selecionar essa localidade em **País ou região**. O Azure usa as informações regionais para fornecer os serviços adequados. Não é possível alterar essa configuração posteriormente.

2. Crie uma conta usando o nome da sua empresa seguido de **.onmicrosoft.com**. 

    ![Captura de tela do novo processo de credencial da conta de avaliação do Intune](./media/free-trial-sign-up/account-sign-up-site-user-id.png)

    Se sua organização tiver seu próprio domínio personalizado que você deseja usar sem **.onmicrosoft.com**, será possível alterá-lo no Centro de administração do Microsoft 365 descrito posteriormente neste artigo.

3. Veja suas novas informações de conta no fim do processo de criação de conta.

    ![Imagem das suas informações de conta](./media/free-trial-sign-up/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Entre no Intune no Gerenciador de Ponto de Extremidade da Microsoft

Se você ainda não entrou no portal, complete as etapas a seguir:

1. Abra uma nova janela do navegador e digite **https://devicemanagement.microsoft.com** na barra de endereços. 
2. Use a ID de usuário recebida nas etapas acima para entrar ( *yourID@yourdomain* .onmicrosoft.com).

    ![Imagem da página de entrada do portal](./media/free-trial-sign-up/azure-portal-signin.png)

Ao inscrever-se para uma avaliação, você receberá uma mensagem de email contendo suas informações de conta e o endereço de email fornecido durante o processo de inscrição. Isso confirma que sua avaliação está ativa.

> [!TIP]
> Ao trabalhar com o Gerenciador de Ponto de Extremidade, você pode obter resultados melhores trabalhando com um navegador no modo normal, em vez de usar o modo privado.

## <a name="confirm-the-mdm-authority-in-intune"></a>Confirmar a autoridade de MDM no Intune

Por padrão, a autoridade de MDM é definida quando você obtém a sua avaliação gratuita. Você pode confirmar se a autoridade de MDM está definida com as seguintes etapas:

1. Se você ainda não tiver entrado, faça logon com o Gerenciador de Ponto de Extremidade da Microsoft.
2. Clique em **Administração de locatários**.
3. Exiba os detalhes do locatário. A **Autoridade de MDM** deve estar definida para o **Microsoft Intune**.

Se, depois de entrar no Microsoft Endpoint Manager, for exibida uma faixa laranja indicando que a autoridade de MDM ainda não foi definida, você poderá ativá-la no momento. A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. A autoridade de MDM deve ser definida antes que os usuários possam registrar dispositivos para gerenciamento.

### <a name="to-set-the-mdm-authority-to-intune-follow-these-steps"></a>Para definir a autoridade de MDM para o Intune, siga estas etapas:

1. Abra uma nova janela do navegador e digite **https://portal.azure.com** na barra de endereços. 
2. Escolha **Todos os serviços** > **Microsoft Intune**.
3. Selecione a faixa que indica que você não habilitou o gerenciamento de dispositivo ou, se você não localizar a faixa imediatamente, selecione **Registro de dispositivo**. A folha **Escolher Autoridade de MDM** será exibida se você ainda não tiver habilitado o gerenciamento de dispositivo.

    > [!NOTE]
    > Se você tiver definido a Autoridade MDM, verá o valor de autoridade MDM na folha **Registro de dispositivo**. A faixa laranja somente será exibida se você ainda não tiver definido a autoridade de MDM. 

    ![Imagem da folha Escolher Autoridade de MDM](./media/free-trial-sign-up/choose-mdm-authority.png) 

4. Se sua Autoridade MDM não estiver definida, em **Escolher Autoridade MDM**, defina-a como **Autoridade MDM do Intune**.

Para obter mais informações sobre a autoridade de MDM, confira [Definir autoridade de gerenciamento de dispositivo móvel](mdm-authority-set.md).

## <a name="configure-your-custom-domain-name-optional"></a>Configurar o nome de domínio personalizado (opcional)

Como mencionado acima, se sua organização tiver seu próprio domínio personalizado que você deseja usar sem **.onmicrosoft.com**, será possível alterá-lo no Centro de administração do Microsoft 365. É possível adicionar, verificar e configurar o nome de domínio personalizado usando as etapas a seguir.  

> [!IMPORTANT]
> Não é possível renomear nem remover a parte *inicial* de **onmicrosoft.com** do nome do domínio. No entanto, é possível adicionar, verificar ou remover os nomes de domínio *personalizados* usados com o Intune para manter a identidade de sua empresa limpa. Para saber mais, confira [Configurar um nome de domínio personalizado](custom-domain-name-configure.md).

1. Acesse o [Centro de administração do Microsoft 365](https://admin.microsoft.com) e entre usando sua conta de administrador.

2. No painel de navegação, escolha **Configuração** > **Domínios** > **Adicionar domínio**.

3. Digite seu nome de domínio personalizado. Em seguida, selecione **Avançar**.

   ![Captura de tela do Centro de administração do Microsoft 365 – Adicionar domínio](./media/free-trial-sign-up/domain-custom-add.png)

4. Verifique se que você é o proprietário do domínio inserido na etapa anterior. 
    
    Selecionar **enviar código por email** enviará um email para o contato registrado do seu domínio. Depois de receber o email, copie o código e insira-o no campo de rotulado **Digite seu código de verificação aqui**. Se o código de verificação for correspondente, o domínio será adicionado ao seu locatário. O email exibido pode não parecer familiar. Alguns registradores ocultam o endereço de email real. Além disso, o endereço de email pode ser diferente do que foi fornecido quando o domínio foi registrado.

   ![Captura de tela do Centro de administração do Microsoft 365 – Verificar domínio](./media/free-trial-sign-up/domain-custom-verify.png)

   > [!NOTE]
   > Para obter os detalhes de verificação de registro TXT, consulte [Criar registros DNS em qualquer provedor de hospedagem de DNS para o Office 365](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Experiências de administrador

Há dois portais de que você usará com maior frequência:
- O Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft ([https://devicemanagement.microsoft.com/](https://devicemanagement.microsoft.com/)) é onde você pode explorar as [funcionalidades do Intune](what-is-intune.md). Um administrador trabalharia com o Intune nesse local.
- O centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) é o local em que você poderá adicionar e gerenciar usuários, se não estiver usando o Azure Active Directory para isso. Você também pode gerenciar outros aspectos da sua conta, incluindo cobrança e suporte.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou uma assinatura gratuita para experimentar o Intune em um ambiente de teste. Para obter mais informações sobre a configuração do Intune, confira [Configurar o Intune](setup-steps.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Criar um usuário e atribuir uma licença a ele](quickstart-create-user.md)
