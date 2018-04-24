---
title: Gerenciamento de dispositivos do Exchange ActiveSync
description: Gerenciar dispositivos móveis com o gerenciamento do Exchange ActiveSync (EAS) usando o conector do Exchange
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f5e9bd3dd2026096c323858fc7faa915895ed55d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a>Gerenciamento de dispositivos móveis do Exchange ActiveSync com o Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Para o Microsoft Intune gerenciar dispositivos móveis diretamente, os dispositivos devem ser [registrados no Intune](prerequisites-for-enrollment.md). Como alternativa, os administradores podem habilitar uma solução de gerenciamento mais limitada que usa o gerenciamento do EAS (Exchange ActiveSync) com um conector do Exchange. Dispositivos podem ser gerenciados nos servidores Exchange locais ou no Exchange Online usando o Microsoft Office 365. O Intune dá suporte apenas a uma conexão do conector do Exchange de qualquer tipo por assinatura.

## <a name="exchange-access-rules-for-mobile-devices"></a>Regras de acesso do Exchange para dispositivos móveis ##

O Exchange precisa de um conjunto de regras que define o que acontece quando os dispositivos móveis tentam se conectar ao EAS. Essas regras são gerenciadas no console de administração do Intune.

[Regras de acesso do Exchange para dispositivos móveis](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a>Problemas com o Exchange Connector
O Exchange Connector permite gerenciar a implantação do Exchange no console do Intune. Primeiro instale e configure o conector do Intune para Exchange apropriado. Escolha a opção apropriada com base em se o servidor Exchange é local ou hospedado como um serviço em nuvem:

-   [Configurar o Intune para o Exchange Online ou novos ambientes do Exchange Online Dedicated](intune-service-to-service-exchange-connector.md)
-   [Instalar o conector do Intune para servidores do Exchange locais e ambientes do Exchange Online Dedicated herdados](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a>Aplicar política a dispositivos móveis gerenciados pelo Exchange
O console do Intune pode ser usado para gerenciar [configurações de política EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) e [restringir o acesso aos recursos da empresa](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Para obter uma lista de recursos e configurações de política do Exchange ActiveSync com suporte de dispositivos móveis específicos, consulte [Tabela de Comparação do Cliente Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Após conectar o Intune a um ambiente do Microsoft Exchange, a política EAS de todos os usuários gerenciados por meio do Intune será redefinida para a política padrão atual no Microsoft Exchange Server, a menos que haja uma política mais específica definida no Intune.

## <a name="wipe-company-data-from-mobile-devices"></a>Apagar os dados da empresa de dispositivos móveis
Por fim, você pode [apagar os dados da empresa dos dispositivos móveis gerenciados EAS](wipe-for-exchange-managed-mobile-devices.md) quando eles não estão mais em uso ou se os dispositivos forem perdidos ou roubados.
