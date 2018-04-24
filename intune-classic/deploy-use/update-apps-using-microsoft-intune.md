---
title: Atualizar aplicativos
description: Use as informações neste tópico para entender como atualizar aplicativos quando uma nova versão é necessária.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ee48f751c181cd12c8e549c5aa4aab0c6252add
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="update-apps-using-microsoft-intune"></a>Atualizar aplicativos usando o Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

O Microsoft Intune pode ajudar você a gerenciar as atualizações de aplicativo. Use as informações neste tópico para entender como atualizar aplicativos quando uma nova versão é necessária.

## <a name="how-to-update-apps"></a>Como atualizar aplicativos
Quando uma nova versão de um aplicativo que você implantou for lançada, o Intune permitirá que você atualize e implante a versão mais recente do aplicativo. Só é possível substituir uma implantação por uma versão mais recente do mesmo aplicativo (que tem o mesmo identificador). Não é possível usar atualizações de aplicativo para atualizar uma implantação com um pacote do aplicativo diferente.

### <a name="app-identifiers"></a>Identificadores de aplicativo
O identificador de aplicativo é uma propriedade que identifica exclusivamente um aplicativo. Não é possível instalar várias cópias de um aplicativo com o mesmo identificador. Veja a seguir alguns exemplos de identificadores de aplicativos:

- **iOS** – ID do pacote (por exemplo: com.microsoft.excel)
- **Android** – ID do pacote (por exemplo: com.microsoft.excel)
- **Windows Phone** – (instalador xap), use a ID do produto (GUID)
- **Windows** – (appx/appxbundle), use o nome completo do pacote



> [!IMPORTANT]
> Quando você implanta um aplicativo com uma ação de implantação de **Instalação requerida** e, posteriormente, altera a ação de implantação para **Instalação disponível**, atualizações do aplicativo não são instaladas automaticamente em dispositivos que instalaram o aplicativo antes da alteração de implantação ter sido feita. Para corrigir esse problema, você pode fazer o seguinte:
>
> -   O usuário do dispositivo deve ir ao portal da empresa, selecionar o aplicativo instalado e escolher **Instalar**.
> -   Altere a ação de implantação para **Desinstalar**e, após o aplicativo ser desinstalado, reimplante o aplicativo com uma ação de implantação de **Instalação disponível**.

### <a name="to-update-an-app"></a>Para atualizar um aplicativo

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Aplicativos**.

2.  Na lista **Aplicativos**, selecione o aplicativo que você deseja atualizar e escolha **Editar**.

3.  No assistente **Editar Software** , forneça quaisquer detalhes novos para o pacote do aplicativo.

4.  Quando você terminar, escolha **Atualizar**.

Da próxima vez que os dispositivos verificarem os aplicativos disponíveis, o aplicativo será atualizado automaticamente para a versão mais recente.
Os aplicativos instalados por meio de um pacote do aplicativo (aplicativos de linha de negócios) serão atualizados automaticamente para implantações necessárias e disponíveis, desde que o aplicativo tenha o mesmo identificador.

Para aplicativos implantados como um link para um repositório, a atualização é gerenciada pelo repositório do qual se origina o aplicativo.
