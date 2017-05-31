---
title: "Aplicativos iOS com políticas de proteção do aplicativo | Microsoft Docs"
description: "Este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 92a91fab353c78c751ae5eb25c9853df5cbcfe53
ms.contentlocale: pt-br
ms.lasthandoff: 05/31/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 Este tópico descreve a experiência do usuário ao usar aplicativos com políticas de proteção de aplicativo aplicadas. As políticas do aplicativo são aplicadas somente quando aplicativos são usados no contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no OneDrive para Empresas.

##  <a name="access-apps"></a>Acessar aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário será solicitado a reiniciar o aplicativo ao usá-lo pela primeira vez. Uma reinicialização é necessária para que essas políticas de proteção de aplicativo possam ser aplicadas ao aplicativo. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Em dispositivos **registrados para gerenciamento no Intune**, o usuário verá uma mensagem informando que seu aplicativo agora é gerenciado.

##  <a name="use-apps-with-multi-identity-support"></a>Usar aplicativos com suporte a várias identidades

Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos quando políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.  

Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho. No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo. No **aplicativo OneDrive**, o usuário será solicitado a fornecer um PIN ao digitar a conta corporativa.  No Microsoft **Word**, **PowerPoint** e **Excel**, o usuário será solicitado a fornecer um PIN ao acessar os documentos armazenados no local do OneDrive for Business da empresa.

- Saiba mais sobre os aplicativos que oferecem suporte a [MAM e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

As políticas de proteção do aplicativo são aplicadas apenas em contextos corporativos. Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.

##  <a name="manage-user-accounts-on-the-device"></a>Gerenciar contas de usuário no dispositivo

O Intune só dá suporte à implantação de políticas de proteção do aplicativo a uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.
  * **Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.  

  * Nos **aplicativos OneDrive** e **Outlook**, é possível usar somente uma conta corporativa. Não é possível adicionar várias contas corporativas a esses aplicativos. É possível remover um usuário e adicionar um usuário diferente ao dispositivo.

* Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.


Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo, mas não a conta associada à Empresa Y. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X.

### <a name="add-a-second-account"></a>Adicionar uma segunda conta

Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio. As contas serão exibidas e você poderá escolher a conta que deseja remover.

## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Consulte também
[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

