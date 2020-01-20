---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 311941c3981e5883d392359dc0919bb85156c4be
ms.sourcegitcommit: fb72b19986f34907d228c856d2e6949751ec02a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75920086"
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
## <a name="week-of-january-6-2020"></a>Semana de 6 de janeiro de 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="smime-support-for-microsoft-outlook-for-ios---2669398---"></a>Suporte para S/MIME no Microsoft Outlook para iOS<!-- 2669398 -->
O Intune dá suporte à entrega de certificados de autenticação e criptografia S/MIME que podem ser usados com o Outlook para iOS em dispositivos iOS. Para obter mais informações, confira [Proteção e rotulagem de confidencialidade no Outlook para iOS e Android](https://aka.ms/omsmime).

#### <a name="cache-win32-app-content-using-microsoft-connected-cache-server---6030314---"></a>Armazenar em cache o conteúdo de aplicativos Win32 usando o servidor do Cache Conectado da Microsoft<!-- 6030314 -->
Instale um servidor do Cache Conectado da Microsoft nos pontos de distribuição do Configuration Manager para armazenar em cache o conteúdo de aplicativos Win32 do Intune. Para obter mais informações, confira [Cache Conectado da Microsoft no Configuration Manager – Suporte para aplicativos Win32 do Intune](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Controle de acesso baseado em funções

#### <a name="windows-10-administrative-templates-admx-profiles-now-support-scope-tags---5137390-wnready--"></a>Os perfis de modelos administrativos (ADMX) do Windows 10 agora dão suporte a marcas de escopo <!--5137390 wnready-->
Agora você pode atribuir marcas de escopo a perfis de modelos administrativos (ADMX). Para fazer isso, acesse **Intune** > **Dispositivos** > **Perfis de configuração** > escolha um perfil de modelos administrativos na lista > **Propriedades** > **Marcas de escopo**. Para obter mais informações sobre marcas de escopo, confira [Atribuir marcas de escopo a outros objetos](../fundamentals/scope-tags.md#assign-scope-tags-to-other-objects).

<!-- ########################## -->
## <a name="week-of-december-30-2019"></a>Semana de 30 de dezembro de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>Recuperar a chave de recuperação pessoal de dispositivos macOS criptografados com MEM<!-- 4851745 -->
Os usuários finais podem reaver sua chave de recuperação pessoal (Chave do FileVault) usando o aplicativo Portal da Empresa do iOS. O dispositivo com a chave de recuperação pessoal deve ser registrado com o Intune e criptografado com o FileVault pelo Intune. Usando o aplicativo Portal da Empresa do iOS, um usuário final pode reaver sua chave de recuperação pessoal em seu dispositivo macOS criptografado clicando em **Obter chave de recuperação**. Você também pode recuperar a chave de recuperação do Intune escolhendo **Dispositivos** > *o dispositivo macOS criptografado e registrado* > **Obter a chave de recuperação**. Para saber mais sobre o FileVault, confira [Criptografia do FileVault para macOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

#### <a name="ios-and-ipados-user-licensed-vpp-apps---5619268---"></a>Aplicativos VPP licenciados para o usuário do iOS e do iPadOS<!-- 5619268 -->
Para dispositivos iOS e iPadOS registrados pelo usuário, os usuários finais não verão mais os aplicativos VPP licenciados para dispositivos recém-criados implantados como disponíveis. No entanto, os usuários finais continuarão a ver todos os aplicativos do VPP licenciados para o usuário dentro do Portal da Empresa. Para saber mais sobre aplicativos VPP, confira [Como gerenciar aplicativos para iOS e macOS adquiridos por meio do Apple Volume Purchase Program com o Microsoft Intune](~/apps/vpp-apps-ios.md).

<!-- ########################## -->
## <a name="week-of-december-23-2019"></a>Semana de 23 de dezembro de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="notice---windows-10-1703-rs2-will-be-moving-out-of-support----5026679---"></a>Aviso: o Windows 10 1703 (RS2) não terá mais suporte <!-- 5026679 -->
A partir de 9 de outubro de 2018, o Windows 10 1703 (RS2) não terá mais suporte da plataforma Microsoft para as edições Home, Pro e Pro for Workstations. Para as edições Windows 10 Enterprise e Education, o Windows 10 1703 (RS2) perdeu o suporte de plataforma em 8 de outubro de 2019. A partir de 26 de dezembro de 2019, atualizaremos a versão mínima do aplicativo de Portal da Empresa do Windows para o Windows 10 1709 (RS3). Os computadores que executam versões anteriores à 1709 não receberão mais versões atualizadas do aplicativo da Microsoft Store. Comunicamos antecipadamente essa alteração aos clientes que gerenciam versões mais antigas do Windows 10 por meio do centro de mensagens. Para saber mais, confira o [informativo sobre o ciclo de vida do Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

<!-- ########################## -->

## <a name="week-of-december-16-2019"></a>Semana de 16 de dezembro de 2019

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updates-to-administrative-templates-for-windows-10-devices----5941568---"></a>Atualizações dos Modelos Administrativos para dispositivos Windows 10 <!-- 5941568 -->

Você pode usar modelos ADMX no Microsoft Intune para controlar e gerenciar as configurações do Microsoft Edge, Office e Windows. O recurso Modelos Administrativos no Intune fez as seguintes atualizações de configuração de política:

- Adicionado suporte para as versões 78 e 79 do Microsoft Edge.
- Inclui os arquivos ADMX de 11 de novembro de 2019 nos [arquivos de Modelo Administrativo (ADMX/ADML) e a Ferramenta de Personalização do Office para Office 365 ProPlus, Office 2019 e Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Para saber mais sobre modelos ADMX no Intune, confira [Usar modelos do Windows 10 para definir configurações de política de grupo no Microsoft Intune](../configuration/administrative-templates-windows.md).

Aplica-se a:

- Windows 10 e posterior

## <a name="week-of-december-9-2019-1912-service-release"></a>Semana de 9 de dezembro de 2019 (versão do serviço 1912)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="migrating-to-microsoft-edge-for-managed-browsing-scenarios---5173762---"></a>Como fazer a migração para o Microsoft Edge em cenários de navegação gerenciada<!-- 5173762 -->
À medida que chegamos mais perto da desativação do Intune Managed Browser, fizemos alterações nas políticas de proteção do aplicativo para simplificar as etapas necessárias para migrar os usuários para o Edge. Atualizamos as opções da configuração **Restringir a transferência de conteúdo da Web com outros aplicativos** da política de proteção do aplicativo para que ela seja uma das seguintes:

- Qualquer aplicativo
- Intune Managed Browser
- Microsoft Edge
- Navegador não gerenciado 

Quando você selecionar **Microsoft Edge**, os usuários finais verão mensagens do acesso condicional notificando-os de que o Microsoft Edge é obrigatório para cenários de navegação gerenciada. Eles deverão baixar o Microsoft Edge e entrar nele com suas respectivas contas do AAD, caso ainda não tenham feito isso.  Isso será o equivalente a ter como destino seus aplicativos habilitados para MAM com a configuração do aplicativo `com.microsoft.intune.useEdge` definida como **Verdadeiro**. As políticas de proteção do aplicativo existentes que usavam a configuração **Navegadores gerenciados por política** agora terão o **Intune Managed Browser** selecionado, e você não verá nenhuma alteração no comportamento. Isso significa que os usuários verão mensagens para uso do Microsoft Edge se você definir a configuração do aplicativo **useEdge** como **Verdadeiro**. Incentivamos todos os clientes que utilizam cenários de navegação gerenciada a atualizar as políticas de proteção do aplicativo com a configuração **Restringir a transferência de conteúdo da Web com outros aplicativos** para garantir que os usuários estejam vendo as diretrizes apropriadas para fazer a transição para o Microsoft Edge, seja qual for o aplicativo do qual eles estão iniciando os links. 

#### <a name="configure-app-notification-content-for-organization-accounts---2576686----"></a>Configurar conteúdo de notificação do aplicativo para contas da organização<!-- 2576686  -->
As APP (políticas de proteção de aplicativo) do Intune em dispositivos Android e iOS permitem controlar o conteúdo de notificação do aplicativo para contas da organização. Você pode selecionar uma opção (Permitir, Bloquear Dados da organização ou Bloquear) para especificar como são exibidas as notificações para contas da organização no aplicativo selecionado. Esse recurso requer suporte de aplicativos e pode não estar disponível para todos os aplicativos habilitados para APP. O Outlook para iOS versão 4.15.0 (ou posterior) e o Outlook para Android 4.83.0 (ou posterior) dão suporte a essa configuração. A configuração está disponível no console, mas a funcionalidade entrará em vigor após 16 de dezembro de 2019. Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](../apps/app-protection-policy.md).

#### <a name="microsoft-app-icons-update--4677605----"></a>Atualização de ícones do aplicativo Microsoft<!--4677605  -->
Os ícones usados para aplicativos da Microsoft no painel de direcionamento de aplicativo para políticas de proteção de aplicativo e de configuração de aplicativo foram atualizados.

#### <a name="require-use-of-approved-keyboards-on-android--4761794----"></a>Exigir o uso de teclados aprovados no Android<!--4761794  -->
Como parte de uma política de proteção de aplicativo, você pode especificar a configuração [**Teclados aprovados**](../apps/app-protection-policy-settings-android.md#data-protection) para gerenciar quais teclados Android podem ser usados com aplicativos Android gerenciados. Quando um usuário abre o aplicativo gerenciado e ainda não usa um teclado aprovado para esse aplicativo, ele recebe uma solicitação para trocar para uma dos teclados aprovados já instalados no dispositivo. Se necessário, é apresentado um link para baixar um teclado aprovado da Google Play Store, que pode ser instalado e configurado. O usuário só pode editar campos de texto em um aplicativo gerenciado quando o teclado ativo não for um dos teclados aprovados.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578----"></a>Experiência de logon único atualizada para aplicativos e sites em dispositivos iOS, iPadOS e macOS<!-- 4999578  -->
O Intune adicionou configurações de SSO (logon único) para dispositivos iOS, iPadOS e macOS. Agora você pode configurar as extensões de aplicativos de SSO de redirecionamento gravadas por sua organização ou pelo seu provedor de identidade. Use essas configurações para definir uma experiência de logon único simplificada para aplicativos e sites que usam métodos de autenticação modernos, como OAuth e SAML2. 

Essas novas configurações ampliam as configurações anteriores para extensões de aplicativo de SSO e a extensão Kerberos integrada da Apple (**Dispositivos** > **Configuração de dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** ou **macOS** para o tipo de plataforma > **Recursos do dispositivo** para o tipo de perfil). 

Para ver todas as configurações de extensão de aplicativo de SSO que você pode definir, acesse [SSO no iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) e [SSO no macOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Aplica-se a:

- iOS/iPadOS
- macOS

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352-wnready-----"></a>Atualizamos duas configurações de restrição de dispositivo para corrigir o comportamento em dispositivos iOS e iPadOS<!-- 5701352 WNReady   -->
Para dispositivos iOS, você pode criar perfis de restrição de dispositivo para **Permitir atualizações over-the-air do PKI** e **Bloquear o Modo restrito de USB** (**Dispositivos** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para plataforma > **Restrições de dispositivo** para o tipo de perfil). Antes desta versão, as configurações e descrições da interface do usuário das configurações a seguir estavam incorretas e agora foram corrigidas. A partir desta versão, o comportamento das configurações é o seguinte:

**Bloquear atualizações over-the-air do PKI**: **Bloquear** impede que os usuários recebam atualizações de software, a menos que o dispositivo esteja conectado a um computador. **Não configurado** (padrão): permite que um dispositivo receba atualizações de software sem estar conectado a um computador.
- Anteriormente, essa opção permitia as seguintes configurações: **Permitir**, na qual os usuários podem receber atualizações de software sem conectar seus dispositivos a um computador.
**Permitir acessórios USB enquanto o dispositivo estiver bloqueado**: **Permitir** deixa que os acessórios USB troquem dados com um dispositivo que tenha sido bloqueado por mais de uma hora. **Não configurado** (padrão) não atualiza o Modo restrito de USB no dispositivo, e os acessórios USB serão impedidos de transferir dados do dispositivo se estiverem bloqueados por mais de uma hora.
- Anteriormente, essa opção permitia as seguintes configurações: **Bloquear** para desabilitar o Modo restrito de USB nos dispositivos supervisionados.

Para saber mais sobre as configurações que você pode definir, confira [Configurações de dispositivos iOS e iPadOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md).

Esse recurso aplica-se a:

- OS/iPadOS

#### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Perfil de configuração do dispositivo de rede com fios para dispositivos macOS<!-- 3508686  -->
   > [!NOTE]
   > Esse recurso foi atrasado, mas será lançado em breve.

#### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998---"></a>Impedir que os usuários configurem credenciais de certificado no repositório de chaves gerenciado em dispositivos de proprietários de dispositivo Android Enterprise<!-- 3311998 -->
Em dispositivos de proprietários de dispositivo Android Enterprise, você pode definir uma nova configuração que impeça os usuários de configurar suas credenciais de certificado no repositório de chaves gerenciado (**Configuração de dispositivos** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Somente Proprietário do Dispositivo > Restrições de Dispositivos** para o tipo de perfil > **Usuários + Contas**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="protected-wipe-action-now-available--51150000---"></a>Agora está disponível a ação de apagamento protegido<!--51150000 -->
Agora você tem a opção de usar a ação Apagar dispositivo para executar um apagamento protegido de um dispositivo. Os apagamentos protegidos são os mesmos que os apagamentos padrão, exceto pelo fato de que não podem ser evitados desligando o dispositivo. Um apagamento protegido continuará tentando redefinir o dispositivo até que seja bem-sucedido. Em algumas configurações, essa ação poderá deixar o dispositivo sem a capacidade de reinicialização. Para saber mais, confira [Desativar ou apagar dispositivos](../remote-actions/devices-wipe.md).

#### <a name="device-ethernet-mac-address-added-to-devices-overview-page--5562275---"></a>Endereço MAC Ethernet do dispositivo adicionado à página Visão geral do dispositivo<!--5562275 -->
Agora você pode ver o endereço MAC Ethernet do dispositivo na página de detalhes do dispositivo (**Dispositivos** > **Todos os dispositivos** > escolher um dispositivo > **Visão geral**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="improved-experience-on-a-shared-device-when-device-based-conditional-access-policies-are-enabled---1734096----"></a>Experiência aprimorada em um dispositivo compartilhado quando as políticas de acesso condicional baseadas em dispositivo estão habilitadas<!-- 1734096  -->
Melhoramos a experiência em um dispositivo compartilhado com vários usuários que são direcionados à política de acesso condicional baseada em dispositivo, verificando a avaliação de conformidade mais recente do usuário ao impor a política. Para saber mais, confira os seguintes artigos de visão geral:
- [Visão geral do Azure para Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Visão geral da conformidade do dispositivo Intune](../protect/device-compliance-get-started.md)

#### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529----"></a>Usar perfis de certificado PKCS para provisionar dispositivos com certificados<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529  -->
Agora, você pode usar perfis de certificado PKCS para emitir certificados para *dispositivos* que executam o Android for Work, o iOS e o Windows, quando associados a perfis como os de Wi-Fi e VPN. Anteriormente, essas três plataformas davam suporte apenas para certificados baseados no usuário, com suporte baseado em dispositivo limitado ao macOS.

> [!NOTE]
> Não há suporte para perfis de certificado PKCS em perfis de Wi-Fi. Em vez disso, use perfis de certificado SCEP ao usar um [tipo de EAP](../configuration/wi-fi-settings-windows.md#enterprise-profile).

Para usar um certificado baseado em dispositivo, ao [criar um perfil de certificado PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) para as plataformas com suporte, selecione **Configurações**. Você verá a configuração para **Tipo de certificado**, que dá suporte às opções de Dispositivo ou Usuário.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="centralized-audit-logs--5603185-5697164---"></a>Logs de auditoria centralizados<!--5603185, 5697164 -->
Uma nova experiência de log de auditoria centralizado agora coleta os logs de auditoria de todas as categorias em uma única página. Você pode filtrar os logs para obter os dados que está procurando. Para ver os logs de auditoria, acesse **Administração de locatários** > **Logs de auditoria**. 

#### <a name="scope-tag-information-included-in-audit-log-activity-details--5763534---"></a>Informações de marca de escopo incluídas nos detalhes da atividade do log de auditoria<!--5763534 -->
Os detalhes da atividade do log de auditoria agora incluem informações de marca de escopo (para objetos do Intune com suporte às marcas de escopo). Para saber mais sobre logs de auditoria, confira [Usar logs de auditoria para acompanhar e monitorar eventos](monitor-audit-logs.md).


<!-- ########################## -->
## <a name="week-of-december-2-2019"></a>Semana de 2 de dezembro de 2019

#### <a name="new-microsoft-endpoint-configuration-manager-co-management-licensing--5027281--"></a>Novo licenciamento de cogerenciamento do Microsoft Endpoint Configuration Manager<!--5027281-->
Uma nova licença já está disponível, que permite que os clientes do Configuration Manager com o Software Assurance obtenham o cogerenciamento do Intune para computadores Windows 10 sem precisar comprar uma licença adicional do Intune para o cogerenciamento. Os clientes não precisam mais atribuir licenças individuais do Intune/do EMS aos usuários finais para cogerenciar o Windows 10.
- Os dispositivos gerenciados pelo Configuration Manager e registrados no cogerenciamento têm quase os mesmos direitos dos computadores gerenciados pelo MDM autônomos do Intune. No entanto, após a redefinição, eles não poderão ser provisionados novamente usando o Autopilot.
- Os dispositivos Windows 10 registrados no Intune que usam outros meios exigem licenças integrais do Intune.
- Os dispositivos em outras plataformas ainda exigem licenças integrais do Intune.

Para obter mais informações, confira [Termos de licenciamento](https://www.microsoft.com/en-us/Licensing/product-licensing/products).


<!-- ########################## -->
## <a name="week-of-november-18-2019-1911-service-release"></a>Semana de 18 de novembro de 2019 (versão do serviço 1911)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Atualização da interface do usuário ao limpar seletivamente dados de aplicativos<!-- 4102028 -->
A interface do usuário para limpar seletivamente os dados do aplicativo no Intune foi atualizada. As alterações da interface do usuário incluem:
- Uma experiência simplificada usando um formato com estilo de assistente condensado dentro de um único painel.
- Uma atualização do fluxo de criação a fim de incluir atribuições.
- Uma página resumida de todas as coisas definidas ao exibir as propriedades, antes de criar uma nova política ou ao editar uma propriedade. Além disso, ao editar propriedades, o resumo mostra apenas a lista de itens da categoria de propriedades em edição.

Para saber mais, confira [Como apagar apenas dados corporativos dos aplicativos gerenciados pelo Intune](~/apps/apps-selective-wipe.md).

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>Suporte a teclados de terceiros para iOS e iPadOS<!-- 4922950 -->
Em março de 2019, anunciamos a remoção do suporte para a configuração da política de proteção de aplicativos para iOS "Teclados de terceiros". O recurso está retornando ao Intune com suporte para iOS e iPadOS. Para habilitar essa configuração, acesse a guia **Proteção de dados** de uma política de proteção de aplicativo do iOS/iPadOS nova ou já existente e localize a configuração **Teclados de terceiros** em **Transferência de Dados**.

O comportamento dessa configuração de política difere um pouco da implementação anterior. Em aplicativos com várias identidades que usam o SDK versão 12.0.16 e posterior, direcionados pelas políticas de proteção de aplicativos com essa configuração definida como **Bloquear**, os usuários finais não poderão optar por teclados de terceiros em suas contas pessoais e em contas da organização. Os aplicativos que usam o SDK 12.0.12 e versões anteriores continuarão exibindo o comportamento documentado no título da postagem do blog, [Problema conhecido: os teclados de terceiros não são bloqueados no iOS para contas pessoais](https://aka.ms/3rdparty_iOS_Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>Defina grupos de usuários do macOS como destino para exigir o gerenciamento Jamf<!-- 4061739  --> 
Você pode direcionar grupos específicos de usuários que receberão seus [dispositivos macOS gerenciados pelo Jamf](../protect/conditional-access-integrate-jamf.md). Isso permite aplicar a integração de conformidade do Jamf a um subconjunto de dispositivos macOS enquanto outros dispositivos são gerenciados pelo Intune. Se você já estiver usando a integração do Jamf, todos os usuários serão definidos como destino para a integração por padrão.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>Novas configurações do Exchange ActiveSync ao criar um Perfil de configuração de dispositivo de email em dispositivos iOS<!-- 4892824   --> 
Em dispositivos iOS/iPadOS, você pode configurar a conectividade de emails em um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **Email** para o tipo de perfil). 

Existem novas configurações do Exchange ActiveSync disponíveis, incluindo:
- **Dados do Exchange para compartilhar**: Escolha os serviços do Exchange para sincronizar (ou bloquear a sincronização) para Calendário, Contatos, Lembretes, Anotações e Email.
- **Permitir que os usuários alterem as configurações de sincronização**: Permita (ou impeça) que os usuários alterem as configurações de sincronização desses serviços em seus dispositivos.  

Para obter mais informações sobre essas configurações, acesse [Configurações de perfil de email para dispositivos iOS no Intune](../configuration/email-settings-ios.md). 

Aplica-se a:

- iOS 13.0 e mais recente
- iPadOS 13.0 e versões mais recentes

#### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-fully-managed-and-dedicated-devices---5353228-----"></a>Impedir que os usuários adicionem contas do Google pessoais a dispositivos totalmente dedicados e gerenciados do Android Enterprise<!-- 5353228   -->
Em dispositivos totalmente dedicados e gerenciados do Android Enterprise, há uma nova configuração que impede que os usuários criem contas pessoais do Google (**Configuração de dispositivos** > **Profis** > **Criar perfis** > **Android Enterprise** para a plataforma > **Somente Proprietário do Dispositivo > Restrições de Dispositivos** para o tipo de perfil > **Configurações de usuários e contas** > **Contas pessoais do Google**).

Para ver as configurações que você pode definir, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md).

Aplica-se a:

- Dispositivos Android Enterprise totalmente gerenciados
- Dispositivos Android Enterprise dedicados

#### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-iosipados-device-restrictions-profile----5468501-----"></a>A configuração Registro em log no lado do servidor para os comandos da Siri foi removida no perfil de restrições de dispositivos iOS/iPadOS <!-- 5468501   -->
Em dispositivos iOS e iPadOS, a configuração **Registro em log no lado do servidor para os comandos da Siri** é removida do console de administração do Gerenciador de Ponto de Extremidade da Microsoft (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **Restrições do dispositivo** para o tipo de perfil > **Aplicativos internos**). 

Essa configuração não afeta dispositivos. Para remover a configuração de perfis existentes, abra o perfil, faça as alterações necessárias e salve o perfil. O perfil é atualizado, e a configuração é excluída dos dispositivos.

Para ver todas as configurações que você pode definir, confira [Configurações de dispositivos iOS e iPadOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md).

Aplica-se a:

- iOS/iPadOS

#### <a name="windows-10-feature-updates-public-preview---2384877---"></a>Atualizações de recursos do Windows 10 (visualização pública)<!-- 2384877 -->
Agora você pode implantar [atualizações de recurso do Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates) em dispositivos Windows 10. As atualizações de recursos do Windows 10 são uma nova política de atualização de software que define a versão do Windows 10 que você deseja que os dispositivos instalem e utilizem. Você pode usar esse novo tipo de política junto com os anéis de atualização existentes do Windows 10.

Os dispositivos que recebem a política de atualizações de recursos do Windows 10 instalarão a versão especificada do Windows e permanecerão com essa versão até que a política seja editada ou removida. Os dispositivos que executam uma versão mais recente do Windows permanecem com sua versão atual. Os dispositivos que são mantidos em uma versão específica do Windows ainda podem instalar as atualizações de qualidade e de segurança para essa versão dos anéis de atualização do Windows 10.

Esse novo tipo de política começa a ser distribuído para os locatários esta semana. Se essa política ainda não estiver disponível para o seu locatário, ela estará em breve.

#### <a name="add-and-change-key-information-in-plist-files-for-macos-applications---4736278---"></a>Adicionar e alterar informações importantes em arquivos plist para aplicativos macOS<!-- 4736278 -->
Em dispositivos macOS, agora você pode criar um perfil de configuração de dispositivo que carrega um arquivo de lista de propriedades (.plist) associado a um aplicativo ou ao dispositivo (**Dispositivos** > **Perfis de configuração** > **Criar perfil** > **macOS** para a plataforma > **Arquivo de Preferência** para o tipo de perfil).

Apenas alguns aplicativos dão suporte para preferências gerenciadas, e esses aplicativos podem não permitir o gerenciamento de todas as configurações. Certifique-se de carregar um arquivo da lista de propriedades que defina as configurações do canal do dispositivo, e não as configurações do canal do usuário.

Para saber mais sobre esse recurso, confira [Adicionar um arquivo de lista de propriedades a dispositivos macOS usando o Microsoft Intune](../configuration/preference-file-settings-macos.md).

Aplica-se a:

- dispositivos macOS executando a versão 10.7 e mais recentes

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="edit-device-name-value-for-autopilot-devices---2640074---"></a>Editar o valor do nome do dispositivo para dispositivos do Autopilot<!-- 2640074 -->
Você pode editar o valor do nome do dispositivo para dispositivos do Autopilot ingressados no Azure AD.  Para saber mais, confira [Editar atributos do dispositivo do Autopilot](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

#### <a name="edit-group-tag-value-for-autopilot-devices---4816775-----"></a>Editar o valor de Tag de Grupo para dispositivos do Autopilot<!-- 4816775   -->
Você pode editar o valor de Tag de Grupo para dispositivos do Autopilot. Para saber mais, confira [Editar atributos do dispositivo do Autopilot](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="updated-support-experience---5012398---"></a>Experiência de suporte atualizada<!-- 5012398 -->

A partir de hoje, será distribuída para os locatários uma experiência atualizada e simplificada no console para [obter ajuda e suporte para o Intune](get-support.md). Se essa nova experiência ainda não estiver disponível para você, ela estará em breve.

Melhoramos a pesquisa no console, os comentários sobre problemas comuns e o fluxo de trabalho que você usa para entrar em contato com o suporte. Ao abrir um problema de suporte, você verá estimativas em tempo real de quando pode esperar um retorno de chamada ou resposta por email, e os clientes de suporte Premier e Unificado podem especificar com facilidade a gravidade do problema, para ajudar a obter suporte de forma mais rápida.

#### <a name="improved-intune-reporting-experience-public-preview----3791418---"></a>Experiência aprimorada de relatórios do Intune (visualização pública) <!-- 3791418 -->
O Intune agora oferece uma experiência aprimorada de relatórios, incluindo novos tipos de relatórios, melhor organização de relatórios, visualizações mais focadas, funcionalidade aprimorada de relatórios e dados mais consistentes e oportunos. Novos tipos de relatório se concentram no seguinte:
- **Operacional** - fornece novos registros com foco de integridade negativa. 
- **Organizacional** - fornece um resumo mais amplo do estado geral.
- **Histórico** – fornece padrões e tendências ao longo de um período.
- **Especialista** – permite que você use dados brutos para criar seus próprios relatórios personalizados.

O primeiro conjunto de novos relatórios se concentra na conformidade do dispositivo. Para saber mais, confira [Blog - Estrutura de relatórios do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) e [Relatórios do Intune](~/fundamentals/reports.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Controle de acesso baseado em funções

#### <a name="duplicate-custom-or-built-in-roles----1081938-----"></a>Duplicar funções personalizadas ou internas <!-- 1081938   -->
Agora, você pode copiar funções internas e personalizadas. Para saber mais, confira [Copiar uma função](../fundamentals/create-custom-role.md#copy-a-role).

#### <a name="new-permissions-for-school-administrator-role----5621805----"></a>Novas permissões para a função de administrador da escola <!-- 5621805  -->  
Duas novas permissões, **Atribuir perfil** e **Sincronizar dispositivo**, foram adicionadas à função de administrador da escola > **Permissões** > **Programas de inscrição**. A permissão de perfil de sincronização permite que administradores de grupo sincronizem os dispositivos do Windows Autopilot. A permissão de atribuição de perfil permite excluir perfis de inscrição da Apple iniciados pelo usuário. Ela também permite que eles gerenciem atribuições de dispositivos do AutoPilot e atribuições de perfil de implantação do AutoPilot. Para obter uma lista de todas as permissões de administrador de escola/administrador de grupo, confira [Atribuir administradores de grupo](https://docs.microsoft.com/intune-education/group-admin-delegate). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="security"></a>Segurança

#### <a name="bitlocker-key-rotation---2564951----"></a>Rodízio de chaves do BitLocker<!-- 2564951  -->
Você pode usar uma ação de dispositivo do Intune para [fazer o rodízio remoto de chaves de recuperação do BitLocker](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) para dispositivos gerenciados que executam o Windows versão 1909 ou posterior. Para se qualificarem para o rodízio de chaves de recuperação, os dispositivos devem ser configurados para oferecer suporte ao rodízio de chaves de recuperação.  

#### <a name="updates-to-dedicated-device-enrollment-to-support-scep-device-certificate-deployment----5198878----"></a>Atualizações na inscrição de dispositivos dedicados para oferecer suporte à implantação de certificado de dispositivos SCEP <!-- 5198878  -->
O Intune agora dá suporte à implantação de certificados de dispositivos SCEP em dispositivos dedicados do Android Enterprise para acesso baseado em certificado a perfis de Wi-Fi. O aplicativo Microsoft Intune deve estar presente no dispositivo para que a implantação funcione. Como resultado, atualizamos a experiência de inscrição em dispositivos dedicados do Android Enterprise. Novas inscrições ainda são iniciadas da mesma forma (com QR, NFC, Zero-touch ou identificador de dispositivo), mas agora têm uma etapa que exige que os usuários instalem o aplicativo Intune. Os dispositivos existentes começarão a instalar o aplicativo automaticamente de forma contínua.

#### <a name="intune-audit-logs-for-business-to-business-collaboration--5670211---"></a>Logs de auditoria do Intune para colaboração entre empresas<!--5670211 -->
A colaboração entre empresas (B2B) permite compartilhar com segurança os aplicativos e serviços da sua empresa com usuários convidados de qualquer outra organização, mantendo o controle sobre seus próprios dados corporativos. O Intune agora dá suporte a logs de auditoria para usuários convidados B2B. Por exemplo, quando os usuários convidados fizerem alterações, o Intune poderá capturar esses dados através de logs de auditoria. Para saber mais, confira [O que é o acesso de usuário convidado no Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)


<!-- ########################## -->
## <a name="week-of-november-11-2019"></a>Semana de 11 de novembro de 2019  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos  

#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Experiência aprimorada de registro do macOS no Portal da Empresa <!-- 5074349  -->  
O Portal da Empresa para a experiência de registro do macOS tem um processo de registro mais simples que se alinha melhor com o Portal da Empresa para a experiência de registro do iOS. Os usuários do dispositivo agora veem:  

* Uma interface do usuário mais elegante.  
* Uma lista de verificação de registro aprimorada.  
* Instruções mais claras sobre como registrar os dispositivos.  
* Opções aprimoradas para solução de problemas.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Aplicativos Web iniciados no aplicativo do Portal da Empresa para Windows<!-- 5030972 -->
Os usuários finais agora podem iniciar aplicativos Web diretamente do aplicativo do Portal da Empresa para Windows. Os usuários finais podem selecionar o aplicativo Web e escolher a opção **Abrir no navegador**. A URL da Web publicada é aberta diretamente em um navegador da Web. Essa funcionalidade será distribuída na próxima semana. Para mais informações sobre aplicativos Web, confira [Adicionar aplicativos Web ao Microsoft Intune](~/apps/web-app.md).  


#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950----"></a>Nova coluna de tipo de atribuição no Portal da Empresa para Windows 10 <!-- 5459950  -->
A coluna Portal da Empresa > **Aplicativos Instalados** > **Tipo de atribuição** foi renomeada para **Exigido pela sua organização**.  Nessa coluna, os usuários verão um valor **Sim** ou **Não** para indicar que um aplicativo é necessário ou se tornou opcional por sua organização. Essas alterações foram feitas porque os usuários do dispositivo estavam confusos sobre o conceito de aplicativos disponíveis. Seus usuários podem encontrar mais informações sobre como instalar aplicativos no Portal da Empresa, confira [Instalar e compartilhar aplicativos em seu dispositivo](/intune-user-help/install-apps-cpapp-windows). Para saber mais sobre como configurar o aplicativo do Portal da Empresa para os seus usuários, confira [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](~/apps/company-portal-app.md).  

<!-- ########################## -->
## <a name="week-of-november-4-2019"></a>Semana de 4 de novembro de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>As linhas de base de segurança recebem suporte no Microsoft Azure Governamental<!-- 4062552 -->

Agora as instâncias do Intune hospedadas no *Microsoft Azure Governamental* podem usar as [linhas de base de segurança](../protect/security-baselines.md) para ajudar na segurança e na proteção de seus usuários e dispositivos.

<!-- ########################## -->
## <a name="week-of-october-28-2019"></a>Semana de 28 de outubro de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Design aprimorado para listas de verificação no aplicativo Portal da Empresa para Android<!-- 5550857 -->  
A lista de verificação de configuração no aplicativo Portal da Empresa para Android foi atualizada com um design leve e novos ícones. As alterações se alinham com as recentes atualizações do aplicativo Portal da Empresa para iOS. Para ver uma comparação lado a lado das alterações, confira [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md). Para ver as etapas de registro atualizadas, confira [Registrar com o perfil de trabalho do Android](/intune-user-help/enroll-device-android-work-profile) e [Registrar seu dispositivo Android](/intune-user-help/enroll-device-android-company-portal).  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Aplicativos Win32 em dispositivos no modo Windows 10 S<!-- 3747604 --> 
É possível instalar e executar aplicativos Win32 em dispositivos gerenciados com o modo Windows 10 S. Para isso, é possível criar uma ou mais políticas complementares para o modo S usando as ferramentas do PowerShell do WDAC (Controle de Aplicativos do Windows Defender). Assine as políticas complementares no Portal de Autenticação do Device Guard e, em seguida, carregue e distribua as políticas por meio do Intune. No Intune, você encontrará esse recurso ao selecionar **Aplicativos cliente** > **Políticas complementares do Windows 10 S**. Confira mais informações em [Habilitar aplicativos Win32 no modo S](~/apps/apps-win32-s-mode.md).

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>Configurar a disponibilidade de aplicativos Win32 com base em uma data e hora<!-- 3510685 -->
Como administrador, você pode configurar a hora de início e a hora do prazo para um aplicativo Win32 obrigatório. Na hora de início, a extensão de gerenciamento do Intune inicia o download do conteúdo do aplicativo e o armazena em cache. O aplicativo será instalado na hora do prazo. Para aplicativos disponíveis, a hora de início informa quando o aplicativo está visível no Portal da Empresa. Confira mais informações em [Gerenciamento de aplicativos Win32 no Intune](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Exigir reinicialização do dispositivo com base no período de carência após a instalação de aplicativo Win32<!-- 3136567 -->
Você pode exigir que um dispositivo seja reiniciado depois que um aplicativo Win32 for instalado com êxito. Confira mais informações em [Gerenciamento de aplicativos Win32 – Configurar detalhes de instalação de aplicativo](~/apps/apps-win32-app-management.md#step-4-configure-app-installation-details).

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>Modo escuro para Portal da Empresa no iOS<!-- 4911422 -->
O Modo escuro está disponível para o Portal da Empresa no iOS. Os usuários podem baixar aplicativos da empresa, gerenciar seus dispositivos e obter suporte de TI no esquema de cores de sua escolha, com base nas configurações do dispositivo. O Portal da Empresa para iOS corresponderá automaticamente às configurações do dispositivo do usuário final para o modo escuro ou claro. Para obter mais informações, confira [Introdução ao modo escuro no Portal da Empresa do Microsoft Intune para iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). Para obter mais informações sobre o Portal da Empresa do iOS, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>O Portal da Empresa para Android impõem a versão mínima do aplicativo<!-- 2378776 -->
Com a configuração **Versão mínima do Portal da Empresa** de uma política de proteção de aplicativo, você pode especificar uma versão mínima definida específica do Portal da Empresa que é imposta em um dispositivo de usuário final. Essa configuração de inicialização condicional permite que você use **Bloquear acesso**, **Apagar dados** ou **Avisar** como possíveis ações quando o valor não for atendido. Os formatos possíveis para esse valor seguem o padrão *[Major].[Minor]* , *[Major].[Minor].[Build]* ou *[Major].[Minor].[Build].[Revision]* .

A configuração **Versão mínima do Portal da Empresa**, se configurada, afetará todos os usuários finais que receberem a versão 5.0.4560.0 do Portal da Empresa e todas as versões futuras do Portal da Empresa. Essa configuração não terá nenhum efeito nos usuários que usam uma versão do Portal da Empresa mais antiga do que a versão na qual esse recurso é lançado. Os usuários finais que usam as atualizações automáticas do aplicativo nos dispositivos provavelmente não verão nenhuma caixa de diálogo desse recurso, considerando que eles provavelmente estarão na versão mais recente do Portal da Empresa. Essa configuração é apenas para Android, com proteção de aplicativo para dispositivos registrados e não registrados. Para mais informações, confira [Configurações de política de proteção do aplicativo Android – Inicialização condicional](~/apps/app-protection-policy-settings-android.md#conditional-launch).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->

### <a name="microsoft-365-device-management"></a>Gerenciamento de dispositivos do Microsoft 365

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Introdução ao Nó de segurança de ponto de extremidade no Gerenciamento de dispositivos do Microsoft 365<!-- 5630102 -->

O nó de **segurança de ponto de extremidade** está disponível agora no Espaço de trabalho especializado de gerenciamento de dispositivos do Microsoft 365 em https://devicemanagement.microsoft.com, que agrupa os recursos para proteger pontos de extremidade, como:

- Linhas de base de segurança:  grupo pré-configurado de definições que ajudam a aplicar um grupo conhecido de definições e valores padrão recomendados pela Microsoft.

- Tarefas de segurança: aproveite o TVM (gerenciamento de ameaças e vulnerabilidades) do Microsoft Defender ATP e use o Intune para corrigir os pontos fracos do ponto de extremidade.

- Microsoft Defender ATP: a ATP (Proteção Avançada contra Ameaças) do Microsoft Defender integrada para ajudar a evitar violações de segurança.

Essas configurações continuarão a ser acessadas de outros nós aplicáveis, como dispositivos, e o estado configurado atual será o mesmo, independentemente de onde você acessar e habilitar esses recursos.

Para obter mais informações sobre esses aprimoramentos, confira a [postagem no blog Sucesso do cliente do Intune](https://aka.ms/Endpoint_security_node) no site da Microsoft Tech Community.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>O Intune é compatível com o iOS 11 e posteriores<!-- 4665324  -->

O registro e o Portal da Empresa do Intune agora são compatíveis com o iOS versão 11 e posteriores. Não há compatibilidade com as versões anteriores.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Linha de base do Microsoft Edge (versão prévia)<!--  3787164  -->

Adicionamos uma versão prévia para a linha de base de segurança das [configurações do Microsoft Edge](../protect/security-baseline-settings-edge.md). 

<!-- ########################## -->
## <a name="week-of-october-21-2019-1910-service-release"></a>Semana de 21 de outubro de 2019 (versão do serviço 1910)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Gerenciamento de dispositivos do Microsoft 365

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Experiência de administração aprimorada no Gerenciamento de dispositivos do Microsoft 365<!-- 5551239 -->

Uma experiência de administração atualizada e simplificada está disponível agora no Espaço de trabalho especializado de gerenciamento de dispositivos do Microsoft 365 em [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com), incluindo:

- **Navegação atualizada**: você encontrará uma navegação simplificada de 1º nível que agrupa logicamente os recursos.
- **Novos filtros de plataforma**: nas páginas Dispositivos e Aplicativos, você pode selecionar uma única plataforma que mostra apenas as políticas e os aplicativos da plataforma selecionada.
- **Uma nova página inicial**: veja rapidamente a integridade do serviço, o estado dos locatários, notícias etc. na nova página inicial.

Para obter mais informações sobre esses aprimoramentos, confira a [postagem no blog Enterprise Mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) no site da Microsoft Tech Community.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Adicionar aplicativos de Defesa contra Ameaças Móveis a dispositivos não registrados<!-- 3005337 -->
É possível criar uma política de proteção de aplicativo do Intune que pode bloquear ou apagar seletivamente os dados corporativos dos usuários com base na integridade do dispositivo. A integridade do dispositivo é determinada usando sua solução de MTD (Defesa contra Ameaças Móveis) escolhida. Esse recurso existe hoje com dispositivos registrados no Intune como uma configuração de conformidade do dispositivo. Com esse novo recurso, ampliamos a detecção de ameaças de um fornecedor de Defesa Contra Ameaças Móveis para funcionar em dispositivos não registrados. No Android, esse recurso exige a versão mais recente do Portal da Empresa no dispositivo. No iOS, esse recurso estará disponível para uso quando os aplicativos integrarem o SDK mais recente do Intune (versão 12.0.15 e superiores). Atualizaremos o tópico Novidades quando o primeiro aplicativo adotar o SDK mais recente do Intune. Os aplicativos restantes ficarão disponíveis de forma contínua. Para saber mais, confira [Criar uma política de proteção de aplicativo com a Defesa contra Ameaças Móveis com o Intune](~/protect/mtd-app-protection-policy.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Novo perfil da interface de configuração de firmware do dispositivo para dispositivos Windows 10 e posteriores (visualização pública)<!-- 2266073  -->

No Windows 10 e posterior, você pode criar um perfil de configuração do dispositivo para controlar configurações e recursos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma). Nesta atualização, há um novo tipo de perfil da interface de configuração de firmware do dispositivo que permite ao Intune gerenciar configurações da UEFI (BIOS).

Para obter mais informações sobre esse recurso, confira [Usar perfis da DFCI em dispositivos Windows no Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md).

Aplica-se a:

- Windows 10 RS5 (1809) e mais recentes em firmware com suporte

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Alterne para mostrar apenas a Página de Status do Registro em dispositivos provisionados pela OOBE (experiência de configuração inicial pelo usuário)<!--3959566-->
Agora você pode optar por mostrar apenas a Página de Status do Registro em dispositivos provisionados pelo OOBE do AutoPilot.

Para ver a nova alternância, escolha **Intune** > **Registro de dispositivo** > **Registro do Windows** > **Página de Status de Registro** > **Criar perfil** > **Configurações** > **Exibir somente a página para dispositivos provisionados pela OOBE (experiência de configuração inicial pelo usuário)** .


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>Semana de 14 de outubro de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos 

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Aplicativo do Google Play disponível gerando relatórios para perfis de trabalho do Android<!-- 3041956   -->
Para instalações de aplicativo disponíveis em dispositivos totalmente gerenciados, dedicados e de perfil de trabalho do Android Enterprise, você pode exibir o status de instalação do aplicativo, bem como a versão instalada de aplicativos gerenciados do Google Play. Para obter mais informações, veja [Como monitorar políticas de proteção de aplicativo](~/apps/app-protection-policies-monitor.md), [Gerenciar dispositivos de perfil de trabalho do Android com o Intune](~/enrollment/android-enterprise-overview.md) e [Tipo de aplicativo do Google Play gerenciado](~/apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Microsoft Edge versão 77 e posteriores para Windows 10 e macOS (versão prévia pública)<!-- 3872025, 4678761  -->
O Microsoft Edge versão 77 e posteriores estarão disponíveis para implantação em computadores que executam o Windows 10 e o macOS. 

A versão prévia pública oferece canais de **Desenvolvimento** e **Beta** para Windows 10 e um canal **Beta** para macOS. A implantação é apenas em inglês (EN); contudo, os usuários finais podem alterar o idioma de exibição no navegador em **Configurações** > **Idiomas**. O Microsoft Edge é um aplicativo Win32 instalado no contexto do sistema e em arquiteturas semelhantes (aplicativo x86 em sistema operacional x86 e aplicativo x64 em sistema operacional x64). Além disso, as atualizações automáticas do navegador são **Ativadas** por padrão e o Microsoft Edge não pode ser desinstalado. Para obter mais informações, confira [Adicionar o Microsoft Edge para Windows 10 ao Microsoft Intune](~/apps/apps-windows-edge.md) e a [Documentação do Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823).

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Atualizar para a interface do usuário de proteção do aplicativo e a interface do usuário de provisionamento de aplicativo iOS<!-- 4102027, 4102029   -->
A interface do usuário para criar e editar políticas de proteção de aplicativo e perfis de provisionamento de aplicativo do iOS no Intune foi atualizada. As alterações da interface do usuário incluem:
- Uma experiência simplificada usando um formato com estilo de assistente condensado dentro de uma folha. 
- Uma atualização do fluxo de criação a fim de incluir atribuições.
- Uma página resumida de todas as coisas definidas ao exibir as propriedades, antes de criar uma nova política ou ao editar uma propriedade. Além disso, ao editar propriedades, o resumo mostra apenas a lista de itens da categoria de propriedades em edição.

Para obter mais informações, confira [Como criar e atribuir políticas de proteção de aplicativo](~/apps/app-protection-policies.md) e [Usar perfis de provisionamento do aplicativo iOS](~/apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Cenários guiados do Intune<!-- 4850318, 4831296, 3610611  -->
O Intune agora fornece cenários orientados para ajudar você a concluir uma tarefa específica ou um conjunto de tarefas no Intune. Um cenário guiado é uma série personalizada de etapas (fluxo de trabalho) centradas em um caso de uso de ponta a ponta. Cenários comuns são definidos com base na função que um administrador, usuário ou dispositivo desempenha e sua organização. Esses fluxos de trabalho normalmente exigem uma coleção de perfis, configurações, aplicativos e controles de segurança cuidadosamente orquestrados para fornecer as melhores experiência do usuário e segurança. Os novos cenários guiados incluem:
- [Implantar o Microsoft Edge para dispositivos móveis](~/fundamentals/guided-scenarios-edge.md)
- [Microsoft Office seguro para aplicativos móveis](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Área de trabalho moderna gerenciada em nuvem](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Para obter mais informações, confira [Visão geral dos cenários do Intune](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Variável de configuração de aplicativos adicional disponível<!-- 4969237   -->
Ao criar uma política de configuração de aplicativos, você pode incluir a variável de configuração `AAD Device ID` como parte de suas definições de configuração. No Intune, selecione **Aplicativos de cliente** > **Políticas de configuração de aplicativo** > **Adicionar**. Insira os detalhes da política de configuração e selecione **Definições de configuração** para exibir a folha **Definições de configuração**. Para obter mais informações, confira [Políticas de configuração de aplicativos para dispositivos Android Enterprise gerenciados – Usar o designer de configuração](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>Criar grupos de objetos de gerenciamento chamados conjuntos de políticas<!-- 3762880  -->
Os conjuntos de políticas permitem que você crie um pacote de referências para entidades de gerenciamento já existentes que precisam ser identificadas, direcionadas e monitoradas como uma única unidade conceitual. Os conjuntos de políticas não substituem conceitos ou objetos existentes. Você pode continuar atribuindo objetos individuais no Intune e também pode referenciá-los como parte de um conjunto de políticas. Portanto, as alterações nesses objetos individuais serão refletidas no Conjunto de políticas.  No Intune, você selecionará **Conjuntos de políticas** > **Criar** para criar um novo Conjunto de políticas. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Atualização da interface do usuário para criar e editar Anéis de atualização do Windows 10<!-- 4099089         -->
Atualizamos a experiência da interface do usuário para [criar e editar Anéis de Atualização do Windows 10](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) para o Intune. As alterações na interface do usuário incluem:  
- Um formato com estilo de assistente condensado em uma única folha do console, que elimina a disposição da folha vista anteriormente quando você configurava os anéis de atualização.   
- O fluxo de trabalho revisado inclui Atribuições antes de concluir a configuração inicial do anel.
- Uma página de resumo que você pode usar para examinar todas as configurações feitas antes de salvar e implantar um novo anel de atualização. Ao editar um anel de atualização, o resumo mostra apenas a lista de itens definidos dentro da categoria de propriedades editada.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>Atualização da interface do usuário para criar e editar a política de atualização de software do iOS<!-- 4099090       --> 
Atualizamos a experiência da interface do usuário para [criar](../protect/software-updates-ios.md#configure-the-policy) e [editar](../protect/software-updates-ios.md#edit-a-policy) as políticas de atualização de software do iOS para o Intune.  As alterações na interface do usuário incluem:  
- Um formato com estilo de assistente condensado em uma única folha do console, que elimina a disposição da folha vista anteriormente quando você configurava as políticas de atualização.   
- O fluxo de trabalho revisado inclui Atribuições antes de concluir a configuração inicial da política.
- Uma página de resumo que você pode usar para examinar todas as configurações feitas antes de salvar e implantar uma nova política. Ao editar uma política, o resumo mostra apenas a lista de itens definidos dentro da categoria de propriedades editada.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404--------"></a>Configurações de reinício estabelecido foram removidas para os anéis do Windows Update<!--  4464404      -->
Conforme anunciado anteriormente, os anéis de atualização do Windows 10 do Intune agora [têm suporte para configurações de datas limite](../protect/windows-update-settings.md) e não têm mais suporte para o *Reinício estabelecido*. As configurações de *Reinício estabelecido* não estão mais disponíveis quando você configura ou gerencia anéis de atualização no Intune.  

Essa alteração se alinha com as recentes [alterações de serviço do Windows](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing) e, em dispositivos que executam o Windows 10 1903 ou posterior, os *prazos* substituem as configurações de *reinício estabelecido*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Impedir a instalação de aplicativos de fontes desconhecidas em dispositivos com perfil de trabalho Android Enterprise<!-- 4760025   -->
Em dispositivos Android Enterprise com perfil de trabalho, os usuários não podem instalar aplicativos de fontes desconhecidas. Nessa atualização, há uma nova configuração – **Impedir as instalações de aplicativos de fontes desconhecidas no perfil pessoal**. Por padrão, essa configuração impede que os usuários efetuam sideload de aplicativos de fontes desconhecidas no perfil pessoal do dispositivo.

Para ver a configuração que você pode definir, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md).

Aplica-se a:

- Perfil de trabalho do Android Enterprise

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Criar um proxy HTTP global em dispositivos do proprietário do dispositivo Android Enterprise<!-- 4816339   -->
Em dispositivos Android Enterprise, você pode configurar um proxy HTTP global para atender aos padrões de navegação na Web de sua organização (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Proprietário do dispositivo > Restrições do dispositivo** para o tipo de perfil > **Conectividade**). Uma vez configurado, todo o tráfego HTTP usará esse proxy.

Para configurar esse recurso e ver as configurações que você pode definir, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md).

Aplica-se a:

- Proprietário do dispositivo Android Enterprise

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>A configuração para conectar automaticamente foi removida nos perfis Wi-Fi no administrador do dispositivo Android e no Android Enterprise<!-- 5021055   -->
No administrador do dispositivo Android e em dispositivos Android Enterprise, você pode criar um perfil de Wi-Fi para definir configurações diferentes (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Administrador do dispositivo Android** ou **Android Enterprise** para a plataforma > **Wi-Fi** para o tipo de perfil). Nessa atualização, a configuração **Conectar automaticamente** foi removida, pois [não tem suporte do Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Caso use essa configuração em um perfil de Wi-Fi, talvez você tenha notado que **Conectar automaticamente** não funciona. Você não precisa realizar nenhuma ação, mas lembre-se de que essa configuração foi removida da interface do usuário do Intune.

Para ver as configurações atuais, acesse [Configurações de Wi-Fi do Android](../configuration/wi-fi-settings-android.md) ou [Configurações de Wi-Fi do Android Enterprise](../configuration/wi-fi-settings-android-enterprise.md).

Aplica-se a:

- Administrador do dispositivo Android 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Novas definições de configuração do dispositivo para dispositivos iOS e iPadOS supervisionados<!-- 5199328   -->
Em dispositivos iOS e iPadOS, você pode criar um perfil para restringir recursos e configurações em dispositivos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **Restrições do dispositivo** para o tipo de perfil). Nessa atualização, há novas configurações que você pode controlar: 
- Acesso à unidade de rede no aplicativo Arquivos  
- Acesso à unidade USB no aplicativo Arquivos 
- Wi-Fi sempre ativado 

Para ver essas configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md).

Aplica-se a:

- iOS 13.0 e mais recente
- iPadOS 13.0 e versões mais recentes

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Especificar quais versões do sistema operacional do dispositivo Android são registradas no perfil de trabalho ou no registro de administrador do dispositivo<!-- 4350697   -->
Usando as restrições de tipo de dispositivo do Intune, você pode usar a versão do sistema operacional do dispositivo para especificar quais dispositivos de usuário usarão o registro de perfil de trabalho do Android Enterprise ou o registro de administrador do dispositivo Android.  Para saber mais, confira [Definir restrições de registro](../enrollment/enrollment-restrictions-set.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Novas restrições para renomeação de dispositivos Windows<!-- 3478938  -->
Ao renomear um dispositivo Windows, você precisa seguir as novas regras:
- 15 caracteres ou menos (deve ser menor ou igual a 63 bytes, não incluindo NULL à direita)
- Não nulo ou uma cadeia de caracteres vazia
- ASCII permitidos: Letras (a-z, A-Z), números (0-9) e hifens
- Unicode permitidos: caracteres >= 0x80, deve ser UTF8 válido, deve ser mapeável para IDN (ou seja, RtlIdnToNameprepUnicode é bem-sucedido; confira RFC 3492)
- Os nomes não devem conter apenas números
- Sem espaços no nome
- Caracteres não permitidos: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)

 Para saber mais, confira [Renomear um dispositivo no Intune](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Novo relatório do Android na Página de visão geral dos dispositivos<!-- 4924364 -->
Um novo relatório para a Página de visão geral dos dispositivos exibe quantos dispositivos Android foram registrados em cada solução de gerenciamento de dispositivo. Este gráfico mostra as contagens de dispositivos com perfil de trabalho, totalmente gerenciados, dedicados e registrados pelo administrador do dispositivo. Para ver o relatório, escolha **Intune** > **Dispositivos** > **Visão geral**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>Certificados PKCS para macOS<!-- 1333650       -->
Agora, você pode [usar certificados PKCS com o macOS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). Você pode selecionar o certificado PKCS como um tipo de perfil para macOS e implantar certificados de usuário e de dispositivo que tenham [campos de entidade personalizada e nome alternativo da entidade](../protect/certficates-pfx-configure.md#subject-name-format).  

O certificado PKCS para macOS também dá suporte a uma nova configuração, _Permitir acesso de todos os aplicativos_. Com essa configuração, você pode habilitar o acesso de todos os aplicativos associados à chave privada do certificado.  Para obter mais informações sobre essa configuração, confira a documentação da Apple em https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>Credenciais derivadas para provisionar dispositivos móveis iOS com certificados<!--  1736036, 1736037, 1772050, 2777333         -->  
O Intune dá suporte ao uso de [credenciais derivadas](../protect/derived-credentials.md) como um método de autenticação e para assinatura S/MIME e criptografia para dispositivos iOS. As credenciais derivadas são uma implementação da norma *NIST (National Institute of Standards and Technology) 800-157* para a implantação de certificados em dispositivos.  

As credenciais derivadas dependem do uso de um cartão de PIV (Verificação de identidade pessoal) ou CAC (Cartão de acesso comum), como um cartão inteligente. Para obter uma credencial derivada para seu dispositivo móvel, os usuários começam no aplicativo Portal da Empresa e seguem um fluxo de trabalho de registro exclusivo para o provedor que você usa.  É comum a todos os provedores a necessidade de usar um cartão inteligente em um computador para se autenticar no provedor de credenciais derivadas. Esse provedor emite um certificado para o dispositivo que é derivado do cartão inteligente do usuário.  

O Intune dá suporte aos seguintes provedores de credenciais derivadas:
- DISA Purebred
- Entrust Datacard
- Intercede

Você usa credenciais derivadas como o método de autenticação para perfis de configuração de dispositivo para VPN, Wi-Fi e email. Você também pode usá-las para autenticação do aplicativo e autenticação e assinatura e criptografia S/MIME.  

Para obter mais informações sobre a norma, confira [Credenciais derivadas de PIV](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) em www.nccoe.nist.gov.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>Use a API do Graph para especificar um nome UPN local como uma variável para certificados SCEP<!--  5437939        -->  
Ao usar a [API do Graph do Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0), você pode especificar onPremisesUserPrincipalName como uma variável para o SAN (nome alternativo da entidade) para certificados SCEP.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Semana de 23 de setembro de 2019

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Registro de usuário do iOS em versão prévia<!-- 4817900 -->
O iOS versão 13.1 da Apple inclui o Registro de Usuário, uma nova forma de gerenciamento leve para dispositivos iOS. Ele pode ser usado no lugar do Registro de Dispositivo ou do Registro de Dispositivo Automatizado (antigamente chamado Programa de registro de dispositivos) para dispositivos de propriedade pessoal. A versão prévia do Intune dá suporte a esse conjunto de recursos, permitindo que você:

- Direcionar o Registro de Usuário para grupos de usuários.
- Dê aos usuários finais a capacidade de escolher entre o Registro de Usuário mais leve ou o Registro de Dispositivo mais forte quando eles registrarem seus dispositivos.

Desde 24/9/2019, com o lançamento do iOS 13.1, estamos no processo de distribuir essas atualizações para todos os clientes e esperamos que sejam concluídas até o final da próxima semana.

Aplica-se a:

- iOS 13.1 e posterior

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Suporte do Intune para dispositivos iPadOS e iOS 13.1<!--5439574-->
O Intune agora dá suporte ao gerenciamento de dispositivos iPadOS e iOS 13.1. Para obter mais informações, consulte [esta postagem do blog](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094).

<!-- ########################## -->

## <a name="week-of-september-16-2019-1909-service-release"></a>Semana de 16 de setembro de 2019 (versão do serviço 1909)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos 

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Aplicativos LOB particulares do Google Play Gerenciado<!-- 1464182  -->
Agora, o Intune permite que os administradores de TI publiquem aplicativos de LOB privados do Android no Google Play Gerenciado por meio de um iframe inserido no console do Intune.  Anteriormente, os administradores de TI precisavam publicar aplicativos LOB diretamente no console de publicação do Google Play, o que exigia várias etapas e consumia muito tempo. Esse novo recurso permite a fácil publicação de aplicativos LOB com um conjunto mínimo de etapas, sem a necessidade de sair do console do Intune.  Os administradores não precisarão mais se registrar manualmente como desenvolvedores no Google e não precisarão mais pagar o valor de registro de US$ 25 do Google.  Qualquer um dos cenários de gerenciamento do Android Enterprise que usam o Google Play Gerenciado pode aproveitar esse recurso (perfil de trabalho, dispositivos dedicados, totalmente gerenciados e não registrados). No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Em seguida, selecione **Google Play Gerenciado** na lista **Tipo de aplicativo**. Para saber mais sobre aplicativos do Google Play Gerenciado, confira [Adicionar aplicativos do Google Play Gerenciado a dispositivos Android Enterprise com o Intune](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Experiência do Portal da Empresa para Windows<!-- 1473353, 3598357 -->
O Portal da Empresa do Windows está sendo atualizado. Você poderá usar vários filtros na página Aplicativos no Portal da Empresa do Windows. A página Detalhes do Dispositivo também está sendo atualizada com uma experiência aprimorada do usuário. Estamos no processo de distribuir essas atualizações para todos os clientes e esperar que sejam concluídas até o final da próxima semana.

#### <a name="macos-support-for-web-apps---3174427---"></a>Suporte do macOS para aplicativos Web<!-- 3174427 -->
Os aplicativos Web, que permitem adicionar um atalho a uma URL na Web, podem ser instalados no Dock usando o Portal da Empresa do macOS. Os usuários finais podem acessar a ação **Instalar** na página de detalhes de um aplicativo Web no Portal da Empresa do macOS. Para obter mais informações sobre o tipo de aplicativo **Link da Web**, confira [Adicionar aplicativos ao Microsoft Intune](../apps/apps-add.md) e [Adicionar aplicativos Web ao Microsoft Intune](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps---3173501----"></a>Suporte do macOS para aplicativos VPP<!-- 3173501  -->
Os aplicativos do macOS, comprados usando o Apple Business Manager, são exibidos no console quando os tokens de VPP da Apple são sincronizados no Intune. Você pode atribuir, revogar e reatribuir licenças baseadas no usuário e no dispositivo para grupos usando o console do Intune. O Microsoft Intune ajuda a gerenciar aplicativos VPP adquiridos para uso em sua empresa ao proporcionar:

- Informações sobre licença de relatórios da app store.
- Acompanhamento de quantas licenças você usou.
- Ajuda para impedir a instalação de mais cópias do aplicativo além das que você já tem.

Saiba mais sobre o Intune e o VPP em [Gerenciar aplicativos e livros comprados por volume com o Microsoft Intune](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Suporte para iframe do Google Play Gerenciado<!-- 2871756  -->
O Intune agora dá suporte para adicionar e gerenciar links da Web diretamente no console do Intune por meio do iframe do Google Play Gerenciado.  Isso permite que os administradores de TI enviem um URL e um ícone gráfico e, em seguida, implantem esses links nos dispositivos, como os aplicativos Android comuns. Qualquer um dos cenários de gerenciamento do Android Enterprise que usam o Google Play Gerenciado pode aproveitar esse recurso (perfil de trabalho, dispositivos dedicados, totalmente gerenciados e não registrados). No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Em seguida, selecione **Google Play Gerenciado** na lista **Tipo de aplicativo**. Para saber mais sobre aplicativos do Google Play Gerenciado, confira [Adicionar aplicativos do Google Play Gerenciado a dispositivos Android Enterprise com o Intune](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>Instalar silenciosamente aplicativos de LOB do Android em dispositivos Zebra<!-- 4252734  -->
Ao instalar aplicativos de LOB (linha de negócios) do Android em [dispositivos Zebra](../configuration/android-zebra-mx-overview.md), em vez de ser solicitado a baixar e instalar o aplicativo LOB, você poderá instalar o aplicativo silenciosamente. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. No painel **Adicionar aplicativo**, selecione **Aplicativo de linha de negócios**. Para saber mais, confira [Adicionar um aplicativo de linha de negócios do Android ao Microsoft Intune](../apps/lob-apps-android.md).

Atualmente, após o download do aplicativo de LOB, uma notificação de **êxito no download** será exibida no dispositivo do usuário. A notificação só pode ser descartada tocando em **Limpar Tudo** na aba de notificações. Esse problema de notificação será corrigido em uma próxima versão e a instalação será completamente silenciosa, sem indicadores visuais.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Ler e gravar operações da API do Graph para aplicativos Intune<!-- 5031704  -->
Os aplicativos podem chamar a API do Intune Graph com operações de leitura e gravação usando a identidade do aplicativo sem credenciais do usuário. Para saber mais sobre como acessar a API do Microsoft Graph para Intune, confira [Como trabalhar com o Intune no Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>Compartilhamento e criptografia de dados protegidos para o SDK de Aplicativo do Intune para iOS<!-- 3586942  -->
O SDK de Aplicativo do Intune para iOS usa as chaves de criptografia de 256 bits quando a criptografia é habilitada por Políticas de Proteção de Aplicativo. Todos os aplicativos precisarão ter um SDK versão 8.1.1 para permitir o compartilhamento de dados protegidos.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>Suporte para perfis de VPN IKEv2 para iOS<!-- 1943438   -->
Nessa atualização, você poderá criar perfis VPN para o cliente VPN nativo do iOS usando o protocolo IKEv2. IKEv2 é um novo tipo de conexão em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **VPN** para tipo de perfil > **Tipo de conexão**.

Esses perfis de VPN configuram o cliente VPN nativo, portanto, nenhum aplicativo cliente VPN é instalado ou enviado para dispositivos gerenciados. Esse recurso exige que dispositivos sejam registrados no Intune (registro do MDM).

Para ver as configurações de VPN atuais que você pode configurar, vá para [Definir configurações de VPN em dispositivos iOS](../configuration/vpn-settings-ios.md).

Aplica-se a:

- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>Recursos do dispositivo, restrições do dispositivo e perfis de extensão para configurações do iOS e macOS são mostrados por tipo de registro<!-- 4886161   -->

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

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Novas configurações de controle de voz para dispositivos iOS supervisionados em execução no modo quiosque<!-- 4892835   -->
No Intune, você pode criar políticas para executar dispositivos iOS supervisionados como um quiosque ou dispositivo dedicado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **Restrições de dispositivo** para tipo de perfil > **Quiosque**).

Nessa atualização, há novas configurações que você pode controlar:
- **Controle de voz**: Habilita o controle de voz no dispositivo no modo de quiosque.
- **Modificação do controle de voz**: Permite que os usuários alterem a configuração do Controle de Voz no dispositivo enquanto estão no modo de quiosque.

Para ver as configurações atuais, acesse [Configurações do quiosque do iOS](../configuration/device-restrictions-ios.md#kiosk).

Aplica-se a:

- iOS 13.0 e posterior

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>Usar o logon único para aplicativos e sites em dispositivos iOS e macOS<!-- 4893175   -->
Nesta atualização, há algumas novas configurações de logon único para dispositivos iOS e macOS (**Configuração de dispositivo** > **Perfis** > **Criar perfil** > **iOS** ou **macOS** para plataforma > **Recursos de dispositivo** para tipo de perfil).

Use essas configurações para configurar uma experiência de logon único, especialmente para aplicativos e sites que usam autenticação Kerberos. Você pode optar por uma extensão de aplicativo de logon único com credencial genérica ou pela extensão Kerberos interna da Apple.

Para ver os recursos atuais do dispositivo que você pode configurar, acesse [Recursos do dispositivo iOS](../configuration/ios-device-features-settings.md) e [Recursos do dispositivo macOS](../configuration/macos-device-features-settings.md).

Aplica-se a:

- iOS 13.0 e mais recente
- macOS 10.15 e mais recente

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>Associar domínios a aplicativos em dispositivos macOS 10.15 ou superiores<!-- 4898079   -->
Nos dispositivos macOS, você pode configurar recursos diferentes e enviá-los aos dispositivos usando uma política (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para plataforma > **Recursos do dispositivo** para tipo de perfil). Nessa atualização, você pode associar domínios a seus aplicativos. Esse recurso ajuda a compartilhar credenciais com sites relacionados ao seu aplicativo e pode ser usado com a extensão de logon único da Apple, links universais e preenchimento automático de senha. 

Para ver os recursos atuais que você pode configurar, acesse [Configurações de recursos de dispositivo macOS no Intune](../configuration/macos-device-features-settings.md).

Aplica-se a:

- macOS 10.15 e mais recente

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>Use "iTunes" e "aplicativos" na URL da loja de aplicativos do iTunes ao mostrar ou ocultar aplicativos em dispositivos supervisionados do iOS<!-- 4928474   --> 
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

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Interface do usuário atualizada para configurar o acesso local ao Microsoft Exchange<!-- 4092920 -->  
Atualizamos o console no qual você [configura o acesso local ao Microsoft Exchange](../protect/conditional-access-exchange-create.md). Todas as configurações para acesso local ao Exchange agora estão disponíveis no mesmo painel do console em que você *Habilita o controle de acesso local do Exchange*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Permitir ou restringir a adição de widgets de aplicativos à tela inicial nos dispositivos de perfil profissional do Android Enterprise<!-- 1109650  --> 
Nos dispositivos Android Enterprise, você pode configurar recursos no perfil de trabalho (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Apenas perfil de trabalho > Restrições de dispositivo** para tipo de perfil). Nessa atualização, você pode permitir que os usuários adicionem widgets expostos por aplicativos de perfil profissional à tela inicial do dispositivo.

Para ver as configurações que você pode definir, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md).

Aplica-se a:
- Perfil de trabalho do Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Os novos locatários terão como padrão o gerenciamento de administradores de dispositivos Android<!-- 4869790   -->
Os recursos de administrador de dispositivos do Android foram substituídos pelo Android Enterprise. Portanto, recomendamos o uso do Android Enterprise para novos registros. Em uma atualização futura, novos locatários precisarão concluir as seguintes etapas de pré-requisito na inscrição do Android para usar o gerenciamento de administrador de dispositivos: Acesse **Intune** > **Registro de dispositivo** > **Registro do Android** > **Dispositivos pessoais e corporativos com privilégios de administração de dispositivos** > **Usar o administrador do dispositivo para gerenciar dispositivos**.

Os locatários existentes não sofrerão alteração em seus ambientes.

Para saber mais sobre o administrador do dispositivo Android no Intune, confira [Registro do administrador do dispositivo Android](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045-idmiss---"></a>Lista de dispositivos DEP associados a um perfil<!-- 5012045 idmiss -->
Agora você pode ver uma lista paginada de dispositivos DEP (Programa de Registro de Dispositivos) Automatizados da Apple associados a um perfil. Você pode pesquisar a lista a partir de qualquer página da lista. Para ver a lista, acesse **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Dispositivos atribuídos** (em **Monitor**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Mais suporte para Android totalmente gerenciado<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
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

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Enviar notificações para um único dispositivo<!-- 4928910 -->
Agora você pode selecionar um único dispositivo e, em seguida, usar uma ação de dispositivo remoto para [enviar uma notificação personalizada apenas para esse dispositivo](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>As ações Apagar e Redefinição de Senha não estão disponíveis para dispositivos iOS registrados usando Registro de Usuário<!-- 4950491 -->
O Registro de Usuário é um novo tipo de registro do dispositivo Apple. Quando você registra dispositivos usando o Registro do Usuário, as ações remotas Apagar e Redefinição de Senha não estarão disponíveis para esses dispositivos.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>Suporte do Intune para dispositivos iOS 13 e macOS Catalina<!-- 4665317 -->
O Intune agora dá suporte ao gerenciamento de dispositivos iOS 13 e macOS Catalina.
Para saber mais, confira a [Postagem no blog Suporte do Microsoft Intune para iOS 13 e iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>Suporte do BitLocker para rotação de senha de recuperação orientada ao cliente<!--  3444125 -->
Use as configurações do Intune Endpoint Protection para configurar a [Rotação da senha de recuperação orientada ao cliente](../protect/endpoint-protection-windows-10.md#windows-encryption) para o BitLocker em dispositivos que executam o Windows versão 1909 ou posterior.

Essa configuração inicia uma atualização de senha de recuperação orientada a cliente após uma recuperação de unidade do SO (usando bootmgr ou WinRE) e desbloqueio de senha de recuperação em uma unidade de dados fixa. Essa configuração atualiza a senha de recuperação específica usada e outras senhas não utilizadas no volume permanecem inalteradas. Para saber mais, confira a documentação do BitLocker CSP para [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Proteção contra Adulterações para o Windows Defender Antivírus<!-- 4705448        -->
Use o Intune para gerenciar a *Proteção contra Adulterações* para o Windows Defender Antivírus. Você encontrará a configuração para [Proteção contra Adulterações](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) no grupo Microsoft Defender Security Center ao usar perfis de configuração de dispositivo para a proteção de ponto de extremidade do Windows 10. Você pode definir a Proteção contra Adulterações para *Habilitada* para ativar as restrições de proteção contra adulterações, definir *Desabilitada* para desativá-las ou definir *Não Configurada* para deixar a configuração atual de dispositivos em vigor.  

Para saber mais sobre a proteção contra adulterações, confira [Impedir alterações nas configurações de segurança com proteção contra adulterações](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) na documentação do Windows.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>As configurações avançadas do Windows Defender Firewall agora estão disponíveis em geral<!--  5317392       -->  
As [regras de firewall personalizadas do Windows Defender para proteção de ponto de extremidade](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), configuradas como parte de um perfil de configuração de dispositivo, não estão mais em versão prévia pública, mas em versão disponível em geral (GA).  Você pode usar as regras para especificar o comportamento de entrada e saída para aplicativos, endereços de rede e portas. Essas regras foram publicadas em julho como uma versão prévia pública. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Controle de acesso baseado em funções

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863-idmiss---"></a>As marcas de escopo agora dão suporte a políticas dos Termos de Uso<!-- 2358863 idmiss -->
Agora você pode atribuir [marcas de escopo](scope-tags.md) às políticas dos Termos de Uso. Para fazer isso, acesse **Intune** > **Registro do dispositivo** > **Termos e condições** > escolha um item na lista > **Propriedades** > **Marcas de escopo** > escolha uma marca de escopo.

## <a name="week-of-september-9-2019"></a>Semana de 9 de setembro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Atualizações do aplicativo Microsoft Intune<!-- 4997846 -->
O aplicativo Microsoft Intune para Android foi atualizado com as seguintes melhorias:
- Layout atualizado e aprimorado para incluir a navegação inferior para as ações mais importantes.
- Página adicional incluída que mostra o perfil do usuário.
- Adicionada ao aplicativo a exibição de notificações acionáveis, como a necessidade de atualizar as configurações de dispositivo.
- Adicionada a exibição de notificações push personalizadas, alinhando o aplicativo ao suporte recentemente adicionado nos aplicativos do Portal da Empresa para iOS e Android. Para saber mais, confira [Enviar notificações personalizadas no Microsoft Intune](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>Para dispositivos iOS, personalize a tela de privacidade do processo de registro do Portal da Empresa<!-- 4394993 -->
Com o Markdown, você pode personalizar a tela de privacidade do Portal da Empresa que os usuários finais exibem durante o registro do iOS. Especificamente, você poderá personalizar a lista daquilo que sua organização não pode ver ou fazer no dispositivo. Para saber mais, confira [Como configurar o aplicativo do Portal da Empresa do Intune](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>Semana de 2 de setembro de 2019

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Atualização da interface do usuário do Intune – Painel de Status do Locatário<!-- 5273210  -->
A interface do usuário para o painel de Status do Locatário foi atualizada para alinhar-se aos estilos de interface do usuário do Azure. Para obter mais informações, veja [Status do locatário](../tenant-status.md).

## <a name="week-of-august-26-2019"></a>Semana de 26 de agosto de 2019

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Definir as configurações do Microsoft Edge usando modelos administrativos para o Windows 10 e mais recente<!-- 5228061 -->

Em dispositivos Windows 10 e mais recente, você pode criar modelos administrativos para definir as configurações da política de grupo no Intune. Nesta atualização, você pode definir as configurações que se aplicam ao Microsoft Edge versão 77 e mais recente.

Para saber mais sobre modelos administrativos, confira [Usar modelos do Windows 10 para definir as configurações da política de grupo no Intune](../configuration/administrative-templates-windows.md).

Aplica-se a:

- Windows 10 e mais recente (Windows RS4 e posterior)

## <a name="week-of-august-12-2019-1908-service-release"></a>Semana de 12 de agosto de 2019 (versão do serviço 1908)

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Controlar o comportamento de desinstalação do aplicativo iOS no cancelamento de registro do dispositivo<!-- 3504144   -->
Os administradores podem determinar se um aplicativo é removido ou mantido em um dispositivo, quando o registro do dispositivo é cancelado no nível do usuário ou do grupo de dispositivos. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Categorizar aplicativos da Microsoft Store para Empresas<!-- 3926922 -->
É possível categorizar aplicativos da Microsoft Store para Empresas. Para fazer isso, escolha **Intune** > **Aplicativos cliente** > **Aplicativos** > Selecione um aplicativo da Microsoft Store para Empresas > **Informações do aplicativo** > **Categoria**. Atribua uma categoria no menu suspenso.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Notificações personalizadas para usuários do aplicativo Microsoft Intune<!-- 4843354  -->
O aplicativo Microsoft Intune para Android agora tem suporte para exibição de notificações push personalizadas, além do suporte recentemente adicionado nos aplicativos do Portal da Empresa para iOS e Android. Para saber mais, confira [Enviar notificações personalizadas no Microsoft Intune](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Novos recursos para dispositivos dedicados Android Enterprise no modo de vários aplicativos<!-- 3755304 3041943 3041946   -->

No Microsoft Intune, você pode controlar recursos e configurações em uma experiência estilo quiosque nos dispositivos dedicados Android Enterprise (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Somente Proprietário do Dispositivo, Restrições do dispositivo** para tipo de perfil).

Os seguintes recursos foram adicionados nesta atualização:

- **Dispositivos dedicados** > **Vários aplicativos**: o **botão Página Inicial virtual** pode ser exibido passando o dedo para cima no dispositivo ou pode estar flutuante na tela para que os usuários possam movê-lo.
- **Dispositivos dedicados** > **Vários aplicativos**: **Acesso à lanterna** permite aos usuários utilizar a lanterna. 
- **Dispositivos dedicados** > **Vários aplicativos**: **Controle de volume de mídia** permite aos usuários controlar o volume de mídia do dispositivo por meio de um controle deslizante. 
- **Dispositivos dedicados** > **Vários aplicativos**:  **Habilitar um protetor de tela**, carregar uma imagem personalizada e controlar quando o protetor de tela é exibido.

Veja as configurações atuais acessando [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Aplica-se a:

- Dispositivos Android Enterprise dedicados

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Novos perfis de configuração e de aplicativos para dispositivos Android Enterprise totalmente gerenciados<!-- 3574215 3574238 3574235 3574232   -->
Com os perfis, você pode definir configurações que apliquem configurações de VPN, email e Wi-Fi aos dispositivos Android Enterprise (totalmente gerenciados) do proprietário do dispositivo. Nesta atualização, é possível:

- Usar [políticas de configuração de aplicativos](../apps/app-configuration-policies-use-android.md) para implantar configurações de email das plataformas Outlook, Gmail e Nine Work.
- Usar perfis de configuração de dispositivos para implantar [configurações de certificado raiz confiável](../protect/certificates-configure.md).
- Usar perfis de configuração de dispositivos para implantar configurações de [VPN](../configuration/vpn-settings-android-enterprise.md) e [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

> [!IMPORTANT]
> Com esse recurso, os usuários se autenticam com nome de usuário e senha em perfis de VPN, Wi-Fi e email. No momento, não há disponibilidade para autenticação baseada em certificado.

Aplica-se a:  
- Proprietário do dispositivo Android Enterprise (totalmente gerenciado)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>Controlar aplicativos, arquivos, documentos e pastas exibidos quando os usuários entram em dispositivos macOS<!--3914202   -->
Você pode habilitar e configurar recursos em dispositivos macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). 

Nesta atualização, há uma nova configuração de Itens de Logon para controlar quais aplicativos, arquivos, documentos e pastas são abertos quando um usuário entra no dispositivo registrado. 

Veja as configurações atuais acessando [Configurações de recurso de dispositivo macOS no Intune](../configuration/macos-device-features-settings.md).

Aplica-se a:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Prazos finais substituem configurações de Reinício estabelecido para anéis de atualização do Windows<!-- 4464404        -->
Para se alinhar às recentes [alterações de manutenção do Windows](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing), os anéis de atualização do Windows 10 do Microsoft Intune agora têm [suporte para configurações de prazos finais](../protect/windows-update-settings.md). Os *prazos finais* determinam quando um dispositivo instala atualizações de recursos e de segurança.  Em dispositivos com Windows 10 1903 ou posterior, os *prazos finais* substituem as configurações de *Reinício estabelecido*.  Futuramente, os *s prazos finais* também substituirão o *Reinício estabelecido* em versões anteriores do Windows 10.  

Quando você não configura *prazos finais*, os dispositivos continuam usando as respectivas configurações de *Reinício estabelecido*. No entanto, o Microsoft Intune removerá o suporte dessas configurações em uma próxima atualização.  

Planeje o uso de *prazos finais* para todos os dispositivos Windows 10. Após aplicar as configurações de *prazos finais*, você poderá alterar as configurações do Intune para que o *Reinício estabelecido* fique Não configurado. Quando definido como Não configurado, o Intune deixa de gerenciar essas configurações nos dispositivos, mas não remove as últimas definições da configuração do dispositivo. Portanto, as últimas configurações que foram definidas para o *Reinício estabelecido* permanecerão ativas e em uso nos dispositivos até que essas configurações sejam modificadas por um método diferente do Intune. Posteriormente, quando a versão do Windows dos dispositivos for alterada ou quando o suporte do Intune para *prazos finais* for estendido para a versão do Windows dos dispositivos, o dispositivo começará a usar as novas configurações que já estarão em vigor.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Suporte para vários Microsoft Intune Certificate Connectors<!--   4704642      -->
Agora, o Microsoft Intune tem suporte para instalação e uso de vários [Microsoft Intune Certificate Connectors para operações PKCS](../protect/certficates-pfx-configure.md). Essa alteração é compatível com o balanceamento de carga e a alta disponibilidade do conector. Cada instância de conector pode processar solicitações de certificado do Intune.  Quando um conector não está disponível, outros conectores continuam a processar solicitações.

Para usar vários conectores, não é necessário atualizar para a versão mais recente do software de conector.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>Novas configurações e alterações em configurações existentes para restringir recursos em dispositivos iOS e macOS<!-- 4867699 4867709   -->
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

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Algumas restrições do dispositivo iOS não supervisionadas passarão a ser somente supervisionadas após o lançamento do iOS 13.0<!-- 4867809   -->
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

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>Status aprimorado do dispositivo para criptografia do FileVault no macOS<!-- 4944983         -->
Atualizamos várias das [mensagens de status do dispositivo](../protect/encryption-monitor.md#device-encryption-status) para a criptografia do FileVault em dispositivos macOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Algumas configurações do Windows Defender Antivírus mostram o status "Com falha" no relatório<!-- 5119229 -->
No Microsoft Intune, você pode criar políticas para usar o Windows Defender Antivírus a fim de verificar seus dispositivos Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Restrições do dispositivo** para o tipo de perfil > **Windows Defender Antivírus**). Os relatórios **Hora para executar uma verificação rápida diária** e **Tipo de verificação do sistema a executar** mostram um status de falha, quando na verdade é um status de êxito. 

Corrigimos esse comportamento nesta atualização. Portanto, as configurações **Hora para executar uma verificação rápida diária** e **Tipo de verificação do sistema a executar** mostram um status de êxito quando as verificações são concluídas com êxito e mostram um status de falha quando ocorre falha na aplicação dessas configurações.

Para obter mais informações sobre as configurações do Windows Defender Antivírus, confira [Configurações de dispositivo Windows 10 (e mais recente) para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="default-scope-tags---3702875----"></a>Marcas de escopo padrão<!-- 3702875  -->
Já está disponível uma nova marca de escopo padrão interna. Todos os objetos sem marca do Intune compatíveis com marcas de escopo receberão automaticamente a marca de escopo padrão. A marca de escopo **padrão** é adicionada a todas as atribuições de função existentes para manter a paridade com a experiência de administrador atual. Se você prefere que um administrador não veja objetos do Intune com a marca de escopo padrão, remova essa marca da atribuição de função. Esse recurso é semelhante ao recurso Escopos de Segurança do Configuration Manager. Para saber mais, confira [Usar o RBAC e marcas de escopo na TI distribuída](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Suporte para registro de administrador de dispositivo Android<!-- 4869749   -->
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

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Adicionar uma coluna de usuário ao processo de upload de arquivos CSV em dispositivos do Autopilot<!-- 3823054 -->
Agora, é possível adicionar uma coluna de usuário ao upload de arquivos CSV em dispositivos do Autopilot. Dessa forma, você pode atribuir usuários em massa ao importar o CSV. Para obter mais informações, confira [Registrar dispositivos Windows no Intune usando o Windows Autopilot](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>Configurar o limite de tempo de limpeza automática do dispositivo para 30 dias<!--4231059  -->
É possível definir o limite de tempo de limpeza automática do dispositivo para até 30 dias (em vez do limite anterior de 90 dias) após o último logon. Para fazer isso, vá até **Intune** > **Dispositivos** > **Configuração** > **Regras de Limpeza do Dispositivo**.

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Número de build incluído na página Hardware do dispositivo Android<!-- 4461910   -->
Há uma nova entrada na página Hardware para cada dispositivo Android inclui o número de build do sistema operacional do dispositivo. Para obter mais informações, confira [Exibir detalhes do dispositivo no Intune](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Semana de 5 de agosto de 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>A Zebra Technologies é um OEM com suporte para OEMConfig em dispositivos Android Enterprise<!-- 4843713 -->

No Intune, você pode criar perfis de configuração de dispositivo e aplicar as configurações a dispositivos Android Enterprise usando o OEMConfig (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **OEMConfig** para o tipo de perfil).

Nesta atualização, a Zebra Technologies é um OEM (fabricante de equipamento original) com suporte para OEMConfig. Para saber mais sobre o OEMConfig, confira [Usar e gerenciar dispositivos Android Enterprise com o OEMConfig](../configuration/android-oem-configuration-overview.md).

Aplica-se a:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019-1907-service-release"></a>Semana de 22 de julho de 2019 (versão do serviço 1907)

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Notificações personalizadas para usuários e grupos<!-- 16766574          -->
Envie notificações por push personalizadas do aplicativo Portal da Empresa para os usuários em dispositivos Android e iOS que você gerencia com o Intune. Essas notificações por push móveis são altamente personalizáveis com texto livre e podem ser usadas para qualquer finalidade. Você pode direcioná-las para grupos de usuários diferentes em sua organização. Para saber mais, confira [Notificações personalizadas](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app---3041950----"></a>Aplicativo do Controlador de Política de Dispositivo do Google<!-- 3041950  -->
O aplicativo Tela Inicial Gerenciada agora fornece acesso ao aplicativo Política do Dispositivo Android do Google. O aplicativo Tela Inicial Gerenciada é um inicializador personalizado usado para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) que usam o modo de quiosque de vários aplicativos. Você pode acessar o aplicativo Política do Dispositivo Android ou orientar os usuários ao aplicativo Política do Dispositivo Android, para fins de suporte e de depuração. Essa capacidade de inicialização está disponível no momento em que o dispositivo é registrado e bloqueado na Tela Inicial Gerenciada. Nenhuma instalação adicional é necessária para usar essa funcionalidade.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>Configurações de proteção do Outlook para dispositivos iOS e Android<!-- 3212619 -->
Agora, você pode definir as configurações gerais e de proteção de dados do aplicativo do Outlook para iOS e do Android usando simples controles de administrador do Intune sem registro de dispositivo. As configurações gerais do aplicativo fornecem paridade com as configurações que os administradores podem habilitar ao gerenciar o Outlook para iOS e Android em dispositivos registrados. Para saber mais sobre as configurações do Outlook, confira [Implantar definições de configurações de aplicativos do Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready------"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 eeready    -->

Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma > **Regras de aplicabilidade**). Nesta atualização, você pode criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Para adicionar uma regra de aplicabilidade, confira [Regras de aplicabilidade](../configuration/device-profile-create.md#applicability-rules).

Aplica-se a: Windows 10 e posterior

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>Usar tokens para adicionar informações específicas do dispositivo em perfis personalizados para dispositivos iOS e macOS<!-- 3330008  -->
Você pode usar perfis personalizados em dispositivos iOS e macOS para definir configurações e recursos que não são internos no Intune (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** ou **macOS** para plataforma > **Personalizado** para o tipo de perfil). Nessa atualização, você pode adicionar tokens aos seus arquivos `.mobileconfig` para adicionar informações específicas do dispositivo. Por exemplo, você pode adicionar `Serial Number: {{serialnumber}}` ao seu arquivo de configuração para mostrar o número de série do dispositivo.

Para criar um perfil personalizado, confira [Configurações personalizadas do iOS](../configuration/custom-settings-ios.md) ou [Configurações personalizadas do macOS](../configuration/custom-settings-macos.md).

Aplica-se a:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Novo designer de configuração ao criar um perfil de OEMConfig para Android Enterprise<!-- 3712769   -->
No Intune, você pode criar um perfil de configuração de dispositivo que usa um aplicativo OEMConfig (Configuração de dispositivo > Perfis > Criar perfil > Android Enterprise para plataforma > OEMConfig para o tipo de perfil). Quando você fizer isso, um editor de JSON é aberto com um modelo e valores para que você altere. 

Essa atualização inclui um Designer de configuração com uma experiência de usuário aprimorada que mostra detalhes inseridos no aplicativo, incluindo títulos, descrições e muito mais. O editor de JSON ainda está disponível e mostra todas as alterações feitas no Designer de configuração.

Para ver as configurações atuais, vá para [Usar e gerenciar dispositivos Android Enterprise com o OEMConfig](../configuration/android-oem-configuration-overview.md).

Aplica-se a: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Interface do usuário atualizada para configurar o Windows Hello<!-- 4089576            -->
Atualizamos o console onde você vai [Configurar o Intune para usar o Windows Hello para empresas](../protect/windows-hello.md). Agora, todas as definições de configuração estão disponíveis no mesmo painel do console em que você habilita o suporte para o Windows Hello.

#### <a name="intune-powershell-sdk---4924113---"></a>SDK do Intune PowerShell<!-- 4924113 --> 
O SDK do Intune PowerShell, compatível com a API do Intune no Microsoft Graph, foi atualizado para a versão 6.1907.1.0. O SDK agora é compatível com o seguinte:
- Funciona com a Automação do Azure.
- Compatível com as operações de leitura de autenticação somente de aplicativo. 
- Compatível com nomes abreviados amigáveis como aliases.
- Em conformidade com as convenções de nomenclatura do PowerShell. Especificamente, o parâmetro `PSCredential` (no cmdlet `Connect-MSGraph`) foi renomeado para `Credential`.
- Compatível com a especificação manual do valor do cabeçalho `Content-Type` ao usar o cmdlet `Invoke-MSGraphRequest`.

Para saber mais, confira [SDK do PowerShell para API do Graph do Microsoft Intune](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Atualizações para restrições de registro<!-- 2871968 -->
As restrições de registro para novos locatários foram atualizadas para que os perfis de trabalho do Android Enterprise sejam permitidos por padrão. Os locatários existentes não sofrerão alteração. Para usar perfis de trabalho do Android Enterprise, você ainda precisa [conectar sua conta do Intune à sua conta do Google Play Gerenciado](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>Atualizações de interface do usuário para registro da Apple e restrições de registro<!--4089575, 4089579  -->
Os processos a seguir usam uma interface do usuário de estilo assistente:
- Registro do dispositivo da Apple. Para saber mais, veja [Registrar automaticamente dispositivos iOS com o Programa de registro de dispositivos da Apple](../enrollment/device-enrollment-program-enroll-ios.md).
- Criação de restrição de registro. Para saber mais, confira [Definir restrições de registro](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509--idmiss---"></a>Manipular a pré-configuração de identificadores de dispositivos corporativos para dispositivos Android Q<!-- 4711509  idmiss -->
No Android Q (V10), a Google removerá a capacidade de agentes de MDM em dispositivos Android gerenciados por legado (administrador do dispositivo) para coletar informações de identificador de dispositivo.  O Intune tem um recurso que permite que os administradores de TI [configurem previamente uma lista de números de série de dispositivos ou IMEIs](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) para marcar automaticamente esses dispositivos como corporativos. Esse recurso não funcionará para dispositivos Android Q gerenciados pelo administrador.  Independentemente do número de série ou IMEI do dispositivo ser carregado, ele sempre será considerado pessoal durante o registro no Intune.  Você pode alternar manualmente a propriedade para corporativo após o registro.  Isso afeta apenas os novos registros e os dispositivos registrados existentes não são afetados.  Os dispositivos Android gerenciados com perfis de trabalho não são afetados por essa alteração e continuarão a funcionar normalmente.  Além disso, os dispositivos Android Q registrados como administrador do dispositivo não poderão mais informar o número de série ou IMEI no console do Intune como propriedades do dispositivo.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Os ícones foram alterados para registros do Android Enterprise (perfil de trabalho, dispositivos dedicados e dispositivos totalmente gerenciados)<!-- 4977730 -->
Os ícones para perfis de registro do Android Enterprise foram alterados. Para ver os novos ícones, vá para **Intune** > **Registro** > **Registro do Android** > procure em **Perfis de registro**.


#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Alteração de coleta de Dados de Diagnóstico do Windows<!-- 4113859 -->
O valor padrão para coleta de dados de diagnóstico foi alterado para dispositivos que executam o Windows 10, versão 1903 e posteriores. A partir do Windows 10 1903, a coleta de dados de diagnóstico está habilitada por padrão. Os dados de diagnóstico do Windows são dados técnicos vitais de dispositivos Windows sobre o dispositivo e como o Windows e o software relacionado estão sendo executados. Para saber mais, veja [Configurar dados de diagnóstico do Windows em sua organização](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Os dispositivos de piloto automático também são aceitos na telemetria "Completa", a menos que definido de outra forma no perfil do AutoPilot com [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="improve-device-location---3855417----"></a>Melhorar a localização do dispositivo<!-- 3855417  -->
Você pode ampliar as coordenadas exatas de um dispositivo usando a ação **Localizar dispositivo**. Para saber mais sobre como localizar dispositivos iOS perdidos, confira [Localizar dispositivos iOS perdidos](../remote-actions/device-locate.md).

### <a name="device-security"></a>Segurança de dispositivo

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Configurações avançadas do Windows Defender Firewall (versão prévia pública)<!--  1311949     -->  
Use o Intune para gerenciar [regras de firewall personalizadas como parte de um perfil de configuração de dispositivo](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) para proteção de ponto de extremidade no Windows 10. As regras poderão especificar o comportamento de entrada e saída para aplicativos, endereços de rede e portas. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Interface do usuário atualizada para gerenciar linhas de base de segurança<!-- 4091125     -->
Atualizamos a [experiência de criação e edição](../protect/security-baselines.md#create-the-profile) no console do Intune para nossas linhas de base de segurança. Alterações incluem:

Um formato de estilo de assistente mais simples, que foi condensado para uma única folha. dentro de uma folha. Esse novo design elimina a expansão da folha que exige que os profissionais de TI percorram vários painéis separados.  
Agora, você pode criar Atribuições como parte da experiência de criação e edição, em vez de ter que retornar posteriormente para atribuir linhas de base. Adicionamos um resumo das configurações que você pode exibir antes de criar uma nova linha de base e ao editar uma existente. Ao editar, o resumo mostra apenas a lista de itens definidos na categoria de propriedades em edição.

<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Semana de 15 de julho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Ícones de Configurações Gerenciadas e Tela Inicial Gerenciada<!-- 4918107 -->
O ícone do aplicativo de Tela Inicial Gerenciada e o ícone de **Configurações Gerenciadas** foram atualizados. O aplicativo Tela Inicial Gerenciada é usado apenas para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) e executando o modo de quiosque em vários aplicativos. Para saber mais sobre o aplicativo de Tela Inicial Gerenciada, confira [Configurar o aplicativo de Tela Inicial Gerenciada da Microsoft para Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Política de dispositivo Android em dispositivos Android Enterprise dedicados<!-- 4918136 -->
Você pode acessar o aplicativo de Política de dispositivo Android na tela de depuração do aplicativo de Tela Inicial Gerenciada. O aplicativo Tela Inicial Gerenciada é usado apenas para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) e executando o modo de quiosque em vários aplicativos. Para saber mais, confira [Configurar o aplicativo de Tela Inicial Gerenciada da Microsoft para o Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates---3902931---"></a>Atualizações do Portal da Empresa para iOS<!-- 3902931 -->
O nome da sua empresa nos prompts de gerenciamento de aplicativo iOS substituirá o texto "i.manage.microsoft.com" atual. Por exemplo, os usuários verão o nome da empresa em vez de "i.manage.microsoft.com" quando os usuários tentarem instalar um aplicativo iOS do Portal da Empresa ou quando os usuários permitirem o gerenciamento do aplicativo. Isso será distribuído para todos os clientes durante os próximos dias.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>Gerenciar FileVault para macOS<!--  3858502 + 4557986 + 1210104  -->
Você pode usar o Intune para [gerenciar a criptografia de chave FileVault para dispositivos macOS](../protect/encrypt-devices.md). Para criptografar dispositivos, use um perfil de configuração de dispositivo do Endpoint Protection.

Nosso suporte para FileVault inclui criptografia de dispositivos não criptografados, caução de uma chave de recuperação pessoal de dispositivos, rotação automática ou manual de chaves de criptografia pessoais e recuperação de chave para seus dispositivos corporativos. Os usuários finais também podem usar o site Portal da Empresa para obter a chave de recuperação pessoal para seus dispositivos criptografados.

Também expandimos o relatório de criptografia para incluir [informações sobre o FileVault](../protect/encryption-monitor.md) junto com as informações do BitLocker, para que você possa visualizar todos os detalhes de criptografia do seu dispositivo em um só lugar.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>Redefinir o Windows AutoPilot remove o usuário principal do dispositivo<!-- 4156123 -->
Quando a redefinição do AutoPilot for usada em um dispositivo, o usuário primário do dispositivo será removido. O próximo usuário que entrar após a redefinição será definido como o usuário primário. Esse recurso será distribuído para todos os clientes durante os próximos dias.

## <a name="week-of-july-8-2019"></a>Semana de 8 de julho de 2019

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Novas configurações do Office, do Windows e do OneDrive nos modelos administrativos do Windows 10 <!-- 3510695 -->

Você pode criar modelos administrativos no Intune que imitam o gerenciamento de política de grupo local (**Gerenciamento de dispositivos** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Modelo administrativo** para tipo de perfil).

Essa atualização inclui mais configurações do Office, do Windows e do OneDrive que você pode adicionar aos seus modelos. Com essas novas configurações, agora você pode definir mais de 2.500 configurações que são 100% baseadas em nuvem.

Para saber mais sobre esse recurso, confira [Usar modelos do Windows 10 para definir as configurações da política de grupo no Intune](../configuration/administrative-templates-windows.md).

Aplica-se a: Windows 10 e posterior

## <a name="week-of-july-1-2019"></a>Semana de 1º de julho de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="aad-and-app-on-android-enterprise-devices---3574267---"></a>AAD e APP em dispositivos Android Enterprise<!-- 3574267 -->
Ao integrar dispositivos Android Enterprise totalmente gerenciados, os usuários agora serão registrados com o AAD (Azure Active Directory) durante a configuração inicial de seu dispositivo novo ou na redefinição de fábrica. Anteriormente, para um dispositivo totalmente gerenciado, após a conclusão da configuração, o usuário precisava iniciar manualmente o aplicativo Microsoft Intune para começar o registro do AAD. Agora, quando o usuário chega na home page do dispositivo após a configuração inicial, o dispositivo é registrado e inscrito.

Além das atualizações do AAD, agora as APP (políticas de proteção de aplicativo) do Intune são compatíveis com dispositivos Android Enterprise totalmente gerenciados. Essa funcionalidade ficará disponível à medida que for distribuída. Para saber mais, confira [Adicionar aplicativos do Google Play gerenciado a dispositivos Android Enterprise com o Intune](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019-1906-service-release"></a>Semana de 24 de junho de 2019 (versão do serviço 1906)

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Configurar que navegador tem permissão para vincular a dados da organização<!-- 3145939 -->
As APP (Políticas de Proteção de Aplicativo) do Intune em dispositivos Android e iOS agora permitem que você transfira links da Web da organização para um navegador específico além do Intune Managed Browser do ou Microsoft Edge.  Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>A página Todos os aplicativos identifica como online/offline os Aplicativos da Microsoft Store para Empresas<!--4089647 -->
A página **Todos os aplicativos** agora inclui rótulos para identificar aplicativos do MSFB (Microsoft Store for Business) como aplicativos online ou offline. Cada aplicativo MSFB agora inclui um sufixo para **Online** ou **Offline**. A página de detalhes do aplicativo também inclui as informações de **Tipo de licença** e **Suporte à instalação de contexto de dispositivo** (somente aplicativos licenciados offline).

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Aplicativo do Portal da Empresa em dispositivos compartilhados do Windows<!--4393553 -->
Agora os usuários podem acessar o aplicativo do Portal da Empresa em dispositivos compartilhados do Windows. Os usuários finais verão um rótulo **Compartilhado** no bloco do dispositivo. Isso se aplica ao Aplicativo do Portal da Empresa para Windows versão 10.3.45609.0 e posterior.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Exibir todos os aplicativos da nova página da Web do Portal da Empresa<!-- 4224326 -->
A nova página **Aplicativos Instalados** do site Portal da Empresa lista todos os aplicativos gerenciados (tanto obrigatórios quanto disponíveis) instalados em dispositivos do usuário. Além do tipo de atribuição, os usuários podem ver o publicador do aplicativo, a data de publicação e o status atual da instalação. Se você ainda não tornou nenhum aplicativo obrigatório ou disponível aos usuários, eles verão uma mensagem explicando que nenhum aplicativo da empresa foi instalado. Para ver a nova página na Web, acesse o [site do Portal da Empresa](https://portal.manage.microsoft.com) e clique em **Aplicativos Instalados**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>A nova exibição permite que os usuários vejam todos os aplicativos gerenciados instalados no dispositivo<!-- 2352913 -->  
O aplicativo Portal da Empresa para Windows agora lista todos os aplicativos gerenciados (tanto obrigatórios quanto disponíveis) instalados em um dispositivo do usuário. Os usuários também podem exibir tentativas de instalação e instalações de aplicativo pendentes e o status atual. Se você ainda não tornou aplicativos obrigatórios ou disponíveis aos usuários, eles verão uma mensagem explicando que nenhum aplicativo da empresa está instalado. Para ver a nova exibição, vá para o painel de navegação Portal da Empresa e selecione **Aplicativos** > **Aplicativos Instalados**.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>Definir configurações para extensões de kernel em dispositivos macOS<!-- 2043024 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma). Essa atualização inclui um novo grupo de configurações que permite configurar e usar extensões de kernel em seus dispositivos. Você pode adicionar extensões específicas ou permitir todas as extensões de um parceiro ou desenvolvedor específico.

Para saber mais sobre esse recurso, confira a [visão geral das extensões do kernel](../configuration/kernel-extensions-overview-macos.md) e as [configurações de extensão do kernel](../configuration/kernel-extensions-settings-macos.md).

Aplica-se a: macOS 10.13.2 e posteriores

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>Configuração de Aplicativos somente da loja para dispositivos Windows 10 incluem mais opções de configuração<!-- 2697002 -->
Quando você cria um perfil de restrições de dispositivo para dispositivos Windows, pode usar a configuração **Somente aplicativos da loja** para que os usuários instalem somente aplicativos da Windows Store (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Restrições de dispositivo** para tipo de perfil). Nessa atualização, essa configuração é expandida para dar suporte a mais opções.

Para ver a nova configuração, vá para [Configurações do dispositivo Windows 10 (e mais recentes) para permitir ou restringir recursos](../configuration/device-restrictions-windows-10.md#app-store).

Aplica-se a: Windows 10 e posterior

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Implantar vários perfis de dispositivo de extensões de mobilidade Zebra em um dispositivo, mesmo grupo de usuários ou mesmo grupo de dispositivos<!-- 4089955 -->
No Intune, você pode usar extensões de mobilidade Zebra (MX) em um perfil de configuração do dispositivo para personalizar as configurações dos dispositivos Zebra que não são nativas do Intune. No momento, você pode implantar um perfil em um único dispositivo. Nesta atualização, você pode implantar vários perfis para:
- O mesmo grupo de usuários
- O mesmo grupo de dispositivos
- Um único dispositivo

[Usar e gerenciar dispositivos Zebra com o Zebra Mobility Extensions no Microsoft Intune](../configuration/android-zebra-mx-overview.md) mostra como usar o MX no Intune.

Aplica-se a: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>Algumas configurações de quiosque em dispositivos iOS são definidas usando "Bloquear", substituindo "Permitir"<!-- 4404075  -->
Quando você cria um perfil de restrições de dispositivo em dispositivos iOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **Restrições de dispositivo** para tipo de perfil > **Quiosque**), define **Bloqueio automático**, **botão de Toque**, **Rotação da tela**, **botão Suspender tela** e **botões de Volume**.

Nessa atualização, os valores são **Bloquear** (bloqueia o recurso) e **Não configurado** (permite o recurso). Para ver as configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos](../configuration/device-restrictions-ios.md#kiosk).

Aplica-se a: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>Use o Face ID para autenticação de senha em dispositivos iOS<!-- 4490704 -->
Quando você cria um perfil de restrições de dispositivo para dispositivos iOS, pode usar uma impressão digital para uma senha. Nessa atualização, as configurações de senha de impressão digital também permitem reconhecimento facial (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** tipo de perfil > **Senha**). Como resultado, as configurações a seguir mudaram:

- **Desbloqueio por impressão digital** agora é **Desbloqueio por Touch ID e Face ID**.
- **Modificação de impressão digital (somente supervisionada)** agora é **Modificação de Touch ID e Face ID (somente supervisionada)** .

O Face ID está disponível no iOS 11.0 e posteriores. Para ver as configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md#password).

Aplica-se a: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>Restringir recursos da loja de aplicativo e jogos em dispositivos iOS agora é dependente da região de classificações<!-- 4593948 -->
Em dispositivos iOS, você pode permitir ou restringir recursos relacionados a jogos, à loja de aplicativos e à exibição de documentos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** tipo de perfil > **App Store, Exibição de Documentos, Jogos**). Também é possível escolher a região de Classificações, como Estados Unidos.

Nessa atualização, o recurso **Aplicativos** foi movido para ser um filho da **Região de classificações** e é dependente da **Região de classificações**. Para ver as configurações, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Aplica-se a: iOS

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Suporte do Windows AutoPilot para Ingresso no Azure AD Híbrido<!-- 4809146-->
O Windows AutoPilot para dispositivos existentes agora é compatível com o Ingresso no Azure AD Híbrido (além da compatibilidade existente para Ingresso no Azure AD). Aplica-se aos dispositivos Windows 10 versão 1809 e posteriores. Para saber mais, confira [ Windows Autopilot para dispositivos existentes](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).

### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Veja o nível de patch de segurança para dispositivos Android<!-- 4461911 -->
Agora é possível ver o nível de patch de segurança para dispositivos Android. Para isso, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**.
O nível do patch está listado na seção **Sistema operacional**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Atribuir marcas de escopo para todos os dispositivos gerenciados em um grupo de segurança<!-- 3173810 -->
Agora você pode atribuir marcas de escopo a um grupo de segurança e todos os dispositivos no grupo de segurança também serão associados a essas marcas de escopo. Todos os dispositivos nesses grupos também receberão a marca de escopo. As marcas de escopo definidas com esse recurso substituirão as marcas de escopo definidas com o fluxo de marcas de escopo atual do dispositivo. Para saber mais, confira [Usar o RBAC e marcas de escopo na TI distribuída](scope-tags.md).

### <a name="device-security"></a>Segurança de dispositivo

#### <a name="use-keyword-search-with-security-baselines------"></a>Usar pesquisa de palavra-chave com Linhas de base de segurança<!--  -->
Ao criar ou editar [Perfis de linha de base de segurança](../protect/security-baselines.md#create-the-profile), você pode especificar palavras-chave na nova barra de *Pesquisa* para filtrar os grupos de configurações disponíveis para aqueles que contêm seus critérios de pesquisa.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>O recurso Linhas de Base de Segurança agora está disponível para o público geral<!-- 3785395 -->
O recurso **Linhas de Base de Segurança** não está mais na versão prévia e agora está disponível para o público geral (GA).  Isso significa que o recurso está pronto para uso na produção. No entanto, os modelos de linha de base individuais podem permanecer na versão prévia e serão avaliados e liberados para GA em suas próprias programações.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>O modelo de Linha de base de segurança do MDM já está disponível ao público geral<!-- 3794072, 4217151,  3534649 -->
O modelo de linha de base de segurança do MDM foi removido da versão prévia e agora está disponível para o público geral (GA). O modelo GA é identificado como **Linha de base de segurança do MDM para maio de 2019**.  Esse é um novo modelo e não uma atualização da versão de visualização.  Como um novo modelo, você precisará examinar as [configurações que ele contém](../protect/security-baseline-settings-mdm.md) e criar novos perfis para implantá-lo em seu dispositivo. Outros modelos de linha de base de segurança podem permanecer em versão prévia. Para obter uma lista de linhas de base disponíveis, confira [Linhas de base de segurança disponíveis](../protect/security-baselines.md#available-security-baselines).  

Além de ser novo, o modelo *Linha de base de segurança do MDM para maio de 2019* inclui as duas configurações que anunciamos recentemente em nosso artigo Em desenvolvimento:  
- Acima do Bloqueio: aplicativos ativados por voz de uma tela bloqueada  
- DeviceGuard: usa VBS (segurança baseada em virtualização) na próxima reinicialização dos dispositivos.  

A *Linha de base de segurança do MDM para maio de 2019* também inclui a adição de várias novas configurações, a remoção de outras e uma revisão do valor padrão de uma configuração. Para obter uma lista detalhada das alterações de versão prévia para GA, confira **O que mudou no novo modelo**.

#### <a name="security-baseline-versioning---3194322---"></a>Controle de versão de linha de base de segurança<!-- 3194322 -->
Linhas de base de segurança para o controle de versão de suporte do Intune. Com esse suporte, à medida que novas versões de cada linha de base de segurança são lançadas, você pode atualizar seus perfis de linha de base de segurança existentes para usar a versão de linha de base mais recente sem precisar recriar e implantar uma nova linha de base do zero. Além disso, no console do Intune, é possível exibir as informações sobre cada linha de base, como o número de perfis individuais que usam a linha de base, quantas versões diferentes da linha de base são usadas por seus perfis e quando foi lançada a linha de base de segurança específica mais recente.  Para saber mais, confira **Linhas de base de segurança**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>A configuração Usar chaves de segurança para entrada foi movida<!-- 4501151 -->
A definição de configuração do dispositivo para a proteção de identidade chamada **Usar chaves de segurança para entrada** não é mais encontrada como uma subconfiguração de *Configurar o Windows Hello para Empresas*. Agora é uma configuração de nível superior que está sempre disponível, mesmo quando você não habilita o uso do Windows Hello para Empresas. Para saber mais, confira [Proteção de identidade](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Controle de acesso baseado em funções

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Novas permissões para administradores de grupos atribuídos<!-- 4504437   -->
A função interna de Administrador da escola do Intune agora tem permissões CRUD (criar, ler, atualizar e excluir) para Aplicativos Gerenciados. Essa atualização significa que, se você estiver atribuído como administrador de grupo no Intune para Educação, agora poderá criar, exibir, atualizar e excluir os MDM Push Certificate do iOS, tokens de servidor MDM do iOS e tokens VPP do IOS, junto com [todas as permissões existentes que você tem](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Para executar qualquer uma dessas ações, vá para **Configurações de locatário** > **Gerenciamento de dispositivo iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Os aplicativos podem usar o API do Graph para chamar as operações de leitura sem credenciais de usuário<!-- 4655885 -->
Aplicativos podem chamar operações de leitura da API do Graph do Intune com identidade de aplicativo sem credenciais de usuário. Para saber mais sobre como acessar a API do Microsoft Graph para Intune, confira [Como trabalhar com o Intune no Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Aplicar marcas de escopo nos Aplicativos da Microsoft Store para Empresas<!-- 4392555 -->
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

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>Novos aplicativos de exemplo que mostram a integração do SDK do Intune disponível no GitHub<!-- 2653471 -->
O conta do GitHub do msintuneappsdk adicionou novos exemplos de aplicativos para iOS (Swift), Android, Xamarin.iOS, Xamarin Forms e Xamarin.Android. Esses aplicativos devem complementar nossa documentação existente e fornecer demonstrações de como integrar o SDK de aplicativo do Intune em seus próprios aplicativos móveis. Se você for um desenvolvedor de aplicativo que precisa de orientações adicionais sobre o SDK do Intune, confira os seguintes exemplos vinculados:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) – um aplicativo de mensagens instantâneas nativo para iOS nativo (Swift), que usa a biblioteca de autenticação do Azure Active Directory (ADAL) para a autenticação agenciada.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) - um aplicativo de lista de tarefas pendentes nativo para Android que usa ADAL para autenticação agenciada.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) - um aplicativo de lista de tarefas pendentes para Xamarin.Android que usa a ADAL para autenticação agenciada. Esse repositório também tem o aplicativo Xamarin.Forms.
- [Aplicativo de exemplo do Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) - um aplicativo de exemplo barebones para Xamarin.iOS.

## <a name="week-of-may-27-2019"></a>Semana de 27 de maio de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Relatórios para aplicativos potencialmente prejudiciais em dispositivos Android<!-- 4223162 -->
Agora, o Intune fornece informações adicionais de relatórios sobre aplicativos potencialmente prejudiciais em dispositivos Android. 

## <a name="week-of-may-20-2019"></a>Semana de 20 de maio de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="windows-company-portal-app---3316993---"></a>Aplicativo do Portal da Empresa para Windows<!-- 3316993 -->
O aplicativo do Portal da Empresa do Windows agora terá uma nova página rotulada **Dispositivos**. A página **Dispositivos** mostrará aos usuários finais todos os seus dispositivos registrados. Os usuários verão essa alteração no Portal da Empresa quando usarem a versão 10.3.4291.0 e posterior. Para obter informações sobre como configurar o Portal da Empresa, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Nome do atributo OrderID do dispositivo Autopilot alterado para Marcação de Grupo <!-- 4659453 -->

Para torná-lo mais intuitivo, o nome do atributo **OrderID** em dispositivos do Autopilot foi alterado para **Marcação de Grupo**. Ao usar CSVs para carregar informações do dispositivo do Autopilot, você precisa usar Marcação de Grupo como o cabeçalho de coluna, não OrderID.  

## <a name="week-of-may-13-2019-1905-service-release"></a>Semana de 13 de maio de 2019 (versão do serviço 1905)

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Método de autenticação de atualização das políticas do Intune e instalação do aplicativo Portal da Empresa<!-- 1927359  -->
Em dispositivos já registrados por meio do Assistente de Instalação com um dos métodos de registro de dispositivo corporativo da Apple, o Intune não oferecerá mais o suporte do Portal da Empresa quando for instalado manualmente pelos usuários finais da loja de aplicativos. Essa alteração só é relevante quando você autentica com o Assistente de Configuração da Apple durante o registro. Além disso, essa alteração afeta apenas dispositivos iOS registrados via:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Programa de registro de dispositivos (DEP) da Apple

Se os usuários instalarem o aplicativo Portal da Empresa pela loja de aplicativos e tentarem registrar esses dispositivos por meio do aplicativo, receberão um erro. Esses dispositivos só devem usar o Portal da Empresa quando ele for enviado por push, automaticamente, pelo Intune durante o registro. Os perfis de registro no Intune, no portal do Azure, serão atualizados para que você possa especificar como os dispositivos são autenticados, e se o usuário recebe o aplicativo Portal da Empresa. Se você quiser que os usuários de dispositivos DEP tenham o Portal da Empresa, especifique suas preferências em um perfil de registro. 

Além disso, a tela **Identificar seu dispositivo** no Portal da Empresa do iOS está sendo removida. Portanto, os administradores que desejem habilitar o Acesso Condicional ou implantar aplicativos da empresa devem atualizar o perfil de registro de DEP. Esse requisito aplica-se somente se o registro de DEP for autenticado com o Assistente de Configuração. Nesse caso, você deve efetuar push do Portal da Empresa para o dispositivo. Para fazer isso, escolha **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Propriedades** > defina **Instalar o Portal da Empresa** para **Sim**.

Para instalar o Portal da Empresa em dispositivos DEP já registrados, acesse Intune > Aplicativos Cliente, e envie-o como um aplicativo gerenciado com políticas de configuração de aplicativo. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Configurar o modo como os usuários finais atualizam um aplicativo de linha de negócios (LOB) usando uma política de proteção de aplicativo<!-- 3568384 -->
Agora é possível configurar onde os usuários finais podem obter uma versão atualizada de um aplicativo de linha de negócios (LOB). Os usuários finais verão esse recurso na caixa de diálogo de inicialização condicional **Versão mínima do aplicativo**, que solicitará que os usuários finais atualizem para uma versão mínima do aplicativo de linha de negócios. Forneça esses detalhes de atualização como parte de sua política de proteção de aplicativo de linha de negócios (APP). Este recurso está disponível para iOS e Android. No iOS, esse recurso requer que o aplicativo seja integrado (ou encapsulado usando a ferramenta de encapsulamento) ao SDK do Intune para iOS v. 10.0.7 ou versão posterior. No Android, esse recurso exige a versão mais recente do Portal da Empresa. Para configurar o modo como um usuário final atualiza um aplicativo de linha de negócios, o aplicativo precisa que uma política de configuração de aplicativo gerenciado seja enviada a ele com a chave, `com.microsoft.intune.myappstore`. O valor enviado define de qual repositório o usuário final baixará o aplicativo. Se o aplicativo for implantado por meio do Portal da Empresa, o valor deverá ser `CompanyPortal`. Para qualquer outro repositório, você deverá inserir uma URL completa.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Scripts do PowerShell da extensão de gerenciamento do Intune<!-- 3734186  -->
A execução de scripts do PowerShell pode ser configurada com privilégios de administrador do usuário no dispositivo. Saiba mais em [Usar scripts do PowerShell em dispositivos Windows 10 no Intune](../apps/intune-management-extension.md) e [Gerenciamento de Aplicativos Win32](../apps/app-management.md).

#### <a name="android-enterprise-app-management---4459905---"></a>Gerenciamento de aplicativos do Android Enterprise<!-- 4459905 -->
Para facilitar a configuração e o uso do gerenciamento de Android Enterprise pelos administradores de TI, o Intune adicionará automaticamente quatro aplicativos comuns relacionados ao Android Enterprise ao console do administrador do Intune. Os quatro aplicativos do Android Enterprise são os seguintes apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** – usado para cenários totalmente gerenciados pelo Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – ajuda a entrar em suas contas se usar a verificação de dois fatores.
- **[Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – usado para cenários de perfil de trabalho das Políticas de Proteção do Aplicativo (APP) e do Android Enterprise.
- [Tela inicial gerenciada](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – usado para cenários dedicados/quiosques do Android Enterprise.

Antes, os administradores de TI precisavam encontrar e aprovar manualmente esses aplicativos na [Google Play Store gerenciada](https://play.google.com/store/apps) como parte da configuração. Essa alteração remove essas etapas que eram manuais para tornar mais fácil e rápido para os clientes usarem o gerenciamento do Android Enterprise.

Os administradores verão esses quatro aplicativos adicionados automaticamente à lista de aplicativos do Intune no momento em que conectarem pela primeira vez o locatário do Intune ao Google Play gerenciado. Confira mais informações em [Conectar sua conta do Intune à sua conta gerenciada do Google Play](../enrollment/connect-intune-android-enterprise.md). Para locatários que já conectaram o próprio locatário ou que já usam o Android Enterprise, não há nada que os administradores precisem fazer. Esses quatro aplicativos aparecerão automaticamente dentro de sete dias após a conclusão da implantação do serviço em maio de 2019.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Conector do Certificado PFX atualizado do Microsoft Intune<!-- 1533038 -->
Lançamos uma atualização para o [Conector do Certificado PFX para o Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) que resolve um problema em que os certificados PFX existentes continuam a ser reprocessados, o que faz com que o conector pare de processar novas solicitações.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Tarefas de segurança do Intune para Defender ATP (em versão prévia pública)<!-- 3208597 -->
Na versão prévia pública, você pode usar o Intune para gerenciar [tarefas de segurança para a ATP (Proteção Avançada contra Ameaças) do Microsoft Defender](../protect/atp-manage-vulnerabilities.md). Essa integração com a ATP adiciona uma abordagem baseada em riscos para detectar, priorizar e corrigir vulnerabilidades e configurações incorretas do ponto de extremidade, enquanto reduz o tempo entre a descoberta e a mitigação.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671-----"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10<!-- 3617671   -->
Muitos dispositivos Windows 10 e posteriores têm chipsets TPM (Trusted Platform Module). Esta atualização inclui uma nova configuração de conformidade que verifica a versão do chip TPM no dispositivo.

O artigo [Configurações de política de conformidade do Windows 10 e posteriores](../protect/compliance-policy-create-windows.md#device-security) descreve esta configuração.

Aplica-se a: Windows 10 e posterior

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Impedir que usuários finais alterem o ponto de acesso pessoal e desabilitem o registro em log do servidor Siri em dispositivos iOS<!-- 4097904   -->  
Crie um perfil de restrições de dispositivo no dispositivo iOS (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações que você poderá configurar:

- **Aplicativos internos**: registro em log no lado do servidor para os comandos da Siri
- **Sem fio**: modificação do usuário do Ponto de acesso pessoal (somente supervisionado)

Para ver essas configurações, vá para [Configurações de aplicativo interno para iOS](../configuration/device-restrictions-ios.md#built-in-apps) e [Configurações sem fio para iOS](../configuration/device-restrictions-ios.md#wireless).

Aplica-se a: iOS 12.2 e posteriores

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>Novas configurações de restrição de dispositivo do aplicativo Sala de aula para dispositivos macOS<!-- 4097905   --> 
Crie perfis de configuração de dispositivo para dispositivos macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Essa atualização inclui novas configurações do aplicativo Sala de aula, a opção de bloquear capturas de tela e a opção de desabilitar a Biblioteca de Fotos do iCloud.

Para ver as configurações atuais, vá para [Configurações do dispositivo macOS para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-macos.md).

Aplica-se a: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>A senha do iOS para acessar a configuração da loja de aplicativos foi renomeada<!-- 4557891  -->
A configuração **Senha para acessar a loja de aplicativos** foi renomeada para **Exigir a senha do iTunes para todas as compras** (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma> **Restrições do Dispositivo** para o tipo de perfil > **Loja de Aplicativos, Exibição de Documentos, Jogos**).

Para ver as configurações disponíveis, acesse a configuração do iOS [Loja de Aplicativos, Exibição de Documentos, Jogos](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Aplica-se a: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Linha de base da Proteção Avançada contra Ameaças do Microsoft Defender (versão prévia)<!--  3754134 -->
Adicionamos uma versão prévia da linha de base de segurança para as configurações da [Proteção Avançada contra Ameaças do Microsoft Defender](../protect/security-baseline-settings-defender-atp.md). Esta linha de base está disponível quando seu ambiente atende aos pré-requisitos para usar a [Proteção Avançada contra Ameaças do Microsoft Defender](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>A página Status do Registro do Windows (ESP) já está amplamente disponível<!-- 3605348 -->
A página Status do Registro saiu da versão prévia. Para saber mais, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Atualização da interface de usuário do Intune – Criação de perfil de registro do Autopilot<!-- 4593669 -->
A interface do usuário para a criação de um perfil de registro do Autopilot foi atualizada para alinhar-se aos estilos de interface do usuário do Azure. Saiba mais em [Criar um perfil de registro do Autopilot](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile). A partir de agora cenários adicionais do Intune serão atualizados para esse novo estilo de interface do usuário.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Habilitar Autopilot Reset para todos os dispositivos do Windows<!-- 4225665 -->
Agora o Autopilot Reset funciona em todos os dispositivos Windows, mesmo aqueles não configurados para usar a página de Status de registro. Se uma página de Status de registro não tiver sido configurada para o dispositivo durante o registro inicial do dispositivo, o dispositivo será direcionado para a área de trabalho depois do login. Ele pode levar até oito horas para sincronizar e aparecer como em conformidade no Intune. Saiba mais em [Redefinir dispositivos com o Windows Autopilot Reset remoto](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>O formato exato do IMEI não é obrigatório ao pesquisar por Todos os dispositivos<!--30407680 -->
Você não precisa incluir espaços em números IMEI ao pesquisar **Todos os dispositivos**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Excluir um dispositivo no portal da Apple será refletido no portal do Intune<!--2489996 -->
Se um dispositivo for excluído do Programa de registro de dispositivos da Apple ou dos portais do Apple Business Manager, o dispositivo será excluído automaticamente do Intune durante a próxima sincronização.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>A Página de status de registro agora acompanha aplicativos Win32<!-- 2714451 -->
Isso se aplica somente a dispositivos que executam o Windows 10 versão 1903 e superior. Para saber mais, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Redefinir e apagar dispositivos em massa usando a API do Graph<!-- 3295288 -->
Você agora pode redefinir e apagar até 100 dispositivos em massa, usando a API do Graph.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>O relatório de criptografia saiu da versão prévia pública<!-- 4587546      -->
O [relatório para BitLocker e criptografia de dispositivo](../protect/encryption-monitor.md) já está amplamente disponível e não faz mais parte da versão prévia pública.

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>Assinatura e configurações de biometria do Outlook para dispositivos iOS e Android<!-- 4050557 -->
Agora você pode especificar se a assinatura padrão está habilitada no Outlook em dispositivos iOS e Android. Além disso, pode permitir que os usuários alterem a configuração biométrica do Outlook no iOS.

## <a name="week-of-may-6-2019"></a>Semana de 6 de maio de 2019

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>Suporte do NAC (Controle de Acesso à Rede) do F5 Access para dispositivos iOS<!-- 4500808 -->

O F5 lançou uma atualização para BIG-IP 13 que permite funcionalidade NAC no F5 Access em iOS no Intune. Para usar esse recurso:

- Atualize o BIG-IP para a atualização 13.1.1.5. O BIG-IP 14 não é compatível.
- Integre o BIG-IP ao Intune para NAC. As etapas em [Visão geral: como configurar o APM para verificações de situação do dispositivo com sistemas de gerenciamento de ponto de extremidade](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Verifique a configuração **Habilitar NAC (controle de acesso de rede)** no perfil de VPN no Intune.

Para ver a configuração disponível, vá para [Definir configurações de VPN em dispositivos iOS](../configuration/vpn-settings-ios.md).

Aplica-se a: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Conector do Certificado PFX atualizado do Microsoft Intune<!-- doc-vso 1521237  -->  
Lançamos uma atualização para o [conector de certificado PFX para o Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) que reduz o intervalo de sondagem de 5 minutos para 30 segundos.




## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
