---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c2b9429bf5b50ac5e416c4a7b356627e9cc9fb1
ms.sourcegitcommit: f75386986d24e7d5dd63a3f1a0a014cb52056063
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560114"
---
# <a name="in-development-for-microsoft-intune---august-2019"></a>Em desenvolvimento para o Microsoft Intune – agosto de 2019

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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Configurar conteúdo de notificação do aplicativo para contas da organização <!-- 2576686 -->
As políticas de proteção de aplicativo do Intune (aplicativo) em dispositivos Android e iOS permitirão que você controle o conteúdo de notificação do aplicativo para contas da organização. Este recurso exigirá suporte de aplicativos e pode não estar disponível para todos os aplicativos habilitados para aplicativo. Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Aplicativo do Google Play disponível gerando relatórios para perfis de trabalho do Android <!-- 3041956  -->
Para instalações de aplicativo disponíveis em dispositivos de perfil de trabalho do Android, você pode exibir o status de instalação do aplicativo e a versão instalada de aplicativos gerenciados do Google Play. Para obter mais informações, veja [Como monitorar políticas de proteção de aplicativo](app-protection-policies-monitor.md), [Gerenciar dispositivos de perfil de trabalho do Android com o Intune](android-enterprise-overview.md) e [Tipo de aplicativo do Google Play gerenciado](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Suporte para perfis de VPN IKEv2 para iOS <!-- 1943438 -->
Você poderá criar perfis VPN para o cliente VPN nativo do iOS usando o protocolo IKEv2. IKEv2 é um novo tipo de conexão em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **VPN** para tipo de perfil > **Configurações**.

Esses perfis VPN configuram o cliente VPN nativo. Portanto, nenhum aplicativo de cliente de VPN é instalado ou enviado por push a dispositivos gerenciados. Esse recurso exige que dispositivos sejam registrados no Intune (registro do MDM).

Para ver as configurações de VPN atuais que você pode configurar, vá para [Definir configurações de VPN em dispositivos iOS no Microsoft Intune](vpn-settings-ios.md).

Aplica-se a: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registro de dispositivo

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Para dispositivos iOS, personalize a tela de privacidade do processo de registro do Portal da Empresa <!-- 4394993  -->
Usando a redução, você poderá personalizar a tela de privacidade do Portal da Empresa que os usuários finais veem durante o registro do iOS. Especificamente, você poderá personalizar a lista de coisas que sua organização não pode ver ou fazer no dispositivo.

<!-- ***********************************************-->
## <a name="security"></a>Segurança

### <a name="import-and-export-security-baselines------3408610------------"></a>Importar e exportar linhas de base de segurança    <!--3408610          -->  
Estamos adicionando a capacidade de exportar e importar linhas de base de segurança. Esse recurso permitirá que você faça suas personalizações com você e compartilhe-as entre os ambientes do Intune.

<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.




