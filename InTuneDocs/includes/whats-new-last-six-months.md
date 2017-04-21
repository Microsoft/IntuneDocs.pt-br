## <a name="march-2017"></a>Março de 2017

### <a name="new-capabilities"></a>Novos recursos

#### <a name="support-for-skycure"></a>Suporte para Skycure

Agora, é possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:

- Defesa física
- Defesa de rede
- Defesa do aplicativo
- Defesa de vulnerabilidades

É possível configurar políticas de acesso condicional de EMS com base na avaliação de risco do Skycure habilitada por meio das políticas de conformidade de dispositivo do Intune. Use essas políticas para permitir ou bloquear o acesso de dispositivos incompatíveis aos recursos corporativos com base em ameaças detectadas. Para saber mais, confira [Conector de Defesa contra Ameaças Móveis do Skycure](/intune/deploy-use/skycure-mobile-threat-defense-connector).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->

O aplicativo Portal da Empresa para Android atualizará sua interface do usuário para uma aparência mais moderna e melhor experiência do usuário. As atualizações importantes são:

- Cores: os cabeçalhos da guia Portal da Empresa estão coloridos na identidade visual definida pela TI.
- Aplicativos: na guia **Aplicativos**, os botões **Aplicativos em destaque** e **Todos os aplicativos** foram atualizados.
- Pesquisa: na guia **Aplicativos**, o botão **Pesquisa** é um botão de ação flutuante.
- Aplicativos de navegação: a exibição **Todos os aplicativos** mostra uma exibição com as guias **Em destaque**, **Todos** e **Categorias** para facilitar a navegação.
- Suporte: as guias **Meus dispositivos** e **Entrar em contato com a TI** foram atualizadas para melhorar a legibilidade.

Para obter mais detalhes sobre essas alterações, consulte [Atualizações da IU para aplicativos do usuário final do Intune](/intune/whats-new/whats-new-in-intune-app-ui).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->

Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Assinatura do Script para o Portal da Empresa do Windows 10<!--941642-->

Se você precisar baixar e carregar o aplicativo Portal da Empresa do Windows 10, agora poderá usar um script para simplificar e facilitar o processo de autenticação do aplicativo para sua organização.   Para baixar o script e suas instruções de uso, consulte [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Script de assinatura do Microsoft Intune para o Portal da Empresa do Windows 10) na Galeria do TechNet. Para obter mais detalhes sobre este lançamento, confira [Atualizar seu aplicativo do Portal da Empresa do Windows 10](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) no Blog da Equipe de Suporte do Intune.


### <a name="notices"></a>Avisos

#### <a name="support-for-ios-103"></a>Suporte para iOS 10.3

A versão do iOS 10.3 começou a ser distribuída em 27 de março de 2017 para os usuários de iOS. Todos os cenários existentes do Intune MDM e MAM são compatíveis com a versão mais recente do sistema operacional Apple. Antecipamos que todas as funcionalidades existentes do Intune disponíveis atualmente para gerenciar dispositivos iOS continuarão a funcionar quando os usuários atualizarem seus dispositivos e aplicativos para o iOS 10.3.

No momento, não há problemas conhecidos para compartilhar. Se você encontrar algum problema com o iOS 10.3, entre em contato com a [equipe de suporte do Intune](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

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
O site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu de hambúrguer", ![Pequena imagem do menu de hambúrguer que é agora adicionada ao canto superior esquerdo do site Portal da Empresa](/intune/whats-new/media/CP_hamburger_menu.png) e que conterá detalhes de contato de suporte técnico e informações sobre os dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente. Você pode localizar imagens de antes e depois disponíveis na [página de atualizações da interface do usuário](/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="notices"></a>Avisos

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A migração de grupo não exigirá nenhuma atualização para grupos ou políticas para dispositivos iOS <!--898837-->
Durante a migração para grupos de dispositivos do Azure Active Directory, para cada grupo de dispositivos do Intune previamente atribuído por um perfil de Registro de Dispositivo Corporativo, um grupo de dispositivos dinâmico correspondente será criado no AAD com base no nome desse perfil. Isso garantirá que, conforme ocorrer o registro dos dispositivos, eles serão automaticamente agrupados e receberão as mesmas políticas e aplicativos que o grupo do Intune original.

Depois que um locatário entrar no processo de migração para agrupamento e direcionamento, o Intune criará automaticamente um grupo dinâmico do AAD para corresponder a um grupo do Intune direcionado por um perfil de Registro de Dispositivo Corporativo. Se o administrador do Intune excluir o grupo do Intune direcionado, o grupo AAD dinâmico correspondente não será excluído. Os membros do grupo e a consulta dinâmica serão apagados, mas o grupo permanecerá até que o administrador de TI remova-o por meio do portal do AAD.

Da mesma forma, se o administrador de TI alterar qual grupo Intune é afetado por um perfil de Registro de Dispositivo Corporativo, o Intune criará um novo grupo dinâmico refletindo a nova atribuição de perfil, mas não removerá o grupo dinâmico criado para a atribuição antiga.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador. O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

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
* __Navegação__: Todos os Aplicativos mostra uma exibição com guias de Em Destaque, Todos e Categorias para facilitar a navegação.
* __Serviço__: as guias Meus Dispositivos e Contatar TI têm legibilidade aprimorada.

Você pode localizar imagens de antes e depois na [página de atualizações da interface do usuário](/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Associar várias ferramentas de gerenciamento da Windows Store para Empresas <!--926135-->
Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Windows Store para Empresas, anteriormente, você podia associar apenas um deles à Windows Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager. Para ver mais detalhes, consulte [Gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune](/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Novidades na visualização pública da experiência de administração do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](/intune-azure/introduction/whats-new).

Você pode encontrar as novidades na visualização do Intune no Azure [aqui](/intune-azure/introduction/whats-new).

## <a name="january-2017"></a>Janeiro de 2017

### <a name="new-capabilities"></a>Novos recursos

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Relatórios no console para MAM sem registro <!--677961-->
Novos relatórios de proteção do aplicativo foram adicionados para dispositivos registrados e não registrados. Saiba mais sobre como é possível [monitorar as políticas de gerenciamento de aplicativo móvel com o Intune aqui](/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Suporte do Android 7.1.1 <!--694397-->
O Intune agora dá suporte completo e gerencia o Android 7.1.1.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Resolver o problema em que os dispositivos iOS estão inativos ou o console do administrador não consegue se comunicar com eles <!--unknown-->
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Avisos

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador.

O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Melhorando o suporte de gerenciamento de aplicativo móvel para o apagamento seletivo <!--581242-->
Os usuários finais receberão outras diretrizes sobre como recuperar o acesso a dados corporativos ou de estudante se esses dados forem removidos automaticamente devido à política “Intervalo offline antes do apagamento dos dados de aplicativo”.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Portal da Empresa para links do iOS abertos no aplicativo <!--665954-->
Os links dentro do aplicativo Portal da Empresa para iOS, incluindo os links para a documentação e os aplicativos, serão abertos diretamente no aplicativo Portal da Empresa usando uma exibição no aplicativo do Safari. Essa atualização será fornecida separadamente da atualização de serviço em janeiro.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizando o site Portal da Empresa <!--753980-->
A partir de fevereiro, o site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu de hambúrguer", ![menu de hambúrguer do site Portal da Empresa](/intune/whats-new/media/CP_hamburger_menu.png) contendo detalhes de contato de suporte técnico e informações sobre os dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente. É possível encontrar imagens de antes e depois disponíveis na [página Novidades na interface do usuário do aplicativo do Intune](/intune/whats-new/whats-new-in-intune-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nova documentação para as políticas de proteção do aplicativo <!--583398-->
Atualizamos nossa documentação para os administradores e desenvolvedores de aplicativo que desejam habilitar políticas de proteção do aplicativo (conhecidas como políticas de MAM) em aplicativos iOS e Android usando a Ferramenta de Disposição do Aplicativo do Intune ou o SDK do Aplicativo do Intune.

Os seguintes artigos foram atualizados:

* [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Introdução ao SDK do Aplicativo do Microsoft Intune](/intune/develop/intune-app-sdk-get-started)
* [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](/intune/develop/intune-app-sdk-ios)

Os seguintes artigos são novas adições à biblioteca de documentos:

* [Plug-in Cordova do SDK de Aplicativo do Intune](/intune/develop/intune-app-sdk-cordova)
* [Componente Xamarin do SDK de Aplicativo do Intune](/intune/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Barra de progresso ao iniciar o Portal da Empresa no iOS <!--665978-->
O Portal da Empresa para iOS introduziu uma barra de progresso na tela de inicialização para fornecer ao usuário informações sobre os processos de carregamento ocorridos. Haverá uma distribuição em fases da barra de progresso para substituição do controle giratório. Isso significa que alguns dos usuários verão a nova barra de progresso enquanto outros continuarão vendo o controle giratório.

## <a name="december-2016"></a>Dezembro de 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Visualização pública da nova experiência do administrador do Intune no Azure <!--736542-->
No início de 2017, migraremos nossa experiência de administração completa para o Azure, permitindo um gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico. Antes de disponibilizar o portal para todos os locatários do Intune, estamos felizes em anunciar que começaremos a implantar uma visualização dessa nova experiência de administração no final deste mês para locatários selecionados.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, saiba mais sobre o que estamos preparando para o Microsoft Intune no portal do Azure em [nova documentação](/intune-azure/introduction/what-is-microsoft-intune).

__Integração de gerenciamento de despesas com telecomunicação__ <!--747605--> Estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Novos recursos

__Autenticação multifator__ <!--747590--> Agora você pode impor a autenticação multifator (MFA) em um grupo selecionado de usuários quando registram um dispositivo iOS, Android, Windows 8.1 e posterior ou Windows Phone 8.1 e posterior do Portal de Gerenciamento do Azure, configurando o MFA no aplicativo de Registro do Microsoft Intune no Azure Active Directory.

__Habilidade de restringir a inscrição do dispositivo móvel__ <!--747596--> O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.
* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.
* Apenas para iOS, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](/intune/deploy-use/manage-corporate-owned-devices).

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

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa do Windows 8.1 e do Portal da Empresa do Windows Phone 8.1 da Windows Store. Para obter mais detalhes, acesse [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Uma atualização no Intune e Android for Work__ Embora possa implantar aplicativos do Android for Work com uma ação __Necessária__, você só pode implantar aplicativos como __Disponível__ se os grupos do Intune tiverem sido migrados para a nova experiência de grupos do Azure AD.

__Agora, o SDK de Aplicativo do Intune para o plug-in do Cordova dá suporte ao MAM sem registro__ Desenvolvedores de aplicativos podem usar o SDK de Aplicativo do Intune para o plug-in do Cordova a fim de habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Cordova para Android e iOS. Encontre o Plug-in Cordova do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Agora, o componente Xamarin do SDK de Aplicativo dá suporte ao MAM sem registro__ Desenvolvedores de aplicativos podem usar o componente Xamarin do SDK de Aplicativo do Intune para habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Xamarin para Android e iOS. Encontre o Componente Xamarin do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Avisos

__O certificado de autenticação da Symantec não exige mais um Portal da Empresa assinado do Windows Phone 8 para upload__ O upload do certificado de autenticação da Symantec não exigirá mais um aplicativo de Portal da Empresa assinado do Windows Phone 8. O certificado pode ser carregado de forma independente.

###<a name="deprecations"></a>Desativações

__Suporte para o Portal da Empresa do Windows Phone 8__ O suporte para o Portal da Empresa do Windows Phone 8 será preterido. O suporte para as plataformas Windows Phone 8 e WinRT foi preterido em outubro de 2016. O suporte para o Portal da Empresa do Windows 8 também foi preterido em outubro de 2016.

## <a name="october-2016"></a>Outubro de 2016

### <a name="conditional-access-for-mobile-application-management"></a>Acesso condicional para gerenciamento de aplicativos móveis
Você poderá restringir o acesso ao Exchange Online somente para aplicativos que deem suporte a políticas de gerenciamento de aplicativos móveis do Intune, como o Outlook. [Esse novo recurso](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) combina perfeitamente com as políticas de MAM (gerenciamento de aplicativo móvel) do Intune, porque você pode bloquear o acesso a clientes de email interno ou outros aplicativos que não foram configurados com as políticas de MAM do Intune. Isso garante que os usuários estão acessando os dados da sua organização com aplicativos que podem ser protegidos usando o MAM do Intune. Você pode começar no gerenciamento de aplicativo móvel do Intune por meio do Portal do Azure. Procure a nova seção de Acesso Condicional na folha "Configurações".

### <a name="conditional-access-for-windows-pcs"></a>Acesso condicional para computadores Windows
Agora é possível criar políticas de acesso condicional por meio do console de administrador do Intune para impedir que computadores Windows acessem o [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) e o [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Você também pode criar políticas de acesso condicional para bloquear o acesso aos aplicativos da área de trabalho e universais do Office.

### <a name="android-for-work-support"></a>Suporte do Android for Work

> [!IMPORTANT]

> Embora possa implantar aplicativos do Android for Work com uma ação __Necessária__, você só pode implantar aplicativos como __Disponível__ se os grupos do Intune tiverem sido migrados para a nova experiência de grupos do Azure AD.

O Intune agora faz parte do programa AfW (Android for Work). Começaremos a distribuir o suporte para recursos do AfW a partir deste mês e continuaremos nos próximos meses. Observe que a implantação de aplicativos disponíveis do AfW utiliza a nova experiência de agrupamento e direcionamento. Contas de serviço do Intune recém-provisionadas poderão usar esse recurso quando o AfW estiver disponível para elas.

[Leia o comunicado da Microsoft sobre o suporte do Intune para o Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Os tópicos sobre o Intune a seguir são novos ou foram atualizados com informações sobre o Android for Work:

Para profissionais de TI:
- [Configurar o Android for Work](/intune/deploy-use/set-up-android-for-work)
- [Restringir o acesso de email ao Exchange Online e ao novo Exchange Online Dedicado com o Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restringir o acesso de email ao Exchange local e ao Exchange Online Dedicado herdado com o Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Configurações de política de conformidade do Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Como implantar aplicativos do Android for Work](/intune/deploy-use/android-for-work-apps)
- [Configurar aplicativos do Android for Work com as políticas de configuração de aplicativo móvel](/intune/deploy-use/afw-app-configuration-policy)
- [Configurações de política do Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Para usuários finais:
- [O que acontece quando você cria um perfil de trabalho](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Criar um perfil de trabalho e registrar seu dispositivo no Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Integração ao Lookout para proteger dispositivos iOS
A Microsoft está se integrando à solução de proteção contra ameaças a dispositivos móveis do Lookout para proteger dispositivos móveis iOS detectando neles a presença de malware, aplicativos arriscados e muito mais. A solução do Lookout ajuda você a determinar o nível de ameaça, que é configurável. Você pode criar uma regra de política de conformidade do Intune para determinar a conformidade do dispositivo com base na avaliação de riscos pelo Lookout. Usando políticas de acesso condicional, você pode permitir ou bloquear o acesso aos recursos da empresa com base no status de conformidade do dispositivo.

Os usuários finais de dispositivos iOS não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em seus dispositivos, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso a dados corporativos. Saiba como [Configurar e implantar aplicativos Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

### <a name="intune-app-wrapping-tool-for-android"></a>Ferramenta de Encapsulamento de Aplicativos do Intune para Android
Você pode habilitar seus aplicativos para usar políticas de MAM (gerenciamento de aplicativo móvel) do Intune usando a Ferramenta de Encapsulamento de Aplicativos do Intune. O suporte para políticas de MAM do Intune sem a necessidade de registro do dispositivo está disponível.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Gerenciar a impressão por meio de aplicativos gerenciados usando políticas MAM
Agora você pode evitar a impressão de dados da empresa por meio de aplicativos que têm políticas MAM. Essa configuração está disponível no [portal do Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) e tem suporte tanto em dispositivos [iOS](/Intune/deploy-use/ios-mam-policy-settings) quanto [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Suporte para impressões digitais em dispositivos Android
Agora, as políticas de MAM (gerenciamento de aplicativo móvel) do Android permitem que os usuários acessem aplicativos com sua impressão digital em vez de digitar o PIN. Consulte esta e outras [configurações de política de gerenciamento de aplicativo móvel para dispositivos Android aqui](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Avisos

__Compatibilidade do Samsung KNOX Android com o Intune__ Alguns modelos do telefone Samsung Galaxy Ace não podem ser gerenciados pelo Intune como dispositivos Samsung KNOX. Em vez disso, quando você registrá-los com o Intune, eles serão gerenciados como dispositivos Android padrão.

Os números de modelo afetados são:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Você e seus usuários finais não precisam executar nenhuma ação adicional. Para obter mais informações, visite o site do [Samsung KNOX](https://www.samsungknox.com).

__O aplicativo de Portal da Empresa para o Windows 8 foi preterido; o suporte para as plataformas Windows Phone 8 e Windows RT está sendo preterido__ A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para o Portal da Empresa do Windows 8. O Microsoft Intune também preterirá o suporte para as plataformas Windows Phone 8 e Windows RT. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8 ou Windows RT.

Você pode continuar a gerenciar dispositivos Windows Phone 8, Windows RT e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.

A partir de novembro de 2016, o suporte para o Portal de Empresa do Windows Phone 8 será preterido.
<!--TFS 1255391-->

### <a name="whats-coming"></a>O que está por vir

__Novo Portal da Empresa do Microsoft Intune disponível para dispositivos Windows 10__ A Microsoft está lançando um novo Portal da Empresa do Microsoft Intune para dispositivos Windows 10. Esse aplicativo, que aproveita o novo formato do Windows 10 Universal, fornecerá ao usuário uma experiência de usuário atualizada dentro do aplicativo e experiências idênticas em todos os dispositivos Windows 10, sejam eles PCs ou dispositivos móveis, habilitando ainda todas as mesmas funcionalidades que eles estão usando atualmente.

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa do Windows 8.1 e do Portal da Empresa do Windows Phone 8.1 da Windows Store. Para obter mais detalhes, acesse [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Setembro de 2016
### <a name="new-features-announcements-and-information"></a>Novos recursos, avisos e informações
* [Acesso condicional do Windows](#windows-conditional-access)
* [Suporte para iOS 10](#ios-10-support)
* [A Ferramenta de Encapsulamento de Aplicativo dá suporte ao MAM sem registro de dispositivo para Android e iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Os grupos do Intune começam a transição para o Azure Active Directory em setembro](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integração do Lookout para proteger dispositivos Android](#lookout-integration-to-protect-android-devices)
* [Atualizações do Portal da Empresa para Android, iOS e Windows](#company-portal-updates)
* [Glossário do Intune](#intune-glossary)
* [O que está por vir](#whats-coming)

### <a name="windows-conditional-access"></a>Acesso condicional do Windows
Agora é possível criar políticas de acesso condicional através do console de administrador do Intune para impedir que PCs Windows acessem o Exchange Online e o SharePoint Online. Você também pode criar políticas de acesso condicional para bloquear o acesso aos aplicativos da área de trabalho e universais do Office.

### <a name="ios-10-support"></a>suporte para iOS 10
Os cenários existentes do Intune MDM e MAM são compatíveis com iOS 10. Para obter dicas, consulte o [Blob da Equipe de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>A Ferramenta de Disposição do Aplicativo dá suporte ao MAM sem registro de dispositivo para Android e iOS
A Ferramenta de Disposição do Aplicativo do Intune é uma ferramenta de linha de comando usada para habilitar o Intune MAM em aplicativos de linha de negócios (LOB) para iOS e Android. Esta é a maneira mais simples de incorporar o SDK do MAM do Intune em seu aplicativo, para que seu aplicativo possa impor políticas MAM implantadas por meio do Intune. Ao usar políticas MAM, você pode:

1. Criptografar os dados do aplicativo.
2. Exigir que o trabalhador de informações insira um PIN ao iniciar o aplicativo.
3. Permitir que o aplicativo transfira dados apenas para outros aplicativos gerenciados.
4. Impedir que o aplicativo faça backup de dados para Android, iTunes e iCloud.
5. Permitir que somente Recortar, Copiar e Colar em e fora de outros aplicativos gerenciados.

A visualização pública da Ferramenta de Disposição do Aplicativo do Intune atualizada agora dá suporte ao MAM sem registro de dispositivo em aplicativos LOB internos no iOS e Android. Isso significa que os usuários finais não precisam registrar seus dispositivos com o Intune para usar aplicativos LOB habilitados para MAM.

Qualquer pessoa pode testar o software de visualização pública e ler a documentação útil, localizada no GitHub do msintuneappsdk:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Antes de instalar e usar o Wrapper do Aplicativo do Microsoft Intune para pré-lançamento para Android e iOS, você deve:

* Examinar os Termos de Licença da Microsoft para a Ferramenta de Disposição do Aplicativo do Microsoft Intune para pré-lançamento para Android e iOS
* Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar a Ferramenta de Disposição do Aplicativo do Microsoft Intune para Pré-lançamento para Android, você concorda com estes termos de licença. Se você não aceitá-los, não use o software.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Os grupos do Intune começam a transição para o Azure Active Directory em setembro
Algumas novas contas do Intune usarão os grupos de segurança do Azure Active Directory em vez de grupos de usuários do Intune. Você saberá que você está trabalhando com grupos de segurança porque a página de grupos do portal do Intune terá um link que direciona para o portal de gerenciamento do Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Integração do Lookout para proteger os dispositivos Android
A Microsoft está se integrando com a solução de proteção de ameaças móveis do Lookout para proteger dispositivos móveis Android ao detectar malware, aplicativos arriscados e muito mais, em dispositivos. A solução do Lookout ajuda você a determinar o nível de ameaça, que é configurável. Você pode criar uma regra de política de conformidade do Intune para determinar a conformidade do dispositivo com base na avaliação de riscos pelo Lookout. Usando políticas de acesso condicional, você pode permitir ou bloquear o acesso aos recursos da empresa com base no status de conformidade do dispositivo.

Os usuários finais de dispositivos não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em dispositivos Android, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso. Para saber mais, consulte [Restringir o acesso com base no dispositivo, na rede e no risco do aplicativo](/intune/deploy-use/device-threat-protection).


### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa

__Android__

<p style="margin-left: 40px">**Acréscimo de “Notificações” ao Portal da Empresa para Android**<br/>
<p style="margin-left: 40px">Um novo ícone de Notificações foi adicionado ao Portal da Empresa para Android na home page. Tocar o ícone acessa a página Notificações, que mostra aos usuários finais todos os itens que requerem atenção no aplicativo do Portal da Empresa, como a falta de conformidade do dispositivo, a atualização de registro e a ativação do registro. O aplicativo do Portal da Empresa para iOS já tem essa experiência de notificações. Ter a nova página Notificações significa que os usuários não verão a página Configuração do Acesso da Empresa sempre que iniciarem ou retomarem o Portal da Empresa, contanto que o dispositivo já esteja registrado. Se você criar suas próprias diretrizes do usuário final, atualize sua documentação para refletir essas alterações. Encontre capturas de tela atualizadas [aqui](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Alterações no suporte para o aplicativo do Portal da Empresa do iOS**<br/>
<p style="margin-left: 40px">Todos os usuários do aplicativo do Portal da Empresa do Microsoft Intune para iOS agora devem usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Melhorias na maneira como os usuários finais do iOS obtêm seus aplicativos**<br/>
<p style="margin-left: 40px">As alterações a seguir foram feitas nos blocos de aplicativos no aplicativo Portal da Empresa para iOS para encaminhar os usuários a diferentes modos de exibição em um único local, o site Portal da Empresa, para todos os seus aplicativos. As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da loja de aplicativos sejam listados no aplicativo Portal da Empresa e exigem que os usuários acessem diferentes modos de exibição para localizar todos os seus aplicativos.

<p style="margin-left: 40px">Anteriormente, o bloco **Aplicativos da Empresa** apontavam para uma lista de todos os aplicativos na guia TODOS do site Portal da Empresa e continuará funcionando da mesma maneira. O nome do bloco foi alterado para **Todos os Aplicativos**.

<p style="margin-left: 40px">Anteriormente, o bloco **Outros Aplicativos** apontava para um modo de exibição no aplicativo Portal da Empresa que lista todos os aplicativos que Apple permite que o aplicativo Portal da Empresa mostre. O nome do bloco foi alterado para **Aplicativos em Destaque** e, ao tocar no bloco, os usuários são levados para a guia EM DESTAQUE do site Portal da Empresa.

<p style="margin-left: 40px">O bloco **Categorias** apontava para um modo de exibição no aplicativo Portal da Empresa que lista categorias de aplicativos. O nome do bloco não foi alterado, mas agora ele aponta para a guia CATEGORIAS do site Portal da Empresa. Você pode encontrar capturas de tela atualizadas [aqui](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Solicite a instalação do aplicativo de Navegador Gerenciado do iOS se o profissional de TI definir esse requisito para um aplicativo**<br/>
<p style="margin-left: 40px">Se você tiver configurado um clipe da Web para ser aberto apenas no navegador gerenciado e o navegador gerenciado não estiver instalado em um dispositivo, o aplicativo Portal da Empresa no dispositivo solicitará que o usuário instale o navegador gerenciado para que o clipe da Web possa ser instalado.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Botão de comentários adicionado ao aplicativo do Portal da Empresa do Windows Phone 8.1**<br/>
<p style="margin-left: 40px">O aplicativo do Portal da Empresa para Windows Phone 8.1 permite que os usuários finais enviem comentários sobre o aplicativo usando um novo botão “enviar comentários”. Para localizar o botão, os usuários tocam no menu de “três pontos” na parte inferior direita da tela do aplicativo do Portal da Empresa e tocam em **enviar comentários**. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do aplicativo do Portal da Empresa para os usuários.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glossário do Intune</br>
Adicionamos um novo [tópico de glossário](/intune/understand-explore/intune-glossary) na biblioteca para ajudá-lo a entender alguns dos termos usados no produto Intune.

## <a name="august-2016"></a>Agosto de 2016
### <a name="app-management"></a>Gerenciamento de aplicativos

__Aplicativos ocultados e mostrados para iOS 9.3__ Para dispositivos que executam o iOS 9.3 ou posterior, você pode usar a lista de aplicativos ocultados e exibidos na política de configuração geral do iOS para:
- Especificar uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
- Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Os aplicativos que você pode especificar incluem os dois aplicativos que você implantou e os aplicativos iOS nativos, como Mensagens e Anotações. Para obter detalhes, consulte [iOS policy settings in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune) (Configurações de política do iOS no Microsoft Intune)
<!---TFS 1279009 checked--->
__Política de aplicativos permitidos e bloqueados para dispositivos Samsung KNOX__ Agora você pode configurar uma política personalizada para dispositivos Samsung KNOX que permite que você crie um dos seguintes procedimentos:
- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Mesmo se instalado, um aplicativo definido na lista bloqueada não poderá ser ativado no dispositivo.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da Google Play Store. Nenhum outro aplicativo pode ser instalado por meio da Store.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX.
Para obter detalhes, consulte [Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Novos aplicativos compatíveis com políticas de MAM (gerenciamento de aplicativo móvel)__ O aplicativo do Yammer para [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) é compatível com as [políticas de MAM (gerenciamento de aplicativo móvel) do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), esteja o dispositivo registrado ou não.

Para obter uma lista completa de aplicativos compatíveis com MAM, visite o site [Microsoft Intune application partners](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) (Parceiros de aplicativos do Microsoft Intune).
<!--- TFS 1252335 & 1252336 checked--->

__Aplicativos do Visualizador do Intune__ Com o lançamento do novo aplicativo de RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do Visualizador do Intune, é recomendável usar o novo [aplicativo do Rights Management (RMS sharing) para o Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança os arquivos corporativos em dispositivos Android. Quando o aplicativo do Visualizador do Intune não tiver mais suporte, ele será removido da Google Store e não estará disponível para uso futuro.

### <a name="device-management"></a>Gerenciamento de dispositivo
__Suporte para Android 7.0__ O Intune oferece suporte de "dia 0" para o próximo sistema de operacional Android 7.0 para dispositivos móveis.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Remoção pelo Google da funcionalidade de redefinição remota de senha em dispositivos Android 7.0
O Google está removendo a capacidade dos administradores de TI e usuários finais de redefinir remotamente a senha de dispositivos Android 7.0. Anteriormente, os administradores de TI podiam redefinir remotamente a senha de um usuário, e os usuários finais podiam redefinir suas senhas do site do Portal da Empresa.



### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa
__Site do Portal da Empresa__
- **Link de comentários do Portal da Empresa para a Microsoft** <br/>
O site do Portal da Empresa permite que os usuários finais toquem em um novo link “Comentário”, na parte inferior da página, para enviar comentários para a Microsoft sobre sua experiência com o site. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do site do Portal da Empresa para os usuários.
<!--- TFS 1313657 checked--->

__iOS__
- **Versão mínima do Managed Browser para iOS atualizada para 8.0**<br/>
O aplicativo Microsoft Intune Managed Browser para iOS foi atualizado para dar suporte a dispositivos executando o iOS 8.0 ou posterior. Embora dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>O que está por vir
__Transição de grupos do Intune para os grupos do Azure Active Directory a partir de setembro de 2016__ O Intune está criando uma nova experiência de gerenciamento de grupos que usa os grupos de segurança do AAD (Azure Active Directory) como grupos de usuários e de dispositivos no Intune. Esses grupos serão usados para todo o gerenciamento de grupo, implantação de política e implantação de perfil **quando lançarmos o novo portal de administração do Intune baseado no Azure**.

Essa nova experiência evitará que você precise duplicar grupos entre serviços, **concederá acesso a alguns recursos de grupo novos do AADP (Azure Active Directory Premium)** e fornecerá extensibilidade usando o PowerShell e o Graph. Ela também unificará a experiência de gerenciamento de grupo no gerenciamento de mobilidade empresarial.

Para habilitar a mudança para grupos de segurança, a experiência no **console do administrador** atual passará por algumas modificações. **Essas alterações e o uso de grupos de segurança do AAD serão registrados na documentação do Intune**.

Os cientes que forem novos no Intune verão **algumas das alterações de grupos de segurança antes dos locatários atuais**.

Além das alterações no gerenciamento de grupo, **as seguintes funcionalidades serão preteridas**:
- Exclusão de membros ou grupos ao criar um novo grupo
- Grupos de **Usuários Desagrupados** e **Dispositivos Desagrupados**
- **Gerenciar Grupos** na função Administrador do Serviço
- Alertas personalizados com base em grupo para Regras de Notificação
- Dinamização com grupos em relatórios
<!--- TFS 1295329--->

__Adição de “Notificações” ao Portal da Empresa para Android__ Lançaremos uma atualização para o Portal da Empresa para Android em setembro que apresentará um novo ícone **Notificações** na home page. Tocar nesse ícone acessará a pagina **Notificações** que lhe mostrará ao seu usuário final todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, atualização de registro e ativação de registro. Se você também usar o aplicativo de Portal da Empresa do iOS, já verá a experiência de notificações. Com a introdução da página **Notificações**, você não verá a página **Configuração de Acesso da Empresa** sempre que iniciar ou retomar o Portal da Empresa para Android contanto que o dispositivo já esteja registrado. Ouvimos que muitos de vocês criaram diretrizes para usuário final e apreciariam um aviso antecipado quando for possível que suas diretrizes/capturas precisem ser atualizadas. Atualize sua documentação para refletir a alteração futura na experiência. Encontre capturas de tela atualizadas aqui: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Serviço preterido

- **Alterações no suporte para o aplicativo do Portal da Empresa do iOS**<br/>
Em setembro, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

- **Versão mínima do Managed Browser para iOS atualizada para 8.0**<br/>
Em agosto, o Intune lançará um aplicativo Microsoft Intune Managed Browser atualizado para iOS que dará suporte apenas a dispositivos executando o iOS 8.0 ou posterior. Embora os dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253--->

- **Aplicativos de Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos a partir de setembro de 2016** <br/>
A partir de setembro de 2016, o Microsoft Intune encerrará o suporte para os aplicativos de Portal da Empresa do Microsoft Intune para as plataformas Windows Phone 8 e Windows 8. Atualize os dispositivos para Windows 8.1 e Windows Phone 8.1, e use os aplicativos de Portal da Empresa correspondentes dessas plataformas para continuar a distribuição de aplicativos para esses dispositivos.
<!---TFS 1255391--->
