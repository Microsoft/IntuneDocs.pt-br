---
title: "Edição antecipada | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 31f984fabd2373d242e5e3399bd0c82fbaf53070
ms.lasthandoff: 04/19/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>A Edição Antecipada do Microsoft Intune – abril de 2017

A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
> As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Status de instalação do aplicativo aprimorado para o aplicativo de Portal da empresa do Windows 10 <!--676495-->

O aplicativo de Portal da empresa do Windows 10 agora oferecerá uma barra de progresso de instalação do aplicativo para todas as instalações de aplicativos modernos iniciadas no Portal da empresa.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Status do sistema de mensagens aprimorado no aplicativo do Portal da empresa para iOS <!--744866-->

Mensagens de erro novas e mais específicas agora serão exibidas no aplicativo do Portal da empresa para iOS para fornecer informações mais acessíveis sobre o que está acontecendo nos dispositivos. Esses casos de erro foram anteriormente incluídos em uma mensagem de erro geral intitulada "Portal da empresa temporariamente indisponível". Além disso, se um usuário inicia o Portal da empresa no iOS quando não tem uma conexão de Internet, ele agora verá uma barra de status permanente na home page não dizendo "Nenhuma Conexão de Internet."

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps disponível para o navegador gerenciado <!--822308, 822303-->

Microsoft MyApps agora tem um suporte melhor dentro do navegador gerenciado. Usuários do navegador gerenciado que não são direcionados ao gerenciamento serão levados diretamente ao serviço MyApps, no qual podem acessar seus aplicativos SaaS provisionados pelo administrador. Usuários que são direcionados ao gerenciamento do Intune ainda poderão acessar MyApps no indicador interno do navegador gerenciado.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Novos ícones para o navegador gerenciado e o Portal da empresa <!--918433, 918431-->

O navegador gerenciado está recebendo ícones atualizados para versões de Android e iOS do aplicativo. O novo ícone conterá o selo do Intune atualizado para torná-lo mais consistente com outros aplicativos no Enterprise Mobility + Security (EM + S). Você pode ver o ícone novo para o Navegador Gerenciado na [página Novidades de interface do usuário do aplicativo Intune](whats-new-in-intune-app-ui.md).

O Portal da empresa também está recebendo ícones atualizados para as versões do Windows, iOS e Android do aplicativo para aprimorar a consistência com outros aplicativos EM + S. Esses ícones serão liberados gradualmente em plataformas a partir de abril até o fim de maio.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Suporte de logon único do Portal da empresa para iOS com o Outlook para iOS <!--834012-->

Os usuários não precisam mais entrar no aplicativo do Outlook se estiverem conectados no aplicativo de Portal da empresa para iOS no mesmo dispositivo com a mesma conta. Quando os usuários iniciarem o aplicativo do Outlook, eles poderão selecionar sua conta e se conectar automaticamente. Também estamos trabalhando para adicionar essa funcionalidade para outros aplicativos da Microsoft.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicador de progresso de conexão no Portal da empresa Android <!--953374-->

Uma atualização para o aplicativo de Portal da empresa Android mostra um indicador de progresso de conexão quando o usuário inicia ou reinicia o aplicativo. O indicador avança por novos status, começando com "Conectando…", "Fazendo logon..." e "Verificando os requisitos de segurança..." antes de permitir que o usuário acesse o aplicativo. Você pode ver as novas telas do aplicativo do Portal da Empresa para Android na [página Novidades de interface do usuário do aplicativo Intune](whats-new-in-intune-app-ui.md).


## <a name="notices"></a>Avisos

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

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


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Visualização pública da nova experiência do administrador do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->

Aplicativos Android na Play Store que oferecem suporte a opções de configuração gerenciada podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### <a name="remote-assistance-for-android-devices----675418---"></a>Assistência remota para dispositivos Android <!-- 675418 -->

Intune usará o software [TeamViewer](https://www.teamviewer.com), adquirido separadamente, para que você possa dar assistência remota a usuários que estão utilizando dispositivos Android.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nova política de Android para PINs complexos <!-- 722069 -->

Você pode definir um tipo de senha necessária de complexo numérico em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Suporte adicional para dispositivos Android for Work

- **Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 -->

  Adicionamos uma nova política de restrição para dispositivo Android for Work que lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

  Nós atualizamos a configuração de **compartilhamento de dados entre os perfis de trabalho e pessoais** em um perfil de restrição de dispositivo Android for Work com novas opções para ajudá-lo a configurar o compartilhamento de dados entre perfis de trabalho e pessoais.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 -->

  Quando você gerencia dispositivos Android for Work com o Intune, são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho. Agora adicionamos um perfil de dispositivo personalizado para dispositivos Android for Work que lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->

Você pode atribuir aplicativos de linha de negócios para iOS (arquivos .ipa) e Android (arquivos .apk) a usuários ou dispositivos.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>Novas políticas para dispositivos iOS <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Aplicativos na tela inicial** – Você pode usar uma política de dispositivo para controlar quais aplicativos os usuários veem na tela inicial de seu dispositivo iOS. Essa política altera o layout da tela inicial, mas não implanta nenhum aplicativo que você especificou que não esteja instalado.

- **Conexões com dispositivos AirPrint** – Você pode usar uma política de dispositivo do Intune para controlar a quais dispositivos AirPrint (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – Você pode usar uma política de dispositivo do Intune para controlar a quais dispositivos AirPlay (como Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – Você pode configurar uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão.

- **Filtro de conteúdo da Web** – Você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois métodos a seguir:

  - Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.
  - Permita que apenas sites especificado sejam acessados pelo navegador Safari. Serão criados no Safari indicadores para cada site que você especificar.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->

Em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes ajustes de notificação para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->

Você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->

Em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes ajustes de domínio:

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 -->

Você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->

Você pode sincronizar os livros que adquiriu da loja Apple de programas de aquisição com base em volume com o Intune e atribuí-los aos usuários.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gerenciamento de vários usuários para dispositivos Samsung KNOX Standard <!-- 971988 -->

Agora há suporte para dispositivos que executam o Samsung KNOX Standard para o gerenciamento de vários usuários pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->

Adicionamos suporte para configurações adicionais de restrição de dispositivos no Windows, como suporte adicional ao navegador Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->

Adicionamos suporte para o gerenciamento de vários usuários para dispositivos que executam a Atualização do Windows 10 para Criadores e estão ingressados no Domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Começar do zero para PCs com Windows 10<!-- 1004830 -->

Nesta versão, adicionamos uma nova ação de dispositivo para começar do zero em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->

Agora você pode criar uma política de atualização de edição para atualizar os dispositivos para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->

Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o registro automático do MDM para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte no momento para cenários de autoatendimento e de Portal da Empresa.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 58112, 736644 -->

Duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local


### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.

