---
title: "Configurações de layout da tela inicial do Microsoft Intune para dispositivos que executam iOS"
titlesuffix: Azure portal
description: "Conheça as configurações que você pode usar para personalizar a tela inicial e o encaixe em dispositivos que executam iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88be142c98d7b89720d245c738a45a26ac825395
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-home-screen-layout-settings-for-devices-running-ios"></a>Configurações de layout da tela inicial do Microsoft Intune para dispositivos que executam iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações para definir o layout do aplicativo e as pastas no encaixe e na tela inicial de dispositivos que executam iOS.

Dispositivos que executam o iOS com um perfil atribuído devem estar no modo supervisionado e executar o iOS 9.3 ou posterior.

1. Do [Intune no Portal do Azure](https://portal.azure.com), navegue até os [**Recursos do dispositivo** na área de configuração do dispositivo](device-features-configure.md).
2. No painel **Recursos do dispositivo** escolha **Layout da Tela inicial (somente supervisionado)**.
3. No painel **Layout da Tela Inicial (apenas supervisionado)**, escolha se deseja configurar o layout de **Encaixe** ou de **Páginas**.

## <a name="add-items-to-the-dock"></a>Adicionar itens ao dock

No painel **Encaixe**, você pode adicionar até seis itens ou pastas ao encaixe na tela do iOS. No entanto, muitos dispositivos dão suporte a uma quantidade menor de itens, por exemplo, dispositivos iPhone dão suporte a até quatro itens. Nesse caso, somente os primeiros quatro itens configurados aparecerão no dispositivo.

1. Escolha **Adicionar** para adicionar um item ao dock.
2. No painel **Adicionar Linha**, escolha se deseja adicionar um **Aplicativo** ou uma **Pasta**.
3. Usando as informações deste tópico, configure os aplicativos e as pastas que você deseja que apareça no dock.
4. Continue adicionando itens. Quando terminar, clique em **OK** em cada painel até voltar ao painel **Criar Perfil**. Escolha **Criar**.

>[!TIP]
> Você pode arrastar e soltar itens em quaisquer lista de Tela inicial e páginas para reordená-las.

### <a name="example"></a>Exemplo

Neste exemplo, você configurou a tela do dock para mostrar apenas os aplicativos Safari, Mail e Bolsa. Na imagem a seguir, o aplicativo Mail está selecionado para ilustrar suas propriedades:

![Exemplo de configurações do dock do iOS](./media/FfFiUcP.png)

Quando você atribuir a política a um iPhone, o resultado será um dock semelhante a esta captura de tela:

![Exemplo de layout do dock do iOS no iPhone](./media/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Adicionar páginas de Tela inicial

Adicione as páginas que você deseja exibir na Tela inicial e os aplicativos que aparecerão em cada página. Os aplicativos adicionados a uma página são dispostos da esquerda para a direita, na ordem especificada na lista. Se você adicionar mais aplicativos que uma página comporta, eles serão movidos para uma página subsequente.

1. No painel **Páginas**, escolha **Adicionar**.
2. No painel **Adicionar Linha**, insira um **Nome da página**. Esse nome é usado para sua referência no Portal do Azure e *não é exibido* no dispositivo iOS.
3. Escolha **Adicionar**, depois escolha se você quer adicionar um **Aplicativo** ou uma **Pasta** à página.
4. Usando as informações deste tópico, configure os aplicativos e as pastas que você deseja que apareça na página.

### <a name="example"></a>Exemplo

Neste exemplo, você configurou uma nova página chamada **Contoso**. A página mostra apenas os aplicativos Buscar Amigos e Ajustes. Na imagem a seguir, o aplicativo Ajustes está selecionado para ilustrar suas propriedades:

![Exemplo de ajustes na Tela inicial do iOS](./media/Jc2OxyX.png)

Quando você atribuir a política a um iPhone, o resultado será uma página semelhante a esta captura de tela:

![Dispositivo iOS com Tela inicial modificada](./media/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Como adicionar um aplicativo à lista

1. Insira o **Nome do Aplicativo**. Esse nome é usado para sua referência no Portal do Azure e *não é exibido* no dispositivo iOS.
2. Insira **ID de Pacote de Aplicativos** do aplicativo que você deseja exibir. Consulte **Referência da ID de Pacote para aplicativos iOS internos** mais adiante neste tópico para obter ajuda.
3. Clique em **OK**, depois continue a adicionar itens, até um máximo de **6** para o dock do dispositivo, e **60** para uma página de dispositivo.
4. Ao terminar, clique em **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Como adicionar uma pasta à lista

Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, na ordem especificada na lista. Se você adicionar mais aplicativos que uma página comporta, eles serão movidos para uma página subsequente.

1. Insira **Nome da pasta**. Esse nome será exibido aos usuários no dispositivo.
2. Escolha **Adicionar** para criar uma página na pasta. Você pode adicionar até 20 páginas.
3. No painel **Adicionar Linha**, insira um nome para a página. Esse nome é usado para sua referência no Portal do Azure e *não é exibido* no dispositivo iOS.
3. Insira o **Nome do Aplicativo**. Esse nome é usado para sua referência no Portal do Azure e *não é exibido* no dispositivo iOS.
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
