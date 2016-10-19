---
title: "Como os usuários iOS podem obter aplicativos | Microsoft Intune"
description: "Métodos para disponibilizar aplicativos do iOS para usuários finais"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 37841027c7ae040163440a19f9e163fb4eb87233
ms.openlocfilehash: ad780fb3403f6caaee1218d785a5cad326c18df5


---


# Como os usuários iOS podem obter aplicativos

Use estas informações para entender como e onde os usuários finais obtêm os aplicativos que você distribui por meio do Microsoft Intune.

**Aplicativos necessários** – Aplicativos que são exigidos pelo administrador e instalados no dispositivo com envolvimento mínimo do usuário, dependendo da plataforma.

**Aplicativos disponíveis** – Aplicativos fornecidos na lista de aplicativos do Portal da Empresa e que o usuário pode optar por instalar.

**Aplicativos gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas e que foram “encapsulados” pelo Intune ou compilados com o SDK (Software Development Kit) do MAM (Mobile Application Management) do Intune. Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.

**Aplicativos não gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas e que não foram encapsulados pelo Intune ou que não incorporam o SDK do MAM do Intune. Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.

As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da loja de aplicativos sejam listados no aplicativo do Portal da Empresa. Para solucionar esse problema, os blocos no aplicativo do Portal da Empresa para iOS encaminham os usuários a diferentes modos de exibição em um único local (o site do Portal da Empresa) para todos os seus aplicativos.

- Anteriormente, **Aplicativos da Empresa** apontava para uma lista de todos os aplicativos na guia TODOS do [site do Portal da Empresa](http://portal.manage.microsoft.com) e continuará funcionando da mesma maneira. O nome do bloco foi alterado para **Todos os Aplicativos**.

- Anteriormente, **Outros Aplicativos** apontava para um modo de exibição no aplicativo do Portal da Empresa que listava todos os aplicativos que a Apple permite que o aplicativo do Portal da Empresa mostre. O nome do bloco foi alterado para **Aplicativos em Destaque** e, ao tocar no bloco, os usuários são levados para a guia EM DESTAQUE do site Portal da Empresa.

-  **Categorias** apontava para um modo de exibição no aplicativo do Portal da Empresa que listava categorias de aplicativos. O nome do bloco não foi alterado, mas agora ele aponta para a guia CATEGORIAS do site Portal da Empresa.
Você pode encontrar capturas de tela atualizadas em [Melhorias na maneira como os usuários finais do iOS obtêm seus aplicativos](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).



### Consulte também
[Como os usuários Android podem obter aplicativos](how-your-android-users-get-their-apps.md)

[Como os usuários Windows podem obter aplicativos](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


