---
title: "A edição antecipada | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Quais são as novidades no Microsoft Intune – outubro
A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Confira se há novas atualizações em Quais São as Novidades.

As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).

### Gerenciar a impressão por meio de aplicativos gerenciados usando políticas MAM
Agora você pode evitar a impressão de dados da empresa por meio de aplicativos que têm políticas MAM. Essa configuração está disponível no [portal do Azure](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) e tem suporte tanto em dispositivos [iOS](..deployuse/ios-mam-policy-settings) quanto [Android](..deployuse/android-mam-policy-settings).
<!--TFS 1014328-->

### Novo Portal da Empresa do Microsoft Intune, disponível para dispositivos Windows 10
A Microsoft está lançando um novo Portal da Empresa do Microsoft Intune para dispositivos Windows 10. Esse aplicativo, que aproveita o novo formato do Windows 10 Universal, fornecerá ao usuário uma experiência de usuário atualizada dentro do aplicativo e experiências idênticas em todos os dispositivos Windows 10, sejam eles PCs ou dispositivos móveis, habilitando ainda todas as mesmas funcionalidades que eles estão usando atualmente.

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa do Windows 8.1 e do Portal da Empresa do Windows Phone 8.1 da Windows Store.
<!--TFS 1016502-->

### Suporte do Android for Work

O Intune está agora faz parte do [programa Android for Work](https://enterprise.google.com/android/partners/). Começaremos a distribuir suporte para recursos do Android for Work para o Intune a partir deste mês.

[Leia o comunicado da Microsoft sobre o suporte do Intune para o Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Compatibilidade do Samsung KNOX Android com o Intune

Alguns modelos do telefone Samsung Galaxy Ace não podem ser gerenciados pelo Intune como dispositivos Samsung KNOX. Em vez disso, quando você registrá-los com o Intune, eles serão gerenciados como dispositivos Android padrão.
Os números de modelo afetados são:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Você e seus usuários finais não precisam executar nenhuma ação adicional.
Para obter mais informações, visite o site do [Samsung KNOX](https://www.samsungknox.com).

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### O aplicativo de Portal da Empresa para o Windows 8 é preterido; o suporte para as plataformas Windows Phone 8 e Windows RT está sendo preterido
A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para o Portal da Empresa do Windows 8. O Microsoft Intune também preterirá o suporte para as plataformas Windows Phone 8 e Windows RT. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8 ou Windows RT.

Você pode continuar a gerenciar dispositivos Windows Phone 8, Windows RT e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.

A partir de novembro de 2016, o suporte para o Portal de Empresa do Windows Phone 8 será preterido.
<!--TFS 1255391-->

### Acesso condicional para gerenciamento de aplicativos móveis
Agora é possível criar uma política de acesso condicional para impedir que aplicativos móveis não gerenciados acessem o [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) e o [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). Você pode bloquear os aplicativos e clientes de email internos que não são habilitados para MAM com o SDK de Aplicativo do Intune.  Isso pode ser feito criando uma política de acesso condicional e especificando os aplicativos que você deseja que tenham acesso ao Exchange Online e ao SharePoint Online usando o portal do Azure.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Integração ao Lookout para proteger dispositivos iOS
A Microsoft está se integrando à solução de proteção contra ameaças a dispositivos móveis do Lookout para proteger dispositivos móveis iOS detectando neles a presença de malware, aplicativos arriscados e muito mais. A solução do Lookout ajuda você a determinar o nível de ameaça, que é configurável. Você pode criar uma regra de política de conformidade do Intune para determinar a conformidade do dispositivo com base na avaliação de riscos pelo Lookout. Usando políticas de acesso condicional, você pode permitir ou bloquear o acesso aos recursos da empresa com base no status de conformidade do dispositivo.

Os usuários finais de dispositivos iOS não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em seus dispositivos, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso a dados corporativos.
<!--TFS 1319493-->

### Ferramenta de Encapsulamento de Aplicativos e SDK de Aplicativo do Intune para Android
Você pode habilitar seus aplicativos para usar políticas de MAM (gerenciamento de aplicativo móvel) do Intune usando a Ferramenta de Encapsulamento de Aplicativos do Intune ou o SDK de Aplicativo do Intune. Novas atualizações para a Ferramenta de Encapsulamento de Aplicativos e o SDK incluirão:

* Suporte para Android N
* Suporte para políticas de MAM do Intune sem a necessidade de registro do dispositivo
* Suporte para aplicativos Android com base em Xamarin

Você pode testar o MAM sem suporte a Xamarin e registro de dispositivo na visualização pública da Ferramenta de Encapsulamento de Aplicativos Android aqui: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.



<!--HONumber=Oct16_HO1-->


