---
title: "Impedir vazamentos de dados da empresa de aplicativos móveis do Office 365"
description: "Use o Intune para proteger os dados de sua organização usando políticas de MAM (gerenciamento de aplicativo móvel) que ajudam a evitar vazamentos de dados da empresa de aplicativos móveis do Office 365 ou outros aplicativos de LOB (linha de negócios)."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3556c130402292450efc26f13f624861322e5ae7
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Guia de início rápido: Impedir vazamentos de dados da empresa de aplicativos móveis do Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune pode ajudá-lo a proteger os dados da sua organização usando políticas de MAM (gerenciamento de aplicativos móveis) que ajudam a evitar vazamentos de dados da empresa de aplicativos móveis do Office 365 ou outros aplicativos de LOB (linha de negócios). As políticas de MAM do Intune podem ser usadas sem a necessidade dos usuários finais registrarem seus dispositivos no MDM (gerenciamento de dispositivo móvel) do Intune. Portanto, se você tiver usuários que não desejam registrar seus dispositivos BYOD iOS ou Android em uma solução de MDM da Microsoft (Intune, Configuration Manager ou EAS), quiser proteger dados corporativos sem gerenciar dispositivos de usuários finais ou já estiver usando uma solução que não faz parte do MDM da Microsoft, o Intune poderá ajudar você a aumentar a segurança de dados da sua empresa.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Este é o guia de início rápido certo para mim?
Você gostaria de permitir que os usuários finais acessassem seus dados do Office 365 e de aplicativos de LOB em seus dispositivos Android e iOS sem a necessidade de registrar o dispositivo em uma solução de MDM (gerenciamento de dispositivo móvel), mas ainda controlar o que eles podem ou não fazer com esses dados, como copiar e colá-los em aplicativos pessoais?

Se sim, o Microsoft Intune permite que você defina políticas de MAM para aplicativos móveis do Office 365 no iOS e Android, inclusive restrições para recortar/copiar/colar, impedir “salvar como”, definir requisitos de PIN e a capacidade de apagar remotamente dados protegidos por MAM.  Isso protege os dados da empresa sem exigir que os usuários registrem seus dispositivos em uma solução de MDM, enquanto mantém uma excelente experiência do usuário final com aplicativos móveis do Office.

## <a name="how-do-i-do-it"></a>Como fazer isso?
1.  Tenha um entendimento básico de [como o MAM (gerenciamento de aplicativos móveis) do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) funciona.
2.  Descubra [o que você precisa fazer para começar a criar políticas de MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) no Portal do Azure.
3.  [Criar e implantar políticas de MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) com o Intune.

### <a name="additional-information"></a>Informação adicional:
- [Experiência do usuário final](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) usando aplicativos habilitados para MAM.
- [Preparar aplicativos de LOB para MAM com o Intune](/intune/apps-prepare-mobile-application-management)
- <a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> Lista de parceiros de aplicativos do Microsoft Intune &rarr;</a> que fornecem aplicativos habilitados para MAM.

## <a name="what-should-i-do-next"></a>O que devo fazer em seguida?
[Migrar de uma solução que não faz parte do MDM da Microsoft para o Microsoft Intune](/intune-classic/deploy-use/migrate-to-intune)

[Registrar dispositivos no MDM do Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
