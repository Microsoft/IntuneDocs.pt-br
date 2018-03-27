---
title: Versões anteriores
description: ''
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: NOINDEX,NOFOLLOW
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 76e53cabba9b684170d659ae5b8ef884bfe9abaa
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="previous-intune-releases"></a>Versões anteriores do Intune

Esta página é uma lista dos anúncios feitos em [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>Julho de 2016

### <a name="app-management"></a>Gerenciamento de aplicativos

__Melhorar a experiência de atualização de perfil de provisionamento de aplicativo__ Os aplicativos móveis de linha de negócios de iOS da Apple são criados com um perfil de provisionamento incluído e com assinatura por código com um certificado. Quando o aplicativo é executado em um dispositivo iOS, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.

A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Com essa atualização, o Intune fornece as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos se aproximando da expiração enquanto o certificado ainda for válido. Para obter mais informações, consulte [Usar políticas de perfil de provisionamento móvel para manter seus aplicativos de linha de negócios atualizados](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__O SDK do Xamarin para aplicativos do Intune está disponível__ O componente Xamarin do SDK do aplicativo do Intune permite que você habilite os recursos de gerenciamento do aplicativo móvel do Intune em seus aplicativos móveis iOS e Android criados com o Xamarin. Você pode encontrar o componente na [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou na [página do GitHub do Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Gerenciamento de dispositivos
__Limites de registro de dispositivo maiores__ O Intune aumentou o limite máximo de registro de dispositivo configurável de 5 para 15 dispositivos por usuário.
<!---TFS 1289896 --->

__Integração do TeamViewer para computadores Windows que executam o software cliente do Intune__
[TeamViewer](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa

__Site do Portal da Empresa__
- **Experiência do usuário final melhorada ao registrar dispositivos Windows**<br/>
Quando você estiver usando o acesso condicional, as etapas de registro para o Windows 8.1, Windows 10 Desktop e Windows 10 Mobile serão esclarecidas no site do Portal da Empresa. Agora os usuários verão as etapas “Registro do dispositivo” e “Ingresso no local de trabalho”, tornando mais fácil que eles vejam o status de seu dispositivo e concluam o processo se enfrentarem uma falha de WPJ (Ingresso no local de trabalho). Também é esperado que as etapas separadas simplifiquem o processo de solução de problemas para os administradores de TI. Anteriormente, quando os usuários finais tentavam se registrar e todas as etapas de registro eram bem-sucedidas exceto pelo WPJ, o dispositivo registrado não aparecia na lista de dispositivos para a identificação dos usuários, causando confusão para os usuários.

__Android__
- **Aplicativo de Portal da Empresa para Android**<br/>
Se os usuários finais do Android virem uma mensagem de erro indicando que o dispositivo não tem um certificado necessário, eles poderão tocar no botão “Como resolver isso” para obter as [etapas](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), que contém os passos que os administradores de TI podem seguir para corrigir o problema do certificado.

- **Restringir instalações de aplicativo carregado por sideload a dispositivos registrados**<br/>
Os dispositivos Android não podem mais instalar aplicativos por meio do site do Portal da Empresa a menos que os dispositivos tenham sido registrados no Intune usando o aplicativo Portal da Empresa do Intune para Android.
<!---TFS 1299082--->

__iOS__
- **Alterações nas contas dos Gerenciadores de Registro de Dispositivo no aplicativo do Portal da Empresa para iOS**<br/>
Para melhorar o desempenho e o dimensionamento, o Intune não mostra mais todos os dispositivos de DEM (Gerenciadores de Registro de Dispositivos) no painel **Meus Dispositivos** do aplicativo Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa.

O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados pode ser executado apenas no console de administração do Intune. Além disso, o Intune está preterindo o uso de contas de DEM com o Programa de Registro de Dispositivo da Apple ou com a ferramenta Apple Configurator. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados.

Use contas de DEM somente quando o registro sem usuário para dispositivos compartilhados estiver indisponível. Para obter mais informações, consulte [Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivos no Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Alteração dos nomes dos recursos do Windows
- O [Microsoft Passport for Windows](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) agora é conhecido como o **Windows Hello para Empresas**.
- [Proteção de dados empresariais](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) agora é conhecido como **Windows Information Protection**.


## <a name="june-2016"></a>Junho de 2016
### <a name="intune-service-health"></a>Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no Portal de gerenciamento do Office 365 em Integridade do Serviço. Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gerenciamento de aplicativos
- **Experiência de configuração de política de dados empresariais do Windows 10 aprimorada.** Fizemos aprimoramentos para a configuração de política de proteção de dados empresariais do Windows 10 em torno da criação de regras de aplicativo, especificando a definição de limites de rede e outras configurações de proteção de dados empresariais. Para saber mais, veja [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Criar uma política de EDP (proteção de dados empresariais) usando o Microsoft Intune).


### <a name="device-management"></a>Gerenciamento de dispositivos
- **configuração de política do Windows Defender para proteger contra aplicativos potencialmente indesejados.** Uma nova configuração do Windows Defender chamada **Detecção de Aplicativos Potencialmente Indesejados** foi adicionada à política de configuração geral para Windows 10 Desktop e Mobile. Você pode usar essa configuração para proteger os computadores Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado. Veja [Windows 10 policy settings in Microsoft Intune](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune) (Configurações de política do Windows 10 no Microsoft Intune) para saber mais.
<!---TFS 1244478--->

### <a name="conditional-access"></a>Acesso condicional
- **Política de controle de acesso de rede do Cisco ISE para o Intune.**  Os clientes que usam o Cisco ISE (Identity Service Engine) 2.1 e também usam o Microsoft Intune podem definir uma política de controle de acesso de rede no ISE.

    Usando essa política, os dispositivos que precisam se conectar à rede usando Wi-Fi ou VPN devem atender às seguintes condições antes de terem permissão de acesso:

    * Deve ser gerenciado pelo Intune
    * Devem ser compatíveis com qualquer política de conformidade do Intune implantada

 Os usuários finais de dispositivos não compatíveis serão solicitados a registrar e corrigir quaisquer problemas de conformidade para obter acesso.
- **Acesso condicional para navegador.** Você pode definir uma política de acesso condicional para o [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) para que eles somente possam ser acessados por navegadores da Web com suporte em dispositivos Android e iOS gerenciados e em conformidade. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **O Dynamics CRM Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e em conformidade. Os usuários finais que tentarem entrar no aplicativo móvel Dynamics CRM no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Atualizações do Portal da Empresa do Intune

__Aplicativo de Portal da Empresa para Android__

- Quando os administradores aplicarem a nova política "Exigir que dispositivos não permitam a instalação de aplicativos de fontes desconhecidas (Android 4.0 +)”, os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "A instalação de fontes desconhecidas deve ser desabilitada." Os usuários precisam ir para **Configurações** > **Segurança** e desativar **Fontes desconhecidas**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/intune-user-help/you-are-asked-to-turn-off-unknown-sources-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores de TI aplicarem a nova política "Exigir que dispositivos tenham habilitado a verificação de aplicativos contra ameaças à segurança (Android 4.0 +)", os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "Verificar dispositivo contra ameaças à segurança". Os usuários precisam ir para **Configurações** > **Google** > **Segurança** e ativar **Verificar dispositivo contra ameaças à segurança**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre a mensagem e porque eles estão sendo solicitados a ativar a configuração.

- Quando os administradores aplicarem a nova política "Exigir que a depuração de USB esteja desabilitada (Android 4.2 +)", os usuários finais com dispositivos Android 4.2 ou posteriores verão a mensagem "A depuração de USB deve ser desabilitada". Os usuários precisam ir para **Configurações** > **Opções do desenvolvedor** e desativar **Depuração de USB**." Um link na mensagem de conformidade permite aos usuários obter mais [informações](/intune-user-help/you-are-asked-to-turn-off-usb-debugging-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores aplicarem a nova política "Nível mínimo de patch de segurança Android (Android 6.0 +)", os usuários finais com dispositivos Android 6.0 ou posteriores verão a mensagem "Este dispositivo não atende ao nível mínimo de patch de segurança Android". Os usuários precisarão instalar o patch de segurança necessário. Um link na mensagem de conformidade permite aos usuários obter [informações](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre como instalar o patch de segurança necessário e ver qual patch de segurança eles já têm instalado atualmente.

__Aplicativo de Portal da Empresa para iOS__

- Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your iOS device manually](/intune-user-help/sync-your-device-manually-ios) (Sincronizar o dispositivo iOS manualmente).

- O aplicativo de Portal da Empresa do Microsoft Intune para iOS foi atualizado para oferecer suporte à versão 8.0 e posteriores do iOS. Essa atualização significa que os usuários finais poderão instalar o aplicativo do Portal da Empresa e registrar novos dispositivos no Intune somente se o dispositivo estiver executando o iOS versão 8.0 ou posterior. Usuários que já registraram dispositivos que estão executando uma versão sem suporte do iOS podem continuar usando o aplicativo de Portal da Empresa que está no dispositivo.

## <a name="may-2016"></a>Maio de 2016
Todos esses recursos também têm suporte para implantações híbridas (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a página [Hybrid What’s New](https://technet.microsoft.com/library/mt718155.aspx) (Novidades do Híbrido).

### <a name="documentation"></a>Documentação
Bem-vindo à versão de preview do [docs.microsoft.com](https://docs.microsoft.com/intune)!
Isso é uma plataforma de conteúdo moderno e completamente novo projetada para tornar mais fácil para você, nosso cliente, entender e usar o Intune.
Para ler sobre todos os novos recursos, consulte [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Apresentando o docs.microsoft.com)

### <a name="intune-service-health"></a>Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) em **Integridade do Serviço**.
Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gerenciamento de aplicativos
- **SDK de MAM: suporte à configuração de tamanho do PIN.** Você poderá especificar o tamanho do PIN para aplicativos de MAM como em um PIN de dispositivo. Isso exigirá que os usuários finais estejam de acordo com as novas restrições que você definir. Eles verão uma tela de PIN um pouco modificada para acomodar uma entrada maior. Para obter detalhes, consulte [MAM policy settings for Android](/intune-classic/deploy-use/ios-mam-policy-settings) (Configurações da política MAM para Android).

- **Skype for Business para iOS e Android.** Agora, você pode gerenciar o Skype for Business com [MAM sem políticas de registro](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.

- **Novos aplicativos disponíveis para gerenciamento com políticas de MAM.** Os aplicativos Microsoft Word, Excel e PowerPoint para Android agora podem ser associados com as políticas MAM em dispositivos que não estão registrados com o Intune. Para ver a lista completa de aplicativos com suporte, vá para a galeria de aplicativos móveis do Microsoft Intune na página [Microsoft Intune application partners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) (Parceiros de aplicativos do Microsoft Intune).


### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa

#### <a name="android-company-portal-app"></a>Aplicativo Android do Portal da Empresa
- **Notificações do sistema do usuário final**: os usuários finais agora verão notificações do sistema do aplicativo do Portal da Empresa do Android quando registram seus dispositivos ou removerem seus dispositivos do Portal da Empresa.

- **Alterações nas contas dos Gerenciadores de Registro de Dispositivo no aplicativo do Portal da Empresa para Android.** Para melhorar o desempenho e o dimensionamento, o Intune não mostrará mais todos os dispositivos de DEM (Gerenciadores de Registro do Dispositivo) no painel Meus Dispositivos do aplicativo do Portal da Empresa do Android. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa. O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune.

#### <a name="company-portal-website"></a>Site do Portal da Empresa
- **Site do Portal da Empresa: a faixa de identificação de dispositivo fornecerá mais informações aos usuários finais.** Os usuários finais agora poderão identificar mais facilmente o dispositivo que selecionaram ao usarem o site do Portal da Empresa. Se o dispositivo errado for selecionado, eles poderão selecionar o dispositivo correto tocando no link **Toque aqui**, na faixa de identificação da página inicial.

### <a name="service-deprecation"></a>Serviço preterido
- **Aplicativos do Visualizador do Intune.** Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
    - Visualizador de AV do Intune
    - Visualizador de PDF do Intune
    - Visualizador de imagem do Intune para Android no Google Play

  Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o aplicativo RMS sharing (com links para documentação).

- **Remoção de direcionamento de grupo personalizado para regras de notificação.**
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de 1º de junho de 2016, direcionar grupos criados pelo usuário não terá mais suporte.

    Hoje, para direcionar uma regra de notificação a um grupo criado no console de administração do Microsoft Intune, você realizaria as seguintes etapas:

    No espaço de trabalho **Administrador**, clique em **Regras de Notificação** > **Criar Nova Regra**

    Na etapa dois do assistente Criar Regra de Notificação, selecione os grupos de dispositivos nos quais a regra será aplicada. Nesta etapa, “selecionar grupos de dispositivos”, está sendo removido do Console do Intune.

    A linha do tempo preliminar para essa alteração é a seguinte:
    - Em junho de 2016 novos locatários não verão a etapa dois do assistente Criação de Regra de Notificação. Os locatários existentes não são afetados.
    - Em torno de agosto de 2016, alguns locatários existentes não verão "selecionar grupos de dispositivo" no assistente.
    - Em torno de outubro de 2016, esperamos que todos os locatários não verão "selecionar grupos de dispositivo" no assistente.


- **Alterações no suporte para o aplicativo do Portal da Empresa do iOS**. Nos próximos meses, haverá uma atualização para o aplicativo de Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 8.0 ou posterior. Os usuários não poderão registrar novos dispositivos que executam versões anteriores à iOS 8.0. Dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e, por um período limitado, poderão continuar usando o aplicativo do Portal da Empresa. No entanto, os dispositivos devem estar no iOS 8.0 ou posterior para acessar as versões mais recentes do aplicativo do Portal da Empresa. É recomendável notificar os usuários para atualizar para o iOS 8.0 ou posterior para que eles se beneficiem com os novos recursos do Intune.  


## <a name="april-2016"></a>Abril de 2016
Todos esses recursos também têm suporte para clientes híbridos (Configuration Manager integrado ao Intune).

### <a name="app-management"></a>Gerenciamento de aplicativos
- **Conformidade de usuário do MAM.**
Agora você pode exibir o [status](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) de suas políticas de gerenciamento de aplicativo para os usuários em seu locatário do AAD (Azure Active Directory). Isso inclui:
   - Dispositivos
   - Aplicativos no dispositivo

   Valores de status:

   **Check in feito**: indica que a política foi implantada para o usuário, e o aplicativo foi usado no contexto de trabalho e recebeu a política com êxito.

    **Check in não feito**: indica que a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.


- **Controles de MAM para impedir a sincronização de contatos do Outlook (Android).**
Uma nova configuração está disponível para [gerenciamento de aplicativos móveis](/intune-classic/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), os contatos que já foram salvos no catálogo de endereços nativos serão removidos. Essa nova configuração tem suporte desde o início usando o aplicativo Outlook em dispositivos Android.

### <a name="device-management"></a>Gerenciamento de dispositivos
- **Identificação de número de telefone para dispositivos de propriedade da empresa.** Os telefones categorizadas como "Empresariais" agora são identificados com o número de telefone completo quando, por exemplo, você executa um relatório de inventário de dispositivo móvel. Os números de telefone BYOD (Traga seu próprio dispositivo) continuam a ser mascarados com ****, somente com os quatro últimos dígitos exibidos.


### <a name="company-portal-updates"></a>Atualizações do portal da empresa
**Aplicativo do portal da Empresa do Android** Os usuários que não tiverem registrado seus dispositivos no Intune e que não tenham o certificado correto instalado não conseguirão entrar no aplicativo Portal da Empresa do Android e verão a mensagem, "Você não pode entrar porque o dispositivo não tem um certificado necessário". A mensagem inclui um link de "Como resolver o problema" que os usuários podem tocar para ver instruções de como instalar o certificado. Para ver as etapas que os usuários finais devem seguir para resolver o problema, consulte [Your device is missing a required certificate](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) (O dispositivo não tem um certificado necessário).

**Aplicativo do portal da Empresa do iOS** Foi adicionado suporte para a ação “puxe para atualizar” para atualizar o conteúdo na tela inicial, que inclui os aplicativos listados, dispositivos listados e informações de contato de TI. A ação “puxe para atualizar” não verifica as informações de conformidade ou política. Para fazer isso, selecione o bloco do dispositivo atual e toque no botão **Sincronizar**.

**Aplicativo do portal da Empresa do Windows 10 Mobile e Windows Phone 8.1** Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) (Sincronizar o dispositivo manualmente para acelerar as instalações de aplicativos).

**Site do Portal da Empresa** Quando os usuários do Windows 10 Mobile e do Windows Phone 8.1 estiverem instalando aplicativos de linha de negócios, eles verão os novos status a seguir, que fornecem mais detalhes sobre o status da instalação:

* **Aguardando o dispositivo sincronizar** – o usuário tocou em "Instalar" e agora o dispositivo tenta sincronizar com a infraestrutura do Intune. A sincronização é necessária para que a instalação possa ser concluída. A mensagem "Aguardando o dispositivo sincronizar" também é um link que os usuários podem tocar para ver [instruções](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) de como sincronizar os dispositivos manualmente com o Intune, quando o processo de sincronização está demorando muito ou fica paralisado.
* **Baixando** – solicitação de download do usuário está sendo processada e o dispositivo está baixando e instalando o aplicativo.

Antes desses status serem adicionados, os usuários ficavam confusos quando a instalação de um aplicativo demorava muito, pois eles viam apenas o status "Instalando", que podia permanecer na tela por horas. A adição dos novos status significa que, em vez de ligar para o suporte, agora os usuários podem tocar no link "Esperando o dispositivo sincronizar" e seguir as instruções para forçar o processo de sincronização a continuar.

>[!div class="step-by-step"]

>[&larr; **Novidades do Intune**](whats-new-in-microsoft-intune.md)    
