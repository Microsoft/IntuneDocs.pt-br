---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/24/2020
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
ms.openlocfilehash: d2f984392983d81bc64edb7206469babdb806d63
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609290"
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

Conheça as novidades de cada semana do Microsoft Intune. Você também pode encontrar [avisos importantes](#notices), [versões anteriores](whats-new-archive.md) e informações sobre [como as atualizações de serviço do Intune são liberadas](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Cada [atualização mensal](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) pode levar até três dias para ser distribuída e estará na seguinte ordem:
>
> - Dia 1: Pacífico Asiático (APAC)
> - Dia 2: Europa, Oriente Médio e África (EMEA)
> - Dia 3: América do Norte
> - Dia 4+: Intune para o governo
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
## <a name="week-of-february-24-2020"></a>Semana de 24 de fevereiro de 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="macos-company-portal-user-experience-improvements---5568987---"></a>Aprimoramentos na experiência do usuário do Portal da Empresa do macOS<!-- 5568987 -->
Fizemos aprimoramentos na experiência de registro do dispositivo macOS e no aplicativo Portal da Empresa para Mac. Você verá o seguinte:
- Uma melhor experiência do **Microsoft AutoUpdate** durante o registro, que garantirá que os usuários tenham a versão mais recente do Portal da Empresa.
- Uma etapa de verificação de conformidade aprimorada durante o registro.
- Suporte para IDs de Incidente copiadas, para que os usuários possam enviar erros de seus dispositivos para a equipe de suporte da empresa mais rapidamente.

Para obter mais informações sobre o registro e o aplicativo Portal da Empresa para Mac, confira [Registrar seu dispositivo macOS usando o aplicativo Portal da Empresa](/intune-user-help/enroll-your-device-in-intune-macos-cp). 

<!-- ########################## -->
## <a name="week-of-february-17-2020-2002-service-release"></a>Semana de 17 de fevereiro de 2020 (versão do Serviço 2002)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="microsoft-defender-advanced-threat-protection-atp-app-for-macos---5424618---"></a>Aplicativo ATP (Proteção Avançada contra Ameaças) do Microsoft Defender para macOS<!-- 5424618 -->
O Intune fornece uma maneira fácil de implantar o aplicativo Microsoft Defender ATP (Proteção Avançada contra Ameaças) para macOS em dispositivos Mac gerenciados. Para obter mais informações, confira [Adicionar o Microsoft Defender ATP a dispositivos macOS usando o Microsoft Intune](~/apps/apps-advanced-threat-protection-macos.md) e [Proteção Avançada contra Ameaças do Microsoft Defender para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac).  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="enable-network-access-control-nac-with-cisco-anyconnect-vpn-on-ios-devices---4860111----"></a>Habilitar o NAC (controle de acesso à rede) com VPN Cisco AnyConnect em dispositivos iOS<!-- 4860111  -->
Em dispositivos iOS, você pode criar um perfil de VPN e usar tipos de conexão diferentes, incluindo o Cisco AnyConnect (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **VPN** para o tipo de perfil > **Cisco AnyConnect** para o tipo de conexão). 

Você pode habilitar o NAC (controle de acesso à rede) com o Cisco AnyConnect. Para usar esse recurso:

1. Em [Guia do administrador do Cisco Identity Services Engine](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html), use as etapas em **Configurar o Microsoft Intune como um servidor do MDM** para configurar o Cisco ISE (Identity Services Engine) no Azure.
2. No perfil de configuração de dispositivo do Intune, selecione a configuração **Habilitar o NAC (controle de acesso à rede)** .

Para ver todas as configurações de VPN disponíveis, vá para [Definir configurações de VPN em dispositivos iOS](../configuration/vpn-settings-ios.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="serial-number-on-the-apple-mdm-push-certificate-page--5947765----"></a>Número de série na página Apple MDM Push Certificate<!--5947765  -->
A página Apple MDM Push Certificate agora mostra o número de série. O número de série é necessário para recuperar acesso ao Apple MDM Push Certificate em caso de perda do acesso à ID da Apple que criou o certificado. Para ver o número de série, acesse **Dispositivos** > **iOS** > **Registro do iOS** > **Apple MDM Push Certificate**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="new-update-schedule-options-for-pushing-os-updates-to-enrolled-iosipados-devices--5879689----"></a>Novas opções de agendamento de atualização para enviar por push atualizações do sistema operacional para dispositivos iOS/iPadOS registrados<!--5879689  -->
Você pode escolher entre as opções a seguir ao agendar atualizações do sistema operacional para dispositivos iOS/iPadOS. Isso se aplica a dispositivos que usavam os tipos de registro Apple Business Manager ou Apple School Manager.
- Atualizar no próximo check-in
- Atualizar durante o horário agendado
- Atualizar fora do horário agendado

Para as duas últimas opções, você pode criar várias janelas de tempo.

Para ver as novas opções, acesse MEM > **Dispositivos** > **iOS** > **Atualizar políticas para iOS/iPadOS** > **Criar perfil**.

#### <a name="choose-which-iosipados-updates-to-push-to-enrolled-devices--5879689----"></a>Escolher quais atualizações do iOS/iPadOS enviar por push a dispositivos registrados<!--5879689  -->
Você poderá escolher uma atualização específica do iOS/iPadOS (exceto a atualização mais recente) para enviar por push para os dispositivos registrados usando o Apple Business Manager ou o Apple School Manager. Esses dispositivos devem ter uma política de configuração de dispositivo definida para atrasar a visibilidade da atualização de software por algum número de dias. Para ver esse recurso, acesse MEM > **Dispositivos** > **iOS** > **Atualizar políticas para iOS/iPadOS** > **Criar perfil**.

### <a name="all-devices-list-improved-search-sort-and-filter--6179023--"></a>Pesquisa, classificação e filtro aprimorados da lista Todos os dispositivos<!--6179023-->
O desempenho, a pesquisa, a classificação e a filtragem da lista Todos os dispositivos foram aprimorados.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Segurança de dispositivo

#### <a name="improved-intune-reporting-experience---3791418-----"></a>Experiência aprimorada de relatórios do Intune<!-- 3791418   -->
O Intune agora oferece uma experiência aprimorada de relatórios, incluindo novos tipos de relatórios, melhor organização de relatórios, visualizações mais focadas, funcionalidade aprimorada de relatórios e dados mais consistentes e oportunos. A experiência de relatório passará da versão prévia pública para a GA (disponibilidade geral). Além disso, a versão GA terá suporte à localização, correções de bug, aprimoramentos de design e dados de conformidade de dispositivo agregados em blocos no [centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431). 

Novos tipos de relatório se concentram no seguinte:
- **Operacional** - fornece novos registros com foco de integridade negativa. 
- **Organizacional** - fornece um resumo mais amplo do estado geral.
- **Histórico** – fornece padrões e tendências ao longo de um período.
- **Especialista** – permite que você use dados brutos para criar seus próprios relatórios personalizados.

O primeiro conjunto de novos relatórios se concentra na conformidade do dispositivo. Para saber mais, confira [Blog - Estrutura de relatórios do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) e [Relatórios do Intune](~/fundamentals/reports.md).

#### <a name="consolidated-the-location-of-security-baselines-in-the-ui---6177074-----"></a>Localização consolidada para as linhas de base de segurança<!-- 6177074   -->
Consolidamos os caminhos para localizar as [linhas de base de segurança](../protect/security-baselines.md) no centro de administração do Microsoft Endpoint Manager, removendo *Linhas de base de segurança* de vários locais da interface do usuário. Para encontrar as Linhas de base de segurança, agora você usa o seguinte caminho:  **Segurança de ponto de extremidade** > **Linhas de base de segurança**.

#### <a name="expanded-support-for-imported-pkcs-certificates---6044197-wnready---"></a>Suporte expandido para certificados PKCS importados<!-- 6044197 WNReady -->
Expandimos o suporte ao uso de [certificados PKCS importados](../protect/certificates-imported-pfx-configure.md#supported-platforms) para dar suporte a *dispositivos Android Enterprise totalmente gerenciados*. Geralmente, a importação de certificados PFX é usada para cenários de criptografia S/MIME, em que os certificados de criptografia de um usuário são necessários em todos os dispositivos dele para que a descriptografia de email possa ocorrer.

As seguintes plataformas dão suporte à importação de certificados PFX:
- Android – Administrador de dispositivo
- Android Enterprise – Totalmente gerenciado
- Android Enterprise – Perfil de trabalho
- iOS
- Mac
- Windows 10

#### <a name="view-the-endpoint-security-configuration-for-devices---6206460----"></a>Exibir a configuração de segurança do ponto de extremidade para dispositivos<!-- 6206460  -->
Atualizamos o nome da opção no centro de administração do Microsoft Endpoint Manager para exibir [configurações de segurança do ponto de extremidade que se aplicam a um dispositivo específico](../protect/security-baselines-monitor.md#view-endpoint-security-configurations-per-device). Essa opção é renomeada para **Configuração de segurança do ponto de extremidade** porque mostra as linhas de base de segurança aplicáveis e políticas adicionais criadas fora das linhas de base de segurança. Anteriormente, essa opção era chamada de *Linhas de base de segurança*. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Controle de acesso baseado em funções

#### <a name="intune-roles-user-interface-changes-coming--5801612-----"></a>Futuras alterações na interface do usuário de Funções do Intune<!--5801612   -->
A interface do usuário do [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Administração de locatários** > **Funções** foi aprimorada para um design mais amigável e intuitivo. Essa experiência fornece as mesmas configurações e detalhes que você usa agora, mas emprega um processo semelhante ao de um assistente.

<!-- ########################## -->
## <a name="week-of-february-17-2020"></a>Semana de 17 de fevereiro de 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="microsofts-new-office-app---5859926---"></a>Novo aplicativo Office da Microsoft<!-- 5859926 -->
O novo aplicativo Office da Microsoft já está em disponibilidade geral para download e uso. O aplicativo Office é uma experiência consolidada em que os usuários podem trabalhar entre o Word, o Excel e o PowerPoint em um único aplicativo. Você pode direcionar uma política de proteção de aplicativo ao Office para assegurar que os dados que estão sendo acessados sejam protegidos.

Para obter mais informações, confira [Como habilitar políticas de proteção de aplicativo do Intune com a versão prévia do aplicativo móvel Office](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-how-to-enable-intune-app-protection-policies-with/ba-p/1045493).

<!-- ########################## -->
## <a name="week-of-february-10-2020"></a>Semana de 10 de fevereiro de 2020

### <a name="windows-7-ends-extended-support--3042987---"></a>Fim do suporte estendido do Windows 7<!--3042987 -->
O Windows 7 atingiu o fim do suporte estendido em 14 de janeiro de 2020. Ao mesmo tempo, o Intune preteriu o suporte para dispositivos que executam o Windows 7. A assistência técnica e as atualizações automáticas que ajudam a proteger seu computador não estão mais disponíveis. Você deve atualizar para o Windows 10. Para obter mais informações, confira a [postagem no blog Planejar mudanças](https://aka.ms/Windows7_Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="microsoft-edge-version-77-and-later-on-windows-10-devices---5843584---"></a>Microsoft Edge versão 77 e posteriores em dispositivos Windows 10<!-- 5843584 -->
O Intune agora dá suporte à desinstalação do Microsoft Edge versão 77 e posterior em dispositivos Windows 10. Para obter mais informações, veja [Adicionar o Microsoft Edge para Windows 10 ao Microsoft Intune](~/apps/apps-windows-edge.md).

#### <a name="screen-removed-from-company-portal-android-work-profile-enrollment--6103987---"></a>Tela removida do Portal da Empresa, registro de perfil de trabalho do Android<!--6103987 -->
A tela **O que vem a seguir?** foi removida do fluxo de registro do perfil de trabalho do Android no Portal da Empresa, para simplificar a experiência do usuário. Acesse [Registrar com o perfil de trabalho do Android](/intune-user-help/enroll-device-android-work-profile) para ver o fluxo de registro do perfil de trabalho do Android atualizado.  

#### <a name="company-portal-app-improved-performance---6178652---"></a>Desempenho aprimorado do aplicativo Portal da Empresa<!-- 6178652 -->
O aplicativo Portal da Empresa foi atualizado para dar suporte a um desempenho aprimorado para dispositivos que usam processadores ARM64, como o Surface Pro X. Anteriormente, o Portal da Empresa operava em um modo ARM32 emulado. Agora, na versão 10.4.7080.0 e posteriores, o aplicativo Portal da Empresa é compilado nativamente para ARM64. Para obter mais informações sobre o aplicativo Portal da Empresa, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](~/apps/company-portal-app.md).

<!-- ########################## -->
## <a name="week-of-january-27-2020"></a>Semana de 27 de janeiro de 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-support-for-additional-microsoft-edge-version-77-deployment-channel-for-macos---5983950----"></a>Suporte do Intune para o canal de implantação adicional do Microsoft Edge versão 77 para macOS<!-- 5983950  -->
Agora, o Microsoft Intune dá suporte ao canal de implantação adicional **Estável** para o aplicativo Microsoft Edge para macOS. O canal **Estável** é recomendado para a implantação geral do Microsoft Edge em ambientes corporativos. Ele é atualizado a cada seis semanas, e cada versão incorpora as melhorias do canal **Beta**. Além dos canais **Estável** e **Beta**, o Intune dá suporte ao canal **Dev**. A versão prévia pública oferece os canais Estável e Dev para o Microsoft Edge versão 77 e posterior para o macOS. As atualizações automáticas do navegador estão ativadas por padrão. Confira mais informações em [Adicionar o Microsoft Edge a dispositivos macOS usando o Microsoft Intune](~/apps/apps-edge-macos.md).

#### <a name="retirement-of-intune-managed-browser--5728447---"></a>Desativação do Intune Managed Browser<!--5728447 -->
O Intune Managed Browser será desativado. Use o Microsoft Edge para obter uma experiência de navegação protegida no Intune. Confira mais informações na entrada "[Executar Ação: use o Microsoft Edge em sua experiência de navegação protegida no Intune](~/fundamentals/whats-new.md#take-action-use-microsoft-edge-for-your-protected-intune-browser-experience)" na seção [Notificações](~/fundamentals/whats-new.md#notices) abaixo.

<!-- ########################## -->
## <a name="week-of-january-20-2020-2001-service-release"></a>Semana de 20 de janeiro de 2020 (versão do Serviço 2001)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="user-experience-change-when-adding-apps-to-intune---4705829-----"></a>Alteração da experiência do usuário ao adicionar aplicativos ao Intune<!-- 4705829   -->
Você verá uma nova experiência do usuário ao adicionar aplicativos por meio do Intune. Essa experiência oferece as mesmas configurações e detalhes que você usou anteriormente, mas a nova experiência emprega um processo semelhante ao de um assistente antes de adicionar um aplicativo ao Intune. Essa nova experiência também fornece uma página de revisão antes de adicionar o aplicativo. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**. Para obter mais informações, confira [Adicionar aplicativos ao Microsoft Intune](~/apps/apps-add.md).

#### <a name="require-win32-apps-to-restart----5622282-----"></a>Exigir a reinicialização de aplicativos Win32 <!-- 5622282   -->
Você pode exigir que aplicativo Win32 seja reiniciado depois da instalação com êxito. Além disso, você pode escolher a quantidade de tempo (o período de carência) antes que a reinicialização ocorra.

#### <a name="user-experience-change-when-configuring-apps-in-intune---4207990-----"></a>Alteração da experiência do usuário ao configurar aplicativos no Intune<!-- 4207990   -->
Você verá uma nova experiência do usuário ao criar políticas de configuração de aplicativos no Intune. Essa experiência oferece as mesmas configurações e detalhes que você usou anteriormente, mas a nova experiência emprega um processo semelhante ao de um assistente antes de adicionar uma política ao Intune. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Aplicativos** > **Políticas de configuração de aplicativos** > **Adicionar**. Para saber mais, confira [Políticas de configuração de aplicativos do Microsoft Intune](~/apps/app-configuration-policies-overview.md). 

#### <a name="intune-support-for-additional-microsoft-edge-for-windows-10-deployment-channel---5861774---"></a>Suporte do Intune para o canal de implantação adicional do Microsoft Edge para Windows 10<!-- 5861774 -->
Agora, o Microsoft Intune dá suporte ao canal de implantação adicional **Estável** para o aplicativo Microsoft Edge (versão 77 e posterior) para Windows 10. O canal **Estável** é recomendado para a implantação geral do Microsoft Edge para Windows 10 em ambientes corporativos. Esse canal é atualizado a cada seis semanas, cada versão incorpora as melhorias do canal **Beta**. Além dos canais **Estável** e **Beta**, o Intune dá suporte ao canal **Dev**. Confira mais informações em [Microsoft Edge para Windows 10 – Definir configurações do aplicativo](~/apps/apps-windows-edge.md#configure-app-settings).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="improved-user-interface-experience-when-configuring-exchange-activesync-on-premises-connector-ui---5695492-----"></a>Experiência aprimorada da interface do usuário ao configurar a interface do usuário do conector local do Exchange ActiveSync<!-- 5695492   -->
Atualizamos a experiência para [configurar o conector local do Exchange ActiveSync](../protect/exchange-connector-install.md). A experiência atualizada usa um único painel para configurar, editar e resumir os detalhes de seus conectores locais. 

#### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-----"></a>Adicionar configurações automáticas de proxy a perfis de Wi-Fi para perfis de trabalho do Android Enterprise<!-- 4490822   -->
Em dispositivos de perfil de trabalho Android Enterprise, é possível criar perfis de Wi-Fi. Ao escolher o tipo Wi-Fi Corporativa, você também pode inserir o tipo de protocolo EAP (Protocolo de Autenticação Extensível) usado em sua rede Wi-Fi.

Agora, ao escolher o tipo Corporativa, também poderá inserir as configurações automáticas de proxy, incluindo uma URL do servidor proxy, como `proxy.contoso.com`.

Para conferir as configurações atuais de Wi-Fi que você pode definir, acesse [Adicionar configurações de Wi-Fi a dispositivos que executam o Android Enterprise e o Android Kiosk no Microsoft Intune](../configuration/wi-fi-settings-android-enterprise.md).

Aplica-se a:
- Perfil de trabalho do Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="block-android-enrollments-by-device-manufacturer--5197392----"></a>Bloquear registros do Android por fabricante do dispositivo<!--5197392  -->
Você pode bloquear o registro de dispositivos com base no fabricante do dispositivo. Isso se aplica ao administrador do dispositivo Android e a dispositivos do perfil de trabalho do Android Enterprise. Para ver as restrições de registro, acesse o [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **Restrições de registro**.

#### <a name="improvements-to-the-iosipados-create-enrollment-type-profile-ui---6055005---"></a>Melhorias na interface do usuário para Criar perfil do tipo de registro do iOS/iPadOS<!-- 6055005 -->
Para o Registro de Usuário do iOS/iPadOS, a página **Criar perfil do tipo de registro** **Configurações** foi simplificada para melhorar o processo de escolha do **Tipo de registro** ao manter a mesma funcionalidade. Para ver a nova interface do usuário, vá até [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **iOS** > **Registro do iOS** > **Tipos de registro** > **Criar perfil** > **Configurações**. Confira mais informações em [Criar um perfil de Registro do Usuário no Intune](../enrollment/ios-user-enrollment.md#create-a-user-enrollment-profile-in-intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Gerenciamento de dispositivo

#### <a name="new-information-in-device-details---4471759-5604099----"></a>Novas informações nos detalhes do dispositivo<!-- 4471759 5604099  -->
Agora, as informações a seguir estão na página de **Visão geral** dos dispositivos:
- Capacidade da Memória (quantidade de memória física no dispositivo)
- Capacidade de Armazenamento (quantidade de armazenamento físico no dispositivo) 
- Arquitetura da CPU

#### <a name="ios-bypass-activation-lock-remote-action-renamed-to-disable-activation-lock---5904591----"></a>A ação remota Ignorar o Bloqueio de Ativação do iOS foi renomeada como Desabilitar o Bloqueio de Ativação <!--5904591  -->
A ação remota **Ignorar o Bloqueio de Ativação** foi renomeada como **Desabilitar o Bloqueio de Ativação**. Confira mais informações em [Desabilitar o Bloqueio de Ativação do iOS com o Intune](../remote-actions/device-activation-lock-bypass.md).

#### <a name="windows-10-feature-update-deployment-support-for-autopilot-devices---5948137-----"></a>Suporte à implantação de atualização de recursos do Windows 10 para dispositivos Autopilot<!-- 5948137   -->
Agora, o Intune dá suporte a dispositivos registrados no Autopilot usando as [implantações de atualização de recursos do Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates).

As políticas de atualização de recursos do Windows 10 não podem ser aplicadas durante a OOBE (experiência pronta para o uso) do Autopilot e serão aplicadas somente na primeira verificação do Windows Update depois que um dispositivo tiver concluído o provisionamento (o que normalmente leva um dia).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="windows-autopilot-deployment-reports-preview----3856172-----"></a>Relatórios de implantação do Windows Autopilot (versão prévia) <!-- 3856172   -->
Um novo relatório detalha cada dispositivo implantado usando o Windows Autopilot. Para obter mais informações, confira [Relatório de implantação do Autopilot](../enrollment/enrollment-autopilot.md#autopilot-deployments-report).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Controle de acesso baseado em funções

#### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-----"></a>Novo Gerenciador de segurança de ponto de extremidade de função interna do Intune<!--4253397   -->
Uma nova função interna do Intune está disponível: o Gerenciador de segurança de ponto de extremidade. Essa nova função proporciona aos administradores um acesso completo ao nó do Gerenciador de ponto de extremidade no Intune e acesso somente leitura para outras áreas. A função é uma expansão da função "Administrador de Segurança" do Azure AD. Se você tiver somente funções de Administrador global atualmente, nenhuma alteração será necessária. Se você usar funções e quiser a granularidade que o Gerente de segurança de ponto de extremidade oferece, atribua essa função quando ela estiver disponível. Confira mais informações sobre a funções internas em [Controle de acesso baseado em função](role-based-access-control.md).

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

#### <a name="windows-10-administrative-templates-admx-profiles-now-support-scope-tags---5137390---"></a>Os perfis de modelos administrativos (ADMX) do Windows 10 agora dão suporte a marcas de escopo <!--5137390 -->
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

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352------"></a>Atualizamos duas configurações de restrição de dispositivo para corrigir o comportamento em dispositivos iOS e iPadOS<!-- 5701352    -->
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
Agora, você pode usar perfis de certificado PKCS para emitir certificados para *dispositivos* que executam o Android for Work, o iOS/iPadOS e o Windows, quando associados a perfis como os de Wi-Fi e VPN. Anteriormente, essas três plataformas davam suporte apenas para certificados baseados no usuário, com suporte baseado em dispositivo limitado ao macOS.

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
Os clientes do Configuration Manager com o Software Assurance podem obter o cogerenciamento do Intune para computadores Windows 10 sem precisar comprar uma licença adicional do Intune para isso. Os clientes não precisam mais atribuir licenças individuais do Intune/do EMS aos usuários finais para cogerenciar o Windows 10.
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

## <a name="whats-new-archive"></a>Arquivos de Novidades
Para acessar os meses anteriores, confira o [arquivo de Novidades](whats-new-archive.md).

## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](../includes/intune-notices.md)]


