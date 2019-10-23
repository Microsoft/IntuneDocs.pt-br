---
title: Registrar dispositivos iOS no Intune
titleSuffix: Microsoft Intune
description: Configurar o registro de dispositivos iOS no Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2fb5208cd7df6dc68bcd20455ae9e06a9dbd7ff5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503153"
---
# <a name="enroll-ios-devices-in-intune"></a>Registrar dispositivos iOS no Intune

O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads e de iPhones para permitir que os usuários tenham um acesso seguro ao email, aos dados e aplicativos da empresa.

Como administrador do Intune, você pode configurar o registro de dispositivos iOS e iPadOS para acessarem recursos da empresa. Você pode permitir aos usuários registrar dispositivos pessoais, conhecido como registro BYOD (traga seu próprio dispositivo). Você também pode configurar o registro de dispositivos de propriedade da empresa.

## <a name="prerequisites-for-ios-enrollment"></a>Pré-requisitos para registro de iOS

Antes de habilitar dispositivos iOS, conclua as seguintes etapas:

- [Verifique se o dispositivo está qualificado para o registro de dispositivo da Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Configure o Intune](../fundamentals/setup-steps.md) – essas etapas configuram sua infraestrutura do Intune. Em especial, o registro de dispositivo exige que você [defina a autoridade MDM](../fundamentals/mdm-authority-set.md).
- [Obtenha um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) –A Apple exige um certificado para habilitar o gerenciamento de dispositivos iOS e macOS.

## <a name="user-owned-ios-and-ipados-devices-byod"></a>Dispositivos iOS e iPadOS de propriedade do usuário (BYOD)

É possível permitir que os usuários registrem seus dispositivos pessoais para o gerenciamento do Intune, conhecidos como "traga seu próprio dispositivo" ou BYOD. Há três opções para registrar usuários:
- As Políticas de proteção de aplicativo oferecem uma experiência de BYOD mais leve, fornecendo gerenciamento somente no nível do aplicativo. No entanto, se você também quiser proteger o dispositivo com um PIN complexo de seis dígitos, poderá usar essas políticas junto com o Registro do usuário.
- O registro de dispositivo pode ser considerado um registro BYOD típico. Ele fornece aos administradores uma grande variedade de opções de gerenciamento.
- O Registro de usuário é um processo de registro mais simplificado que fornece aos administradores um subconjunto de opções de gerenciamento de dispositivo. Esse recurso atualmente está em versão prévia. 

Após você concluir os pré-requisitos e atribuir licenças de usuários, os usuários poderão baixar o aplicativo Portal da Empresa do Intune na App Store e seguir as instruções de registro no aplicativo. É possível personalizar a declaração de privacidade do Portal da Empresa em dispositivos iOS, como explicado em [personalização da declaração de privacidade](../apps/company-portal-app.md#privacy-statement-customization).

## <a name="company-owned-ios-devices"></a>Dispositivos iOS de propriedade da empresa

Para organizações que adquirem dispositivos para os usuários, o Intune dá suporte aos seguintes métodos de registro de dispositivos iOS de propriedade da empresa:

- DEP (Programa de registro de dispositivos) da Apple
- Apple School Manager
- Registro do Assistente de Configuração do Apple Configurator
- Registro direto do Apple Configurator

Também é possível registrar dispositivos iOS de propriedade da empresa com uma conta do [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="device-enrollment-program"></a>Programa de Registro do Dispositivo

As organizações podem comprar dispositivos iOS por meio do DEP (Programa de registro de dispositivos) da Apple. O DEP permite implantar um perfil de registro “over the air” para trazer dispositivos ao gerenciamento. Para obter mais informações, confira [Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).

## <a name="user-enrollment"></a>Registro de usuários
O Registro de usuário fornece aos administradores um subconjunto de opções de gerenciamento em comparação com os outros métodos de registro. Para obter mais informações, confira [Ações compatíveis com Registro de usuário, senhas e outras opções](ios-user-enrollment-supported-actions.md) e [Configurar registro de usuário do iOS e iPadOS](ios-user-enrollment.md).

## <a name="apple-school-manager"></a>Apple School Manager

O Apple School Manager é um programa de compra e de registro de dispositivo para escolas. Como o DEP, você pode implantar um perfil para registrar dispositivos no gerenciamento. Saiba mais sobre o [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator

Você pode registrar dispositivos iOS com o Apple Configurator em execução em um computador Mac. Para preparar os dispositivos, conecte-os via USB e instale um perfil de registro. Você pode registrar dispositivos com o Apple Configurator de duas maneiras:

- Registro do Assistente de Configuração – apaga o dispositivo, prepara-o para executar o Assistente de Configuração e instala as políticas da empresa para o novo usuário do dispositivo.
- Registro direto – não apaga o dispositivo e registra-o com uma política predefinida. Esse método é destinado a dispositivos sem afinidade de usuário.

Saiba mais sobre o [registro do Apple Configurator](apple-configurator-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Usar o Portal da Empresa em dispositivos registrados por DEP ou no Apple Configurator

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão concluir várias etapas adicionais a fim de completar o Assistente de Configuração e instalar o aplicativo Portal da Empresa.

Afinidade de usuário é necessária para dar suporte ao seguinte:

- Aplicativos MAM (Gerenciamento de aplicativos móveis)
- Acesso Condicional para dados de email e da empresa
- Aplicativo do Portal da Empresa

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Como os usuários registram dispositivos iOS corporativos com afinidade de usuário

1. Quando os usuários ligam seus dispositivos, eles recebem uma solicitação para concluir o Assistente de Configuração.
2. Após a configuração, os usuários recebem uma solicitação para inserir uma ID da Apple. Eles precisam fornecer uma ID da Apple para permitir que o dispositivo instale o Portal da Empresa.
3. O dispositivo iOS instala automaticamente o aplicativo Portal da Empresa da App Store.
4. Os usuários devem iniciar o aplicativo Portal da Empresa e entrar usando as credenciais (como o nome pessoal exclusivo ou UPN) associadas à respectiva assinatura do Intune.
5. Depois de fazer logon, o registro está concluído. Agora os usuários podem usar este dispositivo com o conjunto completo de recursos.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Sobre dispositivos gerenciados de propriedade da empresa sem afinidade de usuário

Os dispositivos configurados sem a afinidade de usuário não têm suporte no Portal da Empresa e não devem instalar o aplicativo. O Portal da Empresa se destina a usuários com credenciais corporativas e que precisam de acesso aos recursos corporativos personalizados (como email). Os dispositivos registrados sem afinidade de usuário não devem ter uma entrada de usuário dedicada. O quiosque, o ponto de venda (PDV) ou os dispositivos de utilitário compartilhados são casos de uso comuns de dispositivos registrados sem afinidade de usuário.

Se a afinidade de usuário for necessária, certifique-se de que o perfil de registro do dispositivo tenha a opção **Afinidade de Usuário** selecionada antes de registrar o dispositivo. Para alterar o status de afinidade em um dispositivo, você deve desativar e registrar novamente o dispositivo.

## <a name="see-also"></a>Consulte também

[Solucionando problemas de registro de dispositivo iOS no Microsoft Intune](https://support.microsoft.com/help/4039809)
