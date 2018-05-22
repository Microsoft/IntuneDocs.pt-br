---
title: Conector do Exchange do Intune para Exchange Online
titleSuffix: ''
description: Conecte o Intune ao serviço Office 365 Exchange para dar suporte ao MDM (gerenciamento de dispositivo móvel) do Exchange ActiveSync.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 640d1a5cbd785248cb309bc250c95631295955b3
ms.sourcegitcommit: 71497f0215fc8bed454ac318b0548b1281a8fe0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Configure o conector de serviço do Exchange para Intune e Exchange Online

Este artigo mostra como se conectar o serviço Microsoft Intune ao Exchange Online ou ao novo serviços Exchange Online Dedicado. Para determinar se o seu ambiente Exchange Online Dedicado está na versão **nova** ou **herdada**, entre em contato com seu gerente de conta.

## <a name="service-to-service-connector-requirements"></a>Requisitos para o Service to Service Connector
O **Conector de Serviço a Serviço** tem suporte apenas para o Exchange Online ou para o novo Exchange Online Dedicado e não tem requisitos de infraestrutura local.


|              Requisito               |                                                                                                            Mais informações                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange Online configurado e em execução |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Autoridade de gerenciamento de dispositivo móvel   |                                                       [Configurar a autoridade de gerenciamento de dispositivo móvel para o Microsoft Intune](mdm-authority-set.md)                                                       |
|       Versão do Microsoft Exchange       |                                                                                      Serviço Exchange Online ou o novo Exchange Online Dedicado                                                                                      |
|    Sincronização do Active Directory    | Antes de usar o Conector do Intune, é preciso [configurar a sincronização do Active Directory](/intune/users-add) para que os usuários e grupos de segurança locais sejam sincronizados com sua instância do Azure Active Directory. |

### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

Também é preciso criar uma conta de usuário do Exchange Online que seja usada pelo conector de serviço do Intune Exchange. A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange necessários:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Configurar o Conector de Serviço a Serviço

1. Entre no [Portal do Azure](http://portal.azure.com) com uma conta de usuário com direitos de administrador do Exchange e permissões para os cmdlets [descritos acima](#exchange-cmdlet-requirements). O Microsoft Intune usa o endereço de email do usuário conectado no momento para configurar a conexão.

2. Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** para abrir o painel do Microsoft Intune. Escolha **Acesso condicional** e, em **Instalação**, escolha **Conector de serviço do Exchange**.

4.  Na página **Acesso condicional - Conector de serviço do Exchange**, escolha **Configurar Conector de Serviço a Serviço**. 
   
     ![Imagem mostrando a seleção do link Configurar Conector Serviço a Serviço](media/exchange_service_connector.png)

O Service to Service Connector configura e sincroniza automaticamente seu ambiente do Exchange Online ou do novo Exchange Online Dedicado.

## <a name="validate-your-exchange-connection"></a>Validar a sua conexão do Exchange

Após a configuração do Conector de Serviço a Serviço do Exchange, valide as informações do Servidor de Conector do Exchange na página **Acesso condicional - Connector de serviço do Exchange**.

Você também pode verificar o **Status de conexão** na data e hora da última tentativa de sincronização bem-sucedida.

## <a name="next-steps"></a>Próximas etapas
[Monitorar o acesso condicional do Exchange no Microsoft Intune](conditional-access-exchange-monitor.md)