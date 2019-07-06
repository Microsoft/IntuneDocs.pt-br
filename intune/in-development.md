---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7dd6f62cb53dd0cc373fb3f2ffa7d9434b135cd
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494253"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>Em desenvolvimento para o Microsoft Intune – julho de 2019

Para ajudá-lo em sua preparação e planejamento, esta página listas atualizações e recursos da interface do usuário do Intune que estão em desenvolvimento, mas ainda não foram liberados. Além disso:

- Se prevermos que você precisará agir antes de uma alteração, publicaremos uma postagem complementar do Centro de Mensagens do Office.
- Quando um recurso é lançado em produção, seja como versão prévia ou em disponibilidade geral, a descrição do recurso sairá dessa página, indo para a [página Novidades](whats-new.md).
- Esta página e a [página Novidades](whats-new.md) são atualizadas periodicamente. Volte a ela para verificar se há atualizações adicionais.
- Consulte o [Roteiro M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para entregas estratégicas e linhas do tempo.

> [!Note]
> Esses itens refletem a expectativas atuais da Microsoft sobre as funcionalidades do Intune que estarão presentes em uma versão futura. As datas e os recursos individuais podem mudar. Nem todos os itens em desenvolvimento têm uma descrição de recurso nesta página.

**RSS feed**: receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Gerenciamento de aplicativos


### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Notificações personalizadas para usuários e grupos    <!-- 16766574   -->
Em breve, você poderá enviar notificações por push de ad-hoc personalizado do aplicativo de Portal da empresa aos usuários em dispositivos iOS e Android gerenciados com o Intune. Essas notificações personalizadas não estão vinculadas a recursos específicos do Intune e pode ser usadas para qualquer finalidade necessárias, incluindo notificações gerais que você deseja enviar para alguns ou todos os seus funcionários.  

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Configurar o conteúdo de notificação de aplicativo para contas da organização <!-- 2576686 -->
Políticas de proteção de aplicativo do Intune (aplicativo) em dispositivos Android e iOS permitirá que você controle conteúdo da notificação de aplicativo para contas da organização. Esse recurso exige suporte de aplicativos e pode não estar disponível para todos os aplicativos do aplicativo habilitado. Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Aplicativo do Google Play disponível gerando relatórios para perfis de trabalho do Android <!-- 3041956  -->
Para instalações de aplicativo disponíveis em dispositivos de perfil de trabalho do Android, você pode exibir o status de instalação do aplicativo, bem como a versão instalada de aplicativos gerenciados do Google Play. Para obter mais informações, veja [Como monitorar políticas de proteção de aplicativo](app-protection-policies-monitor.md), [Gerenciar dispositivos de perfil de trabalho do Android com o Intune](android-enterprise-overview.md) e [Tipo de aplicativo do Google Play gerenciado](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuração do dispositivo


### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Suporte para perfis de VPN IKEv2 para iOS <!-- 1943438 -->
Você poderá criar perfis VPN para o cliente VPN nativo do iOS usando o protocolo IKEv2. IKEv2 é um novo tipo de conexão em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **VPN** para tipo de perfil > **Configurações**.

Esses perfis VPN configuram o cliente VPN nativo. Portanto, nenhum aplicativo de cliente de VPN é instalado ou enviado por push a dispositivos gerenciados. Esse recurso exige que dispositivos sejam registrados no Intune (registro do MDM).

Para ver as configurações de VPN atuais que você pode configurar, vá para [Definir configurações de VPN em dispositivos iOS no Microsoft Intune](vpn-settings-ios.md).

Aplica-se a: iOS

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 -->
Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma). Você poderá criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Aplica-se a: 
- Windows 10 e posterior

### <a name="administrative-templates-for-group-policy---------3510695---"></a>Modelos administrativos da Política de Grupo     <!--  3510695 -->
Para ajudar a aprimorar a segurança de dispositivos na nuvem, serão lançados modelos administrativos que permitirão usar o Intune para definir configurações de Política de Grupo selecionadas para computadores Windows.  Esses modelos usam o CSP (Provedor de Serviço de Configuração) de Política para fornecer até 2.500 configurações adicionais do Office, do Windows e do OneDrive.

### <a name="manage-filevault-for-macos-------3858502--1210104-----"></a>Gerenciar o FileVault para macOS   <!--  3858502 + 1210104   -->
Você poderá usar um perfil de configuração de dispositivo do Intune endpoint protection para gerenciar a criptografia de chave FileVault para dispositivos macOS. Isso inclui a caução de exibição do e girar as chaves de criptografia de seus dispositivos corporativos. Os usuários finais poderão recuperar essas chaves por meio do site Portal da empresa.

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Configurações avançadas para o Windows Defender Firewall   <!--  1311949     -->
Como uma versão prévia pública, em breve, você poderá usar o Intune para gerenciar as regras de firewall personalizadas em clientes do Windows Defender.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Novo designer de configuração ao criar um perfil de OEMConfig Android Enterprise <!-- 3712769  -->
No Intune, você pode criar um perfil de configuração de dispositivo que usa um aplicativo OEMConfig (configuração do dispositivo > perfis > Criar perfil > Android enterprise para plataforma > OEMConfig para tipo de perfil). Quando você fizer isso, um editor de JSON é aberto com um modelo e os valores para que você possa alterar. Esta atualização inclui um Designer de configuração com uma experiência de usuário aprimorada que mostra os detalhes inseridos no aplicativo, incluindo de títulos, descrições e muito mais. O editor de JSON ainda está disponível e mostra todas as alterações feitas no Designer de configuração.

Para ver as configurações atuais, acesse [usar e gerenciar dispositivos Android Enterprise com OEMConfig](android-oem-configuration-overview.md).

Aplica-se a: Android Enterprise


<!-- ***********************************************-->
## <a name="device-management"></a>Gerenciamento de dispositivos

### <a name="improve-device-location---3855417---"></a>Melhorar a localização do dispositivo<!-- 3855417 -->
Você poderá ampliar para as coordenadas exatas de um dispositivo usando o **localizar dispositivo** ação. Para obter mais informações sobre como localizar dispositivos iOS perdidos, consulte [localizar dispositivos iOS perdidos](device-locate.md).

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Configurar o limite de tempo de limpeza automática do dispositivo até 30 dias <!--4231059  -->
Você poderá definir o limite de tempo de limpeza de dispositivo automático tão curto como 30 dias (em vez de limite atual de 90 dias) após a última entrada do. Para fazer isso, vá para **Intune** > **dispositivos** > **instalação** > **limpa-se as regras de dispositivo**.


<!-- ***********************************************-->
## <a name="security"></a>Segurança

### <a name="import-and-export-security-baselines------3408610------------"></a>Importar e exportar linhas de base de segurança    <!--3408610          -->  
Estamos adicionando a capacidade de exportar e importar linhas de base de segurança para que você possa levar suas personalizações com você e compartilhá-los entre os ambientes do Intune.



<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


