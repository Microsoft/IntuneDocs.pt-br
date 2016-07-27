---
title: "Recursos de gerenciamento de dispositivo móvel | Microsoft Intune"
description: "Leia este tópico para saber como o Intune pode ajudá-lo a gerenciar seus dispositivos móveis registrados com o serviço."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 23054b2f02d11ca19cd0902ebc1e6fdcf499d1f1
ms.openlocfilehash: 8f44256fe249c60df8e910858516a25463c8e875


---
# Recursos de gerenciamento de dispositivos móveis do Microsoft Intune

O Microsoft Intune permite que você gerencie uma variedade de dispositivos *registrando-os* no serviço. Os usuários podem usar um *portal da empresa* para executar uma variedade de operações como registrar seu dispositivo, procurar e instalar aplicativos, certificar-se de seu dispositivo é compatível com as políticas da empresa e entrar em contato com seu suporte de TI.
Este tópico fornece uma lista completa dos recursos oferecidos pelo registro de dispositivos.

Gerenciamento, inventário, implantação de aplicativos, provisionamento e desativação são manipulados por meio do console de administração do Intune. Os usuários obtêm acesso ao portal da empresa, que permite instalar aplicativos, registrar e remover dispositivos e também os ajuda a entrar em contato com o seu departamento de TI ou suporte técnico.



## Configuração e segurança de dispositivo

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Políticas de configuração<br><br>Políticas personalizadas|As políticas de configuração de dispositivos móveis permitem que você gerencie diversas configurações e recursos nos dispositivos móveis na sua organização. Por exemplo, é possível exigir uma senha, limitar o número de tentativas com falha, limitar os minutos antes do travamento da tela, definir a expiração de senha e impedir o uso de senhas usadas anteriormente. Você também pode controlar o uso de funcionalidades de hardware e software, como a câmera do dispositivo ou o navegador da Web<br><br>Use as políticas personalizadas quando as políticas de configuração não contiverem a configuração que você precisa. Para dispositivos iOS, você pode importar configurações que você exportou da ferramenta configuradora da Apple. Para outros dispositivos, você pode usar configurações OMA-URI para definir configurações e recursos no dispositivo.|[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Apagamento e bloqueio remotos e redefinição de senha|Apague dados confidenciais quando um dispositivo é perdido ou roubado. Por exemplo, você pode bloquear remotamente o dispositivo, restaurá-lo para as configurações de fábrica ou apagar apenas dados corporativos.<br>Você pode redefinir senhas se os usuários perderem o acesso ao dispositivo, bloquear dispositivos ausentes ou roubados, ou até mesmo apagar os dados de dispositivos ausentes ou roubados.|[Ajudar a proteger seus dispositivos com o bloqueio remoto e a redefinição de senha](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) e [Desativar dispositivos do gerenciamento do Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Modo de quiosque|Permite que você bloquear determinados recursos de dispositivos móveis, como a captura de tela e o interruptor de energia. Também permite restringir os dispositivos para que executem um único aplicativo especificado por você.|[Definições de política de configuração do iOS no Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Gerenciamento de aplicativos

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Gerenciamento e implantação de aplicativos|Fornece uma série de ferramentas para ajudá-lo a gerenciar aplicativos móveis ao longo de seu ciclo de vida, incluindo a implantação por meio de arquivos de instalação e lojas de aplicativos, monitoramento detalhado do status de aplicativos e remoção de aplicativos.|[Implantar aplicativos no Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Aplicativos compatíveis e incompatíveis|Permite especificar listas de aplicativos compatíveis (que os usuários podem instalar) e incompatíveis (que não devem ser instalados pelos usuários).|[Configurações de política do iOS no Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Gerenciamento de aplicativos móveis|Configure as restrições para aplicativos usando o gerenciamento de aplicativos móveis para os dispositivos gerenciados com o Intune e dispositivos que não são gerenciados pelo Intune. Isso ajuda você a aumentar a segurança dos dados de sua empresa, restringindo as operações como copiar e colar, backup externo de dados e a transferência de dados entre aplicativos.|[Configurar e implantar políticas de gerenciamento de aplicativos móveis no console do Microsoft Intune](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de disposição de aplicativos do Microsoft Intune](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de encapsulamento de aplicativos do Microsoft Intune](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Configuração do aplicativo móvel iOS|Use políticas de configuração de aplicativo móvel para fornecer as configurações para aplicativos iOS que podem ser necessárias para o usuário executar o aplicativo. Por exemplo, um aplicativo pode exigir que o usuário especifique o número da porta ou as informações de logon. Isso pode ajudar a simplificar a configuração do aplicativo e reduzir o número de chamadas ao suporte técnico.|[Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Perfis de provisionamento de aplicativo móvel do iOS|O Intune oferece as ferramentas para implantar proativamente perfis de provisionamento para aplicativos iOS que estão se aproximando da expiração.|[Usar políticas de perfil de provisionamento móvel do iOS para impedir que os aplicativos expirem](/intune/deploy-use/ios-mobile-app-provisioning-profiles)|
|Navegador gerenciado|Depois de implantar o navegador gerenciado para os usuários, você pode configurar a política de navegador gerenciado para controlar os sites que esses usuários podem visitar. Além disso, você também pode aplicar políticas de gerenciamento de aplicativos móveis para o navegador gerenciado.|[Gerenciar o acesso à internet usando políticas de navegador gerenciado com o Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|O Intune permite integrar-se ao Microsoft Passport for Work, que é um método de entrada alternativo para o Windows 10 que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual.|[Controlar as configurações do Microsoft Passport em dispositivos com Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Acesso de recursos da empresa

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Perfis de certificado|Crie e implante perfis de certificados confiáveis e certificados SCEP que podem ser usados para ajudar a proteger e autenticar perfis de Wi-Fi, VPN e email.|[Proteger o acesso a recursos com perfis de certificado no Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Perfis de Wi-Fi|Implante configurações de rede sem fio aos seus usuários. Ao implantar essas configurações, você minimiza o esforço necessário para o usuário final se conectar à rede corporativa.|[Conexões Wi-Fi no Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Perfis de email|Crie e implante configurações de email para dispositivos. Isso permite que os usuários acessem o email corporativo nos dispositivos pessoais deles sem que precisem fazer nenhum tipo de configuração.|[Configurar o acesso a email corporativo usando perfis de email com o Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Perfis de VPN|Implante configurações de VPN para usuários e dispositivos na sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário final necessário para conectar-se aos recursos na rede da empresa.|[Conexões VPN no Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Políticas de acesso condicional|Gerenciar o acesso ao email do Microsoft Exchange e do SharePoint Online em dispositivos que não são gerenciados pelo Intune.|[Restringir o acesso ao email e ao SharePoint com o Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventário e relatório

|Funcionalidade|Detalhes|Mais informações|
|--------------|-----------|--------------------|
|Inventário e relatório|Encontre informações sobre os dispositivos que você gerencia e o software que eles estão usando.|[Compreenda seus dispositivos com um inventário no Microsoft Intune](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Consulte também
[Recursos de gerenciamento de PC do Windows no Microsoft Intune](windows-pc-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


