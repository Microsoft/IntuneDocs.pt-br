---
title: "Configurações de layout da Tela inicial do Intune para dispositivos iOS"
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: aprenda as configurações que você pode usar para personalizar a Tela inicial e o dock em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7743573ab893b7d54c11e183133fa02368c00779
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Configurações de layout da Tela inicial do Intune para dispositivos iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Use essas configurações para definir o layout de aplicativos, pastas e clipes da Web no dock e na Tela inicial de todos os dispositivos iOS aos quais você atribui a política.

Os dispositivos iOS para os quais você atribui o perfil devem estar no modo supervisionado e executando o iOS 9.3 ou posterior.

1. Na folha **Recursos do dispositivo** escolha **Layout da Tela inicial (somente supervisionado)**.
2. Na folha **Layout da Tela inicial (somente supervisionado)**, escolha se quer configurar os layouts do **Dock**, ou das **Páginas**.

## <a name="add-items-to-the-dock"></a>Adicionar itens ao dock

Na folha **Dock**, você pode adicionar até seis itens ou pastas ao dock na parte inferior da tela do iOS. No entanto, muitos dispositivos oferecem suporte a uma quantidade menor de itens, por exemplo, os iPhones dão suporte a até quatro itens. Nesse caso, somente os primeiros quatro itens configurados aparecerão no dispositivo.

1. Escolha **Adicionar** para adicionar um item ao dock.
2. Na folha **Adicionar Linha**, escolha se você quer adicionar um **Aplicativo** ou uma **Pasta**.
3. Usando as informações das seções **Como adicionar um aplicativo à lista** e **Como adicionar uma pasta à lista** deste tópico, configure os aplicativos e as pastas que você quer exibir no dock.
4. Continue adicionando itens. Quando terminar, clique em **OK** em cada folha até voltar à folha **Criar Perfil**. Escolha **Criar**.

>[!TIP]
> Você pode arrastar e soltar itens em quaisquer lista de Tela inicial e páginas para reordená-las. 

### <a name="example"></a>Exemplo

Neste exemplo, você configurou a tela do dock para mostrar apenas os aplicativos Safari, Mail e Bolsa. Na imagem a seguir, o aplicativo Mail está selecionado para ilustrar suas propriedades:

![Exemplo de configurações do dock do iOS](http://i.imgur.com/FfFiUcP.png)

Quando você atribui a política a um iPhone, o resultado será um dock semelhante a este:

![Exemplo de layout do dock do iOS no iPhone](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Adicionar páginas de Tela inicial

Adicione as páginas que você deseja exibir na Tela inicial e os aplicativos que aparecerão em cada página. Os aplicativos adicionados a uma página são dispostos da esquerda para a direita, na ordem especificada na lista. Se você adicionar mais aplicativos que uma página comporta, eles serão movidos para uma página subsequente.


1. Na folha **Páginas**, escolha **Adicionar**.
2. Na folha **Adicionar Linha**, insira um **Nome de página**. Isso é usado para sua referência no portal do Intune, e *não é exibido* no dispositivo iOS.
3. Escolha **Adicionar**, depois escolha se você quer adicionar um **Aplicativo** ou uma **Pasta** à página.
4. Usando as informações das seções **Como adicionar um aplicativo à lista** e **Como adicionar uma pasta à lista** deste tópico, configure os aplicativos e as pastas que você quer exibir na página.

### <a name="example"></a>Exemplo

Neste exemplo, você configurou uma nova página chamada **Contoso**. A página mostra apenas os aplicativos Buscar Amigos e Ajustes. Na imagem a seguir, o aplicativo Ajustes está selecionado para ilustrar suas propriedades:

![Exemplo de ajustes na Tela inicial do iOS](http://i.imgur.com/Jc2OxyX.png)

Quando você atribui a política a um iPhone, o resultado será uma página semelhante a esta:

![Dispositivo iOS com Tela inicial modificada](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Como adicionar um aplicativo à lista

1. Insira o **Nome do Aplicativo**. Isso é usado para sua referência no portal do Intune, e *não é exibido* no dispositivo iOS.
2. Insira **ID de Pacote de Aplicativos** do aplicativo que você deseja exibir. Consulte **Referência da ID de Pacote para aplicativos iOS internos** mais adiante neste tópico para obter ajuda.
3. Clique em **OK**, depois continue a adicionar itens, até um máximo de **6** para o dock do dispositivo, e **60** para uma página de dispositivo.
4. Ao terminar, clique em **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Como adicionar uma pasta à lista

Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, na ordem especificada na lista. Se você adicionar mais aplicativos que uma página comporta, eles serão movidos para uma página subsequente.

1. Insira **Nome da pasta**. Isso será exibido aos usuários no dispositivo.
2. Escolha **Adicionar** para criar uma página na pasta. Você pode adicionar até 20 páginas.
3. Na folha **Adicionar Linha**, insira um nome para a página. Isso é usado para sua referência no portal do Intune, e *não é exibido* no dispositivo iOS.
3. Insira o **Nome do Aplicativo**. Isso é usado para sua referência no portal do Intune, e *não é exibido* no dispositivo iOS.
2. Insira **ID de Pacote de Aplicativos** do aplicativo que você deseja exibir. Confira **Como adicionar um aplicativo à lista**.
3. Escolha **Adicionar**. Você pode adicionar até 60 itens.
4. Ao terminar, clique em **OK**.


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
|Observações|com.apple.mobilenotes|
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


