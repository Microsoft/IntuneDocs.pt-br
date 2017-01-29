---
title: Novidades | Microsoft Docs
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3ab53e40f4b7ea67733127f445005ecb77a404f7
ms.openlocfilehash: 37031eed6efa48ff52ec37a942fa77af414f78fe


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Novidades do Microsoft Intune – janeiro de 2017
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

> [!Note]
> Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Relatórios no console para MAM sem registro <!--677961-->
Novos relatórios de proteção do aplicativo foram adicionados para dispositivos registrados e não registrados. Saiba mais sobre como é possível [monitorar as políticas de gerenciamento de aplicativo móvel com o Intune aqui](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Suporte do Android 7.1.1 <!--694397-->
O Intune agora dá suporte completo e gerencia o Android 7.1.1.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Resolver o problema em que os dispositivos iOS estão inativos ou o console do administrador não consegue se comunicar com eles <!--unknown-->
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Avisos

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador.

O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Melhorando o suporte de gerenciamento de aplicativo móvel para o apagamento seletivo <!--581242-->
Os usuários finais receberão outras diretrizes sobre como recuperar o acesso a dados corporativos ou de estudante se esses dados forem removidos automaticamente devido à política “Intervalo offline antes do apagamento dos dados de aplicativo”.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizando o site Portal da Empresa <!--753980-->
A partir de fevereiro, o site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu de hambúrguer", ![menu de hambúrguer do site Portal da Empresa](../media/CP_hamburger_menu.png) contendo detalhes de contato de suporte técnico e informações sobre os dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente. Você pode encontrar imagens de antes e depois disponíveis na [página Novidades na interface do usuário do Portal da Empresa](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017).

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nova documentação para as políticas de proteção do aplicativo <!--583398-->
Atualizamos nossa documentação para os administradores e desenvolvedores de aplicativo que desejam habilitar políticas de proteção do aplicativo (conhecidas como políticas de MAM) em aplicativos iOS e Android usando a Ferramenta de Disposição do Aplicativo do Intune ou o SDK do Aplicativo do Intune.

Os seguintes artigos foram atualizados:

* [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Introdução ao SDK do Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Os seguintes artigos são novas adições à biblioteca de documentos:

* [Plug-in Cordova do SDK de Aplicativo do Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Componente Xamarin do SDK de Aplicativo do Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Novidades na visualização pública da experiência de administração do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Em caso de dúvidas sobre a linha do tempo para a migração do locatário, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Você pode encontrar as novidades na visualização do Intune no Azure [aqui](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na visualização do Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Novidades na interface do usuário do Portal da Empresa](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Arquivo de novidades](whats-new-archive.md)



<!--HONumber=Jan17_HO4-->


