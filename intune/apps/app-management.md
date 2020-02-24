---
title: O que é gerenciamento de aplicativo no Microsoft Intune?
titleSuffix: ''
description: Saiba mais sobre os recursos de gerenciamento de aplicativo cliente por plataforma para o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 84d33e0ff6bbe407d9838f97214f37d042a2e261
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414696"
---
# <a name="what-is-microsoft-intune-app-management"></a>O que é o gerenciamento de aplicativo do Microsoft Intune?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como administrador de TI, você pode usar o Microsoft Intune para gerenciar os aplicativos cliente que os colaboradores da sua empresa usam. Essa funcionalidade está além do gerenciamento de dispositivos e proteção de dados. Uma das prioridades do administrador é garantir que os usuários finais tenham acesso aos aplicativos necessários para realizar seu trabalho. Essa meta pode ser um desafio porque:
- Há uma ampla variedade de plataformas de dispositivo e tipos de aplicativos.
- Talvez você precise gerenciar aplicativos nos dispositivos da empresa e nos dispositivos pessoais dos usuários.
- É necessário garantir que a rede e os dados permaneçam seguros.

Além disso, pode ser útil atribuir e gerenciar aplicativos em dispositivos que não estão registrados com o Intune.

## <a name="mobile-application-management-mam-basics"></a>Noções básicas sobre MAM (Gerenciamento de Aplicativos Móveis)

[Gerenciamento de aplicativo móvel do Intune](app-lifecycle.md) refere-se ao pacote de recursos de gerenciamento do Intune que permite publicar, enviar por push, configurar, proteger, monitorar e atualizar aplicativos móveis para os usuários.

O MAM possibilita gerenciar e proteger os dados de sua organização em um aplicativo. Com o **MAM sem registro** (MAM-WE), um aplicativo relacionado ao trabalho ou à escola que contém dados confidenciais pode ser gerenciado em quase todos os [dispositivos](app-management.md#app-management-capabilities-by-platform), incluindo dispositivos pessoais em cenários de **BYOD** (traga seu próprio dispositivo). Vários aplicativos de produtividade, como os aplicativos do Microsoft Office, podem ser gerenciados pelo Intune MAM. Confira a lista oficial de [aplicativos protegidos pelo Microsoft Intune](apps-supported-intune-apps.md) disponíveis para uso público.

O Intune MAM dá suporte a duas configurações:
- **Intune MDM + MAM**: Os administradores de TI apenas podem gerenciar aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos registrados no Intune MDM (gerenciamento de dispositivo móvel). Para gerenciar aplicativos usando o MDM + MAM, os clientes devem usar o console do Intune no portal do Azure em https://portal.azure.com.
- **MAM sem registro de dispositivo**: o MAM sem registro de dispositivo, ou MAM-WE, permite que os administradores de TI gerenciem aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos não registrados no Intune MDM. Isso significa que os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados em provedores de EMM de terceiros. Para gerenciar aplicativos usando o MAM-WE, os clientes devem usar o console do Intune no portal do Azure em https://portal.azure.com. Além disso, os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados com provedores de Gerenciamento de Mobilidade Empresarial (EMM) de terceiros ou não registrados com um MDM. Para saber mais sobre BYOD e EMS da Microsoft, confira [Decisões de tecnologia para habilitar BYOD com Microsoft Enterprise Mobility + Security (EMS)](../fundamentals/byod-technology-decisions.md).

## <a name="app-management-capabilities-by-platform"></a>Recursos de gerenciamento de aplicativo por plataforma

O Intune oferece uma variedade de recursos para ajudar a obter os aplicativos que você precisa, nos dispositivos em que você deseja executá-los. A tabela a seguir fornece um resumo dos recursos de gerenciamento de aplicativo.

|  | Android/Android Enterprise | iOS/iPadOS | macOS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Adicionar e atribuir aplicativos a dispositivos e usuários | Sim | Sim | Sim | Sim | Sim |
| Atribuir aplicativos a dispositivos não registrados com o Intune | Sim | Sim | Não | Não | Não |
| Usar políticas de configuração de aplicativo para controlar o comportamento de inicialização de aplicativos | Sim | Sim | Não | Não | Não |
| Usar políticas de provisionamento de aplicativo móvel para renovar aplicativos expirados | Não | Sim | Não | Não | Não |
| Proteger os dados corporativos em aplicativos com as políticas de proteção de aplicativo | Sim | Sim | Não | Não <sup>1</sup> | Não |
| Remover apenas dados corporativos de um aplicativo instalado (apagamento seletivo do aplicativo) | Sim | Sim | Não | Sim | Sim |
| Monitorar as atribuições de aplicativo | Sim | Sim | Sim | Sim | Sim |
| Atribuir e controlar aplicativos adquiridos por volume de uma loja de aplicativos | Não | Não | Não | Sim | Não |
| Instalação obrigatória de aplicativos nos dispositivos (obrigatório) <sup>2</sup> | Sim | Sim | Sim | Sim | Sim |
| Instalação opcional em dispositivos do Portal da Empresa (instalação disponível) | Sim <sup>3</sup> | Sim | Sim | Sim | Sim |
| Instalar atalho para um aplicativo na Web (link da Web) | Sim <sup>4</sup> | Sim | Sim | Sim | Sim |
| Aplicativos na empresa (linha de negócios) | Sim | Sim | Sim | Sim | Não |
| Aplicativos de uma loja | Sim | Sim | Não | Sim | Sim |
| Atualizar aplicativos | Sim | Sim | Não | Sim | Sim |

<sup>1</sup> Considere usar a [Proteção de Informações do Windows](../protect/windows-information-protection-configure.md) para proteger aplicativos em dispositivos que executam o Windows 10.<br>
<sup>2</sup> Aplica-se apenas a dispositivos gerenciados pelo Intune.<br>
<sup>3</sup> O Intune é compatível com aplicativos disponíveis na loja do Google Play Gerenciado em dispositivos Android Enterprise.<br>
<sup>4</sup> O Intune não fornece a instalação de um atalho para um aplicativo como um link da Web em dispositivos Android Enterprise padrão. No entanto, o suporte ao link da Web é fornecido para [dispositivos Android Enterprise dedicados a vários aplicativos](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings). 


## <a name="get-started"></a>Introdução

Você encontrará a maioria das informações relacionadas ao aplicativo na carga de trabalho **Aplicativos**, que pode ser acessada da seguinte forma:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecione **Aplicativos**.

    ![O painel da carga de trabalho Aplicativos](./media/app-management/apps-workload.png)

As quatro seções a seguir descrevem as opções disponíveis no painel **Aplicativos**.

### <a name="manage"></a>Gerenciar
- **Aplicativos**: Selecione esta opção para adicionar, exibir, atribuir e monitorar os aplicativos usados por sua força de trabalho. Para obter mais informações, consulte:
  - [Adicionar aplicativos](apps-add.md).
  - [Atribuir aplicativos](apps-deploy.md).
  - [Monitorar aplicativos](apps-monitor.md).
- **Políticas de configuração de aplicativo**: Selecione essa opção para fornecer as configurações que possam ser necessárias quando um usuário executar um aplicativo. Para obter mais informações, consulte:
  - [Políticas de configuração de aplicativo para o Intune](app-configuration-policies-overview.md).
    - [Políticas de configuração de aplicativo iOS](app-configuration-policies-use-ios.md).
    - [Políticas de configuração de aplicativo do Android](app-configuration-policies-use-android.md).
- **Políticas de proteção de aplicativo**: Selecione essa opção para associar as configurações de um aplicativo e ajudar a proteger os dados da empresa que ele usa. Por exemplo, você pode restringir os recursos de um aplicativo em se comunicar com outros aplicativos ou exigir que o usuário insira um PIN para acessar um aplicativo da empresa. Para obter mais informações, consulte:
  - [Políticas de Proteção de Aplicativo](app-protection-policies.md).
- **Apagamento seletivo de aplicativos**: Selecione esta opção para remover apenas os dados corporativos do dispositivo de um usuário selecionado. Para obter mais informações, consulte:
  - [Apagamento seletivo de aplicativos](apps-selective-wipe.md).
- **Perfis de provisionamento de aplicativo do iOS**: os aplicativos iOS/iPadOS incluem um perfil de provisionamento e um código assinado por um certificado. Quando o certificado expira, o aplicativo não pode mais ser executado. O Intune fornece as ferramentas para atribuir proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração. Para obter mais informações, consulte:
  - [Perfis de provisionamento de aplicativo iOS](app-provisioning-profile-ios.md).

Para saber mais sobre essa seção, veja [Gerenciar aplicativos](app-management.md).

### <a name="monitor"></a>Monitor
- **Licenças de aplicativo**: Exiba, atribua e monitore aplicativos adquiridos por volume de lojas de aplicativos. Para obter mais informações, consulte:
  - [Aplicativos do VPP (volume-purchased program) do iOS](vpp-apps-ios.md).
  - [Aplicativos adquiridos por volume na Microsoft Store para Empresas](windows-store-for-business.md).
- **Aplicativos Descobertos**: Exiba todos os aplicativos atribuídos pelo Intune ou instalados em um dispositivo. Para saber mais, confira [Aplicativos descobertos pelo Intune](app-discovered-apps.md).
- **Status de Instalação do Aplicativo**: Exiba o status de uma atribuição de aplicativo que você criou. Para saber mais, confira [Como monitorar atribuições e informações de aplicativo com o Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Status de proteção do aplicativo**: Exiba o status de uma política de proteção de aplicativo para um usuário selecionado.
- **Logs de auditoria**: Exiba a atividade relacionada ao aplicativo do Intune de todos os administradores de TI.

Para saber mais sobre essa seção, veja [Monitorar aplicativos](apps-monitor.md).

### <a name="set-up"></a>Configuração
- **Tokens do VPP de iOS**: Aplique e exiba suas licenças VPP (Volume Purchase Program) do iOS/iPadOS. Para obter mais informações, consulte:
  - [Aplicativos iOS comprados por volume](vpp-apps-ios.md)
- **Certificado corporativo do Windows**: Aplique ou Exiba o status de um certificado de assinatura de código usado para distribuir aplicativos de linha de negócios para dispositivos com Windows gerenciados.
- **Certificado da Symantec do Windows**: Aplique ou Exiba o status de um certificado de assinatura de código da Symantec, o qual é necessário para distribuir arquivos appx XAP e WP8.x para dispositivos com Windows 10 Mobile.
- **Microsoft Store para Empresas**: Configure uma integração com a Microsoft Store para Empresas. Depois, você pode sincronizar os aplicativos comprados com o Intune, atribuí-los e acompanhar o uso de licenças. Para obter mais informações, consulte:
  - [Aplicativos adquiridos por volume na Microsoft Store para Empresas](windows-store-for-business.md).
- **Chaves de sideload do Windows**: Adicione uma chave de sideload do Windows que pode ser usada para instalar um aplicativo diretamente nos dispositivos em vez de publicar e baixar o aplicativo da Windows store. Para obter mais informações, consulte:
  - [Sideload um aplicativo do Windows](app-sideload-windows.md).
- **Identidade visual do Portal da Empresa**: Personalize o Portal da Empresa para dar a identidade visual de sua empresa. Para obter mais informações, consulte:
  - [Configuração do Portal da Empresa](company-portal-app.md).
- **Todas as categorias**: Adicione, fixe e exclua os nomes de categoria de aplicativo.
- **Perfil de trabalho do Android**: Aprove e sincronize os aplicativos que você aprovou para sua empresa. Para obter mais informações, consulte:
  - [Aplicativos do perfil de trabalho Android](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Ajuda e suporte
- **Ajuda e suporte**: Solucione problemas, solicite suporte ou Exiba o status do Intune. Para obter mais informações, consulte:
  - [Solucionar problemas](../fundamentals/help-desk-operators.md).

## <a name="next-steps"></a>Próximas etapas

- [Adicionar um aplicativo ao Microsoft Intune](apps-add.md)
