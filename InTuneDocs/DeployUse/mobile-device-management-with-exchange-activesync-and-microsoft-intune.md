---
title: Gerenciamento de Dispositivo do Exchange ActiveSync | Microsoft Intune
description: "Gerenciar dispositivos móveis com o gerenciamento do Exchange ActiveSync (EAS) usando o conector do Exchange"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: de3296e81c88b3ac04e3ba3f3d3ca222a59df7bd
ms.openlocfilehash: 96d8911dafe7897458297867ddfef97206fdfc9c


---

# Gerenciamento de dispositivos móveis do Exchange ActiveSync com o Microsoft Intune
Para o Microsoft Intune gerenciar dispositivos móveis diretamente, os dispositivos devem ser [registrados no Intune](get-ready-to-enroll-devices-in-microsoft-intune.md). Como alternativa, os administradores podem habilitar uma solução de gerenciamento mais limitada que usa o gerenciamento do Exchange ActiveSync (EAS) com um conector do Exchange. Dispositivos podem ser gerenciados nos servidores Exchange locais e no Exchange Online usando o Microsoft Office 365. O Intune oferece suporte apenas a uma conexão do conector do Exchange de qualquer tipo por assinatura.

## Regras de acesso do Exchange para dispositivos móveis ##

O Exchange precisa de um conjunto de regras que define o que acontece quando os dispositivos móveis tentam se conectar ao EAS. Essas regras são gerenciadas no console de administração do Intune.

[Regras de acesso do Exchange para dispositivos móveis](exchange-access-rules-for-mobile-devices.md)

## Problemas com o Exchange Connector
O Exchange Connector permite gerenciar a implantação do Exchange no console do Intune. Primeiro instale e configure o conector do Intune para Exchange apropriado. Escolha a opção apropriada com base em se o servidor Exchange está local ou hospedado como um serviço em nuvem:

-   [Configurar o Intune para os ambientes Exchange Online ou o novo Exchange Online Dedicated](intune-service-to-service-exchange-connector.md)
-   [Instalar o conector do Intune para servidores do Exchange locais e ambientes Exchange Online Dedicated herdados](intune-on-premises-exchange-connector.md)


## Aplicar política a dispositivos móveis gerenciados pelo Exchange
O console do Intune pode ser usado para gerenciar [configurações de política EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) e [restringir o acesso aos recursos da empresa](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Para obter uma lista das configurações de política do Exchange ActiveSync e funcionalidades com suporte de dispositivos móveis específicos, consulte [Exchange ActiveSync Client Comparison Table (Tabela de Comparação do Cliente Exchange ActiveSync)](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Após conectar o Intune a um ambiente do Microsoft Exchange, a política EAS de todos os usuários gerenciados por meio do Intune será redefinida para a política padrão atual no Microsoft Exchange Server, a menos que haja uma política mais específica definida no Intune.

## Apagar os dados da empresa de dispositivos móveis
Por fim, você pode [apagar os dados da empresa dos dispositivos móveis gerenciados EAS](wipe-for-exchange-managed-mobile-devices.md) quando eles não estão mais em uso ou se os dispositivos forem perdidos ou roubados.



<!--HONumber=Jul16_HO5-->


