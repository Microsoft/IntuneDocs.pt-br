---
title: "Configurações de filtro de conteúdo da Web do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar para permitir e bloquear o acesso a sites em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fb2ce8ed9db6ff808cac2ee8ff46ee865dbdf35
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Configurações de filtro de conteúdo da Web para dispositivos iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações para definir as URLs que os usuários finais de navegadores da Web, em dispositivos iOS, podem ou não visitar. Existem dois métodos que você pode usar para configurar URLs:

- **Configurar URLs** – Use o filtro da Web interno da Apple que procura termos adultos como profanação ou linguagem pornográficas. Essa função avalia cada página da Web conforme ela é carregada e tenta identificar e bloquear conteúdo inadequado. Você também pode configurar as URLs que não serão verificadas pelo filtro ou URLs que serão sempre bloqueadas, independentemente das configurações do filtro.

- **Somente para sites específicos** (somente para o navegador da Web Safari somente) - essas URLs são adicionadas aos favoritos do navegador Safari. O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser acessado. Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.
Se você não especificar nenhuma URL, os usuários finais não poderão acessar nenhum site, exceto microsoft.com, microsoft.net e apple.com.



## <a name="get-started"></a>Introdução

1. Na folha Recursos do dispositivo escolha **Filtro de Conteúdo da Web (somente supervisionado)**.
2. Na folha **Filtro de Conteúdo da Web**, escolha o **Tipo de filtro** que você deseja configurar:
    - **Não Configurado** - nenhuma filtragem será executada.
    - **Configurar URLs**
    - **Somente sites específicos**
3. Em seguida, dependendo do tipo de filtro que você estiver usando, siga um destes procedimentos:


## <a name="configure-urls"></a>Configurar URLs

1. Na folha **Filtro de Conteúdo da Web**, escolha uma das configurações a seguir, conforme necessário:
    - **URLs Permitidas** - na folha **URLs Permitidas**, insira as URLs que você deseja permitir (ignorando o Filtro da Web da Apple) e escolha enter após cada uma.
    - **URLs Bloqueadas** - na folha **URLs Bloqueadas**, insira as URLs que você deseja bloquear (independentemente das configurações do Filtro da Web da Apple) e escolha enter após cada uma.
2. Ao terminar, clique em **OK**.


## <a name="specific-websites-only"></a>Somente sites específicos

1. Na folha **Filtro de Conteúdo da Web**, para cada site da Web que você deseja permitir, defina as seguintes configurações:
    - **URL** - insira a URL do site que você deseja permitir, por exemplo, **http://www.contoso.com**.
    - **Caminho do Favorito** - insira o caminho até o local onde você deseja armazenar o favorito por exemplo **/Contoso/Aplicativos de Empresa**. Se você não adicionar um indicador, ele será adicionado à pasta de indicadores padrão no dispositivo.
    - **Título** - insira um título descritivo para o favorito.
2. Clique em **Adicionar** depois de inserir as informações para cada site.
3. Ao terminar, clique em **OK**.

>[!IMPORTANT] 
> As URLs a seguir têm permissão automática do Intune.
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## <a name="finish-up"></a>Concluir

Escolha **OK** para retornar à folha **Criar Perfil** e, em seguida, escolha **Criar**.

## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
