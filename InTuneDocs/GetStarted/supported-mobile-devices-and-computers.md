---
title: "Dispositivos móveis e navegadores com suporte | Microsoft Intune"
description: "Dispositivos móveis e computadores com suporte do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Dispositivos móveis e computadores com suporte

Você pode registrar e gerenciar os seguintes tipos de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Registrar dispositivos fornece [esses recursos](/Intune/get-started/choose-how-to-manage-devices).

Como alternativa, você pode gerenciar computadores Windows com o software cliente Intune PC. O software cliente de computadores Intune dá suporte ao Windows 7 e posterior, exceto ao Windows 10 Home. O Gerenciamento de PCs com o software cliente fornece [esses recursos](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Os clientes com o Enterprise Management Suite podem também usar o Azure AD (Azure Active Directory) para registrar dispositivos Windows 10.

## <a name="microsoft-intune-supported-web-browsers"></a>Navegadores da web com suporte do Microsoft Intune

Diferentes tarefas administrativas exigem que você use um dos seguintes sites administrativos.

- [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Console do administrador do Microsoft Intune](https://admin.manage.microsoft.com/)

> [!Note]
> O Microsoft Edge e os navegadores móveis não têm suporte para o console de administração porque não dão suporte ao [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). O console do Intune está deixando a experiência do Silverlight ao longo de um período. Eventualmente, todos os recursos de gerenciamento de aplicativos e dispositivos móveis do Intune serão [disponibilizados no novo portal do Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Recurso do Intune |Navegadores com suporte|
|---------|---------|
|Console de administração do Intune     |  Internet Explorer 10 ou posterior<br /><br />Google Chrome (versões anteriores à versão 42)<br /><br />Mozilla Firefox com o Silverlight habilitado<br /><br />**Observação:** o Microsoft Edge e navegadores móveis não têm suporte para o console de administração.                      
|Portal de administração do Office 365     |Todos os navegadores, incluindo navegadores móveis e navegadores gerenciados  |
|Site do Portal da Empresa     |**Em dispositivos móveis:** usar o navegador da Web padrão para cada plataforma com suporte   <br /><br />**Em computadores Windows:** Internet Explorer 10 ou posterior ou Microsoft Edge<br /><br />**No Mac OS X 10.9 ou posterior:** Safari da Apple    |

> [!Note]
> O Microsoft Edge e os navegadores móveis não têm suporte para o console de administração porque não dão suporte ao [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). O console do Intune está deixando a experiência do Silverlight ao longo de um período. Eventualmente, todos os recursos de gerenciamento de aplicativos e dispositivos móveis do Intune serão [disponibilizados no novo portal do Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Como administrador de locatários, use este portal para gerenciar a sua assinatura**, incluindo as tarefas a seguir, quando permitido pela sua função de administrador:

- Gerenciar contas de usuário da assinatura e configurar a sincronização de diretório do seu Active Directory local.
- Gerenciar grupos de usuários, chamados grupos de segurança.
- Atribuir licenças aos usuários para usar o Intune.
- Configurar o nome de domínio que você usa com sua assinatura. O nome de domínio define a conta com a qual os usuários entram.
- Gerenciar detalhes de cobrança e compra da sua assinatura, incluindo o número de licenças que possui ou a quantidade de espaço de armazenamento na nuvem que você pode usar.
- Encontrar links para exibir a integridade do serviço do Intune.
- Como administrador de locatários, você pode entrar no portal do Office 365 para gerenciar a assinatura, mesmo que sua conta não tenha recebido a atribuição de uma licença para usar o Intune.
- Qualquer usuário que tenha uma licença para o Intune, mas que não seja um administrador, pode usar este portal para redefinir sua senha da conta e editar seu perfil.
- Para acessar o portal do Office 365, sua conta deve ter um status de entrada de **Permitido**. Esse status é diferente de ter uma licença para a assinatura. Por padrão, todas as contas de usuário são **Permitidas**.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Console do administrador do Microsoft Intune](https://manage.microsoft.com/)

**Como administrador de serviços, use este portal para gerenciar as tarefas do dia a dia**, incluindo:

- Definir políticas para computadores e dispositivos móveis.
- Carregar e implantar software, como atualizações de software e aplicativos.
- Gerenciar a Endpoint Protection em computadores.
- Exibir status do dispositivo e executar relatórios.
- Entrar neste portal. Você deve ter permissões de administrador de serviços ou ser um administrador de locatários com a função de administrador global para entrar neste portal.


Apenas usuários com permissões de administrador de serviços ou administradores de locatários com a função de administrador global podem entrar nesse portal. Para acessar o console de administração, sua conta deve ter uma licença para usar o Intune e um status de entrada de **Permitido**.



<!--HONumber=Nov16_HO4-->


