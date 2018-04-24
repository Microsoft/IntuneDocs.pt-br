---
title: Aplicativos iOS com políticas de proteção de aplicativo
titlesuffix: Microsoft Intune
description: Saiba o que esperar de um aplicativo iOS que tenha políticas de proteção.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2804003a0f1acac56ecaae5e24dcf34b4eb0c256
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Saiba mais sobre a experiência do usuário para aplicativos iOS com políticas de proteção de aplicativo. As políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho. Por exemplo, quando você acessa um aplicativo com uma conta corporativa ou quando você acessa arquivos armazenados no OneDrive da sua empresa.
##  <a name="accessing-apps"></a>Acessando aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário será solicitado a reiniciar o aplicativo ao usá-lo pela primeira vez.  Uma reinicialização é necessária para que as políticas de proteção de aplicativo possam ser aplicadas ao aplicativo. A captura de tela a seguir ilustra isso usando o aplicativo Skype:


![captura de tela do dispositivo iOS mostrando a solicitação do PIN](./media/ios-pin-prompt.png)

Para dispositivos que estão **registrados para gerenciamento no Intune**, o usuário verá uma mensagem informando que seu aplicativo agora é gerenciado:

![captura de tela do dispositivo iOS mostrando a mensagem de que ele é gerenciado pela empresa com a solicitação do PIN](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Usando aplicativos com suporte a várias identidades

As políticas de proteção de aplicativo somente entram em vigor quando um usuário tenta acessar dados relacionados ao trabalho.  Você verá comportamentos diferentes caso o usuário acesse o aplicativo para uso pessoal. 

Para aplicativos compatíveis com várias identidades, o Intune aplica as políticas de proteção de aplicativo somente se o usuário acessa dados de trabalho.  Por exemplo, um usuário pode receber uma solicitação de PIN.  No **aplicativo Outlook**, a solicitação ocorre quando o usuário inicia o aplicativo. No **aplicativo OneDrive**, a solicitação ocorre quando o usuário insere a conta corporativa.  No Microsoft **Word**, **PowerPoint** e **Excel**, a solicitação ocorre quando um usuário acessa documentos no OneDrive da empresa.
##  <a name="managing-user-accounts-on-the-device"></a>Gerenciando contas de usuário no dispositivo

O Intune dá suporte somente a políticas de proteção de aplicativo para apenas uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.
  * O **Microsoft Word**, **Excel** e **PowerPoint** não bloquearão o acesso a uma conta de usuário adicional. No entanto, a conta de usuário não será afetada pelas políticas de proteção de aplicativo.

  * Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.  A adição de várias contas corporativas é bloqueada nesses aplicativos.  No entanto, você pode remover um usuário de um dispositivo e, em seguida, adicionar um usuário diferente ao dispositivo.

* Um dispositivo pode ter várias contas de usuário existente antes que as políticas de proteção de aplicativo sejam implantadas. Nesse caso, a primeira conta na qual as políticas de proteção de aplicativo são implantadas será gerenciada por essas políticas de proteção de aplicativo do Intune.


Leia o cenário de exemplo a seguir para saber como o Intune lida com várias contas de usuário.

O usuário A trabalha para duas empresas: **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção de aplicativo, mas a conta associada à Empresa Y não. Para fazer com que a conta de usuário da Empresa Y seja gerenciada pelas políticas de proteção de aplicativo, o Usuário A deve remover a conta de usuário da Empresa X.
### <a name="adding-a-second-account"></a>Adicionando uma segunda conta

Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio.  As contas serão exibidas e você pode escolher a conta que deseja remover.

![Captura de tela da caixa de diálogo com a mensagem de bloqueio e as opções Sim e Não](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Consulte também
[Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)
