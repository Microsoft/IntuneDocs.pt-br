---
title: Novidades | Microsoft Intune
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Novidades do Microsoft Intune – Outubro 2016
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/library/mt718155.aspx) (Novidades do Híbrido).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Novidades

### Acesso condicional para gerenciamento de aplicativos móveis
Você poderá restringir o acesso ao Exchange Online somente para aplicativos que deem suporte a políticas de gerenciamento de aplicativos móveis do Intune, como o Outlook. [Esse novo recurso](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) combina perfeitamente com as políticas de MAM (gerenciamento de aplicativo móvel) do Intune, porque você pode bloquear o acesso a clientes de email interno ou outros aplicativos que não foram configurados com as políticas de MAM do Intune. Isso garante que os usuários estão acessando os dados da sua organização com aplicativos que podem ser protegidos usando o MAM do Intune. Você pode começar no gerenciamento de aplicativo móvel do Intune pelo portal do Azure. Procure a nova seção de Acesso Condicional na folha "Configurações".

### Acesso condicional para computadores Windows
Agora é possível criar políticas de acesso condicional por meio do console de administrador do Intune para impedir que computadores Windows acessem o [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) e o [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Você também pode criar políticas de acesso condicional para bloquear o acesso aos aplicativos da área de trabalho e universais do Office.

### Suporte do Android for Work
O Intune agora faz parte do programa Android for Work. Começaremos a distribuir suporte para recursos do Android for Work para o Intune a partir deste mês.
[Leia o comunicado da Microsoft sobre o suporte do Intune para o Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Os tópicos sobre o Intune a seguir são novos ou foram atualizados com informações sobre o Android for Work:

Para profissionais de TI:
- [Configurar o Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Restringir acesso a email ao Exchange Online e ao novo Exchange Online Dedicado com o Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restringir acesso a email ao Exchange local e Exchange Online Dedicado herdado com o Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Configurações da política de conformidade do Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Como implantar aplicativos Android for Work](/intune/deploy-use/android-for-work-apps)
- [Configurar aplicativos Android for Work com as políticas de configuração de aplicativo móvel](/intune/deploy-use/afw-app-configuration-policy)
- [Configurações de política do Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Para usuários finais:
- [O que acontece quando você cria um perfil de trabalho](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Criar um perfil de trabalho e registrar seu dispositivo no Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Integração ao Lookout para proteger dispositivos iOS
A Microsoft está se integrando à solução de proteção contra ameaças a dispositivos móveis do Lookout para proteger dispositivos móveis iOS detectando neles a presença de malware, aplicativos arriscados e muito mais. A solução do Lookout ajuda você a determinar o nível de ameaça, que é configurável. Você pode criar uma regra de política de conformidade do Intune para determinar a conformidade do dispositivo com base na avaliação de riscos pelo Lookout. Usando políticas de acesso condicional, você pode permitir ou bloquear o acesso aos recursos da empresa com base no status de conformidade do dispositivo.

Os usuários finais de dispositivos iOS não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em seus dispositivos, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso a dados corporativos. Saiba como [Configurar e implantar aplicativos Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Ferramenta de Encapsulamento de Aplicativos do Intune para Android
Você pode habilitar seus aplicativos para usar políticas de MAM (gerenciamento de aplicativo móvel) do Intune usando a Ferramenta de Encapsulamento de Aplicativos do Intune. O suporte para políticas de MAM do Intune sem a necessidade de registro do dispositivo está disponível.

### Gerenciar a impressão por meio de aplicativos gerenciados usando políticas MAM
Agora você pode evitar a impressão de dados da empresa por meio de aplicativos que têm políticas MAM. Essa configuração está disponível no [portal do Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) e tem suporte tanto em dispositivos [iOS](/Intune/deploy-use/ios-mam-policy-settings) quanto [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

## Avisos

### Compatibilidade do Samsung KNOX Android com o Intune
Alguns modelos do telefone Samsung Galaxy Ace não podem ser gerenciados pelo Intune como dispositivos Samsung KNOX. Em vez disso, quando você registrá-los com o Intune, eles serão gerenciados como dispositivos Android padrão.

Os números de modelo afetados são:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Você e seus usuários finais não precisam executar nenhuma ação adicional. Para obter mais informações, visite o site do [Samsung KNOX](https://www.samsungknox.com).

### O aplicativo de Portal da Empresa para o Windows 8 é preterido; o suporte para as plataformas Windows Phone 8 e Windows RT está sendo preterido
A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para o Portal da Empresa do Windows 8. O Microsoft Intune também preterirá o suporte para as plataformas Windows Phone 8 e Windows RT. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8 ou Windows RT.

Você pode continuar a gerenciar dispositivos Windows Phone 8, Windows RT e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.

A partir de novembro de 2016, o suporte para o Portal de Empresa do Windows Phone 8 será preterido.
<!--TFS 1255391-->

## O que está por vir

### Novo Portal da Empresa do Microsoft Intune, disponível para dispositivos Windows 10
A Microsoft está lançando um novo Portal da Empresa do Microsoft Intune para dispositivos Windows 10. Esse aplicativo, que aproveita o novo formato do Windows 10 Universal, fornecerá ao usuário uma experiência de usuário atualizada dentro do aplicativo e experiências idênticas em todos os dispositivos Windows 10, sejam eles PCs ou dispositivos móveis, habilitando ainda todas as mesmas funcionalidades que eles estão usando atualmente.

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa do Windows 8.1 e do Portal da Empresa do Windows Phone 8.1 da Windows Store. Para obter mais detalhes, acesse [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roteiro da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Versões anteriores do Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


