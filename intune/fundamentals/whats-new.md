---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 571974e1736fb78ae633c02fcfd6e6233056379b
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71920144"
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

Conheça as novidades de cada semana do Microsoft Intune. Você também pode encontrar [avisos importantes](#notices), [versões anteriores](whats-new-archive.md) e informações sobre [como as atualizações de serviço do Intune são liberadas](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728).

> [!Note]
> Cada [atualização mensal](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) pode levar até três dias para ser distribuída e estará na seguinte ordem:
>
> - Dia 1: Pacífico Asiático (APAC)
> - Dia 2: Europa, Oriente Médio e África (EMEA)
> - Dia 3: América do Norte
>
> Alguns recursos podem ser implantados ao longo de várias semanas e podem não estar disponíveis para todos os clientes na primeira semana.
>
> Verifique a [Página de desenvolvimento](in-development.md) para obter uma lista dos próximos recursos em uma versão.

**Feed RSS**: Receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Semana de 23 de setembro de 2019

#### <a name="ios-user-enrollment-in-preview----4817900---"></a>Registro de usuário do iOS em versão prévia <!-- 4817900 -->
O iOS versão 13.1 da Apple inclui o Registro de Usuário, uma nova forma de gerenciamento leve para dispositivos iOS. Ele pode ser usado no lugar do Registro de Dispositivo ou do Registro de Dispositivo Automatizado (antigamente chamado Programa de registro de dispositivos) para dispositivos de propriedade pessoal. A versão prévia do Intune dá suporte a esse conjunto de recursos, permitindo que você:

- Direcionar o Registro de Usuário para grupos de usuários.
- Dê aos usuários finais a capacidade de escolher entre o Registro de Usuário mais leve ou o Registro de Dispositivo mais forte quando eles registrarem seus dispositivos.

Desde 24/9/2019, com o lançamento do iOS 13.1, estamos no processo de distribuir essas atualizações para todos os clientes e esperamos que sejam concluídas até o final da próxima semana.
Aplica-se a:

iOS 13.1 e posterior

#### <a name="intune-support-for-ipados-and-ios-131-devices---5439574--"></a>Suporte do Intune para dispositivos iPadOS e iOS 13.1 <!--5439574-->
O Intune agora dá suporte ao gerenciamento de dispositivos iPadOS e iOS 13.1. Para obter mais informações, consulte [esta postagem do blog](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094).

<!-- ########################## -->

## <a name="week-of-september-16-2019"></a>Semana de 16 de setembro de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos 

#### <a name="managed-google-play-private-lob-apps----1464182----"></a>Aplicativos LOB particulares do Google Play Gerenciado <!-- 1464182  -->
Agora, o Intune permite que os administradores de TI publiquem aplicativos de LOB privados do Android no Google Play Gerenciado por meio de um iframe inserido no console do Intune.  Anteriormente, os administradores de TI precisavam publicar aplicativos LOB diretamente no console de publicação do Google Play, o que exigia várias etapas e consumia muito tempo. Esse novo recurso permite a fácil publicação de aplicativos LOB com um conjunto mínimo de etapas, sem a necessidade de sair do console do Intune.  Os administradores não precisarão mais se registrar manualmente como desenvolvedores no Google e não precisarão mais pagar o valor de registro de US$ 25 do Google.  Qualquer um dos cenários de gerenciamento do Android Enterprise que usam o Google Play Gerenciado pode aproveitar esse recurso (perfil de trabalho, dispositivos dedicados, totalmente gerenciados e não registrados). No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Em seguida, selecione **Google Play Gerenciado** na lista **Tipo de aplicativo**. Para saber mais sobre aplicativos do Google Play Gerenciado, confira [Adicionar aplicativos do Google Play Gerenciado a dispositivos Android Enterprise com o Intune](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience----1473353-3598357---"></a>Experiência do Portal da Empresa para Windows <!-- 1473353, 3598357 -->
O Portal da Empresa do Windows está sendo atualizado. Você poderá usar vários filtros na página Aplicativos no Portal da Empresa do Windows. A página Detalhes do Dispositivo também está sendo atualizada com uma experiência aprimorada do usuário. Estamos no processo de distribuir essas atualizações para todos os clientes e esperar que sejam concluídas até o final da próxima semana.

#### <a name="macos-support-for-web-apps----3174427---"></a>Suporte do macOS para aplicativos Web <!-- 3174427 -->
Os aplicativos Web, que permitem adicionar um atalho a uma URL na Web, podem ser instalados no Dock usando o Portal da Empresa do macOS. Os usuários finais podem acessar a ação **Instalar** na página de detalhes de um aplicativo Web no Portal da Empresa do macOS. Para obter mais informações sobre o tipo de aplicativo **Link da Web**, confira [Adicionar aplicativos ao Microsoft Intune](../apps/apps-add.md) e [Adicionar aplicativos Web ao Microsoft Intune](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps----3173501----"></a>Suporte do macOS para aplicativos VPP <!-- 3173501  -->
Os aplicativos do macOS, comprados usando o Apple Business Manager, são exibidos no console quando os tokens de VPP da Apple são sincronizados no Intune. Você pode atribuir, revogar e reatribuir licenças baseadas no usuário e no dispositivo para grupos usando o console do Intune. O Microsoft Intune ajuda a gerenciar aplicativos VPP adquiridos para uso em sua empresa ao proporcionar:

- Informações sobre licença de relatórios da app store.
- Acompanhamento de quantas licenças você usou.
- Ajuda para impedir a instalação de mais cópias do aplicativo além das que você já tem.

Saiba mais sobre o Intune e o VPP em [Gerenciar aplicativos e livros comprados por volume com o Microsoft Intune](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support----2871756----"></a>Suporte para iframe do Google Play Gerenciado <!-- 2871756  -->
O Intune agora dá suporte para adicionar e gerenciar links da Web diretamente no console do Intune por meio do iframe do Google Play Gerenciado.  Isso permite que os administradores de TI enviem um URL e um ícone gráfico e, em seguida, implantem esses links nos dispositivos, como os aplicativos Android comuns. Qualquer um dos cenários de gerenciamento do Android Enterprise que usam o Google Play Gerenciado pode aproveitar esse recurso (perfil de trabalho, dispositivos dedicados, totalmente gerenciados e não registrados). No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Em seguida, selecione **Google Play Gerenciado** na lista **Tipo de aplicativo**. Para saber mais sobre aplicativos do Google Play Gerenciado, confira [Adicionar aplicativos do Google Play Gerenciado a dispositivos Android Enterprise com o Intune](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices----4252734----"></a>Instalar silenciosamente aplicativos de LOB do Android em dispositivos Zebra <!-- 4252734  -->
Ao instalar aplicativos de LOB (linha de negócios) do Android em [dispositivos Zebra](../configuration/android-zebra-mx-overview.md), em vez de ser solicitado a baixar e instalar o aplicativo LOB, você poderá instalar o aplicativo silenciosamente. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. No painel **Adicionar aplicativo**, selecione **Aplicativo de linha de negócios**. Para saber mais, confira [Adicionar um aplicativo de linha de negócios do Android ao Microsoft Intune](../apps/lob-apps-android.md).

Atualmente, após o download do aplicativo de LOB, uma notificação de **êxito no download** será exibida no dispositivo do usuário. A notificação só pode ser descartada tocando em **Limpar Tudo** na aba de notificações. Esse problema de notificação será corrigido em uma próxima versão e a instalação será completamente silenciosa, sem indicadores visuais.

#### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Ler e gravar operações da API do Graph para aplicativos Intune <!-- 5031704  -->
Os aplicativos podem chamar a API do Intune Graph com operações de leitura e gravação usando a identidade do aplicativo sem credenciais do usuário. Para saber mais sobre como acessar a API do Microsoft Graph para Intune, confira [Como trabalhar com o Intune no Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios----3586942----"></a>Compartilhamento e criptografia de dados protegidos para o SDK de Aplicativo do Intune para iOS <!-- 3586942  -->
O SDK de Aplicativo do Intune para iOS usa as chaves de criptografia de 256 bits quando a criptografia é habilitada por Políticas de Proteção de Aplicativo. Todos os aplicativos precisarão ter um SDK versão 8.1.1 para permitir o compartilhamento de dados protegidos.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438-----"></a>Suporte para perfis de VPN IKEv2 para iOS <!-- 1943438   -->
Nessa atualização, você poderá criar perfis VPN para o cliente VPN nativo do iOS usando o protocolo IKEv2. IKEv2 é um novo tipo de conexão em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **VPN** para tipo de perfil > **Tipo de conexão**.

Esses perfis de VPN configuram o cliente VPN nativo, portanto, nenhum aplicativo cliente VPN é instalado ou enviado para dispositivos gerenciados. Esse recurso exige que dispositivos sejam registrados no Intune (registro do MDM).

Para ver as configurações de VPN atuais que você pode configurar, vá para [Definir configurações de VPN em dispositivos iOS](../configuration/vpn-settings-ios.md).

Aplica-se a:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161-----"></a>Recursos do dispositivo, restrições do dispositivo e perfis de extensão para configurações do iOS e macOS são mostrados por tipo de registro <!-- 4886161   -->

No Intune, você cria perfis para dispositivos iOS e macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** ou **macOS** para a plataforma > **Recursos de dispositivo**, **Restrições de dispositivo** ou **Extensões** para o tipo de perfil). 

Nesta atualização, as configurações disponíveis no portal do Intune são categorizadas pelo tipo de registro a que se aplicam:

- iOS
  - Registro de usuários
  - Registro de dispositivo
  - Registro de dispositivo automatizado (supervisionado)
  - Todos os tipos de registro

- macOS
  - Aprovado pelo usuário
  - Registro de dispositivo
  - Registro de dispositivo automatizado
  - Todos os tipos de registro

Aplica-se a:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835-----"></a>Novas configurações de controle de voz para dispositivos iOS supervisionados em execução no modo quiosque <!-- 4892835   -->
No Intune, você pode criar políticas para executar dispositivos iOS supervisionados como um quiosque ou dispositivo dedicado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **Restrições de dispositivo** para tipo de perfil > **Quiosque**). 

Nessa atualização, há novas configurações que você pode controlar:
- **Controle de voz**: Habilita o controle de voz no dispositivo no modo de quiosque.
- **Modificação do controle de voz**: Permite que os usuários alterem a configuração do Controle de Voz no dispositivo enquanto estão no modo de quiosque.

Para ver as configurações atuais, acesse [Configurações do quiosque do iOS](../configuration/device-restrictions-ios.md#kiosk).

Aplica-se a:
- iOS 13.0 e posterior

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175-----"></a>Usar o logon único para aplicativos e sites em dispositivos iOS e macOS <!-- 4893175   -->
Nesta atualização, há algumas novas configurações de logon único para dispositivos iOS e macOS (**Configuração de dispositivo** > **Perfis** > **Criar perfil** > **iOS** ou **macOS** para plataforma > **Recursos de dispositivo** para tipo de perfil).

Use essas configurações para configurar uma experiência de logon único, especialmente para aplicativos e sites que usam autenticação Kerberos. Você pode optar por uma extensão de aplicativo de logon único com credencial genérica ou pela extensão Kerberos interna da Apple.

Para ver os recursos atuais do dispositivo que você pode configurar, acesse [Recursos do dispositivo iOS](../configuration/ios-device-features-settings.md) e [Recursos do dispositivo macOS](../configuration/macos-device-features-settings.md).

Aplica-se a:
- iOS 13.0 e mais recente
- macOS 10.15 e mais recente

#### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079-----"></a>Associar domínios a aplicativos em dispositivos macOS 10.15 ou superiores <!-- 4898079   -->
Nos dispositivos macOS, você pode configurar recursos diferentes e enviá-los aos dispositivos usando uma política (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para plataforma > **Recursos do dispositivo** para tipo de perfil). Nessa atualização, você pode associar domínios a seus aplicativos. Esse recurso ajuda a compartilhar credenciais com sites relacionados ao seu aplicativo e pode ser usado com a extensão de logon único da Apple, links universais e preenchimento automático de senha. 

Para ver os recursos atuais que você pode configurar, acesse [Configurações de recursos de dispositivo macOS no Intune](../configuration/macos-device-features-settings.md).

Aplica-se a:
- macOS 10.15 e mais recente

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474-----"></a>Use "iTunes" e "aplicativos" na URL da loja de aplicativos do iTunes ao mostrar ou ocultar aplicativos em dispositivos supervisionados do iOS <!-- 4928474   --> 
No Intune, você pode criar políticas para mostrar ou ocultar aplicativos em seus dispositivos iOS supervisionados (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **Restrições de dispositivo** para tipo de perfil > **Mostra ou ocultar aplicativos**). 

Você pode inserir o URL da loja de aplicativos do iTunes, como `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. Nesta atualização, `apps` e `itunes` podem ser usados no URL, como:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Para saber mais sobre estas configurações, confira [Mostrar ou ocultar aplicativos](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Aplica-se a:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Os valores do tipo de senha da política de conformidade do Windows 10 são mais claros e correspondem ao CSP<!-- 5138985 -->
Nos dispositivos Windows 10, você pode criar uma política de conformidade que exija recursos específicos de senha (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10 e posterior** para plataforma > **Segurança do Sistema**). Nesta atualização:
- Os valores de **Tipo de senha** são mais claros e atualizados para corresponder ao [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- A configuração **Expiração da senha (dias)** é atualizada para permitir valores de 1 a 730 dias. 

Para saber mais sobre as configurações de conformidade do Windows 10, confira [Configurações do Windows 10 e posteriores para marcar os dispositivos como compatíveis ou não](../protect/compliance-policy-create-windows.md). 

Aplica-se a:
- Windows 10 e posterior

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access-------4092920---"></a>Interface do usuário atualizada para configurar o acesso local ao Microsoft Exchange    <!-- 4092920 -->  
Atualizamos o console no qual você [configura o acesso local ao Microsoft Exchange](../protect/conditional-access-exchange-create.md). Todas as configurações para acesso local ao Exchange agora estão disponíveis no mesmo painel do console em que você *Habilita o controle de acesso local do Exchange*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices----1109650----"></a>Permitir ou restringir a adição de widgets de aplicativos à tela inicial nos dispositivos de perfil profissional do Android Enterprise <!-- 1109650  --> 
Nos dispositivos Android Enterprise, você pode configurar recursos no perfil de trabalho (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Apenas perfil de trabalho > Restrições de dispositivo** para tipo de perfil). Nessa atualização, você pode permitir que os usuários adicionem widgets expostos por aplicativos de perfil profissional à tela inicial do dispositivo.

Para ver as configurações que você pode definir, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md).

Aplica-se a:
- Perfil de trabalho do Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790-----"></a>Os novos locatários terão como padrão o gerenciamento de administradores de dispositivos Android <!-- 4869790   -->
Os recursos de administrador de dispositivos do Android foram substituídos pelo Android Enterprise. Portanto, recomendamos o uso do Android Enterprise para novos registros. Em uma atualização futura, novos locatários precisarão concluir as seguintes etapas de pré-requisito na inscrição do Android para usar o gerenciamento de administrador de dispositivos: Acesse **Intune** > **Registro de dispositivo** > **Registro do Android** > **Dispositivos pessoais e corporativos com privilégios de administração de dispositivos** > **Usar o administrador do dispositivo para gerenciar dispositivos**.

Os locatários existentes não sofrerão alteração em seus ambientes. 

Para saber mais sobre o administrador do dispositivo Android no Intune, confira [Registro do administrador do dispositivo Android](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile----5012045-idmiss---"></a>Lista de dispositivos DEP associados a um perfil <!-- 5012045 idmiss -->
Agora você pode ver uma lista paginada de dispositivos DEP (Programa de Registro de Dispositivos) Automatizados da Apple associados a um perfil. Você pode pesquisar a lista a partir de qualquer página da lista. Para ver a lista, acesse **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Dispositivos atribuídos** (em **Monitor**). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="more-android-fully-managed-support----3464667-4631425-4631440-5227935-4062195-----"></a>Mais suporte para Android totalmente gerenciado <!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Adicionamos o seguinte suporte para dispositivos Android totalmente gerenciados:

- Os certificados SCEP para Android totalmente gerenciado estão disponíveis para autenticação de certificados em dispositivos gerenciados como Proprietário do dispositivo. Os certificados SCEP já têm suporte nos dispositivos de Perfil de Trabalho.  Com os certificados SCEP para Proprietário do Dispositivo, você será capaz de: <!-- 5227935 -->
    - criar um perfil SCEP na seção Proprietário do Dispositivo do Android Enterprise
    - vincular certificados SCEP ao perfil Wi-Fi do Proprietário do Dispositivo para autenticação
    - vincular certificados SCEP a perfis VPN do Proprietário do Dispositivo para autenticação
    - vincular certificados SCEP a perfis de email do Proprietário do Dispositivo para autenticação (via AppConfig)
- Os aplicativos do sistema são compatíveis com dispositivos Android Enterprise. No Intune, adicione um aplicativo do sistema Android Enterprise selecionando **Aplicativos clientes** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo**, selecione **Aplicativo do sistema Android Enterprise**. Para saber mais, confira [Adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune](../apps/apps-ae-system.md). <!-- 4062195 -->
- Em **Conformidade do Dispositivo** > **Android Enterprise** > **Proprietário do Dispositivo**, você pode criar uma política de conformidade que defina o nível de atestado do Google SafetyNet.   <!-- 4631425 -->
- Nos dispositivos totalmente gerenciados do Android Enterprise, os provedores de defesa contra ameaças móveis são compatíveis. Em **Conformidade do dispositivo** > **Android Enterprise** > **Proprietário do Dispositivo**, você pode escolher um nível aceitável de ameaça. <!-- 4631440 --> [Configurações do Android Enterprise para marcar dispositivos como em conformidade ou não em conformidade usando o Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) mostra as configurações atuais.
- Nos dispositivos totalmente gerenciados do Android Enterprise, o aplicativo Microsoft Launcher agora pode ser definido por meio de políticas de configuração de aplicativos para permitir uma experiência padronizada ao usuário final no dispositivo totalmente gerenciado. O aplicativo Microsoft Launcher pode ser usado para personalizar seu dispositivo Android. Usando o aplicativo com uma conta da Microsoft ou uma conta corporativa/de estudante, você pode acessar sua agenda, documentos e atividades recentes em seu feed personalizado. <!-- 5334044 -->

Com essa atualização, temos o prazer de anunciar que o suporte do Intune ao Android Enterprise Totalmente Gerenciado está agora disponível.

Aplica-se a:

- Dispositivos Android Enterprise totalmente gerenciados

#### <a name="send-custom-notifications-to-a-single-device-----4928910---"></a>Enviar notificações para um único dispositivo  <!-- 4928910 -->
Agora você pode selecionar um único dispositivo e, em seguida, usar uma ação de dispositivo remoto para [enviar uma notificação personalizada apenas para esse dispositivo](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment----4950491---"></a>As ações Apagar e Redefinição de Senha não estão disponíveis para dispositivos iOS registrados usando Registro de Usuário <!-- 4950491 -->
O Registro de Usuário é um novo tipo de registro do dispositivo Apple. Quando você registra dispositivos usando o Registro do Usuário, as ações remotas Apagar e Redefinição de Senha não estarão disponíveis para esses dispositivos.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices----4665317---"></a>Suporte do Intune para dispositivos iOS 13 e macOS Catalina <!-- 4665317 -->
O Intune agora dá suporte ao gerenciamento de dispositivos iOS 13 e macOS Catalina. Para saber mais, confira a [Postagem no blog Suporte do Microsoft Intune para iOS 13 e iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation-------3444125---"></a>Suporte do BitLocker para rotação de senha de recuperação orientada ao cliente   <!--  3444125 -->
Use as configurações do Intune Endpoint Protection para configurar a [Rotação da senha de recuperação orientada ao cliente](../protect/endpoint-protection-windows-10.md#windows-encryption) para o BitLocker em dispositivos que executam o Windows versão 1909 ou posterior.

Essa configuração inicia uma atualização de senha de recuperação orientada a cliente após uma recuperação de unidade do SO (usando bootmgr ou WinRE) e desbloqueio de senha de recuperação em uma unidade de dados fixa. Essa configuração atualiza a senha de recuperação específica usada e outras senhas não utilizadas no volume permanecem inalteradas. Para saber mais, confira a documentação do BitLocker CSP para [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus-----4705448----------"></a>Proteção contra Adulterações para o Windows Defender Antivírus  <!-- 4705448        -->
Use o Intune para gerenciar a *Proteção contra Adulterações* para o Windows Defender Antivírus. Você encontrará a configuração para [Proteção contra Adulterações](../protect/endpoint-protection-windows-10.md#windows-defender-security-center) no grupo Microsoft Defender Security Center ao usar perfis de configuração de dispositivo para a proteção de ponto de extremidade do Windows 10. Você pode definir a Proteção contra Adulterações para *Habilitada* para ativar as restrições de proteção contra adulterações, definir *Desabilitada* para desativá-las ou definir *Não Configurada* para deixar a configuração atual de dispositivos em vigor.  

Para saber mais sobre a proteção contra adulterações, confira [Impedir alterações nas configurações de segurança com proteção contra adulterações](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) na documentação do Windows. 

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available-----5317392---------"></a>As configurações avançadas do Windows Defender Firewall agora estão disponíveis em geral <!--  5317392       -->  
As [regras de firewall personalizadas do Windows Defender para proteção de ponto de extremidade](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), configuradas como parte de um perfil de configuração de dispositivo, não estão mais em versão prévia pública, mas em versão disponível em geral (GA).  Você pode usar as regras para especificar o comportamento de entrada e saída para aplicativos, endereços de rede e portas. Essas regras foram publicadas em julho como uma versão prévia pública. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-now-support-terms-of-use-policies----2358863-idmiss---"></a>As marcas de escopo agora dão suporte a políticas dos Termos de Uso <!-- 2358863 idmiss -->
Agora você pode atribuir [marcas de escopo](scope-tags.md) às políticas dos Termos de Uso. Para fazer isso, acesse **Intune** > **Registro do dispositivo** > **Termos e condições** > escolha um item na lista > **Propriedades** > **Marcas de escopo** > escolha uma marca de escopo.

## <a name="week-of-september-9-2019"></a>Semana de 9 de setembro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="updates-to-microsoft-intune-app----4997846---"></a>Atualizações do aplicativo Microsoft Intune <!-- 4997846 -->
O aplicativo Microsoft Intune para Android foi atualizado com as seguintes melhorias:
- Layout atualizado e aprimorado para incluir a navegação inferior para as ações mais importantes.
- Página adicional incluída que mostra o perfil do usuário.
- Adicionada ao aplicativo a exibição de notificações acionáveis, como a necessidade de atualizar as configurações de dispositivo.
- Adicionada a exibição de notificações push personalizadas, alinhando o aplicativo ao suporte recentemente adicionado nos aplicativos do Portal da Empresa para iOS e Android. Para saber mais, confira [Enviar notificações personalizadas no Microsoft Intune](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993---"></a>Para dispositivos iOS, personalize a tela de privacidade do processo de registro do Portal da Empresa <!-- 4394993 -->
Com o Markdown, você pode personalizar a tela de privacidade do Portal da Empresa que os usuários finais exibem durante o registro do iOS. Especificamente, você poderá personalizar a lista daquilo que sua organização não pode ver ou fazer no dispositivo. Para saber mais, confira [Como configurar o aplicativo do Portal da Empresa do Intune](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>Semana de 2 de setembro de 2019

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-user-interface-update--tenant-status-dashboard-----5273210----"></a>Atualização da interface do usuário do Intune – Painel de Status do Locatário  <!-- 5273210  -->
A interface do usuário para o painel de Status do Locatário foi atualizada para alinhar-se aos estilos de interface do usuário do Azure. Para obter mais informações, veja [Status do locatário](../tenant-status.md).


## <a name="week-of-august-26-2019"></a>Semana de 26 de agosto de 2019

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer----5228061---"></a>Definir as configurações do Microsoft Edge usando modelos administrativos para o Windows 10 e mais recente <!-- 5228061 -->

Em dispositivos Windows 10 e mais recente, você pode criar modelos administrativos para definir as configurações da política de grupo no Intune. Nesta atualização, você pode definir as configurações que se aplicam ao Microsoft Edge versão 77 e mais recente.

Para saber mais sobre modelos administrativos, confira [Usar modelos do Windows 10 para definir as configurações da política de grupo no Intune](../configuration/administrative-templates-windows.md).

Aplica-se a:

- Windows 10 e mais recente (Windows RS4 e posterior)

## <a name="week-of-august-12-2019"></a>Semana de 12 de agosto de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144-----"></a>Controlar o comportamento de desinstalação do aplicativo iOS no cancelamento de registro do dispositivo <!-- 3504144   -->
Os administradores podem determinar se um aplicativo é removido ou mantido em um dispositivo, quando o registro do dispositivo é cancelado no nível do usuário ou do grupo de dispositivos. 

#### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Categorizar aplicativos da Microsoft Store para Empresas <!-- 3926922 -->
É possível categorizar aplicativos da Microsoft Store para Empresas. Para fazer isso, escolha **Intune** > **Aplicativos cliente** > **Aplicativos** > Selecione um aplicativo da Microsoft Store para Empresas > **Informações do aplicativo** > **Categoria**. Atribua uma categoria no menu suspenso.

#### <a name="customized-notifications-for-microsoft-intune-app-users----4843354----"></a>Notificações personalizadas para usuários do aplicativo Microsoft Intune <!-- 4843354  -->
O aplicativo Microsoft Intune para Android agora tem suporte para exibição de notificações push personalizadas, além do suporte recentemente adicionado nos aplicativos do Portal da Empresa para iOS e Android. Para saber mais, confira [Enviar notificações personalizadas no Microsoft Intune](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946-----"></a>Novos recursos para dispositivos dedicados Android Enterprise no modo de vários aplicativos <!-- 3755304 3041943 3041946   -->

No Microsoft Intune, você pode controlar recursos e configurações em uma experiência estilo quiosque nos dispositivos dedicados Android Enterprise (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Somente Proprietário do Dispositivo, Restrições do dispositivo** para tipo de perfil).

Os seguintes recursos foram adicionados nesta atualização:

- **Dispositivos dedicados** > **Vários aplicativos**: o **botão Página Inicial virtual** pode ser exibido passando o dedo para cima no dispositivo ou pode estar flutuante na tela para que os usuários possam movê-lo.
- **Dispositivos dedicados** > **Vários aplicativos**: **Acesso à lanterna** permite aos usuários utilizar a lanterna. 
- **Dispositivos dedicados** > **Vários aplicativos**: **Controle de volume de mídia** permite aos usuários controlar o volume de mídia do dispositivo por meio de um controle deslizante. 
- **Dispositivos dedicados** > **Vários aplicativos**:  **Habilitar um protetor de tela**, carregar uma imagem personalizada e controlar quando o protetor de tela é exibido.

Veja as configurações atuais acessando [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Aplica-se a:

- Dispositivos Android Enterprise dedicados

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215-3574238-3574235-3574232-----"></a>Novos perfis de configuração e de aplicativos para dispositivos Android Enterprise totalmente gerenciados <!-- 3574215 3574238 3574235 3574232   -->
Com os perfis, você pode definir configurações que apliquem configurações de VPN, email e Wi-Fi aos dispositivos Android Enterprise (totalmente gerenciados) do proprietário do dispositivo. Nesta atualização, é possível:

- Usar [políticas de configuração de aplicativos](../apps/app-configuration-policies-use-android.md) para implantar configurações de email das plataformas Outlook, Gmail e Nine Work.
- Usar perfis de configuração de dispositivos para implantar [configurações de certificado raiz confiável](../protect/certificates-configure.md).
- Usar perfis de configuração de dispositivos para implantar configurações de [VPN](../configuration/vpn-settings-android-enterprise.md) e [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

> [!IMPORTANT]
> Com esse recurso, os usuários se autenticam com nome de usuário e senha em perfis de VPN, Wi-Fi e email. No momento, não há disponibilidade para autenticação baseada em certificado.

Aplica-se a:  
- Proprietário do dispositivo Android Enterprise (totalmente gerenciado)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices---3914202-----"></a>Controlar aplicativos, arquivos, documentos e pastas exibidos quando os usuários entram em dispositivos macOS <!--3914202   -->
Você pode habilitar e configurar recursos em dispositivos macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). 

Nesta atualização, há uma nova configuração de Itens de Logon para controlar quais aplicativos, arquivos, documentos e pastas são abertos quando um usuário entra no dispositivo registrado. 

Veja as configurações atuais acessando [Configurações de recurso de dispositivo macOS no Intune](../configuration/macos-device-features-settings.md).

Aplica-se a:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings------4464404----------"></a>Prazos finais substituem configurações de Reinício estabelecido para anéis de atualização do Windows   <!-- 4464404        -->
Para se alinhar às recentes [alterações de manutenção do Windows](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing), os anéis de atualização do Windows 10 do Microsoft Intune agora têm [suporte para configurações de prazos finais](../protect/windows-update-settings.md). Os *prazos finais* determinam quando um dispositivo instala atualizações de recursos e de segurança.  Em dispositivos com Windows 10 1903 ou posterior, os *prazos finais* substituem as configurações de *Reinício estabelecido*.  Futuramente, os *s prazos finais* também substituirão o *Reinício estabelecido* em versões anteriores do Windows 10.  

Quando você não configura *prazos finais*, os dispositivos continuam usando as respectivas configurações de *Reinício estabelecido*. No entanto, o [Microsoft Intune removerá o suporte dessas configurações ](whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) em uma próxima atualização.  

Planeje o uso de *prazos finais* para todos os dispositivos Windows 10. Após aplicar as configurações de *prazos finais*, você poderá alterar as configurações do Intune para que o *Reinício estabelecido* fique Não configurado. Quando definido como Não configurado, o Intune deixa de gerenciar essas configurações nos dispositivos, mas não remove as últimas definições da configuração do dispositivo. Portanto, as últimas configurações que foram definidas para o *Reinício estabelecido* permanecerão ativas e em uso nos dispositivos até que essas configurações sejam modificadas por um método diferente do Intune. Posteriormente, quando a versão do Windows dos dispositivos for alterada ou quando o suporte do Intune para *prazos finais* for estendido para a versão do Windows dos dispositivos, o dispositivo começará a usar as novas configurações que já estarão em vigor.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors--------4704642--------"></a>Suporte para vários Microsoft Intune Certificate Connectors   <!--   4704642      -->
Agora, o Microsoft Intune tem suporte para instalação e uso de vários [Microsoft Intune Certificate Connectors para operações PKCS](../protect/certficates-pfx-configure.md). Essa alteração é compatível com o balanceamento de carga e a alta disponibilidade do conector. Cada instância de conector pode processar solicitações de certificado do Intune.  Quando um conector não está disponível, outros conectores continuam a processar solicitações. 

Para usar vários conectores, não é necessário atualizar para a versão mais recente do software de conector.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709-----"></a>Novas configurações e alterações em configurações existentes para restringir recursos em dispositivos iOS e macOS <!-- 4867699 4867709   -->
Você pode criar perfis para restringir configurações em dispositivos com iOS e macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** ou **macOS** para o tipo de plataforma > **Restrições do dispositivo**). Essa atualização inclui os seguintes recursos:

- Em **macOS** > **Restrições do dispositivo** > **Nuvem e armazenamento**, use a nova configuração **Handoff** para impedir que os usuários iniciem o trabalho em um dispositivo macOS e continuem trabalhando em outro dispositivo macOS ou iOS.

  Para ver as configurações atuais, vá para [Configurações do dispositivo macOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-macos.md).

- Em **iOS** > **Restrições do dispositivo**, há algumas alterações:

  - **Aplicativos internos** > **Buscar iPhone (somente supervisionado)** : nova configuração que bloqueia esse recurso, no recurso do aplicativo Buscar. 
  - **Aplicativos internos** > **Buscar Amigos (somente supervisionado)** : nova configuração que bloqueia esse recurso, no recurso do aplicativo Buscar. 
  - **Sem fio** > **Modificação do estado do Wi-Fi (somente supervisionado)** : nova configuração que impede os usuários de ativar ou desativar o Wi-Fi nos dispositivos.
  - **Teclado e Dicionário** > **QuickPath (somente supervisionado)** : nova configuração que bloqueia o recurso QuickPath.
  - **Nuvem e armazenamento**: a **Continuação da atividade** é renomeada para **Handoff**.

  Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md).

Aplica-se a:  
- macOS 10.15 e mais recente
- iOS 13 e mais recente

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809-----"></a>Algumas restrições do dispositivo iOS não supervisionadas passarão a ser somente supervisionadas após o lançamento do iOS 13.0 <!-- 4867809   -->
Nesta atualização, algumas configurações se aplicam a dispositivos somente supervisionados após o lançamento do iOS 13.0. Caso essas configurações sejam definidas e atribuídas a dispositivos não supervisionados antes do lançamento do iOS 13.0, elas ainda serão aplicadas a esses dispositivos não supervisionados. Elas também estarão em vigor após a atualização dos dispositivos para o iOS 13.0. Essas restrições serão removidas de dispositivos não supervisionados que forem armazenados em backup e restaurados. 

Essas configurações incluem:

- Loja de Aplicativos, Exibição de Documentos, Jogos
  - Loja de aplicativos
  - Conteúdo adulto de música, podcast ou notícias do iTunes
  - Adição de amigos no Game Center
  - Jogo para vários participantes
- Aplicativos internos
  - Câmera
    - FaceTime
  - Safari
    - Preenchimento automático
- Nuvem e Armazenamento
  - Backup no iCloud
  - Bloquear a sincronização de documentos do iCloud
  - Bloquear a sincronização do Conjunto de Chaves do iCloud

Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md).

Aplica-se a:  
- iOS 13.0 e mais recente

#### <a name="improved-device-status-for-macos-filevault-encryption-----4944983-----------"></a>Status aprimorado do dispositivo para criptografia do FileVault no macOS  <!-- 4944983         -->
Atualizamos várias das [mensagens de status do dispositivo](../protect/encryption-monitor.md#device-encryption-status) para a criptografia do FileVault em dispositivos macOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status----5119229---"></a>Algumas configurações do Windows Defender Antivírus mostram o status "Com falha" no relatório <!-- 5119229 -->
No Microsoft Intune, você pode criar políticas para usar o Windows Defender Antivírus a fim de verificar seus dispositivos Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Restrições do dispositivo** para o tipo de perfil > **Windows Defender Antivírus**). Os relatórios **Hora para executar uma verificação rápida diária** e **Tipo de verificação do sistema a executar** mostram um status de falha, quando na verdade é um status de êxito. 

Corrigimos esse comportamento nesta atualização. Portanto, as configurações **Hora para executar uma verificação rápida diária** e **Tipo de verificação do sistema a executar** mostram um status de êxito quando as verificações são concluídas com êxito e mostram um status de falha quando ocorre falha na aplicação dessas configurações. 

Para obter mais informações sobre as configurações do Windows Defender Antivírus, confira [Configurações de dispositivo Windows 10 (e mais recente) para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus). 

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="default-scope-tags----3702875----"></a>Marcas de escopo padrão <!-- 3702875  -->
Já está disponível uma nova marca de escopo padrão interna. Todos os objetos sem marca do Intune compatíveis com marcas de escopo receberão automaticamente a marca de escopo padrão. A marca de escopo **padrão** é adicionada a todas as atribuições de função existentes para manter a paridade com a experiência de administrador atual. Se você prefere que um administrador não veja objetos do Intune com a marca de escopo padrão, remova essa marca da atribuição de função. Esse recurso é semelhante ao recurso Escopos de Segurança do System Center Configuration Manager. Para saber mais, confira [Usar o RBAC e marcas de escopo na TI distribuída](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support----4869749-----"></a>Suporte para registro de administrador de dispositivo Android <!-- 4869749   -->
Adicionamos a opção de registro de administrador de dispositivo Android à página de registro do Android (**Intune** > **Registro do dispositivo** > **Registro do Android**). O administrador do dispositivo Android ainda estará habilitado por padrão para todos os locatários.  Para saber mais, confira [Registro de administrador de dispositivos Android](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Ignorar mais telas no Assistente de Configuração <!--4877451  -->
Você pode definir perfis do Programa de registro de dispositivos para ignorar as seguintes telas do Assistente de Configuração:
- Para iOS
    - Aparência
    - Idioma expresso
    - Idioma preferencial
    - Migração de dispositivo para dispositivo
- Para macOS
    - Tempo da Tela
    - Configuração do Touch ID

Para obter mais informações sobre como personalizar o Assistente de Configuração, confira os tópicos [Criar um perfil de registro da Apple para iOS](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) e [Criar um perfil de registro da Apple para macOS](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process----3823054---"></a>Adicionar uma coluna de usuário ao processo de upload de arquivos CSV em dispositivos do Autopilot <!-- 3823054 -->
Agora, é possível adicionar uma coluna de usuário ao upload de arquivos CSV em dispositivos do Autopilot. Dessa forma, você pode atribuir usuários em massa ao importar o CSV. Para obter mais informações, confira [Registrar dispositivos Windows no Intune usando o Windows Autopilot](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Configurar o limite de tempo de limpeza automática do dispositivo para 30 dias <!--4231059  -->
É possível definir o limite de tempo de limpeza automática do dispositivo para até 30 dias (em vez do limite anterior de 90 dias) após o último logon. Para fazer isso, vá até **Intune** > **Dispositivos** > **Configuração** > **Regras de Limpeza do Dispositivo**.

#### <a name="build-number-included-on-android-device-hardware-page----4461910-----"></a>Número de build incluído na página Hardware do dispositivo Android <!-- 4461910   -->
Há uma nova entrada na página Hardware para cada dispositivo Android inclui o número de build do sistema operacional do dispositivo. Para obter mais informações, confira [Exibir detalhes do dispositivo no Intune](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Semana de 5 de agosto de 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices-----4843713---"></a>A Zebra Technologies é um OEM com suporte para OEMConfig em dispositivos Android Enterprise  <!-- 4843713 -->

No Intune, você pode criar perfis de configuração de dispositivo e aplicar as configurações a dispositivos Android Enterprise usando o OEMConfig (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **OEMConfig** para o tipo de perfil).

Nesta atualização, a Zebra Technologies é um OEM (fabricante de equipamento original) com suporte para OEMConfig. Para saber mais sobre o OEMConfig, confira [Usar e gerenciar dispositivos Android Enterprise com o OEMConfig](../configuration/android-oem-configuration-overview.md).

Aplica-se a:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019"></a>Semana de 22 de julho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="customized-notifications-for-users-and-groups-------16766574------------"></a>Notificações personalizadas para usuários e grupos    <!-- 16766574          -->
Envie notificações por push personalizadas do aplicativo Portal da Empresa para os usuários em dispositivos Android e iOS que você gerencia com o Intune. Essas notificações por push móveis são altamente personalizáveis com texto livre e podem ser usadas para qualquer finalidade. Você pode direcioná-las para grupos de usuários diferentes em sua organização. Para saber mais, confira [Notificações personalizadas](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app----3041950----"></a>Aplicativo do Controlador de Política de Dispositivo do Google <!-- 3041950  -->
O aplicativo Tela Inicial Gerenciada agora fornece acesso ao aplicativo Política do Dispositivo Android do Google. O aplicativo Tela Inicial Gerenciada é um inicializador personalizado usado para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) que usam o modo de quiosque de vários aplicativos. Você pode acessar o aplicativo Política do Dispositivo Android ou orientar os usuários ao aplicativo Política do Dispositivo Android, para fins de suporte e de depuração. Essa capacidade de inicialização está disponível no momento em que o dispositivo é registrado e bloqueado na Tela Inicial Gerenciada. Nenhuma instalação adicional é necessária para usar essa funcionalidade.

#### <a name="outlook-protection-settings-for-ios-and-android-devices----3212619---"></a>Configurações de proteção do Outlook para dispositivos iOS e Android <!-- 3212619 -->
Agora, você pode definir as configurações gerais e de proteção de dados do aplicativo do Outlook para iOS e do Android usando simples controles de administrador do Intune sem registro de dispositivo. As configurações gerais do aplicativo fornecem paridade com as configurações que os administradores podem habilitar ao gerenciar o Outlook para iOS e Android em dispositivos registrados. Para saber mais sobre as configurações do Outlook, confira [Implantar definições de configurações de aplicativos do Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 eeready   idstaged -->

Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma > **Regras de aplicabilidade**). Nesta atualização, você pode criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Para adicionar uma regra de aplicabilidade, confira [Regras de aplicabilidade](../configuration/device-profile-create.md#applicability-rules).

Aplica-se a: Windows 10 e posterior

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices----3330008----"></a>Usar tokens para adicionar informações específicas do dispositivo em perfis personalizados para dispositivos iOS e macOS <!-- 3330008  -->
Você pode usar perfis personalizados em dispositivos iOS e macOS para definir configurações e recursos que não são internos no Intune (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** ou **macOS** para plataforma > **Personalizado** para o tipo de perfil). Nessa atualização, você pode adicionar tokens aos seus arquivos `.mobileconfig` para adicionar informações específicas do dispositivo. Por exemplo, você pode adicionar `Serial Number: {{serialnumber}}` ao seu arquivo de configuração para mostrar o número de série do dispositivo.

Para criar um perfil personalizado, confira [Configurações personalizadas do iOS](../configuration/custom-settings-ios.md) ou [Configurações personalizadas do macOS](../configuration/custom-settings-macos.md).

Aplica-se a:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769-----"></a>Novo designer de configuração ao criar um perfil de OEMConfig para Android Enterprise <!-- 3712769   -->
No Intune, você pode criar um perfil de configuração de dispositivo que usa um aplicativo OEMConfig (Configuração de dispositivo > Perfis > Criar perfil > Android Enterprise para plataforma > OEMConfig para o tipo de perfil). Quando você fizer isso, um editor de JSON é aberto com um modelo e valores para que você altere. 

Essa atualização inclui um Designer de configuração com uma experiência de usuário aprimorada que mostra detalhes inseridos no aplicativo, incluindo títulos, descrições e muito mais. O editor de JSON ainda está disponível e mostra todas as alterações feitas no Designer de configuração.

Para ver as configurações atuais, vá para [Usar e gerenciar dispositivos Android Enterprise com o OEMConfig](../configuration/android-oem-configuration-overview.md).

Aplica-se a: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello-----4089576--------------"></a>Interface do usuário atualizada para configurar o Windows Hello  <!-- 4089576            -->
Atualizamos o console onde você vai [Configurar o Intune para usar o Windows Hello para empresas](../protect/windows-hello.md). Agora, todas as definições de configuração estão disponíveis no mesmo painel do console em que você habilita o suporte para o Windows Hello. 


#### <a name="intune-powershell-sdk----4924113---"></a>SDK do Intune PowerShell <!-- 4924113 --> 
O SDK do Intune PowerShell, compatível com a API do Intune no Microsoft Graph, foi atualizado para a versão 6.1907.1.0. O SDK agora é compatível com o seguinte:
- Funciona com a Automação do Azure.
- Compatível com as operações de leitura de autenticação somente de aplicativo. 
- Compatível com nomes abreviados amigáveis como aliases.
- Em conformidade com as convenções de nomenclatura do PowerShell. Especificamente, o parâmetro `PSCredential` (no cmdlet `Connect-MSGraph`) foi renomeado para `Credential`.
- Compatível com a especificação manual do valor do cabeçalho `Content-Type` ao usar o cmdlet `Invoke-MSGraphRequest`.

Para saber mais, confira [SDK do PowerShell para API do Graph do Microsoft Intune](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="updates-for-enrollment-restrictions-----2871968---"></a>Atualizações para restrições de registro  <!-- 2871968 -->
As restrições de registro para novos locatários foram atualizadas para que os perfis de trabalho do Android Enterprise sejam permitidos por padrão. Os locatários existentes não sofrerão alteração. Para usar perfis de trabalho do Android Enterprise, você ainda precisa [conectar sua conta do Intune à sua conta do Google Play Gerenciado](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions---4089575-4089579----"></a>Atualizações de interface do usuário para registro da Apple e restrições de registro <!--4089575, 4089579  -->
Os processos a seguir usam uma interface do usuário de estilo assistente:
- Registro do dispositivo da Apple. Para saber mais, veja [Registrar automaticamente dispositivos iOS com o Programa de registro de dispositivos da Apple](../enrollment/device-enrollment-program-enroll-ios.md).
- Criação de restrição de registro. Para saber mais, confira [Definir restrições de registro](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices----4711509--idmiss---"></a>Manipular a pré-configuração de identificadores de dispositivos corporativos para dispositivos Android Q <!-- 4711509  idmiss -->
No Android Q (V10), a Google removerá a capacidade de agentes de MDM em dispositivos Android gerenciados por legado (administrador do dispositivo) para coletar informações de identificador de dispositivo.  O Intune tem um recurso que permite que os administradores de TI [configurem previamente uma lista de números de série de dispositivos ou IMEIs](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) para marcar automaticamente esses dispositivos como corporativos. Esse recurso não funcionará para dispositivos Android Q gerenciados pelo administrador.  Independentemente do número de série ou IMEI do dispositivo ser carregado, ele sempre será considerado pessoal durante o registro no Intune.  Você pode alternar manualmente a propriedade para corporativo após o registro.  Isso afeta apenas os novos registros e os dispositivos registrados existentes não são afetados.  Os dispositivos Android gerenciados com perfis de trabalho não são afetados por essa alteração e continuarão a funcionar normalmente.  Além disso, os dispositivos Android Q registrados como administrador do dispositivo não poderão mais informar o número de série ou IMEI no console do Intune como propriedades do dispositivo.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices----4977730---"></a>Os ícones foram alterados para registros do Android Enterprise (perfil de trabalho, dispositivos dedicados e dispositivos totalmente gerenciados) <!-- 4977730 -->
Os ícones para perfis de registro do Android Enterprise foram alterados. Para ver os novos ícones, vá para **Intune** > **Registro** > **Registro do Android** > procure em **Perfis de registro**.


#### <a name="windows-diagnostic-data-collection-change----4113859---"></a>Alteração de coleta de Dados de Diagnóstico do Windows <!-- 4113859 -->
O valor padrão para coleta de dados de diagnóstico foi alterado para dispositivos que executam o Windows 10, versão 1903 e posteriores. A partir do Windows 10 1903, a coleta de dados de diagnóstico está habilitada por padrão. Os dados de diagnóstico do Windows são dados técnicos vitais de dispositivos Windows sobre o dispositivo e como o Windows e o software relacionado estão sendo executados. Para saber mais, veja [Configurar dados de diagnóstico do Windows em sua organização](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Os dispositivos de piloto automático também são aceitos na telemetria "Completa", a menos que definido de outra forma no perfil do AutoPilot com [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="improve-device-location---3855417----"></a>Melhorar a localização do dispositivo<!-- 3855417  -->
Você pode ampliar as coordenadas exatas de um dispositivo usando a ação **Localizar dispositivo**. Para saber mais sobre como localizar dispositivos iOS perdidos, confira [Localizar dispositivos iOS perdidos](../remote-actions/device-locate.md).


### <a name="device-security"></a>Segurança de dispositivo

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview------1311949-------"></a>Configurações avançadas do Windows Defender Firewall (versão prévia pública)  <!--  1311949     -->  
Use o Intune para gerenciar [regras de firewall personalizadas como parte de um perfil de configuração de dispositivo](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) para proteção de ponto de extremidade no Windows 10. As regras poderão especificar o comportamento de entrada e saída para aplicativos, endereços de rede e portas. 

#### <a name="updated-ui-for-managing-security-baselines------4091125-------"></a>Interface do usuário atualizada para gerenciar linhas de base de segurança   <!-- 4091125     -->
Atualizamos a [experiência de criação e edição](../protect/security-baselines.md#create-the-profile) no console do Intune para nossas linhas de base de segurança. Alterações incluem:

Um formato de estilo de assistente mais simples, que foi condensado para uma única folha. dentro de uma folha. Esse novo design elimina a expansão da folha que exige que os profissionais de TI percorram vários painéis separados.  
Agora, você pode criar Atribuições como parte da experiência de criação e edição, em vez de ter que retornar posteriormente para atribuir linhas de base. Adicionamos um resumo das configurações que você pode exibir antes de criar uma nova linha de base e ao editar uma existente. Ao editar, o resumo mostra apenas a lista de itens definidos na categoria de propriedades em edição.



<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Semana de 15 de julho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="managed-home-screen-and-managed-settings-icons----4918107---"></a>Ícones de Configurações Gerenciadas e Tela Inicial Gerenciada <!-- 4918107 -->
O ícone do aplicativo de Tela Inicial Gerenciada e o ícone de **Configurações Gerenciadas** foram atualizados. O aplicativo Tela Inicial Gerenciada é usado apenas para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) e executando o modo de quiosque em vários aplicativos. Para saber mais sobre o aplicativo de Tela Inicial Gerenciada, confira [Configurar o aplicativo de Tela Inicial Gerenciada da Microsoft para Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices----4918136---"></a>Política de dispositivo Android em dispositivos Android Enterprise dedicados <!-- 4918136 -->
Você pode acessar o aplicativo de Política de dispositivo Android na tela de depuração do aplicativo de Tela Inicial Gerenciada. O aplicativo Tela Inicial Gerenciada é usado apenas para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) e executando o modo de quiosque em vários aplicativos. Para saber mais, confira [Configurar o aplicativo de Tela Inicial Gerenciada da Microsoft para o Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates----3902931---"></a>Atualizações do Portal da Empresa para iOS <!-- 3902931 -->
O nome da sua empresa nos prompts de gerenciamento de aplicativo iOS substituirá o texto "i.manage.microsoft.com" atual. Por exemplo, os usuários verão o nome da empresa em vez de "i.manage.microsoft.com" quando os usuários tentarem instalar um aplicativo iOS do Portal da Empresa ou quando os usuários permitirem o gerenciamento do aplicativo. Isso será distribuído para todos os clientes durante os próximos dias.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="manage-filevault-for-macos-------3858502--4557986--1210104----"></a>Gerenciar FileVault para macOS   <!--  3858502 + 4557986 + 1210104  -->
Você pode usar o Intune para [gerenciar a criptografia de chave FileVault para dispositivos macOS](../protect/encrypt-devices.md). Para criptografar dispositivos, use um perfil de configuração de dispositivo do Endpoint Protection.

Nosso suporte para FileVault inclui criptografia de dispositivos não criptografados, caução de uma chave de recuperação pessoal de dispositivos, rotação automática ou manual de chaves de criptografia pessoais e recuperação de chave para seus dispositivos corporativos. Os usuários finais também podem usar o site Portal da Empresa para obter a chave de recuperação pessoal para seus dispositivos criptografados. 

Também expandimos o relatório de criptografia para incluir [informações sobre o FileVault](../protect/encryption-monitor.md) junto com as informações do BitLocker, para que você possa visualizar todos os detalhes de criptografia do seu dispositivo em um só lugar. 

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user----4156123---"></a>Redefinir o Windows AutoPilot remove o usuário principal do dispositivo <!-- 4156123 -->
Quando a redefinição do AutoPilot for usada em um dispositivo, o usuário primário do dispositivo será removido. O próximo usuário que entrar após a redefinição será definido como o usuário primário. Esse recurso será distribuído para todos os clientes durante os próximos dias.

## <a name="week-of-july-8-2019"></a>Semana de 8 de julho de 2019

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Novas configurações do Office, do Windows e do OneDrive nos modelos administrativos do Windows 10 <!-- 3510695 -->

Você pode criar modelos administrativos no Intune que imitam o gerenciamento de política de grupo local (**Gerenciamento de dispositivos** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Modelo administrativo** para tipo de perfil).

Essa atualização inclui mais configurações do Office, do Windows e do OneDrive que você pode adicionar aos seus modelos. Com essas novas configurações, agora você pode definir mais de 2.500 configurações que são 100% baseadas em nuvem.

Para saber mais sobre esse recurso, confira [Usar modelos do Windows 10 para definir as configurações da política de grupo no Intune](../configuration/administrative-templates-windows.md).

Aplica-se a: Windows 10 e posterior

## <a name="week-of-july-1-2019"></a>Semana de 1º de julho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="aad-and-app-on-android-enterprise-devices----3574267---"></a>AAD e APP em dispositivos Android Enterprise <!-- 3574267 -->
Ao integrar dispositivos Android Enterprise totalmente gerenciados, os usuários agora serão registrados com o AAD (Azure Active Directory) durante a configuração inicial de seu dispositivo novo ou na redefinição de fábrica. Anteriormente, para um dispositivo totalmente gerenciado, após a conclusão da configuração, o usuário precisava iniciar manualmente o aplicativo Microsoft Intune para começar o registro do AAD. Agora, quando o usuário chega na home page do dispositivo após a configuração inicial, o dispositivo é registrado e inscrito.

Além das atualizações do AAD, agora as APP (políticas de proteção de aplicativo) do Intune são compatíveis com dispositivos Android Enterprise totalmente gerenciados. Essa funcionalidade ficará disponível à medida que for distribuída. Para saber mais, confira [Adicionar aplicativos do Google Play gerenciado a dispositivos Android Enterprise com o Intune](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019"></a>Semana de 24 de junho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Configurar que navegador tem permissão para vincular a dados da organização <!-- 3145939 -->
As APP (Políticas de Proteção de Aplicativo) do Intune em dispositivos Android e iOS agora permitem que você transfira links da Web da organização para um navegador específico além do Intune Managed Browser do ou Microsoft Edge.  Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>A página Todos os aplicativos identifica como online/offline os Aplicativos da Microsoft Store para Empresas<!--4089647 -->
A página **Todos os aplicativos** agora inclui rótulos para identificar aplicativos do MSFB (Microsoft Store for Business) como aplicativos online ou offline. Cada aplicativo MSFB agora inclui um sufixo para **Online** ou **Offline**. A página de detalhes do aplicativo também inclui as informações de **Tipo de licença** e **Suporte à instalação de contexto de dispositivo** (somente aplicativos licenciados offline).

#### <a name="company-portal-app-on-windows-shared-devices---4393553---"></a>Aplicativo do Portal da Empresa em dispositivos compartilhados do Windows <!--4393553 -->
Agora os usuários podem acessar o aplicativo do Portal da Empresa em dispositivos compartilhados do Windows. Os usuários finais verão um rótulo **Compartilhado** no bloco do dispositivo. Isso se aplica ao Aplicativo do Portal da Empresa para Windows versão 10.3.45609.0 e posterior.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page----4224326---"></a>Exibir todos os aplicativos da nova página da Web do Portal da Empresa <!-- 4224326 -->
A nova página **Aplicativos Instalados** do site Portal da Empresa lista todos os aplicativos gerenciados (tanto obrigatórios quanto disponíveis) instalados em dispositivos do usuário. Além do tipo de atribuição, os usuários podem ver o publicador do aplicativo, a data de publicação e o status atual da instalação. Se você ainda não tornou nenhum aplicativo obrigatório ou disponível aos usuários, eles verão uma mensagem explicando que nenhum aplicativo da empresa foi instalado. Para ver a nova página na Web, acesse o [site do Portal da Empresa](https://portal.manage.microsoft.com) e clique em **Aplicativos Instalados**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device----2352913---"></a>A nova exibição permite que os usuários vejam todos os aplicativos gerenciados instalados no dispositivo <!-- 2352913 -->  
O aplicativo Portal da Empresa para Windows agora lista todos os aplicativos gerenciados (tanto obrigatórios quanto disponíveis) instalados em um dispositivo do usuário. Os usuários também podem exibir tentativas de instalação e instalações de aplicativo pendentes e o status atual. Se você ainda não tornou aplicativos obrigatórios ou disponíveis aos usuários, eles verão uma mensagem explicando que nenhum aplicativo da empresa está instalado. Para ver a nova exibição, vá para o painel de navegação Portal da Empresa e selecione **Aplicativos** > **Aplicativos Instalados**.    

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Definir configurações para extensões de kernel em dispositivos macOS <!-- 2043024 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma). Essa atualização inclui um novo grupo de configurações que permite configurar e usar extensões de kernel em seus dispositivos. Você pode adicionar extensões específicas ou permitir todas as extensões de um parceiro ou desenvolvedor específico.

Para saber mais sobre esse recurso, confira a [visão geral das extensões do kernel](../configuration/kernel-extensions-overview-macos.md) e as [configurações de extensão do kernel](../configuration/kernel-extensions-settings-macos.md).

Aplica-se a: macOS 10.13.2 e posteriores

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002---"></a>Configuração de Aplicativos somente da loja para dispositivos Windows 10 incluem mais opções de configuração <!-- 2697002 -->
Quando você cria um perfil de restrições de dispositivo para dispositivos Windows, pode usar a configuração **Somente aplicativos da loja** para que os usuários instalem somente aplicativos da Windows Store (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Restrições de dispositivo** para tipo de perfil). Nessa atualização, essa configuração é expandida para dar suporte a mais opções. 

Para ver a nova configuração, vá para [Configurações do dispositivo Windows 10 (e mais recentes) para permitir ou restringir recursos](../configuration/device-restrictions-windows-10.md#app-store).

Aplica-se a: Windows 10 e posterior

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Implantar vários perfis de dispositivo de extensões de mobilidade Zebra em um dispositivo, mesmo grupo de usuários ou mesmo grupo de dispositivos <!-- 4089955 -->
No Intune, você pode usar extensões de mobilidade Zebra (MX) em um perfil de configuração do dispositivo para personalizar as configurações dos dispositivos Zebra que não são nativas do Intune. No momento, você pode implantar um perfil em um único dispositivo. Nesta atualização, você pode implantar vários perfis para:
- O mesmo grupo de usuários
- O mesmo grupo de dispositivos
- Um único dispositivo

[Usar e gerenciar dispositivos Zebra com o Zebra Mobility Extensions no Microsoft Intune](../configuration/android-zebra-mx-overview.md) mostra como usar o MX no Intune.

Aplica-se a: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Algumas configurações de quiosque em dispositivos iOS são definidas usando "Bloquear", substituindo "Permitir" <!-- 4404075  -->
Quando você cria um perfil de restrições de dispositivo em dispositivos iOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **Restrições de dispositivo** para tipo de perfil > **Quiosque**), define **Bloqueio automático**, **botão de Toque**, **Rotação da tela**, **botão Suspender tela** e **botões de Volume**. 

Nessa atualização, os valores são **Bloquear** (bloqueia o recurso) e **Não configurado** (permite o recurso). Para ver as configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos](../configuration/device-restrictions-ios.md#kiosk). 

Aplica-se a: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704---"></a>Use o Face ID para autenticação de senha em dispositivos iOS <!-- 4490704 -->
Quando você cria um perfil de restrições de dispositivo para dispositivos iOS, pode usar uma impressão digital para uma senha. Nessa atualização, as configurações de senha de impressão digital também permitem reconhecimento facial (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** tipo de perfil > **Senha**). Como resultado, as configurações a seguir mudaram:

- **Desbloqueio por impressão digital** agora é **Desbloqueio por Touch ID e Face ID**.
- **Modificação de impressão digital (somente supervisionada)** agora é **Modificação de Touch ID e Face ID (somente supervisionada)** .

O Face ID está disponível no iOS 11.0 e posteriores. Para ver as configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md#password).

Aplica-se a: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region----4593948---"></a>Restringir recursos da loja de aplicativo e jogos em dispositivos iOS agora é dependente da região de classificações <!-- 4593948 -->
Em dispositivos iOS, você pode permitir ou restringir recursos relacionados a jogos, à loja de aplicativos e à exibição de documentos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** tipo de perfil > **App Store, Exibição de Documentos, Jogos**). Também é possível escolher a região de Classificações, como Estados Unidos. 

Nessa atualização, o recurso **Aplicativos** foi movido para ser um filho da **Região de classificações** e é dependente da **Região de classificações**. Para ver as configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Aplica-se a: iOS

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join----4809146--"></a>Suporte do Windows AutoPilot para Ingresso no Azure AD Híbrido <!-- 4809146-->
O Windows AutoPilot para dispositivos existentes agora é compatível com o Ingresso no Azure AD Híbrido (além da compatibilidade existente para Ingresso no Azure AD). Aplica-se aos dispositivos Windows 10 versão 1809 e posteriores. Para saber mais, confira [ Windows Autopilot para dispositivos existentes](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).



### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="see-the-security-patch-level-for-android-devices----4461911---"></a>Veja o nível de patch de segurança para dispositivos Android <!-- 4461911 -->
Agora é possível ver o nível de patch de segurança para dispositivos Android. Para isso, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**.
O nível do patch está listado na seção **Sistema operacional**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Atribuir marcas de escopo para todos os dispositivos gerenciados em um grupo de segurança <!-- 3173810 -->
Agora você pode atribuir marcas de escopo a um grupo de segurança e todos os dispositivos no grupo de segurança também serão associados a essas marcas de escopo. Todos os dispositivos nesses grupos também receberão a marca de escopo. As marcas de escopo definidas com esse recurso substituirão as marcas de escopo definidas com o fluxo de marcas de escopo atual do dispositivo. Para saber mais, confira [Usar o RBAC e marcas de escopo na TI distribuída](scope-tags.md).

### <a name="device-security"></a>Segurança de dispositivo

#### <a name="use-keyword-search-with-security-baselines-------"></a>Usar pesquisa de palavra-chave com Linhas de base de segurança <!--  -->
Ao criar ou editar [Perfis de linha de base de segurança](../protect/security-baselines.md#create-the-profile), você pode especificar palavras-chave na nova barra de *Pesquisa* para filtrar os grupos de configurações disponíveis para aqueles que contêm seus critérios de pesquisa. 

#### <a name="the-security-baselines-feature-is-now-generally-available-----3785395---"></a>O recurso Linhas de Base de Segurança agora está disponível para o público geral  <!-- 3785395 -->
O recurso **Linhas de Base de Segurança** não está mais na versão prévia e agora está disponível para o público geral (GA).  Isso significa que o recurso está pronto para uso na produção. No entanto, os modelos de linha de base individuais podem permanecer na versão prévia e serão avaliados e liberados para GA em suas próprias programações.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available------3794072-4217151--3534649---"></a>O modelo de Linha de base de segurança do MDM já está disponível ao público geral   <!-- 3794072, 4217151,  3534649 -->
O modelo de linha de base de segurança do MDM foi removido da versão prévia e agora está disponível para o público geral (GA). O modelo GA é identificado como **Linha de base de segurança do MDM para maio de 2019**.  Esse é um novo modelo e não uma atualização da versão de visualização.  Como um novo modelo, você precisará examinar as [configurações que ele contém](../protect/security-baseline-settings-mdm.md) e criar novos perfis para implantá-lo em seu dispositivo. Outros modelos de linha de base de segurança podem permanecer em versão prévia. Para obter uma lista de linhas de base disponíveis, confira [Linhas de base de segurança disponíveis](../protect/security-baselines.md#available-security-baselines).  

Além de ser novo, o modelo *Linha de base de segurança do MDM para maio de 2019* inclui as duas configurações que anunciamos recentemente em nosso artigo Em desenvolvimento:  
- Acima do Bloqueio: aplicativos ativados por voz de uma tela bloqueada  
- DeviceGuard: usa VBS (segurança baseada em virtualização) na próxima reinicialização dos dispositivos.  

A *Linha de base de segurança do MDM para maio de 2019* também inclui a adição de várias novas configurações, a remoção de outras e uma revisão do valor padrão de uma configuração. Para obter uma lista detalhada das alterações de versão prévia para GA, confira **O que mudou no novo modelo**.

#### <a name="security-baseline-versioning-----3194322---"></a>Controle de versão de linha de base de segurança  <!-- 3194322 -->
Linhas de base de segurança para o controle de versão de suporte do Intune. Com esse suporte, à medida que novas versões de cada linha de base de segurança são lançadas, você pode atualizar seus perfis de linha de base de segurança existentes para usar a versão de linha de base mais recente sem precisar recriar e implantar uma nova linha de base do zero. Além disso, no console do Intune, é possível exibir as informações sobre cada linha de base, como o número de perfis individuais que usam a linha de base, quantas versões diferentes da linha de base são usadas por seus perfis e quando foi lançada a linha de base de segurança específica mais recente.  Para saber mais, confira **Linhas de base de segurança**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved-----4501151---"></a>A configuração Usar chaves de segurança para entrada foi movida  <!-- 4501151 -->
A definição de configuração do dispositivo para a proteção de identidade chamada **Usar chaves de segurança para entrada** não é mais encontrada como uma subconfiguração de *Configurar o Windows Hello para Empresas*. Agora é uma configuração de nível superior que está sempre disponível, mesmo quando você não habilita o uso do Windows Hello para Empresas. Para saber mais, confira [Proteção de identidade](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="new-permissions-for-assigned-group-admins------4504437-----"></a>Novas permissões para administradores de grupos atribuídos   <!-- 4504437   -->
A função interna de Administrador da escola do Intune agora tem permissões CRUD (criar, ler, atualizar e excluir) para Aplicativos Gerenciados. Essa atualização significa que, se você estiver atribuído como administrador de grupo no Intune para Educação, agora poderá criar, exibir, atualizar e excluir os MDM Push Certificate do iOS, tokens de servidor MDM do iOS e tokens VPP do IOS, junto com [todas as permissões existentes que você tem](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Para executar qualquer uma dessas ações, vá para **Configurações de locatário** > **Gerenciamento de dispositivo iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials----4655885---"></a>Os aplicativos podem usar o API do Graph para chamar as operações de leitura sem credenciais de usuário <!-- 4655885 -->
Aplicativos podem chamar operações de leitura da API do Graph do Intune com identidade de aplicativo sem credenciais de usuário. Para saber mais sobre como acessar a API do Microsoft Graph para Intune, confira [Como trabalhar com o Intune no Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps----4392555---"></a>Aplicar marcas de escopo nos Aplicativos da Microsoft Store para Empresas <!-- 4392555 -->
Agora é possível aplicar marcas de escopo nos Aplicativos da Microsoft Store para Empresas. Saiba mais sobre marcas de escopo, confira [Usar RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](scope-tags.md).

## <a name="week-of-june-17-2019"></a>Semana de 17 de junho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="new-features-in-microsoft-intune-app"></a>Novos recursos do aplicativo do Microsoft Intune
Adicionamos novos recursos ao aplicativo do Microsoft Intune (versão prévia) para Android. Os usuários em dispositivos Android totalmente gerenciados agora podem:  

* Exibir e gerenciar os dispositivos registrados por meio do aplicativo Portal da Empresa do Intune ou o aplicativo Microsoft Intune.    
* Entre em contato com a organização para suporte.    
* Enviar comentários para a Microsoft.    
* Exibir os termos e condições, se definido pela organização.    

## <a name="week-of-june-10-2019"></a>Semana de 10 de junho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>Novos aplicativos de exemplo que mostram a integração do SDK do Intune disponível no GitHub <!-- 2653471 -->
O conta do GitHub do msintuneappsdk adicionou novos exemplos de aplicativos para iOS (Swift), Android, Xamarin.iOS, Xamarin Forms e Xamarin.Android. Esses aplicativos devem complementar nossa documentação existente e fornecer demonstrações de como integrar o SDK de aplicativo do Intune em seus próprios aplicativos móveis. Se você for um desenvolvedor de aplicativo que precisa de orientações adicionais sobre o SDK do Intune, confira os seguintes exemplos vinculados:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) – um aplicativo de mensagens instantâneas nativo para iOS nativo (Swift), que usa a biblioteca de autenticação do Azure Active Directory (ADAL) para a autenticação agenciada.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) - um aplicativo de lista de tarefas pendentes nativo para Android que usa ADAL para autenticação agenciada.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) - um aplicativo de lista de tarefas pendentes para Xamarin.Android que usa a ADAL para autenticação agenciada. Esse repositório também tem o aplicativo Xamarin.Forms.
- [Aplicativo de exemplo do Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) - um aplicativo de exemplo barebones para Xamarin.iOS.

## <a name="week-of-may-27-2019"></a>Semana de 27 de maio de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Relatórios para aplicativos potencialmente prejudiciais em dispositivos Android <!-- 4223162 -->
Agora, o Intune fornece informações adicionais de relatórios sobre aplicativos potencialmente prejudiciais em dispositivos Android. 

## <a name="week-of-may-20-2019"></a>Semana de 20 de maio de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="windows-company-portal-app----3316993---"></a>Aplicativo do Portal da Empresa para Windows <!-- 3316993 -->
O aplicativo do Portal da Empresa do Windows agora terá uma nova página rotulada **Dispositivos**. A página **Dispositivos** mostrará aos usuários finais todos os seus dispositivos registrados. Os usuários verão essa alteração no Portal da Empresa quando usarem a versão 10.3.4291.0 e posterior. Para obter informações sobre como configurar o Portal da Empresa, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Nome do atributo OrderID do dispositivo Autopilot alterado para Marcação de Grupo <!-- 4659453 -->

Para torná-lo mais intuitivo, o nome do atributo **OrderID** em dispositivos do Autopilot foi alterado para **Marcação de Grupo**. Ao usar CSVs para carregar informações do dispositivo do Autopilot, você precisa usar Marcação de Grupo como o cabeçalho de coluna, não OrderID.  

## <a name="week-of-may-13-2019"></a>Semana de 13 de maio de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359----"></a>Método de autenticação de atualização das políticas do Intune e instalação do aplicativo Portal da Empresa  <!-- 1927359  -->
Em dispositivos já registrados por meio do Assistente de Instalação com um dos métodos de registro de dispositivo corporativo da Apple, o Intune não oferecerá mais o suporte do Portal da Empresa quando for instalado manualmente pelos usuários finais da loja de aplicativos. Essa alteração só é relevante quando você autentica com o Assistente de Configuração da Apple durante o registro. Além disso, essa alteração afeta apenas dispositivos iOS registrados via:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Programa de registro de dispositivos (DEP) da Apple

Se os usuários instalarem o aplicativo Portal da Empresa pela loja de aplicativos e tentarem registrar esses dispositivos por meio do aplicativo, receberão um erro. Esses dispositivos só devem usar o Portal da Empresa quando ele for enviado por push, automaticamente, pelo Intune durante o registro. Os perfis de registro no Intune, no portal do Azure, serão atualizados para que você possa especificar como os dispositivos são autenticados, e se o usuário recebe o aplicativo Portal da Empresa. Se você quiser que os usuários de dispositivos DEP tenham o Portal da Empresa, especifique suas preferências em um perfil de registro. 

Além disso, a tela **Identificar seu dispositivo** no Portal da Empresa do iOS está sendo removida. Portanto, os administradores que desejem habilitar o Acesso Condicional ou implantar aplicativos da empresa devem atualizar o perfil de registro de DEP. Esse requisito aplica-se somente se o registro de DEP for autenticado com o Assistente de Configuração. Nesse caso, você deve efetuar push do Portal da Empresa para o dispositivo. Para fazer isso, escolha **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Propriedades** > defina **Instalar o Portal da Empresa** para **Sim**.

Para instalar o Portal da Empresa em dispositivos DEP já registrados, acesse Intune > Aplicativos Cliente, e envie-o como um aplicativo gerenciado com políticas de configuração de aplicativo. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Configurar o modo como os usuários finais atualizam um aplicativo de linha de negócios (LOB) usando uma política de proteção de aplicativo <!-- 3568384 -->
Agora é possível configurar onde os usuários finais podem obter uma versão atualizada de um aplicativo de linha de negócios (LOB). Os usuários finais verão esse recurso na caixa de diálogo de inicialização condicional **Versão mínima do aplicativo**, que solicitará que os usuários finais atualizem para uma versão mínima do aplicativo de linha de negócios. Forneça esses detalhes de atualização como parte de sua política de proteção de aplicativo de linha de negócios (APP). Este recurso está disponível para iOS e Android. No iOS, esse recurso requer que o aplicativo seja integrado (ou encapsulado usando a ferramenta de encapsulamento) ao SDK do Intune para iOS v. 10.0.7 ou versão posterior. No Android, esse recurso exige a versão mais recente do Portal da Empresa. Para configurar o modo como um usuário final atualiza um aplicativo de linha de negócios, o aplicativo precisa que uma política de configuração de aplicativo gerenciado seja enviada a ele com a chave, `com.microsoft.intune.myappstore`. O valor enviado define de qual repositório o usuário final baixará o aplicativo. Se o aplicativo for implantado por meio do Portal da Empresa, o valor deverá ser `CompanyPortal`. Para qualquer outro repositório, você deverá inserir uma URL completa.

#### <a name="intune-management-extension-powershell-scripts-----3734186----"></a>Scripts do PowerShell da extensão de gerenciamento do Intune  <!-- 3734186  -->
A execução de scripts do PowerShell pode ser configurada com privilégios de administrador do usuário no dispositivo. Saiba mais em [Usar scripts do PowerShell em dispositivos Windows 10 no Intune](../apps/intune-management-extension.md) e [Gerenciamento de Aplicativos Win32](../apps/app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Gerenciamento de aplicativos do Android Enterprise <!-- 4459905 -->
Para facilitar a configuração e o uso do gerenciamento de Android Enterprise pelos administradores de TI, o Intune adicionará automaticamente quatro aplicativos comuns relacionados ao Android Enterprise ao console do administrador do Intune. Os quatro aplicativos do Android Enterprise são os seguintes apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – usado para cenários totalmente gerenciados pelo Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – ajuda a entrar em suas contas se usar a verificação de dois fatores.
- **[Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – usado para cenários de perfil de trabalho das Políticas de Proteção do Aplicativo (APP) e do Android Enterprise.
- [Tela inicial gerenciada](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – usado para cenários dedicados/quiosques do Android Enterprise.

Antes, os administradores de TI precisavam encontrar e aprovar manualmente esses aplicativos na [Google Play Store gerenciada](https://play.google.com/store/apps) como parte da configuração. Essa alteração remove essas etapas que eram manuais para tornar mais fácil e rápido para os clientes usarem o gerenciamento do Android Enterprise.

Os administradores verão esses quatro aplicativos adicionados automaticamente à lista de aplicativos do Intune no momento em que conectarem pela primeira vez o locatário do Intune ao Google Play gerenciado. Confira mais informações em [Conectar sua conta do Intune à sua conta gerenciada do Google Play](../enrollment/connect-intune-android-enterprise.md). Para locatários que já conectaram o próprio locatário ou que já usam o Android Enterprise, não há nada que os administradores precisem fazer. Esses quatro aplicativos aparecerão automaticamente dentro de sete dias após a conclusão da implantação do serviço em maio de 2019.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Conector do Certificado PFX atualizado do Microsoft Intune  <!-- 1533038 -->
Lançamos uma atualização para o [Conector do Certificado PFX para o Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) que resolve um problema em que os certificados PFX existentes continuam a ser reprocessados, o que faz com que o conector pare de processar novas solicitações.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Tarefas de segurança do Intune para Defender ATP (em versão prévia pública)     <!-- 3208597 -->
Na versão prévia pública, você pode usar o Intune para gerenciar [tarefas de segurança para a ATP (Proteção Avançada contra Ameaças) do Microsoft Defender](../protect/atp-manage-vulnerabilities.md). Essa integração com a ATP adiciona uma abordagem baseada em riscos para detectar, priorizar e corrigir vulnerabilidades e configurações incorretas do ponto de extremidade, enquanto reduz o tempo entre a descoberta e a mitigação.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671   idstaged-->
Muitos dispositivos Windows 10 e posteriores têm chipsets TPM (Trusted Platform Module). Esta atualização inclui uma nova configuração de conformidade que verifica a versão do chip TPM no dispositivo. 

O artigo [Configurações de política de conformidade do Windows 10 e posteriores](../protect/compliance-policy-create-windows.md#device-security) descreve esta configuração.

Aplica-se a: Windows 10 e posterior

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Impedir que usuários finais alterem o ponto de acesso pessoal e desabilitem o registro em log do servidor Siri em dispositivos iOS <!-- 4097904   -->  
Crie um perfil de restrições de dispositivo no dispositivo iOS (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações que você poderá configurar:

- **Aplicativos internos**: registro em log no lado do servidor para os comandos da Siri
- **Sem fio**: modificação do usuário do Ponto de acesso pessoal (somente supervisionado)

Para ver essas configurações, vá para [Configurações de aplicativo interno para iOS](../configuration/device-restrictions-ios.md#built-in-apps) e [Configurações sem fio para iOS](../configuration/device-restrictions-ios.md#wireless).

Aplica-se a: iOS 12.2 e posteriores

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Novas configurações de restrição de dispositivo do aplicativo Sala de aula para dispositivos macOS <!-- 4097905   --> 
Crie perfis de configuração de dispositivo para dispositivos macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Essa atualização inclui novas configurações do aplicativo Sala de aula, a opção de bloquear capturas de tela e a opção de desabilitar a Biblioteca de Fotos do iCloud.

Para ver as configurações atuais, vá para [Configurações do dispositivo macOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-macos.md).

Aplica-se a: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>A senha do iOS para acessar a configuração da loja de aplicativos foi renomeada<!-- 4557891  -->
A configuração **Senha para acessar a loja de aplicativos** foi renomeada para **Exigir a senha do iTunes para todas as compras** (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma> **Restrições do Dispositivo** para o tipo de perfil > **Loja de Aplicativos, Exibição de Documentos, Jogos**).

Para ver as configurações disponíveis, acesse a configuração do iOS [Loja de Aplicativos, Exibição de Documentos, Jogos](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Aplica-se a: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Linha de base da Proteção Avançada contra Ameaças do Microsoft Defender (versão prévia)  <!--  3754134 -->
Adicionamos uma versão prévia da linha de base de segurança para as configurações da [Proteção Avançada contra Ameaças do Microsoft Defender](../protect/security-baseline-settings-defender-atp.md). Esta linha de base está disponível quando seu ambiente atende aos pré-requisitos para usar a [Proteção Avançada contra Ameaças do Microsoft Defender](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>A página Status do Registro do Windows (ESP) já está amplamente disponível <!-- 3605348 -->
A página Status do Registro saiu da versão prévia. Para saber mais, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Atualização da interface de usuário do Intune – Criação de perfil de registro do Autopilot  <!-- 4593669 -->
A interface do usuário para a criação de um perfil de registro do Autopilot foi atualizada para alinhar-se aos estilos de interface do usuário do Azure. Saiba mais em [Criar um perfil de registro do Autopilot](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile). A partir de agora cenários adicionais do Intune serão atualizados para esse novo estilo de interface do usuário.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Habilitar Autopilot Reset para todos os dispositivos do Windows <!-- 4225665 -->
Agora o Autopilot Reset funciona em todos os dispositivos Windows, mesmo aqueles não configurados para usar a página de Status de registro. Se uma página de Status de registro não tiver sido configurada para o dispositivo durante o registro inicial do dispositivo, o dispositivo será direcionado para a área de trabalho depois do login. Ele pode levar até oito horas para sincronizar e aparecer como em conformidade no Intune. Saiba mais em [Redefinir dispositivos com o Windows Autopilot Reset remoto](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>O formato exato do IMEI não é obrigatório ao pesquisar por Todos os dispositivos <!--30407680 -->
Você não precisa incluir espaços em números IMEI ao pesquisar **Todos os dispositivos**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Excluir um dispositivo no portal da Apple será refletido no portal do Intune <!--2489996 -->
Se um dispositivo for excluído do Programa de registro de dispositivos da Apple ou dos portais do Apple Business Manager, o dispositivo será excluído automaticamente do Intune durante a próxima sincronização.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>A Página de status de registro agora acompanha aplicativos Win32 <!-- 2714451 -->
Isso se aplica somente a dispositivos que executam o Windows 10 versão 1903 e superior. Para saber mais, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Redefinir e apagar dispositivos em massa usando a API do Graph <!-- 3295288 -->
Você agora pode redefinir e apagar até 100 dispositivos em massa, usando a API do Graph.


### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>O relatório de criptografia saiu da versão prévia pública   <!-- 4587546      -->
O [relatório para BitLocker e criptografia de dispositivo](../protect/encryption-monitor.md) já está amplamente disponível e não faz mais parte da versão prévia pública. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Assinatura e configurações de biometria do Outlook para dispositivos iOS e Android <!-- 4050557 -->
Agora você pode especificar se a assinatura padrão está habilitada no Outlook em dispositivos iOS e Android. Além disso, pode permitir que os usuários alterem a configuração biométrica do Outlook no iOS.

## <a name="week-of-may-6-2019"></a>Semana de 6 de maio de 2019 

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Suporte do NAC (Controle de Acesso à Rede) do F5 Access para dispositivos iOS <!-- 4500808 -->

O F5 lançou uma atualização para BIG-IP 13 que permite funcionalidade NAC no F5 Access em iOS no Intune. Para usar esse recurso:

- Atualize o BIG-IP para a atualização 13.1.1.5. O BIG-IP 14 não é compatível.
- Integre o BIG-IP com o Intune para NAC. As etapas em [Visão geral: como configurar o APM para verificações de situação do dispositivo com sistemas de gerenciamento de ponto de extremidade](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Verifique a configuração **Habilitar NAC (controle de acesso de rede)** no perfil de VPN no Intune.

Para ver a configuração disponível, vá para [Definir configurações de VPN em dispositivos iOS](../configuration/vpn-settings-ios.md).

Aplica-se a: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Conector do Certificado PFX atualizado do Microsoft Intune <!-- doc-vso 1521237  -->  
Lançamos uma atualização para o [conector de certificado PFX para o Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) que reduz o intervalo de sondagem de 5 minutos para 30 segundos.

## <a name="week-of-april-22-2019"></a>Semana de 22 de abril de 2019

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Usar o Gerenciador de Conformidade para criar avaliações para o Microsoft Intune<!-- 4404750 -->

O [Gerenciador de Conformidade](https://servicetrust.microsoft.com/ComplianceManager) (o link abre outro site da Microsoft) é uma ferramenta de avaliação de risco baseada em fluxo de trabalho no Portal de Confiança do Serviço da Microsoft. Ele permite que você acompanhe, atribua e verifique as atividades de conformidade regulatória de sua organização relacionadas aos serviços da Microsoft. Crie sua própria avaliação de conformidade com o Office 365, o Azure, o Dynamics, os Serviços Profissionais e o Intune. O Intune tem duas avaliações disponíveis – FFIEC e RGPD.

O Gerenciador de Conformidade ajuda você a concentrar seus esforços com o detalhamento dos controles – controles gerenciados pela Microsoft e controles gerenciados por sua organização. Conclua as avaliações e, em seguida, exporte-as e imprima-as.

A conformidade com [FFIEC (Federal Financial Institutions Examination Council)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (o link abre outro site da Microsoft) é um conjunto de padrões de bancos online emitido pelo FFIEC. É a avaliação mais solicitada para instituições financeiras que usam o Intune. Ela interpreta como o Intune ajuda a atender às diretrizes de segurança cibernética do FFIEC relacionadas a cargas de trabalho de nuvem pública. A avaliação do FFIEC do Intune é a segunda avaliação do FFIEC no Gerenciador de Conformidade.

No exemplo a seguir, você poderá ver o detalhamento dos controles do FFIEC. A Microsoft aborda 64 controles. Você é responsável pelos 12 controles restantes.

![Confira uma avaliação de exemplo do Intune para o FFIEC, incluindo as ações do cliente e as ações da Microsoft](./media/whats-new/intune-ffiec-assessment-status.png)

O [RGPD (Regulamento Geral sobre a Proteção de Dados)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (o link abre outro site da Microsoft) é uma lei da UE (União Europeia) que ajuda a proteger os direitos de indivíduos e seus dados. O RGPD é a avaliação mais solicitada para ajudar a cumprir as regulamentações referentes à privacidade. 

No exemplo a seguir, você verá o detalhamento dos controles do RGPD. A Microsoft aborda 49 controles. Você é responsável pelos 66 controles restantes.

![Confira uma avaliação de exemplo do Intune para o RGPD, incluindo as ações do cliente e as ações da Microsoft](./media/whats-new/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Semana de 15 de abril de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Criptografia OpenSSL para políticas de proteção de aplicativo do Android <!-- 3747362 -->
A APP (Política de Proteção de Aplicativo) do Intune em dispositivos Android agora usa uma biblioteca de criptografia OpenSSL em conformidade com o FIPS 140-2. Para obter mais informações, confira a seção [criptografia](../apps/app-protection-policy-settings-android.md#encryption) de [Configurações da política de proteção de aplicativo do Android no Microsoft Intune](../apps/app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Habilitar dependências de aplicativo Win32 <!-- 2617348  -->
Como administrador, você pode exigir que outros aplicativos sejam instalados como dependências antes da instalação do aplicativo Win32. Especificamente, o dispositivo precisa instalar os aplicativos dependentes antes de instalar o aplicativo Win32. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar** para exibir a folha **Adicionar aplicativo**. Selecione **Aplicativo do Windows (Win32)** como o **Tipo de aplicativo**. Depois de adicionar o aplicativo, selecione **Dependências** para adicionar os aplicativos dependentes que precisam ser instalados para que o aplicativo Win32 possa ser instalado. Para obter mais informações, confira [Intune autônomo – gerenciamento de aplicativos Win32](./../apps/app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Informações de instalação de versão do aplicativo para aplicativos da Microsoft Store para Empresas <!-- 3537391   -->
Os relatórios de instalação de aplicativo incluem informações de versão do aplicativo para aplicativos da Microsoft Store para Empresas. No Intune, selecione **Aplicativos cliente** > **Aplicativos**. Selecione um **aplicativo da Microsoft Store para Empresas** e, em seguida, selecione **Status de instalação do dispositivo** na seção **Monitorar**.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Adições às regras de requisitos de aplicativos Win32 <!-- 3676883   -->
Você pode criar regras de requisitos baseadas em scripts do PowerShell, valores do Registro e informações do sistema de arquivos. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Em seguida, selecione **Aplicativo do Windows (Win32)** como o **Tipo de aplicativo** na folha **Adicionar aplicativo**.  Selecione **Requisitos** > **Adicionar** para configurar regras de requisitos adicionais. Em seguida, selecione **Tipo de arquivo**, **Registro** ou **Script** como o **Tipo de requisito**. Para obter mais informações, confira [Gerenciamento de aplicativos Win32](./../apps/app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Configurar os aplicativos Win32 para serem instalados em dispositivos ingressados no Azure AD registrados no Intune <!-- 3695227  -->
Você pode atribuir os aplicativos Win32 para serem instalados em dispositivos ingressados no Azure AD registrados no Intune. Para obter mais informações sobre aplicativos Win32 no Intune, confira [Gerenciamento de aplicativos Win32](./../apps/app-management.md).

#### <a name="device-overview-shows-primary-user---3794259----"></a>A página Visão geral do dispositivo mostra o usuário primário <!--3794259  -->
A página Visão geral do dispositivo mostrará o usuário primário, também chamado de usuário UDA (afinidade de dispositivo de usuário). Para ver o usuário primário de um dispositivo, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo. O usuário primário será exibido próximo à parte superior da página **Visão Geral**.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Relatórios adicionais de aplicativos do Google Play Gerenciado para dispositivos de perfil de trabalho do Android Enterprise <!-- 4105925  -->
Para aplicativos do Google Play Gerenciado implantados em dispositivos de perfil de trabalho do Android Enterprise, você pode exibir o número de versão específico do aplicativo instalado em um dispositivo. Isso se aplica somente aos aplicativos obrigatórios.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>Teclados de terceiros para iOS <!-- 4111843   -->
O suporte da APP (política de proteção de aplicativo) do Intune à configuração **Teclados de Terceiros** do iOS será encerrado devido a uma alteração da plataforma iOS. Você não poderá definir essa configuração no Console de Administração do Intune e ela não será imposta no cliente no SDK do Aplicativo do Intune.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Definir as configurações de logon e controlar as opções de reinicialização em dispositivos macOS <!-- 1210083  -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). Essa atualização inclui novas configurações de janela de logon, como exibição de uma faixa personalizada, escolher como os usuários se conectam, mostrar ou ocultar as configurações de energia, entre outros.

Para ver essas configurações, acesse [Configurações de recurso de dispositivo macOS](../configuration/macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Configurar o Wi-Fi em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo em execução no modo de quiosque de vários aplicativos <!--3041940  -->
Habilite as configurações em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo durante a execução como um dispositivo dedicado no modo de quiosque de vários aplicativos. Nessa atualização, você pode permitir que os usuários configurem e se conectem a redes Wi-Fi (**Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo, Restrições de dispositivo** para o tipo de perfil > **Dispositivos dedicados** > **Modo de quiosque**: **Vários aplicativos** > **Configuração de Wi-Fi**). 

Para ver todas as configurações que você pode configurar, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](../configuration/device-restrictions-android-for-work.md).

Aplica-se a: Dispositivos dedicados Android Enterprise em execução no modo de quiosque de vários aplicativos


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Configurar o Bluetooth e o emparelhamento em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo em execução no modo de quiosque de vários aplicativos <!-- 3041941  -->
Habilite as configurações em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo durante a execução como um dispositivo dedicado no modo de quiosque de vários aplicativos. Nessa atualização, você pode permitir que os usuários finais habilitem o Bluetooth e emparelhem dispositivos via Bluetooth (**Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo, Restrições de dispositivo** para o tipo de perfil > **Dispositivos dedicados** > **Modo de quiosque**: **Vários aplicativos** > **Configuração do Bluetooth**). 

Para ver todas as configurações que você pode configurar, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](../configuration/device-restrictions-android-for-work.md).

Aplica-se a: Dispositivos dedicados Android Enterprise em execução no modo de quiosque de vários aplicativos

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Criar e usar perfis de configuração de dispositivo do OEMConfig no Intune <!-- 3305883  -->
Nessa atualização, o Intune dá suporte à configuração de dispositivos Android Enterprise com o OEMConfig. Especificamente, você pode criar um perfil de configuração do dispositivo e aplicar as configurações a dispositivos Android Enterprise usando o OEMConfig (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma).

No momento, há suporte para OEMs conforme o OEM. Se um aplicativo OEMConfig desejado não estiver disponível na lista de aplicativos OEMConfig, contate `IntuneOEMConfig@microsoft.com`.

Para saber mais sobre esse recurso, acesse [Usar e gerenciar dispositivos Android Enterprise com o OEMConfig no Microsoft Intune](../configuration/android-oem-configuration-overview.md).

Aplica-se a: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Notificações do Windows Update  <!-- 3316758, 3316782  -->
Adicionamos duas *Configurações da experiência do usuário* às configurações de grupo do Windows Update que você pode gerenciar no console do Intune. Agora você pode:
- Bloquear ou permitir que os usuários [verifiquem se há atualizações do Windows](../protect/windows-update-settings.md).
- Gerenciar o [nível de notificação do Windows Update](../protect/windows-update-settings.md) visto pelos usuários.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Novas configurações de restrição de dispositivo para dispositivos Android Enterprise, Proprietário do Dispositivo <!-- 3574254  -->
Em dispositivos Android Enterprise, você pode criar um perfil de restrição de dispositivo para permitir ou restringir recursos, definir regras de senha, entre outros (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo > Restrições de dispositivo** para o tipo de perfil). 

Essa atualização inclui novas configurações de senha, permite o acesso completo aos aplicativos na Google Play Store para dispositivos totalmente gerenciados, entre outros. Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](../configuration/device-restrictions-android-for-work.md). 

Aplica-se a: Dispositivos Android Enterprise totalmente gerenciados

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671 -->

Esse recurso está atrasado e deve ser lançado posteriormente.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Atualização das alterações de interface do usuário para o navegador Microsoft Edge em dispositivos Windows 10 e posterior <!-- 3775833   -->
Ao criar um perfil de configuração do dispositivo, você pode permitir ou restringir recursos do Microsoft Edge em dispositivos Windows 10 e posterior (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Restrições de dispositivo** para o tipo de perfil > **Navegador Microsoft Edge**). Nessa atualização, as configurações do Microsoft Edge são mais descritivas e mais fáceis de entender. 

Para ver esses recursos, acesse [Configurações de restrição de dispositivo do navegador Microsoft Edge](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

Aplica-se a: Windows 10 e posterior

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Suporte expandido para dispositivos Android Enterprise totalmente gerenciados (versão prévia)  <!--   3903241, 3903244, 3903246   -->
Ainda em uma versão prévia pública, expandimos nosso suporte de dispositivos Android Enterprise totalmente gerenciados ([anunciado pela primeira vez em janeiro de 2019](whats-new.md#week-of-january-14-2019)) para incluir o seguinte: 

- Em dispositivos totalmente gerenciados e dedicados, você pode criar [políticas de conformidade](../protect/compliance-policy-create-android-for-work.md) para incluir regras de senha e requisitos de sistema operacional (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android Enterprise** para a plataforma > **Proprietário do dispositivo** para o tipo de perfil). 

  Em dispositivos dedicados, o dispositivo pode ser mostrado como **Sem conformidade**. O Acesso Condicional não está disponível em dispositivos dedicados. Lembre-se de concluir todas as tarefas ou ações para colocar os dispositivos dedicados em conformidade com as políticas atribuídas.

- [Acesso Condicional](../protect/conditional-access.md) – as políticas de Acesso Condicional que se aplicam ao Android também se aplicam aos dispositivos Android Enterprise totalmente gerenciados. Os usuários agora podem registrar seus dispositivos totalmente gerenciados no Azure Active Directory usando o **aplicativo do Microsoft Intune**. Em seguida, veja e resolva os problemas de conformidade para acessar recursos organizacionais.

- Novo aplicativo de usuário final (aplicativo do Microsoft Intune) – há um novo aplicativo de usuário final para dispositivos Android totalmente gerenciados chamado **Microsoft Intune**. Esse novo aplicativo é leve e moderno e fornece uma funcionalmente semelhante à do aplicativo do Portal da Empresa, mas para dispositivos totalmente gerenciados. Para saber mais, confira [Aplicativo do Microsoft Intune no Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Para configurar dispositivos totalmente gerenciados do Android, acesse **Registro de dispositivo** > **Registro do Android** > **Dispositivos corporativos totalmente gerenciados**. O suporte para dispositivos Android totalmente gerenciados permanece em versão prévia e alguns recursos do Intune podem não estar totalmente funcionais.  

Para saber mais sobre essa versão prévia, confira nosso blog [Microsoft Intune – Versão Prévia 2 para dispositivos Android Enterprise totalmente gerenciados](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Configurar o perfil para ignorar algumas telas durante a execução do Assistente de Configuração <!-- 2276470  -->
Ao criar um perfil de registro do macOS, você poderá configurá-lo para ignorar uma das seguintes telas quando um usuário percorrer o Assistente de Configuração:
- Aparência
- Tom de Exibição
- iCloudStorage Se você editar um perfil ou criar um novo, as telas ignoradas selecionadas precisarão ser sincronizadas com o servidor MDM da Apple.  Os usuários podem emitir uma sincronização manual dos dispositivos, para que não haja atraso na aplicação das alterações de perfil.
Saiba mais em [Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos ou o Apple School Manager](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Nomeação de dispositivo em massa ao registrar dispositivos iOS corporativos<!--3566569  -->
Ao usar um dos métodos de registro corporativo da Apple (DEP/ABM/ASM), você pode definir um formato de nome de dispositivo para nomear automaticamente os dispositivos iOS de entrada. Especifique um formato que inclua o tipo de dispositivo e o número de série no modelo. Para fazer isso, escolha **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > **Selecionar um token** >**Criar perfil** > **Formato de nomeação de dispositivo**. Você pode editar os perfis existentes, mas somente os dispositivos recém-sincronizados terão o nome aplicado.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Atualização da mensagem de tempo limite padrão na Página de Status de Registro <!-- 3959331 -->
Atualizamos a mensagem de tempo limite padrão que os usuários veem quando o ESP (Página de Status de Registro) excede o valor de tempo limite especificado no perfil do ESP. A nova mensagem padrão é o que os usuários veem e ajuda-os a entender as próximas ações a serem executadas com sua implantação do ESP.  

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Desativar dispositivos sem conformidade  <!-- 1827291   -->
Esse recurso foi adiado e está planejado para uma versão futura.


### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Alterações do Intune Data Warehouse V1.0 que refletem novamente a versão beta <!-- 4403765 -->
Quando a V1.0 foi introduzida pela primeira vez em 1808, ela tinha algumas diferenças da API beta. Em 1903, essas alterações serão refletidas novamente para a versão beta da API. Se você tem relatórios importantes que usam a versão beta da API, recomendamos expressamente alternar esses relatórios para a V1.0 a fim de evitar alterações da falha. Para obter mais informações, confira [Log de alterações da API do Intune Data Warehouse](../developer/reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorar o status da linha de base de segurança (versão prévia pública) <!-- 3082047 --> 
Adicionamos uma [exibição por categoria](../protect/security-baselines-monitor.md#per-category-view) ao monitoramento das linhas de base de segurança. (As linhas de base de segurança permanecem em versão prévia). A exibição por categoria exibe cada categoria da linha de base juntamente com o percentual de dispositivos que se enquadram em cada grupo de status dessa categoria. Agora você pode ver quantos dispositivos não correspondem às categorias individuais, estão configurados incorretamente ou não são aplicáveis.

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Marcas de escopo para tokens VPP da Apple <!--2371886  -->
Agora você pode adicionar marcas de escopo a tokens VPP da Apple. Somente os usuários atribuídos com a mesma marca de escopo terão acesso ao token VPP da Apple com essa marca. Os aplicativos e os livros eletrônicos VPP adquiridos com esse token herdam as marcas de escopo. Para obter mais informações sobre marcas de escopo, confira [Usar o RBAC e marcas de escopo](scope-tags.md).







## <a name="week-of-april-1-2019"></a>Semana de 1º de abril de 2019

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Atualização dos conectores de certificado  <!-- ICM 113304612 -->
Lançamos atualizações para o [Intune Certificate Connector e o Conector de Certificado PFX para o Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors). As novas versões corrigem vários problemas conhecidos.  

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!-- 2536024 -->
A página inicial do aplicativo do Portal da Empresa para dispositivos iOS foi reformulada. Com essa alteração, a página inicial seguirá melhor os padrões de interface do usuário do iOS e também fornecerá detectabilidade aprimorada para aplicativos e livros eletrônicos.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Alterações no registro do Portal da Empresa para usuários de dispositivos iOS 12 <!--3448635 -->  
As telas e as etapas de registro do Portal da Empresa para iOS foram atualizadas para se alinharem com as alterações de registro do MDM lançadas no Apple iOS 12.2. O fluxo de trabalho atualizado solicita o seguinte aos usuários:  

* permitir que o Safari abra o site do Portal da Empresa e baixe o perfil de gerenciamento antes de retornar ao aplicativo do Portal da Empresa.  
* abrir o aplicativo de Configurações para instalar o perfil de gerenciamento em seus dispositivos.
* retornar ao aplicativo do Portal da Empresa para concluir o registro.  

Para ver as etapas e as telas de registro atualizadas, confira [Registrar dispositivo iOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>Semana de 25 de março de 2019

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Suporte para o aplicativo de Conformidade do Power BI na folha do Data Warehouse no Microsoft Intune <!-- 4260871 -->
Anteriormente, o link **Baixar arquivo do Power BI** na folha **Intune Data Warehouse** baixava um relatório do Intune Data Warehouse (arquivo .pbix). Esse relatório foi substituído pelo aplicativo de Conformidade do Power BI. O aplicativo de Conformidade do Power BI não exigirá carregamento nem instalação especiais. Ele será aberto diretamente no portal online do Power BI e exibirá dados especificamente para seu locatário do Intune com base em suas credenciais. No Intune, selecione o link **Configurar o Intune Data Warehouse** no lado direito da folha do Intune. Em seguida, clique em **Obter o Aplicativo do Power BI**. Para obter mais informações, confira [Conectar-se ao Data Warehouse com o Power BI](../developer/reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>Semana de 18 de março de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Implantar o Microsoft Visio e o Microsoft Project <!-- 3725386  -->
Agora você pode implantar o Microsoft Visio Pro para Office 365 e o Microsoft Project Online Desktop Client como aplicativos independentes em dispositivos Windows 10 usando o Microsoft Intune, caso você tenha licenças para esses aplicativos. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar** para exibir a folha **Adicionar aplicativo**. Na folha **Adicionar aplicativo**, selecione **Windows 10** como o **Tipo de aplicativo**. Em seguida, selecione **Configurar Pacote de Aplicativos** para selecionar os aplicativos a serem instalados. Para obter mais informações sobre os aplicativos do Office 365 para dispositivos Windows 10, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](../apps/apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Alteração no nome de produto do Microsoft Visio Pro para Office 365 <!-- 3593653  -->
O **Microsoft Visio Pro para Office 365** agora será conhecido como **Microsoft Visio Online Plano 2**.  Para obter mais informações sobre o Microsoft Visio, confira [Visio Online Plano 2](https://products.office.com/visio/visio-online-plan-2). Para obter mais informações sobre os aplicativos do Office 365 para dispositivos Windows 10, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](../apps/apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Configuração do limite de caracteres da APP (Política de Proteção de Aplicativo) do Intune <!-- 3291302  -->
Os administradores do Intune podem especificar uma exceção para a configuração de política **Restringir recortar, copiar e colar com outros aplicativos** da APP do Intune.  Como administrador, você pode especificar o número de caracteres que podem ser recortados ou copiados de um aplicativo gerenciado. Essa configuração permitirá o compartilhamento do número especificado de caracteres com qualquer aplicativo, independentemente da configuração "Restringir recortar, copiar e colar com outros aplicativos". Observe que a versão do aplicativo do Portal da Empresa do Intune para Android exige a versão 5.0.4364.0 ou posterior. Para obter mais informações, confira [Proteção de dados do iOS](../apps/app-protection-policy-settings-ios.md#data-protection), [Proteção de dados do Android](../apps/app-protection-policy-settings-android.md#data-protection) e [Examinar os logs de proteção de aplicativo cliente](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>XML do ODT (Ferramenta de Implantação do Office) para implantação do Office ProPlus <!-- 3192477   -->
Você poderá fornecer o XML do ODT (Ferramenta de Implantação do Office) ao criar uma instância do Office Pro Plus no console de administração do Intune. Isso permitirá uma maior capacidade de personalização, caso as opções existentes de interface do usuário do Intune não atendam às suas necessidades. Para obter mais informações, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](../apps/apps-add-office365.md) e [Opções de configuração para a Ferramenta de Implantação do Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente <!-- 1429026  -->
No aplicativo do Portal da Empresa do Windows, os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente com base na cor dominante do ícone (caso seja possível detectá-la). Quando aplicável, essa tela de fundo substituirá a borda cinza que era visível anteriormente em blocos de aplicativo. Os usuários verão essa alteração em versões do Portal da Empresa mais recentes que 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Instalar os aplicativos disponíveis usando o aplicativo do Portal da Empresa após o registro em massa do Windows <!-- 2751523   -->
Os dispositivos Windows registrados no Intune com o [registro em massa do Windows](../enrollment/windows-bulk-enroll.md) (pacotes de provisionamento) poderão usar o aplicativo do Portal da Empresa para instalar os aplicativos disponíveis. Para obter mais informações sobre o aplicativo do Portal da Empresa, confira [Adicionar manualmente o Portal da Empresa do Windows 10](../apps/store-apps-company-portal-app.md) e [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](../apps/company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>O aplicativo Microsoft Teams pode ser selecionado como parte do pacote de aplicativos do Office <!-- 3828932  -->
O aplicativo Microsoft Teams pode ser incluído ou excluído como parte da instalação do pacote de aplicativos do Office Pro Plus. Esse recurso funciona no Office Pro Plus número de build 16.0.11328.20116 e posterior. O usuário precisa sair do dispositivo e, em seguida, entrar nele para concluir a instalação. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Selecione um dos tipos de aplicativo **Pacote do Office 365** e, em seguida, selecione **Configurar Pacote de Aplicativos**.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Iniciar automaticamente um aplicativo quando vários aplicativos estão em execução no modo de quiosque em dispositivos Windows 10 e posterior <!-- 2351390 -->

Em dispositivos Windows 10 e posterior, você pode executar um dispositivo no modo de quiosque e executar muitos aplicativos. Nessa atualização, há uma configuração de **Inicialização Automática** (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Quiosque** para o tipo de perfil > **Quiosque de vários aplicativos**). Use essa configuração para iniciar automaticamente um aplicativo quando o usuário entrar no dispositivo.

Para ver uma lista e uma descrição de todas as configurações de quiosque, confira [Configurações de dispositivos Windows 10 e posterior para execução como um quiosque no Intune](../configuration/kiosk-settings-windows.md).

Aplica-se a: Windows 10 e posterior

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Os logs operacionais também mostram detalhes sobre os dispositivos sem conformidade <!-- 4063755  -->
Durante o roteamento de logs do Intune para recursos do Azure Monitor, você também pode rotear os logs operacionais. Nessa atualização, os logs operacionais também fornecem informações sobre os dispositivos sem conformidade. 

Para obter mais informações sobre esse recurso, confira [Enviar dados de log para o armazenamento, os hubs de eventos ou a análise de logs no Intune](../review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Rotear logs para o Azure Monitor em mais cargas de trabalho do Intune <!-- 3804627 -->
No Intune, você pode rotear logs de auditoria e operacionais para os hubs de eventos, o armazenamento e a análise de logs no Azure Monitor (**Intune** > **Monitoramento** > **Configurações de diagnóstico**). Nessa atualização, você pode rotear esses logs em mais cargas de trabalho do Intune, incluindo conformidade, configurações, aplicativos cliente, entre outros. 

Para saber mais sobre os logs de roteamento para o Azure Monitor, confira [Enviar dados de log para o armazenamento, os hubs de eventos ou a análise de logs](../review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Criar e usar extensões de mobilidade em dispositivos Android Zebra no Intune <!-- 3305880   -->
Nessa atualização, o Intune dá suporte à configuração de dispositivos Android Zebra. Especificamente, você pode criar um perfil de configuração do dispositivo e aplicar as configurações a dispositivos Android Zebra usando perfis MX (extensões de mobilidade) gerados pelo StageNow (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android** para a plataforma > **Perfil MX (somente Zebra)** para o tipo de perfil).

Para obter mais informações sobre esse recurso, confira [Usar e gerenciar dispositivos Zebra com extensões de mobilidade no Intune](../configuration/android-zebra-mx-overview.md).

Aplica-se a: Android

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Relatório de criptografia para dispositivos Windows 10 (em versão prévia pública)<!-- 2351538 -->  
Use o novo [Relatório de criptografia (versão prévia)](../protect/encryption-monitor.md) para exibir detalhes sobre o status da criptografia de seus dispositivos Windows 10. Os detalhes disponíveis incluem uma versão TPM de dispositivos, preparação e status de criptografia, relatório de erros, entre outros.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Acessar as chaves de recuperação do BitLocker no portal do Intune (em versão prévia pública) <!-- 2351547   -->  
Agora você pode usar o Intune para [exibir detalhes](../protect/encryption-monitor.md) sobre a ID de Chave e as chaves de recuperação do BitLocker no Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Suporte do Microsoft Edge para cenários do Intune em dispositivos iOS e Android <!-- 3411007 -->
O Microsoft Edge dará suporte a todos os mesmos cenários de gerenciamento do Intune Managed Browser com a adição de melhorias na experiência do usuário final. Os recursos empresariais do Microsoft Edge que são habilitados por políticas do Intune incluem identidade dupla, integração de política de proteção de aplicativo, integração de proxy de aplicativo do Azure e Favoritos e atalhos de página inicial gerenciados. Para obter mais informações, confira o [suporte do Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>O Exchange Online e o Intune Connector preterem o suporte para dispositivos somente do EAS <!--3105122  -->
O console do Intune não dá mais suporte à exibição e ao gerenciamento de dispositivos somente do EAS conectados ao Exchange Online com o Intune Connector. Em vez disso, você tem as seguintes opções:
- Registrar dispositivos no Gerenciamento de Dispositivo Móvel (MDM)
- Usar políticas de Proteção de Aplicativo do Intune para gerenciar seus dispositivos
- Usar controles do Exchange, conforme descrito em [Clientes e celulares no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Pesquisar a página Todos os dispositivos em busca de um dispositivo exato usando o [nome] <!--4254930 -->
Agora você pode pesquisar um nome de dispositivo exato. Acesse **Intune** > **Dispositivos** > **Todos os dispositivos** > na caixa de pesquisa e coloque o nome do dispositivo entre {} para pesquisar uma correspondência exata. Por exemplo, **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Suporte para conectores adicionais na página Status do Locatário <!-- 3617202  -->
A [página Status do Locatário](../tenant-status.md) agora exibe informações de status para conectores adicionais, incluindo *Windows Defender ATP* (Proteção Avançada contra Ameaças) e outros conectores de Defesa contra Ameaças Móveis.

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Como permitir acesso somente leitura do Intune a apenas algumas funções do Azure Active Directory <!-- 3637917  -->
O acesso somente leitura do Intune foi permitido às funções do Azure AD a seguir. As permissões concedidas com funções do Azure AD substituem as permissões concedidas com o RBAC (controle de acesso baseado em função) do Intune.

Acesso somente leitura aos dados de auditoria do Intune:

- Administrador de conformidade
- Administrador de dados de conformidade

Acesso somente leitura a todos os dados do Intune:

- Administrador de Segurança
- Operador de segurança
- Leitor de segurança

Para obter mais informações, confira [Controle de acesso baseado em função](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Marcas de escopo para perfis de provisionamento de aplicativo do iOS <!--2934430   -->
Você pode adicionar uma marca de escopo a um perfil de provisionamento de aplicativo do iOS, de modo que somente as pessoas com funções que também receberam essa marca de escopo tenham acesso ao perfil de provisionamento de aplicativo do iOS. Para obter mais informações, confira [Usar o RBAC e marcas de escopo](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Marcas de escopo para políticas de configuração de aplicativos <!--2371891   -->
Você pode adicionar uma marca de escopo a uma política de configuração de aplicativos, de modo que somente as pessoas com funções que também receberam essa marca de escopo tenham acesso à política de configuração de aplicativos. A política de configuração de aplicativos só pode ser direcionada ou associada a aplicativos que receberam a mesma marca de escopo. Para obter mais informações, confira [Usar o RBAC e marcas de escopo](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Suporte do Microsoft Edge para cenários do Intune em dispositivos iOS e Android <!-- 3411007 -->
O Microsoft Edge dará suporte a todos os mesmos cenários de gerenciamento do Intune Managed Browser com a adição de melhorias na experiência do usuário final. Os recursos empresariais do Microsoft Edge que são habilitados por políticas do Intune incluem identidade dupla, integração de política de proteção de aplicativo, integração de proxy de aplicativo do Azure e Favoritos e atalhos de página inicial gerenciados. Para obter mais informações, confira o [suporte do Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>Semana de 25 de fevereiro de 2019

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="intune-powershell-module----951068----"></a>Módulo do PowerShell do Intune <!-- 951068  -->
O módulo do PowerShell do Intune, que fornece suporte para a API do Intune por meio do Microsoft Graph, agora está disponível na [Galeria do Microsoft PowerShell](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Detalhes sobre como usar este módulo](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Exemplos de cenários de uso deste módulo](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Suporte aprimorado para a Otimização de Entrega  <!--3183757  -->
Expandimos o suporte no Intune para configurar a Otimização de Entrega. Agora você pode configurar uma lista expandida de [configurações de Otimização de Entrega](../configuration/delivery-optimization-settings.md) e direcioná-la a seus dispositivos diretamente no console do Intune.


## <a name="week-of-february-18-2019"></a>Semana de 18 de fevereiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>O Intune aproveitará as APIs do Google Play Protect em dispositivos Android <!-- 2577355   -->
Alguns administradores de TI se deparam com um cenário de BYOD, em que os usuários finais podem acabar efetuando rooting ou desbloqueio por jailbreak dos respectivos dispositivos móveis. Esse comportamento, embora às vezes não mal-intencionado, resulta em um desvio de muitas políticas do Intune que são definidas para proteger os dados da organização em dispositivos de usuário final. Assim, o Intune fornece detecção de root e jailbreak para dispositivos registrados e não registrados. Com esta versão, o Intune agora aproveitará as APIs do Google Play Protect para adicionar a nossas verificações de detecção de root existentes para dispositivos não registrados. Embora o Google não compartilhe as verificações de detecção de root que ocorrem na íntegra, esperamos que essas APIs detectem os usuários que realizaram rooting de seus dispositivos por qualquer motivo, desde personalização de dispositivo até possibilidade de obtenção das atualizações mais recentes do sistema operacional em dispositivos mais antigos. Esses usuários podem então ser impedidos de acessar dados corporativos e suas contas corporativas podem ser apagadas de seus aplicativos habilitados para política. Para o valor adicional, o administrador de TI agora tem várias atualizações de geração de relatórios na folha da Proteção de Aplicativo do Intune – o relatório "Usuários sinalizados" mostrará quais usuários são detectados por meio do verificação de API do SafetyNet da Google Play Protect, o relatório "Aplicativos potencialmente prejudiciais" mostrará quais aplicativos são detectados por meio da verificação de API da Verificação de Aplicativos do Google. Este recurso está disponível no Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informações do aplicativo Win32 disponíveis na folha Solução de Problemas <!-- 2617342   -->
Agora você pode coletar arquivos de log de falha para uma instalação de aplicativo Win32 na folha **Solução de Problemas** do aplicativo do Intune. Para obter mais informações sobre solução de problemas de instalação do aplicativo, confira [Solução de problemas de instalação do aplicativo](./../apps/troubleshoot-app-install.md) e [Solução de problemas de aplicativos Win32](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Detalhes do status do aplicativo para aplicativos iOS <!-- 3761235   -->
Há novas mensagens de erro de instalação de aplicativo relacionadas ao seguinte:
- Falha em aplicativos VPP durante a instalação no iPad compartilhado
- Falha quando o repositório do aplicativo é desabilitado
- Falha ao localizar a licença do VPP para o aplicativo
- Falha ao instalar aplicativos do sistema com o provedor de MDM
- Falha ao instalar aplicativos quando o dispositivo está no modo perdido ou modo de quiosque
- Falha ao instalar o aplicativo quando o usuário não está conectado à App Store

No Intune, selecione **Aplicativos cliente** > **Aplicativos** > "Nome do aplicativo" > **Status de instalação do dispositivo**. Novas mensagens de erro estarão disponíveis na coluna **Detalhes do status**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Nova tela Categorias de aplicativo no aplicativo do Portal da Empresa para Windows 10<!-- 3834780  -->
Uma nova tela chamada **Categorias de aplicativo** foi adicionada para melhorar a experiência de navegação e de seleção do aplicativo no Portal da Empresa para Windows 10. Agora os usuários verão os aplicativos classificados em categorias como **Em destaque**, **Educação** e **Produtividade**. Essa alteração é exibida nas versões do Portal da Empresa 10.3.3451.0 e posteriores. Para exibir a nova tela, confira [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md). Para obter mais informações sobre os aplicativos no Portal da Empresa, confira [Instalar e compartilhar aplicativos em seu dispositivo](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Aplicativo de Conformidade do Power BI <!-- 1455231 doc-work-item -->
Acesse o Intune Data Warehouse no Power BI Online usando o aplicativo [Conformidade do Intune (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Com esse aplicativo do Power BI, agora você pode acessar e compartilhar relatórios pré-criados sem nenhuma configuração e sem sair do navegador da Web. Para obter mais informações, confira [Log de alterações – aplicativo de Conformidade do Power BI](../developer/reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>Os scripts do PowerShell podem ser executados em um host de 64 bits em dispositivos de 64 bits <!-- 1862675   -->
Quando você adiciona um script do PowerShell a um perfil de configuração do dispositivo, o script é executado sempre em 32 bits, mesmo em sistemas operacionais de 64 bits. Com essa atualização, um administrador pode executar o script em um host do PowerShell de 64 bits em dispositivos de 64 bits (**Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar** > **Configurar** > **Executar o script no host do PowerShell de 64 bits**).

Para obter mais detalhes sobre como usar o PowerShell, veja [scripts do PowerShell no Intune](../apps/intune-management-extension.md).

Aplica-se a: Windows 10 e posterior

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>Os usuários do macOS deverão atualizar suas senhas <!-- 1873216 -->
O Intune impõe a configuração **ChangeAtNextAuth** em dispositivos macOS. Essa configuração afeta os usuários finais e os dispositivos que têm políticas de senha de conformidade ou perfis de senha de restrição de dispositivo. Os usuários finais deverão atualizar suas senhas uma vez. Esse prompt ocorre sempre que um usuário executa pela primeira vez uma tarefa que exige autenticação, como a entrada no dispositivo. Os usuários também podem precisar atualizar suas senhas ao realizar tarefas que exigem privilégios administrativos, como solicitação de acesso ao conjunto de chaves. 

As alterações na política de senha novas ou existentes pelo administrador solicitam que os usuários finais atualizem suas senhas novamente.

Aplica-se a:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521------"></a>Atribuir certificados SCEP a um dispositivo macOS sem usuário    <!-- 2340521    -->
Você pode atribuir certificados do protocolo SCEP usando atributos do dispositivo a dispositivos macOS, incluindo dispositivos sem afinidade de usuário, e associar o perfil de certificado a perfis de VPN ou Wi-Fi. Isso expande o suporte que já temos para [atribuir certificados SCEP a dispositivos com e sem afinidade de usuário](../protect/certificates-profile-scep.md) que executam o Windows, o iOS e o Android.  Essa atualização adiciona a opção de selecionar um tipo de Certificado do *Dispositivo* quando você configura um perfil de certificado SCEP para o macOS.

Aplica-se a: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Atualização da interface do usuário de Acesso Condicional do Intune   <!-- 2432313   -->
Fizemos melhorias na interface do usuário para Acesso Condicional no console do Intune. Como por exemplo:
- Substituição da folha *Acesso Condicional* do Intune pela folha do Azure Active Directory. Isso garante que você terá acesso à variedade completa de definições e configurações de [Acesso Condicional](../protect/conditional-access.md) (que continua sendo uma tecnologia do Azure AD) no console do Intune. 
- Renomeamos a folha *Acesso local* para *Acesso ao Exchange* e relocamos a configuração *Conector de serviço do Exchange* para essa folha renomeada.  Essa alteração consolida o local em que você [configura e monitora os detalhes relacionados ao Exchange Online e localmente](../protect/exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Os aplicativos do navegador de quiosque e do navegador Microsoft Edge podem ser executados em dispositivos Windows 10 no modo de quiosque <!-- 2935135   -->
Você pode usar dispositivos Windows 10 no modo de quiosque para executar um ou muitos aplicativos. Esta atualização inclui várias alterações para usar aplicativos de navegador no modo de quiosque, incluindo:

- Adicionar o navegador Microsoft Edge ou o navegador de quiosque para serem executados como aplicativos no dispositivo de quiosque (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **Windows 10 e posterior** para a plataforma > **Quiosque** para tipo de perfil).
- Novos recursos e novas configurações estão disponíveis para permissão ou restrição (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **Windows 10 e posterior** para a plataforma > **Restrições de dispositivo** para o tipo de perfil), incluindo:

- Navegador Microsoft Edge:
  - Usar o modo de quiosque do Microsoft Edge
  - Atualizar o navegador após tempo ocioso

- Favoritos e pesquisa:
  - Permitir alterações no mecanismo de pesquisa

Para obter uma lista dessas configurações, confira:

- [Configurações de dispositivos com Windows 10 (e posterior) para execução como um quiosque](../configuration/kiosk-settings-windows.md)
- [Restrições de dispositivo do navegador Microsoft Edge](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Favoritos e restrições de dispositivo de pesquisa](../configuration/device-restrictions-windows-10.md##favorites-and-search)

Aplica-se a: Windows 10 e posterior

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Novas configurações de restrição de dispositivo para dispositivos iOS e macOS <!-- 3448774   -->
Você pode restringir algumas configurações e recursos em dispositivos que executam o iOS e macOS (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **iOS** ou **macOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil). Essa atualização adiciona mais recursos e configurações que você pode controlar, incluindo o tempo da tela de configuração, a alteração das configurações do eSIM e planos do celular, entre outros, em dispositivos iOS. Além disso, o atraso da visibilidade do usuário das atualizações de software e o bloqueio do cache de conteúdo em dispositivos macOS. 

Para ver os recursos e as configurações que você pode restringir, confira:

- [Configurações de restrição de dispositivo iOS](../configuration/device-restrictions-ios.md)
- [Configurações de restrição de dispositivo macOS](../configuration/device-restrictions-macos.md)

Aplica-se a:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Os dispositivos de "quiosque" agora são chamados "dispositivos Dedicados" em dispositivos Android Enterprise <!-- 3598402   -->
Para alinhamento com a terminologia do Android, o **quiosque** foi alterado para **dispositivos dedicados** em dispositivos Android Enterprise (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise para a plataforma > **Somente Proprietário do Dispositivo** > **Restrições de dispositivo** > **Dispositivos dedicados**).

Para ver as configurações disponíveis, acesse [Configurações do dispositivo para permitir ou restringir recursos](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Aplica-se a:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>As configurações do iOS Safari e Atrasando a visibilidade das atualizações de software pelo usuário estão sendo movidas para a interface do usuário do Intune <!-- 3640850, 3803313   -->
Para dispositivos iOS, você pode definir as configurações do Safari e configurar as Atualizações de Software. Nesta atualização, essas configurações estão sendo movidas para diferentes partes da interface do usuário do Intune:

- As configurações do Safari foram movidas da opção **Safari** (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil) para **[Aplicativos Internos](../configuration/device-restrictions-ios.md#built-in-apps)** .
- A configuração **Atrasando a visibilidade das atualizações de software pelo usuário para dispositivos iOS supervisionados** (**Atualizações de software** > **Atualizar as políticas para iOS**) está sendo movida para **Restrições de dispositivo** >  **[Geral](../configuration/device-restrictions-ios.md#general)** .  Para obter detalhes sobre o impacto das políticas existentes, confira [Atualizações de software do iOS](../protect/software-updates-ios.md#configure-the-policy). 

Para obter uma lista das configurações, confira:

- [Restrições de dispositivo iOS](../configuration/device-restrictions-ios.md) 
- [Atualizações de software do iOS](../protect/software-updates-ios.md)

Esse recurso aplica-se a: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>A configuração Habilitando restrições nas configurações do dispositivo é renomeada para Tempo de Tela em dispositivos iOS <!-- 3699164   -->
Você pode configurar a **Habilitar restrições nas configurações do dispositivo** em dispositivos iOS supervisionados (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil > **Geral**). Nesta atualização, essa configuração é renomeada para **Tempo de Tela (somente supervisionado)** . 

O comportamento é o mesmo. Especificamente: 

- iOS 11.4.1 e versões anteriores: **Bloquear** impede que os usuários finais definam suas próprias restrições nas configurações do dispositivo. 
- iOS 12.0 e versões posteriores: **Bloquear** impede que os usuários finais configurem seu próprio **Tempo de Tela** nas configurações do dispositivo, incluindo restrições de privacidade e de conteúdo. Dispositivos atualizados para o iOS 12.0 não exibirão mais a guia de restrições nas configurações do dispositivo. Essas configurações estão no **Tempo de Tela**. 

Para obter uma lista das configurações, confira [Restrições de dispositivo iOS](../configuration/device-restrictions-ios.md#general).

Aplica-se a: 
- iOS


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Renomear um dispositivo Windows registrado <!-- 1911112  -->
Agora você pode renomear um dispositivo Windows 10 registrado (RS4 ou posterior). Para fazê-lo, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Renomear dispositivo**. No momento, esse recurso não dá suporte à renomeação de dispositivos Windows do Azure AD híbrido.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Atribuir automaticamente marcas de escopo aos recursos criados por um administrador com esse escopo <!-- 3173823  -->
Quando um administrador cria um recurso, todas as marcas de escopo atribuídas ao administrador serão atribuídas automaticamente a esse novo recurso.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>O relatório de registro com falha é movido para a folha Registro de Dispositivo <!-- 3560202  -->
O relatório **Registros com falha** foi movido para a seção **Monitorar** da folha **Registro de dispositivo**. Duas novas colunas (Método de Registro e Versão do Sistema Operacional) foram adicionadas.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Relatório de abandono do Portal da Empresa renomeado para Registros de usuário incompletos <!--3815076 eemiss -->
O relatório **Abandono do Portal da Empresa** foi renomeado para **Registros de usuário incompletos**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Semana de 4 de fevereiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Modo Escuro do Portal da Empresa do Intune macOS <!-- 3300524  -->
O Portal da Empresa do Intune no macOS agora dá suporte ao Modo Escuro para macOS. Quando você habilitar o Modo Escuro em um dispositivo macOS 10.14 ou superior, o Portal da Empresa ajustará sua aparência de acordo com as cores para refletir o modo.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>Semana de 21 de janeiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Notificações do sistema para aplicativos Win32 <!-- 3136566   -->
Você pode suprimir a exibição de notificações do sistema ao usuário final de acordo com a atribuição de aplicativo. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > selecione o aplicativo > **Atribuições** > **Incluir Grupos**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Atualização da interface do usuário de políticas de proteção de aplicativo do Intune <!-- 3251427  -->
Alteramos os rótulos das configurações e dos botões da proteção de aplicativo do Intune, a fim de facilitar a compreensão. Entre as alterações estão:  
- Mudamos os controles de **sim** / **não** para, principalmente, **bloquear** / **permitir** e **desabilitar** / **habilitar**. Os rótulos também foram atualizados.  
- As configurações foram reformatadas, portanto, a configuração e seu rótulo estão lado a lado no controle, fornecendo uma navegação melhor.   

As configurações padrão e o número de configurações permanecem iguais, mas essa alteração permite que o usuário entenda, navegue e utilize as configurações mais facilmente para aplicar as políticas de proteção de aplicativo específicas. Para saber mais, confira [Configurações do iOS](../apps/app-protection-policy-settings-ios.md) e [Configurações do Android](../apps/app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Configurações adicionais para o Outlook <!-- 3301182  -->
Agora você pode definir as seguintes configurações adicionais para o Outlook para iOS e Android usando o Intune:

- Permitir o uso somente de contas corporativas ou de estudante no Outlook no iOS e no Android
- Implantar a autenticação moderna para o Office 365 e a autenticação moderna híbrida para contas locais
- Usar `SAMAccountName` para o campo de nome de usuário no perfil de email quando a autenticação Básica for selecionada
- Permitir que os contatos sejam salvos
- Configurar MailTips de destinatários externos
- Configurar **Caixa de Entrada Destaques**
- Exigir biometria para acessar o Outlook para iOS
- Bloquear imagens externas

> [!NOTE]
> Se estiver usando políticas de Proteção de Aplicativo do Intune para gerenciar o acesso de identidades corporativas, considere a possibilidade de não habilitar a opção **Exigir biometria**. Para saber mais, confira **Exigir credenciais corporativas para acesso** para [Configurações de acesso do iOS](../apps/app-protection-policy-settings-ios.md#access-requirements) e [Configurações de acesso do Android](../apps/app-protection-policy-settings-android.md#access-requirements).

Para obter mais informações, confira [Definições de configuração do Microsoft Outlook](../apps/app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Excluir aplicativos Android Enterprise <!-- 1352553 -->
Você pode excluir aplicativos do Google Play Gerenciado no Microsoft Intune. Para excluir um aplicativo do Google Play Gerenciado, abra o Microsoft Intune no portal do Azure e selecione **Aplicativos do cliente** > **Aplicativos**. Na lista de aplicativos, selecione as reticências (...) à direita do aplicativo do Google Play Gerenciado e, em seguida, selecione **Excluir** na lista exibida. Quando você exclui um aplicativo do Google Play gerenciado na lista de aplicativos, o aplicativo do Google Play gerenciado torna-se para aprovação automaticamente.

#### <a name="managed-google-play-app-type----1352580---"></a>Tipo de aplicativo do Google Play Gerenciado <!-- 1352580 -->
O tipo de aplicativo **Google Play gerenciado** permitirá que você adicione especificamente [aplicativos do Google Play gerenciado](https://play.google.com/work/search?q=microsoft&c=apps) ao Intune. Como administrador do Intune, agora você pode navegar, pesquisar, aprovar, sincronizar e atribuir aplicativos aprovados do Google Play Gerenciado no Intune.  Não é mais necessário navegar até o console do Google Play Gerenciado separadamente, nem autenticar novamente.  No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo**, selecione **Google Play Gerenciado** como o tipo de aplicativo.

### <a name="default-android-pin-keyboard----3802457---"></a>Teclado padrão de PIN do Android <!-- 3802457 -->
Para usuários finais que definiram um PIN de APP (Política de Proteção de Aplicativo) do Intune em seus dispositivos Android com o tipo PIN "Numérico", agora será exibido o teclado Android padrão em vez da interface do usuário de teclado Android fixa que foi criada anteriormente. Essa alteração foi feita para ser consistente ao usar teclados padrão no Android e iOS, para os tipos PIN "Numérico" e/ou "Senha". Para obter mais informações sobre as configurações de acesso do usuário final no Android, tais como o PIN do aplicativo, veja [requisitos de acesso do Android](../apps/app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Usar as configurações recomendadas pela Microsoft com linhas de base de segurança (versão prévia pública) <!-- 2055484   -->

O Intune integra-se a outros serviços que têm foco na segurança, incluindo o Windows Defender ATP e o Office 365 ATP. Os clientes estão solicitando uma estratégia comum e um conjunto coeso de fluxos de trabalho de segurança de ponta a ponta entre os serviços do Microsoft 365. Nossa meta é alinhar estratégias para criar soluções que façam a ponte entre operações de segurança e tarefas comuns do administrador. No Intune, nosso objetivo é atingir essa meta publicando um conjunto de "Linhas de base de segurança" recomendadas pela Microsoft (**Intune** > **Linhas de base de segurança**).  Um administrador pode criar políticas de segurança diretamente dessas linhas de base e, depois, implantá-las para seus usuários. Também é possível personalizar as recomendações de melhores práticas para atender às necessidades da sua organização. O Intune garante que os dispositivos estejam em conformidade com essas linhas de base e notifica os administradores de usuários ou dispositivos que não estão em conformidade.

Esse recurso está em versão prévia pública, portanto, todos os perfis criados agora não serão movidos para modelos de linhas de base de segurança que estejam em GA (disponibilidade geral). Você não deve planejar usar esses modelos de versão prévia em seu ambiente de produção.

Para saber mais sobre linhas de base de segurança, veja [Criar uma linha de base de segurança do Windows 10 no Intune](../protect/security-baselines-monitor.md).

Esse recurso aplica-se a: Windows 10 e posterior

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Aqueles que não são administradores podem habilitar o BitLocker em dispositivos Windows 10 ingressados no Azure AD<!-- 2147379   -->
Ao habilitar as configurações do BitLocker em dispositivos com Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Endpoint Protection** para o tipo de perfil > **Criptografia do Windows**), você adiciona as configurações do BitLocker. 

Esta atualização inclui uma nova configuração de BitLocker para permitir que os usuários padrão (não administradores) habilitem a criptografia. 

Para ver essas configurações, acesse [Configurações do Endpoint Protection para Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Verificar a conformidade do Configuration Manager <!-- 2192052  eepublished  -->
Essa atualização inclui uma nova configuração de conformidade do System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10 e posterior** > **Conformidade do Configuration Manager**). O Configuration Manager envia sinais para a conformidade do Intune. Com essa configuração, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

[Conformidade do Configuration Manager](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) descreve essa configuração.

Aplica-se a: Windows 10 e posterior

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Personalizar o papel de parede em dispositivos iOS supervisionados usando um perfil de configuração do dispositivo <!-- 2809324   -->
Ao criar um perfil de configuração do dispositivo para dispositivos iOS, você poderá personalizar alguns recursos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações de **Papel de parede** que permitem a um administrador usar uma imagem .png, .jpg ou .jpeg na tela inicial ou na tela de bloqueio. Essas configurações de papel de parede se aplicam somente a dispositivos supervisionados. 

Para obter uma lista com essas configurações, veja [Configurações de recurso em dispositivo iOS](../configuration/ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>O quiosque do Windows 10 está em disponibilidade geral <!-- 3594661  -->
Nesta atualização, o recurso de Quiosque em dispositivos com Windows 10 e posteriores já está disponível (GA). Para ver todas as configurações que você pode adicionar e definir, consulte [Configurações de quiosque para Windows 10 (e posterior)](../configuration/kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>O Compartilhamento de Contatos via Bluetooth foi removido de Restrições de Dispositivo > Proprietário do Dispositivo Android Enterprise <!-- 3598396   -->
Quando você cria um perfil de restrições de dispositivo para dispositivos Android Enterprise, há uma configuração **Compartilhamento de Contatos via Bluetooth**. Nesta atualização, a configuração **Compartilhamento de Contatos via Bluetooth** foi removida (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Restrições de Dispositivo > Proprietário do dispositivo** para o tipo de perfil > **Geral**). 

Não há suporte para a configuração **Compartilhamento de Contatos via Bluetooth** no gerenciamento do Proprietário do Dispositivo Android Enterprise. Portanto, quando essa configuração for removida, ela não afetará nenhum dispositivo ou locatário, mesmo se ela estiver habilitada e configurada no ambiente.

Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](../configuration/device-restrictions-android-for-work.md).

Aplica-se a: Proprietário do Dispositivo Android Enterprise

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Suporte de apagamento seletivo para dispositivos WIP sem registro <!-- 1434452 -->
O WIP-WE (Proteção de Informações do Windows sem registro) permite que os clientes protejam seus dados corporativos em dispositivos Windows 10 sem a necessidade de registro MDM completo. Depois que os documentos forem protegidos com uma política de WIP-WE, os dados protegidos poderão ser apagados seletivamente por um administrador do Intune. Se o usuário e o dispositivo forem selecionados e uma solicitação de apagamento for enviada, todos os dados protegidos por meio da política de WIP-WE ficarão inutilizáveis. No Intune no portal do Azure, selecione **Aplicativo móvel** > **Apagamento seletivo do aplicativo**.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Novos logs operacionais e capacidade de enviar logs para serviços do Azure Monitor <!-- 3762211  -->
O Intune tem log de auditoria interno que rastreia os eventos à medida que as alterações são feitas. Esta atualização inclui novos recursos de registro em log, incluindo: 
- Logs operacionais (versão prévia) que mostram detalhes sobre os usuários e dispositivos registrados, incluindo tentativas com falha e sucesso.
- Os logs de auditoria e operacional podem ser enviados ao Azure Monitor, incluindo contas de armazenamento, hubs de eventos e log analytics. Esses serviços permitem que você armazene, use análises como Splunk e QRadar e obtenha visualizações de seus dados de log.

[Enviar dados de log para o armazenamento, hubs de eventos ou log analytics no Intune](../review-logs-using-azure-monitor.md) fornece mais informações sobre esse recurso.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Ignorar mais telas do Assistente de Configuração em um dispositivo iOS DEP <!-- 2687509  -->
Além das telas que você pode ignorar no momento, você poderá definir dispositivos iOS DEP para ignorar as seguintes telas no Assistente de Configuração quando um usuário registrar o dispositivo: Exiba tom, Privacidade, Migração do Android, botão Página Inicial, iMessage e FaceTime, Integração, Migração de Inspeção, Aparência, Hora na Tela, Atualização de Software, Configuração do SIM.
Para escolher quais telas ignorar, acesse **Registro do dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Propriedades** > **Personalização do Assistente de Configuração** > escolha **Ocultar** para as telas que você deseja ignorar > **OK**.
Se você cria um perfil novo ou edita um perfil, as telas ignoradas selecionadas precisam ser sincronizadas com o servidor MDM da Apple. Os usuários podem emitir uma sincronização manual dos dispositivos, para que não haja atraso na aplicação das alterações de perfil.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Implantação do aplicativo APP-WE do Android Enterprise <!-- 1171203 -->
Para dispositivos Android em um cenário de implantação APP-WE (Política de proteção de aplicativo sem registro), é possível usar o Google Play gerenciado para implantar aplicativos da loja e aplicativos de LOB para os usuários. Especificamente, é possível fornecer aos usuários finais uma experiência de catálogo e instalação de aplicativos que não exige mais que eles afrouxem a postura de segurança de seus dispositivos ao permitir instalações de fontes desconhecidas. Além disso, esse cenário de implantação fornece uma experiência aprimorada ao usuário final.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>Semana de 14 de janeiro de 2019

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Versão prévia do suporte para dispositivos Android corporativos totalmente gerenciados <!-- 1574342  -->
O Intune agora dá suporte total a dispositivos Android totalmente gerenciados, um cenário de "proprietário do dispositivo" de propriedade corporativa no qual os dispositivos são gerenciados de modo estrito pelo departamento de TI e são afiliados a usuários individuais. Isso permite aos administradores gerenciar todo o dispositivo, impor uma extensa variedade de controles de política não disponíveis aos perfis de trabalho e restringe a instalação de aplicativos por parte dos usuários apenas à Google Play gerenciada. Para obter mais informações, confira [Configurar o registro de dispositivos Android totalmente gerenciados no Intune](../enrollment/android-fully-managed-enroll.md) e [Registrar seus dispositivos dedicados ou dispositivos totalmente gerenciados](../enrollment/android-dedicated-devices-fully-managed-enroll.md).  Observe que esse recurso está em versão prévia. Algumas funcionalidades do Intune, como certificados, conformidade e Acesso Condicional, não estão atualmente disponíveis em dispositivos de usuário Android totalmente gerenciados.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>Semana de 7 de janeiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-app-pin----2298397---"></a>PIN do aplicativo do Intune <!-- 2298397 -->
Como administrador de TI, você pode configurar o número de dias que um usuário final pode aguardar até que o PIN do aplicativo Intune precise ser alterado. A nova configuração é *Redefinição de PIN após o número de dias* e será disponibilizada no portal do Azure pela seleção de **Intune** > **Aplicativos cliente** > **Políticas de proteção do aplicativo** > **Criar Política** > **Configurações** > **Requisitos de acesso**. Disponível para dispositivos [iOS](../apps/app-protection-policy-settings-ios.md) e [Android](../apps/app-protection-policy-settings-android.md), esse recurso dá suporte a um valor inteiro positivo.


#### <a name="intune-device-reporting-fields----2748738---"></a>Campos de relatório de dispositivo do Intune <!-- 2748738 -->
O Intune fornece campos adicionais de relatório do dispositivo, incluindo ID de Registro do Aplicativo, fabricante do Android, modelo e versão do patch de segurança, bem como modelo do iOS. No Intune, esses campos estão disponíveis pela seleção de **Aplicativos cliente** > **Status de proteção do aplicativo** e escolha de **Relatório de Proteção do Aplicativo: iOS, Android**. Além disso, esses parâmetros ajudam a configurar a lista **Permissão** para o fabricante do dispositivo (Android), a lista **Permissão** para o modelo do dispositivo (Android e iOS) e a configuração de versão mínima do patch de segurança do Android. 


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Os modelos administrativos estão em versão prévia pública e passaram a ter seu próprio perfil de configuração <!-- 3322847 -->

Atualmente, os modelos administrativos no Intune (**Configuração do dispositivo** > **Modelos administrativos**) estão em versão prévia pública. Com esta atualização:

- Os modelos administrativos incluem aproximadamente 300 configurações que podem ser gerenciadas no Intune. Anteriormente, essas configurações só existiam no editor de política de grupo.
- Os modelos administrativos estão disponíveis na versão prévia pública.
- Os modelos administrativos estão sendo transferidos de **Configuração do dispositivo** > **Modelos administrativos** para **Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma**, escolha **Windows 10 e posterior**, em **Tipo de perfil**, escolha **Modelos administrativos**.
- O relatório está habilitado

Para ler mais sobre esse recurso, acesse [Modelos do Windows 10 para definir as configurações da Política de Grupo](../configuration/administrative-templates-windows.md).

Aplica-se a: Windows 10 e posterior

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Usar o S/MIME para criptografar e assinar vários dispositivos para um usuário  <!-- 1333642 -->
Essa atualização inclui uma criptografia de email S/MIME usando um novo perfil de certificado importado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > selecionar a plataforma > tipo de perfil **Certificado PKCS importado**). No Intune, você pode importar certificados no formato PFX. Em seguida, o Intune pode fornecer os mesmos certificados para vários dispositivos registrados por um único usuário. Isso também inclui:
- O perfil de email do iOS nativo permite habilitar a criptografia S/MIME usando certificados importados no formato PFX.
- O aplicativo de email nativo em dispositivos Windows Phone 10 usam automaticamente o certificado S/MIME.
- Os certificados privados podem ser entregues em várias plataformas. Porém, nem todos os aplicativos de email são compatíveis com S/MIME.
- Em outras plataformas, talvez você precise configurar manualmente o aplicativo de email para habilitar o S/MIME.  
- Os aplicativos de email compatíveis com a criptografia S/MIME podem manipular a recuperação de certificados para criptografia de email S/MIME de uma maneira com a qual o MDM não é compatível, como a leitura do repositório de certificados do editor.
Para obter mais informações sobre esse recurso, confira [Visão geral do S/MIME para assinar e criptografar emails](../protect/certificates-s-mime-encryption-sign.md).
Com suporte em: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Novas opções para se conectar automaticamente e persistir as regras ao usar configurações de DNS em dispositivos Windows 10 e posterior <!-- 1333665, 2999078 -->
Em dispositivos Windows 10 e posterior, é possível criar um perfil de configuração de VPN que inclua uma lista de servidores DNS para resolver domínios, por exemplo, contoso.com. Essa atualização inclui novas configurações de resolução de nomes (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **Windows 10 e posterior** para a plataforma > escolha **VPN** para o tipo de perfil > **Configurações de DNS** >**Adicionar**): 
- **Conectar automaticamente**: Quando essa opção está **Habilitada**, o dispositivo se conecta automaticamente à VPN quando um dispositivo entra em contato com um domínio inserido por você, por exemplo, contoso.com.
- **Persistente**: Por padrão, todas as regras de NRPT (Tabela de Políticas de Resolução de Nomes) estão ativas, desde que o dispositivo esteja conectado usando esse perfil de VPN. Quando essa configuração está **Habilitada** em uma regra de NRPT, a regra permanece ativa no dispositivo, mesmo quando a VPN desconectar. A regra permanece até que o perfil de VPN seja removido ou até que a regra seja removida manualmente, o que pode ser feito com o PowerShell.
[Configurações de VPN do Windows 10](../configuration/vpn-settings-windows-10.md) descreve as configurações. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Usar a detecção de rede confiável para perfis de VPN em dispositivos Windows 10 <!-- 1500165 -->
Ao usar a detecção de rede confiável, é possível impedir que os perfis de VPN criem automaticamente uma conexão VPN quando o usuário já está em uma rede confiável. Com essa atualização, é possível adicionar sufixos DNS para habilitar a detecção de rede confiável em dispositivos que executam o Windows 10 e posterior (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **VPN** para o tipo de perfil).
[Configurações de VPN do Windows 10](../configuration/vpn-settings-windows-10.md) lista as configurações de VPN atuais.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Gerenciar dispositivos Windows Holographic for Business usados por vários usuários <!-- 1907917, 1063203 -->
No momento, é possível definir as configurações de computador compartilhado em dispositivos Windows 10 e Windows Holographic for Business usando uma configuração personalizada de OMA-URI. Com essa atualização, um novo perfil é adicionado para definir as configurações de dispositivo compartilhado (**Configuração do dispositivo** > **Perfis** > **Criar Perfil** > **Windows 10 e posterior** > **Dispositivo multiusuário compartilhado**).
Para saber mais sobre esse recurso, acesse [Configurações do Intune para gerenciar dispositivos compartilhados](../configuration/shared-user-device-settings.md).
Aplica-se a: Windows 10 e posteriores, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Novas configurações de Atualização do Windows 10 <!--2626030  2512994  -->
Para os [Grupos de Atualização do Windows 10](../protect/windows-update-for-business-configure.md), é possível configurar:
- **Comportamento de atualização automática** – use uma nova opção, *Redefinir para padrão*, para restaurar as configurações originais de atualização automática em um computador Windows 10 em computadores que executam a *Atualização de outubro de 2018*
- **Impedir que o usuário pause as atualizações do Windows** – defina uma nova configuração de atualizações de Software para impedir ou permitir que os usuários pausem uma instalação de atualização nas *Configurações* de seus computadores. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>Os perfis de email do iOS podem usar assinatura e criptografia S/MIME <!-- 2662949 -->
É possível criar um perfil de email que inclua configurações diferentes. Essa atualização inclui configurações de S/MIME que podem ser usadas para assinar e criptografar comunicações por email em dispositivos iOS (**Configurações do dispositivo** > **Perfis** > **Criar perfil** > escolha **iOS** para a plataforma > **Email** para o tipo de perfil).
[Definições de configuração de email do iOS](../configuration/email-settings-ios.md) lista as configurações.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Algumas configurações do BitLocker dão suporte à edição Windows 10 Pro<!-- 2727036 -->
É possível criar um perfil de configuração que defina as configurações do Endpoint Protection em dispositivos Windows 10, incluindo o BitLocker. Essa atualização adiciona suporte à edição Windows 10 Professional em algumas configurações do BitLocker. Para ver essas configurações de proteção, acesse [Configurações do Endpoint Protection do Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>A configuração de dispositivo compartilhado foi renomeada para Mensagem da Tela de Bloqueio em dispositivos iOS no portal do Azure<!-- 2809362 -->
Ao criar um perfil de configuração para dispositivos iOS, é possível adicionar definições de **Configuração de Dispositivo Compartilhado** para mostrar um texto específico na tela de bloqueio. Essa atualização inclui as seguintes alterações: 
- A **Configuração de Dispositivo Compartilhado** no portal do Azure foi renomeada para "Mensagem na Tela de Bloqueio (apenas supervisionada)" (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **iOS** para a plataforma > escolha **Recursos do dispositivo** para o tipo de perfil > **Mensagem na Tela de Bloqueio**).
- Ao adicionar mensagens da tela de bloqueio, é possível inserir um número de série, um nome de dispositivo ou outro valor específico do dispositivo como variável em **Informações da tag do ativo** e **Nota de rodapé da tela de bloqueio**. Por exemplo, é possível inserir `Device name: {{devicename}}` ou `Serial number is {{serialnumber}}` usando colchetes. [Tokens de iOS](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) lista os tokens disponíveis que podem ser usados.
[Configurações para exibir mensagens na tela de bloqueio](../configuration/ios-device-features-settings.md#lock-screen-message) lista as configurações.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Novas configurações de restrição de dispositivo da App Store, Exibição de Documentos, Jogos adicionadas a dispositivos iOS <!-- 2827760-->
Em **Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil > **App Store, Exibição de Documentos, Jogos**, as seguintes configurações são adicionadas: Permitir que aplicativos gerenciados gravem contatos em contas de contatos não gerenciadas Permitir que aplicativos não gerenciados leiam contas de contatos gerenciadas Para ver essas configurações, acesse [Restrições de dispositivo do iOS](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Novas configurações de notificação, dicas e keyguard para dispositivos de proprietário de dispositivo Android Enterprise <!-- 3201839 3201843 -->
Esta atualização inclui vários recursos novos em dispositivos com Android Enterprise durante a execução como proprietário do dispositivo. Para usar esses recursos, acesse **Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma**, escolha **Android Enterprise** > em **Tipo de perfil**, escolha **Somente proprietário do dispositivo** > **Restrições do Dispositivo**.

Os novos recursos incluem: 

- Desabilitar a exibição de notificações do sistema, incluindo chamadas recebidas, alertas do sistema, erros de sistema e muito mais.
- Sugestão de ignorar os tutoriais iniciais e as dicas para aplicativos abertos pela primeira vez.
- Desabilitar as configurações avançadas de keyguard, como câmera, notificações, impressão digital para desbloqueio e muito mais.


Para ver as configurações, acesse [Configurações de restrição de dispositivo empresarial Android](../configuration/device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Os dispositivos de proprietário de dispositivo Android Enterprise podem usar conexões VPN Always On <!-- 3202194 -->
Nesta atualização, é possível usar as conexões VPN Sempre Ativa em dispositivos com Android Enterprise. As conexões VPN sempre ativadas permanecem conectadas ou são reconectadas imediatamente quando o usuário desbloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. Você também pode colocar a conexão em modo de "bloqueio", o que bloqueia todo o tráfego até que a conexão VPN seja ativada.
É possível habilitar a VPN Sempre Ativa em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Restrições de dispositivo** para Somente Proprietário do Dispositivo > **Conectividade**. Para ver as configurações, acesse [Configurações de restrição de dispositivo empresarial Android](../configuration/device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nova configuração para encerrar processos no Gerenciador de Tarefas em dispositivos Windows 10 <!-- 3285177 --> 
Esta atualização inclui uma nova configuração para encerrar processos usando o Gerenciador de Tarefas em dispositivos com Windows 10. Usando um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma** , escolha **Windows 10** > no **Tipo de perfil**, escolha **Restrições de dispositivo** > **Geral**), é possível permitir ou impedir essa configuração.
Para ver essas configurações, acesse [Configurações de restrição de dispositivo do Windows 10](../configuration/device-restrictions-windows-10.md).
Aplica-se a: Windows 10 e posterior

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Mensagens mais detalhadas sobre a falha de restrição de registro <!-- 3111564 -->
Mensagens de erro mais detalhadas estão disponíveis quando as restrições de registro não são atendidas. Para ver essas mensagens, acesse **Intune** > **Solucionar problemas** e verifique a tabela Falhas de registro. Para obter mais informações, confira a [lista de falhas de registro](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="tenant-status-dashboard-----1124854---"></a>Painel Status do Locatário  <!-- 1124854 -->
A nova [página Status do Locatário](tenant-status.md) fornece uma localização única em que você pode exibir o status e os detalhes relacionados de seu locatário.  O painel é dividido em quatro áreas:
- **Detalhes do Locatário** – exibe informações que incluem o nome do Locatário e a localização, a Autoridade de MDM, o total dos dispositivos registrados no locatário e contagens de licenças. Essa seção também lista a versão de serviço atual do locatário.
- **Status do Conector** – exibe informações sobre os conectores disponíveis configurados e também pode listar aqueles que ainda não foram habilitados.  
   Com base no estado atual de cada conector, eles são sinalizados como Íntegros, Aviso ou Não Íntegros. Selecione um conector para examiná-lo e exibir detalhes ou configurar informações adicionais para ele.
- **Integridade do Serviço Intune** – exibe detalhes sobre incidentes ativos ou interrupções do locatário. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office.
- **Notícias do Intune** – exibe as mensagens ativas do locatário. As mensagens incluem itens como notificações quando seu locatário receber os últimos recursos do Intune.  As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nova experiência de ajuda e suporte no Portal da Empresa para Windows 10 <!-- 1488939-->
A nova página Ajuda e suporte do Portal da Empresa ajuda os usuários a solucionar problemas e solicitar ajuda para problemas de acesso e de aplicativo. Na nova página, eles podem enviar por email detalhes do log de diagnóstico e de erro e encontrar os detalhes da Assistência Técnica de sua organização. Eles também encontrarão uma seção de perguntas frequentes com links para a documentação relevante do Intune. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nova experiência de Ajuda e Suporte do Intune   <!-- #3307080 -->
Estamos distribuindo a nova experiência de Ajuda e Suporte a todos os locatários nos próximos dias. Essa nova experiência está disponível para o Intune e pode ser acessada ao usar as folhas do Intune no [portal do Azure](https://portal.azure.com/).
A nova experiência permite que você descreva seu problema em suas próprias palavras e receba informações de solução de problemas e conteúdo de correção baseado na Web. Essas soluções são oferecidas por meio de um algoritmo de aprendizado de máquina baseado em regras, orientado por consultas de usuário. Além das diretrizes específicas do problema, você usa o novo fluxo de trabalho de criação de caso para abrir um caso de suporte por email ou telefone. Essa nova experiência substitui a experiência anterior de Ajuda e Suporte de um conjunto estático de opções pré-selecionadas com base na área do console em que você está quando abre a Ajuda e Suporte. Para obter mais informações, confira [Como obter suporte para o Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-for-apps----1081941---"></a>Marcas de escopo para aplicativos <!-- 1081941 -->
Você pode criar marcas de escopo para limitar o acesso para funções e aplicativos. Você pode adicionar uma tag de escopo a um aplicativo para que somente as pessoas com as funções também atribuídas a essa tag de escopo tenham acesso ao aplicativo. Atualmente, os aplicativos adicionados ao Intune pela Google Play gerenciado ou a partir de aplicativos adquiridos usando o VPP (Volume Purchase Program) da Apple não podem receber marcas de escopo (está planejado o suporte futuro). Para obter mais informações, confira [Usar marcas de escopo para filtrar políticas](scope-tags.md).

## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](../includes/intune-notices.md)]