---
title: "Versões anteriores | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ffbb26f30c7801789a47d57ffed00696f5e6d81a
ms.openlocfilehash: 11e90ce994d17d9dcc62edba775dd0ab8110414e


---

# Versões anteriores do Intune
## Agosto de 2016
## Agosto de 2016
## Gerenciamento de aplicativos
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Aplicativos ocultados e mostrados para iOS 9.3
Para dispositivos supervisionados que executam o iOS 9.3 ou posterior, você pode usar a lista de aplicativos ocultados e exibidos na política de configuração geral do iOS para:
- Especificar uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
- Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Os aplicativos que você pode especificar incluem os dois aplicativos que você implantou e os aplicativos iOS nativos, como Mensagens e Anotações. Para obter detalhes, consulte [iOS policy settings in Microsoft Intune]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune) (Configurações de política do iOS no Microsoft Intune)
<!---TFS 1279009 checked--->
### Política de aplicativos permitidos e bloqueados para dispositivos Samsung KNOX
Agora você pode configurar uma política personalizada para dispositivos Samsung KNOX que permite que você crie um dos seguintes procedimentos:
- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Mesmo se instalado, um aplicativo definido na lista de bloqueados não pode ser ativado no dispositivo.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Nenhum outro aplicativo pode ser instalado da loja.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX.
Para obter detalhes, consulte [Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->
### Novos aplicativos compatíveis com políticas de MAM (Gerenciamento de Aplicativo Móvel)
O aplicativo do Yammer para [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) é compatível com as [políticas de MAM (gerenciamento de Aplicativo Móvel) do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), esteja o dispositivo registrado ou não.

Para obter uma lista completa de aplicativos compatíveis com MAM, visite o site [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) (Parceiros de aplicativos do Microsoft Intune).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Aplicativos do Visualizador do Intune
Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do Visualizador do Intune, é recomendável usar o novo [aplicativo do Rights Management (RMS sharing) para o Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança os arquivos corporativos em dispositivos Android. Quando o aplicativo do Visualizador do Intune não tiver mais suporte, ele será removido da Google Store e não estará disponível para uso futuro.

## Gerenciamento de dispositivos
### Suporte do Android 7.0
O Intune oferece suporte de "dia 0" para o próximo sistema de operacional Android 7.0 para dispositivos móveis.
<!---TFS 1262053--->
### Remoção pelo Google da funcionalidade de redefinição remota de senha em dispositivos Android 7.0
O Google está removendo a capacidade dos administradores de TI e usuários finais de redefinir remotamente a senha de dispositivos Android 7.0. Anteriormente, os administradores de TI podiam redefinir remotamente a senha de um usuário, e os usuários finais podiam redefinir suas senhas do site do Portal da Empresa.



## Atualizações do Portal da Empresa
### Site do Portal da Empresa
- **Link de comentários do Portal da Empresa para a Microsoft** <br/>
O site de Portal da empresa permite que os usuários finais toquem em um novo link "Comentários" na parte inferior da página para enviar comentários à Microsoft sobre sua experiência com o site. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do site do Portal da Empresa para os usuários.
<!--- TFS 1313657 checked--->

### iOS
- **Versão mínima do Managed Browser do iOS atualizada para 8.0**<br/>
O aplicativo Microsoft Intune Managed Browser para iOS foi atualizado para dar suporte a dispositivos que executam o iOS 8.0 ou posterior. Embora dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253 checked--->

## O que está por vir

### suporte para iOS 10
O Intune terá suporte completo para o iOS 10. Mais informações serão fornecidas após o lançamento público do iOS 10.

### Transição de grupos do Intune para os grupos do Azure Active Directory a partir de setembro de 2016
O Intune está criando uma nova experiência de gerenciamento de grupos que usa os grupos de segurança do AAD (Azure Active Directory) como grupos de usuários e de dispositivos no Intune. Esses grupos serão usados para todo o gerenciamento de grupo, implantação de política e implantação de perfil **quando lançarmos o novo portal de administração do Intune baseado no Azure**.

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

### Adição de 'Notificações' ao Portal da Empresa para Android
Lançaremos uma atualização para o Portal da Empresa para Android em setembro que apresentará um novo ícone **Notificações** na home page. Tocar nesse ícone acessará a pagina **Notificações** que lhe mostrará ao seu usuário final todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, atualização de registro e ativação de registro. Se você também usar o aplicativo de Portal da Empresa do iOS, já verá a experiência de notificações. Com a introdução da página **Notificações**, você não verá a página **Configuração de Acesso da Empresa** sempre que iniciar ou retomar o Portal da Empresa para Android contanto que o dispositivo já esteja registrado. Ouvimos que muitos de vocês criaram diretrizes para usuário final e apreciariam um aviso antecipado quando for possível que suas diretrizes/capturas precisem ser atualizadas. Atualize sua documentação para refletir a alteração futura na experiência. Encontre capturas de tela atualizadas aqui: https://aka.ms/androidcpupdate.  

### Melhorias na maneira como os usuários finais do iOS obtêm seus aplicativos
As alterações a seguir estão sendo feitas em setembro nos blocos de aplicativos no aplicativo Portal da Empresa para iOS para encaminhar os usuários a diferentes modos de exibição em um único local, o site Portal da Empresa, para todos os seus aplicativos. Atualmente, as restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da app store sejam listados no aplicativo Portal da Empresa e exigem que os usuários acessem diferentes modos de exibição para localizar todos os seus aplicativos.

- Atualmente, o bloco **Aplicativos da Empresa** aponta para uma lista de todos os aplicativos na guia TODOS do site Portal da Empresa e continuará a funcionar da mesma maneira. O nome do bloco será alterado para **Todos os Aplicativos**.
- O bloco **Outros Aplicativos** aponta para um modo de exibição no aplicativo Portal da Empresa que lista todos os aplicativos que Apple permite que o aplicativo Portal da Empresa mostre. O nome do bloco será alterado para **Aplicativos em Destaque** e, ao tocar no bloco, os usuários são levados para a guia EM DESTAQUE do site Portal da Empresa.
-  O bloco **Categorias** aponta atualmente para um modo de exibição no aplicativo Portal da Empresa que lista categorias de aplicativos. O nome do bloco não será alterado, mas agora apontará para a guia CATEGORIAS do site Portal da Empresa. Você pode encontrar capturas de tela atualizadas [aqui](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Roteiro de nuvem
Mantenha-se informado sobre futuros desenvolvimentos do Intune com a [Estratégia de plataforma em nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviço preterido
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Alterações no suporte para o aplicativo Portal da Empresa do iOS**<br/>
Em setembro, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

- **Versão mínima do Managed Browser do iOS atualizada para 8.0**<br/>
Em agosto, o Intune lançará um aplicativo Microsoft Intune Managed Browser atualizado para iOS que dará suporte apenas a dispositivos executando o iOS 8.0 ou posterior. Embora os dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253--->

- **Aplicativos Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos** <br/>
A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para aplicativos do Portal da Empresa do Windows 8 e Windows Phone 8. O Microsoft Intune também preterirá o suporte para a plataforma Windows Phone 8. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8. Você pode continuar a gerenciar dispositivos Windows Phone 8 e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.
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

## Julho de 2016
### Gerenciamento de aplicativos
#### Melhorar a experiência de atualização de perfil de provisionamento de aplicativo
Os aplicativos móveis de linha de negócios de iOS da Apple são criados com um perfil de provisionamento incluído e com assinatura por código com um certificado. Quando o aplicativo é executado em um dispositivo iOS, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.

A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Com essa atualização, o Intune fornece as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos se aproximando da expiração enquanto o certificado ainda for válido. Para obter mais informações, consulte [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Usar políticas de perfil de provisionamento para manter seus aplicativos de linha de negócios atualizados).
<!--- TFS 1280247--->
#### O SDK do Xamarin para aplicativos do Intune está disponível
O componente Xamarin do SDK do aplicativo do Intune permite que você habilite os recursos de gerenciamento do aplicativo móvel do Intune em seus aplicativos móveis iOS e Android criados com o Xamarin. Você pode encontrar o componente na [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou na [página do GitHub do Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Gerenciamento de dispositivos
#### Limites de registro de dispositivo maior
O Intune aumentou o limite máximo de registro de dispositivo configurável de 5 para 15 dispositivos por usuário.
<!---TFS 1289896 --->

#### Integração do TeamViewer para computadores Windows que executam o software cliente do Intune
A integração do [TeamViewer](https://www.teamviewer.com) para computadores Windows que executam o cliente do Intune permite que você estabeleça sessões de assistência remota com computadores Windows para ajudar a dar suporte a departamentos de suporte técnico para o usuário final. Compatível com o Windows 7, 8, 8.1 e o Windows 10. Para detalhes, consulte [Common Windows PC management tasks with the Microsoft Intune computer client](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) (Tarefas comuns de gerenciamento de computadores Windows com o cliente de computador do Microsoft Intune).
<!---TFS 1284856--->

### Atualizações do Portal da Empresa
#### Site do Portal da Empresa
- **Experiência do usuário final melhorada ao registrar dispositivos Windows**<br/>
Quando você estiver usando o acesso condicional, as etapas de registro para o Windows 8.1, Windows 10 Desktop e Windows 10 Mobile serão esclarecidas no site do Portal da Empresa. Agora os usuários verão as etapas “Registro do dispositivo” e “Ingresso no local de trabalho”, tornando mais fácil que eles vejam o status de seu dispositivo e concluam o processo se enfrentarem uma falha de WPJ (Ingresso no local de trabalho). Também é esperado que as etapas separadas simplifiquem o processo de solução de problemas para os administradores de TI. Anteriormente, quando os usuários finais tentavam se registrar e todas as etapas de registro eram bem-sucedidas exceto pelo WPJ, o dispositivo registrado não aparecia na lista de dispositivos para a identificação dos usuários, causando confusão para os usuários.

#### Android
- **Aplicativo Android do Portal da Empresa**<br/>
Se os usuários finais do Android virem uma mensagem de erro indicando que o dispositivo não tem um certificado necessário, eles poderão tocar no botão “Como resolver isso” para obter as [etapas](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) para instalar o certificado que está faltando. Se os usuários concluírem as etapas, mas virem uma mensagem de erro adicional de “certificado faltando”, será solicitado que eles entrem em contato com o administrador de TI e forneçam este [link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), que contém as etapas que os administradores de TI podem usar para corrigir o problema do certificado.

- **Restringir instalações de aplicativo carregado por sideload a dispositivos registrados**<br/>
Os dispositivos Android não podem mais instalar aplicativos por meio do site do Portal da Empresa a menos que os dispositivos tenham sido registrados no Intune usando o aplicativo Portal da Empresa do Intune para Android.
<!---TFS 1299082--->

#### iOS
- **Muda para as contas de Gerenciadores de Registro de Dispositivos no aplicativo Portal da Empresa do iOS**<br/>
Para melhorar o desempenho e o dimensionamento, o Intune não mostra mais todos os dispositivos de DEM (Gerenciadores de Registro de Dispositivos) no painel **Meus Dispositivos** do aplicativo Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa.

O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune. Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados.

Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível. Para obter mais informações, consulte [Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivos no Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Alteração dos nomes dos recursos do Windows
- O [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) agora é conhecido como o **Windows Hello para Empresas**.
- [Proteção de dados empresariais](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) agora é conhecido como **Windows Information Protection**.

## Junho de 2016
### Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no Portal de gerenciamento do Office 365 em Integridade do Serviço. Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### Gerenciamento de aplicativos
- **Experiência aprimorada configuração de política de dados empresariais do Windows 10.** Fizemos aprimoramentos para a configuração de política de proteção de dados empresariais do Windows 10 em torno da criação de regras de aplicativo, especificando a definição de limites de rede e outras configurações de proteção de dados empresariais. Para saber mais, veja [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Criar uma política de EDP (proteção de dados empresariais) usando o Microsoft Intune).


### Gerenciamento de dispositivos
- **A configuração de política do Windows Defender para proteger contra aplicativos potencialmente indesejados.** Uma nova configuração do Windows Defender chamada **Detecção de Aplicativos Potencialmente Indesejados** foi adicionada à política de configuração geral para Windows 10 Desktop e Mobile. Você pode usar essa configuração para proteger os computadores Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado. Veja [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) (Configurações de política do Windows 10 no Microsoft Intune) para saber mais.
<!---TFS 1244478--->

### Acesso condicional
- **Política de controle de acesso de rede do Cisco ISE para o Intune.**  Os clientes que usam o Cisco ISE (Identity Service Engine) 2.1 e também usam o Microsoft Intune podem definir uma política de controle de acesso de rede no ISE.

    Usando essa política, os dispositivos que precisam se conectar à rede usando Wi-Fi ou VPN devem atender às seguintes condições antes de terem permissão de acesso:

    * Deve ser gerenciado pelo Intune
    * Deve ser compatível com qualquer política de conformidade do Intune implantada

 Os usuários finais de dispositivos não compatíveis serão solicitados a registrar e corrigir quaisquer problemas de conformidade para obter acesso.
- **Acesso condicional para navegador.** Você pode definir uma política de acesso condicional para o [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) e o [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) para que eles somente possam ser acessados por navegadores da Web com suporte em dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **O Dynamics CRM Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Dynamics CRM no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
<!---TFS1295358--->

##E Atualizações do Portal da Empresa

#### Aplicativo Android do Portal da Empresa

- Quando os administradores aplicarem a nova política "Exigir que dispositivos não permitam a instalação de aplicativos de fontes desconhecidas (Android 4.0 +)”, os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "A instalação de fontes desconhecidas deve ser desabilitada." Os usuários precisam ir para **Configurações** > **Segurança** e desativar **Fontes desconhecidas**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores de TI aplicarem a nova política "Exigir que dispositivos tenham habilitado a verificação de aplicativos contra ameaças à segurança (Android 4.0 +)", os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "Verificar dispositivo contra ameaças à segurança". Os usuários precisam ir para **Configurações** > **Google** > **Segurança** e ativar **Verificar dispositivo contra ameaças à segurança**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre a mensagem e porque eles estão sendo solicitados a ativar a configuração.

- Quando os administradores aplicarem a nova política "Exigir que a depuração de USB esteja desabilitada (Android 4.2 +)", os usuários finais com dispositivos Android 4.2 ou posteriores verão a mensagem "A depuração de USB deve ser desabilitada". Os usuários precisam ir para **Configurações** > **Opções do desenvolvedor** e desativar **Depuração de USB**." Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores aplicarem a nova política "Nível mínimo de patch de segurança Android (Android 6.0 +)", os usuários finais com dispositivos Android 6.0 ou posteriores verão a mensagem "Este dispositivo não atende ao nível mínimo de patch de segurança Android". Os usuários precisarão instalar o patch de segurança necessário. Um link na mensagem de conformidade permite aos usuários obter [informações](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre como instalar o patch de segurança necessário e ver qual patch de segurança eles já têm instalado atualmente.

#### Aplicativo Portal da Empresa para iOS

- Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Sincronizar o dispositivo iOS manualmente).

- O aplicativo de Portal da Empresa do Microsoft Intune para iOS foi atualizado para oferecer suporte à versão 8.0 e posteriores do iOS. Essa atualização significa que os usuários finais podem instalar o aplicativo do Portal da Empresa e registrar novos dispositivos no Intune somente se o dispositivo estiver executando o iOS versão 8.0 ou posterior. Usuários que já registraram dispositivos que estão executando uma versão sem suporte do iOS podem continuar usando o aplicativo de Portal da Empresa que está no dispositivo.


## Maio de 2016

Todos esses recursos também têm suporte para implantações híbridas (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a página [Hybrid What’s New](https://technet.microsoft.com/en-us/library/mt718155.aspx) (Novidades do Híbrido).

### Documentação
Bem-vindo à versão de preview do [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Isso é uma plataforma de conteúdo moderno e completamente novo projetada para tornar mais fácil para você, nosso cliente, entender e usar o Intune.
Para ler sobre todos os novos recursos, consulte [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Apresentando o docs.microsoft.com)

### Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) em **Integridade do Serviço**.
Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Gerenciamento de aplicativos
- **SDK do MAM (gerenciamento de aplicativo móvel): Suporte à configuração de tamanho do PIN.** Você poderá especificar o tamanho do PIN para aplicativos de MAM como em um PIN de dispositivo. Isso exigirá que os usuários finais estejam de acordo com as novas restrições que você definir. Eles verão uma tela de PIN um pouco modificada para acomodar uma entrada maior. Para obter detalhes, consulte [Configurações de política de gerenciamento de aplicativo móvel de Android](/intune/deploy-use/android-mam-policy-settings) e [Configurações de política de gerenciamento de aplicativo móvel iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype for Business para iOS e Android.** Agora, você pode gerenciar o Skype for Business com [MAM sem políticas de registro](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.

- **Novos aplicativos disponíveis para gerenciamento com políticas MAM.** Os aplicativos Microsoft Word, Excel e PowerPoint para Android agora podem ser associados com as políticas MAM em dispositivos que não estão registrados com o Intune. Para ver a lista completa de aplicativos com suporte, vá para a galeria de aplicativos móveis do Microsoft Intune na página [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) (Parceiros de aplicativos do Microsoft Intune).


### Atualizações do Portal da Empresa

#### Aplicativo Android do Portal da Empresa
- **Notificações do sistema do usuário final**: os usuários finais agora verão notificações do sistema do aplicativo do Portal da Empresa do Android quando registram seus dispositivos ou removerem seus dispositivos do Portal da Empresa.

- **Muda para as contas de Gerenciadores de Registro do Dispositivo no aplicativo do Portal da Empresa do Android.** Para melhorar o desempenho e o dimensionamento, o Intune não mostrará mais todos os dispositivos de DEM (Gerenciadores de Registro do Dispositivo) no painel Meus Dispositivos do aplicativo do Portal da Empresa do Android. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa. O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune.

#### Site do Portal da Empresa
- **Site do Portal da Empresa: a faixa de identificação de dispositivo fornecerá mais informações aos usuários finais.** Os usuários finais agora poderão identificar mais facilmente o dispositivo que selecionaram ao usarem o site do Portal da Empresa. Se o dispositivo errado for selecionado, eles poderão selecionar o dispositivo correto tocando no link **Toque aqui**, na faixa de identificação da página inicial.

## O que está por vir
- **Integração da interface do usuário do Centro de Mensagens**. Como parte da migração do Intune para o [Portal de Gerenciamento do Office 365](https://portal.office.com/), começaremos a usufruir do Centro de Mensagens que ele tem para comunicar novos recursos e outras notificações. Além disso, ao instalar o aplicativo móvel de administração do Office 365 complementar, você pode receber notificações no telefone celular e encaminhar facilmente todas as mensagens para usuários ou para um alias de distribuição.
Começaremos a usar o Centro de Mensagens na versão de maio para notificá-lo quando as atualizações forem concluídas e passarem a incluir informações sobre os recursos novos e aprimorados do Intune. Confira o Centro de Mensagens hoje mesmo fazendo logon no [Portal de gerenciamento do Office 365](https://portal.office.com/) e escolhendo a opção CENTRO DE MENSAGENS no painel de navegação à esquerda.

- **Alterações nas contas dos Gerenciadores de Registro do Dispositivo**. Para melhorar o desempenho e o dimensionamento, o Intune não mostrará mais **todos** os dispositivos de DEM (Gerenciadores de Registro do Dispositivo) no painel **Meus Dispositivos** do aplicativo do Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa. O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune. Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados. Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível.

### Roteiro de nuvem
Mantenha-se informado sobre futuros desenvolvimentos do Intune com a [Estratégia de plataforma em nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviço preterido
- **Aplicativos do visualizador do Intune.** Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
    - Visualizador de AV do Intune
    - Visualizador de PDF do Intune
    - Visualizador de imagem do Intune para Android no Google Play

  Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o aplicativo RMS sharing (com links para documentação).

- **Remoção de aplicação de regras de notificação em grupo personalizado.**
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de 1º de junho de 2016, direcionar grupos criados pelo usuário não terá mais suporte.

    Hoje, para direcionar uma regra de notificação a um grupo criado no console de administração do Microsoft Intune, você realizaria as seguintes etapas:

    No espaço de trabalho **Administrador**, clique em **Regras de Notificação** > **Criar Nova Regra**

    Na etapa dois do assistente Criar Regra de Notificação, selecione os grupos de dispositivos nos quais a regra será aplicada. Nesta etapa, “selecionar grupos de dispositivos”, está sendo removido do Console do Intune.

    A linha do tempo preliminar para essa alteração é a seguinte:
    - Em junho de 2016 novos locatários não verão a etapa dois do assistente Criação de Regra de Notificação. Os locatários existentes não são afetados.
    - Em torno de agosto de 2016, alguns locatários existentes não verão "selecionar grupos de dispositivo" no assistente.
    - Em torno de outubro de 2016, esperamos que todos os locatários não verão "selecionar grupos de dispositivo" no assistente.


- **Alterações no suporte para o aplicativo do Portal da Empresa do iOS**. Nos próximos meses, haverá uma atualização para o aplicativo de Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 8.0 ou posterior. Os usuários não poderão registrar novos dispositivos que executam versões anteriores à iOS 8.0. Dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e, por um período limitado, poderão continuar usando o aplicativo do Portal da Empresa. No entanto, os dispositivos devem estar no iOS 8.0 ou posterior para acessar as versões mais recentes do aplicativo do Portal da Empresa. É recomendável notificar os usuários para atualizar para o iOS 8.0 ou posterior para que eles se beneficiem com os novos recursos do Intune.  


## Abril de 2016
Todos esses recursos também têm suporte para clientes híbridos (Configuration Manager integrado ao Intune).
### Gerenciamento de aplicativos
- **Conformidade de usuário do MAM.**
Agora você pode exibir o [status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) de suas políticas de gerenciamento de aplicativo para os usuários em seu locatário do AAD (Azure Active Directory). Isso inclui:
   - Dispositivos
   - Aplicativos no dispositivo

   Valores de status:

   **Check in feito**: indica que a política foi implantada para o usuário, e o aplicativo foi usado no contexto de trabalho e recebeu a política com êxito.

    **Check in não feito**: indica que a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.


- **Controles de MAM para impedir a sincronização de contatos do Outlook (Android).**
Uma nova configuração está disponível para o [gerenciamento de aplicativo móvel](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) sem registro de dispositivo. Essa configuração permite impedir que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos Android. Quando essa configuração for habilitada, os aplicativos selecionados não poderão mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, os aplicativos selecionados poderão salvar contatos no catálogo de endereços nativo. Quando você [apagar um dispositivo ou aplicativo remotamente](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Essa nova configuração tem suporte desde o início usando o aplicativo Outlook em dispositivos Android.

### Gerenciamento de dispositivos
- **Identificação de número de telefone para dispositivos de propriedade da empresa.** Os telefones categorizadas como "Empresariais" agora são identificados com o número de telefone completo quando, por exemplo, você executa um relatório de inventário de dispositivo móvel. Os números de telefone BYOD (Traga seu próprio dispositivo) continuam a ser mascarados com ****, somente com os quatro últimos dígitos exibidos.


### Atualizações do portal da empresa
**Aplicativo do portal da Empresa do Android** Os usuários que não tiverem registrado seus dispositivos no Intune e que não tenham o certificado correto instalado não conseguirão entrar no aplicativo Portal da Empresa do Android e verão a mensagem, "Você não pode entrar porque o dispositivo não tem um certificado necessário". A mensagem inclui um link de "Como resolver o problema" que os usuários podem tocar para ver instruções de como instalar o certificado. Para ver as etapas que os usuários finais devem seguir para resolver o problema, consulte [Your device is missing a required certificate](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) (O dispositivo não tem um certificado necessário).

**Aplicativo do portal da Empresa do iOS** Foi adicionado suporte para a ação “puxe para atualizar” para atualizar o conteúdo na tela inicial, que inclui os aplicativos listados, dispositivos listados e informações de contato de TI. A ação “puxe para atualizar” não verifica as informações de conformidade ou política. Para fazer isso, selecione o bloco do dispositivo atual e toque no botão **Sincronizar**.

**Aplicativo do portal da Empresa do Windows 10 Mobile e Windows Phone 8.1** Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) (Sincronizar o dispositivo manualmente para acelerar as instalações de aplicativos).

**Site do Portal da Empresa** Quando os usuários do Windows 10 Mobile e do Windows Phone 8.1 estiverem instalando aplicativos de linha de negócios, eles verão os novos status a seguir, que fornecem mais detalhes sobre o status da instalação:

* **Aguardando o dispositivo sincronizar** – o usuário tocou em "Instalar" e agora o dispositivo tenta sincronizar com a infraestrutura do Intune. A sincronização é necessária para que a instalação possa ser concluída. A mensagem "Aguardando o dispositivo sincronizar" também é um link que os usuários podem tocar para ver [instruções](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) de como sincronizar os dispositivos manualmente com o Intune, quando o processo de sincronização está demorando muito ou fica paralisado.
* **Baixando** – solicitação de download do usuário está sendo processada e o dispositivo está baixando e instalando o aplicativo.

Antes desses status serem adicionados, os usuários ficavam confusos quando a instalação de um aplicativo demorava muito, pois eles viam apenas o status "Instalando", que podia permanecer na tela por horas. A adição dos novos status significa que, em vez de ligar para o suporte, agora os usuários podem tocar no link "Esperando o dispositivo sincronizar" e seguir as instruções para forçar o processo de sincronização a continuar.


## Março de 2016
### O que há de novo a partir de 29 de março de 2016
Com exceção da atualização da política de configuração geral do Windows 10, todas as funcionalidades lançadas em 29 de março de 2016 também têm suporte para clientes híbridos (Configuration Manager integrado com o Intune). O suporte a configurações híbridas para a atualização de política de configuração geral do Windows 10 estará disponível em breve. Observe que alguns dessas funcionalidades podem exigir a versão mais recente do Configuration Manager.

### Gerenciamento de aplicativos
- **Controles de MAM para impedir a sincronização de contatos do Outlook (iOS).** Uma nova configuração está disponível para o gerenciamento de aplicativo móvel sem registro de dispositivo. Essa configuração permite impedir que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos iOS. Quando essa configuração for habilitada, o aplicativo não poderá mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, o aplicativo poderá salvar contatos no catálogo de endereços nativo. Quando você apagar um dispositivo seletivamente, os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Essa nova configuração tem suporte no aplicativo Outlook em dispositivos iOS. Para obter mais detalhes sobre essa e outras configurações, consulte [Create and deploy MAM policies](https://technet.microsoft.com/en-us/library/dn292747.aspx) (Criar e implantar políticas MAM).

### Controle de acesso
- **O Skype for Business Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o Skype for Business Online para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Skype for Business no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar. Para ver mais detalhes, consulte [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx) (Gerenciar o acesso ao Skype for Business Online).

### Gerenciamento de dispositivo
- **Suporte do Intune para iOS 9.3.** Em 21 de março, segunda-feira, a Apple anunciou a disponibilidade do iOS 9.3. Estávamos trabalhando duro para garantir que o Microsoft Intune seja compatível com a versão mais recente do sistema operacional de móvel da Apple e [temos prazer de anunciar que o Intune já dá suporte ao gerenciamento de dispositivos iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Todas as funcionalidades do Intune existentes atualmente disponíveis para gerenciar dispositivos iOS continuarão a funcionar perfeitamente quando os usuários atualizarem seus dispositivos para o iOS 9.3. Além disso, o iOS 9.3 também têm suporte para clientes híbridos a partir de hoje (Configuration Manager integrado ao Intune).

- **A política de configuração geral do Windows 10 agora contém configurações para gerenciar o Windows Defender em computadores Windows 10 registrados.** Para ver mais detalhes, consulte [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx) (Definições de política de configuração do Windows 10 no Microsoft Intune).


### Portal da empresa

- **Pacotes de aplicativos do Windows disponíveis diretamente do site de Portal da Empresa.** Usuários de computadores Windows 8, Windows 8.1 e Windows RT agora podem instalar pacotes de aplicativos do Windows (com a extensão .appx) diretamente do site Portal da Empresa. Anteriormente, você precisava implantar, ou os usuários tinham que instalar, o aplicativo Portal da Empresa em seus dispositivos para instalar aplicativos.

- **Os usuários podem bloquear remotamente seu dispositivo no site do Portal da Empresa.** Uma nova opção de Bloqueio Remoto foi adicionada no site Portal da Empresa para permitir que os usuários bloqueiem seus dispositivos remotamente usando o Portal, em caso de perda ou roubo do dispositivo. Consulte as [instruções do usuário final](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). A tabela a seguir lista o suporte às plataformas para bloqueio remoto do Intune Standalone e do Intune com o Configuration Manager.

|Plataforma | Detalhes do suporte|
|---------|----------------|
|Android |Com suporte|
|iOS |Com suporte|
|Windows 10 Mobile |Com suporte apenas se o telefone tiver uma senha definida|
|Windows 10 Desktop |Sem suporte|
|Windows Phone 8.1 |Com suporte apenas se o telefone tiver uma senha definida|
|Windows Phone 8.0 |Sem suporte|
|Computador (Windows 8.0 e anterior) |Sem suporte|
|Computador (Windows 8.1) |Sem suporte|

### O que há de novo a partir de 10 de março de 2016

### Gerenciamento de aplicativos

- **Tirar proveito do gerenciamento “aberto em” do iOS de dispositivos que são registrados em uma solução de MDM de terceiros** Você pode usar o seu fornecedor MDM (gerenciamento de dispositivo móvel) para tirar proveito do gerenciamento “aberto em” do iOS. Você pode definir as restrições nas definições de perfil da configuração e implantar o aplicativo usando [Manage data transfer between iOS apps](/intune/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune) (Gerenciar transferência de dados entre aplicativos iOS).

     Essa abordagem tem dois benefícios principais:

     1. Os usuários devem fazer logon com sua conta de trabalho antes de obter acesso a todos os dados corporativos de outros aplicativos ou Serviços de Nuvem. Isso garante que as políticas de MAM (gerenciamento de aplicativo móvel) estejam em vigor quando os dados são acessados.

     2. Perfis de email gerenciado e outros aplicativos gerenciados implantados por meio de uma solução MDM de terceiros podem compartilhar arquivos e dados com os aplicativos que têm políticas de MAM do Intune.

- **Gerencie o aplicativo Microsoft Outlook com políticas MAM para dispositivos não registrados no Intune** Agora você pode gerenciar o aplicativo Microsoft Outlook em dispositivos que não estão registrados no Intune com a política de gerenciamento de aplicativos móveis do Intune. O aplicativo Microsoft Outlook atualizado com as funcionalidades MAM está disponível para ambos os dispositivos [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). Use as instruções no tópico [criar e implantar políticas de gerenciamento de aplicativo móvel](https://technet.microsoft.com/library/mt627829.aspx) para criar uma política de MAM.  


- **Políticas de configuração de aplicativo móvel oferecem mais flexibilidade para especificar detalhes do usuário para aplicativos iOS** Você pode fornecer as configurações de usuário que um aplicativo iOS poderá precisar quando for aberto. Por exemplo, você poderia fornecer uma porta de rede ou um nome de usuário. Para ver mais detalhes, consulte [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) (Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune).


- **Implantar o Adobe Reader para o Microsoft Intune para dispositivos iOS gerenciados pelo Intune em sua empresa** O aplicativo Adobe Reader para iOS agora pode ser gerenciado em dispositivos registrados com a política de gerenciamento de aplicativos móveis do Intune.

- **Garanta que os clipes da Web implantados sejam abertos em um navegador gerenciado** Você pode implantar clipes da Web direcionados que só podem ser abertos usando o navegador gerenciado em dispositivos iOS e Android. Por exemplo, você implanta links para recursos corporativos por meio do Portal da Empresa, e quando os usuários navegam para os links, eles abrem diretamente no navegador gerenciado em que eles são protegidos pela política de MAM. Para ver mais detalhes, consulte [Implantar aplicativos ](/intune/deploy-use/deploy-apps).


- **Localizar, gerenciar e distribuir aplicativos da Windows Store para Empresas para dispositivos Windows 10 do console do administrador do Intune** Suporte para a Windows Store para Empresas está disponível no Intune para ajudá-lo a encontrar, gerenciar e distribuir aplicativos para os dispositivos Windows 10 que você está gerenciando. A Windows Store para Empresas permite que você gerencie o processo de implantação e monitoramento desses aplicativos do console do administrador do Intune – o mesmo console que você usa para gerenciar seus outros aplicativos. Especificamente, a Windows Store para Empresas gerencia o conteúdo e licenciamento de "aplicativos licenciados online". Para obter detalhes, consulte [Manage apps you purchased from the Windows Store for Business](/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune) (Gerenciar aplicativos adquiridos na Windows Store para Empresas).


### Gerenciamento de dispositivo
- **A distribuição de certificados PFX para dispositivos iOS** Os administradores do Intune podem criar e implantar os certificados PFX do iOS para Wi-Fi, email e autenticação de VPN em dispositivos iOS. Esse recurso já está disponível para dispositivos Android e Windows 10. Para detalhes, consulte [Enable access to company resources using certificate profiles](/intune/deploy-use/secure-resource-access-with-certificate-profiles) (Habilitar o acesso aos recursos da empresa usando perfis de certificado).


- **Aplicar aplicativos e políticas para grupos de dispositivos diferentes com base na seleção da categoria de usuário** Os administradores do Intune agora podem definir categorias de dispositivo personalizado para os usuários selecionem durante o registro. Por exemplo, os administradores talvez queiram que os usuários especifiquem se eles estão registrando um dispositivo usado para "Caixa Registradora" ou "Caminhão de Entrega" ou "Sala de Estoque". A categoria selecionada fará com que o dispositivo se torne um membro de um grupo de dispositivo do Intune, que pode ser usado para implantar políticas e aplicativos diferentes para o dispositivo registrado. Para detalhes, consulte [Categorize devices with device group mapping](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) (Categorizar os dispositivos com o mapeamento do grupo de dispositivos).

### Alterações e atualizações no Portal da Empresa da Microsoft
As alterações a seguir foram feitas ao Portal da Empresa nesta versão.

**Aplicativo Android do Portal da Empresa**

* Quando os usuários iniciam um aplicativo gerenciado pelo MAM (gerenciamento de aplicativo móvel), eles verão uma mensagem notificando que o aplicativo é gerenciado pela empresa. Os usuários agora podem tocar no link "Saiba Mais" para obter [mais informações](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) aqui sobre o que significa "aplicativos gerenciados". Eles também podem tocar em "Não Mostrar Novamente" para que a mensagem não apareçam quando iniciar o aplicativo.
* Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) para ver os detalhes.
* As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.


**Aplicativo Portal da Empresa para iOS**
* Quando os usuários iniciam um aplicativo gerenciado pelo MAM (gerenciamento de aplicativo móvel), eles verão uma mensagem notificando que o aplicativo é gerenciado pela empresa. Os usuários agora podem tocar no link "Saiba Mais" para obter [mais informações](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) aqui sobre o que significa "aplicativos gerenciados". Eles também podem tocar em "Não Mostrar Novamente" para que a mensagem não apareçam quando iniciar o aplicativo.
* Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) para ver os detalhes.
* As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.




## Fevereiro de 2016
### Alterações e atualizações no Portal da Empresa da Microsoft

As alterações a seguir foram feitas ao Portal da Empresa nesta versão.

#### Aplicativo Android do Portal da Empresa
- Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) para ver os detalhes.
- As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.

#### Aplicativo Portal da Empresa para iOS
 - Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) para ver os detalhes.

 - As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.


## Janeiro de 2016

### Usufrua dos recursos do Windows 10
* **Acesso condicional com o Serviço de Atestado de Integridade** Os administradores podem exibir o status do Atestado de Integridade do Dispositivo Windows 10 no console de administração do Intune. O atestado de integridade do dispositivo permite que o administrador garanta que os computadores cliente têm configurações confiáveis de BIOS, TPM e software de inicialização. Para dar suporte ao atestado de integridade do dispositivo, os dispositivos do cliente devem estar executando o Windows 10 com o TPM 2 habilitado. O atestado de integridade do dispositivo exibe o número de dispositivos habilitados para cada um dos seguintes:
    * Antimalware de inicialização antecipada
    * BitLocker
    * Inicialização Segura
    * Integridade do código

    Leia [Introdução às políticas de conformidade do dispositivo do Microsoft Intune](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) para obter mais detalhes sobre a configuração de integridade do dispositivo, pontos de dados coletados e relatório de atestado de integridade. Os [detalhes do serviço HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx) explicam o serviço com mais detalhes.

* **Gerenciamento de certificado e Política do Windows 10 Passport for Work** Com o Intune, você pode [fazer a integração com o Microsoft Passport for Work](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune), que é um método de entrada alternativo para o Windows 10 que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual. O Passport permite que você use um gesto de usuário para logon, em vez de uma senha. Um gesto do usuário pode ser um PIN simples, uma autenticação biométrica, como o Windows Hello, ou um dispositivo externo, como um leitor de impressão digital.

* **VPN para aplicativos específicos** Você pode selecionar os aplicativos que se conectam automaticamente à rede corporativa por VPN. Crie a lista de aplicativos ao configurar o perfil VPN, conforme descrito em Ajudar os usuários a se conectarem ao trabalho usando perfis VPN com o Microsoft Intune.

* **Suporte para Apagamento Completo do Windows 10** Agora você pode executar um apagamento remoto completo de dispositivos Windows 10 Desktop registrados no Intune através do console de administração do Intune. O apagamento completo do Windows 10 faz uma redefinição de fábrica do dispositivo.


### Atualização do VPP (Apple Volume Purchase Program)
O Intune agora pode ajudá-lo a [gerenciar aplicativos que você adquiriu pelo VPP (Apple Volume Purchase Program) para Empresas](/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Isso inclui a sincronização de informações de licença entre a Apple e o Intune e controle de quantas cópias de cada aplicativo você implantou.

### Use números IMEI para identificar dispositivos corporativos
Agora você pode [importar números IMEI (Identidade de Equipamentos Móveis Internacional)](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) em plataformas de dispositivos móveis para ajudar a identificar dispositivos móveis corporativos. Depois de registrados no Intune, os dispositivos com números IMEI importados são marcados como corporativos, que podem ser usados para a aplicação de políticas que são diferentes das que foram aplicadas a dispositivos de propriedade pessoal.

### Agora mais aplicativos são compatíveis com as políticas de MAM do Intune
Aplicativos adicionais de parceiros da Microsoft agora são compatíveis com políticas de MAM (gerenciamento de aplicativo móvel) do Intune (para dispositivos gerenciados pelo Intune):
* Box for EMM (da Box Inc) – somente iOS
* Adobe Reader (da Adobe) – somente Android
* Foxit PDF Reader (da Foxit Corporation) – iOS e Android


### O suporte do IE9 termina em janeiro
Iniciando em fevereiro de 2016, o Internet Explorer 9 não será mais suportado como um navegador oficial para acessar o site do portal da empresa do Microsoft Intune, o portal de contas do e o console de administração do Intune. Você precisará migrar para o Internet Explorer 10 ou posterior.


>[!div class="step-by-step"]

>[&larr; **Novidades do Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Oct16_HO1-->


