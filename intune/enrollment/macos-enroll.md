---
title: Configurar o registro de dispositivos macOS
titleSuffix: Microsoft Intune
description: Saiba como configurar o registro de dispositivos macOS no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9cddb9b74d9132ace07c17a3156e61148b720d66
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207172"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Configurar o registro de dispositivos macOS no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune permite gerenciar dispositivos macOS para fornecer aos usuários acesso a email e aplicativos da empresa.

Como administrador do Intune, você pode configurar o registro para dispositivos macOS de propriedade da empresa e dispositivos macOS de propriedade pessoal ("traga seu próprio dispositivo" ou BYOD). 

## <a name="prerequisites"></a>Pré-requisitos

Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:

- [Verifique se o dispositivo está qualificado para o registro de dispositivo da Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Configurar domínios](../fundamentals/custom-domain-name-configure.md)
- [Definir a Autoridade MDM](../fundamentals/mdm-authority-set.md)
- [Criar grupos](../fundamentals/groups-add.md)
- [Configurar o Portal da Empresa](../apps/company-portal-app.md)
- Atribua licenças de usuário no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](../enrollment/apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Dispositivos macOS de propriedade do usuário (BYOD)

Você pode permitir que os usuários registrem seus próprios dispositivos pessoais no gerenciamento do Intune. Isso é conhecido como "Traga seu próprio dispositivo" ou BYOD. Depois de concluir os pré-requisitos e as licenças de usuários atribuídos, seus usuários poderão inscrever seus dispositivos:
- acessando o [site do Portal da Empresa](https://portal.manage.microsoft.com) ou
- baixando o aplicativo no Portal da Empresa do Mac em [aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac).

Você pode também enviar aos seus usuários um link para as etapas de registro online: [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](../fundamentals/end-user-educate.md)
- [Como usar seu dispositivo macOS com o Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Dispositivos macOS de propriedade da empresa
Para organizações que adquirem dispositivos para seus usuários, o Intune dá suporte aos seguintes métodos de registro de dispositivos macOS de propriedade da empresa:
- [DEP (Programa de registro de dispositivos) da Apple](device-enrollment-program-enroll-macos.md): As organizações podem comprar dispositivos macOS por meio do DEP (Programa de registro de dispositivos) da Apple. O DEP permite implantar um perfil de registro “over the air” para trazer dispositivos ao gerenciamento.
- [DEM (Gerenciador de registro de dispositivos)](device-enrollment-manager-enroll.md): Você pode usar uma conta do DEM para registrar até 1.000 dispositivos.

## <a name="block-macos-enrollment"></a>Bloquear registro do macOS
Por padrão, o Intune permite o registro de dispositivos macOS. Para bloquear o registro de dispositivos macOS, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

## <a name="enroll-virtual-macos-machines-for-testing"></a>Registrar máquinas macOS virtuais para teste

> [!NOTE]
> Só há suporte para máquinas virtuais macOS para teste. Você não deve usar máquinas virtuais macOS como dispositivos de produção para seus usuários finais. 

É possível registrar máquinas virtuais macOS para teste usando o Parallels Desktop ou o VMware Fusion. 

Para o Parallels Desktop, é necessário definir o tipo de hardware e o número de série para as máquinas virtuais para que o Intune possa reconhecê-las. Siga as instruções do Parallels para definir o tipo de hardware e o [número de série](http://kb.parallels.com/123455) para definir as configurações necessárias para teste. É recomendável que haja correspondência entre o tipo de hardware do dispositivo que executa as máquinas virtuais e o tipo de hardware das máquinas virtuais que você está criando. É possível encontrar esse tipo de hardware no **Menu da Apple** > **Sobre este Mac** > **Relatório do sistema** > **Identificador do modelo**. 

Para o VMware Fusion, é necessário [editar o arquivo .vmx](https://kb.vmware.com/s/article/1014782) para definir o número de série e modelo de hardware da máquina virtual. É recomendável que haja correspondência entre o tipo de hardware do dispositivo que executa as máquinas virtuais e o tipo de hardware das máquinas virtuais que você está criando. É possível encontrar esse tipo de hardware no **Menu da Apple** > **Sobre este Mac** > **Relatório do sistema** > **Identificador do modelo**. 

## <a name="user-approved-enrollment"></a>Registro aprovado pelo usuário
O registro de MDM Aprovado pelo Usuário é um tipo de registro macOS que você pode usar para gerenciar determinadas configurações sensíveis para a segurança. Para obter mais informações, consulte a [documentação de suporte da Apple](https://support.apple.com/HT208019).  
 
Durante o processo de registro BYOD, será solicitado que o usuário aprove manualmente o perfil de gerenciamento da Apple. As instruções são fornecidas no aplicativo Portal da Empresa para macOS. Embora a aprovação do perfil de gerenciamento não seja necessária para a conclusão do registro, o Intune recomenda o uso de registros aprovados pelo usuário. Se o usuário não aprovar o perfil durante o registro, poderá acessar **Preferências do Sistema** > **Perfis**, escolher o perfil de gerenciamento e escolher **Aprovar**.    

### <a name="find-out-if-a-device-is-user-approved"></a>Descubra se um dispositivo foi Aprovado pelo usuário
1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Escolha **Dispositivos** > **Todos os dispositivos**> escolha o dispositivo > **Hardware**.
3. Verifique o campo **Registro aprovado pelo usuário**.


## <a name="next-steps"></a>Próximas etapas

Depois que os dispositivos macOS forem registrados, você poderá [criar configurações personalizadas para dispositivos macOS](../configuration/custom-settings-macos.md).
