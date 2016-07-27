---
title: "Versões anteriores | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b812a3124c330a9b45378c99ee77959c8d7bc537
ms.openlocfilehash: b30ab535ac7d8b10e3feef52ab01a68ba8572dba


---

# Versões anteriores do Intune
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
- **Acesso condicional para navegador.** Você pode definir uma política de acesso condicional para o [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) e o [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) para que eles somente possam ser acessados por navegadores da Web com suporte em dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **O Dynamics CRM Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Dynamics CRM no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
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
- **SDK do MAM (gerenciamento de aplicativo móvel): Suporte à configuração de tamanho do PIN.** Você poderá especificar o tamanho do PIN para aplicativos de MAM como em um PIN de dispositivo. Isso exigirá que os usuários finais estejam de acordo com as novas restrições que você definir. Eles verão uma tela de PIN um pouco modificada para acomodar uma entrada maior. Para obter detalhes, consulte [MAM policy settings for Android](/intune/deploy-use/android-mam-policy-settings) (Configurações de política MAM para Android) e [MAM policy settings for iOS](/intune/deploy-use/ios-mam-policy-settings) (Configurações de política MAM para iOS).

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
Agora você pode exibir o [status](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) de suas políticas de gerenciamento de aplicativo para os usuários em seu locatário do AAD (Azure Active Directory). Isso inclui:
   - Dispositivos
   - Aplicativos no dispositivo

   Valores de status:

   **Check in feito**: indica que a política foi implantada para o usuário, e o aplicativo foi usado no contexto de trabalho e recebeu a política com êxito.

    **Check in não feito**: indica que a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.


- **Controles de MAM para impedir a sincronização de contatos do Outlook (Android).**
Uma nova configuração está disponível para o [gerenciamento de aplicativo móvel](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) sem registro de dispositivo. Essa configuração permite impedir que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos Android. Quando essa configuração for habilitada, os aplicativos selecionados não poderão mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, os aplicativos selecionados poderão salvar contatos no catálogo de endereços nativo. Quando você [apagar um dispositivo ou aplicativo remotamente](wipe-managed-company-app-data-with-Microsoft-Intune.md), os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Essa nova configuração tem suporte desde o início usando o aplicativo Outlook em dispositivos Android.

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

- **Tirar proveito do gerenciamento “aberto em” do iOS de dispositivos que são registrados em uma solução de MDM de terceiros** Você pode usar o seu fornecedor MDM (gerenciamento de dispositivo móvel) para tirar proveito do gerenciamento “aberto em” do iOS. Você pode definir as restrições nas definições de perfil da configuração e implantar o aplicativo usando [Manage data transfer between iOS apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) (Gerenciar transferência de dados entre aplicativos iOS).

     Essa abordagem tem dois benefícios principais:

     1. Os usuários devem fazer logon com sua conta de trabalho antes de obter acesso a todos os dados corporativos de outros aplicativos ou Serviços de Nuvem. Isso garante que as políticas de MAM (gerenciamento de aplicativo móvel) estejam em vigor quando os dados são acessados.

     2. Perfis de email gerenciado e outros aplicativos gerenciados implantados por meio de uma solução MDM de terceiros podem compartilhar arquivos e dados com os aplicativos que têm políticas de MAM do Intune.

- **Gerencie o aplicativo Microsoft Outlook com políticas MAM para dispositivos não registrados no Intune** Agora você pode gerenciar o aplicativo Microsoft Outlook em dispositivos que não estão registrados no Intune com a política de gerenciamento de aplicativos móveis do Intune. O aplicativo Microsoft Outlook atualizado com as funcionalidades MAM está disponível para ambos os dispositivos [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). Use as instruções no tópico [criar e implantar políticas de gerenciamento de aplicativo móvel](https://technet.microsoft.com/library/mt627829.aspx) para criar uma política de MAM.  


- **Políticas de configuração de aplicativo móvel oferecem mais flexibilidade para especificar detalhes do usuário para aplicativos iOS** Você pode fornecer as configurações de usuário que um aplicativo iOS poderá precisar quando for aberto. Por exemplo, você poderia fornecer uma porta de rede ou um nome de usuário. Para ver mais detalhes, consulte [Configure iOS apps with mobile app configuration policies in Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) (Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune).


- **Implantar o Adobe Reader para o Microsoft Intune para dispositivos iOS gerenciados pelo Intune em sua empresa** O aplicativo Adobe Reader para iOS agora pode ser gerenciado em dispositivos registrados com a política de gerenciamento de aplicativos móveis do Intune.

- **Garanta que os clipes da Web implantados sejam abertos em um navegador gerenciado** Você pode implantar clipes da Web direcionados que só podem ser abertos usando o navegador gerenciado em dispositivos iOS e Android. Por exemplo, você implanta links para recursos corporativos por meio do Portal da Empresa, e quando os usuários navegam para os links, eles abrem diretamente no navegador gerenciado em que eles são protegidos pela política de MAM. Para ver mais detalhes, consulte [Implantar aplicativos ](deploy-apps.md).


- **Localizar, gerenciar e distribuir aplicativos da Windows Store para Empresas para dispositivos Windows 10 do console do administrador do Intune** Suporte para a Windows Store para Empresas está disponível no Intune para ajudá-lo a encontrar, gerenciar e distribuir aplicativos para os dispositivos Windows 10 que você está gerenciando. A Windows Store para Empresas permite que você gerencie o processo de implantação e monitoramento desses aplicativos do console do administrador do Intune – o mesmo console que você usa para gerenciar seus outros aplicativos. Especificamente, a Windows Store para Empresas gerencia o conteúdo e licenciamento de "aplicativos licenciados online". Para obter detalhes, consulte [Manage apps you purchased from the Windows Store for Business](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) (Gerenciar aplicativos adquiridos na Windows Store para Empresas).


### Gerenciamento de dispositivo
- **A distribuição de certificados PFX para dispositivos iOS** Os administradores do Intune podem criar e implantar os certificados PFX do iOS para Wi-Fi, email e autenticação de VPN em dispositivos iOS. Esse recurso já está disponível para dispositivos Android e Windows 10. Para detalhes, consulte [Enable access to company resources using certificate profiles](secure-resource-access-with-certificate-profiles.md) (Habilitar o acesso aos recursos da empresa usando perfis de certificado).


- **Aplicar aplicativos e políticas para grupos de dispositivos diferentes com base na seleção da categoria de usuário** Os administradores do Intune agora podem definir categorias de dispositivo personalizado para os usuários selecionem durante o registro. Por exemplo, os administradores talvez queiram que os usuários especifiquem se eles estão registrando um dispositivo usado para "Caixa Registradora" ou "Caminhão de Entrega" ou "Sala de Estoque". A categoria selecionada fará com que o dispositivo se torne um membro de um grupo de dispositivo do Intune, que pode ser usado para implantar políticas e aplicativos diferentes para o dispositivo registrado. Para detalhes, consulte [Categorize devices with device group mapping](categorize-devices-with-device-group-mapping-in-microsoft-intune.md) (Categorizar os dispositivos com o mapeamento do grupo de dispositivos).

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

    Leia [Introdução às políticas de conformidade do dispositivo do Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) para obter mais detalhes sobre a configuração de integridade do dispositivo, pontos de dados coletados e relatório de atestado de integridade. Os [detalhes do serviço HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx) explicam o serviço com mais detalhes.

* **Gerenciamento de certificado e Política do Windows 10 Passport for Work** Com o Intune, você pode [fazer a integração com o Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), que é um método de entrada alternativo para o Windows 10 que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual. O Passport permite que você use um gesto de usuário para logon, em vez de uma senha. Um gesto do usuário pode ser um PIN simples, uma autenticação biométrica, como o Windows Hello, ou um dispositivo externo, como um leitor de impressão digital.

* **VPN para aplicativos específicos** Você pode selecionar os aplicativos que se conectam automaticamente à rede corporativa por VPN. Crie a lista de aplicativos ao configurar o perfil VPN, conforme descrito em Ajudar os usuários a se conectarem ao trabalho usando perfis VPN com o Microsoft Intune.

* **Suporte para Apagamento Completo do Windows 10** Agora você pode executar um apagamento remoto completo de dispositivos Windows 10 Desktop registrados no Intune através do console de administração do Intune. O apagamento completo do Windows 10 faz uma redefinição de fábrica do dispositivo.


### Atualização do VPP (Apple Volume Purchase Program)
O Intune agora pode ajudá-lo a [gerenciar aplicativos que você adquiriu pelo VPP (Apple Volume Purchase Program) para Empresas](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Isso inclui a sincronização de informações de licença entre a Apple e o Intune e controle de quantas cópias de cada aplicativo você implantou.

### Use números IMEI para identificar dispositivos corporativos
Agora você pode [importar números IMEI (Identidade de Equipamentos Móveis Internacional)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) em plataformas de dispositivos móveis para ajudar a identificar dispositivos móveis corporativos. Depois de registrados no Intune, os dispositivos com números IMEI importados são marcados como corporativos, que podem ser usados para a aplicação de políticas que são diferentes das que foram aplicadas a dispositivos de propriedade pessoal.

### Agora mais aplicativos são compatíveis com as políticas de MAM do Intune
Aplicativos adicionais de parceiros da Microsoft agora são compatíveis com políticas de MAM (gerenciamento de aplicativo móvel) do Intune (para dispositivos gerenciados pelo Intune):
* Box for EMM (da Box Inc) – somente iOS
* Adobe Reader (da Adobe) – somente Android
* Foxit PDF Reader (da Foxit Corporation) – iOS e Android


### O suporte do IE9 termina em janeiro
Iniciando em fevereiro de 2016, o Internet Explorer 9 não será mais suportado como um navegador oficial para acessar o site do portal da empresa do Microsoft Intune, o portal de contas do e o console de administração do Intune. Você precisará migrar para o Internet Explorer 10 ou posterior.


>[!div class="step-by-step"]

>[&larr; **Novidades do Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Jul16_HO3-->


