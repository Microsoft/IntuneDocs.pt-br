---
title: Configurações da Proteção de Informações do Windows no Microsoft Intune | Microsoft Intune
description: Conheça as configurações do Microsoft Intune que você pode usar para gerenciar a Proteção de Informações do Windows.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6a5dea2075def1d7a30fdebc5722c4117a1579f
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229625"
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Como configurar a proteção de informações do Windows no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Com o aumento de dispositivos do funcionário na empresa, também há um risco crescente de vazamentos de dados acidentais por meio de aplicativos e serviços, como email, mídia social e nuvem pública, que estão fora do controle da empresa. Por exemplo, um funcionário envia as imagens mais recentes de engenharia de uma conta de email pessoal, copia e cola informações do produto em um tweet ou salva um relatório de vendas em andamento no armazenamento de nuvem pública.

A **Proteção de Informações do Windows** ajuda a proteger contra esse possível vazamentos de dados sem interferir na experiência do funcionário. Ele também ajuda a proteger dados e aplicativos corporativos e contra vazamentos de dados acidentais em dispositivos pessoais e de funcionários que os funcionários trazem para o trabalho sem a necessidade de alterações em seu ambiente ou outros aplicativos.

Essa política do Intune gerencia a lista de aplicativos protegidos pelo Windows Information Protection, os locais de rede corporativa, o nível de proteção e as configurações de criptografia.

>[!NOTE]
> Para usar o aplicativo Portal da Empresa do Windows 10 com a Proteção de Informações do Windows, você deve adicionar o aplicativo Portal da Empresa no modo **Isento** da Proteção de Informações do Windows. 

## <a name="next-steps"></a>Próximas etapas
Para obter mais informações, consulte:
-  [Proteja seus dados empresariais usando a Proteção de Informações do Windows](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
- [Criar uma política de WIP (Proteção de Informações do Windows) usando o console clássico do Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Criar uma política de WIP (Proteção de Informações do Windows) com MDM usando o portal do Azure para Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Criar uma política de WIP (Proteção de Informações do Windows) com MAM usando o portal do Azure para Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
