---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/07/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d71ae3c15dddedd5d9ebfaf06fcae25af89f6b82
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912617"
---
# <a name="in-development-for-microsoft-intune---january-2020"></a>Em desenvolvimento para o Microsoft Intune – janeiro de 2020

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

### <a name="retarget-web-clips-to-microsoft-edge-on-ios-devices---5455276---"></a>Redirecionar clipes da Web para o Microsoft Edge em dispositivos iOS<!-- 5455276 -->
Os clipes da Web, que atuam como aplicativos Web fixados em dispositivos iOS, precisarão ser atualizados. Clipes da Web implantados recentemente serão abertos no Microsoft Edge em vez do Intune Managed Browser se for necessário abrir em um navegador protegido. Você precisa redirecionar os clipes da Web preexistentes para garantir que eles sejam abertos no Microsoft Edge em vez do Managed Browser. 


<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Perfil de configuração do dispositivo de rede com fios para dispositivos macOS<!-- 3508686  -->
Um novo perfil de configuração de dispositivo macOS estará disponível, com a capacidade de configurar redes com fio (**Configuração de dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Rede com fio** para o tipo de perfil). Use esse recurso para criar perfis 802.1x para gerenciar redes com fio e implantar essas redes em seus dispositivos macOS.

Aplica-se a:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-ios-devices----1947932-idready---"></a>Perfis VPN com conexões VPN IKEv2 podem usar o Always On com dispositivos iOS <!-- 1947932 idready -->
Em dispositivos iOS, você pode criar um perfil de VPN que usa uma conexão IKEv2 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS/iPadOS** para a plataforma > **VPN** para o tipo de perfil). Em uma atualização futura, você poderá configurar o AlwaysOn com IKEv2. Quando configurados, os perfis de VPN IKEv2 se conectam automaticamente e permanecem conectados (ou reconectam-se rapidamente) à VPN. Ele permanece conectado mesmo ao se movimentar entre redes ou reiniciar dispositivos.

No iOS, a VPN AlwaysOn é limitada a perfis IKEv2.

Para ver as configurações de IKEv2 atuais que você pode configurar, vá para [Adicionar configurações de VPN em dispositivos iOS no Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Aplica-se a:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-ios-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Experiência aprimorada da interface do usuário ao criar perfis de configuração em dispositivos iOS e macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Quando você criar um perfil para dispositivos iOS ou macOS, a experiência no Centro de Administração do Gerenciamento de Ponto de Extremidade será atualizada. Essa alteração afeta os seguintes perfis de configuração de dispositivo (**Dispositivos** > **Perfis de Configuração** > **Criar perfil** > **iOS** ou **macOS** para plataforma):

- Personalizado: iOS, macOS
- Recursos do dispositivo: iOS, macOS
- Restrições de dispositivo: iOS, macOS
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
<!--## Device management-->



<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Controle de acesso baseado em funções

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Futuras alterações na interface do usuário de Funções do Intune<!--5801612 idready-->
A interface do usuário do [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Administração de locatários** > **Funções** será alterada para um design mais amigável e intuitivo. Essa experiência fornece as mesmas configurações e detalhes que você usa agora, mas emprega um processo semelhante ao de um assistente.


<!-- ***********************************************-->
## <a name="security"></a>Segurança

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Suporte para credenciais derivadas em dispositivos Android COBO<!--4839592-->
Você poderá usar credenciais derivadas em dispositivos Android Enterprise totalmente gerenciados. Será incluído suporte para recuperar uma credencial derivada para o Entrust Datacard, o Intercede e o DISA Purebred. Você poderá usar a credencial derivada para autenticação do aplicativo, Wi-Fi, VPN ou assinatura S/MIME e/ou criptografia com aplicativos que têm suporte. 

<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Consulte também
Para saber os detalhes dos desenvolvimentos mais recentes, veja [Novidades do Microsoft Intune](whats-new.md).


