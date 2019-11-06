---
title: Como os usuários iOS podem obter aplicativos
description: Métodos para disponibilizar aplicativos do iOS para usuários finais
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 06cc977ce8b0b892e1020436f89ada4a40bac3f2
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73413988"
---
# <a name="how-your-ios-users-get-their-apps"></a>Como os usuários iOS podem obter aplicativos

Use estas informações para entender como e onde os usuários finais obtêm os aplicativos que você distribui por meio do Microsoft Intune.

**Aplicativos necessários** – Aplicativos que são exigidos pelo administrador e instalados no dispositivo com envolvimento mínimo do usuário, dependendo da plataforma.

**Aplicativos disponíveis** – Aplicativos fornecidos na lista de aplicativos do Portal da Empresa e que o usuário pode optar por instalar.

**Aplicativos gerenciados** – aplicativos que podem ser gerenciados por meio de políticas e que foram "encapsulados" pelo Intune ou foram criados com o SDK (Software Development Kit) de Aplicativo do Intune. Esses aplicativos podem ser gerenciados pelo Intune e políticas de proteção de aplicativo podem ser aplicadas a eles.

**Aplicativos não gerenciados** – aplicativos que os usuários podem baixar da Loja de aplicativos do iOS que não estão integrados com o SDK de aplicativos do Intune. O Intune não tem qualquer controle sobre a distribuição, gerenciamento ou apagamento seletivo desses aplicativos.  

As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da loja de aplicativos sejam listados no aplicativo do Portal da Empresa. Para solucionar esse problema, os blocos no aplicativo do Portal da Empresa para iOS encaminham os usuários a diferentes modos de exibição em um único local (o site do Portal da Empresa) para todos os seus aplicativos.

Os usuários registrados obtêm seus aplicativos tocando nos blocos a seguir na tela Aplicativos do aplicativo de Portal da Empresa:

- **Todos os Aplicativos** aponta para uma lista de todos os aplicativos na guia TODOS do [site do Portal da Empresa](https://portal.manage.microsoft.com).

- **Aplicativos em destaque** leva os usuários à guia EM DESTAQUE do site do Portal da empresa.

- **Categorias** aponta para a guia CATEGORIAS do site do Portal da Empresa.

![Tela de aplicativos do Portal da Empresa para iOS](./media/end-user-apps-ios/ios-cp-app-main-apps-screen.png)

Para obter informações sobre como adicionar aplicativos, confira [Como adicionar um aplicativo ao Microsoft Intune](../apps/apps-add.md).

## <a name="see-also"></a>Consulte também

[Como os usuários do Android podem obter aplicativos](end-user-apps-android.md)

[Como os usuários do Windows podem obter aplicativos](end-user-apps-windows.md)
