---
title: O que é gerenciamento de aplicativo no Microsoft Intune?
titlesuffix: ''
description: Saiba mais sobre os recursos de gerenciamento de aplicativo cliente por plataforma para o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f2c5da7772ff137e44fead66f00fe34004bb1f4
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850889"
---
# <a name="what-is-microsoft-intune-app-management"></a>O que é o gerenciamento de aplicativo do Microsoft Intune?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como administrador de TI, você pode usar o Microsoft Intune para gerenciar os aplicativos cliente que os colaboradores da sua empresa usam. Essa funcionalidade está além do gerenciamento de dispositivos e proteção de dados. Uma das prioridades do administrador é garantir que os usuários finais tenham acesso aos aplicativos necessários para realizar seu trabalho. Essa meta pode ser um desafio porque:
- Há uma ampla variedade de plataformas de dispositivo e tipos de aplicativos.
- Talvez você precise gerenciar aplicativos nos dispositivos da empresa e nos dispositivos pessoais dos usuários.
- É necessário garantir que a rede e os dados permaneçam seguros.

Além disso, pode ser útil atribuir e gerenciar aplicativos em dispositivos que não estão registrados com o Intune.

O Intune oferece uma variedade de recursos para ajudar a obter os aplicativos que você precisa, nos dispositivos em que você deseja executá-los. A tabela a seguir fornece um resumo dos recursos de gerenciamento de aplicativo: 

## <a name="app-management-capabilities-by-platform"></a>Recursos de gerenciamento de aplicativo por plataforma

|  | Android | iOS | macOS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Adicionar e atribuir aplicativos a dispositivos e usuários | Sim | Sim | Sim | Sim | Sim |
| Atribuir aplicativos a dispositivos não registrados com o Intune | Sim | Sim | Não | Não | Não |
| Usar políticas de configuração de aplicativo para controlar o comportamento de inicialização de aplicativos | Não | Sim | Não | Não | Não |
| Usar políticas de provisionamento de aplicativo móvel para renovar aplicativos expirados | Não | Sim | Não | Não | Não |
| Proteger os dados corporativos em aplicativos com as políticas de proteção de aplicativo | Sim | Sim | Não | Nº 1 | Não |
| Remover apenas dados corporativos de um aplicativo instalado (apagamento seletivo do aplicativo) | Sim | Sim | Não | Sim | Sim |
| Monitorar as atribuições de aplicativo | Sim | Sim | Sim | Sim | Sim |
| Atribuir e controlar aplicativos adquiridos por volume de uma loja de aplicativos | Não | Não | Não | Sim | Não |
| Instalação obrigatória de aplicativos nos dispositivos (obrigatório)2 | Sim | Sim | Sim | Sim | Sim |
| Instalação opcional em dispositivos do Portal da Empresa (instalação disponível) | Sim | Sim | Sim | Sim | Sim |
| Instalar atalho para um aplicativo na Web (link da Web) | Sim | Sim | Sim | Sim | Sim |
| Aplicativos na empresa (linha de negócios) | Sim | Sim | Sim | Sim | Não |
| Aplicativos de uma loja | Sim | Sim | Não | Sim | Sim |
| Atualizar aplicativos | Sim | Sim | Não | Sim | Sim |

<sup>1</sup> Considere usar a [Proteção de Informações do Windows](windows-information-protection-configure.md) para proteger aplicativos em dispositivos que executam o Windows 10.

<sup>2</sup> Aplica-se apenas a dispositivos gerenciados pelo Intune.

## <a name="get-started"></a>Introdução

Encontre a maioria das informações relacionadas a aplicativos na carga de trabalho **Aplicativos Clientes**, que pode ser acessada da seguinte forma:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Microsoft Intune**, selecione **Aplicativos clientes**.

    ![O painel de carga de trabalho "Aplicativos cliente"](./media/apps-workload.png)

As quatro seções a seguir descrevem as opções disponíveis no painel **Aplicativos clientes**.

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
- **Perfis de provisionamento de aplicativo do iOS**: os aplicativos iOS incluem um perfil de provisionamento e um código assinado por um certificado. Quando o certificado expira, o aplicativo não pode mais ser executado. O Intune fornece as ferramentas para atribuir proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração. Para obter mais informações, consulte:
    - [Perfis de provisionamento de aplicativo iOS](app-provisioning-profile-ios.md).

Para saber mais sobre essa seção, veja [Gerenciar aplicativos](app-management.md).

### <a name="monitor"></a>Monitor
- **Licenças de aplicativo**: Exiba, atribua e monitore aplicativos adquiridos por volume de lojas de aplicativos. Para obter mais informações, consulte:
    - [Aplicativos do VPP (volume-purchased program) do iOS](vpp-apps-ios.md).
    - [Aplicativos adquiridos por volume na Microsoft Store para Empresas](windows-store-for-business.md).
- **Aplicativos Descobertos**: Exiba todos os aplicativos atribuídos pelo Intune ou instalados em um dispositivo. Para obter mais informações, confira [Exibir detalhes do dispositivo com o Microsoft Intune](device-inventory.md).
- **Status de Instalação do Aplicativo**: Exiba o status de uma atribuição de aplicativo que você criou. Para saber mais, confira [Como monitorar atribuições e informações de aplicativo com o Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Status de proteção do aplicativo**: Exiba o status de uma política de proteção de aplicativo para um usuário selecionado.
- **Logs de auditoria**: Exiba a atividade relacionada ao aplicativo do Intune de todos os administradores de TI.

Para saber mais sobre essa seção, veja [Monitorar aplicativos](apps-monitor.md).

### <a name="set-up"></a>Configurar
- **Tokens do VPP de iOS**: Aplique e Exiba sua licenças VPP (Programa de compra em volume) do iOS. Para obter mais informações, consulte:
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
    - [Solucionar problemas](help-desk-operators.md).

## <a name="next-steps"></a>Próximas etapas

- [Adicionar um aplicativo ao Microsoft Intune](apps-add.md)
