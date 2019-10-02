---
title: Recursos de gerenciamento de dispositivo do Microsoft Intune
description: Leia este tópico para saber como o Intune pode ajudar a gerenciar dispositivos registrados.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1bac049aebfb0fec6c9d86e1e08e81237867175d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723106"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Recursos de gerenciamento de dispositivos registrados do Microsoft Intune

O Microsoft Intune permite que você gerencie uma variedade de dispositivos *registrando-os* no serviço. Você mesmo pode registrar alguns tipos de dispositivos, ou os usuários podem registrá-los usando o aplicativo do *portal da empresa*. O registro permite que eles procurem e instalem aplicativos, garantam que os dispositivos deles estão em conformidade com as políticas da empresa e entrem em contato com o suporte de TI.

Este artigo fornece uma lista completa dos recursos obtidos após o registro dos dispositivos.

O gerenciamento, o inventário, a implantação de aplicativos, o provisionamento e a desativação são manipulados por meio do Intune no portal do Azure.

Os usuários obtêm acesso ao portal da empresa, o que lhes permite instalar aplicativos, registrar e remover dispositivos e entrar em contato com seu departamento de TI ou suporte técnico.



## <a name="device-security-and-configuration"></a>Configuração e segurança de dispositivo

|Capacidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Políticas de configuração<br><br>Políticas personalizadas| Permite que você gerencie diversas configurações e recursos em dispositivos móveis da sua organização. Por exemplo, é possível exigir uma senha, limitar o número de tentativas com falha, limitar o tempo antes do travamento da tela, definir a expiração da senha e impedir o uso de senhas usadas anteriormente. Você também pode controlar o uso de recursos de hardware e software, como a câmera do dispositivo ou o navegador da Web.<br><br>Use as políticas personalizadas quando as políticas de configuração não contiverem a configuração de que você precisa. Para dispositivos iOS, você pode importar configurações que exportou da ferramenta Apple Configurator. Para outros dispositivos, você pode usar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir configurações e recursos no dispositivo.|[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](../protect/device-compliance-get-started.md)|
|Apagamento e bloqueio remotos e redefinição de senha|Apaga dados confidenciais quando um dispositivo é perdido ou roubado. Por exemplo, você pode bloquear remotamente o dispositivo, restaurá-lo para as configurações de fábrica ou apagar apenas dados corporativos.<br><br>Você pode redefinir senhas se os usuários perderem o acesso ao dispositivo, bloquear dispositivos ausentes ou roubados, ou até mesmo apagar os dados de dispositivos ausentes ou roubados.|Ajude a proteger os dispositivos com [bloqueio remoto](../remote-actions/device-remote-lock.md) e [redefinição de senha](../remote-actions/device-passcode-reset.md)|
|Modo de quiosque|Permite que você bloqueie determinados recursos de dispositivos móveis, como capturas de tela e interruptores. Também permite restringir os dispositivos para que executem um único aplicativo especificado por você. |[Configurações da política de configuração do iOS no Microsoft Intune](../configuration/device-restrictions-ios.md)|

## <a name="app-management"></a>Gerenciamento de aplicativos

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Gerenciamento e implantação de aplicativos|Fornece uma série de ferramentas para ajudá-lo a gerenciar aplicativos móveis ao longo de seu ciclo de vida, incluindo a implantação por meio de arquivos de instalação e lojas de aplicativos, monitoramento detalhado do status de aplicativos e remoção de aplicativos.|[Implantar aplicativos no Microsoft Intune](../apps/apps-deploy.md)|
|Aplicativos compatíveis e incompatíveis|Permite especificar listas de aplicativos em conformidade (que os usuários podem instalar) e aplicativos sem conformidade (que os usuários não podem instalar).|[Configurações da política do iOS no Microsoft Intune](../configuration/device-restrictions-ios.md)|
|Gerenciamento de aplicativos móveis|Configura restrições para aplicativos usando o gerenciamento de aplicativos móveis para todos os dispositivos, gerenciados ou não com o Intune. Você pode aumentar a segurança dos dados de sua empresa restringindo operações como copiar e colar, backup externo de dados e transferência de dados entre aplicativos.|[Configurar e implantar políticas de gerenciamento de aplicativo móvel no console do Microsoft Intune](../developer/app-wrapper-prepare-android.md)|
|Configuração do aplicativo móvel iOS|Usa políticas de configuração de aplicativo móvel para fornecer configurações para aplicativos iOS que podem ser necessárias quando o usuário executar o aplicativo. Por exemplo, um aplicativo pode exigir que o usuário especifique o número da porta ou informações de logon. Você pode simplificar a configuração do aplicativo e reduzir o número de chamadas de suporte.|[Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune](../apps/app-configuration-policies-use-ios.md)|
|Perfis de provisionamento de aplicativo móvel do iOS|Ajuda a implantar perfis de provisionamento para aplicativos iOS que estão se aproximando da expiração. |[Usar políticas de perfil de provisionamento móvel do iOS para impedir que os aplicativos expirem](../apps/app-provisioning-profile-ios.md)|
|Navegador gerenciado|Configura políticas de navegador gerenciado para controlar os sites que os usuários do dispositivo podem visitar. Além disso, você também pode aplicar políticas de gerenciamento de aplicativos móveis para o navegador gerenciado.|[Gerenciar o acesso à Internet usando políticas de navegador gerenciado com o Microsoft Intune](../apps/app-configuration-managed-browser.md)|
|Windows Hello para Empresas|Permite se integrar ao Windows Hello para Empresas, que é um método de entrada alternativo para o Windows 10 que usa o Active Directory local ou o Azure Active Directory para substituir senhas, cartões inteligentes ou cartões inteligentes virtuais.|[Controlar as configurações do Windows Hello para Empresas em dispositivos com o Microsoft Intune](../protect/windows-hello.md)|
|Aplicativos adquiridos por volume|Ajuda a gerenciar aplicativos adquiridos por meio de um programa de compra por volume, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.|[Gerenciar aplicativos adquiridos por volume usando o Microsoft Intune](../apps/vpp-apps.md)|

## <a name="company-resource-access"></a>Acesso de recursos da empresa

|Capacidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Perfis de certificado|Cria e implanta perfis de certificados confiáveis e certificados SCEP (protocolo SCEP), que podem ser usados para proteger e autenticar perfis de Wi-Fi, VPN e email.|[Proteger o acesso a recursos com perfis de certificado no Microsoft Intune](../protect/certificates-configure.md)|
|Perfis de Wi-Fi|Implanta configurações de rede sem fio para seus usuários. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar à rede corporativa.|[Conexões Wi-Fi no Microsoft Intune](../configuration/wi-fi-settings-configure.md)|
|Perfis de email|Cria e implanta configurações de email nos dispositivos para que os usuários possam acessar o email corporativo em seus dispositivos pessoais sem que precisem fazer nenhum tipo de configuração.|[Configurar o acesso a email corporativo usando perfis de email com o Microsoft Intune](../configuration/email-settings-configure.md)|
|Perfis de VPN|Implanta configurações de VPN para usuários e dispositivos na sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário necessário para se conectar aos recursos da rede da empresa.|[Conexões VPN no Microsoft Intune](../configuration/device-profiles.md#vpn)|
|Políticas de acesso condicional|Gerencia o acesso ao email do Microsoft Exchange e ao SharePoint Online em dispositivos que não são gerenciados pelo Intune.|[Restringir o acesso ao email e ao SharePoint com o Microsoft Intune](../protect/app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Próximas etapas

[Consulte uma lista de dispositivos que você pode gerenciar](../remote-actions/device-management.md).
