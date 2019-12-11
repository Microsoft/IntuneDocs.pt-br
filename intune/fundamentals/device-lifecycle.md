---
title: Visão geral do ciclo de vida de MDM do Microsoft Intune
description: Saiba como o Intune ajuda a gerenciar dispositivos durante o ciclo de vida – desde o registro à configuração, até a desativação eventual.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 46a23ca18e385fa085afb59a654290702465a0ce
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414044"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Visão geral sobre o ciclo de vida de MDM (gerenciamento de dispositivo móvel) do Microsoft Intune

Todos os dispositivos que você gerencia têm um *ciclo de vida*. O Intune pode ajudá-lo a gerenciar esse ciclo de vida: desde o registro, à configuração e proteção até a desativação do dispositivo quando ele não for mais necessário.

![O ciclo de vida do dispositivo](./media/device-lifecycle/device-lifecycle.png "p ciclo de vida do dispositivo Intune")

## <a name="enroll"></a>Registrar

As estratégias atuais de MDM (gerenciamento de dispositivo móvel) lidam com uma variedades de telefones, tablets e computadores (iOS, Android, Windows e Mac OS X). Se você precisa conseguir gerenciar o dispositivo, o que geralmente é o caso para dispositivos corporativos, a primeira etapa é [configurar o registro do dispositivo](../enrollment/device-enrollment.md). Você também pode gerenciar computadores Windows registrando-os no Intune (MDM) ou [instalando o software cliente do Intune](../manage-windows-pcs-with-microsoft-intune.md).

## <a name="configure"></a>Configurar

Registrar seus dispositivos é apenas a primeira etapa. Para tirar proveito de tudo o que o Intune oferece e garantir que seus dispositivos estão seguros e são compatíveis com os padrões da empresa, você pode escolher entre uma ampla variedade de políticas. Elas permitem configurar quase todos os aspectos de funcionamento dos dispositivos gerenciados. Por exemplo, os usuários devem ter uma senha em dispositivos que têm dados da empresa? Você pode exigir uma. Você tem Wi-Fi corporativo? Você pode configurá-lo automaticamente. Estes são os tipos de opções de configuração disponíveis:

- [**Configuração do dispositivo**](../configuration/device-profiles.md). Essas políticas permitem configurar os recursos e as funcionalidades dos dispositivos gerenciados. Por exemplo, você pode exigir o uso de uma senha em Windows Phones ou desabilitar o uso da câmera em iPhones.
- [**Acesso de recursos da empresa**](../configuration/device-profiles.md). Quando você permite que os usuários acessem seu trabalho em dispositivos pessoais, isso pode apresentar desafios. Por exemplo, como garantir que todos os dispositivos que precisam acessar o email da empresa estejam configurados corretamente? Como garantir que os usuários podem acessar a rede da empresa com uma conexão VPN sem precisar saber configurações complexas? O Intune pode ajudar a reduzir essa carga, com a configuração automática dos dispositivos gerenciados para acessar os recursos comuns da empresa.
- [**Políticas de gerenciamento de computadores Windows (com o software cliente do Intune)** ](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md). Embora o registro de computadores Windows no Intune proporcione a maioria das funcionalidades de gerenciamento de dispositivos, o Intune continua dando suporte ao gerenciamento de computadores Windows com o software cliente do Intune. Se você precisar obter informações sobre algumas das tarefas que podem ser executadas com computadores, comece aqui.

## <a name="protect"></a>Proteger

No moderno mundo de TI, proteger dispositivos contra o acesso não autorizado é uma das tarefas mais importantes que você realiza. Além dos itens descritos na etapa **Configurar** do ciclo de vida do dispositivo, o Intune fornece essas funcionalidades que ajudam a proteger dispositivos gerenciados contra o acesso não autorizado ou contra ataques mal-intencionados:

- [**Autenticação multifator**](../enrollment/multi-factor-authentication.md). Adicionar uma camada extra de autenticação aos logons de usuário pode ajudar a tornar os dispositivos ainda mais seguros. Vários dispositivos dão suporte à autenticação multifator que exige um segundo nível de autenticação, como uma chamada telefônica ou mensagem de texto, antes que os usuários possam obter acesso.
- [**Configurações do Windows Hello para Empresas**](../protect/windows-hello.md). O Windows Hello para Empresas é um método de entrada alternativo que permite aos usuários usar um *gesto* – como uma impressão digital ou o Windows Hello – para fazer logon sem a necessidade de uma senha.
- [**Políticas para proteger computadores Windows (com o software cliente do Intune)** ](../policies-to-protect-windows-pcs-in-microsoft-intune.md). Quando você gerencia computadores Windows usando o software cliente do Intune, há políticas disponíveis que permitem controlar as configurações do Endpoint Protection, atualizações de software e Firewall do Windows em computadores gerenciados.

## <a name="retire"></a>Desativar

Quando um dispositivo é perdido ou roubado, quando ele precisa ser substituído ou quando os usuários mudam de cargo, geralmente, esse é o momento de [desativar ou apagar](../remote-actions/device-management.md) o dispositivo. Há várias maneiras de fazer isso – incluindo a redefinição do dispositivo, sua remoção do gerenciamento ou apagamento dos dados corporativos do dispositivo.

## <a name="next-steps"></a>Próximas etapas

- Saiba mais sobre o [gerenciamento de dispositivos no Microsoft Intune](../remote-actions/device-management.md)
