---
title: "Dispositivos com suporte – Microsoft Intune"
description: Lista as plataformas de dispositivo e navegadores com suporte para o gerenciamento de dispositivo do Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/22/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4cfdf6a8aab1bda15015f85b1fb8f364e6a0edfa
ms.sourcegitcommit: 29ee35da2864b25f4432d2423b285014c77040af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2017
---
# <a name="supported-devices-and-browsers"></a>Dispositivos e navegadores com suporte

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Este artigo é voltado para os administradores de sistema responsáveis pelo gerenciamento de dispositivo na empresa. Para obter ajuda sobre como instalar o Intune em seu telefone, consulte [usando dispositivos gerenciados para realizar seu trabalho](/intune-user-help/company-portal-frequently-asked-questions).

Antes de iniciar a configuração do Microsoft Intune, examine os requisitos a seguir:

- [Dispositivos e computadores com suporte](#intune-supported-devices)
- [Lista de navegadores da Web com suporte para o Intune](#intune-supported-web-browsers)

Familiarize-se também com o [uso de largura de banda da rede do Intune](network-bandwidth-use.md) ([Portal Clássico](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Dispositivos com suporte do Intune

É possível gerenciar os seguintes dispositivos com o gerenciamento de dispositivo móvel do Intune:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

O Intune não pode ser usado para gerenciar sistemas operacionais Windows Server.

### <a name="windows-pc-software-client"></a>Cliente de software de computadores Windows

Um [cliente de software do Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) pode ser implantado e instalado em computadores Windows como um método alternativo de registro. Essa funcionalidade só está disponível no Portal Clássico do Intune. É possível usar o cliente de software do Intune para gerenciar computadores Windows 7 e posterior, com exceção do Windows 10 Home Edition.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Navegadores da web com suporte para o Intune

Diferentes tarefas administrativas exigem o uso de um dos seguintes sites administrativos.

- [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portal do Azure](https://portal.azure.com/)

Há suporte para os seguintes navegadores nesses portais:
- Microsoft Edge (última versão)
- Microsoft Internet Explorer 11
- Safari (última versão, somente Mac)
- Chrome (última versão)
- Firefox (última versão)

### <a name="intune-classic-portal"></a>Portal clássico do Intune

Os recursos somente clássicos do Intune, como o cliente de software de computador do Intune e a integração com parceiros de Defesa contra Ameaças Móveis, estão disponíveis somente no portal clássico do Intune (https://manage.microsoft.com). O portal clássico do Intune requer suporte do navegador Silverlight.

Os seguintes navegadores Silverlight dão suporte ao Portal Clássico do Intune:
- Internet Explorer 10 ou posterior
- Google Chrome (versões anteriores à versão 42)
- Mozilla Firefox com o Silverlight habilitado [Saiba mais](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Não há suporte para o Microsoft Edge nem para navegadores móveis no Portal Clássico do Intune, pois eles não dão suporte ao [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Apenas usuários com permissões de administrador de serviços ou administradores de locatários com a função de administrador global podem entrar nesse portal. Para acessar o console de administração, sua conta deve ter uma licença para usar o Intune e um status de entrada de **Permitido**.
