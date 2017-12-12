---
title: Sincronizar o dispositivo Windows manualmente | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1c1ade50ff6a458633598d2788d176dd79cbfebd
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="sync-your-windows-device-manually"></a>Sincronizar o dispositivo Windows manualmente

Às vezes, tentar instalar um aplicativo no dispositivo Windows pode levar mais tempo do que o esperado. Se isso acontecer, você poderá tentar sincronizar o dispositivo Windows manualmente. A sincronização pode ajudar a acelerar a instalação.

> [!Note]
> Os aplicativos poderão levar algum tempo para serem instalados se você estiver em uma rede com velocidades mais lentas ou se houver uma quantidade maior de dispositivos baixando conteúdo ao mesmo tempo.

As versões do Windows a seguir podem ser sincronizadas manualmente. Infelizmente, se o dispositivo estiver usando outra versão do Windows, não será possível iniciar uma sincronização manual.

* [Sincronizar Windows 10 Desktop](#windows-10-desktop)
* [Sincronizar Windows 10 Mobile](#windows-10-mobile)
* [Sincronizar Windows Phone 8.1](#windows-phone-81)

## <a name="windows-10-desktop"></a>Windows 10 Desktop
Há mais de uma versão do Windows 10, portanto, há dois conjuntos de etapas. Para descobrir quais etapas usar, examine as capturas de tela e siga as etapas que se parecem com o que você vê em seu dispositivo.

1. Clique no botão **Iniciar** e, em seguida, escolha **Configurações**.

    ![O botão Iniciar](./media/win10pc-sync-1-start-button.png)

2. Na página **Configurações**, escolha **Contas**.

    ![Escolha Contas na página Configurações](./media/win10pc-sync-2-settings-accounts.png)

3. Examine as duas próximas telas e localize a que é semelhante ao que você vê em seu dispositivo. Siga as etapas fornecidas com a tela que você vê em seu dispositivo.

    Se você vir esta tela, que exibe “Acessar conta corporativa ou de estudante”, siga as instruções em [As etapas a serem seguidas se você vir Acessar conta corporativa ou de estudante](#steps-to-follow-if-you-see-access-work-or-school).

    ![Etapas de sincronização a serem seguidas se você vir Acessar conta corporativa ou de estudante](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Se você vir essa tela, que exibe “Acessar conta corporativa”, siga as etapas em [As etapas a serem seguidas se você vir Acessar conta corporativa](#steps-to-follow-if-you-see-work-access).

    ![Escolha acesso corporativo como tipo de conta](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>As etapas a serem seguidas se você vir Acessar conta corporativa ou de estudante

1. Na página **Contas**, escolha **Acessar conta corporativa ou de estudante**.

    ![Escolha Acessar conta corporativa ou de estudante](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Escolha sua conta corporativa ou de estudante. Dependendo de como o suporte de sua empresa tiver configurado as coisas, você poderá ver duas contas semelhantes ao exemplo a seguir. Ao lado de uma conta, há uma pasta, ao lado da outra há um logotipo da Microsoft.

    - Se vir a conta com a pasta, selecione-a e procure um botão de **Informações** abaixo dela.
    - Se vir apenas a conta com o logotipo da Microsoft, selecione a conta e procure um botão de **Informações** abaixo dela.

    ![Escolha o nome da sua conta ao lado da pasta ou do logotipo da Microsoft](./media/win10pc-rs1-sync-info-button.png)

3. Escolha o botão de **Informações**. É aberta uma caixa de diálogo semelhante ao exemplo a seguir.

    ![Escolha o nome da sua conta ao lado da pasta ou do logotipo da Microsoft](./media/win10pc-rs1-sync-button.png)

4. Escolha o botão **Sincronizar**. O dispositivo será sincronizado com o Intune.

### <a name="steps-to-follow-if-you-see-work-access"></a>Etapas a serem seguidas se você vir Acesso corporativo

1. Na página **Contas**, escolha **Acesso corporativo**.

    ![Escolha acesso corporativo como tipo de conta](./media/win10pc-sync-3-work-access.png)

2. Na seção **Registrar-se no gerenciamento de dispositivo**, escolha o nome da sua empresa.

    ![Escolha o nome da empresa para o gerenciamento de dispositivos](./media/win10pc-sync-4-tap-com-name.png)

3. Escolha o botão **Sincronizar**.

    ![Escolha o botão Sincronizar](./media/win10pc-sync-5-tap-sync.png)

   O botão fica esmaecido até que a sincronização seja concluída.

### <a name="windows-10-mobile"></a>Windows 10 Mobile
Para sincronizar manualmente seu dispositivo Windows 10 Mobile e acelerar uma instalação de aplicativo que está lenta:

   1. Vá para **Todos os aplicativos** > **Configurações** > **Contas**.

       ![Escolha Contas na tela Configurações](./media/win10m-sync-1-settings-accounts.png)

   2. Escolha **Acesso corporativo**.

       ![Escolha acesso corporativo como tipo de conta](./media/win10m-sync-2-work-access.png)

   3. Em **Registrar-se no gerenciamento de dispositivo**, escolha no nome da sua empresa.

       ![Escolha o nome da empresa para o gerenciamento de dispositivos](./media/win10m-sync-3-tap-comp-name.png)

   4. Escolha o ícone **Sincronizar**.

       ![Escolha o ícone Sincronizar](./media/win10m-sync-4-tap-sync.png)

       A mensagem “Estamos sincronizando sua conta” aparece na parte superior da tela. O botão **Sincronizar** fica esmaecido até que o dispositivo termine a sincronização.

## <a name="windows-phone-81"></a>Windows Phone 8.1
Para sincronizar manualmente seu dispositivo Windows Phone 8.1 e acelerar uma instalação de aplicativo que está lenta:

1. Vá para **Todos os aplicativos** > **Configurações** > **Local de trabalho**.

    ![Lista de configurações](./media/wp81-1-sync-settings-workplace.png)

2. Escolha o nome da sua empresa.

    ![Escolha o nome da empresa para a conta de local de trabalho](./media/wp81-2-sync-tap-compname.png)

3. Escolha o ícone **Sincronizar**.

    ![Escolha o ícone Sincronizar](./media/wp81-3-sync-tap-sync-button.png)

   A mensagem “Estamos sincronizando sua conta” aparece na parte superior da tela até que o dispositivo conclua a sincronização.

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
