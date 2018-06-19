---
title: Introdução aos aplicativos no Microsoft Intune
titlesuffix: ''
description: Localize e adicione aplicativos em dispositivos para permitir que os colaboradores realizem seus trabalhos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d99812c57596e10d0cdfa2c0f4504f8a6ac583c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223791"
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Introdução à adição de aplicativos no Microsoft Intune

Antes que possa atribuir, monitorar, configurar ou proteger aplicativos, você precisa adicioná-los ao Intune. O Intune é compatível com vários tipos de aplicativos. Além disso, as opções disponíveis são diferentes para cada tipo de aplicativo.

O Intune permite que você adicione e atribua esses tipos de aplicativo aos seus dispositivos corporativos:
- **Aplicativos da loja** – para dispositivos nos quais você precisa de gerenciamento de aplicativos móveis adicional aplicado aos aplicativos disponíveis na App Store.
- **Aplicativos escritos internamente (linha de negócios)**: nos quais você carrega um arquivo que é baixado nos dispositivos dos usuários.
- **Aplicativos internos** – nos quais você atribui aplicativos gerenciados organizados, como aplicativos do Office 365, para dispositivos iOS e Android.
- **Aplicativos na Web** – nos quais o Intune cria um atalho para o aplicativo Web na tela inicial do dispositivo.

## <a name="how-do-i-assign-a-public-store-app"></a>Como fazer para atribuir um aplicativo de loja pública?

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione **Aplicativos Móveis** e selecione **Aplicativos**.
4. Selecione **Adicionar** e, em seguida, escolha **iOS** como o **Tipo de aplicativo**.
5. Escolha **Selecionar aplicativo** para exibir o painel **Pesquisar na Loja de Aplicativos**.
6. Na caixa de texto, pesquise um aplicativo para atribuir ao dispositivo. Escolha o aplicativo e, em seguida, clique em **Selecionar**.
7. No painel **Adicionar aplicativo**, selecione **Informações do aplicativo** e verifique se todas as informações do aplicativo foram preenchidas. Você pode adicionar outros detalhes opcionais para ajudar a organizar este aplicativo, como **Proprietário**, **Notas**, **Desenvolvedor** e uma **URL de Privacidade** para a política de privacidade da sua empresa.
8. Verifique se você selecionou **Sim** para **Exibir este aplicativo em destaque no Portal da Empresa** e selecione **OK**.
9. Selecione **Adicionar** no painel **Adicionar aplicativo** para adicionar o aplicativo. Essa ação levará você para a **Visão geral** desse aplicativo. Escolha **Atribuições** e, em seguida, clique em **Adicionar grupo** para atribuí-lo ao seu grupo de teste. Deixe o aplicativo **Disponível** para download. O aplicativo deverá aparecer como uma **Aplicativo em Destaque** no seu dispositivo de teste.


- [Como atribuir aplicativos aos grupos](apps-deploy.md)

## <a name="learn-more"></a>Saiba mais

* [O que é o gerenciamento de aplicativo do Microsoft Intune?](app-management.md)
* [Visão geral do ciclo de vida do aplicativo](app-lifecycle.md)
* [O que são políticas de proteção do aplicativo?](app-protection-policy.md)
