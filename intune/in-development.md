---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c8a7be6646c0035eaefed6d61d749c8469c8a4e
ms.sourcegitcommit: 119962948045079022aa48f968dde3e961d7cd0c
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67031660"
---
# <a name="in-development-for-microsoft-intune---june-2019"></a>Em desenvolvimento para o Microsoft Intune – junho de 2019

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
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- ***********************************************-->
### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Os usuários de dispositivos podem exibir todos os aplicativos gerenciados que você instalou ou tentou instalar <!-- 2352913 -->
O Portal da Empresa para Windows listará todos os aplicativos gerenciados (obrigatórios e disponíveis) instalados em um dispositivo do usuário. Os usuários poderão exibir tentativas e instalações de aplicativos pendentes e o status atual. Se a sua organização não torna aplicativos obrigatórios ou disponíveis, os usuários veem uma mensagem explicando que nenhum aplicativo da empresa foi instalado. Os usuários também poderão classificar ou filtrar seus aplicativos por status de instalação.

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Configurar que navegador tem permissão para vincular a dados da organização <!-- 3145939 -->
APP (Políticas de Proteção de Aplicativo) do Intune em dispositivos Android e iOS permitirão que você transfira links da Web da organização para um navegador específico além do Intune Managed Browser do ou Microsoft Edge.  Para saber mais sobre APP, veja [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

#### <a name="installed-apps-page-on-the-company-portal-website-----4224326---"></a>Página de aplicativos instalados no site do Portal da Empresa  <!-- 4224326 -->
O [site do Portal da Empresa](https://portal.manage.microsoft.com/) incluirá uma nova página para mostrar aos usuários todos os aplicativos instalados em seu dispositivo. Essa lista inclui os aplicativos disponíveis e os aplicativos necessários para sua organização. Nessa página, os usuários poderão ver os status de instalação e do requisito dos aplicativos em seu dispositivo. Para obter mais informações sobre o site Portal da Empresa, veja [Como usar o site do Portal da Empresa do Intune](/intune-user-help/using-the-intune-company-portal-website) e [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](company-portal-app.md).

#### <a name="call-graph-api-read-operations-from-an-application-without-user-credentials----4655885---"></a>Chamar operações de leitura da API do Graph de um aplicativo sem credenciais de usuário <!-- 4655885 -->
Aplicativos poderão chamar operações de leitura da API do Graph do Intune com identidade de aplicativo sem credenciais de usuário. Para obter mais informações, veja [Obter acesso sem um usuário](https://docs.microsoft.com/graph/auth-v2-service).

<!-- ***********************************************-->
### <a name="device-configuration"></a>Configuração do dispositivo


#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Suporte para perfis de VPN IKEv2 para iOS <!-- 1943438 -->
Você poderá criar perfis VPN para o cliente VPN nativo do iOS usando o protocolo IKEv2. IKEv2 é um novo tipo de conexão em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **VPN** para tipo de perfil > **Configurações**.

Esses perfis VPN configuram o cliente VPN nativo. Portanto, nenhum aplicativo de cliente de VPN é instalado ou enviado por push a dispositivos gerenciados. Esse recurso exige que dispositivos sejam registrados no Intune (registro do MDM).

Para ver as configurações de VPN atuais que você pode configurar, vá para [Definir configurações de VPN em dispositivos iOS no Microsoft Intune](vpn-settings-ios.md).

Aplica-se a: iOS

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----20430240---"></a>Definir configurações para extensões de kernel em dispositivos macOS <!-- 20430240 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma). Uma atualização futura incluirá um novo grupo de configurações que permite configurar e usar extensões de kernel em seus dispositivos.

Aplica-se a: macOS 10.13.2 e posteriores

#### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Suporte de linha de base para pesquisa de palavra-chave  <!-- 3082036         -->
Em breve, ao criar ou editar um perfil de linha de base de segurança, você poderá usar a *pesquisa* para filtrar as configurações exibidas no console.   

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 -->
Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma). Você poderá criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Aplica-se a: 
- Windows 10 e posterior

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002----"></a>Configuração de Aplicativos somente da loja para dispositivos Windows 10 incluem mais opções de configuração <!-- 2697002  -->

Quando você cria um perfil de restrições de dispositivo para dispositivos Windows, pode usar a configuração **Somente aplicativos da loja** para que os usuários instalem somente aplicativos da Windows Store (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Restrições de dispositivo** para tipo de perfil). Em uma atualização futura, essa configuração será expandida para dar suporte a mais opções. 

Para ver as configurações atuais, vá para [Configurações do dispositivo Windows 10 (e mais recentes) permitir ou restringir recursos usando o Intune](device-restrictions-windows-10.md#app-store).

Aplica-se ao Windows 10 e posteriores

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Implantar vários perfis de dispositivo de extensões de mobilidade Zebra em um dispositivo, mesmo grupo de usuários ou mesmo grupo de dispositivos <!-- 4089955 -->
No Intune, você pode usar extensões de mobilidade Zebra (MX) em um perfil de configuração do dispositivo para personalizar as configurações ou adicionar as configurações não internas do Intune. No momento, você pode implantar um perfil em um único dispositivo. Em uma atualização futura, você poderá implantar vários perfis para:

- O mesmo grupo de usuários
- O mesmo grupo de dispositivos
- Um único dispositivo

[Usar e gerenciar dispositivos Zebra com o Zebra Mobility Extensions no Microsoft Intune](android-zebra-mx-overview.md) mostra como usar o MX no Intune.

Aplica-se a: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Algumas configurações de quiosque em dispositivos iOS são definidas usando "Bloquear", substituindo "Permitir" <!-- 4404075  -->
Quando você cria um perfil de restrições de dispositivo em dispositivos iOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para plataforma > **Restrições de dispositivo** para tipo de perfil > **Quiosque**), define **Bloqueio automático**, **botão de Toque**, **Rotação da tela**, **botão Suspender tela** e **botões de Volume**. 

Atualmente, essas configurações são definidas usando **Permitir** (bloqueia o recurso) ou **Não configurado** (permite o recurso). Em uma atualização futura, os valores serão **Bloquear** (bloqueia o recurso) ou **Não configurado** (permite o recurso).

Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos](device-restrictions-ios.md). 

Aplica-se a: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704----"></a>Use o Face ID para autenticação de senha em dispositivos iOS <!-- 4490704  -->
Quando você cria um perfil de restrições de dispositivo para dispositivos iOS, pode usar uma impressão digital para uma senha. Em uma atualização futura, as configurações de senha de impressão digital também permitirão reconhecimento facial (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** tipo de perfil > **Senha**). Como resultado, as configurações a seguir estão mudando:

- **Desbloqueio por impressão digital** agora é **Desbloqueio por Touch ID e Face ID**.
- **Modificação de impressão digital (somente supervisionada)** agora é **Modificação de Touch ID e Face ID (somente supervisionada)** .

O Face ID está disponível no iOS 11.0 e posteriores. Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](device-restrictions-ios.md#password).

Aplica-se a: iOS

#### <a name="apps-feature-is-dependent-on-ratings-region-when-restricting-gaming-and-app-store-features-on-ios-devices----4593948----"></a>O recurso do aplicativo depende da região de classificações ao restringir recursos da loja de aplicativo e jogos em dispositivos iOS <!-- 4593948  -->
Em dispositivos iOS, você pode permitir ou restringir recursos relacionados a jogos, à loja de aplicativos e à exibição de documentos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** tipo de perfil > **App Store, Exibição de Documentos, Jogos**). Também é possível escolher a região de Classificações, como Estados Unidos. Em uma atualização futura, o recurso **Aplicativos** será movido para ser um filho da **Região de classificações** e é dependente da **Região de classificações**.

Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos usando o Intune](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Aplica-se a: iOS

#### <a name="administrative-templates-for-group-policy---------3510695---"></a>Modelos administrativos da Política de Grupo     <!--  3510695 -->
Para ajudar a aprimorar a segurança de dispositivos na nuvem, serão lançados modelos administrativos que permitirão usar o Intune para definir configurações de Política de Grupo selecionadas para computadores Windows.  Esses modelos usam o CSP (Provedor de Serviço de Configuração) de Política para fornecer até 2.500 configurações adicionais do Office, do Windows e do OneDrive.

####  <a name="new-settings-for-the-windows-security-baseline-----3534649-4217151------------"></a>Novas configurações para a linha de base de segurança do Windows  <!-- 3534649, 4217151          -->
Estamos adicionando novas configurações à linha de base de segurança do Windows. A primeira configuração é para Segurança Baseada em Virtualização, que requer inicialização segura. A segunda configuração permitirá que você gerencie a ativação por voz de aplicativos do Windows quando a tela estiver bloqueada.

#### <a name="security-baselines-will-be-generally-available------3785395---------"></a>Linhas de Base de Segurança estarão em disponibilidade geral  <!--  3785395       -->
O recurso de Linhas de Base de Segurança em breve estarão fora de versão prévia e em disponibilidade geral. 

#### <a name="the-windows-security-baseline-template-will-be-generally-available-------3794072---------"></a>O modelo de Linha de Base de Segurança do Windows estará em disponibilidade geral   <!--  3794072       -->
O modelo de Linha de Base de Segurança do Windows em breve estará fora de versão prévia e em disponibilidade geral. A versão prévia do modelo será desativada e um novo modelo estará disponível.

<!-- ***********************************************-->
### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Atribuir marcas de escopo para todos os dispositivos gerenciados em um grupo de segurança <!-- 3173810 -->
No momento, você pode atribuir uma marca de escopo a um dispositivo acessando a página **Propriedades** de cada dispositivo individual e selecionando as marcas de escopo. Em uma atualização futura, você poderá atribuir marcas de escopo a um grupo de segurança e todos os dispositivos no grupo de segurança também serão associados a essas marcas de escopo. Para fazer isso, escolha **Intune** > **Funções** > **Escopo (Marcas)**  > **Criar** > **Escopo (Marcas)** > escolha os grupos aos quais você deseja atribuir a marca de escopo. Todos os dispositivos nesses grupos também receberão a marca de escopo. As marcas de escopo definidas com esse recurso substituirão as marcas de escopo definidas com o fluxo de marcas de escopo atual do dispositivo. (Em uma atualização futura, o fluxo atual para atribuir marcas de escopo a dispositivos será somente leitura.)

#### <a name="see-the-security-patch-level-for-android-devices----4461911----"></a>Veja o nível de patch de segurança para dispositivos Android <!-- 4461911  -->
Você poderá ver o nível de patch de segurança para dispositivos Android. Para isso, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Monitorar** > **Hardware**.


<!-- ***********************************************-->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


