---
title: Novidades | Microsoft Docs
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: b3cf8d8f60482be2d4d903d1b2c00c1a3a392b73
ms.lasthandoff: 04/20/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Novidades no Microsoft Intune - abril de 2017
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

> [!Note]
> Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123-->

Estamos aperfeiçoando a experiência de início de sessão nos aplicativos do Portal da Empresa Intune para Android, iOS e Windows. A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração. Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único. Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.

Confira capturas de tela da experiência de entrada anterior, a nova experiência de entrada com as credenciais e a nova experiência de entrada através de outro dispositivo na página [Novidades na interface de usuário do aplicativo](whats-new-in-intune-app-ui.md).

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps disponível para o navegador gerenciado <!--822308, 822303-->

Microsoft MyApps agora tem um suporte melhor dentro do navegador gerenciado. Usuários do navegador gerenciado que não são direcionados ao gerenciamento serão levados diretamente ao serviço MyApps, no qual podem acessar seus aplicativos SaaS provisionados pelo administrador. Usuários que são direcionados ao gerenciamento do Intune ainda poderão acessar MyApps no indicador interno do navegador gerenciado.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Novos ícones para o navegador gerenciado e o Portal da empresa <!--918433, 918431, 971473-->

O navegador gerenciado está recebendo ícones atualizados para versões de Android e iOS do aplicativo. O novo ícone conterá o selo do Intune atualizado para torná-lo mais consistente com outros aplicativos no Enterprise Mobility + Security (EM + S). Você pode ver o ícone novo para o Navegador Gerenciado na [página Novidades de interface do usuário do aplicativo Intune](whats-new-in-intune-app-ui.md).

O Portal da empresa também está recebendo ícones atualizados para as versões do Windows, iOS e Android do aplicativo para aprimorar a consistência com outros aplicativos EM + S. Esses ícones serão liberados gradualmente em plataformas a partir de abril até o fim de maio.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicador de progresso de conexão no Portal da empresa Android <!--953374-->

Uma atualização para o aplicativo de Portal da empresa Android mostra um indicador de progresso de conexão quando o usuário inicia ou reinicia o aplicativo. O indicador avança por novos status, começando com "Conectando…", "Fazendo logon..." e "Verificando os requisitos de segurança..." antes de permitir que o usuário acesse o aplicativo. Você pode ver as novas telas do aplicativo do Portal da Empresa para Android na [página Novidades de interface do usuário do aplicativo Intune](whats-new-in-intune-app-ui.md).

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Bloquear o acesso dos aplicativos ao SharePoint Online<!-- 679339 -->

Agora você pode criar uma política de acesso condicional baseada no aplicativo para bloquear aplicativos, que não têm políticas de proteção de aplicativo aplicadas a elas acessando [SharePoint Online](/InTune/deploy-use/mam-ca-for-sharepoint-online). No cenário de acesso condicional baseado em aplicativos, você pode especificar os aplicativos os quais deseja conceder acesso ao SharePoint Online usando o Portal do Azure.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->

Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](/intune/deploy-use/bulk-enroll-windows) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte no momento para cenários de autoatendimento e de Portal da empresa.

## <a name="notices"></a>Avisos

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->

Para contas do Intune criadas depois de janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho de registrar dispositivos na Versão Prévia do Portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Quais são as novidades para Appx do Intune no Azure <!-- 1000270 -->

Como parte da migração para o Intune no Azure, estamos fazendo três alterações de appx:

1. Adição de um novo tipo de aplicativo appx no console clássico do Intune que somente pode ser implantado em dispositivos registrados MDM.
2. Adaptação do tipo de aplicativo appx existente para ser direcionado somente para computadores gerenciados por meio do agente Intune PC.
3. Conversão de todos os appxs existentes em appxs MDM com a migração.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?

Isso não afetará nenhuma de suas implantações existentes para dispositivos que são gerenciados por meio do agente Intune PC. No entanto, após a migração, você não poderá implantar esses appxs migrados nos novos dispositivos que são gerenciados por meio do agente Intune PC que não foram anteriormente direcionados.

#### <a name="what-action-do-i-need-to-take"></a>O que preciso fazer

Após a migração, você precisará recarregar o appx novamente como um appx de PC se quiser fazer novas implantações de PC. Para obter mais informações, consulte [Alterações de appx no Intune no Azure](https://aka.ms/appxchange) no blog da equipe de suporte do Intune.  


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Novidades na visualização pública da experiência de administração do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](/intune-azure/introduction/whats-new).

> [!Note]
> Para a visualização do portal do Azure, estamos implantando atualizações este mês. No entanto, as alterações podem não estar disponíveis imediatamente devido a como o serviço do Intune é distribuído.  Vários componentes do serviço devem ser atualizados em sequência antes dos novos recursos do portal ficarem disponíveis. Procure alterações na visualização do portal do Azure na distribuição posterior deste mês. Para obter uma lista completa de alterações, consulte [O que há de novo na visualização do Microsoft Intune](/intune-azure/introduction/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Funções de administração que estão sendo substituídas no Portal do Azure

As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure. Após a migração para o Portal do Azure, será necessário atribuir novamente essas novas funções de administração aos seus administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>O que está por vir

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na visualização do Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Novidades na interface do usuário do Portal da Empresa](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Arquivo de novidades](whats-new-archive.md)

