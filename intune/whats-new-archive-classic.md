---
title: Novidades no arquivo do portal clássico do Microsoft Intune
description: Arquivado de comunicados de novidades do Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/08/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a5186af2e02363d74f2f046188168efd38eee363
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55843418"
---
# <a name="whats-new-in-the-intune-classic-portal---previous-months"></a>Novidades do Portal Clássico do Intune – meses anteriores

[!INCLUDE [classic-portal](./includes/classic-portal.md)]

Esta página lista os novos recursos e avisos já anunciados na [página de novidades](whats-new.md) do Portal Clássico do Intune.

## <a name="april-2017"></a>Abril de 2017

### <a name="new-capabilities"></a>Novos recursos

#### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps disponível para o navegador gerenciado <!--822308, 822303-->

Microsoft MyApps agora tem um suporte melhor dentro do navegador gerenciado. Os usuários do Navegador Gerenciado que não são destinados ao gerenciamento serão levados diretamente para o serviço MyApps, onde poderão acessar seus aplicativos SaaS provisionados pelo administrador. Usuários que são direcionados ao gerenciamento do Intune ainda poderão acessar MyApps no indicador interno do navegador gerenciado.

#### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Novos ícones para o navegador gerenciado e o Portal da empresa <!--918433, 918431, 971473-->

O navegador gerenciado está recebendo ícones atualizados para versões de Android e iOS do aplicativo. O novo ícone conterá o emblema Intune atualizado para torná-lo mais consistente com outros aplicativos no Enterprise Mobility + Security (EM+S). Você pode ver o ícone novo para o Navegador Gerenciado nas [novidades na página de IU do aplicativo Intune](whats-new-app-ui.md).

O Portal da Empresa também está recebendo ícones atualizados para as versões do Android, iOS e Windows do aplicativo para aprimorar a consistência com outros aplicativos EM+S. Esses ícones serão liberados gradualmente em plataformas a partir de abril até o fim de maio.

#### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicador de progresso de entrada no Portal da Empresa Android <!--953374-->

Uma atualização para o aplicativo de Portal da empresa Android mostra um indicador de progresso de conexão quando o usuário inicia ou reinicia o aplicativo. O indicador avança em novos status, começando com "Conectando …", então, "Entrando..." e "Verificando os requisitos de segurança..." antes de permitir que o usuário acesse o aplicativo. Você pode ver as novas telas do aplicativo do Portal da Empresa para Android na [página Novidades de interface do usuário do aplicativo Intune](whats-new-app-ui.md).

#### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Bloquear o acesso dos aplicativos ao SharePoint Online<!-- 679339 -->

Agora você pode criar uma política de acesso condicional baseada no aplicativo para bloquear aplicativos, que não têm políticas de proteção de aplicativo aplicadas a elas acessando [SharePoint Online](app-based-conditional-access-intune-create.md). No cenário de acesso condicional baseado em aplicativos, você pode especificar os aplicativos os quais deseja conceder acesso ao SharePoint Online usando o Portal do Azure.

#### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Suporte de logon único do Portal da empresa para iOS com o Outlook para iOS <!--834012-->
Os usuários não precisam mais entrar no aplicativo do Outlook se estiverem conectados no aplicativo de Portal da empresa para iOS no mesmo dispositivo com a mesma conta. Quando os usuários iniciarem o aplicativo do Outlook, eles poderão selecionar sua conta e se conectar automaticamente. Também estamos trabalhando para adicionar essa funcionalidade para outros aplicativos da Microsoft.

#### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Status do sistema de mensagens aprimorado no aplicativo do Portal da empresa para iOS <!--744866-->
Mensagens de erro novas e mais específicas agora serão exibidas no aplicativo do Portal da empresa para iOS para fornecer informações mais acessíveis sobre o que está acontecendo nos dispositivos. Esses casos de erro foram anteriormente incluídos em uma mensagem de erro geral intitulada "Portal da empresa temporariamente indisponível". Além disso, se um usuário inicia o Portal da empresa no iOS quando não tem uma conexão de Internet, ele agora verá uma barra de status permanente na home page não dizendo "Nenhuma Conexão de Internet."

#### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Status de instalação do aplicativo aprimorado para o aplicativo de Portal da empresa do Windows 10 <!--676495-->

As novas melhorias para instalação de aplicativos iniciadas no aplicativo Portal da Empresa para Windows 10 incluem:
-   Relatório de progresso da instalação mais rápido para pacotes MSI
-   Relatório de progresso da instalação mais rápido para aplicativos modernos em dispositivos com a Atualização de Aniversário do Windows 10 e versões posteriores
-   Nova barra de progresso para a instalação de aplicativos modernos em dispositivos com a Atualização de Aniversário do Windows 10 e versões posteriores

Você pode ver a nova barra de progresso na [página Novidades sobre a interface do usuário do aplicativo Intune](whats-new-app-ui.md).

#### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->

Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte no momento para cenários de autoatendimento e de Portal da empresa.

### <a name="whats-new-in-the-public-preview-of-intune-in-the-azure-portal--736542--"></a>Novidades na visualização pública do Intune no Portal do Azure<!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](whats-new.md).

Você pode encontrar as novidades na visualização do Intune no Azure [aqui](whats-new.md).

### <a name="notices"></a>Avisos

#### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->

Para contas do Intune criadas depois de janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho de registrar dispositivos na Versão Prévia do Portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal do Azure. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.

#### <a name="whats-coming-for-appx-in-intune-in-the-azure-portal----1000270---"></a>Quais são as novidades para Appx no Intune no Portal do Azure <!-- 1000270 -->

Como parte da migração para o Intune no Portal do Azure, estamos fazendo três alterações de appx:

1. Adição de um novo tipo de aplicativo appx no console do Intune que somente pode ser implantado em dispositivos registrados MDM.
2. Adaptação do tipo de aplicativo appx existente para ser direcionado somente para computadores gerenciados por meio do agente Intune PC.
3. Conversão de todos os appxs existentes em appxs MDM com a migração.

##### <a name="how-does-this-affect-me"></a>Como isso me afeta?

Isso não afetará nenhuma de suas implantações existentes para dispositivos que são gerenciados por meio do agente Intune PC. No entanto, após a migração, você não poderá implantar esses appxs migrados nos novos dispositivos que são gerenciados por meio do agente Intune PC que não foram anteriormente direcionados.

##### <a name="what-action-do-i-need-to-take"></a>O que preciso fazer

Após a migração, você precisará recarregar o appx novamente como um appx de PC se quiser fazer novas implantações de PC. Para saber mais, veja [Alterações de appx no Intune no Portal do Azure](https://aka.ms/appxchange) no blog da equipe de suporte do Intune.  

#### <a name="administration-roles-being-replaced-in-azure-portal"></a>Funções de administração que estão sendo substituídas no Portal do Azure

As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente Leitura) usadas no portal clássico do Intune (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (controles de administração baseados em função) no portal do Azure do Intune. Após a migração para o Portal do Azure, será necessário atribuir novamente essas novas funções de administração aos seus administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](role-based-access-control.md).

### <a name="whats-coming"></a>O que está por vir

#### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123-->

Anunciamos uma alteração que entrará em vigor nos próximos meses, que visa melhorar a experiência de entrada para os aplicativos do Portal da Empresa do Intune para Android, iOS e Windows. A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração. Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único. Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.

Encontre capturas de tela da experiência de entrada anterior, da nova experiência de entrada com credenciais e da nova experiência de entrada em outro dispositivo na página [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

#### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planejar mudanças: o Intune está mudando a experiência do Portal do Parceiro <!-- 1050016 -->

Vamos remover a página do Parceiro do Microsoft Intune em manage.microsoft.com, a partir da atualização do serviço em meados de maio de 2017.  

Se você for um administrador de parceiro, não será mais possível exibir conteúdo e tomar medidas em nome de seus clientes na página de Parceiro do Microsoft Intune. Em vez disso, deverá entrar em um dos outros Portais de Parceiro da Microsoft.

O [Microsoft Partner Center](https://partnercenter.microsoft.com/) e o [Centro de administração do parceiro do Office 365](https://portal.office.com/) permitem entrar nas contas de clientes que você gerencia. Avançando como parceiro, use um desse sites para gerenciar os clientes.


#### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS.

Disponibilizamos uma versão do aplicativo Portal da Empresa para iOS por meio do programa TestFlight da Apple, que impõe os novos requisitos de ATS. Se quiser experimentá-lo a fim de testar a conformidade com a ATS, envie um email para <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> informando seu nome e sobrenome, endereço de email e nome da empresa. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

## <a name="march-2017"></a>Março de 2017

### <a name="new-capabilities"></a>Novos recursos

#### <a name="support-for-skycure"></a>Suporte para Skycure

Agora, é possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:

- Defesa física
- Defesa de rede
- Defesa do aplicativo
- Defesa de vulnerabilidades

É possível configurar políticas de acesso condicional de EMS com base na avaliação de risco do Symantec Endpoint Protection Mobile (Skycure) habilitada por meio das políticas de conformidade de dispositivo do Intune. Use essas políticas para permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base em ameaças detectadas. Para saber mais, confira [Conector do Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->

O aplicativo Portal da Empresa para Android atualizará sua interface do usuário para uma aparência mais moderna e melhor experiência do usuário. As atualizações importantes são:

- Cores: os cabeçalhos da guia Portal da Empresa estão coloridos na identidade visual definida pela TI.
- Aplicativos: na guia **Aplicativos**, os botões **Aplicativos em destaque** e **Todos os aplicativos** foram atualizados.
- Pesquisa: na guia **Aplicativos**, o botão **Pesquisa** é um botão de ação flutuante.
- Aplicativos de navegação: a exibição **Todos os aplicativos** mostra uma exibição com as guias **Em destaque**, **Todos** e **Categorias** para facilitar a navegação.
- Suporte: as guias **Meus dispositivos** e **Entrar em contato com a TI** foram atualizadas para melhorar a legibilidade.

Para obter mais detalhes sobre essas alterações, consulte [Atualizações da IU para aplicativos do usuário final do Intune](whats-new-app-ui.md).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->

Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Assinatura do Script para o Portal da Empresa do Windows 10<!--941642-->

Se você precisar baixar e carregar o aplicativo Portal da Empresa do Windows 10, agora poderá usar um script para simplificar e facilitar o processo de autenticação do aplicativo para sua organização.   Para baixar o script e suas instruções de uso, consulte [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Script de assinatura do Microsoft Intune para o Portal da Empresa do Windows 10) na Galeria do TechNet. Para obter mais detalhes sobre este lançamento, confira [Atualizar seu aplicativo do Portal da Empresa do Windows 10](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) no Blog da Equipe de Suporte do Intune.


### <a name="notices"></a>Avisos

#### <a name="support-for-ios-103"></a>Suporte para iOS 10.3

A versão do iOS 10.3 começou a ser distribuída em 27 de março de 2017 para os usuários de iOS. Todos os cenários existentes do Intune MDM e MAM são compatíveis com a versão mais recente do sistema operacional Apple. Antecipamos que todas as funcionalidades existentes do Intune disponíveis atualmente para gerenciar dispositivos iOS continuarão a funcionar quando os usuários atualizarem seus dispositivos e aplicativos para o iOS 10.3.

No momento, não há problemas conhecidos para compartilhar. Se você encontrar algum problema com o iOS 10.3, entre em contato com a [equipe de suporte do Intune](get-support.md).

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Suporte aprimorado para os usuários do Android com base na China <!--720444-->

Devido à ausência da Google Play Store na China, os dispositivos Android devem obter aplicativos dos mercados chineses. O Portal da Empresa dará suporte a este fluxo de trabalho, redirecionando os usuários Android na China para baixarem os aplicativos Portal da Empresa e Outlook de lojas de aplicativos locais. Isso melhorará a experiência do usuário quando as políticas de acesso condicional estiverem habilitadas para gerenciamento de dispositivos e aplicativos móveis. Os aplicativos Portal da Empresa e Outlook para Android estão disponíveis nas seguintes lojas de aplicativos chinesas:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Prática recomendada: verificar se seus aplicativos Portal da Empresa estão atualizados<!--879465-->

Em dezembro de 2016, lançamos uma atualização que habilitou a imposição da autenticação multifator (MFA) em um grupo de usuários quando eles registram um dispositivo iOS, Android, Windows 8.1+ ou Windows Phone 8.1+. Este recurso não pode funcionar sem determinadas versões da linha de base do aplicativo Portal da Empresa para o Android (v5.0.3419.0+) e o iOS (v2.1.17+).

A Microsoft está aperfeiçoando continuamente o Intune adicionando novas funções ao console e aos aplicativos Portal da Empresa em todas as plataformas com suporte. Como resultado, a Microsoft lança apenas correções para os problemas encontrados na versão atual do aplicativo Portal da Empresa. Portanto, recomendamos usar as versões mais recentes dos aplicativos Portal da Empresa para ter a melhor experiência de usuário.

>[!Tip]
> Faça com que os usuários definam seus dispositivos para atualizarem automaticamente os aplicativos na loja de aplicativos apropriada. Se você disponibilizou o aplicativo Portal da Empresa Android em um compartilhamento de rede, poderá baixar a versão mais recente no [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=49140).

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Agora, o Microsoft Teams está habilitado para o MAM no iOS e Android

A Microsoft anunciou a disponibilidade geral do Microsoft Teams. Os aplicativos Microsoft Teams atualizados para o iOS e Android agora são habilitados com os recursos MAM (gerenciamento do aplicativo móvel) do Intune, portanto, você pode capacitar as equipes a trabalharem livremente entre os dispositivos, garantindo que as conversas e os dados corporativos estejam protegidos o tempo todo. Para obter mais detalhes, consulte [o comunicado sobre o Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) no blog Enterprise Mobility + Security.


## <a name="february-2017"></a>Fevereiro de 2017

### <a name="new-capabilities"></a>Novos recursos

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizando o site Portal da Empresa <!--753980-->
O site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu hambúrguer", ![Imagem pequena do menu hambúrguer que foi adicionado no canto superior esquerdo do site do Portal da Empresa](./media/CP_hamburger_menu.png).

### <a name="notices"></a>Avisos

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A migração de grupo não exigirá nenhuma atualização para grupos ou políticas para dispositivos iOS <!--898837-->
Durante a migração para grupos de dispositivos do Azure Active Directory, para cada grupo de dispositivos do Intune previamente atribuído por um perfil de Registro de Dispositivo Corporativo, um grupo de dispositivos dinâmico correspondente será criado no AAD com base no nome desse perfil. Isso garantirá que, conforme ocorrer o registro dos dispositivos, eles serão automaticamente agrupados e receberão as mesmas políticas e aplicativos que o grupo do Intune original.

Depois que um locatário entrar no processo de migração para agrupamento e direcionamento, o Intune criará automaticamente um grupo dinâmico do AAD para corresponder a um grupo do Intune direcionado por um perfil de Registro de Dispositivo Corporativo. Se o administrador do Intune excluir o grupo do Intune direcionado, o grupo AAD dinâmico correspondente não será excluído. Os membros do grupo e a consulta dinâmica serão apagados, mas o grupo permanecerá até que o administrador de TI remova-o por meio do portal do AAD.

Da mesma forma, se o administrador de TI alterar qual grupo Intune é afetado por um perfil de Registro de Dispositivo Corporativo, o Intune criará um novo grupo dinâmico refletindo a nova atribuição de perfil, mas não removerá o grupo dinâmico criado para a atribuição antiga.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador. O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](manage-windows-pcs-with-microsoft-intune.md).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Melhorando o suporte de gerenciamento de aplicativo móvel para o apagamento seletivo <!--581242-->
Os usuários finais receberão outras diretrizes sobre como recuperar o acesso a dados corporativos ou de estudante se esses dados forem removidos automaticamente devido à política “Intervalo offline antes do apagamento dos dados de aplicativo”.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Portal da Empresa para links do iOS abertos no aplicativo <!--665954-->
Os links dentro do aplicativo Portal da Empresa para iOS, incluindo os links para a documentação e os aplicativos, serão abertos diretamente no aplicativo Portal da Empresa usando uma exibição no aplicativo do Safari. Essa atualização será fornecida separadamente da atualização de serviço em janeiro.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Novo endereço de servidor MDM para dispositivos Windows <!--893007-->
Uma tentativa registrar um dispositivo por usuários do Windows e Windows Phone falhará se eles inserirem __manage.microsoft.com__ como o endereço do servidor MDM (se solicitado). O endereço do servidor MDM está mudando de __manage.microsoft.com__ para __enrollment.manage.microsoft.com__. Notifique seu usuário para usar __enrollment.manage.microsoft.com__ como o endereço do servidor MDM se solicitado durante o registro de um dispositivo Windows ou Windows Phone. Não é necessária nenhuma alteração em sua configuração CNAME. Para obter informações adicionais sobre essa alteração, visite [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->
A partir de março, o aplicativo de Portal da empresa para Android seguirá [as diretrizes de design de material](https://material.io/guidelines/material-design/introduction.html) para criar uma aparência mais moderna. Essa experiência do usuário aprimorada inclui:

* __Cores__: cabeçalhos de guia podem ser coloridos de acordo com sua paleta de cores personalizada.
* __Interface__: os botões Aplicativos em Destaque e Todos os Aplicativos foram atualizados na guia Aplicativos. O botão Pesquisa agora é um botão de ação flutuante.
* __Navegação__: todos os Aplicativos mostra uma exibição com guias de Em Destaque, Todos e Categorias para facilitar a navegação.
* __Serviço__: as guias Meus Dispositivos e Contatar TI têm legibilidade aprimorada.

Você pode localizar imagens de antes e depois na [página de atualizações da interface do usuário](whats-new-app-ui.md).

### <a name="associate-multiple-management-tools-with-the-microsoft-store-for-business---926135--"></a>Associar várias ferramentas de gerenciamento com a Microsoft Store para Empresas <!--926135-->
Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Microsoft Store para Empresas, anteriormente, era possível associar apenas um deles à Microsoft Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento ao armazenamento, por exemplo, o Intune e o Configuration Manager. Para ver mais detalhes, consulte [Gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune](windows-store-for-business.md).

## <a name="whats-new-in-the-public-preview-of-intune-in-the-azure-portal---736542--"></a>Novidades na visualização pública do Intune no Portal do Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](whats-new.md).

Você pode encontrar as novidades na visualização do Intune no Azure [aqui](whats-new.md).

## <a name="january-2017"></a>Janeiro de 2017

### <a name="new-capabilities"></a>Novos recursos

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Relatórios no console para MAM sem registro <!--677961-->
Novos relatórios de proteção do aplicativo foram adicionados para dispositivos registrados e não registrados. Saiba mais sobre como é possível [monitorar as políticas de gerenciamento de aplicativo móvel com o Intune](app-protection-policies-monitor.md).

#### <a name="android-711-support---694397--"></a>Suporte do Android 7.1.1 <!--694397-->
O Intune agora dá suporte completo e gerencia o Android 7.1.1.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Resolver o problema em que os dispositivos iOS estão inativos ou o console do administrador não consegue se comunicar com eles <!--unknown-->
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](troubleshoot-device-enrollment-in-intune.md#devices-are-inactive-or-the-admin-console-cant-communicate-with-them).

### <a name="notices"></a>Avisos

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador.

O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](manage-windows-pcs-with-microsoft-intune.md).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Melhorando o suporte de gerenciamento de aplicativo móvel para o apagamento seletivo <!--581242-->
Os usuários finais receberão outras diretrizes sobre como recuperar o acesso a dados corporativos ou de estudante se esses dados forem removidos automaticamente devido à política “Intervalo offline antes do apagamento dos dados de aplicativo”.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Portal da Empresa para links do iOS abertos no aplicativo <!--665954-->
Os links dentro do aplicativo Portal da Empresa para iOS, incluindo os links para a documentação e os aplicativos, serão abertos diretamente no aplicativo Portal da Empresa usando uma exibição no aplicativo do Safari. Essa atualização será fornecida separadamente da atualização de serviço em janeiro.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizando o site Portal da Empresa <!--753980-->
A partir de fevereiro, o site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu hambúrguer", ![Menu Hambúrguer do site do Portal da Empresa](./media/CP_hamburger_menu.png).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nova documentação para as políticas de proteção do aplicativo <!--583398-->
Atualizamos nossa documentação para os administradores e desenvolvedores de aplicativo que desejam habilitar políticas de proteção do aplicativo (conhecidas como políticas de MAM) em aplicativos iOS e Android usando a Ferramenta de Disposição do Aplicativo do Intune ou o SDK do Aplicativo do Intune.

Os seguintes artigos foram atualizados:

* [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](apps-prepare-mobile-application-management.md)
* [Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](app-wrapper-prepare-ios.md)
* [Introdução ao SDK do Aplicativo do Microsoft Intune](app-sdk-get-started.md)
* [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md)

Os seguintes artigos são novas adições à biblioteca de documentos:

* [Plug-in Cordova do SDK de Aplicativo do Intune](app-sdk-cordova.md)
* [Componente Xamarin do SDK de Aplicativo do Intune](app-sdk-xamarin.md)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Barra de progresso ao iniciar o Portal da Empresa no iOS <!--665978-->
O Portal da Empresa para iOS introduziu uma barra de progresso na tela de inicialização para fornecer ao usuário informações sobre os processos de carregamento ocorridos. Haverá uma distribuição em fases da barra de progresso para substituição do controle giratório. Isso significa que alguns dos usuários verão a nova barra de progresso enquanto outros continuarão vendo o controle giratório.

## <a name="december-2016"></a>Dezembro de 2016

### <a name="public-preview-of-intune-in-the-azure-portal--736542--"></a>Visualização pública do Intune no Portal do Azure<!--736542-->
No início de 2017, migraremos nossa experiência de administração completa para o Azure, permitindo um gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico. Antes de disponibilizar o portal para todos os locatários do Intune, estamos felizes em anunciar que começaremos a implantar uma visualização dessa nova experiência de administração no final deste mês para locatários selecionados.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, saiba mais sobre o que estamos preparando para o Microsoft Intune no portal do Azure em [nova documentação](/intune/what-is-intune).

__Integração de gerenciamento de despesas com telecomunicação__ <!--747605--> Estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com/). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](get-support.md).

### <a name="new-capabilities"></a>Novos recursos

__Autenticação multifator__ <!--747590--> Agora você pode impor a autenticação multifator (MFA) em um grupo selecionado de usuários quando registram um dispositivo iOS, Android, Windows 8.1 e posterior ou Windows Phone 8.1 e posterior do Portal de Gerenciamento do Azure, configurando o MFA no aplicativo de Registro do Microsoft Intune no Azure Active Directory.

__Habilidade de restringir a inscrição do dispositivo móvel__ <!--747596--> O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.
* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.
* Apenas para iOS, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](device-enrollment.md).

### <a name="notices"></a>Avisos

__Mudança da autenticação multifator na inscrição para o portal do Azure__ <!--VSO 750545--> Anteriormente, os administradores iriam para o console do Intune ou para o console do Configuration Manager (anterior à versão de outubro de 2016) a fim de definir o MFA para os registros do Intune. Com esse recurso atualizado, você fará o logon no [portal do Microsoft Azure](https://manage.windowsazure.com) usando suas credenciais do Intune e configurará o MFA por meio do Azure AD. Saiba mais sobre isso [aqui](https://aka.ms/mfa_ad).

__Aplicativo de Portal da empresa para Android já disponível na China__ <!--VSO 658093--> Estamos publicando o aplicativo de Portal da empresa para Android para download na China. Devido à ausência da Google Play Store na China, os dispositivos Android devem obter aplicativos dos mercados de aplicativo chineses. O aplicativo do Portal da Empresa para Android estará disponível para download nas seguintes lojas:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

O aplicativo de Portal da Empresa para Android usa o Google Play Services para se comunicar com o serviço Microsoft Intune. Como o Google Play Services ainda não está disponível na China, a execução de qualquer uma das seguintes tarefas pode levar até 8 horas para ser concluída. 

|Console de Administração do Intune| Aplicativo do Portal da Empresa do Intune para Android |Site do Portal da Empresa do Intune|   
|---|---|---|
|Apagamento completo| Remover um dispositivo remoto| Remover dispositivo (local e remoto)|
|Apagamento seletivo| Redefinir dispositivo| Redefinir o dispositivo|
|Implantações de aplicativo novo ou atualizado| Instalar aplicativos de linha de negócios disponíveis| Redefinição de senha de dispositivo|
|Bloqueio remoto|||
|Redefinição de senha|||

### <a name="deprecations"></a>Desativações

__O Firefox não oferece suporte ao Silverlight__ <!--VSO TBA--> O Mozilla não oferecerá suporte para o Silverlight na versão 52 do [navegador Firefox](https://www.mozilla.org/firefox) a partir de março de 2017. Como consequência, não será possível fazer logon no console existente do Intune usando as versões posteriores a 51. É recomendável usar o Internet Explorer 10 ou 11 para acessar o console de administração ou uma [versão do Firefox anterior à versão 52](https://ftp.mozilla.org/pub/firefox/releases/). A transição do Intune para o portal do Azure permitirá oferecer suporte a vários [navegadores modernos](/azure/azure-preview-portal-supported-browsers-devices), sem depender do Silverlight.

__Remoção das políticas de caixa de entrada do Exchange Online__ <!--770687--> A partir de dezembro, os administradores não poderão exibir ou configurar as políticas de caixa de correio móvel do Exchange Online (EAS) dentro do console do Intune. Essa alteração será revertida para todos os locatários do Intune em dezembro e janeiro. Todas as políticas existentes permanecerão conforme configurado. Para configurar novas políticas, use o Shell de Gerenciamento do Exchange. Mais informações estão disponíveis [aqui](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx).

__Não há mais suporte para os aplicativos Intune AV Player, Visualizador de Imagens e Visualizador de PDF no Android__ <!--747553--> A partir de meados de dezembro de 2016, os usuários não poderão usar os aplicativos Intune AV Player, Visualizador de Imagens e Visualizador de PDF. Esses aplicativos foram substituídos com o aplicativo de Proteção de Informações do Azure. Saiba mais sobre o aplicativo de Proteção de Informações do Azure [aqui](/information-protection/rms-client/mobile-app-faq).

## <a name="november-2016"></a>Novembro de 2016

### <a name="new-capabilities"></a>Novos recursos

__Novo Portal da Empresa do Microsoft Intune disponível para dispositivos Windows 10__ A Microsoft lançou um novo [aplicativo do Portal da Empresa do Microsoft Intune para dispositivos Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Esse aplicativo, que aproveita o novo formato do Windows 10 Universal, fornecerá ao usuário uma experiência de usuário atualizada dentro do aplicativo e experiências idênticas em todos os dispositivos Windows 10, sejam eles PCs ou dispositivos móveis, habilitando ainda todas as mesmas funcionalidades que eles estão usando atualmente.

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa para Windows 8.1 e do Portal da Empresa para Windows Phone 8.1 da Microsoft Store. Para obter mais detalhes, acesse [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Uma atualização no Intune e Android for Work__ Embora possa implantar aplicativos do Android for Work com uma ação __Necessária__, você só pode implantar aplicativos como __Disponível__ se os grupos do Intune tiverem sido migrados para a nova experiência de grupos do Azure AD.

__Agora, o SDK de Aplicativo do Intune para o plug-in do Cordova dá suporte ao MAM sem registro__ Desenvolvedores de aplicativos podem usar o SDK de Aplicativo do Intune para o plug-in do Cordova a fim de habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Cordova para Android e iOS. Encontre o Plug-in Cordova do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Agora, o componente Xamarin do SDK de Aplicativo dá suporte ao MAM sem registro__ Desenvolvedores de aplicativos podem usar o componente Xamarin do SDK de Aplicativo do Intune para habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Xamarin para Android e iOS. Encontre o Componente Xamarin do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Avisos

__O certificado de autenticação da Symantec não exige mais um Portal da Empresa assinado do Windows Phone 8 para upload__ O upload do certificado de autenticação da Symantec não exigirá mais um aplicativo de Portal da Empresa assinado do Windows Phone 8. O certificado pode ser carregado de forma independente.

### <a name="deprecations"></a>Desativações

__Suporte para o Portal da Empresa do Windows Phone 8__ O suporte para o Portal da Empresa do Windows Phone 8 será preterido. O suporte para as plataformas Windows Phone 8 e WinRT foi preterido em outubro de 2016. O suporte para o Portal da Empresa do Windows 8 também foi preterido em outubro de 2016.


### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
