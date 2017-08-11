---
title: "Introdução aos aplicativos"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 71093f8ac17fc6d6938f5c263a40204f89419726
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-apps"></a>Introdução aos aplicativos

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune dá suporte a algumas maneiras diferentes de implantar aplicativos em seus dispositivos corporativos:

* **Instaladores de software**: nos quais você pode carregar um arquivo que será baixado nos dispositivos dos usuários
* __Links externos__: para quando você tem um aplicativo em uma loja de aplicativos pública ou um aplicativo Web
* **Aplicativos gerenciados**: para dispositivos iOS nos quais você precisa de gerenciamento de aplicativos móveis adicional para os aplicativos disponíveis na App Store

Acompanhe um dos métodos de implantação de aplicativos mais rápidos existente atribuindo um aplicativo de loja pública.

__Como atribuo um aplicativo de loja pública?__

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Usando **Pesquisar recursos**, pesquise **Intune**.
3. Selecione **Aplicativos Móveis** e selecione **Aplicativos**.
4. Selecione **Adicionar** e **Aplicativo da loja iOS** como o **Tipo de aplicativo**.
5. Na caixa de texto, pesquise um aplicativo para atribuir ao dispositivo. Escolha o aplicativo e selecione **OK**.
6. Na folha **Adicionar aplicativo**, selecione **Informações do aplicativo** e verifique se todas as informações do aplicativo foram populadas. Você pode adicionar outros detalhes opcionais para ajudar a organizar este aplicativo, como **Proprietário**, **Notas**, **Desenvolvedor** e uma **URL de Privacidade** para a política de privacidade da sua empresa.
7. Verifique se você selecionou Sim para Exibir este aplicativo em destaque no Portal da Empresa e selecione OK.
8. Selecione **Adicionar** para adicionar o aplicativo. Isso levará você para a **Visão geral** do aplicativo. Escolha **Atribuições** e clique em **Selecionar grupos** atribuí-lo ao seu grupo de teste. Deixe o aplicativo **Disponível** para download. O aplicativo deverá aparecer como uma **Aplicativo em Destaque** no seu dispositivo de teste.