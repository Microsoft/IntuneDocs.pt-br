---
# required metadata

title: Referência da política do Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Referência da política do Microsoft Intune

Use as informações neste tópico para ajudar na decisão sobre qual política do Microsoft Intune você precisa usar para gerenciar seus dispositivos.

> [!TIP]
> Para obter mais informações detalhadas sobre como usar políticas, consulte [Manage settings and features on your devices with Microsoft Intune Policies (Gerenciar configurações e funcionalidades em seus dispositivos com as políticas do Microsoft Intune)](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).


## Políticas de configuração do Android

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Configuração personalizada (Android 4 e posterior, Samsung KNOX padrão 4.0 e posterior)**|Implante configurações OMA-URI, como configurações de Wi-Fi que podem ser usadas para controlar recursos do dispositivo. Isso é útil quando a configuração não está disponível em uma política de configuração.<br /><br />Para ver mais detalhes, consulte [Android policy settings in Microsoft Intune (Configurações de política do Android no Microsoft Intune)](android-policy-settings-in-microsoft-intune.md).|
|**Perfil de email (Samsung KNOX Standard 4.0 e posterior)**|Criar, implantar e monitorar as configurações de email do Exchange ActiveSync nos dispositivos gerenciados. Isso permite que os usuários acessem o email corporativo nos dispositivos pessoais deles sem que precisem fazer nenhum tipo de configuração.<br /><br />Para ver mais detalhes, consulte [Configure access to corporate email using email profiles with Microsoft Intune (Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune)](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Configuração geral (Android 4 e posterior, Samsung KNOX Standard 4.0 e posterior)**|Configurar a segurança de dispositivo móvel e configurações funcionais.<br />Especifique os aplicativos que são compatíveis ou não, e reporte quando eles são usados.<br />Configure o modo de quiosque que bloqueia dispositivos para permitir que somente determinados recursos de trabalho, por exemplo, permitir que o dispositivo execute apenas um aplicativo ou desabilitar os botões de volume.<br /><br />Para ver mais detalhes, consulte [Android policy settings in Microsoft Intune (Configurações de política do Android no Microsoft Intune)](android-policy-settings-in-microsoft-intune.md).|
|**Perfil de certificado PKCS nº 12 (.PFX) (Android 4 e posterior)**|Use esse perfil para criar e implantar configurações PFX para solicitações de certificado do dispositivo.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de certificado SCEP (Android 4 e posterior)**|Configurar um certificado do protocolo SCEP que pode ser usado com um certificado confiável de dispositivos móveis para autenticar dispositivos móveis a fim de permitir que acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de certificado confiável (Android 4 e posterior)**|Configurar um certificado confiável de dispositivo móvel que pode ser usado para autenticar dispositivos móveis para permitir que eles acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de VPN (Android 4 e posterior)**|Configurar e implantar configurações que oferecem aos usuários acesso seguro à rede da empresa a partir de seus dispositivos móveis. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar ao seu trabalho para o usuário final.<br /><br />Para ver mais detalhes, consulte [VPN connections in Microsoft Intune.md (Conexões VPN no Microsoft Intune.md)](vpn-connections-in-microsoft-intune.md).|
|**Perfil de Wi-Fi (Android 4 e posterior)**|Configurar e implantar as configurações de rede sem fio para usuários em sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário final necessário para conectar-se à rede sem fio.<br /><br />Para ver mais detalhes, consulte [Wi-Fi connections in Microsoft Intune (Conexões Wi-Fi no Microsoft Intune)](wi-fi-connections-in-microsoft-intune.md).|

## Políticas de configuração de iOS

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Configuração personalizada (iOS 7.1 e posterior)**|Implante perfis de configuração para dispositivos iOS que você criou usando a ferramenta Apple Configurador. Isso é útil quando a configuração não está disponível em uma política de configuração.<br /><br />Para ver mais detalhes, consulte [iOS policy settings in Microsoft Intune (Configurações de política do iOS no Microsoft Intune)](ios-policy-settings-in-microsoft-intune.md).|
|**Perfil de email (iOS 7.1 e posterior)**|Criar, implantar e monitorar as configurações de email do Exchange ActiveSync nos dispositivos gerenciados. Isso permite que os usuários acessem o email corporativo nos dispositivos pessoais deles sem que precisem fazer nenhum tipo de configuração.<br /><br />Para ver mais detalhes, consulte [Configure access to corporate email using email profiles with Microsoft Intune (Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune)](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Configuração geral (iOS 7.1 e posterior)**|Configurar a segurança de dispositivo móvel e configurações funcionais.<br />-   Especificar os aplicativos que são compatíveis ou não, e reportar quando eles são usados.<br />Configure o modo de quiosque que bloqueia dispositivos para permitir que somente determinados recursos de trabalho, por exemplo, permitir que o dispositivo execute apenas um aplicativo ou desabilitar os botões de volume.<br /><br />Para ver mais detalhes, consulte [iOS policy settings in Microsoft Intune (Configurações de política do iOS no Microsoft Intune)](ios-policy-settings-in-microsoft-intune.md).|
|**Perfil de certificado SCEP (iOS 7.1 e posterior)**|Configurar um certificado do protocolo SCEP que pode ser usado com um certificado confiável de dispositivos móveis para autenticar dispositivos móveis a fim de permitir que acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de certificado confiável (iOS 7.1 e posterior)**|Configurar um certificado confiável de dispositivo móvel que pode ser usado para autenticar dispositivos móveis para permitir que eles acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de VPN (iOS 7.1 e posterior)**|Configurar e implantar configurações que oferecem aos usuários acesso seguro à rede da empresa a partir de seus dispositivos móveis. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar ao seu trabalho para o usuário final.<br /><br />Para ver mais detalhes, consulte [VPN connections in Microsoft Intune.md (Conexões VPN no Microsoft Intune.md)](vpn-connections-in-microsoft-intune.md).|
|**Perfil de Wi-Fi (iOS 7.1 e posterior)**|Configurar e implantar as configurações de rede sem fio para usuários em sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário final necessário para conectar-se à rede sem fio.<br /><br />Para ver mais detalhes, consulte [Wi-Fi connections in Microsoft Intune (Conexões Wi-Fi no Microsoft Intune)](wi-fi-connections-in-microsoft-intune.md).|
|**Política de configuração de aplicativo móvel (iOS 7.1 e posterior)**|Use políticas de configuração de aplicativo móvel para fornecer automaticamente as configurações que podem ser necessárias quando o usuário executa um aplicativo iOS.<br /><br />Para ver mais detalhes, consulte [Configure iOS apps with mobile app configuration policies in Microsoft Intune (Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune)](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).|

## Políticas de configuração do Mac OS X

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Configuração personalizada (Mac OS X 10.9 e posterior)**|Implante perfis de configuração para computadores Mac que você criou usando a ferramenta Apple Configurator. Isso é útil quando a configuração não está disponível em uma política de configuração.<br /><br />Para ver mais detalhes, consulte [Mac OS X policy settings in Microsoft Intune (Configurações de política do Mac OS X no Microsoft Intune)](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Configuração geral (Mac OS X 10.9 e posterior)**|Configurar a segurança de dispositivo móvel e configurações funcionais.<br />Especifique os aplicativos que são compatíveis ou não, e reporte quando eles são usados.<br /><br />Para ver mais detalhes, consulte [Mac OS X policy settings in Microsoft Intune (Configurações de política do Mac OS X no Microsoft Intune)](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Perfil de certificado SCEP (Mac OS X 10.9 e posterior)**|Configurar um certificado do protocolo SCEP que pode ser usado com um certificado confiável de dispositivos móveis para autenticar dispositivos móveis a fim de permitir que acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de certificado confiável (Mac OS X 10.9 e posterior)**|Configurar um certificado confiável de dispositivo móvel que pode ser usado para autenticar dispositivos móveis para permitir que eles acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de VPN (Mac OS X 10.9 e posterior)**|Configurar e implantar configurações que oferecem aos usuários acesso seguro à rede da empresa a partir de seus dispositivos móveis. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar ao seu trabalho para o usuário final.<br /><br />Para ver mais detalhes, consulte [VPN connections in Microsoft Intune.md (Conexões VPN no Microsoft Intune.md)](vpn-connections-in-microsoft-intune.md).|
|**Perfil de Wi-Fi (Mac OS X 10.9 e posterior)**|Configurar e implantar as configurações de rede sem fio para usuários em sua organização. Ao implantar essas configurações, você minimiza o esforço do usuário final necessário para conectar-se à rede sem fio.<br /><br />Para ver mais detalhes, consulte [Wi-Fi connections in Microsoft Intune (Conexões Wi-Fi no Microsoft Intune)](wi-fi-connections-in-microsoft-intune.md).|

## Políticas de configuração do Windows
Aplica-se apenas a Windows Phone e dispositivos com Windows.

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Configuração personalizada (Windows 10 Desktop e Mobile e posterior)**|Implante as configurações OMA-URI que podem ser usadas para controlar recursos do dispositivo. Isso é útil quando a configuração não está disponível em uma política de configuração.<br />    Para ver mais detalhes, consulte [Windows 10 policy settings in Microsoft Intune (Configurações de política do Windows 10 no Microsoft Intune)](windows-10-policy-settings-in-microsoft-intune.md).|
|**Configuração personalizada (Windows Phone 8.1 e posterior)**|Implante as configurações OMA-URI que podem ser usadas para controlar recursos do dispositivo. Isso é útil quando a configuração não está disponível em uma política de configuração.<br /><br />Para ver mais detalhes, consulte [Windows Phone 8.1 settings in Microsoft Intune (Configurações do Windows Phone 8.1 no Microsoft Intune)](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Política de Atualização de Edição (Windows 10 Desktop e posterior)**<br><br>**Política de Atualização de Edição (Windows 10 Holographic e posterior)**|Configurar e implantar políticas contendo informações de chave de licença ou chave do produto (Product Key) que são usadas para atualizar dispositivos Windows 10 para uma versão mais recente<br><br>Para detalhes, consulte [Edition upgrade policy settings in Microsoft Intune (Configurações da política de atualização de edição no Microsoft Intune)](edition-upgrade-policy-settings-in-microsoft-intune.md).|  
|**Perfil de email (Windows Phone 8 e posterior)**<br /><br />**Perfil de email (Windows 10 Desktop e Mobile e posterior)**|Criar, implantar e monitorar as configurações de email do Exchange ActiveSync nos dispositivos gerenciados. Isso permite que os usuários acessem o email corporativo nos dispositivos pessoais deles sem que precisem fazer nenhum tipo de configuração.<br /><br />Para ver mais detalhes, consulte [Configure access to corporate email using email profiles with Microsoft Intune (Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune)](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Configuração geral (Windows 10 Desktop e Mobile e posterior)**|Configure a segurança do dispositivo móvel e configurações funcionais para dispositivos Windows 10 Desktop e Mobile.<br /><br />Para ver mais detalhes, consulte [Windows 10 policy settings in Microsoft Intune (Configurações de política do Windows 10 no Microsoft Intune)](windows-10-policy-settings-in-microsoft-intune.md).|
|**Configuração geral (Windows 10 Team e posterior)**|Defina as configurações funcionais e de segurança do dispositivo para dispositivos registrados no Windows 10 Team (por exemplo, um dispositivo de Surface Hub).<br /><br />Para detalhes, consulte [Windows Team configuration policy settings in Microsoft Intune (Definições de política de configuração do Windows Team no Microsoft Intune)](windows-team-configuration-policy-settings-in-microsoft-intune.md).|
|**Configuração geral (Windows 8.1 e posterior)**|Configure a segurança do dispositivo móvel e configurações funcionais para dispositivos com Windows.<br /><br />Para ver mais detalhes, consulte [Windows policy settings in Microsoft Intune (Configurações de política do Windows no Microsoft Intune)](windows-configuration-policy-settings-in-microsoft-intune.md).|
|**Configuração geral (Windows Phone 8.1 e posterior)**|Configurar a segurança de dispositivo móvel e configurações funcionais.<br />Especificar os aplicativos que os usuários podem ou não usar e impedir que aplicativos incompatíveis sejam instalados ou usados.<br /><br />Para ver mais detalhes, consulte [Windows Phone 8.1 settings in Microsoft Intune (Configurações do Windows Phone 8.1 no Microsoft Intune)](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Perfil de certificado PKCS nº 12 (.PFX) (Windows 10 Desktop e Mobile e posterior)**|Use esse perfil para criar e implantar configurações PFX para solicitações de certificado do dispositivo.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de certificado SCEP (Windows 8.1 e posterior)**<br /><br />**Perfil de certificado SCEP (Windows Phone 8.1 e posterior)**|Configurar um certificado do protocolo SCEP que pode ser usado com um certificado confiável de dispositivos móveis para autenticar dispositivos móveis a fim de permitir que acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md).|
|**Perfil de certificado confiável (Windows 8.1 e posterior)**<br /><br />**Perfil de certificado confiável (Windows Phone 8.1 e posterior)**|Configurar um certificado confiável de dispositivo móvel que pode ser usado para autenticar dispositivos móveis para permitir que eles acessem recursos da rede, como aqueles configurados por Wi-Fi e perfis VPN.<br /><br />Para ver mais detalhes, consulte [Secure resource access with certificate profiles in Microsoft Intune (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune)](secure-resource-access-with-certificate-profiles.md)).|
|**Perfil da VPN (Windows 10 Desktop e Mobile e posterior)**<br /><br />**Perfil de VPN (Windows 8.1 e posterior)**<br /><br />**Perfil de VPN (Windows Phone 8.1 e posterior)**|Configurar e implantar configurações que oferecem aos usuários acesso seguro à rede da empresa a partir de seus dispositivos móveis. Ao implantar essas configurações, você minimiza o esforço necessário para se conectar ao seu trabalho para o usuário final.<br /><br />Para ver mais detalhes, consulte [VPN connections in Microsoft Intune.md (Conexões VPN no Microsoft Intune.md)](vpn-connections-in-microsoft-intune.md).|
|**Importação de Wi-Fi**|Importar e implantar configurações de Wi-Fi do Windows que você exportou anteriormente em um arquivo.<br /><br />Para ver mais detalhes, consulte [Wi-Fi connections in Microsoft Intune (Conexões Wi-Fi no Microsoft Intune)](wi-fi-connections-in-microsoft-intune.md).|

## Políticas de software

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Política de navegador gerenciado (Android 4 e posterior)**<br /><br />**Política de navegador gerenciado (iOS 7.1 e posterior)**|Especifique os sites que os usuários podem e que não podem acessar quando estiverem usando o aplicativo de navegador gerenciado.<br /><br />Para detalhes, consulte [Manage Internet access using managed browser policies with Microsoft Intune (Gerenciar o acesso à Internet usando políticas de navegador gerenciado com o Microsoft Intune)](manage-internet-access-using-managed-browser-policies.md).|
|**Política de gerenciamento de aplicativos móveis (Android 4 e posterior)**<br /><br />**Política de gerenciamento de aplicativo móvel (iOS 7.1 e posterior)**|Modificar a funcionalidade dos aplicativos que você implanta, para ajudar a colocá-los em linha com as políticas de conformidade e segurança da empresa. Por exemplo, você pode restringir as operações de recortar, copiar e colar em um aplicativo restrito, ou então configurar um aplicativo para abrir todos os links da web dentro do navegador gerenciado.<br /><br />Para detalhes, consulte [Configure and deploy mobile application management policies in the Microsoft Intune console (Configurar e implantar políticas de gerenciamento de aplicativo móvel no console do Microsoft Intune)](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)|

## Configurações comuns de dispositivo móvel

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Política do Exchange ActiveSync**|Configure a segurança do dispositivo móvel e configurações funcionais para dispositivos que são gerenciados pelo Exchange ActiveSync.<br /><br />Para detalhes, consulte [Exchange ActiveSync policy settings in Microsoft Intune (Configurações de política do Exchange ActiveSync no Microsoft Intune)](exchange-activesync-policy-settings-in-microsoft-intune.md).|
|**Política de segurança de dispositivo móvel**|<ul><li>Configura as configurações para dispositivos móveis (todas as plataformas), incluindo:<br /><br /><ul><li>Segurança </li><li>Criptografia</li><li>Sistema</li><li>Email</li><li>Aplicativos</li></ul></li></ul> **Importante:** o Microsoft Intune agora tem **políticas de configuração** separadas para cada plataforma de dispositivo e essas políticas contêm as configurações mais recentes que você pode usar. Você pode continuar a usar a política de segurança de dispositivo móvel e todas as implantações existentes continuarão funcionando, mas você deve planejar a migração para as novas políticas de configuração assim que possível.<br />Para detalhes, consulte [Mobile device security policy settings in Microsoft Intune (Configurações de política de segurança de dispositivo móvel no Microsoft Intune)](mobile-device-security-policy-settings-in-microsoft-intune.md).|

## Políticas de conformidade e acesso condicionais

### Acesso condicional

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Política do Exchange Online**<br /><br />**Política local do Exchange**|Gerenciar o acesso ao email do Microsoft Exchange por dispositivos que não são gerenciados pelo Intune ou que não são compatíveis com uma política de conformidade que você criou.<br /><br />Para ver mais detalhes, consulte [Restrict email access to Exchange Online and new Exchange Online Dedicated environment with Intune (Restringir acesso a email ao Exchange Online e ao novo ambiente do Exchange Online Dedicado com o Intune)](restrict-access-to-exchange-online-with-microsoft-intune.md).|
|**Política do SharePoint Online**|Gerenciar o acesso ao SharePoint Online de dispositivos que não são gerenciados pelo Intune ou que não são compatíveis com uma política de conformidade que você criou.<br /><br />Para ver mais detalhes, consulte [Restrict access to SharePoint Online with Microsoft Intune (Restringir o acesso ao SharePoint Online com o Microsoft Intune)](restrict-access-to-sharepoint-online-with-microsoft-intune.md).|
|**Skype for Business**|Gerenciar o acesso ao Skype for Business de dispositivos que não são gerenciados pelo Intune ou que não são compatíveis com uma política de conformidade que você criou.<br /><br />Para ver mais detalhes, consulte [Restrict access to Skype for Business with Microsoft Intune (Restringir o acesso ao Skype for Business com o Microsoft Intune)](restrict-access-to-skype-for-business-online-with-microsoft-intune.md).|
> [!NOTE]
> Você não pode implantar políticas de acesso condicional a usuários e dispositivos. Em vez disso, configure a política necessária e ela se aplica a todos os grupos de destino na política.

### Políticas de conformidade

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Políticas de conformidade**|Defina o nível de conformidade para os dispositivos e, em seguida, reporte sobre os dispositivos que não forem compatíveis. Essas políticas são usadas com acesso condicional para ajudar a avaliar os dispositivos que devem ser bloqueados dos serviços.<br /><br />Para ver mais detalhes, consulte [Device compliance policies in Microsoft Intune (Políticas de conformidade do dispositivo no Microsoft Intune)](introduction-to-device-compliance-policies-in-microsoft-intune.md).|

## Gerenciamento de computador Windows

|Nome da política|Use quando desejar|
|---------------|------------------------|
|**Configurações do agente do Microsoft Intune**|Configure o cliente do computador do Intune no computador, incluindo configurações para:<br /><br />-   Endpoint Protection<br />-   Atualizações de software<br />-   Agenda de verificação de política<br /><br />Esse tipo de política pode ser implantado somente para grupos de dispositivos.<br /><br />Os clientes do Intune baixam políticas novas e atualizadas de acordo com a configuração **Frequência de detecção de aplicativos e atualização**, cujo valor padrão é 8 horas. No entanto, você pode forçar uma atualização de política a qualquer momento nos computadores.<br /><br />Para ver mais detalhes, consulte [Keep Windows PCs up to date with software updates in Microsoft Intune (Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune)](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Configurações do Microsoft Intune Center**|Configure os detalhes exibidos na central do Microsoft Intune nos computadores gerenciados.<br /><br />Esse tipo de política pode ser implantado somente para grupos de dispositivos.<br /><br />Para detalhes, consulte [Common Windows PC management tasks with the Microsoft Intune computer client (Tarefas comuns de gerenciamento de computadores Windows com o cliente de computador do Microsoft Intune)](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).|
|**Configurações do Firewall do Windows**|Define as configurações do Firewall do Windows e as exceções para comunicações de rede comuns em computadores, incluindo:<br /><br />-   BranchCache<br />-   Assistência Remota<br />-   Compartilhamento de mídia<br /><br />Esse tipo de política pode ser implantado somente para grupos de dispositivos.<br /><br />Para ver mais detalhes, consulte [Help secure Windows PCs with Endpoint Protection for Microsoft Intune (Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune)](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).|

### Consulte também

[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


