---
title: Configurações de filtro de conteúdo da Web do Microsoft Intune para dispositivos iOS
titlesuffix: ''
description: Conheça as configurações do Microsoft Intune que você pode usar para permitir e bloquear o acesso aos sites de dispositivos que executam iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24be76637257a3252d6660e8912d7fd2e214dccf
ms.sourcegitcommit: 4ef14cc543b73191862201c1e0bae44dddd7d9f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2018
ms.locfileid: "37921341"
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Configurações de filtro de conteúdo da Web para dispositivos iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Microsoft Intune que você pode usar para controlar o acesso de URL do navegador de dispositivos que executam o iOS.

Existem dois métodos que podem ser usados para configurar URLs:

- **Configurar URLs** – Use o filtro da Web interno da Apple que procura termos adultos como profanação ou linguagem pornográficas. Essa função avalia cada página da Web conforme ela é carregada e tenta identificar e bloquear conteúdo inadequado. Você também pode configurar as URLs que não serão verificadas pelo filtro ou URLs que serão sempre bloqueadas, independentemente das configurações do filtro.

- **Somente para sites específicos** (somente para o navegador da Web Safari somente) - essas URLs são adicionadas aos favoritos do navegador Safari. O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser acessado. Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.
Se você não especificar nenhuma URL, os usuários finais não poderão acessar nenhum site, exceto microsoft.com, microsoft.net e apple.com.

## <a name="get-started"></a>Introdução

1. Na página Recursos do dispositivo, escolha **Filtro de Conteúdo da Web (somente supervisionado)**.
2. Na página **Filtro de Conteúdo da Web**, escolha o **Tipo de filtro** que você deseja configurar:
    - **Não Configurado** - nenhuma filtragem será executada.
    - **Configurar URLs**
    - **Somente sites específicos**
3. Em seguida, dependendo do tipo de filtro que você estiver usando, siga um destes procedimentos:


## <a name="configure-urls"></a>Configurar URLs

1. Na página **Filtro de Conteúdo da Web**, escolha uma das configurações a seguir, conforme necessário:
   - **URLs Permitidas** – Na página **URLs Permitidas**, insira as URLs que você deseja permitir (ignorando o Filtro da Web da Apple) e escolha Enter após cada uma delas.
     > [!NOTE]
     > As URLs especificadas aqui são aquelas que você não deseja submeter ao filtro da Web da Apple. Essas URLs não representam uma lista com os únicos sites permitidos. Se for isso o que você deseja, use **Somente sites específicos**.

   - **URLs Bloqueadas** – Na página **URLs Bloqueadas**, insira as URLs que você deseja bloquear (independentemente das configurações do Filtro da Web da Apple) e selecione Enter após cada uma.
2. Ao terminar, clique em **OK**.


## <a name="specific-websites-only"></a>Somente sites específicos

1. No painel **Filtro de Conteúdo da Web**, para cada site da Web que você deseja permitir, defina as seguintes configurações:
    - **URL** – insira a URL do site que você deseja permitir, por exemplo, `https://www.contoso.com`.
    - **Caminho do Favorito** - insira o caminho até o local onde você deseja armazenar o favorito por exemplo **/Contoso/Aplicativos de Empresa**. Se você não adicionar um indicador, ele será adicionado à pasta de indicadores padrão no dispositivo.
    - **Título** - insira um título descritivo para o favorito.
2. Clique em **Adicionar** depois de inserir as informações para cada site.
3. Ao terminar, clique em **OK**.

> [!IMPORTANT]
> As URLs a seguir têm permissão automática do Intune.
> - <www.microsoft.com>
> - <www.microsoft.net>
> - <www.apple.com>

## <a name="finish-up"></a>Concluir

Escolha **OK** para retornar ao painel **Criar Perfil** e, em seguida, escolha **Criar**.

## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
