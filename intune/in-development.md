---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 969e7bc4804e1f66230c76d742bec2c67c2fa006
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670936"
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

### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144---"></a>Controlar o comportamento de desinstalação do aplicativo iOS no cancelamento do registro do dispositivo <!-- 3504144 -->
Os administradores poderão gerenciar se um aplicativo é removido ou mantido em um dispositivo quando o registro do dispositivo é cancelado no nível de um usuário ou de um grupo de dispositivos. 

### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Categorizar aplicativos da Microsoft Store para Empresas <!-- 3926922 -->
Você poderá categorizar Microsoft Store para aplicativos de negócios. Para fazer isso, escolha**aplicativos** **cliente aplicativos** > do **Intune** > > selecione uma**categoria**de **informações** > do aplicativo Microsoft Store para o aplicativo de negócios >. No menu suspenso, atribua uma categoria.
### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Configurar conteúdo de notificação do aplicativo para contas da organização <!-- 2576686 -->
As políticas de proteção de aplicativo do Intune (aplicativo) em dispositivos Android e iOS permitirão que você controle o conteúdo de notificação do aplicativo para contas da organização. Este recurso exigirá suporte de aplicativos e pode não estar disponível para todos os aplicativos habilitados para aplicativo. Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Aplicativo do Google Play disponível gerando relatórios para perfis de trabalho do Android <!-- 3041956  -->
Para instalações de aplicativo disponíveis em dispositivos de perfil de trabalho do Android, você pode exibir o status de instalação do aplicativo e a versão instalada de aplicativos gerenciados do Google Play. Para obter mais informações, veja [Como monitorar políticas de proteção de aplicativo](app-protection-policies-monitor.md), [Gerenciar dispositivos de perfil de trabalho do Android com o Intune](android-enterprise-overview.md) e [Tipo de aplicativo do Google Play gerenciado](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809----"></a>Algumas restrições de dispositivo iOS não supervisionadas ficarão supervisionadas somente com a versão iOS 13,0 <!-- 4867809  -->
Algumas configurações serão aplicadas a dispositivos supervisionados com a versão 13,0 do iOS. Essas configurações incluem:

- Loja de Aplicativos, Exibição de Documentos, Jogos
  - Loja de aplicativos
  - Conteúdo explícito do iTunes, música, podcast ou notícias
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

Se essas configurações forem configuradas e atribuídas a dispositivos não supervisionados antes da versão 13,0 do iOS, as configurações ainda serão aplicadas a esses dispositivos não supervisionados. Eles ainda se aplicam após a atualização dos dispositivos para iOS 13,0. Essas restrições são removidas em dispositivos não supervisionados que são armazenados em backup e restaurados. 

Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](device-restrictions-ios.md).

Aplica-se a:  
- iOS 13,0 e mais recente

### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709----"></a>Novas configurações e alterações nas configurações existentes para restringir recursos em dispositivos iOS e macOS <!-- 4867699 4867709  -->
Você poderá criar perfis para restringir as configurações em dispositivos que executam Ios e MacOS (**perfis** > de**configuração** > de dispositivo**Criar perfil** > **Ios** ou **MacOS** para plataforma Digite > **restrições de dispositivo**). Os seguintes recursos serão adicionados:

- Em **restrições**dedispositivo > MacOS**nuvem earmazenamento** >  **, use a nova**configuração deentrega **para** impedir que os usuários iniciem o trabalho em um dispositivo macOS e continuem trabalhando em outro dispositivo macOS ou iOS.
  Para ver as configurações atuais, vá para [Configurações do dispositivo macOS para permitir ou restringir recursos usando o Intune](device-restrictions-macos.md).
- Em**restrições de dispositivo** **Ios** > , há algumas alterações:
  - **Aplicativos internos localizam** **meu iPhone (somente supervisionado)** : nova configuração que bloqueia esse recurso no recurso Localizar meu aplicativo. >  
  - **Os aplicativos** > internos**encontram meus amigos (somente supervisionado)** : nova configuração que bloqueia esse recurso no recurso Localizar meu aplicativo. 
  - **Modificação sem fio** > **do estado de Wi-Fi (apenas**no modo supervisionado): nova configuração que impede que os usuários ativem ou desativem o Wi-Fi no dispositivo.
  - **QuickPath de teclado e dicionário** >  **(somente supervisionado)** : nova configuração que bloqueia o recurso QuickPath.
  - **Nuvem e armazenamento**: a **continuação da atividade** é renomeada para **entrega**.

  Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](device-restrictions-ios.md).

Aplica-se a:  
- macOS 10,15 e mais recente
- iOS 13 e mais recente

### <a name="control-the-apps-files-documents-and-folders-that-open-when-user-signs-in-to-macos-devices---3914202----"></a>Controlar os aplicativos, arquivos, documentos e pastas que são abertos quando o usuário entra em dispositivos macOS <!--3914202  -->
Você poderá habilitar e configurar recursos em dispositivos MacOS (**perfis** > de**configuração** > do dispositivo**Criar perfil** > **MacOS** para plataforma > **recursos do dispositivo** para tipo de perfil). 

Haverá novas configurações de itens de logon para controlar quais aplicativos, arquivos, documentos e pastas serão abertos quando um usuário entrar no dispositivo registrado. 

Veja as configurações atuais acessando [Configurações de recurso de dispositivo macOS no Intune](macos-device-features-settings.md).

Aplica-se a:  
- macOS

### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946----"></a>Novos recursos para dispositivos Android Enterprise dedicados no modo de vários aplicativos <!-- 3755304 3041943 3041946  -->
Você poderá controlar recursos e configurações em uma experiência de estilo de quiosque em seus dispositivos Android Enterprise dedicados. Para fazer isso, escolha **configuração** > do dispositivo**perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **somente proprietário do dispositivo, restrições de dispositivo** para o tipo de perfil.

Os seguintes recursos serão adicionados:
- **Vários aplicativos** > dedicadosde**dispositivos**: o**botãoHome** virtual pode ser mostrado passando o dedo para cima no dispositivo ou flutuando na tela para que os usuários possam movê-lo.
- **Dispositivos** > dedicados**vários aplicativos**: o **acesso à lanterna** permite que os usuários usem a lanterna. 
- **Vários aplicativos** > dedicadosde**dispositivos** :**ocontrole** de volume de mídia permite que os usuários controlem o volume de mídia do dispositivo usando um controle deslizante. 
- **Dispositivos** > **dedicadosmultiaplicativo**: habilitar uma proteção de tela, carregar uma imagem personalizada e controlar quando a proteção de tela é mostrada.

Veja as configurações atuais acessando [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](device-restrictions-android-for-work.md#dedicated-device-settings).

Aplica-se a:  
- Dispositivos Android Enterprise dedicados

### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215----"></a>Novos perfis de aplicativo e configuração para dispositivos Android Enterprise totalmente gerenciados <!-- 3574215  -->
Usando perfis, você poderá definir configurações que aplicam configurações de VPN, email e Wi-Fi aos dispositivos Android Enterprise totalmente gerenciados. Você poderá:
- Use perfis de aplicativo para implantar configurações de email do Outlook, Gmail e nove work.
- Use perfis de configuração de dispositivo para implantar configurações de certificado raiz confiável.
- Use perfis de configuração de dispositivo para implantar configurações de VPN e Wi-Fi.

Os usuários serão autenticados com seu nome de usuário e senha para perfis de VPN, Wi-Fi e de email. Atualmente, a autenticação baseada em certificado não está disponível. 

Aplica-se a:  
- Android Enterprise totalmente gerenciado

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Suporte para perfis de VPN IKEv2 para iOS <!-- 1943438 -->
Você poderá criar perfis VPN para o cliente VPN nativo do iOS usando o protocolo IKEv2. IKEv2 é um novo tipo de conexão em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **VPN** para tipo de perfil > **Configurações**.

Esses perfis VPN configuram o cliente VPN nativo. Portanto, nenhum aplicativo de cliente de VPN é instalado ou enviado por push a dispositivos gerenciados. Esse recurso exige que dispositivos sejam registrados no Intune (registro do MDM).

Para ver as configurações de VPN atuais que você pode configurar, vá para [Definir configurações de VPN em dispositivos iOS no Microsoft Intune](vpn-settings-ios.md).

Aplica-se a: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registro de dispositivo

### <a name="skip-more-screens-in-setup-assistant---4877451---"></a>Ignorar mais telas no assistente de configuração <!--4877451 -->
Você poderá definir perfis de Programa de registro de dispositivos para ignorar as seguintes telas do assistente de configuração: 
- Tempo da Tela
- Configuração do touch ID

Para fazer isso, acesse **registro** > de dispositivo inscrição da**Apple** > tokens do**programa de registro** > escolha um token > **perfis** > escolha um perfil > **Propriedades** > **Editar** ao lado de **personalização do assistente de configuração**.
Para obter mais informações sobre a personalização do assistente de configuração, consulte [criar um perfil de registro da Apple ](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

### <a name="android-enrollment-device-administrator-support----4869749----"></a>Suporte ao administrador do dispositivo de registro do Android <!-- 4869749  -->
A opção de registro de administrador de dispositivo Android será adicionada à página de registro do Android (registro**Android**de**registro** > de dispositivo do**Intune** > ). O administrador do dispositivo Android ainda estará habilitado por padrão para todos os locatários.  

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Para dispositivos iOS, personalize a tela de privacidade do processo de registro do Portal da Empresa <!-- 4394993  -->
Usando a redução, você poderá personalizar a tela de privacidade do Portal da Empresa que os usuários finais veem durante o registro do iOS. Especificamente, você poderá personalizar a lista de coisas que sua organização não pode ver ou fazer no dispositivo.

<!-- ***********************************************-->
## <a name="device-management"></a>Gerenciamento de dispositivos

### <a name="build-number-included-on-android-device-hardware-page----4461910----"></a>Número de Build incluído na página de hardware do dispositivo Android <!-- 4461910  -->
Uma nova entrada na página de hardware para cada dispositivo Android incluirá o número de Build do sistema operacional do dispositivo.

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Configurar o limite de tempo de limpeza de dispositivo automático para 30 dias <!--4231059  -->
Você poderá definir o limite de tempo de limpeza do dispositivo automático como 30 dias (em vez do limite atual de 90 dias) após a última entrada. Para fazer isso, vá para**dispositivos** > do **Intune** > **Configurar** > **regras de limpeza do dispositivo**.

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Controle de acesso baseado em função

### <a name="default-scope-tag----3702875---"></a>Marca de escopo padrão <!-- 3702875 -->
Uma nova marca de escopo padrão interna estará disponível. Todos os objetos do Intune não marcados que dão suporte a marcas de escopo serão automaticamente atribuídos à marca de escopo padrão. A marca de escopo **padrão** será adicionada a todas as atribuições de função existentes para manter a paridade com a experiência de administração hoje. Se você não quiser que um administrador Veja objetos do Intune com marcas de escopo padrão, remova a marca de escopo padrão da atribuição de função. Esse recurso é semelhante ao recurso de escopos de segurança no System Center Configuration Manager.

<!-- ***********************************************-->
## <a name="security"></a>Segurança

### <a name="import-and-export-security-baselines------3408610------------"></a>Importar e exportar linhas de base de segurança    <!--3408610          -->  
Estamos adicionando a capacidade de exportar e importar linhas de base de segurança. Esse recurso permitirá que você faça suas personalizações com você e compartilhe-as entre os ambientes do Intune.

<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.




