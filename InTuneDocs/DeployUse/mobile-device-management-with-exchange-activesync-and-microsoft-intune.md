---
title: Gerenciamento de Dispositivo do Exchange ActiveSync | Microsoft Intune
description: "Gerencie diretamente dispositivos móveis não registrados pelos usuários com o gerenciamento do EAS (Exchange ActiveSync) usando o Exchange Connector"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: f545c7db4c29690a72c5a84dfcab6f179cbe72a2


---

# Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Microsoft Intune
Para o Microsoft Intune gerenciar dispositivos móveis diretamente, os usuários precisarão registrar os dispositivos no Intune. É possível habilitar o gerenciamento do EAS (Exchange ActiveSync) para os dispositivos móveis que os usuários não registraram usando o Exchange Connector. Dispositivos podem ser gerenciados nos servidores locais e hospedado no Exchange hospedado na nuvem do Microsoft Office 365.

## Regras de acesso do Exchange para dispositivos móveis ##

O Exchange precisa de um conjunto de regras que define o que acontece quando os dispositivos móveis tentam se conectar ao EAS. Essas regras são gerenciadas no console de administração do Intune.

[Regras de acesso do Exchange para dispositivos móveis](exchange-access-rules-for-mobile-devices.md)

## Problemas com o Exchange Connector
O Exchange Connector permite gerenciar a implantação do Exchange no console do Intune. Primeiro instale e configure o conector do Intune para Exchange apropriado. Escolha a opção apropriada com base em se o servidor Exchange está local ou hospedado como um serviço em nuvem:

-   [Instalar o conector do Intune para o Exchange local](intune-on-premises-exchange-connector.md)
-   [Configurar o Intune Service to Service connector para o Exchange hospedado](intune-service-to-service-exchange-connector.md)

## Aplicar política a dispositivos móveis gerenciados pelo Exchange
As configurações da política podem ser aplicadas pelo console do Intune, consulte [Manage settings and features on your devices with Microsoft Intune policies (Gerenciar configurações e funcionalidades em seus dispositivos com as políticas do Microsoft Intune)](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Para obter uma lista das configurações de política do Exchange ActiveSync e funcionalidades com suporte de dispositivos móveis específicos, consulte [Exchange ActiveSync Client Comparison Table (Tabela de Comparação do Cliente Exchange ActiveSync)](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Após conectar o Intune a um ambiente do Microsoft Exchange, a política EAS de todos os usuários gerenciados por meio do Intune será redefinida para a política padrão atual no Microsoft Exchange Server, a menos que haja uma política mais específica definida no Intune.

## Apagar os dados da empresa de dispositivos móveis
Por fim, você pode [apagar os dados da empresa dos dispositivos móveis gerenciados EAS](wipe-for-exchange-managed-mobile-devices.md) quando eles não estão mais em uso ou se os dispositivos forem perdidos ou roubados.



<!--HONumber=Jul16_HO4-->


