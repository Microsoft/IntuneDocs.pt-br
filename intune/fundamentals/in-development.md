---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e099537bce6327e9a8991bc42f406e4abd3dfd2e
ms.sourcegitcommit: 6608dc70d01376e0cd90aa620a2fe01337f6a2f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260224"
---
# <a name="in-development-for-microsoft-intune---march-2020"></a>Em desenvolvimento para o Microsoft Intune – março de 2020

Para ajudá-lo em sua preparação e planejamento, esta página relaciona atualizações e recursos da interface do usuário do Intune que estão em desenvolvimento, mas ainda não foram liberados. Além das informações nesta página: 

- Se prevermos que você precisará agir antes de uma alteração, publicaremos uma postagem complementar no centro de mensagens do Office.
- Quando um recurso entra em produção, seja como versão prévia ou em disponibilidade geral, sua descrição vai desta página para [Novidades](whats-new.md).
- Esta página e a página [Novidades](whats-new.md) são atualizadas periodicamente. Volte a ela para verificar se há atualizações adicionais.
- Confira o [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para entregas estratégicas e linhas do tempo.

> [!NOTE]
> Esta página reflete nossas expectativas atuais sobre os recursos do Intune em uma versão futura. As datas e os recursos individuais podem mudar. Esta página não descreve todos os recursos em desenvolvimento.

**Feed RSS**: descubra quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Gerenciamento de aplicativos

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Redirecionar clipes da Web para o Microsoft Edge em dispositivos iOS/iPadOS<!-- 5455276 -->
Os clipes da Web, que atuam como aplicativos Web fixados em dispositivos iOS/iPadOS, precisarão ser atualizados. Clipes da Web implantados recentemente serão abertos no Microsoft Edge em vez do Intune Managed Browser se for necessário abrir em um navegador protegido. Você precisa redirecionar os clipes da Web preexistentes para garantir que eles sejam abertos no Microsoft Edge em vez do Managed Browser.

### <a name="macos-and-ios-company-portal-updates---5779439-5780234----"></a>Atualizações do Portal da Empresa para macOS e iOS<!-- 5779439, 5780234  -->
O painel Perfil do Portal da Empresa para macOS e iOS será atualizado para incluir o botão sair. Além disso, essa atualização incluirá aprimoramentos da interface do usuário no painel Perfil no Portal da Empresa para macOS. Para obter mais informações sobre o Portal da Empresa, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](~/apps/company-portal-app.md).

### <a name="updates-to-branding-and-customization-pane---5236032---"></a>Atualizações no painel de Identidade visual e personalização<!-- 5236032 -->
Estamos atualizando o painel do Intune chamado "Identidade visual e personalização" para fazer aprimoramentos, que incluem:

- Renomear o painel para **Personalização**.
- Aprimorar a organização e o design das configurações.
- Aprimorar o texto e as dicas de ferramenta das configurações.

Para encontrar essas configurações no Intune, navegue até o [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e selecione **Administração de locatário** > **Personalização**. Para obter informações sobre a personalização existente, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](~/apps/company-portal-app.md).

### <a name="configure-the-ios-microsoft-azure-ad-sso-app-extension---567534----"></a>Configurar a extensão de aplicativo de SSO do Microsoft Azure AD para iOS<!-- 567534  -->
A equipe do Microsoft Azure AD está desenvolvendo uma extensão de aplicativo de SSO (logon único) de redirecionamento para permitir que usuários do iOS e do iPadOS 13.0 e posteriores acessem diretamente os aplicativos e sites da Microsoft com um logon. Quando a extensão de aplicativo de SSO do AAD for lançada, você poderá configurar a extensão de SSO com o perfil **Recursos do dispositivo** > **Extensão de aplicativo de logon único** no console de administração com poucos cliques. 

Para obter mais informações sobre extensões de aplicativo de SSO para iOS ou sobre como configurar recursos do dispositivo, confira [Extensão de aplicativo de logon único](~/configuration/device-features-configure.md#single-sign-on-app-extension).

### <a name="company-portal-for-ios-to-support-landscape-mode--6048329----"></a>O Portal da Empresa para iOS dará suporte ao modo paisagem<!--6048329  -->
Os usuários poderão registrar seus dispositivos, localizar aplicativos e obter suporte de TI usando a orientação de tela que desejarem. O aplicativo detectará automaticamente a orientação e ajustará as telas para que se encaixem no modo retrato ou paisagem, a menos que os usuários bloqueiem a tela no modo retrato. 

### <a name="configure-if-enrollment-is-available-in-company-portal-for-android-and-ios---4260128-idready-idstaged---"></a>Configurar se o registro fica disponível no Portal da Empresa para Android e iOS<!-- 4260128 idready idstaged -->
Será disponibilizada uma nova configuração para que você defina se o registro de dispositivo no Portal da Empresa em dispositivos Android e iOS fica disponível com prompts, disponível sem prompts ou não disponível para os usuários. Para encontrar essas configurações no Intune, navegue até o [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e selecione **Administração de locatário** > **Personalização** > **Editar** > **Registro de dispositivo**. Para obter mais informações sobre a personalização existente do Portal da Empresa, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](~/apps/company-portal-app.md).

### <a name="improved-sign-in-experience-in-company-portal-for-android---6103997----"></a>Experiência de entrada aprimorada no Portal da Empresa para Android<!-- 6103997  -->
Estamos atualizando o layout de várias telas de entrada no aplicativo Portal da Empresa para Android para tornar a experiência mais moderna, simples e limpa para os usuários.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Perfil de configuração do dispositivo de rede com fios para dispositivos macOS<!-- 3508686  -->
Um novo perfil de configuração de dispositivo macOS estará disponível, com a capacidade de configurar redes com fio (**Configuração de dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Rede com fio** para o tipo de perfil). Use esse recurso para criar perfis 802.1x para gerenciar redes com fio e implantar essas redes em seus dispositivos macOS.

Aplica-se a:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932----"></a>Perfis VPN com conexões VPN IKEv2 podem usar o Always On com dispositivos iOS/iPadOS <!-- 1947932  -->
Em dispositivos iOS/iPadOS, você pode criar um perfil de VPN que usa uma conexão IKEv2 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **VPN** para o tipo de perfil). Em uma atualização futura, você poderá configurar o AlwaysOn com IKEv2. Quando configurados, os perfis de VPN IKEv2 se conectam automaticamente e permanecem conectados (ou reconectam-se rapidamente) à VPN. Ele permanece conectado mesmo ao se movimentar entre redes ou reiniciar dispositivos.

No iOS/iPadOS, a VPN AlwaysOn é limitada a perfis IKEv2.

Para ver as configurações de IKEv2 atuais que você pode configurar, vá para [Adicionar configurações de VPN em dispositivos iOS/iPadOS no Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Aplica-se a:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984----"></a>Experiência aprimorada da interface do usuário ao criar perfis de configuração em dispositivos iOS/iPadOS e macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984  -->
Quando você criar um perfil para dispositivos iOS/iPadOS ou macOS, a experiência no Centro de Administração do Gerenciamento de Ponto de Extremidade será atualizada. Essa alteração afeta os seguintes perfis de configuração de dispositivo (**Dispositivos** > **Perfis de Configuração** > **Criar perfil** > **iOS** ou **macOS** para plataforma):

- Personalizado: iOS/iPadOS, macOS
- Recursos do dispositivo: iOS/iPadOS, macOS
- Restrições de dispositivo: iOS/iPadOS, macOS
- Endpoint Protection: macOS
- Extensões: macOS
- Arquivo de preferência: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-----"></a>Experiência aprimorada da interface do usuário ao criar perfis de configuração OEMConfig em dispositivos Android Enterprise<!-- 5568645   -->
Quando você criar ou editar um perfil OEMConfig para dispositivos Android Enterprise, a experiência no Centro de Administração do Gerenciamento de Ponto de Extremidade será atualizada. A experiência atualizada fornecerá um resumo das configurações que você definiu em um relance. Essa alteração afeta o perfil de configuração de dispositivo OEMConfig (**Dispositivos** > **Perfis de configuração** > **Criar perfil** > **Android Enterprise** para a plataforma > **OEMConfig** para o tipo de perfil).

Esse recurso aplica-se a:
- Android Enterprise 

### <a name="enterprise-app-trust-settings-modification-setting-will-be-removed-from-iosipados-device-restriction-profiles---6225131----"></a>A configuração de modificação das configurações de confiança do aplicativo empresarial será removida dos perfis de restrição de dispositivo para iOS/iPadOS<!-- 6225131  -->
Em dispositivos IOS/iPadOS, crie um perfil de restrições de dispositivo (**Dispositivos** > **Perfis de criação** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). A configuração **Modificação das configurações de confiança do aplicativo empresarial** será removida pela Apple e será removida do Intune. Se você usar atualmente essa configuração em um perfil, ela não sofrerá impacto e permanecerá no seu perfil até que você crie um perfil. Essa configuração também será removida de todos os relatórios do Intune.

Aplica-se a:
- iOS/iPadOS

Para ver as configurações que pode restringir, acesse [Configurações do dispositivo iOS e iPadOS para permitir ou restringir recursos](../configuration/device-restrictions-ios.md).

### <a name="device-configuration-profile-settings-and-values-will-be-updated-for-windows-platforms---4091122---"></a>As configurações e os valores do perfil de configuração do dispositivo serão atualizados para plataformas Windows<!-- 4091122 -->
Quando você cria perfis de configuração do dispositivo para plataformas Windows (**Dispositivos** > **Perfis de configuração** > **Criar perfil** > qualquer opção do **Windows** para a plataforma), algumas configurações e seus valores são diferentes do CSP, o que pode ser confuso. Os nomes e os valores das configurações serão atualizados para que fiquem mais claros.

Aplica-se a:

- Perfis de configuração do dispositivo para Windows 10 e posteriores
- Perfis de configuração do dispositivo do Windows Holographic for Business
- Perfis de configuração do dispositivo Windows 8.1
- Perfis de configuração do dispositivo Windows Phone 8.1

### <a name="improved-user-interface-experience-when-creating-device-restrictions-profiles-on-android-and-android-enterprise-devices---5841361---"></a>Experiência aprimorada da interface do usuário ao criar perfis de restrições de dispositivos em dispositivos Android e Android Enterprise<!-- 5841361 -->
Quando você criar um perfil para dispositivos Android ou Android Enterprise, a experiência no Centro de Administração do Endpoint Manager será atualizada. Essa alteração afeta os seguintes perfis de configuração do dispositivo (**Dispositivos** > **Perfis de configuração** > **Criar perfil** > **Administrador de dispositivos Android** ou **Android Enterprise** para a plataforma):

- Restrições de dispositivo: Administrador do dispositivo Android
- Restrições de dispositivo: Proprietário do dispositivo Android Enterprise
- Restrições de dispositivo: Perfil de trabalho do Android Enterprise

Para obter mais informações sobre as restrições de dispositivo que você pode configurar, confira [Administrador de dispositivos Android](../configuration/device-restrictions-android.md) e [Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="delete-bundles-and-bundle-arrays-in-oemconfig-device-configuration-profiles-on-android-enterprise-devices---5550355----"></a>Excluir pacotes e matrizes de pacotes em perfis de configuração de dispositivo OEMConfig em dispositivos Android Enterprise<!-- 5550355  -->
Em dispositivos Android Enterprise, você cria e atualiza perfis OEMConfig. Os usuários poderão excluir pacotes e matrizes de pacotes usando o **Designer de configuração** no Intune.

Para saber mais sobre os perfis OEMConfig, confira [Usar e gerenciar dispositivos Android Enterprise com OEMConfig no Microsoft Intune](../configuration/android-oem-configuration-overview.md).

Esse recurso aplica-se a:
- Android Enterprise

### <a name="support-for-wpa-and-wpa2-in-ios-enterprise-wi-fi-profiles--6215273-----"></a>Suporte para WPA e WPA2 em perfis de Wi-Fi Enterprise para iOS<!--6215273   -->
Estamos adicionando o campo *Tipo de segurança* ao [Perfil de Wi-Fi Enterprise para iOS](../configuration/wi-fi-settings-ios.md) (**Dispositivos** > **Perfis de configuração** > **Criar perfil** e selecione **iOS/iPadOS** para *Plataforma* e, em seguida, **Wi-Fi** para *Perfil*). É semelhante às opções disponíveis para um Perfil de Wi-Fi Básico para iOS. Com essa alteração, você poderá criar perfis que especificam o tipo de segurança **WPA-Enterprise** ou **WPA/WPA2-Enterprise** e, em seguida, especificar uma seleção para o *Tipo de EAP*.

### <a name="new-user-experience-for-certificate-email-vpn-and-wi-fi-profiles---5615208-----"></a>Nova experiência do usuário para perfis de certificado, email, VPN e Wi-Fi<!-- 5615208   -->
Estamos atualizando a [experiência do usuário](../configuration/device-profile-create.md) no Centro de Administração do Endpoint Manager (**Dispositivos** > **Perfis de configuração** > **Criar perfil**) para criar e modificar os tipos de perfil a seguir. A nova experiência apresentará as mesmas configurações de antes, mas usará uma experiência semelhante a um assistente que não exige tanta rolagem horizontal. Você não precisará modificar configurações existentes com a nova experiência.
- Credencial derivada
- Email
- Certificado PKCS
- Certificado importado PKCS
- Certificado SCEP
- Certificado confiável
- VPN
- Wi-Fi

(**Dispositivos** > **Perfis de configuração** > **Criar perfil** e, em seguida, para *Tipo de perfil*, selecione qualquer um dos perfis anteriores.)

### <a name="configure-the-microsoft-defender-atp-app-for-macos-----5520115----"></a>Configurar o aplicativo Microsoft Defender ATP para macOS  <!-- 5520115  -->
Em breve, você poderá definir as [configurações](../protect/endpoint-protection-macos.md) do aplicativo Microsoft Defender ATP para dispositivos que executam o macOS como parte de um perfil de configuração de dispositivo do Endpoint Protection (**Dispositivos** > **Perfis de configuração** > **Criar perfil**, selecione **macOS** para a *Plataforma* e, em seguida, **Endpoint Protection** para o *Tipo de perfil*). Haverá oito itens de configuração para dispositivos macOS. 

O Defender ATP tem suporte no macOS 10.13 (High Sierra) e posteriores e o aplicativo [Microsoft Defender ATP](../apps/apps-advanced-threat-protection-macos.md) precisa ser implantado no dispositivo *depois* da aplicação dessas configurações. As configurações devem ser enviadas ao dispositivo antes que o aplicativo seja implantado. Não haverá suporte para versões Beta do macOS.

### <a name="new-filevault-setting-for-macos-endpoint-protection-device-configuration-policy---5459801-----"></a>Nova configuração de FileVault para a política de configuração de dispositivo do Endpoint Protection para macOS<!-- 5459801   -->
Estamos adicionando uma nova configuração à categoria FileVault dentro do modelo [Endpoint Protection para macOS](../protect/endpoint-protection-macos.md): Ocultar a chave de recuperação. (**Dispositivos** > **Perfis de configuração** > **Criar perfil**, selecione **macOS** para a *Plataforma* e, em seguida, **Endpoint Protection** para o *Tipo de perfil*). Essa configuração oculta a chave pessoal do usuário final durante a criptografia do FileVault 2. Um usuário do dispositivo pode exibir sua chave de recuperação pessoal a qualquer momento no aplicativo Portal da Empresa para iOS ou no site Portal da Empresa para o dispositivo macOS criptografado. Para exibir a chave de recuperação pessoal, ele pode acessar os detalhes do dispositivo e clicar em *obter chave de recuperação*.

Essa configuração não estará disponível em políticas criadas anteriormente. Você precisará recriar as políticas de FileVault para definir essa configuração e usá-la. 

###  <a name="ui-update-when-configuring-compliance-policy----3961639----"></a>Atualização da interface do usuário ao configurar a política de conformidade <!-- 3961639  -->
Estamos atualizando a interface do usuário para configurar as políticas de conformidade no Microsoft Endpoint Manager (**Dispositivos** > **Políticas de conformidade** > **políticas** > **Criar política**). Você verá uma nova experiência de usuário que fornece as mesmas configurações e detalhes que usava anteriormente. A nova experiência seguirá um processo semelhante a um assistente para criar uma política de conformidade e incluirá a página na qual você pode adicionar *Atribuições* para a política e, em seguida, uma página de *Resumo* em que pode examinar sua configuração antes de criar a política. 

### <a name="configure-delivery-optimization-agent-when-downloading-win32-app-content---5410945----"></a>Configurar o agente de Otimização de Entrega ao baixar conteúdo de aplicativos Win32<!-- 5410945  -->
Você poderá configurar o agente de Otimização de Entrega para baixar conteúdo de aplicativos Win32 em primeiro ou segundo plano com base na atribuição. Para aplicativos Win32 existentes, o conteúdo continuará sendo baixado em segundo plano. No [Centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**. Selecione **Windows 10 e posterior** como a **Plataforma**. Em **Tipo de perfil**, selecione **Otimização de Entrega**. Para obter mais informações sobre a Otimização de Entrega, confira [Configuração de aplicativos Win32 – Otimização de Entrega](~/apps/apps-win32-app-management.md#delivery-optimization).


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Gerenciamento de dispositivo

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Alterar o Usuário Primário para dispositivos Windows <!-- 3794742 -->
Você poderá alterar o Usuário Primário para dispositivos Ingressados no Azure AD e Windows híbridos. Para fazer isso, acesse **Intune** > **Dispositivos** > **Todos os dispositivos** > escolher um dispositivo > **Propriedades** > **Usuário Primário**. 

### <a name="new-android-report-on-android-devices-overview-page---5435435---"></a>Novo relatório do Android na página de visão geral de Dispositivos Android<!-- 5435435 -->
Adicionaremos ao console de administração do Microsoft Endpoint Manager na página de visão geral dos Dispositivos Android um relatório que exibe quantos dispositivos Android foram registrados em cada solução de gerenciamento de dispositivo. Este gráfico (assim como o mesmo gráfico que já existe no console do Azure) mostra as contagens de dispositivos com perfil de trabalho, totalmente gerenciados, dedicados e registrados pelo administrador do dispositivo. Para ver o relatório, escolha **Dispositivos** > **Android** > **Visão geral**.

### <a name="powershell-scripts-support-for-byod-devices---1862833----"></a>Suporte de scripts do PowerShell para dispositivos BYOD<!-- 1862833  -->
Os scripts do PowerShell darão suporte a dispositivos registrados do Azure AD no Intune. Para obter mais informações sobre o PowerShell, confira [Usar scripts do PowerShell em dispositivos Windows 10 no Intune](~/apps/intune-management-extension.md). Essa funcionalidade não dá suporte a dispositivos que executam o Windows 10 Home Edition.

### <a name="additional-data-warehouse-device-inventory-properties---6125732----"></a>Propriedades adicionais de inventário de dispositivos do Data Warehouse<!-- 6125732  -->
Propriedades adicionais de inventário de dispositivos estarão disponíveis usando o Data Warehouse do Intune. As seguintes propriedades serão expostas por meio da coleção de [dispositivos](~/developer/intune-data-warehouse-collections.md#devices):
- Capacidade de armazenamento 
- Capacidade de memória
- Versão do Office 365
- modelo do dispositivo

Para obter mais informações sobre o Data Warehouse, confira [API de Data Warehouse do Microsoft Intune](~/developer/reports-nav-intune-data-warehouse.md).

### <a name="guide-users-from-android-device-administrator-management-to-work-profile-management--5857738--"></a>Orientar usuários do gerenciamento do administrador de dispositivos Android para o gerenciamento de perfis de trabalho<!--5857738-->
Estamos lançando uma nova configuração de conformidade para a plataforma de administrador de dispositivos Android. Essa configuração permite fazer com que o dispositivo não esteja em conformidade quando ele é gerenciado com o administrador de dispositivos.

Nesses dispositivos que não estão em conformidade, na página **Atualizar configurações do dispositivo**, os usuários verão a mensagem **Mudar para a nova configuração de gerenciamento de dispositivo**. Se tocar no botão **Resolver**, ele será guiado pelos processos de:

1. Cancelar o registro do gerenciamento do administrador de dispositivos
2. Registrar-se no gerenciamento de perfil de trabalho
3. Resolver problemas de conformidade 
 
O Google está reduzindo o suporte para o administrador de dispositivos em novos lançamentos do Android em um esforço para migrar para um gerenciamento de dispositivo moderno, mais avançado e mais seguro com o Android Enterprise.  O Intune só pode dar suporte completo para os dispositivos Android gerenciados pelo administrador de dispositivos que executam o Android 10 e posterior até o segundo trimestre de 2020. Dispositivos gerenciados pelo administrador de dispositivos que executam o Android 10 ou posterior não poderão ser totalmente gerenciados após essa data (exceto pela Samsung). Em particular, os dispositivos afetados não receberão novos requisitos de senha. Para obter mais informações, confira este [Aviso](#decreasing-support-for-android-device-administrator).

### <a name="retire-noncompliant-devices---1827291---"></a>Desativar dispositivos sem conformidade<!-- 1827291 -->
Estamos adicionando uma nova ação de conformidade opcional para desativar um dispositivo fora de conformidade (**Dispositivos** > **Políticas de conformidade** > **Políticas** > **Criar política** e, em seguida, exiba as *Ações* disponíveis na página *Ações para não conformidade*).  Desativar um dispositivo não compatível remove todos os dados da empresa dele e também remove o dispositivo do gerenciamento pelo Intune. Essa ação é executada quando o valor configurado em dias é atingido. O valor mínimo é de 30 dias.  A aprovação explícita do administrador de TI será necessária para desativar dispositivos usando a seção *Desativar dispositivos não fora de conformidade*, em que os administradores podem desativar todos os dispositivos qualificados.

### <a name="new-information-in-device-details---5604099---"></a>Novas informações nos detalhes do dispositivo<!-- 5604099 -->
As seguintes informações estarão na página de **Visão geral** dos dispositivos:
- Capacidade de armazenamento (quantidade de armazenamento físico no dispositivo)
- Capacidade de memória (quantidade de memória física no dispositivo)

### <a name="script-support-for-macos-devices---4280361----"></a>Suporte de script para dispositivos macOS<!-- 4280361  -->
Você poderá adicionar e implantar scripts em dispositivos macOS. Esse suporte estende sua capacidade de configurar dispositivos macOS além do que é possível usando recursos de MDM nativos em dispositivos macOS. 

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
## <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

### <a name="help-and-support-workflow-update-to-support-additional-services---5654170---"></a>Atualização do fluxo de trabalho de ajuda e suporte para dar suporte a serviços adicionais<!-- 5654170 -->
Estamos atualizando a página de Ajuda e suporte no Centro de Administração do Microsoft Endpoint Manager para que você possa escolher o tipo de gerenciamento usado, a fim de fornecer melhor suporte específico (**Solução de problemas + suporte** >  **Ajuda e suporte**). Com essa alteração, você poderá selecionar entre os seguintes tipos de gerenciamento:
- Configuration Manager (inclui a Análise de Área de Trabalho)
- Intune
- Cogerenciamento

<!-- ***********************************************-->
<!--
## Role-based access control
-->

<!-- ***********************************************-->
## <a name="security"></a>Segurança

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Suporte para credenciais derivadas em dispositivos Android COBO<!--4839592-->
Você poderá usar credenciais derivadas em dispositivos Android Enterprise totalmente gerenciados. Será incluído suporte para recuperar uma credencial derivada para o Entrust Datacard, o Intercede e o DISA Purebred. Você poderá usar a credencial derivada para autenticação do aplicativo, Wi-Fi, VPN ou assinatura S/MIME e/ou criptografia com aplicativos que têm suporte.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Usar a política de antivírus para gerenciar as configurações do Antivírus Microsoft Defender e da experiência de Segurança do Windows<!--6131401 -->
No nó *Segurança do ponto de extremidade*, você poderá definir as configurações para **Antivírus**. Ao configurar a política para antivírus, você definirá configurações para seus dispositivos Windows 10 por meio de dois tipos de perfil:

- Microsoft Defender Antivírus: gerencie configurações para proteção de nuvem, exclusões do Antivírus, correção, opções de verificação e muito mais.
- Experiência de Segurança do Windows: gerencie como os usuários veem as configurações de Segurança do Windows em seus dispositivos. Você poderá configurar o que os usuários finais podem ver na central de Segurança do Microsoft Defender e as notificações recebidas.

### <a name="users-personal-encrypted-recovery-key---6273943---"></a>Chave de recuperação criptografada pessoal do usuário<!-- 6273943 -->
Um novo recurso do Intune estará disponível para permitir que os usuários recuperem suas chaves de recuperação criptografadas do **FileVault** para dispositivos Mac por meio do aplicativo Portal da Empresa para Android ou do aplicativo Intune para Android. Haverá um link no aplicativo Portal da Empresa e no aplicativo Intune que abrirá um navegador Chrome para o Portal da Empresa na Web, em que o usuário poderá ver a chave de recuperação do **FileVault** necessária para acessar seus dispositivos Mac. Para obter mais informações sobre criptografia, confira [Usar criptografia de dispositivo com o Intune](~/protect/encrypt-devices.md).

### <a name="privacy-preferences-settings-for-macos-devices---2934232---"></a>Configurações de preferências de privacidade para dispositivos macOS<!-- 2934232 --> 
Com o lançamento do macOS Catalina 10.15, a Apple acrescentou novos aprimoramentos de segurança e privacidade. Por padrão, aplicativos e processos não conseguem acessar dados específicos sem o consentimento do usuário. Se os usuários não consentirem, os aplicativos e processos poderão deixar de funcionar. O Intune está adicionando suporte para configurações que permitem que os administradores de TI permitam ou proíbam o consentimento de acesso a dados em nome dos usuários finais em dispositivos que executam o macOS 10.14 e posterior. Essas configurações garantirão que os aplicativos e processos continuem funcionando corretamente e reduzirão o número de prompts que os usuários finais receberão. 

### <a name="updated-ui-text-and-labels-for-windows-10-endpoint-protection-profile-settings---5983747---"></a>Atualização de texto e rótulos da interface do usuário para as configurações de perfil do Windows 10 Endpoint Protection<!-- 5983747 -->
Estamos atualizando o texto para várias configurações que você define como perfis de configuração de dispositivo do Windows 10 a fim de facilitar a compreensão do uso e dos resultados pretendidos das configurações. 

As configurações que estamos atualizando incluem perfis de configuração de dispositivo do Windows 10 para: 
- [Restrições de dispositivo](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) > Microsoft Defender Antivírus  
- [Endpoint Protection](../protect/endpoint-protection-windows-10.md) > Microsoft Defender Antivírus

As configurações que têm suporte com o Intune não serão alteradas. Essa é apenas uma atualização do texto da interface do usuário no Centro de Administração do Microsoft Endpoint Management. 


<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Consulte também
Para saber os detalhes dos desenvolvimentos mais recentes, veja [Novidades do Microsoft Intune](whats-new.md).



