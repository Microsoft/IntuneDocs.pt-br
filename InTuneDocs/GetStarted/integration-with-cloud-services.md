---
title: "Integração do Intune com serviços em nuvem da Microsoft | Microsoft Intune"
description: "Integração do Intune com produtos e serviços em nuvem da Microsoft e com outros produtos da Microsoft"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 83020d347a4bc036778d830f5189e68e7f8d85da


---

# Integração do Intune com produtos e serviços em nuvem da Microsoft

Antes de configurar o [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], examine este tópico e outros requisitos listados em [O que saber antes de começar a usar Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).
##Integração com outros serviços em nuvem da Microsoft


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] compartilha uma base comum com outros serviços em nuvem da Microsoft. Ao usar a mesma conta para assinar vários serviços de nuvem, esses serviços usam a mesma infraestrutura do AD do Microsoft Azure e são locatários do AD do Azure. O AD Azure fornece os principais recursos de gerenciamento de identidades e diretórios de serviços em nuvem da Microsoft.

Saiba mais sobre como [administrar o Azure AD](http://technet.microsoft.com/library/hh967611.aspx) na biblioteca do TechNet.

## Integração com outros produtos da Microsoft
Você pode usar o [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] como um serviço de nuvem autônomo ou como um serviço de nuvem integrado a outros produtos. Atualmente, apenas o [!INCLUDE[cmshort](../includes/cmshort_md.md)] pode ser integrado diretamente ao [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

A decisão de integrar o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ao [!INCLUDE[cmshort](../includes/cmshort_md.md)] é uma escolha permanente que requer que você defina a autoridade de gerenciamento de dispositivos móveis a partir do console do [!INCLUDE[cmshort](../includes/cmshort_md.md)] e não a partir do [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. Depois que a autoridade de gerenciamento de dispositivo móvel é definida, não é possível alterar ou reverter esta configuração.

Ao usar o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] com o [!INCLUDE[cmshort](../includes/cmshort_md.md)], [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] não é utilizado para gerenciar o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] e sim o console do [!INCLUDE[cmshort](../includes/cmshort_md.md)]. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ainda usa seu armazenamento em nuvem no Azure para hospedar o software que você implanta nos dispositivos gerenciados com [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Para obter mais informações, consulte [Manage Mobile Devices with Configuration Manager and Microsoft Intune (Gerenciar dispositivos móveis com o Configuration Manager e o Microsoft Intune)](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) na documentação do [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1.

### Consulte também
[O que saber antes de começar a usar o Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


