---
title: Configurar o registro de dispositivos macOS
titlesuffix: Microsoft Intune
description: Saiba como configurar o registro de dispositivos macOS no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f8cddb69ac85e45acde8a846df3b5413c3b75bf
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Configurar o registro de dispositivos macOS no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune permite que você gerencie dispositivos macOS. Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos acessando o [site do Portal da Empresa](http://portal.manage.microsoft.com) e seguir as instruções. Quando os dispositivos macOS estiverem sob gerenciamento, você pode [criar configurações personalizadas para dispositivos macOS](custom-settings-macos.md). Mais recursos serão disponibilizados em breve.

## <a name="prerequisites"></a>Pré-requisitos

Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:

- [Configurar domínios](custom-domain-name-configure.md)
- [Definir a Autoridade MDM](mdm-authority-set.md)
- [Criar grupos](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](company-portal-app.md)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](apple-mdm-push-certificate-get.md)

## <a name="user-owned-ios-devices-byod"></a>BYOD (Dispositivos iOS de propriedade do usuário)

É possível permitir que os usuários registrem seus dispositivos pessoais para o gerenciamento do Intune, conhecidos como "traga seu próprio dispositivo" ou BYOD. Depois de concluir os pré-requisitos e atribuir licenças de usuários, eles poderão baixar o aplicativo Portal da Empresa do macOS na App Store e seguir as instruções de registro no aplicativo.

## <a name="company-owned-ios-devices"></a>Dispositivos iOS de propriedade da empresa
Para organizações que compram dispositivos para os usuários, o Intune é compatível com o registro de dispositivos macOS da empresa com uma conta do [gerenciador de registros de dispositivo](device-enrollment-manager-enroll.md).

## <a name="set-up-macos-enrollment"></a>Configurar registro do macOS

Por padrão, o Intune já está configurado para permitir o registro de dispositivos macOS.

Para bloquear o registro de dispositivos macOS, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Peça aos usuários finais que acessem o [site do Portal da Empresa](https://portal.manage.microsoft.com) e sigam os prompts para registrar seus dispositivos. Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md)
- [Como usar seu dispositivo macOS com o Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="enroll-virtual-macos-machines-for-testing"></a>Registrar máquinas macOS virtuais para teste

> [!NOTE]
> Só há suporte para máquinas virtuais macOS para teste. Você não deve usar máquinas virtuais macOS como dispositivos de produção para seus usuários finais. 

É possível registrar máquinas virtuais macOS para teste usando o Parallels Desktop ou o VMware Fusion. 

Para o Parallels Desktop, é necessário definir o tipo de hardware e o número de série para as máquinas virtuais para que o Intune possa reconhecê-las. Siga as instruções do Parallels para [definir o tipo de hardware](http://kb.parallels.com/123594) e o [número de série](http://kb.parallels.com/123455) para definir as configurações necessárias para teste. É recomendável que haja correspondência entre o tipo de hardware do dispositivo que executa as máquinas virtuais e o tipo de hardware das máquinas virtuais que você está criando. É possível encontrar esse tipo de hardware no **Menu da Apple** > **Sobre este Mac** > **Relatório do sistema** > **Identificador do modelo**. 

Para o VMware Fusion, é necessário [editar o arquivo .vmx](https://kb.vmware.com/s/article/1014782) para definir o número de série e modelo de hardware da máquina virtual. É recomendável que haja correspondência entre o tipo de hardware do dispositivo que executa as máquinas virtuais e o tipo de hardware das máquinas virtuais que você está criando. É possível encontrar esse tipo de hardware no **Menu da Apple** > **Sobre este Mac** > **Relatório do sistema** > **Identificador do modelo**. 

## <a name="user-approved-enrollment"></a>Registro aprovado pelo usuário

O registro de MDM Aprovado pelo Usuário é um tipo de registro macOS que você pode usar para gerenciar determinadas configurações sensíveis para a segurança. Para obter mais informações, consulte a [documentação de suporte da Apple](https://support.apple.com/HT208019).

Para ser aprovado pelo usuário, o usuário final deve, após registrar-se usando o Portal da Empresa macOS, fornecer manualmente sua aprovação usando as Preferências do Sistema. O Portal da empresa macOS fornece instruções para fazer isso para usuários que usam o macOS 10.13.2 e posteriores.

Para descobrir se um dispositivo foi Aprovado pelo Usuário, acesse o portal do Intune e escolha **Dispositivos** > **Todos os Dispositivos**> escolher o dispositivo > **Hardware**. Verifique o campo **Aprovados pelo Usuário**.