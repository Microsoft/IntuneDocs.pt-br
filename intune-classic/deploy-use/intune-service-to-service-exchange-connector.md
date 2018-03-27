---
title: Exchange Connector para o Exchange Online
description: Conecte o Intune ao serviço Office 365 Exchange para dar suporte ao MDM (gerenciamento de dispositivo móvel) do Exchange ActiveSync.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 78b4e91fd61bb79c2a3a6d86d5a79c39b320cc5e
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Configurar o Service to Service Connector do Intune para o Exchange Online

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use essas informações para conectar o serviço Microsoft Intune e Exchange Online ou o novo Exchange Online Dedicado. Para determinar se o seu ambiente Exchange Online Dedicado está na versão **nova** ou **herdada**, entre em contato com seu gerente de conta. O Intune oferece suporte apenas a uma conexão do conector do Exchange de qualquer tipo por assinatura.

## <a name="service-to-service-connector-requirements"></a>Requisitos para o Service to Service Connector
O **Service to Service Connector** tem suporte apenas para o Exchange Online ou para o novo Exchange Online Dedicado e não tem requisitos de infraestrutura local.

|Requisito|Mais informações|
|---------------|--------------------|
|Exchange Online configurado e em execução|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autoridade de gerenciamento de dispositivo móvel| [Configurar a autoridade de gerenciamento de dispositivo móvel para o Microsoft Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Versão do Microsoft Exchange|Serviço Exchange Online ou o novo Exchange Online Dedicado|/intune/users-permissions-add
|Sincronização do Active Directory|Antes de usar o Conector do Intune, é preciso [configurar a sincronização do Active Directory](/intune/users-permissions-add) para que os usuários e grupos de segurança locais sejam sincronizados com sua instância do Azure Active Directory.|

### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

Também é preciso criar uma conta de usuário do Exchange Online que seja usada pelo Intune Exchange Connector. A conta deve ter permissão para usar o console de administração do Intune e executar os seguintes cmdlets necessários do Windows PowerShell Exchange:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Configurar o Conector de Serviço a Serviço

1. Abra o [console de administração do Microsoft Intune](https://manage.microsoft.com) com uma conta de usuário com direitos de administrador do Exchange e permissões para os cmdlets [descritos acima](#exchange-cmdlet-requirements). O Microsoft Intune usa o endereço de email do usuário conectado no momento para configurar a conexão.

2.  No painel de atalhos do espaço de trabalho, selecione **ADMIN**>**Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange** > **Configurar Conexão com o Exchange**.
![Configurar página do Service to Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na página **Configurar a Conexão do Exchange**, clique em **Configurar o Conector de Serviços**.


O Service to Service Connector configura e sincroniza automaticamente seu ambiente do Exchange Online ou do novo Exchange Online Dedicado.

## <a name="validate-your-exchange-connection"></a>Validar a sua conexão do Exchange

Após configurar com êxito o Exchange Connector, vá para o [console de administração do Microsoft Intune](https://manage.microsoft.com). Selecione **Admin**> **Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange**. Em seguida, confirme se os detalhes fornecidos aparecem em **Informações sobre Conexão com o Exchange**.

Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.
