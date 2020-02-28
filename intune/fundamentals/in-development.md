---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7113552e09a7c7fa145a452e56575bfaf5297c3e
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514550"
---
# <a name="in-development-for-microsoft-intune---february-2020"></a>Em desenvolvimento para o Microsoft Intune – fevereiro de 2020

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

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Exibir notificações do aplicativo Portal da Empresa no Windows<!-- 1808082  -->
Atualizaremos o aplicativo Portal da Empresa em dispositivos Windows para exibir notificações do sistema para os usuários, mesmo quando o aplicativo estiver fechado. A atualização mostrará notificações dos aplicativos disponíveis somente quando o status da instalação for concluído ou com falha. O aplicativo Portal da Empresa não mostrará notificações de aplicativos necessários. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Exibir mensagens de status de instalação para o aplicativo Portal da Empresa<!-- 2514416  -->
O aplicativo Portal da Empresa mostrará mensagens de status de instalação de aplicativos adicionais aos usuários finais. As seguintes condições se aplicarão a novos recursos de dependência do Win32:
- Falha ao instalar o aplicativo. As dependências definidas pelo administrador não foram atendidas.

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Redirecionar clipes da Web para o Microsoft Edge em dispositivos iOS/iPadOS<!-- 5455276 -->
Os clipes da Web, que atuam como aplicativos Web fixados em dispositivos iOS/iPadOS, precisarão ser atualizados. Clipes da Web implantados recentemente serão abertos no Microsoft Edge em vez do Intune Managed Browser se for necessário abrir em um navegador protegido. Você precisa redirecionar os clipes da Web preexistentes para garantir que eles sejam abertos no Microsoft Edge em vez do Managed Browser.

### <a name="macos-company-portal-user-experience-improvements---5568987---"></a>Aprimoramentos na experiência do usuário do Portal da Empresa do macOS<!-- 5568987 -->
Estamos fazendo aprimoramentos na experiência de registro do dispositivo macOS e no aplicativo Portal da Empresa para Mac. Você pode esperar o seguinte:
- Uma melhor experiência do **Microsoft AutoUpdate** durante o registro, que garantirá que os usuários tenham a versão mais recente do Portal da Empresa.
- Uma etapa de verificação de conformidade aprimorada durante o registro.
- Suporte para IDs de Incidente copiadas, para que os usuários possam enviar erros de seus dispositivos para a equipe de suporte da empresa mais rapidamente.

Para obter mais informações sobre o registro e o aplicativo Portal da Empresa para Mac, confira Registrar seu dispositivo macOS usando o aplicativo Portal da Empresa (https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp). 


### <a name="screen-removed-from-company-portal-android-work-profile-enrollment--6103987---"></a>Tela removida do Portal da Empresa, registro de perfil de trabalho do Android<!--6103987 -->
A tela **O que vem a seguir?** será removida do fluxo de registro do perfil de trabalho do Android no Portal da Empresa, para simplificar a experiência do usuário. Acesse [Registrar com o perfil de trabalho do Android]( https://docs.microsoft.com/intune-user-help/enroll-device-android-work-profile) para ver o fluxo de registro do perfil de trabalho do Android atual.

### <a name="microsoft-defender-advanced-threat-protection-atp-app-for-macos---5424518-idready---"></a>Aplicativo ATP (Proteção Avançada contra Ameaças) do Microsoft Defender para macOS<!-- 5424518 idready -->
O Intune fornecerá uma maneira fácil de implantar o aplicativo ATP (Proteção Avançada contra Ameaças) do Microsoft defender para macOS em dispositivos Mac gerenciados. Para saber mais, confira [Proteção Avançada contra Ameaças do Microsoft Defender para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac). 

<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Perfil de configuração do dispositivo de rede com fios para dispositivos macOS<!-- 3508686  -->
Um novo perfil de configuração de dispositivo macOS estará disponível, com a capacidade de configurar redes com fio (**Configuração de dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Rede com fio** para o tipo de perfil). Use esse recurso para criar perfis 802.1x para gerenciar redes com fio e implantar essas redes em seus dispositivos macOS.

Aplica-se a:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932-idready---"></a>Perfis VPN com conexões VPN IKEv2 podem usar o Always On com dispositivos iOS/iPadOS <!-- 1947932 idready -->
Em dispositivos iOS/iPadOS, você pode criar um perfil de VPN que usa uma conexão IKEv2 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **VPN** para o tipo de perfil). Em uma atualização futura, você poderá configurar o AlwaysOn com IKEv2. Quando configurados, os perfis de VPN IKEv2 se conectam automaticamente e permanecem conectados (ou reconectam-se rapidamente) à VPN. Ele permanece conectado mesmo ao se movimentar entre redes ou reiniciar dispositivos.

No iOS/iPadOS, a VPN AlwaysOn é limitada a perfis IKEv2.

Para ver as configurações de IKEv2 atuais que você pode configurar, vá para [Adicionar configurações de VPN em dispositivos iOS/iPadOS no Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Aplica-se a:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Experiência aprimorada da interface do usuário ao criar perfis de configuração em dispositivos iOS/iPadOS e macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Quando você criar um perfil para dispositivos iOS/iPadOS ou macOS, a experiência no Centro de Administração do Gerenciamento de Ponto de Extremidade será atualizada. Essa alteração afeta os seguintes perfis de configuração de dispositivo (**Dispositivos** > **Perfis de Configuração** > **Criar perfil** > **iOS** ou **macOS** para plataforma):

- Personalizado: iOS/iPadOS, macOS
- Recursos do dispositivo: iOS/iPadOS, macOS
- Restrições de dispositivo: iOS/iPadOS, macOS
- Endpoint Protection: macOS
- Extensões: macOS
- Arquivo de preferência: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Experiência aprimorada da interface do usuário ao criar perfis de configuração OEMConfig em dispositivos Android Enterprise<!-- 5568645 idready  -->
Quando você criar ou editar um perfil OEMConfig para dispositivos Android Enterprise, a experiência no Centro de Administração do Gerenciamento de Ponto de Extremidade será atualizada. A experiência atualizada fornecerá um resumo das configurações que você definiu em um relance. Essa alteração afeta o perfil de configuração de dispositivo OEMConfig (**Dispositivos** > **Perfis de configuração** > **Criar perfil** > **Android Enterprise** para a plataforma > **OEMConfig** para o tipo de perfil).

Esse recurso aplica-se a:
- Android Enterprise 


<!-- ***********************************************-->
<!--## Device enrollment-->


<!-- ***********************************************-->
## <a name="device-management"></a>Gerenciamento de dispositivo

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Alterar o Usuário Primário para dispositivos Windows <!-- 3794742 -->
Você poderá alterar o Usuário Primário para dispositivos Ingressados no Azure AD e Windows híbridos. Para fazer isso, acesse **Intune** > **Dispositivos** > **Todos os dispositivos** > escolher um dispositivo > **Propriedades** > **Usuário Primário**. 

### <a name="serial-number-on-the-apple-mdm-push-certificate-page--5947765---"></a>Número de série na página Apple MDM Push Certificate<!--5947765 -->
A página Apple MDM Push Certificate mostrará o número de série. O número de série é necessário para recuperar acesso ao Apple MDM Push Certificate em caso de perda do acesso à ID da Apple que criou o certificado. Para ver o número de série, acesse **Dispositivos** > **iOS** > **Registro do iOS** > **Apple MDM Push Certificate**.

### <a name="choose-which-iosipados-updates-to-push-to-enrolled-devices--5879689---"></a>Escolher quais atualizações do iOS/iPadOS enviar por push a dispositivos registrados<!--5879689 -->
Você poderá escolher uma atualização específica do iOS/iPadOS para enviar por push para os dispositivos registrados usando o Apple Business Manager ou o Apple School Manager. Esses dispositivos devem ter uma política de configuração de dispositivo definida para atrasar a visibilidade da atualização de software por algum número de dias. Para ver esse recurso, acesse MEM > **Dispositivos** > **iOS** > **Atualizar políticas para iOS/iPadOS** > **Criar perfil**.

### <a name="new-update-schedule-options-for-pushing-os-updates-to-enrolled-iosipados-devices--5879689--"></a>Novas opções de agendamento de atualização para enviar por push atualizações do sistema operacional para dispositivos iOS/iPadOS registrados<!--5879689-->
Você poderá usar as opções a seguir ao agendar atualizações do sistema operacional para dispositivos iOS/iPadOS. Isso se aplica a dispositivos que usavam os tipos de registro Apple Business Manager ou Apple School Manager.
- Atualizar no próximo check-in
- Atualizar durante o horário agendado
- Atualizar fora do horário agendado

Para as duas últimas opções, você pode criar várias janelas de tempo.

Para ver as novas opções, acesse MEM > **Dispositivos** > **iOS** > **Atualizar políticas para iOS/iPadOS** > **Criar perfil**.


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitoramento e solução de problemas

### <a name="improved-intune-reporting-experience---3791418-idready---"></a>Experiência aprimorada de relatórios do Intune<!-- 3791418 idready -->
O Intune agora oferece uma experiência aprimorada de relatórios, incluindo novos tipos de relatórios, melhor organização de relatórios, visualizações mais focadas, funcionalidade aprimorada de relatórios e dados mais consistentes e oportunos. A experiência de relatório passará da versão prévia pública para a GA (disponibilidade geral). Além disso, a versão GA terá suporte à localização, correções de bug, aprimoramentos de design e dados de conformidade de dispositivo agregados em blocos no [centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

Novos tipos de relatório se concentram no seguinte:
- **Operacional** - fornece novos registros com foco de integridade negativa. 
- **Organizacional** - fornece um resumo mais amplo do estado geral.
- **Histórico** – fornece padrões e tendências ao longo de um período.
- **Especialista** – permite que você use dados brutos para criar seus próprios relatórios personalizados.

O primeiro conjunto de novos relatórios se concentra na conformidade do dispositivo. Para saber mais, confira [Blog - Estrutura de relatórios do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) e [Relatórios do Intune](~/fundamentals/reports.md).



<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Controle de acesso baseado em funções

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Futuras alterações na interface do usuário de Funções do Intune<!--5801612 idready-->
A interface do usuário do [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Administração de locatários** > **Funções** será alterada para um design mais amigável e intuitivo. Essa experiência fornece as mesmas configurações e detalhes que você usa agora, mas emprega um processo semelhante ao de um assistente.


<!-- ***********************************************-->
## <a name="security"></a>Segurança

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Suporte para credenciais derivadas em dispositivos Android COBO<!--4839592-->
Você poderá usar credenciais derivadas em dispositivos Android Enterprise totalmente gerenciados. Será incluído suporte para recuperar uma credencial derivada para o Entrust Datacard, o Intercede e o DISA Purebred. Você poderá usar a credencial derivada para autenticação do aplicativo, Wi-Fi, VPN ou assinatura S/MIME e/ou criptografia com aplicativos que têm suporte.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Usar a política de antivírus para gerenciar as configurações do Antivírus Microsoft Defender e da experiência de Segurança do Windows<!--6131401 -->
No nó *Segurança do ponto de extremidade*, você poderá definir as configurações para **Antivírus**. Ao configurar a política para antivírus, você definirá configurações para seus dispositivos Windows 10 por meio de dois tipos de perfil:

- Microsoft Defender Antivírus: gerencie configurações para proteção de nuvem, exclusões do Antivírus, correção, opções de verificação e muito mais.
- Experiência de Segurança do Windows: gerencie como os usuários veem as configurações de Segurança do Windows em seus dispositivos. Você poderá configurar o que os usuários finais podem ver na central de Segurança do Microsoft Defender e as notificações recebidas. 

<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Consulte também
Para saber os detalhes dos desenvolvimentos mais recentes, veja [Novidades do Microsoft Intune](whats-new.md).


