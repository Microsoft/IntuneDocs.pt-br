---
title: "Versões anteriores | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4dab832da4490c3df045d2c627b231028c92b25
ms.openlocfilehash: 3de5e57589a24600301e54a3b60eecb5321ff838


---

# <a name="previous-intune-releases"></a>Versões anteriores do Intune

Esta página é uma lista dos anúncios feitos em [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="may-2016"></a>Maio de 2016
Todos esses recursos também têm suporte para implantações híbridas (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a página [Hybrid What’s New](https://technet.microsoft.com/en-us/library/mt718155.aspx) (Novidades do Híbrido).

### <a name="documentation"></a>Documentação
Bem-vindo à versão de preview do [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Isso é uma plataforma de conteúdo moderno e completamente novo projetada para tornar mais fácil para você, nosso cliente, entender e usar o Intune.
Para ler sobre todos os novos recursos, consulte [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Apresentando o docs.microsoft.com)

### <a name="intune-service-health"></a>Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) em **Integridade do Serviço**.
Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gerenciamento de aplicativos
- **SDK de MAM: suporte à configuração de tamanho do PIN.** Você poderá especificar o tamanho do PIN para aplicativos de MAM como em um PIN de dispositivo. Isso exigirá que os usuários finais estejam de acordo com as novas restrições que você definir. Eles verão uma tela de PIN um pouco modificada para acomodar uma entrada maior. Para obter detalhes, consulte [Configurações de política de gerenciamento de aplicativo móvel de Android](/intune/deploy-use/android-mam-policy-settings) e [Configurações de política de gerenciamento de aplicativo móvel iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype for Business para iOS e Android.** Agora, você pode gerenciar o Skype for Business com [MAM sem políticas de registro](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.

- **Novos aplicativos disponíveis para gerenciamento com políticas de MAM.** Os aplicativos Microsoft Word, Excel e PowerPoint para Android agora podem ser associados com as políticas MAM em dispositivos que não estão registrados com o Intune. Para ver a lista completa de aplicativos com suporte, vá para a galeria de aplicativos móveis do Microsoft Intune na página [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) (Parceiros de aplicativos do Microsoft Intune).


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
Agora você pode exibir o [status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) de suas políticas de gerenciamento de aplicativo para os usuários em seu locatário do AAD (Azure Active Directory). Isso inclui:
   - Dispositivos
   - Aplicativos no dispositivo

   Valores de status:

   **Check in feito**: indica que a política foi implantada para o usuário, e o aplicativo foi usado no contexto de trabalho e recebeu a política com êxito.

    **Check in não feito**: indica que a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.


- **Controles de MAM para impedir a sincronização de contatos do Outlook (Android).**
Uma nova configuração está disponível para o [gerenciamento de aplicativo móvel](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) sem registro de dispositivo. Essa configuração permite impedir que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos Android. Quando essa configuração for habilitada, os aplicativos selecionados não poderão mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, os aplicativos selecionados poderão salvar contatos no catálogo de endereços nativo. Quando você [apagar um dispositivo ou aplicativo remotamente](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Essa nova configuração tem suporte desde o início usando o aplicativo Outlook em dispositivos Android.

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



<!--HONumber=Dec16_HO1-->


