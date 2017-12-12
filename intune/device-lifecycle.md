---
title: "Visão geral do ciclo de vida do MDM"
description: "Saiba como o Intune ajuda a gerenciar dispositivos por meio de seu ciclo de vida – desde o registro, a configuração até a desativação eventual."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 33bcfd8c83c00a7d9d5625ec0fb87e442f728f2b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="overview-of-the-mobile-device-management-mdm-lifecycle"></a>Visão geral sobre o ciclo de vida de MDM (gerenciamento de dispositivos móveis)

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Todos os dispositivos gerenciados têm o que chamamos um *ciclo de vida*. O Intune pode ajudá-lo a gerenciar esse ciclo de vida – desde o registro, a configuração e proteção até a desativação do dispositivo quando ele não for mais necessário:

![O ciclo de vida do dispositivo](./media/device-lifecycle.png "o ciclo de vida do dispositivo do Intune")

## <a name="enroll"></a>Registrar
As estratégias atuais de MDM (gerenciamento de dispositivo móvel) lidam com uma variedades de telefones, tablets e computadores (iOS, Android, Windows e Mac OS X). Se você precisa conseguir gerenciar o dispositivo, o que geralmente é o caso para dispositivos de propriedade corporativa, a primeira etapa é [configurar o registro de dispositivo](device-enrollment.md) ([portal Clássico](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)). Você também pode gerenciar computadores Windows registrando-os no Intune (MDM) ou [instalando o software cliente do Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune).

## <a name="configure"></a>Configurar
Registrar seus dispositivos é apenas a primeira etapa. Para tirar proveito de tudo o que o Intune oferece e garantir que seus dispositivos estão seguros e são compatíveis com os padrões da empresa, você pode escolher entre uma ampla variedade de políticas. Elas permitem configurar quase todos os aspectos de funcionamento dos dispositivos gerenciados. Por exemplo, os usuários devem ter uma senha em dispositivos que têm dados da empresa? Você pode exigir uma. Você tem Wi-Fi corporativo? Você pode configurá-lo automaticamente. Estes são os tipos de opções de configuração disponíveis:

- [**Configuração de dispositivo**](device-profiles.md) ([portal Clássico](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)). Essas políticas permitem configurar os recursos e as funcionalidades dos dispositivos gerenciados. Por exemplo, você pode exigir o uso de uma senha em Windows Phones ou desabilitar o uso da câmera em iPhones.
- [**Acesso aos recursos da empresa**](device-profiles.md) ([portal Clássico](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune)). Quando você permite que os usuários acessem seu trabalho em dispositivos pessoais, isso pode apresentar desafios. Por exemplo, como garantir que todos os dispositivos que precisam acessar o email da empresa estejam configurados corretamente? Como garantir que os usuários podem acessar a rede da empresa com uma conexão VPN sem precisar saber configurações complexas? O Intune pode ajudar a reduzir essa carga, com a configuração automática dos dispositivos gerenciados para acessar os recursos comuns da empresa.
- [**Políticas de gerenciamento de computadores Windows (com o software cliente do Intune)**](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client). Embora o registro de computadores Windows no Intune proporcione a maioria das funcionalidades de gerenciamento de dispositivos, o Intune continua dando suporte ao gerenciamento de computadores Windows com o software cliente do Intune. Se você precisar obter informações sobre algumas das tarefas que podem ser executadas com computadores, comece aqui.

## <a name="protect"></a>Proteger
No moderno mundo de TI, proteger dispositivos contra o acesso não autorizado é uma das tarefas mais importantes que você realizará. Além dos itens descritos na etapa **Configurar** do ciclo de vida do dispositivo, o Intune fornece essas funcionalidades que ajudam a proteger dispositivos gerenciados contra o acesso não autorizado ou contra ataques mal-intencionados:
- [**Autenticação multifator**](/intune-classic/deploy-use/protect-your-devices-with-microsoft-intune). Adicionar uma camada extra de autenticação aos logons de usuário pode ajudar a tornar os dispositivos ainda mais seguros. Vários dispositivos dão suporte à autenticação multifator que exige um segundo nível de autenticação, como uma chamada telefônica ou mensagem de texto, antes que os usuários possam obter acesso.
- [**Configurações do Windows Hello para Empresas**](windows-hello.md) ([portal Clássico](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)). O Windows Hello para Empresas é um método de entrada alternativo que permite aos usuários usar um *gesto* – como uma impressão digital ou o Windows Hello – para fazer logon sem a necessidade de uma senha.
- [**Políticas para proteger computadores Windows (com o software cliente do Intune)**](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune). Quando você gerencia computadores Windows usando o software cliente do Intune, há políticas disponíveis que permitem controlar as configurações do Endpoint Protection, atualizações de software e Firewall do Windows em computadores gerenciados.

## <a name="retire"></a>Desativar
Quando um dispositivo é perdido ou roubado, quando ele precisa ser substituído ou quando os usuários mudam de cargo, geralmente, esse é o momento de [desativar ou apagar](device-management.md) ([portal Clássico](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)) o dispositivo. Há várias maneiras de fazer isso – incluindo a redefinição do dispositivo, sua remoção do gerenciamento ou apagamento dos dados corporativos do dispositivo.
