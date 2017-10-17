---
title: Recursos de gerenciamento de dispositivos registrados
description: "Leia este tópico para saber como o Intune pode ajudar a gerenciar dispositivos registrados."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f543996bf573aef9dd606ae403185da65a3599d2
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Recursos de gerenciamento de dispositivos registrados do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune permite que você gerencie uma variedade de dispositivos *registrando-os* no serviço. Você mesmo pode registrar alguns tipos de dispositivos, ou os usuários podem registrá-los usando o aplicativo do *portal da empresa*. Isso também permite que eles executem operações como navegar e instalar aplicativos, garantindo que seus dispositivos sejam compatíveis com as políticas da empresa, e entrem em contato com o suporte de TI.

Este tópico fornece uma lista completa dos recursos obtidos após o registro do dispositivo.

Gerenciamento, inventário, implantação de aplicativos, provisionamento e desativação são manipulados por meio do console de administração do Intune. Os usuários obtêm acesso ao portal da empresa, o que lhes permite instalar aplicativos, registrar e remover dispositivos e entrar em contato com seu departamento de TI ou suporte técnico.



## <a name="device-security-and-configuration"></a>Configuração e segurança de dispositivo

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Políticas de configuração<br><br>Políticas personalizadas| Permite que você gerencie diversas configurações e recursos em dispositivos móveis da sua organização. Por exemplo, é possível exigir uma senha, limitar o número de tentativas com falha, limitar o tempo antes do travamento da tela, definir a expiração da senha e impedir o uso de senhas usadas anteriormente. Você também pode controlar o uso de recursos de hardware e software, como a câmera do dispositivo ou o navegador da Web.<br><br>Use as políticas personalizadas quando as políticas de configuração não contiverem a configuração de que você precisa. Para dispositivos iOS, você pode importar configurações que exportou da ferramenta Apple Configurator. Para outros dispositivos, você pode usar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir configurações e recursos no dispositivo.|[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)|
|Apagamento e bloqueio remotos e redefinição de senha|Apaga dados confidenciais quando um dispositivo é perdido ou roubado. Por exemplo, você pode bloquear remotamente o dispositivo, restaurá-lo para as configurações de fábrica ou apagar apenas dados corporativos.<br><br>Você pode redefinir senhas se os usuários perderem o acesso ao dispositivo, bloquear dispositivos ausentes ou roubados, ou até mesmo apagar os dados de dispositivos ausentes ou roubados.|[Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Modo de quiosque|Permite que você bloqueie determinados recursos de dispositivos móveis, como capturas de tela e interruptores. Também permite restringir os dispositivos para que executem um único aplicativo especificado por você.|[Configurações da política de configuração do iOS no Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Gerenciamento de aplicativos

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Gerenciamento e implantação de aplicativos|Fornece uma série de ferramentas para ajudá-lo a gerenciar aplicativos móveis ao longo de seu ciclo de vida, incluindo a implantação por meio de arquivos de instalação e lojas de aplicativos, monitoramento detalhado do status de aplicativos e remoção de aplicativos.|[Implantar aplicativos no Microsoft Intune](/intune-classic/deploy-use/deploy-apps)|
|Aplicativos compatíveis e incompatíveis|Permite especificar listas de aplicativos compatíveis (que os usuários podem instalar) e aplicativos incompatíveis (que os usuários não podem instalar).|[Configurações da política do iOS no Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Gerenciamento de aplicativos móveis|Configura restrições para aplicativos usando o gerenciamento de aplicativos móveis para todos os dispositivos, gerenciados ou não com o Intune. Isso ajuda você a aumentar a segurança dos dados de sua empresa, restringindo operações como copiar e colar, backup externo de dados e transferência de dados entre aplicativos.|[Configurar e implantar políticas de gerenciamento de aplicativo móvel no console do Microsoft Intune](/intune/app-wrapper-prepare-android)|
|Configuração do aplicativo móvel iOS|Usa políticas de configuração de aplicativo móvel para fornecer configurações para aplicativos iOS que podem ser necessárias quando o usuário executar o aplicativo. Por exemplo, um aplicativo pode exigir que o usuário especifique o número da porta ou informações de logon. Isso pode ajudar a simplificar a configuração do aplicativo e reduzir o número de chamadas de suporte.|[Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Perfis de provisionamento de aplicativo móvel do iOS|Ajuda a implantar perfis de provisionamento para aplicativos iOS que estão se aproximando da expiração. |[Usar políticas de perfil de provisionamento móvel do iOS para impedir que os aplicativos expirem](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Navegador gerenciado|Configura políticas de navegador gerenciado para controlar os sites que os usuários do dispositivo podem visitar. Além disso, você também pode aplicar políticas de gerenciamento de aplicativos móveis para o navegador gerenciado.|[Gerenciar o acesso à Internet usando políticas de navegador gerenciado com o Microsoft Intune](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Windows Hello para Empresas|Permite se integrar ao Windows Hello para Empresas, que é um método de entrada alternativo para o Windows 10 que usa o Active Directory local ou o Azure Active Directory para substituir senhas, cartões inteligentes ou cartões inteligentes virtuais.|[Controlar as configurações do Windows Hello para Empresas em dispositivos com o Microsoft Intune](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Aplicativos adquiridos por volume|Ajuda a gerenciar aplicativos adquiridos por meio de um programa de compra por volume, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.|[Gerenciar aplicativos adquiridos por volume usando o Microsoft Intune](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Acesso de recursos da empresa

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Perfis de certificado|Cria e implanta perfis de certificados confiáveis e certificados SCEP (protocolo SCEP), que podem ser usados para proteger e autenticar perfis de Wi-Fi, VPN e email.|[Proteger o acesso a recursos com perfis de certificado no Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)|
|Perfis de Wi-Fi|Implanta configurações de rede sem fio para seus usuários. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar à rede corporativa.|[Conexões Wi-Fi no Microsoft Intune](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Perfis de email|Cria e implanta configurações de email para dispositivos. Isso significa que os usuários podem acessar o email corporativo em seus dispositivos pessoais sem que precisem fazer nenhum tipo de configuração.|[Configurar o acesso a email corporativo usando perfis de email com o Microsoft Intune](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Perfis de VPN|Implanta configurações de VPN para usuários e dispositivos na sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário necessário para se conectar aos recursos da rede da empresa.|[Conexões VPN no Microsoft Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Políticas de acesso condicional|Gerencia o acesso ao email do Microsoft Exchange e ao SharePoint Online em dispositivos que não são gerenciados pelo Intune.|[Restringir o acesso ao email e ao SharePoint com o Microsoft Intune](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Inventário e relatório

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Inventário e relatório|Encontra informações sobre os dispositivos que você gerencia e os softwares que os dispositivos estão usando.|[Compreender seus dispositivos com um inventário no Microsoft Intune](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|
