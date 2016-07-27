---
title: Atualizar aplicativos | Microsoft Intune
description: "Use as informações neste tópico para entender como você pode atualizar aplicativos quando uma nova versão é requerida."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: bb077902e33d6ab18dea33a6ab2d1ff9a70ce937


---

# Atualizar aplicativos usando o Microsoft Intune
O Microsoft Intune pode ajudar você a gerenciar as atualizações de aplicativo. Use as informações neste tópico para entender como você pode atualizar aplicativos quando uma nova versão é requerida.

## Como atualizar aplicativos
Quando uma nova versão de um aplicativo que você implantou for lançada, o Intune permitirá que você atualize e implante a versão mais recente do aplicativo. Só é possível substituir uma implantação com uma versão mais recente do mesmo aplicativo (usando o mesmo identificador). Não é possível usar atualizações de aplicativo para atualizar uma implantação com um pacote do aplicativo diferente.

### Identificadores de aplicativo
O identificador de aplicativo é uma propriedade que identifica exclusivamente um aplicativo. Não é possível instalar várias cópias de um aplicativo com o mesmo identificador. Por exemplo:

- **iOS** – ID do pacote (por exemplo: com.microsoft.excel)
- **Android** – ID do pacote (por exemplo: com.microsoft.excel)
- **Windows Phone** – (instalador xap), use a ID do produto (GUID)
- **Windows** – (appx/appxbundle), use o nome completo do pacote



> [!IMPORTANT]
> Quando você implanta um aplicativo com uma ação de implantação de **Instalação requerida** e, posteriormente, altera a ação de implantação para **Instalação disponível**, atualizações do aplicativo não são instaladas automaticamente em dispositivos que instalaram o aplicativo antes da alteração de implantação ter sido feita. Para corrigir esse problema, você pode fazer o seguinte:
> 
> -   O usuário do dispositivo deve ir ao portal da empresa, selecionar o aplicativo instalado e escolher **Instalar**.
> -   Altere a ação de implantação para **Desinstalar**e, após o aplicativo ser desinstalado, reimplante o aplicativo com uma ação de implantação de **Instalação disponível**.

### Para atualizar um aplicativo

1.  No [Console do administrador do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Aplicativos**.

2.  Na lista **Aplicativos**, selecione o aplicativo que você deseja atualizar e escolha **Editar**.

3.  No assistente **Editar Software** , forneça quaisquer detalhes novos para o pacote do aplicativo.

4.  Quando você terminar, escolha **Atualizar**.

Da próxima vez que os dispositivos verificarem os aplicativos disponíveis, o aplicativo será atualizado automaticamente para a versão mais recente.
Para aplicativos instalados por meio de um pacote do aplicativo (aplicativos de linha de negócios), o aplicativo será atualizado automaticamente para implantações necessárias e disponíveis, desde que o aplicativo tenha o mesmo identificador.
Para aplicativos implantados como um link para um repositório, a atualização é gerenciada pelo repositório do qual se origina o aplicativo.






<!--HONumber=Jul16_HO3-->


