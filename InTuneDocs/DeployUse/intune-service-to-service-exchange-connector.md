---
# required metadata

title: Configurar o conector do Microsoft Intune Exchange para o Exchange hospedado | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurar o Intune Service to Service Connector para Exchange Online

Use essas informações para conectar o serviço Microsoft Intune e Exchange Online hospedado pelo Office 365.

## Requisitos para o Service to Service Connector
O **Service to Service Connector** tem suporte apenas para o Exchange hospedado e não tem requisitos de infraestrutura local.

|Requisito|Mais informações|
|---------------|--------------------|
|Hosted Exchange configurado e em execução|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autoridade de gerenciamento de dispositivo móvel| [Configurar a autoridade de gerenciamento de dispositivo móvel para o Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Versão do Microsoft Exchange|Você deve ter uma assinatura do Office 365 que tenha um Exchange Server 2013 ou locatário posterior. Desde que o locatário seja o Exchange Server 2013 ou posterior, o conector terá suporte para o Exchange Server 2010 no mesmo ambiente.|
|Sincronização do Active Directory|Antes de usar o Conector do Intune, é preciso [configurar a sincronização do Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) para que os usuários e grupos de segurança locais sejam sincronizados com sua instância do Azure Active Directory.|

### Requisitos de cmdlets do Exchange

Também é preciso criar uma conta de usuário do Exchange Online que seja usada pelo Intune Exchange Connector. A conta deve ter permissão para usar o console do administrador do Intune e executar estes cmdlets do Windows PowerShell Exchange necessários:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Configurar o Service to Service Connector

1. Abra o [console de administração do Microsoft Intune](http://manage.microsoft.com) com uma conta de usuário com direitos de administrador do Exchange e permissões para os cmdlets [acima](#exchange-cmdlet-requirements). O Microsoft Intune usa o endereço de email do usuário conectado no momento para configurar a conexão.

2.  No painel de atalhos do espaço de trabalho, escolha **ADMIN**, acesse **Gerenciamento de Dispositivos Móveis** > **Microsoft Exchange** > **Configurar Conexão do Exchange**.
![Configurar página do Service to Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na página **Configurar a Conexão do Exchange**, clique em **Configurar o Service to Service Connector**.


O Service to Service Connector será configurado e sincronizado automaticamente com o ambiente do Exchange Hospedado.

## Validar a sua conexão do Exchange

Após configurar com êxito o Exchange Connector, no console do administrador do Intune, escolha o espaço de trabalho **ADMINISTRADOR** e acesse **Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange** e valide que os detalhes fornecidos aparecem em **Informações de Conexão do Exchange**.

Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.


<!--HONumber=May16_HO1-->


