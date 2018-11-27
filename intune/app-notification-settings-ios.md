---
title: Criar notificações de aplicativos para dispositivos iOS – Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie notificações de aplicativo para dispositivos iOS no Microsoft Intune. Escolha quais para aplicativos enviar notificações, definir as configurações de notificação na tela de bloqueio, habilitar o som, escolher o tipo de alerta e adicionar uma notificação.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2bf4919fecbba8ad4c0f3b8535adf8b97a35342e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182186"
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>Configurar definições das notificações de aplicativo em dispositivos iOS no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configure como os aplicativos instalados em um dispositivo iOS enviam notificações. Essa configuração dá suporte a dispositivos supervisionados que executam o iOS 9.3 e posterior.

## <a name="add-the-app-notification"></a>Adicionar a notificação do aplicativo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Dentro de seu perfil do iOS ou do macOS, selecione **Recursos de dispositivo**. [Recursos do dispositivo iOS ou macOS](device-features-configure.md) lista as etapas para criar um perfil.
3. Selecione as **Notificações do aplicativo (somente supervisionado)** e, em seguida, **Adicionar**: ![adicionar notificação do aplicativo no perfil de iOS ou macOS no Intune](./media/ios-macos-app-notifications.png)
4. Digite as seguintes propriedades:

   - **ID do pacote de aplicativos**: insira a **ID do pacote de aplicativos** do aplicativo que você deseja configurar. A **Referência da ID de pacote para aplicativos iOS nativos** (neste artigo) pode ajudar.
   - **Nome do aplicativo**: insira o nome do aplicativo que você deseja configurar. Esse nome não é exibido no dispositivo e é usado para ajudar a identificar o aplicativo na lista.
   - **Editor**: insira o editor do aplicativo que você deseja configurar. O nome do publicador não é exibido no dispositivo e é usado somente para ajudar a identificar o aplicativo na lista.
   - **Notificações**: habilite ou desabilite o envio de notificações do aplicativo para o dispositivo. Se você desabilitar essa configuração, as configurações a seguir também serão desabilitadas.
     - **Mostrar no Centro de Notificações** – Habilite essa definição para permitir que o aplicativo mostre as notificações no Centro de Notificações do dispositivo.
     - **Mostrar na Tela de Bloqueio** – Habilite essa definição para ver as notificações do aplicativo na tela de bloqueio do dispositivo.
     - **Tipo de alerta** - selecione o tipo de notificação desejado quando o dispositivo for desbloqueado entre as seguintes opções:
       - **Nenhuma** - nenhuma notificação é exibida.
       - **Faixa** - uma faixa é exibida rapidamente mostrando a notificação.
       - **Modal** - a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.
     - **Notificação no ícone do aplicativo** – Habilite esta definição para adicionar uma notificação ao ícone do aplicativo a fim de indicar que o aplicativo enviou uma notificação.
     - **Sons** – Habilite esta definição para tocar um som quando uma notificação for entregue.

5. Continue adicionando quantos aplicativos forem necessários. Após terminar de adicionar os aplicativos, selecione **OK**.
6. Selecione **Criar** para salvar seu perfil.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referência de ID de Pacote para aplicativos iOS internos

A lista a seguir mostra a ID do pacote de alguns aplicativos iOS nativos comuns. Para localizar a ID do pacote de outros aplicativos, é melhor entrar em contato com seu fornecedor de software.

|||
|-|-|
|Nome do aplicativo|ID do pacote|
|Loja de aplicativos|com.apple.AppStore|
|Calculadora|com.apple.calculator|
|Calendário|com.apple.mobilecal|
|Câmera|com.apple.camera|
|Relógio|com.apple.mobiletimer|
|Bússola|com.apple.compass|
|Contacts|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Buscar Amigos|com.apple.mobileme.fmf1|
|Buscar iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Integridade|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Email|com.apple.mobilemail|
|Mapas|com.apple.Maps|
|Mensagens|com.apple.MobileSMS|
|Música|com.apple.Music|
|News|com.apple.news|
|Anotações|com.apple.mobilenotes|
|Números|com.apple.Numbers|
|Páginas|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotos|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Lembretes|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Configurações|com.apple.Preferences|
|Bolsa|com.apple.stocks|
|Dicas|com.apple.tips|
|Vídeos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Carteira|com.apple.Passbook|
|Assistir|com.apple.Bridge|
|Clima|com.apple.weather|

## <a name="next-steps"></a>Próximas etapas

Atribua o perfil do dispositivo aos grupos escolhidos. [Como atribuir perfis de dispositivo](device-profile-assign.md) lista as etapas.