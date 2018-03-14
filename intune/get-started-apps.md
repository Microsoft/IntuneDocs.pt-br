---
title: "Introdução aos aplicativos no Microsoft Intune"
titlesuffix: 
description: Localize e adicione aplicativos em dispositivos para permitir que os colaboradores realizem seus trabalhos.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Introdução à adição de aplicativos no Microsoft Intune

Antes que possa atribuir, monitorar, configurar ou proteger aplicativos, você precisa adicioná-los ao Intune. O Intune é compatível com vários tipos de aplicativos. Além disso, as opções disponíveis são diferentes para cada tipo de aplicativo.

O Intune permite que você adicione e atribua esses tipos de aplicativo aos seus dispositivos corporativos:
- **Aplicativos da loja** – para dispositivos nos quais você precisa de gerenciamento de aplicativos móveis adicional aplicado aos aplicativos disponíveis na App Store.
- **Aplicativos escritos internamente (linha de negócios)**: nos quais você carrega um arquivo que é baixado nos dispositivos dos usuários.
- **Aplicativos internos** – nos quais você atribui aplicativos gerenciados organizados, como aplicativos do Office 365, para dispositivos iOS e Android. 
- **Aplicativos na Web** – nos quais o Intune cria um atalho para o aplicativo Web na tela inicial do dispositivo.

## <a name="how-do-i-assign-a-public-store-app"></a>Como fazer para atribuir um aplicativo de loja pública?

O exemplo a seguir explica como adicionar um aplicativo iOS no Microsoft Intune.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** na seção **Gerenciar**.
5. Escolha **Adicionar** no lado direito do painel **Aplicativos**.
6. Na lista **Tipo de aplicativo**, selecione **iOS** nos tipos disponíveis de **aplicativos da Loja**.
6. Escolha **Pesquisar na Loja de Aplicativos**.
7. Na folha **Pesquisar na Loja de Aplicativos**, selecione primeiro a localidade do país da loja de aplicativos.
8. Na caixa de pesquisa, digite o nome (ou parte do nome). O Intune pesquisará na loja e retornará uma lista de resultados relevantes.
9. Na lista, escolha o aplicativo e clique em **Selecionar**.
10. Selecione **Informações do aplicativo** para configurar as informações do aplicativo.
11. (Opcional) adicione detalhes para ajudar a organizar este aplicativo, como **Proprietário**, **Notas**, **Desenvolvedor** e uma **URL de Privacidade** (que aponte para a política de privacidade da sua empresa).
12. Selecione **Sim** para a opção **Exibir este aplicativo em destaque no Portal da Empresa**. 
13. Clique em **OK** depois de adicionar todas as informações necessárias do aplicativo.
14. Clique em **Adicionar** na folha **Adicionar aplicativo**. Isso levará você até a **Visão geral** desse aplicativo. 

## <a name="next-steps"></a>Próximas etapas

Agora que adicionou um aplicativo ao Intune, você pode atribuir quais grupos de funcionários poderão incluir o aplicativo nos respectivos dispositivos.

- [Como atribuir aplicativos aos grupos](apps-deploy.md)
- 
## <a name="learn-more"></a>Saiba mais

* [O que é o gerenciamento de aplicativo do Microsoft Intune?](app-management.md)
* [Visão geral do ciclo de vida do aplicativo](app-lifecycle.md)
* [O que são políticas de proteção do aplicativo?](app-protection-policy.md)
