---
title: Escolha como registrar dispositivos iOS no Intune
titlesuffix: Microsoft Intune
description: Configurar o registro de dispositivos iOS no Microsoft Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e79122c1bea970525faaf443f9bf4271d050abe2
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="enroll-ios-devices-in-intune"></a>Registrar dispositivos iOS no Intune

O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads e de iPhones para permitir acesso ao email e aos aplicativos da empresa aos usuários.

Como administrador do Intune, você pode habilitar o registro para dispositivos iOS. Você pode permitir que os usuários registrem seus dispositivos pessoais, conhecido como o registro BYOD (traga seu próprio dispositivo). Você também pode habilitar o registro de dispositivos de propriedade da empresa.

## <a name="prerequisites-for-ios-enrollment"></a>Pré-requisitos para registro de iOS
Antes de habilitar dispositivos iOS, conclua as seguintes etapas:
- [Configure o Intune](setup-steps.md) – essas etapas configuram sua infraestrutura do Intune. Em especial, o registro de dispositivo exige que você [defina a autoridade MDM](mdm-authority-set.md).
- [Obtenha um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) –A Apple exige um certificado para habilitar o gerenciamento de dispositivos iOS e macOS.

## <a name="user-owned-ios-devices-byod"></a>BYOD (Dispositivos iOS de propriedade do usuário)

É possível permitir que os usuários registrem seus dispositivos pessoais para o gerenciamento do Intune, conhecidos como "traga seu próprio dispositivo" ou BYOD. Depois de concluir os pré-requisitos e atribuir licenças de usuários, eles poderão baixar o aplicativo Portal da Empresa do Intune na App Store e seguir as instruções de registro no aplicativo.

## <a name="company-owned-ios-devices"></a>Dispositivos iOS de propriedade da empresa
Para organizações que adquirem dispositivos para seus usuários, o Intune dá suporte aos seguintes métodos de registro de dispositivos iOS de propriedade da empresa:

- DEP (Programa de registro de dispositivos) da Apple
- Apple School Manager
- Registro do Assistente de Configuração do Apple Configurator
- Registro direto do Apple Configurator

Também é possível registrar dispositivos iOS de propriedade da empresa com uma conta do [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="device-enrollment-program"></a>Programa de Registro do Dispositivo
As organizações podem comprar dispositivos iOS por meio do DEP (Programa de registro de dispositivos) da Apple. O DEP permite implantar um perfil de registro “over the air” para trazer dispositivos ao gerenciamento. Saiba mais sobre o [Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
O Apple School Manager é um programa de compra e de registro de dispositivo para escolas. Como o DEP, você pode implantar um perfil para registrar dispositivos no gerenciamento. Saiba mais sobre o [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Você pode registrar dispositivos iOS com o Apple Configurator em execução em um computador Mac. Para preparar os dispositivos, conecte-os via USB e instale um perfil de registro. Você pode registrar dispositivos com o Apple Configurator de duas maneiras:
- Registro do Assistente de Configuração – restaura o dispositivo para as configurações de fábrica, prepara-o para executar o Assistente de Configuração e instala as políticas da empresa para o novo usuário do dispositivo.
- Registro direto – não redefine o dispositivo para as configurações de fábrica e registra o dispositivo com uma política predefinida. Esse método é destinado a dispositivos sem afinidade de usuário.

Saiba mais sobre o [registro do Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Usar o Portal da Empresa em dispositivos registrados por DEP ou no Apple Configurator

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão concluir várias etapas adicionais a fim de completar o Assistente de Configuração e instalar o aplicativo Portal da Empresa.

Afinidade de usuário é necessária para dar suporte ao seguinte:
  - Aplicativos MAM (Gerenciamento de aplicativos móveis)
  - Acesso condicional para dados de email e da empresa
  - Aplicativo do Portal da Empresa

**Como os usuários registram dispositivos iOS corporativos com afinidade do usuário**
1. Quando os usuários ligam seus dispositivos, eles recebem uma solicitação para concluir o Assistente de Configuração. Durante a configuração, os usuários receberão uma solicitação por suas credenciais. Eles devem usar as credenciais (ou seja, o nome pessoal exclusivo ou UPN) associadas à assinatura do Intune.

2. Durante a configuração, os usuários receberão uma solicitação por uma ID Apple. Eles precisam fornecer uma ID Apple para permitir que o dispositivo instale o Portal da Empresa. Também podem fornecer a ID pelo menu de ajustes do iOS após a conclusão da instalação.

3. Após a conclusão da configuração, o dispositivo iOS deve instalar o aplicativo Portal da Empresa na App Store.

4. Agora, o usuário pode entrar no Portal da Empresa usando o UPN usado durante a configuração do dispositivo.

5. Após o logon, o usuário recebe uma solicitação para registrar seu dispositivo. A primeira etapa é identificar o dispositivo. O aplicativo apresenta uma lista de dispositivos iOS que já foram registrados pela empresa e atribuídos à conta do Intune do usuário. O usuário deve escolher o dispositivo correspondente.

  Se o dispositivo ainda não tiver sido registrado pela empresa, ele deverá escolher **novo dispositivo** para continuar com o fluxo de registro padrão.

6. Na próxima tela, o usuário deverá confirmar o número de série do novo dispositivo. O usuário pode tocar no link **confirmar o Número de Série**, o que iniciará as instruções para usar o aplicativo de Configurações a fim de verificar o número de série. Em seguida, o usuário deve inserir os quatro últimos caracteres do número de série no aplicativo Portal da Empresa.

  Essa etapa verifica se o dispositivo é o dispositivo corporativo registrado no Intune. Se o número de série no dispositivo não corresponder, o dispositivo incorreto terá sido selecionado. O usuário deve voltar à tela anterior e selecionar um dispositivo diferente.

7. Após a verificação do número de série, o aplicativo Portal da Empresa redirecionará para o site do Portal da Empresa a fim de finalizar o registro. Em seguida, o site solicita que o usuário retorne ao aplicativo.

8. O registro está concluído. Agora o usuário pode usar este dispositivo com o conjunto completo de recursos.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Sobre dispositivos gerenciados de propriedade da empresa sem afinidade de usuário

Os dispositivos configurados sem a afinidade de usuário não têm suporte no Portal da Empresa e não devem instalar o aplicativo. O Portal da Empresa se destina a usuários com credenciais corporativas e que precisam de acesso aos recursos corporativos personalizados (por exemplo, email). Os dispositivos registrados sem afinidade de usuário não devem ter uma entrada de usuário dedicada. O quiosque, o ponto de venda (PDV) ou os dispositivos de utilitário compartilhados são casos de uso comuns de dispositivos registrados sem afinidade de usuário.

Se a afinidade de usuário for necessária, certifique-se de que o perfil de registro do dispositivo tenha a opção **Afinidade de Usuário** selecionada antes de registrar o dispositivo. Para alterar o status de afinidade em um dispositivo, você deve desativar e registrar novamente o dispositivo.

