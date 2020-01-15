---
title: Aplicativos para ambientes de alta GCC e DoD
titleSuffix: Microsoft Intune
description: Saiba mais sobre aplicativos que envolvem ambientes de alta GCC e DoD usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 29329f86-1aa5-434f-9925-8dc28bf35348
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5d37bf060f11be9e295a9ef2743fa0ba33844df7
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839347"
---
# <a name="deploying-apps-using-intune-on-the-gcc-high-and-dod-environments"></a>Como implantar aplicativos usando o Intune em ambientes de alta GCC e DoD 

O Microsoft Intune pode ser usado por administradores de locatários para distribuir aplicativos para sua força de trabalho. A força de trabalho são os funcionários da empresa, os usuários dos aplicativos. Há muitos tipos de aplicativos que podem ser implantados do Intune em ambientes de alta GCC ou DoD. Se um administrador precisar carregar e distribuir um aplicativo do Windows destinado para um público-alvo de alta GCC ou DoD personalizado, criado por fornecedores terceiros ou como um aplicativo offline baixado da [Microsoft Store para Empresas](https://businessstore.microsoft.com/store), o administrador poderá optar por distribuí-lo como um [aplicativo de linha de negócios](apps-add.md#app-types-in-microsoft-intune).  

> [!NOTE]
> Para ambientes comerciais, um administrador de locatários pode sincronizar sua Store para Empresas com o Intune; no entanto, para ambientes de alta GCC e DoD, este serviço não está disponível. Os administradores nesta situação devem implantar um aplicativo carregando diretamente no Intune.  

## <a name="add-line-of-business-apps-using-intune"></a>Adicionar aplicativos de linha de negócios usando o Intune 

Para adicionar um aplicativo de linha de negócios destinado a um ambiente de alta GCC ou DoD usando o Intune, é possível seguir as instruções do [aplicativo de LOB do Windows](lob-apps-windows.md). É possível optar por implantar primeiro o Portal da Empresa da Microsoft Store para Empresas. Se você optar por usar o Portal da Empresa, poderá instalar e implantar manualmente o Portal da Empresa. Para saber mais, confira [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](company-portal-app.md). 

## <a name="distribute-offline-apps-from-the-store-for-business-using-intune"></a>Distribuir aplicativos offline da Store para Empresas usando o Intune  

Se for necessário [baixar um aplicativo licenciado offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps#download-an-offline-licensed-app) da Microsoft Store para Empresas, siga estas etapas para baixar o aplicativo: 

1. Entrar na [Store para Empresas](https://businessstore.microsoft.com/).
2. Selecione **Gerenciar** > **Configurações**.
3. Em **Experiência de Compra**, defina **Mostrar aplicativos offline** como **Ativado**.

Ao comprar aplicativos, se uma versão offline estiver disponível, será possível optar por alterar o tipo de licença para offline. Após obter o aplicativo, será possível gerenciá-lo selecionando **Gerenciar** > **Produtos e Serviços** na [Store para Empresas](https://businessstore.microsoft.com/). Além disso, é possível baixar o aplicativo e suas dependências. Em seguida, será possível implantar esse aplicativo baixado (e suas dependências) em usuários que usam o Intune.  

## <a name="syncing-intune-to-the-store-for-business"></a>Como sincronizar o Intune com a Store para Empresas 

Em um ambiente comercial (não governamental), um administrador pode sincronizar o Intune com a Microsoft Store para Empresas. Esse não é um recurso disponível nos ambientes governamentais. Para saber mais sobre diferenças entre o Intune em ambientes comerciais e o Intune para ambientes do governo, confira [Descrição de Serviços do Enterprise Mobility + Security para o governo dos Estados Unidos](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description).  

Para sincronizar o Intune com sua conta da Microsoft Store para Empresas, confira [Como gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune](windows-store-for-business.md).  

## <a name="compliance"></a>Conformidade 

Examine as declarações de privacidade e de conformidade de aplicativos e compare-os com os requisitos de conformidade, de segurança e de privacidade de sua organização ao avaliar o uso apropriado desses serviços.   

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como implantar e atribuir aplicativos, confira [Atribuir aplicativos a grupos no Microsoft Intune](apps-deploy.md).

 
