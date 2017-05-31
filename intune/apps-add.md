---
title: Como adicionar aplicativos ao Microsoft Intune | Microsoft Docs
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: tais procedimentos ajudam você a deixar seus aplicativos no Intune prontos para serem atribuído aos usuários e dispositivos. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 36cafd2b943ab1dd5045a8ed1fe1fcf1b28af385
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Como adicionar um aplicativo no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Antes de gerenciar e atribuir aplicativos aos seus usuários, você deve adicioná-los ao Intune. O Intune dá suporte a uma ampla variedade de tipos diferentes de aplicativos e as opções podem ser diferentes para cada tipo.

O Intune permite que você adicione e atribua esses tipos de aplicativo:

![Tipos de aplicativo com suporte no Intune](./media/app-types.png)

Há suporte para as seguintes plataformas.

- Aplicativos da Android Store
- Aplicativos LOB para Android
- Aplicativos da iOS Store
- Aplicativos LOB para iOS
- Aplicativos Web
- Aplicativos da Windows Phone 8.1 Store
- Aplicativos de linha de negócios para Windows Phone (arquivos .xap)
- Aplicativos da Windows Store
- Aplicativos de linha de negócios para Windows (apenas arquivos .msi)

>[!TIP]
> Um aplicativo LOB (ou de linha de negócios) é aquele que você instala do arquivo de instalação, em vez de instalar de uma loja de aplicativos. Por exemplo, para instalar um aplicativo LOB para iOS, adicione o respectivo arquivo morto cuja extensão seja .ipa. Normalmente, são aplicativos que você tem gravados internamente.

## <a name="before-you-start"></a>Antes de começar

Considere os pontos a seguir antes de começar a adicionar e atribuir aplicativos.

- Quando você adiciona e atribui um aplicativo de uma loja, os usuários finais devem ter uma conta nessa loja para poder instalar o aplicativo.
- Alguns aplicativos ou itens que você atribui podem ser dependentes de aplicativos internos do iOS. Por exemplo, quando você atribui um livro da iOS Store, o aplicativo iBooks deve estar presente no dispositivo. Se você tiver removido o aplicativo interno iBooks, não será possível usar o Intune para reabilitá-lo.

## <a name="cloud-storage-space"></a>Espaço de armazenamento em nuvem
Todos os aplicativos que você cria usando o tipo de instalação do instalador do software (por exemplo, um aplicativo LOB) são empacotados e carregados no armazenamento em nuvem do Microsoft Intune. Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações. A assinatura completa inclui 20 GB de espaço de armazenamento.

Você pode adquirir armazenamento adicional para o Intune usando seu método de compra original.  Se você paga por cartão de crédito ou fatura, visite o [portal de Gerenciamento de Assinatura](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Caso contrário, entre em contato com seu parceiro ou associado de vendas.

Os requisitos de espaço de armazenamento em nuvem são os seguintes:

-   Todos os arquivos de instalação do aplicativo devem estar na mesma pasta.
-   O tamanho máximo do arquivo para qualquer arquivo que você carregar é de 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Como criar e editar categorias para aplicativos

Categorias de aplicativo podem ser usadas para ajudar a classificar aplicativos para facilitar a tarefa dos usuários finais de localizá-los no portal da empresa. Você pode atribuir uma ou mais categorias a um aplicativo, por exemplo, **Aplicativos de desenvolvedor** ou **Aplicativos de comunicação**.
Quando você adiciona um aplicativo ao Intune, terá a opção de selecionar a categoria desejada. Use os tópicos específicos da plataforma para adicionar um aplicativo e atribuir categorias. Para criar e editar suas próprias categorias, use o procedimento a seguir:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Categorias de aplicativos**.
5. Na folha **Categorias de aplicativos**, é mostrada uma lista de categorias atuais. Escolha uma das seguintes ações:
    - **Criar uma categoria de** – Na folha **Criar categoria**, insira um nome para a nova categoria. Os nomes podem ser inseridos em apenas um idioma e não são traduzidos pelo Intune. Quando terminar, clique em **Criar**.
    - **Editar uma categoria** – Para qualquer categoria na lista, escolha “**...** “. Na folha **Propriedades**, você pode inserir um novo nome para a categoria ou excluí-la.


## <a name="apps-added-automatically-by-intune"></a>Aplicativos adicionados automaticamente pelo Intune

Os aplicativos a seguir, publicados pela Microsoft, estão internos ao Intune e estão prontos para atribuição:

|||
|-|-|
|Nome|Plataforma|Tipo de aplicativo|
|Azure Information Protection|Android|Aplicativo gerenciado da loja do Android|
|Dynamics CRM para telefones|Android|Aplicativo gerenciado da loja do Android|
|Dynamics CRM para tablets|Android|Aplicativo gerenciado da loja do Android|
|Excel|iOS|Aplicativo gerenciado de loja do iOS|
|Excel|Android|Aplicativo gerenciado da loja do Android|
|Managed Browser|Android|Aplicativo gerenciado da loja do Android|
|Managed Browser|iOS|Aplicativo gerenciado de loja do iOS|
|Microsoft Dynamics CRM em telefones|iOS|Aplicativo gerenciado de loja do iOS|
|Microsoft Dynamics CRM em tablets|iOS|Aplicativo gerenciado de loja do iOS|
|Microsoft Power BI|iOS|Aplicativo gerenciado de loja do iOS|
|Microsoft Power BI|Android|Aplicativo gerenciado da loja do Android|
|Microsoft SharePoint|iOS|Aplicativo gerenciado de loja do iOS|
|Microsoft SharePoint|Android|Aplicativo gerenciado da loja do Android|
|Microsoft Teams|Android|Aplicativo gerenciado da loja do Android|
|Microsoft Teams|iOS|Aplicativo gerenciado de loja do iOS|
|OneDrive|iOS|Aplicativo gerenciado de loja do iOS|
|OneDrive|Android|Aplicativo gerenciado da loja do Android|
|OneNote|iOS|Aplicativo gerenciado de loja do iOS|
|Outlook|Android|Aplicativo gerenciado da loja do Android|
|Outlook|iOS|Aplicativo gerenciado de loja do iOS|
|Outlook Groups|Android|Aplicativo gerenciado da loja do Android|
|Outlook Groups|iOS|Aplicativo gerenciado de loja do iOS|
|PowerPoint|iOS|Aplicativo gerenciado de loja do iOS|

## <a name="next-steps"></a>Próximas etapas

Escolha um dos tópicos a seguir para saber como adicionar aplicativos para cada plataforma no Microsoft Intune:

- [Aplicativos da Android Store](store-apps-android.md)
- [Aplicativos LOB para Android](lob-apps-android.md)
- [Aplicativos da iOS Store](store-apps-ios.md)
- [Aplicativos LOB para iOS](lob-apps-ios.md)
- [Aplicativos Web (para todas as plataformas)](web-app.md)
- [Aplicação da loja do Windows Phone 8.1](store-apps-windows-phone-8-1.md)
- [Aplicativos LOB para Windows Phone](lob-apps-windows-phone.md)
- [Aplicativos da Windows Store](store-apps-windows.md)
- [Aplicativos LOB para Windows](lob-apps-windows.md)

