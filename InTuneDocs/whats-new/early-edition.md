---
title: "A Edição Antecipada | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>A Edição Antecipada do Microsoft Intune – janeiro

A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
> As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="actions-for-non-compliance---730266--"></a>Medidas para não conformidade <!--730266-->
_Ações de não conformidade_ é um novo recurso das políticas de conformidade que permite tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Relatórios no console para MAM sem registro <!--677961-->
Novos relatórios de proteção do aplicativo foram adicionados para dispositivos registrados e não registrados. Saiba mais sobre como é possível [monitorar as políticas de gerenciamento de aplicativo móvel com o Intune aqui](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>Configurar o acesso condicional para o MAM com o SharePoint Online <!--679339-->
Você pode impedir que os aplicativos sem suporte das políticas de gerenciamento do aplicativo móvel do Intune (MAM) acessem o SharePoint Online.  Você pode começar usando o gerenciamento de aplicativo móvel do Intune no portal do Azure. Procure a seção __Acesso Condicional__ na folha __Configurações__ que inclui a opção para o SharePoint Online. Este recurso será enviado separadamente do restante da versão de serviço. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Suporte do Android 7.1.1 <!--694397-->
O Intune agora dá suporte completo e gerencia o Android 7.1.1.

## <a name="notices"></a>Avisos

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador.

O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Portal da Empresa para links do iOS abertos no aplicativo <!--665954-->
Os links dentro do aplicativo Portal da Empresa para iOS, incluindo os links para a documentação e os aplicativos, serão abertos diretamente no aplicativo Portal da Empresa usando uma exibição no aplicativo do Safari. Essa atualização será fornecida separadamente da atualização de serviço em janeiro.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Melhorando o suporte de gerenciamento de aplicativo móvel para o apagamento seletivo <!--581242-->
Os usuários finais receberão outras diretrizes sobre como recuperar o acesso a dados corporativos ou de estudante se esses dados forem removidos automaticamente devido à política “Intervalo offline antes do apagamento dos dados de aplicativo”.<!--, or the removal of the Intune Company Portal on Android.-->

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

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Barra de progresso ao iniciar o Portal da Empresa no iOS <!--665978-->
O Portal da Empresa para iOS introduziu uma barra de progresso na tela de inicialização para fornecer ao usuário informações sobre os processos de carregamento ocorridos. Haverá uma distribuição em fases da barra de progresso para substituição do controle giratório. Isso significa que alguns dos usuários verão a nova barra de progresso enquanto outros continuarão vendo o controle giratório.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Visualização pública da nova experiência do administrador do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Em caso de dúvidas sobre a linha do tempo para a migração do locatário, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="january-2017"></a>Janeiro de 2017

#### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748803-->
Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="december-2016"></a>Dezembro de 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integração de gerenciamento de despesas de telecomunicações na visualização pública do portal do Azure<!--747605-->
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.



<!--HONumber=Dec16_HO4-->


