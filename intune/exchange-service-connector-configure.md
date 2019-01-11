---
title: Intune Exchange Connector para Exchange Online | Microsoft Intune
description: Conecte o Intune ao serviço Office 365 Exchange para dar suporte ao MDM (gerenciamento de dispositivo móvel) do Exchange ActiveSync.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9845ed1b809b611975c07c6c8335acd237d845c0
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816694"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Configure o conector de serviço do Exchange para Intune e Exchange Online
Este artigo mostra como se conectar o serviço Microsoft Intune ao Exchange Online ou ao novo serviços Exchange Online Dedicado. Para determinar se o seu ambiente Exchange Online Dedicado está na versão **nova** ou **herdada**, entre em contato com seu gerente de conta.

Com o **Service to Service Connector**, é possível controlar os dispositivos gerenciados do EAS (Exchange ActiveSync) e do Intune usando um único console administrativo.  O conector não é necessário para habilitar o Acesso condicional para o Exchange Online.

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

1. Entre no [portal do Azure](https://portal.azure.com) com uma conta de usuário com direitos de administrador do Exchange e permissões para os cmdlets [descritos acima](#exchange-cmdlet-requirements), uma licença válida do Intune e a função de Administrador Global. O Microsoft Intune usa o endereço de email do usuário conectado no momento para configurar a conexão.

2. Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** para abrir o painel do Microsoft Intune. Escolha **Acesso condicional** e, em **Instalação**, escolha **Conector de serviço do Exchange**.

4.  Na página **Acesso condicional - Conector de serviço do Exchange**, escolha **Configurar Conector de Serviço a Serviço**. 
   
     ![Imagem mostrando a seleção do link Configurar Conector Serviço a Serviço](media/exchange_service_connector.png)

O Service to Service Connector configura e sincroniza automaticamente seu ambiente do Exchange Online ou do novo Exchange Online Dedicado.

## <a name="validate-your-exchange-connection"></a>Validar a sua conexão do Exchange

Após a configuração do Conector de Serviço a Serviço do Exchange, valide as informações do Servidor de Conector do Exchange na página **Acesso condicional - Connector de serviço do Exchange**.

Você também pode verificar o **Status de conexão** na data e hora da última tentativa de sincronização bem-sucedida.

 