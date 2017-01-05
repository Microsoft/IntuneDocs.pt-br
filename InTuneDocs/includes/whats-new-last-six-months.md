## <a name="november-2016"></a>Novembro de 2016

### <a name="new-capabilities"></a>Novos recursos

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Novo Portal da Empresa do Microsoft Intune disponível para dispositivos Windows 10__ A Microsoft lançou um novo [aplicativo do Portal da Empresa do Microsoft Intune para dispositivos Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Esse aplicativo, que aproveita o novo formato do Windows 10 Universal, fornecerá ao usuário uma experiência de usuário atualizada dentro do aplicativo e experiências idênticas em todos os dispositivos Windows 10, sejam eles PCs ou dispositivos móveis, habilitando ainda todas as mesmas funcionalidades que eles estão usando atualmente.

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa do Windows 8.1 e do Portal da Empresa do Windows Phone 8.1 da Windows Store. Para obter mais detalhes, acesse [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Uma atualização no Intune e no Android for Work__

> Embora possa implantar aplicativos do Android for Work com uma ação __Necessária__, você só pode implantar aplicativos como __Disponível__ se os grupos do Intune tiverem sido migrados para a nova experiência de grupos do Azure AD.

__Agora, o SDK de Aplicativo do Intune para o plug-in do Cordova dá suporte ao MAM sem registro__ Desenvolvedores de aplicativos podem usar o SDK de Aplicativo do Intune para o plug-in do Cordova a fim de habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Cordova para Android e iOS. Encontre o Plug-in Cordova do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Agora, o componente Xamarin do SDK de Aplicativo dá suporte ao MAM sem registro__ Desenvolvedores de aplicativos podem usar o componente Xamarin do SDK de Aplicativo do Intune para habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Xamarin para Android e iOS. Encontre o Componente Xamarin do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Avisos

__O certificado de autenticação da Symantec não exige mais um Portal da Empresa assinado do Windows Phone 8 para upload__ O upload do certificado de autenticação da Symantec não exigirá mais um aplicativo de Portal da Empresa assinado do Windows Phone 8. O certificado pode ser carregado de forma independente.

###<a name="deprecations"></a>Desativações

__Suporte para o Portal da Empresa do Windows Phone 8__ O suporte para o Portal da Empresa do Windows Phone 8 será preterido. O suporte para as plataformas Windows Phone 8 e WinRT foi preterido em outubro de 2016. O suporte para o Portal da Empresa do Windows 8 também foi preterido em outubro de 2016.

## <a name="october-2016"></a>Outubro de 2016

### <a name="conditional-access-for-mobile-application-management"></a>Acesso condicional para gerenciamento de aplicativos móveis
Você poderá restringir o acesso ao Exchange Online somente para aplicativos que deem suporte a políticas de gerenciamento de aplicativos móveis do Intune, como o Outlook. [Esse novo recurso](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) combina perfeitamente com as políticas de MAM (gerenciamento de aplicativo móvel) do Intune, porque você pode bloquear o acesso a clientes de email interno ou outros aplicativos que não foram configurados com as políticas de MAM do Intune. Isso garante que os usuários estão acessando os dados da sua organização com aplicativos que podem ser protegidos usando o MAM do Intune. Você pode começar no gerenciamento de aplicativo móvel do Intune pelo portal do Azure. Procure a nova seção de Acesso Condicional na folha "Configurações".

### <a name="conditional-access-for-windows-pcs"></a>Acesso condicional para computadores Windows
Agora é possível criar políticas de acesso condicional por meio do console de administrador do Intune para impedir que computadores Windows acessem o [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) e o [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Você também pode criar políticas de acesso condicional para bloquear o acesso aos aplicativos da área de trabalho e universais do Office.

### <a name="android-for-work-support"></a>Suporte do Android for Work

> [!IMPORTANT]

> Embora possa implantar aplicativos do Android for Work com uma ação __Necessária__, você só pode implantar aplicativos como __Disponível__ se os grupos do Intune tiverem sido migrados para a nova experiência de grupos do Azure AD.

O Intune agora faz parte do programa AfW (Android for Work). Começaremos a distribuir o suporte para recursos do AfW a partir deste mês e continuaremos nos próximos meses. Observe que a implantação de aplicativos disponíveis do AfW utiliza a nova experiência de agrupamento e direcionamento. Contas de serviço do Intune recém-provisionadas poderão usar esse recurso quando o AfW estiver disponível para elas.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Leia o comunicado da Microsoft sobre o suporte do Intune para o Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Os tópicos sobre o Intune a seguir são novos ou foram atualizados com informações sobre o Android for Work:

Para profissionais de TI:
- [Configurar o Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
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

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

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

Os usuários finais de dispositivos não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em dispositivos Android, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso. Para saber mais, consulte [Restringir o acesso com base no dispositivo, na rede e no risco do aplicativo](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa

__Android__

<p style="margin-left: 40px">**Acréscimo de “Notificações” ao Portal da Empresa para Android**<br/>
<p style="margin-left: 40px">Um novo ícone de Notificações foi acrescentado ao Portal da Empresa para Android na home page. Tocar nesse ícone acessará a página Notificações, que mostra a seus usuários finais todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, a atualização de registro e a ativação de registro. O aplicativo de Portal da Empresa para iOS já tem essa experiência de notificações. Ter a nova página de Notificações significa que o usuário não verá a página Configuração de Acesso da Empresa sempre que iniciar ou retomar o Portal da Empresa, contanto que o dispositivo já esteja registrado. Se você criar suas próprias diretrizes para o usuário final, convém atualizar a documentação para refletir essa alteração. Encontre capturas de tela atualizadas [aqui](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Alterações no suporte para o aplicativo do Portal da Empresa do iOS**<br/>
<p style="margin-left: 40px">Todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS agora devem usar a versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.
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
<p style="margin-left: 40px">O aplicativo de Portal da Empresa do Windows Phone 8.1 permite aos usuários finais enviar comentários sobre o aplicativo usando um novo botão "enviar comentários". Para localizar o botão, os usuários tocam no menu de "reticências" na parte inferior direita da tela do aplicativo de Portal da Empresa e em **enviar comentários**. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do aplicativo do Portal da Empresa para os usuários.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glossário do Intune</br>
Adicionamos um novo [tópico de glossário](https://docs.microsoft.com/intune/understand-explore/intune-glossary) na biblioteca para ajudá-lo a entender alguns dos termos usados no produto Intune.

## <a name="august-2016"></a>Agosto de 2016
### <a name="app-management"></a>Gerenciamento de aplicativos
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Aplicativos ocultados e mostrados para iOS 9.3__ Para dispositivos que executam o iOS 9.3 ou posterior, você pode usar a lista de aplicativos ocultados e exibidos na política de configuração geral do iOS para:
- Especificar uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
- Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Os aplicativos que você pode especificar incluem os dois aplicativos que você implantou e os aplicativos iOS nativos, como Mensagens e Anotações. Para obter detalhes, consulte [iOS policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune) (Configurações de política do iOS no Microsoft Intune)
<!---TFS 1279009 checked--->
__Política de aplicativos permitidos e bloqueados para dispositivos Samsung KNOX__ Agora você pode configurar uma política personalizada para dispositivos Samsung KNOX que permite que você crie um dos seguintes procedimentos:
- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Mesmo se instalado, um aplicativo definido na lista de bloqueados não pode ser ativado no dispositivo.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Nenhum outro aplicativo pode ser instalado da loja.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX.
Para obter detalhes, consulte [Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Novos aplicativos compatíveis com políticas de MAM (gerenciamento de aplicativo móvel)__ O aplicativo do Yammer para [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) é compatível com as [políticas de MAM (gerenciamento de aplicativo móvel) do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), esteja o dispositivo registrado ou não.

Para obter uma lista completa de aplicativos compatíveis com MAM, visite o site [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) (Parceiros de aplicativos do Microsoft Intune).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Aplicativos do Visualizador do Intune__ Com o lançamento do novo aplicativo de RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do Visualizador do Intune, é recomendável usar o novo [aplicativo do Rights Management (RMS sharing) para o Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança os arquivos corporativos em dispositivos Android. Quando o aplicativo do Visualizador do Intune não tiver mais suporte, ele será removido da Google Store e não estará disponível para uso futuro.

### <a name="device-management"></a>Gerenciamento de dispositivo
__Suporte para Android 7.0__ O Intune oferece suporte de "dia 0" para o próximo sistema de operacional Android 7.0 para dispositivos móveis.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Remoção pelo Google da funcionalidade de redefinição remota de senha em dispositivos Android 7.0
O Google está removendo a capacidade dos administradores de TI e usuários finais de redefinir remotamente a senha de dispositivos Android 7.0. Anteriormente, os administradores de TI podiam redefinir remotamente a senha de um usuário, e os usuários finais podiam redefinir suas senhas do site do Portal da Empresa.



### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa
__Site do Portal da Empresa__
- **Link de comentários do Portal da Empresa para a Microsoft** <br/>
O site de Portal da empresa permite que os usuários finais toquem em um novo link "Comentários" na parte inferior da página para enviar comentários à Microsoft sobre sua experiência com o site. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do site do Portal da Empresa para os usuários.
<!--- TFS 1313657 checked--->

__iOS__
- **Versão mínima do Managed Browser para iOS atualizada para 8.0**<br/>
O aplicativo Microsoft Intune Managed Browser para iOS foi atualizado para dar suporte a dispositivos que executam o iOS 8.0 ou posterior. Embora dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
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
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Alterações no suporte para o aplicativo do Portal da Empresa do iOS**<br/>
Em setembro, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

- **Versão mínima do Managed Browser para iOS atualizada para 8.0**<br/>
Em agosto, o Intune lançará um aplicativo Microsoft Intune Managed Browser atualizado para iOS que dará suporte apenas a dispositivos executando o iOS 8.0 ou posterior. Embora os dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253--->

- **Aplicativos de Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos a partir de setembro de 2016** <br/>
A partir de setembro de 2016, o Microsoft Intune encerrará o suporte para os aplicativos de Portal da Empresa do Microsoft Intune para as plataformas Windows Phone 8 e Windows 8. Atualize os dispositivos para Windows 8.1 e Windows Phone 8.1, e use os aplicativos de Portal da Empresa correspondentes dessas plataformas para continuar a distribuição de aplicativos para esses dispositivos.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Julho de 2016
### <a name="app-management"></a>Gerenciamento de aplicativos

__Melhorar a experiência de atualização de perfil de provisionamento de aplicativo__ Os aplicativos móveis de linha de negócios de iOS da Apple são criados com um perfil de provisionamento incluído e com assinatura por código com um certificado. Quando o aplicativo é executado em um dispositivo iOS, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.

A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Com essa atualização, o Intune fornece as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos se aproximando da expiração enquanto o certificado ainda for válido. Para obter mais informações, consulte [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Usar políticas de perfil de provisionamento para manter seus aplicativos de linha de negócios atualizados).
<!--- TFS 1280247--->

__O SDK do Xamarin para aplicativos do Intune está disponível__ O componente Xamarin do SDK do aplicativo do Intune permite que você habilite os recursos de gerenciamento do aplicativo móvel do Intune em seus aplicativos móveis iOS e Android criados com o Xamarin. Você pode encontrar o componente na [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou na [página do GitHub do Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Gerenciamento de dispositivo
__Limites de registro de dispositivo maiores__ O Intune aumentou o limite máximo de registro de dispositivo configurável de 5 para 15 dispositivos por usuário.
<!---TFS 1289896 --->

__Integração do TeamViewer para computadores Windows que executam o software cliente do Intune__
 A integração do [TeamViewer](https://www.teamviewer.com) para computadores Windows que executam o cliente do Intune permite que você estabeleça sessões de assistência remota com computadores Windows para ajudar a dar suporte a departamentos de suporte técnico para o usuário final. Compatível com o Windows 7, 8, 8.1 e o Windows 10. Para detalhes, consulte [Common Windows PC management tasks with the Microsoft Intune computer client](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) (Tarefas comuns de gerenciamento de computadores Windows com o cliente de computador do Microsoft Intune).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa

__Site do Portal da Empresa__
- **Experiência do usuário final melhorada ao registrar dispositivos Windows**<br/>
Quando você estiver usando o acesso condicional, as etapas de registro para o Windows 8.1, Windows 10 Desktop e Windows 10 Mobile serão esclarecidas no site do Portal da Empresa. Agora os usuários verão as etapas “Registro do dispositivo” e “Ingresso no local de trabalho”, tornando mais fácil que eles vejam o status de seu dispositivo e concluam o processo se enfrentarem uma falha de WPJ (Ingresso no local de trabalho). Também é esperado que as etapas separadas simplifiquem o processo de solução de problemas para os administradores de TI. Anteriormente, quando os usuários finais tentavam se registrar e todas as etapas de registro eram bem-sucedidas exceto pelo WPJ, o dispositivo registrado não aparecia na lista de dispositivos para a identificação dos usuários, causando confusão para os usuários.

__Android__
- **Aplicativo de Portal da Empresa para Android**<br/>
Se os usuários finais do Android virem uma mensagem de erro indicando que o dispositivo não tem um certificado necessário, eles poderão tocar no botão “Como resolver isso” para obter as [etapas](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) para instalar o certificado que está faltando. Se os usuários concluírem as etapas, mas virem uma mensagem de erro adicional de “certificado faltando”, será solicitado que eles entrem em contato com o administrador de TI e forneçam este [link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), que contém as etapas que os administradores de TI podem usar para corrigir o problema do certificado.

- **Restringir instalações de aplicativo carregado por sideload a dispositivos registrados**<br/>
Os dispositivos Android não podem mais instalar aplicativos por meio do site do Portal da Empresa a menos que os dispositivos tenham sido registrados no Intune usando o aplicativo Portal da Empresa do Intune para Android.
<!---TFS 1299082--->

__iOS__
- **Alterações nas contas dos Gerenciadores de Registro de Dispositivo no aplicativo do Portal da Empresa para iOS**<br/>
Para melhorar o desempenho e o dimensionamento, o Intune não mostra mais todos os dispositivos de DEM (Gerenciadores de Registro de Dispositivos) no painel **Meus Dispositivos** do aplicativo Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa.

O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune. Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados.

Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível. Para obter mais informações, consulte [Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivos no Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Alteração dos nomes dos recursos do Windows
- O [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) agora é conhecido como o **Windows Hello para Empresas**.
- [Proteção de dados empresariais](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) agora é conhecido como **Windows Information Protection**.

## <a name="june-2016"></a>Junho de 2016
### <a name="intune-service-health"></a>Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no Portal de gerenciamento do Office 365 em Integridade do Serviço. Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gerenciamento de aplicativos
- **Experiência de configuração de política de dados empresariais do Windows 10 aprimorada.** Fizemos aprimoramentos para a configuração de política de proteção de dados empresariais do Windows 10 em torno da criação de regras de aplicativo, especificando a definição de limites de rede e outras configurações de proteção de dados empresariais. Para saber mais, veja [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Criar uma política de EDP (proteção de dados empresariais) usando o Microsoft Intune).


### <a name="device-management"></a>Gerenciamento de dispositivos
- **configuração de política do Windows Defender para proteger contra aplicativos potencialmente indesejados.** Uma nova configuração do Windows Defender chamada **Detecção de Aplicativos Potencialmente Indesejados** foi adicionada à política de configuração geral para Windows 10 Desktop e Mobile. Você pode usar essa configuração para proteger os computadores Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado. Veja [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) (Configurações de política do Windows 10 no Microsoft Intune) para saber mais.
<!---TFS 1244478--->

### <a name="conditional-access"></a>Acesso condicional
- **Política de controle de acesso de rede do Cisco ISE para o Intune.**  Os clientes que usam o Cisco ISE (Identity Service Engine) 2.1 e também usam o Microsoft Intune podem definir uma política de controle de acesso de rede no ISE.

    Usando essa política, os dispositivos que precisam se conectar à rede usando Wi-Fi ou VPN devem atender às seguintes condições antes de terem permissão de acesso:

    * Deve ser gerenciado pelo Intune
    * Deve ser compatível com qualquer política de conformidade do Intune implantada

 Os usuários finais de dispositivos não compatíveis serão solicitados a registrar e corrigir quaisquer problemas de conformidade para obter acesso.
- **Acesso condicional para navegador.** Você pode definir uma política de acesso condicional para o [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) e o [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) para que eles somente possam ser acessados por navegadores da Web com suporte em dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **O Dynamics CRM Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Dynamics CRM no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Atualizações do Portal da Empresa do Intune

__Aplicativo de Portal da Empresa para Android__

- Quando os administradores aplicarem a nova política "Exigir que dispositivos não permitam a instalação de aplicativos de fontes desconhecidas (Android 4.0 +)”, os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "A instalação de fontes desconhecidas deve ser desabilitada." Os usuários precisam ir para **Configurações** > **Segurança** e desativar **Fontes desconhecidas**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores de TI aplicarem a nova política "Exigir que dispositivos tenham habilitado a verificação de aplicativos contra ameaças à segurança (Android 4.0 +)", os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "Verificar dispositivo contra ameaças à segurança". Os usuários precisam ir para **Configurações** > **Google** > **Segurança** e ativar **Verificar dispositivo contra ameaças à segurança**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre a mensagem e porque eles estão sendo solicitados a ativar a configuração.

- Quando os administradores aplicarem a nova política "Exigir que a depuração de USB esteja desabilitada (Android 4.2 +)", os usuários finais com dispositivos Android 4.2 ou posteriores verão a mensagem "A depuração de USB deve ser desabilitada". Os usuários precisam ir para **Configurações** > **Opções do desenvolvedor** e desativar **Depuração de USB**." Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores aplicarem a nova política "Nível mínimo de patch de segurança Android (Android 6.0 +)", os usuários finais com dispositivos Android 6.0 ou posteriores verão a mensagem "Este dispositivo não atende ao nível mínimo de patch de segurança Android". Os usuários precisarão instalar o patch de segurança necessário. Um link na mensagem de conformidade permite aos usuários obter [informações](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre como instalar o patch de segurança necessário e ver qual patch de segurança eles já têm instalado atualmente.

__Aplicativo de Portal da Empresa para iOS__

- Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Sincronizar o dispositivo iOS manualmente).

- O aplicativo de Portal da Empresa do Microsoft Intune para iOS foi atualizado para oferecer suporte à versão 8.0 e posteriores do iOS. Essa atualização significa que os usuários finais podem instalar o aplicativo do Portal da Empresa e registrar novos dispositivos no Intune somente se o dispositivo estiver executando o iOS versão 8.0 ou posterior. Usuários que já registraram dispositivos que estão executando uma versão sem suporte do iOS podem continuar usando o aplicativo de Portal da Empresa que está no dispositivo.


<!--HONumber=Jan17_HO1-->


