---
title: "Aplicativos iOS com políticas de MAM | Microsoft Docs"
description: "Este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de gerenciamento de aplicativo móvel."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: f5a26d3d5ed060571892d91637dc12cae08f1a69


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>O que esperar quando seu aplicativo iOS é gerenciado por políticas de MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 Este tópico descreve a experiência do usuário em aplicativos com políticas de MAM. Políticas de MAM (gerenciamento de aplicativo móvel) são aplicadas somente quando os aplicativos são usados em um contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive de uma empresa.

##  <a name="access-apps"></a>Acessar aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário será solicitado a reiniciar o aplicativo ao usá-lo pela primeira vez.  Uma reinicialização é necessária para que as políticas de MAM possam ser aplicadas ao aplicativo. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Em dispositivos **registrados para gerenciamento no Intune**, o usuário verá uma mensagem informando que seu aplicativo agora é gerenciado:

![Captura de tela do dispositivo iOS mostrando a mensagem de que o aplicativo agora é gerenciado pela empresa, com a solicitação do PIN](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>Usar aplicativos com suporte a várias identidades

As políticas de MAM são aplicadas apenas em contextos corporativos. Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.

 Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho. No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo. No **aplicativo OneDrive**, o usuário será solicitado a fornecer um PIN ao digitar a conta corporativa.  No Microsoft **Word**, **PowerPoint** e **Excel**, o usuário será solicitado a fornecer um PIN ao acessar os documentos armazenados no local do OneDrive for Business da empresa.

##  <a name="manage-user-accounts-on-the-device"></a>Gerenciar contas de usuário no dispositivo

O Intune só dá suporte à implantação de políticas de MAM a uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtém as políticas de MAM é afetado pela política.
  * **Microsoft Word**, **Excel**, e **PowerPoint** não bloqueiam uma segunda conta de usuário, mas a segunda conta de usuário não é afetada pelas políticas de MAM.  

  * Nos **aplicativos OneDrive** e **Outlook**, é possível usar somente uma conta corporativa. Não é possível adicionar várias contas corporativas a esses aplicativos. É possível remover um usuário e adicionar um usuário diferente ao dispositivo.

* Se um dispositivo tiver várias contas de usuário existentes antes da implantação das políticas de MAM, a conta em que as políticas de MAM forem implantadas primeiro será gerenciada pelas políticas de MAM do Intune.


Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de MAM. A **Empresa X** implanta políticas MAM **antes da** **empresa Y**. A conta associada à **Empresa X** obterá a política de MAM, mas não a conta associada à Empresa Y. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de MAM, será necessário remover a conta de usuário associada à Empresa X.

### <a name="add-a-second-account"></a>Adicionar uma segunda conta

Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio. As contas serão exibidas e você poderá escolher a conta que deseja remover.

![Captura de tela da caixa de diálogo com a mensagem de bloqueio e as opções Sim e Não](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo Android é gerenciado por políticas de MAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Consulte também
[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


