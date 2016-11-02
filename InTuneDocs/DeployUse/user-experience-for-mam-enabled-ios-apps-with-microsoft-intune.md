---
title: "Aplicativos iOS com políticas de MAM | Microsoft Intune"
description: "Este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# O que esperar quando seu aplicativo iOS é gerenciado por políticas de MAM
 Este tópico descreve a experiência do usuário para aplicativos com políticas de MAM. Políticas de MAM (gerenciamento de aplicativo móvel) são aplicadas somente quando os aplicativos são usados no contexto de trabalho, como acessar aplicativos usando sua conta do trabalho ou acessar arquivos armazenados no local de negócios do OneDrive de sua empresa.
##  Acessando aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário final será solicitado a reiniciar o aplicativo quando usar o aplicativo pela primeira vez.  Uma reinicialização é necessária para que políticas de MAM possam ser aplicadas ao aplicativo. A captura de tela a seguir ilustra isso usando o aplicativo Skype:


![captura de tela do dispositivo iOS mostrando a solicitação do PIN](../media/appmanagement/iOS_AppPINPrompt.png)

Para dispositivos que estão **registrados para gerenciamento no Intune**, o usuário final verá uma mensagem informando que seu aplicativo agora é gerenciado:

![captura de tela do dispositivo iOS mostrando a mensagem de que ele é gerenciado pela empresa com a solicitação do PIN](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Usando aplicativos com suporte a várias identidades

As políticas de MAM são aplicadas apenas no contexto de trabalho ao usar o aplicativo, de modo que você pode ver diferentes comportamentos de aplicativo dependendo do contexto: trabalho ou pessoal.  

Para aplicativos que dão suporte a várias identidades, o Intune aplica as políticas de MAM somente quando o usuário final estiver usando o aplicativo no contexto de trabalho.  Por exemplo, o usuário final receberá um prompt para fornecer o PIN ao acessar dados de trabalho.  Para o **aplicativo Outlook**, o usuário final será solicitado a fornecer um PIN ao iniciar o aplicativo. Para o **aplicativo OneDrive**, isso acontece quando o usuário final insere a conta de trabalho.  Para o Microsoft **Word**, **PowerPoint* e **Excel**, isso acontece quando o usuário final acessa os documentos armazenados no local do OneDrive for Business da empresa.
##  Gerenciando contas de usuário no dispositivo

O Intune só dá suporte a políticas de MAM a apenas uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtém as políticas de MAM é afetado pela política.
  * **Microsoft Word**, **Excel**, e **PowerPoint** não bloqueiam uma segunda conta de usuário, mas a segunda conta de usuário não é afetada pelas políticas de MAM.  

  * Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.  A adição de várias contas corporativas é bloqueada nesses aplicativos.  É possível remover um usuário e adicionar um usuário diferente ao dispositivo.

* Se um dispositivo existente tiver várias contas de usuário antes que as políticas de MAM sejam implantadas, a conta em que as políticas de MAM forem implantadas primeiro será gerenciada pelas políticas de MAM do Intune.


Leia o cenário de exemplo abaixo para obter uma compreensão mais profunda de como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas - **empresa X**, e **empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de MAM. A **Empresa X** implanta políticas MAM **antes da** **empresa Y**. A conta associada à **empresa X** obterá a política de MAM, mas não a conta associada à empresa Y. Se você quiser que a conta de usuário associada à empresa Y seja gerenciada pelas políticas de MAM, deverá remover a conta de usuário associada a empresa X.
### Adicionando uma segunda conta

Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio.  As contas serão exibidas e você pode escolher a conta que deseja remover.

![Captura de tela da caixa de diálogo com a mensagem de bloqueio e as opções Sim e Não](../media/AppManagement/iOS_SwitchUser.PNG)
## Próximas etapas
[O que esperar quando seu aplicativo Android é gerenciado por políticas de MAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Consulte também
[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


