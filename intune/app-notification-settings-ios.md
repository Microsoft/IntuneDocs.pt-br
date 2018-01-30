---
title: "Configurações de notificação de aplicativo do Intune para dispositivos iOS"
titlesuffix: Azure portal
description: "Conheça as configurações que você pode usar para controlar as notificações de aplicativos em dispositivos iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91e4b6197c7606a70862ad5fb12b10b5e0f3ed81
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>Configurações de notificação de aplicativo do Intune para dispositivos iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Permite a configuração de como os aplicativos instalados em um dispositivo enviam notificações. Essa configuração dá suporte a dispositivos supervisionados que executam o iOS 9.3 e posterior.

## <a name="configure-settings"></a>Definir configurações

1. Na folha Recursos do dispositivo escolha **Notificações de Aplicativo (somente supervisionado)**.
2. Na folha **Notificações do Aplicativo**, escolha **Adicionar** e configure os seguintes valores:
    - **ID do pacote de aplicativos** - insira a **ID do Pacote de Aplicativos** do aplicativo que você deseja configurar. Consulte **Referência da ID de Pacote para aplicativos iOS internos** mais adiante neste tópico para obter ajuda.
    - **Nome do aplicativo** - insira o nome do aplicativo que você deseja configurar. Esse nome não é exibido no dispositivo e é usado para ajudar a identificar o aplicativo na lista.
    - **Editor** - insira o editor que você deseja configurar. O nome do publicador não é exibido no dispositivo e é usado somente para ajudar a identificar o aplicativo na lista.
    - **Notificações** - habilite ou desabilite o envio de notificações para o dispositivo pelo aplicativo. Se você desabilitar essa configuração, as configurações a seguir também serão desabilitadas.
        - **Mostrar no Centro de Notificações** – Habilite essa definição para permitir que o aplicativo mostre as notificações no Centro de Notificações do dispositivo.
        - **Mostrar na Tela de Bloqueio** – Habilite essa definição para ver as notificações do aplicativo na tela de bloqueio do dispositivo.
        - **Tipo de alerta** - selecione o tipo de notificação desejado quando o dispositivo for desbloqueado entre as seguintes opções:
            - **Nenhuma** - nenhuma notificação é exibida.
            - **Faixa** - uma faixa é exibida rapidamente mostrando a notificação.
            - **Modal** - a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.
        - **Notificação no ícone do aplicativo** – Habilite esta definição para adicionar uma notificação ao ícone do aplicativo a fim de indicar que o aplicativo enviou uma notificação.
        - **Sons** – Habilite esta definição para tocar um som quando uma notificação for entregue.
3. Continue adicionando quantos aplicativos forem necessários. Quando terminar, escolha **OK**.
4. Escolha **OK** em até voltar à folha **Criar Perfil**, depois escolha **Criar**. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referência de ID de Pacote para aplicativos iOS internos

Esta lista mostra a ID de pacote de alguns aplicativos iOS internos comuns. Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software. 

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

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
