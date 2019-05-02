---
title: No desenvolvimento - Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune no desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa38a684a32756d4f2c3be3b750f8e79b66e98f6
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587375"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>No desenvolvimento do Microsoft Intune – abril de 2019

Para ajudá-lo em sua preparação e planejamento, esta página listas UI Intune atualiza e recursos que estão em desenvolvimento, mas ainda não foi liberado. Além disso:

- Se prevemos que você precisará agir antes de uma alteração, publicaremos uma postagem complementar do Centro de mensagens do Office.
- Quando um recurso é iniciado em produção, como uma visualização ou em disponibilidade geral, a descrição do recurso moverá desativar esta página e para o [página de novidades](whats-new.md).
- Esta página e o [página de novidades](whats-new.md) são atualizados periodicamente. Volte a ela para verificar se há atualizações adicionais.
- Consulte a [M365 roteiro](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para entregas estratégicas e linhas do tempo.

> [!Note]
> Esses itens refletem a expectativas atuais da Microsoft sobre os recursos do Intune vem em uma versão futura. As datas e os recursos individuais podem ser alteradas. Nem todos os itens no desenvolvimento de tem uma descrição do recurso nesta página.

**RSS feed**: receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Definir configurações de logon e controlar as opções de reinicialização em dispositivos macOS <!-- 1210083 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**configuração do dispositivo** > **perfis** > **criar perfil** > escolher **macOS** para a plataforma > **recursos do dispositivo** para tipo de perfil). Novas configurações de janela de logon será incluem itens como mostrando uma faixa personalizada, escolha como os usuários entrarem, mostrarem ou ocultar as configurações de energia e muito mais.

Para ver as configurações atuais, acesse [configurações de recurso de dispositivo macOS](macos-device-features-settings.md).

Aplica-se a: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Configurações avançadas para o Windows Defender Firewall <!-- 1311949 -->
Em breve, você poderá usar o Intune para gerenciar as regras de firewall personalizadas em clientes do Windows Defender. As regras poderão especificar o comportamento de entrada e saído para aplicativos, endereços de rede e portas. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Precisam de acesso condicional de proteção de aplicativo  <!--1634317 -->
Você poderá usar *política de proteção de aplicativo exigem*, que confirma a política é aplicada a um aplicativo do usuário antes de entrar ser concluída para impedir que os usuários acessem dados que você protege com acesso condicional. Enquanto a garantia de política pode causar lentidão na primeira experiência de uso, ele ajuda a proteger contra problemas de rede, configurações incorretas administrativas ou intencionais esforços para impressão com as políticas de proteção de aplicativo. 

### <a name="retire-noncompliant-devices----1827291---"></a>Desativar dispositivos não compatíveis <!-- 1827291 -->
Vamos adicionar uma nova ação de conformidade para desativar um dispositivo não compatível. Desativar um dispositivo não compatível remove todos os dados da empresa dele e também remove o dispositivo seja gerenciado pelo Intune. Essa ação é executada quando o valor configurado nos dias for atingido. O valor mínimo é de 30 dias. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Definir configurações para extensões de kernel em dispositivos macOS <!-- 2043024 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**configuração do dispositivo** > **perfis** > **criar perfil** > escolher **macOS** para plataforma). Um novo grupo de configurações permitirá que você configurar e usar extensões de kernel em seus dispositivos.

Aplica-se a: macOS 10.13.2 e posteriores

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Configurar o perfil para ignorar algumas telas durante a execução do Assistente de Configuração <!-- 2276470 -->
Ao criar um perfil de registro do macOS, você poderá configurá-lo para ignorar qualquer uma das telas a seguir quando um usuário executar o Assistente de Configuração:
- Migração do Android
- Tom de Exibição
- Privacidade
- iCloudStorage Se você editar um perfil ou criar um novo, as telas ignoradas selecionadas precisarão ser sincronizadas com o servidor MDM da Apple. Os usuários podem emitir uma sincronização manual dos dispositivos, para que não haja atraso na aplicação das alterações de perfil.
Saiba mais em [Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos ou o Apple School Manager](device-enrollment-program-enroll-macos.md).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Os usuários de dispositivos podem exibir todos os aplicativos gerenciados que você instalou ou tentou instalar <!-- 2352913 -->
Portal de empresa para Windows listará todos os aplicativos gerenciados&ndash; necessário e disponível&ndash; que são instalados em um dispositivo do usuário. Os usuários poderão a tentativa de modo de exibição e pendentes instalações de aplicativos e seus status atuais. Se sua organização não faz aplicativos obrigatória ou estará disponível, os usuários verão uma mensagem explicando que não há aplicativos da empresa foram instalados. Os usuários também poderão classificar ou filtrar seus aplicativos por status de instalação.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Marcas de escopo para tokens de VPP da Apple <!--2371886 -->
Você poderá adicionar marcas de escopo para tokens de VPP da Apple. Somente os usuários que recebem a mesma marca de escopo terá acesso ao token do Apple VPP com essa marca. Aplicativos de VPP e livros eletrônicos adquiridos com esse token herdam as marcas de escopo. Para obter mais informações sobre marcas de escopo, consulte [marcas de escopo e Use RBAC](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo Windows 10 <!-- 2549910 -->
Você cria perfis de configuração do dispositivo Windows 10 (**configuração do dispositivo** > **perfis** > **criar perfil**  >  **Windows 10** para plataforma). Você poderá criar uma **regra de aplicabilidade** para que o perfil só se aplica a uma edição específica ou uma versão específica. Por exemplo, você pode criar um perfil que permite que algumas configurações de disco BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplica a dispositivos que executam o Windows 10 Enterprise.

Aplica-se a: 
- Windows 10 e posterior

### <a name="enable-win32-app-dependencies----2617348---"></a>Habilitar dependências de aplicativo Win32 <!-- 2617348 -->
Visualização pública – como administrador, você poderá exigir que os outros aplicativos são instalados como dependências antes de instalar o aplicativo do Win32. Especificamente, o dispositivo deve instalar os aplicativos dependentes antes de instalar o aplicativo do Win32. Essa funcionalidade estará disponível somente depois que o agente de gerenciamento do Intune foi atualizado para a versão de 1904 (maior que 1.18.120.0) que pode levar de 1 ou 2 semanas adicionais depois de atualizarmos o serviço como 1904. No Intune, selecione **aplicativos de cliente** > **aplicativos** > **adicionar** para exibir o **Adicionar aplicativo** folha. Selecione **aplicativo do Windows (Win32)** como o **tipo de aplicativo**. Para obter mais informações, consulte [Intune Standalone - gerenciamento de aplicativo Win32](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nova configuração de restrição de dispositivo para Android Enterprise, o proprietário do dispositivo: permitir que os usuários se conectarem às redes Wi-Fi em dispositivos Android Enterprise dedicados que executam o modo de quiosque de vários aplicativos <!--3041940 -->
Os administradores poderão alternar uma nova configuração que permite que usuários configurem o Bluetooth em seus dispositivos Android Enterprise dedicados que executam o modo de quiosque de vários aplicativos. Para ver essa configuração no console do Intune, escolha **Intune** > **configuração do dispositivo** > **perfis**  >  **Criar perfil** > escolha **Android Enterprise** para a plataforma > **somente o proprietário do dispositivo, restrições de dispositivo** para tipo de perfil > **configurações**   >  **Dedicado dispositivos** > selecione **vários aplicativos** do **modo de quiosque** configuração de lista suspensa. Uma opção chamada **configuração de Wi-Fi** estarão disponíveis para habilitar. 

Aplica-se a: Android Enterprise dedicado a dispositivos que executam o modo de quiosque de vários aplicativos. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nova configuração de restrição de dispositivo para Android Enterprise, o proprietário do dispositivo: permitir que os usuários a configurar o Bluetooth e emparelhamento em dispositivos Android Enterprise dedicado <!--3041941 -->
Os administradores poderão alternar uma nova configuração que permite que usuários configurem o Bluetooth em seus dispositivos Android Enterprise dedicados que executam o modo de quiosque de vários aplicativos. Para ver essa configuração no console do Intune, escolha **Intune** > **configuração do dispositivo** > **perfis**  >  **Criar perfil** > escolha **Android Enterprise** para a plataforma > **somente o proprietário do dispositivo, restrições de dispositivo** para tipo de perfil > **configurações**   >  **Dedicado dispositivos** > selecione **vários aplicativos** do **modo de quiosque** configuração de lista suspensa. Uma opção chamada **Bluetooth configuração** estarão disponíveis para habilitar. 

Aplica-se a: Android Enterprise dedicado a dispositivos que executam o modo de quiosque de vários aplicativos. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorar o status de linha de base de segurança (visualização pública) <!-- 3082047 --> 
Quando você monitora o *status do dispositivo* para suas linhas de base de segurança, o modo de exibição organizará o status pelas categorias da linha de base, como *acima do bloqueio*, *BitLocker*e  *Navegador*. Todas as categorias de linha de base disponíveis serão representadas. Para cada categoria, você verá o número de dispositivos não coincidem com uma categoria específica de linha de base, está configurados incorretamente ou não é aplicável.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Tarefas de segurança do Intune para Defender ATP (em visualização pública) <!-- 3208597 -->
Disponível como visualização pública, Intune logo adicionará tarefas de segurança para o recém-anunciado ameaças da Microsoft Defender & gerenciamento de vulnerabilidades.  Com essa integração, os administradores de operações de segurança no Windows Defender ATP WDATP () com mais eficiência podem se comunicar as correções recomendadas ameaças emergentes para os administradores do Intune. A adição de tarefas de segurança adiciona uma abordagem baseada em riscos para detectar, priorizar e corrigir vulnerabilidades de ponto de extremidade e configurações incorretas.

Para saber mais sobre tarefas de segurança no Intune, consulte o postagem no blog sobre [usando tarefas de segurança do Intune para estender o Microsoft Defender ATP ameaça e vulnerabilidade gerenciamento](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Criar e usar perfis de configuração de dispositivo OEMConfig no Intune <!-- 3305883 -->
Intune oferecerá suporte a configurar dispositivos Android Enterprise com OEMConfig. Especificamente, você pode criar um perfil de configuração do dispositivo e aplicar as configurações para dispositivos Android Enterprise usando OEMConfig (**configuração do dispositivo** > **perfis**  >  **Criar perfil** > **Android enterprise** para plataforma).

Suporte para os OEMs está atualmente em uma base por OEM. Se um aplicativo OEMConfig desejado não estiver disponível na lista de aplicativos OEMConfig, entre em contato com `IntuneOEMConfig@microsoft.com`.

Aplica-se a: 
- Android Enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Novas configurações de restrição de dispositivo Android Enterprise, o proprietário do dispositivo <!-- 3574254 -->
Em dispositivos Android Enterprise, você pode criar um perfil de restrição de dispositivo para permitir ou restringir os recursos, definir regras de senha e muito mais (**configuração do dispositivo** > **perfis**  >  **Criar perfil** > escolher **Android Enterprise** para a plataforma > **somente o proprietário do dispositivo > restrições de dispositivo** para tipo de perfil). 

Novas configurações, incluindo configurações de senha, permitindo total acessem a aplicativos no Google Play Store para dispositivos totalmente gerenciados e estarão mais disponíveis. 

Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md). 

Aplica-se a: dispositivos totalmente gerenciados do Android Enterprise

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671 -->
Muitos Windows 10 e dispositivos posteriores têm chipsets Trusted Platform Module (TPM). Uma nova configuração de conformidade verificará se um TPM está no dispositivo.

[Windows 10 e posteriores configurações de política de conformidade](compliance-policy-create-windows.md) lista as configurações atuais.

Aplica-se a: 
- Windows 10 e posterior

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Configurar seus aplicativos do Win32 para ser instalado em registrados no Intune dispositivos ingressados no Azure AD <!-- 3695227 -->
Você conseguirá dispositivos adicionados ao atribuir os aplicativos do Win32 para ser instalado no Intune registrados do Azure AD. Para obter mais informações sobre aplicativos Win32 no Intune, consulte [gerenciamento de aplicativo Win32](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Linha de base da Proteção Avançada contra Ameaças do Windows Defender <!-- 3754134 -->
Vamos adicionar a nova linha de base para ajudá-lo a definir as configurações do Windows Defender Advanced Threat Protection.

### <a name="device-overview-shows-primary-user---794259---"></a>Visão geral do dispositivo mostra o usuário primário <!--794259 -->
A página de visão geral do dispositivo mostrará que o usuário primário, também chamado do usuário de afinidade de dispositivo usuário (UDA). Para ver o usuário primário para um dispositivo, escolha **Intune** > **dispositivos** > **todos os dispositivos** > escolha um dispositivo. O usuário principal será exibido próximo à parte superior a **visão geral** página.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Suporte expandido para dispositivos Android Enterprise totalmente gerenciado <!-- 3903241, 3903244, 3903246 -->
Vamos expandir esse suporte de dispositivos Android Enterprise totalmente gerenciado ([anunciada pela primeira vez em janeiro de 2019](whats-new.md#week-of-january-14-2019) para incluir o seguinte:
- Conformidade
- Acesso condicional
- Novo aplicativo de usuário final

Para configurar dispositivos totalmente gerenciados do Android, acesse **Registro de dispositivo** > **Registro do Android** > **Dispositivos corporativos totalmente gerenciados**. Suporte para dispositivos Android gerenciados totalmente permanece em visualização e alguns recursos do Intune podem não estar totalmente funcionais. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Aplicativo Google Play gerenciado adicionais de relatórios para dispositivos de perfil de trabalho do Android Enterprise <!-- 4105925 -->
Para aplicativos do Google Play gerenciado implantados em dispositivos de perfil de trabalho do Android Enterprise, será possível exibir o número de versão específica do aplicativo instalado em um dispositivo. Isso se aplica somente a aplicativos necessários. A mesma funcionalidade de aplicativos disponíveis será habilitada em uma versão futura.

### <a name="ios-third-party-keyboards----4111843---"></a>Teclados de terceiros para iOS <!-- 4111843 -->
Suporte para a política de proteção de aplicativo do Intune (aplicativo) para o **teclados de terceiros** configuração será encerrado devido a uma alteração de plataforma iOS. Você não poderá definir essa configuração no Console de administração do Intune e não serão imposta no cliente no SDK do Intune App.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Bloquear usuários de verificar se há atualizações do Windows <!-- 3316758 -->
Estamos adicionando uma nova configuração de anel de atualização do Windows que você pode usar para impedir que os usuários verificando se há atualizações do Windows. Essa configuração não estará disponível de dentro do portal, mas pode ser configurada usando a API do Graph do Intune.

### <a name="windows-update-notifications----3316782---"></a>Notificações de atualização do Windows <!-- 3316782 -->
Estamos adicionando suporte para as configurações do anel de atualização do Windows para que você possa configurar as notificações de atualização do Windows que os usuários veem. Essa configuração não estará disponível de dentro do portal, mas pode ser configurada usando a API do Graph do Intune.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Acesso mais fácil a configurações de diagnóstico <!-- 3804627 -->
Estamos adicionando uma nova opção para o **logs de auditoria** folha em cada carga de trabalho do Log de auditoria no console do Intune que você pode usar para abrir diretamente o *configurações de diagnóstico* página.

## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


