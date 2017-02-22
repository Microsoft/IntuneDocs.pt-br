---
title: "Como adicionar aplicativos ao Microsoft Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: tais procedimentos ajudam você a deixar seus aplicativos no Intune prontos para serem atribuído aos usuários e dispositivos. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>Como adicionar um aplicativo 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Antes de gerenciar e atribuir aplicativos aos seus usuários, você deve adicioná-los ao Intune. O Intune dá suporte a uma ampla variedade de tipos diferentes de aplicativos e as opções podem ser diferentes para cada tipo.

O Intune dá suporte à adição e atribuição desses tipos de aplicativos:

![Tipos de aplicativo com suporte no Intune](./media/app-types.png)

Há suporte para as seguintes plataformas. Clique em um dos tópicos para obter mais informações sobre como adicionar cada tipo de aplicativo.

- [Aplicativos de linha de negócios Android](/intune-azure/manage-apps/android-lob-app)
- [Aplicativos da Android Store](/intune-azure/manage-apps/android-store-app)
- [Aplicativos de linha de negócios iOS](/intune-azure/manage-apps/ios-lob-app)
- [Aplicativos da iOS Store](/intune-azure/manage-apps/ios-store-app)
- [Aplicativos Web (para todas as plataformas)](/intune-azure/manage-apps/web-app)
- [Aplicação da loja do Windows Phone 8.1](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Aplicativos da Windows Store](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Quando você adiciona e implanta um aplicativo de uma loja, os usuários finais deve ter uma conta naquela loja para poderem instalar o aplicativo.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Como criar e editar categorias para aplicativos 

Categorias de aplicativo podem ser usadas para ajudar a classificar aplicativos para facilitar a tarefa dos usuários finais de localizá-los no portal da empresa. Você pode atribuir uma ou mais categorias a um aplicativo, por exemplo, **Aplicativos de desenvolvedor** ou **Aplicativos de comunicação**. Quando você adiciona um aplicativo ao Intune, terá a opção de selecionar a categoria desejada. Use os tópicos específicos da plataforma para adicionar um aplicativo e atribuir categorias. Para criar e editar suas próprias categorias, use o procedimento a seguir: 

1. Entre no portal do Azure. 
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. 
3. Na folha **Intune**, escolha **Gerenciar aplicativos**. 
4. Na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Categorias de aplicativos**. 
5. Na folha **Categorias de aplicativos**, é mostrada uma lista de categorias atuais. Escolha uma das seguintes ações: 
    - **Criar uma categoria de** – Na folha **Criar categoria**, insira um nome para a nova categoria. Os nomes podem ser inseridos em apenas um idioma e não são traduzidos pelo Intune. Quando terminar, clique em **Criar**.
    - **Editar uma categoria** – Para qualquer categoria na lista, escolha “**... **“. Na folha **Propriedades**, você pode inserir um novo nome para a categoria ou excluí-la. --->






<!--HONumber=Feb17_HO1-->


