---
title: "Dispositivos com suporte – Microsoft Intune | Microsoft Docs"
description: Lista as plataformas de dispositivo e navegadores com suporte para o gerenciamento de dispositivo do Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b3732d0c6461f9fb8462ae5584055204d597aae0
ms.openlocfilehash: 0af4f49713a65900079d69a09f20d210797c935c


---

# <a name="supported-devices-and-browsers"></a>Dispositivos e navegadores com suporte

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este artigo é voltado para os administradores de sistema responsáveis pelo gerenciamento de dispositivo na empresa. Para obter ajuda sobre como instalar o Intune em seu telefone, consulte [usando dispositivos gerenciados para realizar seu trabalho](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

Antes de iniciar a configuração do Microsoft Intune, examine os requisitos a seguir:

- [Dispositivos e computadores com suporte](#intune-supported-devices)
- [Lista de navegadores da Web com suporte para o Intune](#intune-supported-web-browsers)

Você também deve se familiarizar com o [uso de largura de banda da rede do Intune](network-bandwidth-use.md).

## <a name="intune-supported-devices"></a>Dispositivos com suporte do Intune

É possível gerenciar os seguintes dispositivos com o gerenciamento de dispositivo móvel do Intune:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

O Intune não pode ser usado para gerenciar sistemas operacionais Windows Server.

O gerenciamento de dispositivo do Intune fornece [estes recursos](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Cliente de software de computadores Windows

Um [cliente de software do Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) pode ser implantado e instalado em computadores Windows como um método alternativo de registro. É possível usar o cliente de software do Intune para gerenciar computadores Windows 7 e posterior, com exceção do Windows 10 Home Edition. O Gerenciamento de PCs com o software cliente fornece [esses recursos](windows-pc-management-capabilities-in-microsoft-intune.md).

### <a name="exchange-activesync-management"></a>Gerenciamento do Exchange ActiveSync

É possível gerenciar [dispositivos Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) no console do Intune. Essa opção fornece um conjunto limitado de recursos de gerenciamento quando comparada aos outros métodos. Consulte [Recursos de Gerenciamento de Dispositivo Móvel Interno no Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) para obter uma lista de dispositivos com suporte.

## <a name="intune-supported-web-browsers"></a>Navegadores da web com suporte para o Intune

Diferentes tarefas administrativas exigem o uso de um dos seguintes sites administrativos.

- [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Console do administrador do Microsoft Intune](https://admin.manage.microsoft.com/)

|Recurso do Intune |Navegadores com suporte|
|---------|---------|
|**Console de Administração do Intune**     |  Internet Explorer 10 ou posterior<br /><br />Google Chrome (versões anteriores à versão 42)<br /><br />Mozilla Firefox com o Silverlight habilitado<br />**Observação:** o Mozilla removerá o suporte para o Silverlight a partir de março de 2017. [Saiba mais](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Portal de Administração do Office 365**     |Todos os navegadores, incluindo navegadores móveis e navegadores gerenciados  |
|**Site do Portal da Empresa**     |**Em dispositivos móveis:** usar o navegador da Web padrão para cada plataforma com suporte   <br /><br />**Em computadores Windows:** Internet Explorer 10 ou posterior ou Microsoft Edge<br /><br />**No Mac OS X 10.9 ou posterior:** Safari da Apple    |

> [!Note]
> O Microsoft Edge e os navegadores móveis não têm suporte para o console de administração porque não dão suporte ao [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). O console do Intune está deixando a experiência do Silverlight ao longo de um período. Eventualmente, todos os recursos de gerenciamento de aplicativos e dispositivos móveis do Intune serão [disponibilizados no novo portal do Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Apenas usuários com permissões de administrador de serviços ou administradores de locatários com a função de administrador global podem entrar nesse portal. Para acessar o console de administração, sua conta deve ter uma licença para usar o Intune e um status de entrada de **Permitido**.

>[!div class="step-by-step"]

>[**Rede** &rarr;](network-bandwidth-use.md)  



<!--HONumber=Feb17_HO2-->


