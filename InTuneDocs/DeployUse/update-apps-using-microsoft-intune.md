---
title: Atualizar aplicativos | Microsoft Intune
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 0581d1476fba5bedcdd4446df20f8f92b151f41b
ms.openlocfilehash: 9e5b8f4a467e8e58cc2f8fa495b5f008eee7e35b


---

# Atualizar aplicativos usando o Microsoft Intune
O Microsoft Intune pode ajudar você a gerenciar as atualizações de aplicativo. Use as informações neste tópico para entender como você pode atualizar aplicativos quando uma nova versão é requerida.

## Como atualizar aplicativos
Quando uma nova versão de um aplicativo que você implantou for lançada, o Intune permitirá que você atualize e implante a versão mais recente do aplicativo. Só é possível substituir uma implantação com uma versão mais recente do mesmo aplicativo (usando o mesmo identificador). Não é possível usar atualizações de aplicativo para atualizar uma implantação com um pacote do aplicativo diferente.

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






<!--HONumber=Jul16_HO2-->


