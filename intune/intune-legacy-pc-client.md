---
title: Cliente para PC herdado do Intune e Intune no Azure
description: Considerações ao usar o Intune no Azure para gerenciar os dispositivos do Windows de sua organização.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 27f3a184e355f63d20a79fd92e8326206f6eee15
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185620"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Intune no console do Azure e cliente para PC herdado do Intune

O Intune usa uma arquitetura de serviço de aplicativo SaaS baseada no Azure. O Azure fornece aprimoramentos consideráveis em desempenho, capacidade e escala. Isso oferece experiências de administração avançada do Intune e fluxos de trabalho otimizados no portal do Azure. 

Ao usar o Intune no Azure para gerenciar os dispositivos do Windows de sua organização, considere os seguintes pontos:

## <a name="manage-windows-10-devices-by-using-mdm"></a>Gerenciar dispositivos Windows 10 usando MDM

Recomendamos que você use [MDM (gerenciamento de dispositivo móvel) para gerenciar seus dispositivos com Windows 10](https://docs.microsoft.com/intune/device-restrictions-windows-10) em vez de usar o cliente herdado para PC do Intune. A capacidade de gerenciar o Windows 10 por MDM está disponível no Intune no Portal do Azure. O MDM do Windows 10 fornece muitos recursos novos de gerenciamento e segurança que não estão disponíveis por meio do cliente herdado para PC do Intune.

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Recursos herdados do Cliente para PC só estão disponíveis no console do Silverlight

Os fluxos de trabalho de gerenciamento do Cliente para PC do Intune usam o [Console de administração do Intune baseado no Silverlight](https://manage.microsoft.com/), o que tem as seguintes consequências:

- Para todas as tarefas de gerenciamento sem agrupamento que usam o Cliente para PC do Intune, você deve usar o console do Silverlight.
- Ao gerenciar grupos, você deve usar o [Intune no Portal do Azure](https://portal.azure.com/). Esse requisito existe porque o Intune usa Grupos do Azure AD em vez de Grupos herdados do Intune. 

Devido à mudança para os Grupos do Azure AD, a filtragem "baseada em grupo" nas exibições de painel de console do Silverlight mudou um pouco. Para filtrar na interface do usuário atualizada do Silverlight, execute estas etapas:

1. Selecione um modo de exibição.
2. Na caixa **Filtros**, insira o nome do grupo que você deseja filtrar e pressione Enter. Isso filtrará o modo de exibição de lista para os dispositivos nesse grupo específico.

   ![](media/intune-legacy-pc-client/image01.png)


## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Continuar a gerenciar o Windows 7 usando o cliente para PC do Intune

Para Windows 7, que não pode ser gerenciado por meio do MDM, continuaremos a dar suporte a recursos existentes de cliente para PC do Intune somente no console do Silverlight. Considere a migração para o gerenciamento por MDM ao atualizar para o Windows 10.

## <a name="mdm-capabilities"></a>Recursos de MDM

Para obter uma comparação detalhada do cliente para PC e dos recursos de MDM, veja [Comparar o gerenciamento de PCs com Windows como computadores ou dispositivos móveis](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison). As atualizações do MDM continuarão a trazer novos recursos de gerenciamento para dispositivos Windows 10 inscritos em MDM, incluindo opções de avaliação para aplicativos Win 32. Confira [Novidades](https://docs.microsoft.com/intune/whats-new) para conhecer as adições à versão mais recente do serviço.

## <a name="switch-from-pc-client-to-mdm"></a>Alternar do cliente para PC para MDM

Para alternar do gerenciamento de dispositivos Windows 10 com o Cliente para PC do Intune para o gerenciamento com MDM, execute estas etapas:

1. No console do Silverlight, execute um **Apagamento seletivo** para cancelar o registro do dispositivo no Cliente para PC.
  ![](media/intune-legacy-pc-client/image02.png)
2. Registrar novamente o dispositivo usando [MDM (e/ou Ingresso no Azure AD)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Próximas etapas
[Registrar dispositivos Windows](https://docs.microsoft.com/intune/windows-enroll)

 
