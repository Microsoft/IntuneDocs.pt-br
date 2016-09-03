---
title: Restringir o acesso a email ao Dynamics CRM Online | Microsoft Intune
description: Proteja e controle o acesso ao Dynamics CRM Online com acesso condicional.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 875da922b311b06fa8a1eb8ba7207108684825d5


---

# Restringir o acesso a email ao Dynamics CRM Online com o Intune
Você pode controlar o acesso ao Microsoft Dynamics CRM Online de dispositivos iOS e Android com acesso condicional do Microsoft Intune.  Acesso condicional do Intune tem dois componentes:
* A [política de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md), com que o dispositivo deve estar em conformidade para ser considerado compatível.
* A [política de acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), na qual você especifica as condições que o dispositivo deve atender para acessar o serviço.

Para saber mais sobre como o acesso condicional funciona, leia o artigo [Restrict access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (Restringir acesso a email, O365 e outros serviços).

Quando um determinado usuário tenta usar o aplicativo Dynamics CRM em seu dispositivo, ocorre a seguinte avaliação:

![O diagrama mostra os pontos de decisão usados para determinar se um dispositivo tem acesso permitido ou bloqueado acesso a um serviço](../media/mdm-ca-dynamics-crm-flow-diagram.png)

O dispositivo que precisa acessar o Dynamics CRM Online deve:
* Ser um dispositivo **Android** ou **iOS**.
* Ser **registrado** com o Microsoft Intune.
* Ser **compatível** com qualquer política de conformidade do Microsoft Intune implantada.

O estado do dispositivo é armazenado no Azure Active Directory, que concede ou bloqueia o acesso com base nas condições que você especificar.

Se uma condição não for atendida, o usuário receberá uma das seguintes mensagens de erro ao fazer logon:
* Se o dispositivo não estiver registrado no Microsoft Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do portal da empresa e registrá-lo.
* Se o dispositivo não for compatível, será exibida uma mensagem que direciona o usuário ao site do Portal da Empresa do Microsoft Intune ou ao aplicativo Portal da Empresa, em que ele pode encontrar informações sobre o problema e como corrigi-lo.

## Configurar acesso condicional para o Dynamics CRM Online  
### Etapa 1: Configurar grupos de segurança do Active Directory

Antes de começar, configure os grupos de segurança do Active Directory do Azure para a política de acesso condicional. Você pode configurar esses grupos no **Centro de administração do Office 365**. Esses grupos serão usados para afetar ou isentar os usuários da política. Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.

Você pode especificar dois tipos de grupos para usar com a política do Dynamics CRM:
* **Grupos de destino** – contém grupos de usuários aos quais a política será aplicada.
* **Grupos isentos** – contém grupos de usuários isentos da política.

Se um usuário estiver nos dois grupos, ele ficará isento da política.

### Etapa 2: Configurar e implantar uma política de conformidade
[Crie](create-a-device-compliance-policy-in-microsoft-intune.md) e [implante](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) uma política de conformidade para todos os dispositivos que serão afetados pela política. Esses seriam todos os dispositivos usados pelos usuários nos Grupos de destino.

> [!NOTE]
> Enquanto as políticas de conformidade são implantadas em grupos do Microsoft Intune, as políticas de acesso condicional são destinadas a grupos de segurança do Azure Active Directory.

> [!IMPORTANT]
> Se você não tiver implantado uma política de conformidade, os dispositivos serão tratados como compatíveis.

Quando estiver pronto, continue na Etapa 3.
### Etapa 3: Configurar a política do Dynamics CRM
Em seguida, configure a política para exigir que somente dispositivos gerenciados e compatíveis possam acessar o Dynamics CRM. Essa política será armazenada no Active Directory do Azure.

1.  No console de administração do Microsoft Intune, escolha **Política > Acesso Condicional > Política do Dynamics CRM Online**.

  ![Captura de tela da página de política de acesso condicional do Dynamics CRM Online](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  Selecione **Habilitar política de acesso condicional**.
3.  Em **Acesso ao aplicativo**, você pode optar por aplicar a política de acesso condicional a:
  * **iOS**
  * **Android**
4.  Em **Grupos de Destino**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory aos quais a política será aplicada. Você pode optar por aplicá-la a todos os usuários ou apenas a um grupos seleto de usuários.
5.  Opcionalmente, em **Grupos Isentos**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory que são isentos dessa política.
6.  Quando terminar, selecione **Salvar**.

Você configurou o acesso condicional ao Dynamics CRM. Você não precisa implantar a política de acesso condicional, ele entra em vigor imediatamente.
##  Monitorar a conformidade e políticas de acesso condicional

No espaço de trabalho **Grupos** , você pode exibir o status de acesso condicional de seus dispositivos.

Selecione qualquer grupo de dispositivos móveis e então, na guia **Dispositivos** , selecione um dos seguintes **Filtros**:
* **Dispositivos que não estão registrados no AAD** – esses dispositivos estão bloqueados do Dynamics CRM.
* **Dispositivos que não são compatíveis** – esses dispositivos estão bloqueados do Dynamics CRM.
* **Dispositivos que estão registrados no AAD e são compatíveis** – esses dispositivos podem acessar o Dynamics CRM.

##  Próximas etapas
[Restringir o acesso ao Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)

[Restringir o acesso ao Exchange local](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
[Restringir o acesso ao SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Restringir o acesso ao Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->

