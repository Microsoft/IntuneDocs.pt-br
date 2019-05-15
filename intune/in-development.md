---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
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
# <a name="in-development-for-microsoft-intune---april-2019"></a>Em desenvolvimento para o Microsoft Intune – abril de 2019

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

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Definir as configurações de logon e controlar as opções de reinicialização em dispositivos macOS <!-- 1210083 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). Novas configurações de janela de logon incluirão itens como exibição de uma faixa personalizada, escolher como os usuários se conectam, mostrar ou ocultar as configurações de energia, entre outros.

Para ver as configurações atuais, acesse [Configurações de recurso de dispositivo macOS](macos-device-features-settings.md).

Aplica-se a: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Configurações avançadas para o Windows Defender Firewall <!-- 1311949 -->
Em breve, você poderá usar o Intune para gerenciar as regras de firewall personalizadas em clientes do Windows Defender. As regras poderão especificar o comportamento de entrada e saída para aplicativos, endereços de rede e portas. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Exigir acesso condicional de proteção de aplicativo  <!--1634317 -->
Você poderá usar a *política Exigir Proteção de Aplicativo*, que confirma que a política é aplicada a um aplicativo do usuário antes de a entrada ser concluída para impedir que os usuários acessem dados que você protege com acesso condicional. Embora a garantia de política possa causar lentidão na primeira experiência de uso, ela ajuda na proteção contra problemas de rede, configurações administrativas incorretas ou esforços intencionais para burlar políticas de proteção de aplicativo. 

### <a name="retire-noncompliant-devices----1827291---"></a>Desativar dispositivos sem conformidade <!-- 1827291 -->
Vamos adicionar uma nova ação de conformidade para desativar um dispositivo não compatível. Desativar um dispositivo não compatível remove todos os dados da empresa dele e também remove o dispositivo do gerenciamento pelo Intune. Essa ação é executada quando o valor configurado em dias é atingido. O valor mínimo é de 30 dias. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Definir configurações para extensões de kernel em dispositivos macOS <!-- 2043024 -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma). Um novo grupo de configurações permitirá que você configure e use extensões de kernel em seus dispositivos.

Aplica-se a: macOS 10.13.2 e posteriores

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Configurar o perfil para ignorar algumas telas durante a execução do Assistente de Configuração <!-- 2276470 -->
Ao criar um perfil de registro do macOS, você poderá configurá-lo para ignorar qualquer uma das telas a seguir quando um usuário executar o Assistente de Configuração:
- Migração do Android
- Tom de Exibição
- Privacidade
- iCloudStorage Se você editar um perfil ou criar um novo, as telas ignoradas selecionadas precisarão ser sincronizadas com o servidor MDM da Apple. Os usuários podem emitir uma sincronização manual dos dispositivos, para que não haja atraso na aplicação das alterações de perfil.
Saiba mais em [Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos ou o Apple School Manager](device-enrollment-program-enroll-macos.md).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Os usuários de dispositivos podem exibir todos os aplicativos gerenciados que você instalou ou tentou instalar <!-- 2352913 -->
O Portal da Empresa para Windows listará todos os aplicativos gerenciados&ndash; necessários e disponíveis&ndash; instalados em um dispositivo do usuário. Os usuários poderão exibir tentativas e instalações de aplicativos pendentes e o status atual. Se a sua organização não torna aplicativos obrigatórios ou disponíveis, os usuários veem uma mensagem explicando que nenhum aplicativo da empresa foi instalado. Os usuários também poderão classificar ou filtrar seus aplicativos por status de instalação.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Marcas de escopo para tokens VPP da Apple <!--2371886 -->
Você poderá adicionar marcas de escopo para tokens da de VPP da Apple. Somente os usuários atribuídos com a mesma marca de escopo terão acesso ao token VPP da Apple com essa marca. Os aplicativos e os livros eletrônicos VPP adquiridos com esse token herdam as marcas de escopo. Para obter mais informações sobre marcas de escopo, confira [Usar o RBAC e marcas de escopo](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 -->
Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma). Você poderá criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Aplica-se a: 
- Windows 10 e posterior

### <a name="enable-win32-app-dependencies----2617348---"></a>Habilitar dependências de aplicativo Win32 <!-- 2617348 -->
Versão prévia pública – como administrador, você poderá exigir que outros aplicativos sejam instalados como dependências antes da instalação do aplicativo Win32. Especificamente, o dispositivo precisa instalar os aplicativos dependentes antes de instalar o aplicativo Win32. Essa funcionalidade estará disponível somente depois que o agente de Gerenciamento do Intune for atualizado para a versão 1904 (posterior a 1.18.120.0), o que poderá levar a uma ou duas semanas adicionais depois de atualizarmos o serviço para 1904. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar** para exibir a folha **Adicionar aplicativo**. Selecione **Aplicativo do Windows (Win32)** como o **Tipo de aplicativo**. Para obter mais informações, confira [Intune autônomo – gerenciamento de aplicativos Win32](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nova configuração de restrição de dispositivo para Android Enterprise, Proprietário do Dispositivo: permita que os usuários conectem-se às redes Wi-Fi em dispositivos Android Enterprise dedicados que estão executando o modo de quiosque de vários aplicativos <!--3041940 -->
Os administradores poderão alternar uma nova configuração que permita aos usuários configurar o Bluetooth em seus dispositivos Android Enterprise dedicados que executam o modo de quiosque de vários aplicativos. Para ver essa configuração no console do Intune, escolha **Intune** > **Configuração do dispositivo** > **Perfis**  >  **Criar perfil** > escolha **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo, Restrições de dispositivo** para o tipo de perfil > **Configurações** > **Dispositivos dedicados** > selecione **Vários aplicativos** na lista suspensa de configuração **Modo de quiosque**. Uma opção chamada **Configuração de Wi-Fi** estará disponível para ser habilitada. 

Aplica-se a: dispositivos dedicados Android Enterprise em execução no modo de quiosque de vários aplicativos. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nova configuração de restrição de dispositivo para Android Enterprise, Proprietário do Dispositivo: permita aos usuários configurar Bluetooth e emparelhamento em dispositivos Android Enterprise dedicados <!--3041941 -->
Os administradores poderão alternar uma nova configuração que permita aos usuários configurar o Bluetooth em seus dispositivos Android Enterprise dedicados que executam o modo de quiosque de vários aplicativos. Para ver essa configuração no console do Intune, escolha **Intune** > **Configuração do dispositivo** > **Perfis**  >  **Criar perfil** > escolha **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo, Restrições de dispositivo** para o tipo de perfil > **Configurações** > **Dispositivos dedicados** > selecione **Vários aplicativos** na lista suspensa de configuração **Modo de quiosque**. Uma opção chamada **Configuração de Bluetooth** estará disponível para ser habilitada. 

Aplica-se a: dispositivos dedicados Android Enterprise em execução no modo de quiosque de vários aplicativos. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorar o status da linha de base de segurança (versão prévia pública) <!-- 3082047 --> 
Quando você monitora o *Status do dispositivo* para suas linhas de base de segurança, a exibição organizará o status pelas categorias da linha de base, como *Acima do bloqueio*, *BitLocker* e *Navegador*. Todas as categorias de linha de base disponíveis serão representadas. Para cada categoria, você verá quantos dispositivos não correspondem a uma categoria específica de linha de base, estão configurados incorretamente ou não são aplicáveis.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Tarefas de segurança do Intune para Defender ATP (em versão prévia pública) <!-- 3208597 -->
Disponível como versão prévia pública, o Intune logo adicionará tarefas de segurança para o recém-anunciado Gerenciamento de Vulnerabilidade e Ameaças do Microsoft Defender.  Com essa integração, os administradores de operações de segurança no WDATP (Windows Defender ATP) poderão comunicar com mais eficiência aos administradores do Intune as correções recomendadas para ameaças emergentes. A adição de tarefas de segurança adiciona uma abordagem baseada em riscos para descobrir, priorizar e corrigir vulnerabilidades de ponto de extremidade e configurações incorretas.

Para saber mais sobre tarefas de segurança no Intune, veja a postagem no blog sobre [como usar tarefas de segurança do Intune para estender o Gerenciamento de Vulnerabilidade e Ameaças do Microsoft Defender ATP](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Criar e usar perfis de configuração de dispositivo do OEMConfig no Intune <!-- 3305883 -->
O Intune oferecerá suporte para configurar dispositivos Android Enterprise com OEMConfig. Especificamente, você pode criar um perfil de configuração do dispositivo e aplicar as configurações a dispositivos Android Enterprise usando o OEMConfig (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma).

No momento, há suporte para OEMs conforme o OEM. Se um aplicativo OEMConfig desejado não estiver disponível na lista de aplicativos OEMConfig, contate `IntuneOEMConfig@microsoft.com`.

Aplica-se a: 
- Android Enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Novas configurações de restrição de dispositivo para dispositivos Android Enterprise, Proprietário do Dispositivo <!-- 3574254 -->
Em dispositivos Android Enterprise, você pode criar um perfil de restrição de dispositivo para permitir ou restringir recursos, definir regras de senha, entre outros (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo > Restrições de dispositivo** para o tipo de perfil). 

Novas configurações, incluindo configurações de senha, permitindo acesso completo a aplicativos na Google Play Store para dispositivos totalmente gerenciados e muito mais estarão disponíveis. 

Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md). 

Aplica-se a: dispositivos Android Enterprise totalmente gerenciados

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671 -->
Muitos dispositivos Windows 10 e posteriores têm chipsets TPM (Trusted Platform Module). Uma nova configuração de conformidade verificará se um TPM está no dispositivo.

[Configurações de política de conformidade do Windows 10 e posteriores](compliance-policy-create-windows.md) lista as configurações atuais.

Aplica-se a: 
- Windows 10 e posterior

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Configurar os aplicativos Win32 para serem instalados em dispositivos ingressados no Azure AD registrados no Intune <!-- 3695227 -->
Você poderá atribuir os aplicativos Win32 a serem instalados em dispositivos ingressados no Azure AD registrados no Intune. Para obter mais informações sobre aplicativos Win32 no Intune, confira [Gerenciamento de aplicativos Win32](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Linha de base da Proteção Avançada contra Ameaças do Windows Defender <!-- 3754134 -->
Vamos adicionar a nova linha de base para ajudá-lo a definir as configurações de Proteção Avançada contra Ameaças do Windows Defender.

### <a name="device-overview-shows-primary-user---794259---"></a>A página Visão geral do dispositivo mostra o usuário primário <!--794259 -->
A página Visão geral do dispositivo mostrará o usuário primário, também chamado de usuário UDA (afinidade de dispositivo de usuário). Para ver o usuário primário de um dispositivo, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo. O usuário primário será exibido próximo à parte superior da página **Visão Geral**.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Suporte expandido para dispositivos Android Enterprise totalmente gerenciados <!-- 3903241, 3903244, 3903246 -->
Vamos expandir nosso suporte de dispositivos Android Enterprise totalmente gerenciados ([anunciado pela primeira vez em janeiro de 2019](whats-new.md#week-of-january-14-2019)) para incluir o seguinte:
- Conformidade
- Acesso condicional
- Novo aplicativo do usuário final

Para configurar dispositivos totalmente gerenciados do Android, acesse **Registro de dispositivo** > **Registro do Android** > **Dispositivos corporativos totalmente gerenciados**. O suporte para dispositivos Android totalmente gerenciados permanece em versão prévia e alguns recursos do Intune podem não estar totalmente funcionais. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Relatórios adicionais de aplicativos do Google Play Gerenciado para dispositivos de perfil de trabalho do Android Enterprise <!-- 4105925 -->
Para aplicativos do Google Play Gerenciado implantados em dispositivos de perfil de trabalho do Android Enterprise, será possível exibir o número de versão específico do aplicativo instalado em um dispositivo. Isso se aplica somente aos aplicativos obrigatórios. A mesma funcionalidade para aplicativos disponíveis será habilitada em uma versão futura.

### <a name="ios-third-party-keyboards----4111843---"></a>Teclados de terceiros para iOS <!-- 4111843 -->
O suporte para a APP (política de proteção de aplicativo) do Intune para a configuração **Teclados de Terceiros** será encerrado devido a uma alteração da plataforma iOS. Você não poderá definir essa configuração no Console de Administração do Intune e ela não será imposta no cliente no SDK do Aplicativo do Intune.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Impedir usuários de verificar se há atualizações do Windows <!-- 3316758 -->
Estamos adicionando uma nova configuração de anel do Windows Update que você pode usar para impedir que os usuários verifiquem se há atualizações do Windows. Essa configuração não estará disponível de dentro do portal, mas pode ser configurada usando a API do Graph do Intune.

### <a name="windows-update-notifications----3316782---"></a>Notificações do Windows Update <!-- 3316782 -->
Estamos adicionando suporte para as configurações de anel do Windows Update para que você possa configurar as notificações do Windows Update que os usuários veem. Essa configuração não estará disponível de dentro do portal, mas pode ser configurada usando a API do Graph do Intune.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Acesso mais fácil às Configurações de Diagnóstico <!-- 3804627 -->
Estamos adicionando uma nova opção à folha **Logs de auditoria** em cada carga de trabalho do Log de Auditoria no console do Intune que você pode usar para abrir diretamente a página *Configurações de Diagnóstico*.

## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


