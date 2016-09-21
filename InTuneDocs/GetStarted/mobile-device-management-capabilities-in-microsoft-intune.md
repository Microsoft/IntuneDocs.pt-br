---
title: Recursos de gerenciamento de dispositivos registrados | Microsoft Intune
description: "Leia este tópico para saber como o Intune pode ajudar a gerenciar dispositivos registrados."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ff6bfdc079e00f8a39cc532d1f6f9049aa6a32c8
ms.openlocfilehash: 10dfecd41e68440a4c27aa7358dbbc88b6106001


---
# Recursos de gerenciamento de dispositivos registrados do Microsoft Intune

O Microsoft Intune permite que você gerencie uma variedade de dispositivos *registrando-os* no serviço. Você mesmo pode registrar alguns tipos de dispositivos, ou os usuários podem registrá-los usando o aplicativo do *portal da empresa*. Isso também permite que eles executem operações como navegar e instalar aplicativos, garantindo que seus dispositivos sejam compatíveis com as políticas da empresa, e entrem em contato com o suporte de TI.

Este tópico fornece uma lista completa dos recursos obtidos após o registro do dispositivo.

Gerenciamento, inventário, implantação de aplicativos, provisionamento e desativação são manipulados por meio do console de administração do Intune. Os usuários obtêm acesso ao portal da empresa, o que lhes permite instalar aplicativos, registrar e remover dispositivos e entrar em contato com seu departamento de TI ou suporte técnico.



## Configuração e segurança de dispositivo

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Políticas de configuração<br><br>Políticas personalizadas| Permite que você gerencie diversas configurações e recursos em dispositivos móveis da sua organização. Por exemplo, é possível exigir uma senha, limitar o número de tentativas com falha, limitar o tempo antes do travamento da tela, definir a expiração da senha e impedir o uso de senhas usadas anteriormente. Você também pode controlar o uso de recursos de hardware e software, como a câmera do dispositivo ou o navegador da Web.<br><br>Use as políticas personalizadas quando as políticas de configuração não contiverem a configuração de que você precisa. Para dispositivos iOS, você pode importar configurações que exportou da ferramenta Apple Configurator. Para outros dispositivos, você pode usar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir configurações e recursos no dispositivo.|[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Apagamento e bloqueio remotos e redefinição de senha|Apaga dados confidenciais quando um dispositivo é perdido ou roubado. Por exemplo, você pode bloquear remotamente o dispositivo, restaurá-lo para as configurações de fábrica ou apagar apenas dados corporativos.<br><br>Você pode redefinir senhas se os usuários perderem o acesso ao dispositivo, bloquear dispositivos ausentes ou roubados, ou até mesmo apagar os dados de dispositivos ausentes ou roubados.|[Ajudar a proteger seus dispositivos com o bloqueio remoto e a redefinição de senha](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) e [Desativar dispositivos do gerenciamento do Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Modo de quiosque|Permite que você bloqueie determinados recursos de dispositivos móveis, como capturas de tela e interruptores. Também permite restringir os dispositivos para que executem um único aplicativo especificado por você.|[Definições de política de configuração do iOS no Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Gerenciamento de aplicativos

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Gerenciamento e implantação de aplicativos|Fornece uma série de ferramentas para ajudá-lo a gerenciar aplicativos móveis ao longo de seu ciclo de vida, incluindo a implantação por meio de arquivos de instalação e lojas de aplicativos, monitoramento detalhado do status de aplicativos e remoção de aplicativos.|[Implantar aplicativos no Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Aplicativos compatíveis e incompatíveis|Permite especificar listas de aplicativos compatíveis (que os usuários podem instalar) e aplicativos incompatíveis (que os usuários não podem instalar).|[Configurações de política do iOS no Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Gerenciamento de aplicativos móveis|Configura restrições para aplicativos usando o gerenciamento de aplicativos móveis para todos os dispositivos, gerenciados ou não com o Intune. Isso ajuda você a aumentar a segurança dos dados de sua empresa, restringindo operações como copiar e colar, backup externo de dados e transferência de dados entre aplicativos.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de disposição de aplicativos do Microsoft Intune](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de encapsulamento de aplicativos do Microsoft Intune](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Configuração do aplicativo móvel iOS|Usa políticas de configuração de aplicativo móvel para fornecer configurações para aplicativos iOS que podem ser necessárias quando o usuário executar o aplicativo. Por exemplo, um aplicativo pode exigir que o usuário especifique o número da porta ou informações de logon. Isso pode ajudar a simplificar a configuração do aplicativo e reduzir o número de chamadas de suporte.|[Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Perfis de provisionamento de aplicativo móvel do iOS|Ajuda a implantar perfis de provisionamento para aplicativos iOS que estão se aproximando da expiração. |[Usar políticas de perfil de provisionamento móvel do iOS para impedir que os aplicativos expirem](/intune/deploy-use/ios-mobile-app-provisioning-profiles)|
|Navegador gerenciado|Configura políticas de navegador gerenciado para controlar os sites que os usuários do dispositivo podem visitar. Além disso, você também pode aplicar políticas de gerenciamento de aplicativos móveis para o navegador gerenciado.|[Gerenciar o acesso à internet usando políticas de navegador gerenciado com o Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Windows Hello para Empresas|Permite se integrar ao Windows Hello para Empresas, que é um método de entrada alternativo para o Windows 10 que usa o Active Directory local ou o Azure Active Directory para substituir senhas, cartões inteligentes ou cartões inteligentes virtuais.|[Controlar configurações do Windows Hello para Empresas em dispositivos com o Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Aplicativos adquiridos por volume|Ajuda a gerenciar aplicativos adquiridos por meio de um programa de compra por volume, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.|[Gerenciar aplicativos adquiridos por volume que usam o Microsoft Intune](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## Acesso de recursos da empresa

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Perfis de certificado|Cria e implanta perfis de certificados confiáveis e certificados SCEP (protocolo SCEP), que podem ser usados para proteger e autenticar perfis de Wi-Fi, VPN e email.|[Proteger o acesso a recursos com perfis de certificado no Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Perfis de Wi-Fi|Implanta configurações de rede sem fio para seus usuários. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar à rede corporativa.|[Conexões Wi-Fi no Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Perfis de email|Cria e implanta configurações de email para dispositivos. Isso significa que os usuários podem acessar o email corporativo em seus dispositivos pessoais sem que precisem fazer nenhum tipo de configuração.|[Configurar o acesso a email corporativo usando perfis de email com o Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Perfis de VPN|Implanta configurações de VPN para usuários e dispositivos na sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário necessário para se conectar aos recursos da rede da empresa.|[Conexões VPN no Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Políticas de acesso condicional|Gerencia o acesso ao email do Microsoft Exchange e ao SharePoint Online em dispositivos que não são gerenciados pelo Intune.|[Restringir o acesso ao email e ao SharePoint com o Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventário e relatório

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Inventário e relatório|Encontra informações sobre os dispositivos que você gerencia e os softwares que os dispositivos estão usando.|[Compreenda seus dispositivos com um inventário no Microsoft Intune](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Consulte também
[Recursos de gerenciamento de PC do Windows no Microsoft Intune](windows-pc-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Sep16_HO1-->


