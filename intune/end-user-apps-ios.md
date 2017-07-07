---
title: "Como os usuários iOS podem obter aplicativos"
description: "Métodos para disponibilizar aplicativos do iOS para usuários finais"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0061d4ecd8d71f8b7363193e36b838741aa56a92
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="how-your-ios-users-get-their-apps"></a>Como os usuários iOS podem obter aplicativos

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Use estas informações para entender como e onde os usuários finais obtêm os aplicativos que você distribui por meio do Microsoft Intune.

**Aplicativos necessários** – Aplicativos que são exigidos pelo administrador e instalados no dispositivo com envolvimento mínimo do usuário, dependendo da plataforma.

**Aplicativos disponíveis** – Aplicativos fornecidos na lista de aplicativos do Portal da Empresa e que o usuário pode optar por instalar.

**Aplicativos gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas e que foram “encapsulados” pelo Intune ou compilados com o SDK (Software Development Kit) do MAM (Mobile Application Management) do Intune. Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.

**Aplicativos não gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas e que não foram encapsulados pelo Intune ou que não incorporam o SDK do MAM do Intune. Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.

As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da loja de aplicativos sejam listados no aplicativo do Portal da Empresa. Para solucionar esse problema, os blocos no aplicativo do Portal da Empresa para iOS encaminham os usuários a diferentes modos de exibição em um único local (o site do Portal da Empresa) para todos os seus aplicativos.

Os usuários registrados obtêm seus aplicativos tocando nos blocos a seguir na tela Aplicativos do aplicativo de Portal da Empresa:

- **Todos os Aplicativos** aponta para uma lista de todos os aplicativos na guia TODOS do [site do Portal da Empresa](https://portal.manage.microsoft.com).

- **Aplicativos em destaque** leva os usuários à guia EM DESTAQUE do site do Portal da empresa.

- **Categorias** aponta para a guia CATEGORIAS do site do Portal da Empresa.


![Tela de aplicativos do Portal da Empresa para iOS](./media/ios-cp-app-main-apps-screen.png)

Para obter informações sobre como adicionar aplicativos e colocá-los nesses blocos, consulte [Adicionar aplicativos para dispositivos registrados ao Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Consulte também
[Como os usuários do Android podem obter aplicativos](end-user-apps-android.md)

[Como os usuários do Windows podem obter aplicativos](end-user-apps-windows.md)
