---
title: "O que é o gerenciamento de aplicativos | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: use este tópico para aprender as noções básicas sobre gerenciamento de aplicativos com o Microsoft Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 56eefde5969f5426886c07bd6e9a548c8526e82e
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-microsoft-intune-app-management"></a>O que é o gerenciamento de aplicativo do Microsoft Intune?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]


Como um administrador de TI, você provavelmente será encarregado de verificar se os usuários finais têm acesso aos aplicativos que precisam para realizar seu trabalho. Isso pode ser um desafio porque:
- Há uma ampla variedade de plataformas de dispositivo e tipos de aplicativos.
- Pode ser necessário gerenciar aplicativos em dispositivos da empresa, bem como nos dispositivos dos próprios usuários.
- É necessário fazer tudo isso e garantir ao mesmo tempo que a rede e os dados permaneçam seguros. 

Além disso, pode ser útil atribuir e gerenciar aplicativos em dispositivos que não estão registrados com o Intune.

O Intune oferece uma variedade de recursos para ajudar a obter os aplicativos que você precisa, nos dispositivos que você deseja.

## <a name="app-management-capabilities-by-platform"></a>Recursos de gerenciamento de aplicativo por plataforma

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Adicionar e atribuir aplicativos a dispositivos e usuários|Sim|Sim|Sim|Sim|
|Atribuir aplicativos a dispositivos não registrados com o Intune|Sim|Sim|Não|Não|
|Usar políticas de configuração de aplicativo para controlar o comportamento de inicialização de aplicativos|Não|Sim|Não|Não|
|Usar políticas de provisionamento de aplicativo móvel para renovar aplicativos expirados|Não|Sim|Não|Não|
|Proteger os dados corporativos em aplicativos com as políticas de proteção de aplicativo|Sim|Sim|Não|Não<sup>1</sup>|
|Remover apenas dados corporativos de um aplicativo instalado (apagamento seletivo do aplicativo)|Sim|Sim|Sim|Sim|
|Monitorar as atribuições de aplicativo|Sim|Sim|Sim|Sim|
|Atribuir e controlar aplicativos adquiridos por volume de uma loja de aplicativos|Não|Não|Não|Sim|
|Instalação obrigatória de aplicativos nos dispositivos (Obrigatório)<sup>2</sup>|Sim|Sim|Sim|Sim|
|Instalação opcional em dispositivos do Portal da Empresa (instalação disponível)|Sim|Sim|Sim|Sim|
|Instalar o atalho a um aplicativo na Web (clipe da Web)|Sim|Sim|Sim|Sim|
|Aplicativos na empresa (linha de negócios)|Sim|Sim|Não|Não|
|Aplicativos de uma loja|Sim|Sim|Sim|Sim|
|Atualizar aplicativos|Sim|Sim|Sim|Sim|

<sup>1</sup> Considere usar a [Proteção de Informações do Windows]windows-information-protection-configure.md) para proteger aplicativos em dispositivos com o Windows 10.

<sup>2</sup>Aplica-se apenas a dispositivos gerenciados pelo Intune.


## <a name="how-to-get-started"></a>Como começar

Você encontrará a maioria das tarefas relacionadas à carga de trabalho de **Aplicativos Móveis**, que pode ser acessada da seguinte maneira:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.

    ![A carga de trabalho de Aplicativos Móveis](./media/apps-workload.png)

### <a name="manage"></a>Gerenciar
- **Aplicativos** – É aqui que você vai adicionar, atribuir e monitorar a maioria de seus aplicativos. 
    - [Adicionar aplicativos](apps-add.md)
    - [Atribuir aplicativos](apps-deploy.md)
    - [Monitorar aplicativos](apps-monitor.md)
- **Políticas de configuração de aplicativo** – as políticas de configuração de aplicativo permitem que você forneça as configurações que podem ser necessárias quando um usuário executa um aplicativo. Para obter detalhes, consulte:
    - [Políticas de configuração de aplicativo](app-configuration-policies.md)
- **Políticas de proteção de aplicativo** – permite associar as configurações de um aplicativo para ajudar a proteger os dados da empresa que ele usa. Por exemplo, você pode restringir os recursos de um aplicativo em se comunicar com outros aplicativos ou exigir que o usuário insira um PIN para acessar um aplicativo da empresa.
    - [Políticas de proteção de aplicativo](app-protection-policies.md)
- **Apagamento seletivo do aplicativo** – remover apenas os dados corporativos de um dispositivo de usuários que você selecionar.
    - [Apagamento seletivo de aplicativos](apps-selective-wipe.md)
- **Perfis de provisionamento de iOS** – os aplicativos iOS incluem um perfil de provisionamento e um código assinado por um certificado. Quando o certificado expira, o aplicativo não pode mais ser executado. O Intune fornece as ferramentas para atribuir proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.
    - [Perfis de provisionamento de aplicativo iOS](app-provisioning-profile-ios.md)

### <a name="monitor"></a>Monitor
- **Aplicativos Licenciados** – exiba, atribua e monitore aplicativos adquiridos por volume de lojas de aplicativos.
    - [Aplicativos da Windows Store para Empresas comprados por volume](windows-store-for-business.md)
- **Aplicativos descobertos** – Mostra todos os aplicativos que foram atribuídos pelo Intune e instalados em um dispositivo.
- **Status de instalação do aplicativo** – Mostra o status de uma atribuição de aplicativo que você criou.
- **Status de proteção do aplicativo** – mostra o status de uma política de proteção de aplicativo para um usuário selecionado.

Para obter detalhes, consulte [Monitorar aplicativos](apps-monitor.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Windows Store para Empresas** – Configurar a integração da Windows Store para Empresas. Depois de fazer isso, você pode sincronizar os aplicativos adquiridos com o Intune, atribuí-los e acompanhar o uso de licenças. 
    - [Aplicativos da Windows Store para Empresas comprados por volume](windows-store-for-business.md)
- **Identidade visual do Portal da Empresa** – personalize o Portal da Empresa para dar a identidade visual de sua empresa. 
    - [Configuração do Portal da Empresa](company-portal-app.md)

