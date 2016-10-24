---
title: Acesso condicional baseado em aplicativo ao O365 | Microsoft Intune
description: "Entenda como o AC para MAM pode ajudar a controlar os aplicativos que têm acesso aos serviços do O365."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Crie uma política que permita apenas aos aplicativos móveis que dão suporte às políticas de MAM do Intune acessar os serviços do Office 365
As [Políticas de gerenciamento de aplicativos móveis (MAM) do Intune](protect-apps-and-data-with-microsoft-intune.md) ajudam a proteger os dados da empresa em dispositivos registrados para gerenciamento no Intune. É possível usar as políticas MAM em **dispositivos do funcionário que não estão registrados para gerenciamento no Intune**.  Nesse caso, mesmo que você não gerencie o dispositivo, ainda é necessário se certificar de que os dados e recursos da empresa estão protegidos. Ao usar o acesso condicional para MAM (MAM CA), você pode criar uma política que permita aos aplicativos móveis que dão suporte às políticas de MAM do Intune acessar serviços do O365, como o Exchange Online.

Por exemplo, ao permitir que apenas o **aplicativo do Microsoft Outlook** acesse o Exchange Online você pode **bloquear os aplicativos de email interno no iOS e no Android**, que não têm a proteção de dados das políticas de MAM do Intune, para receber email do **Exchange Online**.

## Pré-requisitos
**Antes** de configurar uma política de AC de MAM, você deve ter uma **assinatura premium do Enterprise Mobility + Security ou do Azure Active Directory** e os usuários devem ser licenciados para o EMS ou Azure AD. Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Aplicativos com suporte
**Exchange Online**
* Microsoft Outlook para Android e iOS

## Sobrepõe outros métodos de acesso condicional e autenticação
### AC de MAM com autenticação baseada em certificado do Azure Active Directory

O AC de MAM não deve ser usado com a autenticação baseada em certificado do Azure Active Directory (Azure AD). Só é possível ter um deles configurado de cada vez.
### AC do MAM com acesso condicional baseado na conformidade do dispositivo  

Você pode configurar o [Acesso condicional baseado na conformidade do dispositivo](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**AC do Dispositivo**) no [console do administrador do Intune](https://manage.microsoft.com) ou no [console de gerenciamento do Azure AD Premium] (https://manage.windowsazure.com). O AC do dispositivo exige que os usuários se conectem ao Exchange Online somente por meio de dispositivos gerenciados pelo Intune que estejam em conformidade com a política de conformidade do dispositivo do Intune ou computadores de domínio associado.  Se um usuário pertencer a um ou mais grupos de segurança destinados a políticas de AC de MAM e de AC do dispositivo, o usuário deverá atender a um dos dois requisitos:
* O aplicativo usado para acessar o serviço é móvel com suporte do AC do MAM e o dispositivo no qual aplicativo está sendo executado tem um **Autenticador iOS (para dispositivos iOS)** ou o **aplicativo do Portal da Empresa (para dispositivos Android)** instalados.
* O dispositivo utilizado para acessar o serviço é **compatível e gerenciado pelo Intune** com a política de conformidade do dispositivo do Intune ou é um **computador de domínio associado**.  Aqui estão alguns exemplos para ajudar a ilustrar essa situação:
  * Se um usuário tentar se conectar por meio do **aplicativo de email nativo do iOS**, ele deverá usar um **dispositivo gerenciado e compatível**, pois não há suporte do AC do MAM para o aplicativo de email nativo.
  * Se um usuário tentar se conectar por meio de um **computador doméstico Windows**, a **política de AC do dispositivo** será aplicada, exigindo que o usuário use um computador de domínio associado.


## O que esperar ao usar um aplicativo com AC do MAM
O AC de MAM verifica a identidade do aplicativo aprovado por meio de um aplicativo agente, que deve estar presente no dispositivo:
*  No **iOS**, o **aplicativo Microsoft Authenticator** é o aplicativo agente.
* No **Android**, o **aplicativo do Portal da Empresa do Intune** é o aplicativo agente. 

Quando os usuários finais entram pela primeira vez em um aplicativo em que há suporte para AC de MAM, como o OneDrive ou o Outlook, eles são solicitados a instalar o aplicativo agente e a registrar o dispositivo com o Azure AD. O registro de dispositivos no Azure AD (anteriormente conhecido como Ingresso no Local de Trabalho) criará um registro de dispositivo e um certificado no qual os tokens serão emitidos.  Esse processo **não** é igual ao **registro do MDM**. Não há perfis de gerenciamento ou políticas aplicadas e não há nenhum inventário de aplicativos do dispositivo.  O processo de instalação do aplicativo agente e de registro do dispositivo só ocorrerá quando o aplicativo gerenciado for usado pela primeira vez.


## Próximas etapas
[Criar uma política do Exchange Online para aplicativos MAM](mam-ca-for-exchange-online.md)

[Bloquear aplicativos que não têm autenticação moderna](block-apps-with-no-modern-authentication.md)

### Consulte também

[Proteger os dados do aplicativo com políticas de MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


