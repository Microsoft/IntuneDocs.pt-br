---
title: "O que é o gerenciamento de aplicativo"
titlesuffix: Azure portal
description: "Use este tópico para conhecer os conceitos básicos sobre o gerenciamento de aplicativos com o Microsoft Intune"
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/08/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00e6b9f05f967da9066639dbf1b25bc76a49541b
ms.sourcegitcommit: 0a5f424a8f683daa919b13b5c363173040d561c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/13/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>O que é o gerenciamento de aplicativo do Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Como administrador de TI, você é responsável por garantir que os usuários finais têm acesso aos aplicativos de que precisam para realizar seu trabalho. Isso pode ser um desafio porque:
- Há uma ampla variedade de plataformas de dispositivo e tipos de aplicativos.
- Talvez você precise gerenciar aplicativos nos dispositivos da empresa e nos dispositivos dos próprios usuários.
- É necessário garantir que a rede e os dados permaneçam seguros.

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
|Aplicativos na empresa (linha de negócios)|Sim|Sim|Não|Sim|
|Aplicativos de uma loja|Sim|Sim|Sim|Sim|
|Atualizar aplicativos|Sim|Sim|Sim|Sim|

<sup>1</sup> Considere usar a [Proteção de Informações do Windows](windows-information-protection-configure.md) para proteger aplicativos em dispositivos que executam o Windows 10.

<sup>2</sup>Aplica-se apenas a dispositivos gerenciados pelo Intune.

## <a name="how-to-get-started"></a>Como começar

Encontre a maioria das tarefas relacionadas ao aplicativo na carga de trabalho **Aplicativos Móveis**, que pode ser acessada da seguinte maneira:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.

    ![A carga de trabalho de Aplicativos Móveis](./media/apps-workload.png)

### <a name="manage"></a>Gerenciar
- **Aplicativos** – esse nó é o local em que você adiciona, atribui e monitora a maioria de seus aplicativos.
    - [Adicionar aplicativos](apps-add.md)
    - [Atribuir aplicativos](apps-deploy.md)
    - [Monitorar aplicativos](apps-monitor.md)
- **Políticas de configuração de aplicativo** – as políticas de configuração de aplicativo permitem que você forneça as configurações que podem ser necessárias quando um usuário executa um aplicativo.
    - [Políticas de configuração de aplicativo iOS](app-configuration-policies-use-ios.md)
    - [Políticas de configuração de aplicativo do Android](app-configuration-policies-use-android.md)
- **Políticas de proteção de aplicativo** – permite associar as configurações de um aplicativo para ajudar a proteger os dados da empresa que ele usa. Por exemplo, você pode restringir os recursos de um aplicativo em se comunicar com outros aplicativos ou exigir que o usuário insira um PIN para acessar um aplicativo da empresa.
    - [Políticas de proteção de aplicativo](app-protection-policies.md)
- **Apagamento seletivo do aplicativo** – remover apenas os dados corporativos de um dispositivo de usuários que você selecionar.
    - [Apagamento seletivo de aplicativos](apps-selective-wipe.md)
- **Perfis de provisionamento de iOS** – os aplicativos iOS incluem um perfil de provisionamento e um código assinado por um certificado. Quando o certificado expira, o aplicativo não pode mais ser executado. O Intune fornece as ferramentas para atribuir proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.
    - [Perfis de provisionamento de aplicativo iOS](app-provisioning-profile-ios.md)

Para obter mais detalhes, consulte [Gerenciar aplicativos](app-management.md).

### <a name="monitor"></a>Monitor
- **Licenças de aplicativo** – exiba, atribua e monitore aplicativos adquiridos por volume de lojas de aplicativos.
    - [Aplicativos adquiridos por volume na Microsoft Store para Empresas](windows-store-for-business.md)
- **Aplicativos Descobertos** – mostra todos os aplicativos que foram atribuídos pelo Intune e instalados em um dispositivo.
- **Status de instalação do aplicativo** – Mostra o status de uma atribuição de aplicativo que você criou.
- **Status de proteção do aplicativo** – mostra o status de uma política de proteção de aplicativo para um usuário selecionado.
- **Logs de auditoria** – mostra a atividade relacionada ao aplicativo do Intune feita por todos os administradores de TI.

Para obter mais detalhes, consulte [Monitorar aplicativos](apps-monitor.md).

### <a name="setup"></a>Configuração
- **Tokens VPP iOS** – aplique e exiba sua licenças VPP (Programa de compra por volume) do iOS.
    - [Aplicativos iOS comprados por volume](vpp-apps-ios.md)
- **Certificado corporativo do Windows** – aplique ou exiba o status de um certificado de assinatura de código usado para distribuir aplicativos de linha de negócios para dispositivos com Windows gerenciados. 
- **Certificado da Symantec do Windows** – aplique ou exiba o status de um certificado de assinatura de código da Symantec, o qual é necessário para distribuir arquivos appx XAP e WP8.x para dispositivos com Windows 10 Mobile. 
- **Microsoft Store para Empresas** – Configure a integração com a Microsoft Store para Empresas. Depois, você pode sincronizar os aplicativos comprados com o Intune, atribuí-los e acompanhar o uso de licenças.
    - [Aplicativos adquiridos por volume na Microsoft Store para Empresas](windows-store-for-business.md)
- **Chaves de sideload do Windows** – você pode adicionar uma chave de sideload do Windows que pode ser usada para instalar um aplicativo diretamente nos dispositivos em vez de publicar e baixar o aplicativo da Windows store.
    - [Sideload um aplicativo do Windows](app-sideload-windows.md) 
- **Identidade visual do Portal da Empresa** – personalize o Portal da Empresa para dar a identidade visual de sua empresa.
    - [Configuração do Portal da Empresa](company-portal-app.md)
- **Categorias de aplicativo** – adicione, fixe e exclua os nomes de categoria de aplicativo.
- **Android For Work** – aprove e sincronize os aplicativos que você aprovou para sua empresa.
    - [Aplicativos Android for Work](apps-add-android-for-work.md) 

### <a name="help-and-support"></a>Ajuda e Suporte
- **Ajuda e suporte** – solucione problemas, solicite suporte ou exiba o status do Intune.
    - [Solucionar problemas](help-desk-operators.md)
