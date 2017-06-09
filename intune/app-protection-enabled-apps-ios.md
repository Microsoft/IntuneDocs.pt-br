---
title: "Aplicativos iOS com políticas de proteção do aplicativo | Visualização do Intune Azure"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5e172b940dfae32213c870b29f05f56573192704
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo
[!INCLUDE[azure_preview](./includes/azure_preview.md)]Este tópico descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo. Políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho, como acessar aplicativos usando sua conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive na sua empresa.
##  <a name="accessing-apps"></a>Acessando aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário final será solicitado a reiniciar o aplicativo quando usar o aplicativo pela primeira vez.  Uma reinicialização é necessária para que as políticas de proteção de aplicativo possam ser aplicadas ao aplicativo. A captura de tela a seguir ilustra isso usando o aplicativo Skype:


![captura de tela do dispositivo iOS mostrando a solicitação do PIN](./media/ios-pin-prompt.png)

Para dispositivos que estão **registrados para gerenciamento no Intune**, o usuário final verá uma mensagem informando que seu aplicativo agora é gerenciado:

![captura de tela do dispositivo iOS mostrando a mensagem de que ele é gerenciado pela empresa com a solicitação do PIN](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Usando aplicativos com suporte a várias identidades

As políticas de proteção de aplicativo são aplicadas apenas no contexto de trabalho ao usar o aplicativo, de modo que você pode ver diferentes comportamentos de aplicativo dependendo do contexto: trabalho ou pessoal.  

Para aplicativos que dão suporte a várias identidades, o Intune aplica as políticas de proteção de aplicativo somente quando o usuário final estiver usando o aplicativo no contexto de trabalho.  Por exemplo, o usuário final receberá um prompt para fornecer o PIN ao acessar dados de trabalho.  Para o **aplicativo Outlook**, o usuário final será solicitado a fornecer um PIN ao iniciar o aplicativo. Para o **aplicativo OneDrive**, isso acontece quando o usuário final insere a conta de trabalho.  Para o Microsoft **Word**, **PowerPoint* e **Excel**, isso acontece quando o usuário final acessa os documentos armazenados no local do OneDrive for Business da empresa.
##  <a name="managing-user-accounts-on-the-device"></a>Gerenciando contas de usuário no dispositivo

O Intune dá suporte somente a políticas de proteção de aplicativo para apenas uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.
  * **Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.  

  * Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.  A adição de várias contas corporativas é bloqueada nesses aplicativos.  É possível remover um usuário e adicionar um usuário diferente ao dispositivo.

* Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.


Leia o cenário de exemplo abaixo para obter uma compreensão mais profunda de como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas - **empresa X**, e **empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção de aplicativo, mas a conta associada à Empresa Y não a obterá. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção de aplicativo, será necessário remover a conta de usuário associada à Empresa X.
### <a name="adding-a-second-account"></a>Adicionando uma segunda conta

Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio.  As contas serão exibidas e você pode escolher a conta que deseja remover.

![Captura de tela da caixa de diálogo com a mensagem de bloqueio e as opções Sim e Não](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Consulte também
[Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)

