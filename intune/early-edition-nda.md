---
title: Edição antecipada - Microsoft Intune
titlesuffix: ''
description: Edição antecipada do Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: d50925d9f5422e1bfea01869233c63d6a2889109
ms.sourcegitcommit: 12f8b7f0bca1baa2c1f68dd6af4f16a4814daa11
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55737495"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>A edição antecipada do Microsoft Intune – janeiro de 2019

> [!Note]
> Notificação de NDA: As seguintes alterações estão em desenvolvimento para o Intune. Essas informações são compartilhadas nos termos do NDA de forma muito limitada. Não poste nenhuma dessas informações em mídia social nem em sites públicos, como Twitter, UserVoice, Reddit e assim por diante. 

A **edição antecipada** fornece uma lista de recursos, compartilhados nos termos do NDA, que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não tweet, poste no UserVoice nem compartilhe de nenhuma outra forma essas informações fora de sua empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure
<!-- 1902 start-->

### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675----"></a>Scripts de PowerShell podem ser executados em um host de 64 bits em dispositivos de 64 bits <!-- 1862675  -->
Quando você adiciona um script do PowerShell a um perfil de configuração do dispositivo, o script é executado sempre em 32 bits, mesmo em sistemas operacionais de 64 bits. Com essa atualização, um administrador pode executar o script em um host do PowerShell de 64 bits em dispositivos de 64 bits (**Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar** > **Configurar** > **Executar o script no host do PowerShell de 64 bits**).
Para obter mais detalhes sobre como usar o PowerShell, veja [scripts do PowerShell no Intune](intune-management-extension.md).
Aplica-se a: Windows 10 e posterior

### <a name="rename-an-enrolled-windows-device----1911112----"></a>Renomear um dispositivo Windows registrado <!-- 1911112  -->
Você poderá renomear um dispositivo Windows 10 registrado (RS4 ou posterior). Para fazê-lo, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Renomear dispositivo**.

### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521-----"></a>Atribuir certificados SCEP em um dispositivo macOS sem usuário    <!-- 2340521   -->
Você poderá atribuir certificados do protocolo SCEP a um dispositivo sem usuário macOS e associe o certificado ao Wi-Fi ou perfis de VPN. Isso expande o suporte existente que já temos para [atribuir certificados em dispositivos sem usuários que executam Windows, iOS e Android](certificates-scep-configure.md#create-a-scep-certificate-profile).

### <a name="intune-conditional-access-ui-update------2432313----"></a>Atualização de interface do usuário de acesso condicional do Intune   <!-- 2432313  -->
Estamos fazendo aprimoramentos na interface do usuário para acesso condicional no console do Intune. Como por exemplo:
- Substitua a folha *Acesso condicional* do Intune pela folha do Azure Active Directory. Isso garante que você terá acesso ao intervalo completo de definições e configurações para o acesso condicional que continua sendo uma tecnologia do Azure AD.
- Realoque a configuração de *Conector de serviço do Exchange* para o que é atualmente a folha *Acesso local*. Também estamos renomeando essa folha para *Acesso ao Exchange*. Essa alteração consolidará o local em que você pode configurar e monitorar os detalhes relacionados ao Exchange online e local.

### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355----"></a>O Intune aproveitará as APIs do Google Play Protect em dispositivos Android <!-- 2577355  -->
Alguns administradores de TI se deparam com um cenário de BYOD, em que os usuários finais podem acabar efetuando rooting ou desbloqueio por jailbreak dos respectivos dispositivos móveis. Esse comportamento, embora às vezes não mal-intencionado, resulta em um desvio de muitas políticas do Intune que são definidas para proteger os dados da organização em dispositivos de usuário final. Assim, o Intune fornece detecção de root e jailbreak para dispositivos registrados e não registrados. Com esta versão, o Intune agora aproveitará as APIs do Google Play Protect para adicionar a nossas verificações de detecção de root existentes para dispositivos não registrados. Embora o Google não compartilhe as verificações de detecção de root que ocorrem na íntegra, esperamos que essas APIs detectem os usuários que realizaram rooting de seus dispositivos por qualquer motivo, desde personalização de dispositivo até possibilidade de obtenção das atualizações mais recentes do sistema operacional em dispositivos mais antigos. Esses usuários podem então ser impedidos de acessar dados corporativos e suas contas corporativas podem ser apagadas de seus aplicativos habilitados para política. Para o valor adicional, o administrador de TI agora tem várias atualizações de geração de relatórios na folha da Proteção de Aplicativo do Intune – o relatório "Usuários sinalizados" mostrará quais usuários são detectados por meio do verificação de API do SafetyNet da Google Play Protect, o relatório "Aplicativos potencialmente prejudiciais" mostrará quais aplicativos são detectados por meio da verificação de API da Verificação de Aplicativos do Google. Este recurso está disponível no Android. 

### <a name="win32-app-information-available-in-troubleshooting-blade----2617342------"></a>Informações do aplicativo Win32 disponíveis na folha de solução de problemas <!-- 2617342    -->
Você poderá coletar arquivos de log de falha para uma instalação de aplicativo Win32 da folha **solução de problemas** do aplicativo do Intune. Para obter mais informações sobre como solucionar problemas de instalação do aplicativo, veja [Solucionar problemas de instalação do aplicativo](troubleshoot-app-install.md).

### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135----"></a>Aplicativos de navegador de quiosque e navegador Microsoft Edge podem ser executados em dispositivos Windows 10 no modo de quiosque <!-- 2935135  -->
Você pode usar dispositivos Windows 10 no modo de quiosque para executar um ou vários aplicativos. Esta atualização inclui várias alterações para usar aplicativos de navegador no modo de quiosque, incluindo:

- Adicionar o navegador Microsoft Edge ou o navegador de quiosque para serem executados como aplicativos no dispositivo de quiosque (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **Windows 10 e posterior** para a plataforma > **Quiosque** para tipo de perfil).
- Restringir o Microsoft Edge para que ele possa (ou não) ser executado no modo de quiosque (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **Windows 10 e posterior** para a plataforma > **Restrições de dispositivo** para tipo de perfil > **Navegador Microsoft Edge**). Quando ele não é executado no modo de quiosque, as configurações do Microsoft Edge podem ser alteradas pelos usuários finais.

Para obter uma lista das configurações atuais, veja:

- [Configurações de dispositivos com Windows 10 (e posterior) para execução como um quiosque](kiosk-settings-windows.md)
- [Restrições de dispositivo do navegador Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)

Aplica-se a: Windows 10 e posterior

### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Atribuir automaticamente marcas de escopo para recursos criados por um administrador com esse escopo <!-- 3173823  -->
Quando um administrador cria um recurso, todas as marcas de escopo atribuídas ao administrador serão atribuídas automaticamente a esse novo recurso.

### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774---"></a>Novas configurações de restrição de dispositivo adicionadas para dispositivos iOS e macOS <!-- 3448774 -->
Você pode restringir algumas configurações e recursos em dispositivos que executam o iOS e macOS (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **iOS** ou **macOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil). Essa atualização adiciona mais recursos e configurações que você pode controlar, incluindo a definição do tempo de tela, a alteração de configurações do eSIM e planos de celular, o atraso da visibilidade de atualizações de software pelo usuário, o bloqueio do cache de conteúdo e muito mais.
Para ver os recursos e configurações que você pode restringir atualmente, consulte:
- [Configurações de restrição de dispositivo iOS](device-restrictions-ios.md)
- [Configurações de restrição de dispositivo macOS](device-restrictions-macos.md)

Aplica-se a:
- iOS
- macOS

### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202---"></a>O relatório de registro com falha se move para a folha de Registro de Dispositivo <!-- 3560202 -->
O relatório **Registros com falha** será movido para a seção **Monitorar** da folha **Registro de dispositivo**. Duas novas colunas (Método de Registro e Versão do Sistema Operacional) também são adicionadas.

### <a name="change-kiosk-to-dedicated-devices----3598402----"></a>Alterar "Quiosque" para "Dispositivos dedicados" <!-- 3598402  -->
Para alinhar-se à terminologia do Android, **Quiosque** será alterado para **Dispositivos dedicados** em Perfis de configuração do dispositivo, **Android enterprise** > **Proprietário do Dispositivo** > **Restrições de Dispositivo**.

### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850--3803313----"></a>As configurações de iOS do Safari e de Atrasar a visibilidade de atualizações de software pelo usuário estão sendo movidas na interface do usuário do Intune <!-- 3640850, , 3803313  -->
Para dispositivos iOS, você pode definir as configurações do Safari e configurar as Atualizações de Software. Nesta atualização, essas configurações estão sendo movidas para diferentes partes da interface do usuário do Intune:

- As configurações do Safari estão mudando de **Safari** (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil) para **Aplicativos internos**. 
- A configuração **Atrasar a visibilidade de atualizações de software pelo usuário para dispositivos iOS supervisionados** (**Atualizações de software** > **Atualizar as políticas para iOS**) está sendo movida para **Restrições de dispositivo** > **Geral**.

Para obter uma lista das configurações atuais, confira [Restrições de dispositivo iOS](device-restrictions-ios.md) e [Atualizações de software iOS](software-updates-ios.md).

Aplica-se a: 
- iOS

### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164----"></a>Habilitar restrições nas configurações do dispositivo é renomeado para Tempo de Tela em dispositivos iOS <!-- 3699164  -->
Você pode configurar a **Habilitar restrições nas configurações do dispositivo** em dispositivos iOS supervisionados (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil > **Geral**). Nesta atualização, essa configuração é renomeada para **Tempo de Tela (somente supervisionado)**. O comportamento é o mesmo. Especificamente: 

- iOS 11.4.1 e versões anteriores: **Bloquear** impede que os usuários finais definam suas próprias restrições nas configurações do dispositivo. 
- iOS 12.0 e versões posteriores: **Bloquear** impede que os usuários finais configurem seu próprio **Tempo de Tela** nas configurações do dispositivo, incluindo restrições de privacidade e de conteúdo. Dispositivos atualizados para o iOS 12.0 não exibirão mais a guia de restrições nas configurações do dispositivo. Essas configurações estão no **Tempo de Tela**. 

Para obter uma lista das configurações atuais, confira [Restrições de dispositivo iOS](device-restrictions-ios.md).

Aplica-se a: 
- iOS

### <a name="app-status-details-for-ios-apps----3761235----"></a>Detalhes do status do aplicativo para aplicativos iOS <!-- 3761235  -->
Haverá novas mensagens de erro de instalação de aplicativo relacionadas ao seguinte:
- Falha em aplicativos VPP durante a instalação no iPad compartilhado
- Falha quando o repositório do aplicativo é desabilitado
- Falha ao localizar a licença do VPP para o aplicativo
- Falha ao instalar aplicativos do sistema com o provedor de MDM
- Falha ao instalar aplicativos quando o dispositivo está no modo perdido ou modo de quiosque
- Falha ao instalar o aplicativo quando o usuário não está conectado à App Store

No Intune, selecione **Aplicativos cliente** > **Aplicativos** > "Nome do aplicativo" > **Status de instalação do dispositivo**. Novas mensagens de erro estarão disponíveis na coluna **Detalhes do status**.

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implantação de aplicativos online licenciados da Microsoft Store para Empresas <!-- 1672660  -->
Você poderá atribuir aplicativos online licenciados obrigatórios da Microsoft Store para Empresas no contexto de dispositivo. A implantação de um aplicativo da Microsoft Store para Empresas dessa maneira permitirá que o aplicativo seja instalado para todos os usuários no dispositivo. Isso é aplicável somente a dispositivos Windows 10 RS4+ desktop. A opção de instalação no contexto de dispositivo está disponível na página Atribuição de aplicativo do Cliente para aplicativos Online Licenciados da MSFB.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Implantação do aplicativo APP-WE do Android Enterprise <!-- 1171203 -->
Para dispositivos Android em um cenário de implantação APP-WE (Política de proteção de aplicativo sem registro), é possível usar o Google Play gerenciado para implantar aplicativos da loja e aplicativos de LOB para os usuários. Especificamente, o departamento de TI pode fornecer uma experiência de catálogo e instalação de aplicativos que não exige mais dos usuários finais a negligência com relação à postura de segurança de seus dispositivos ao permitir instalações de fontes desconhecidas. Além disso, esse cenário de implantação fornece uma experiência aprimorada ao usuário final.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Método de autenticação de atualização das políticas do Intune e instalação do aplicativo Portal da Empresa <!-- 1927359 -->
Em dispositivos já registrados por meio do Assistente de Instalação com um dos métodos de registro de dispositivo corporativo da Apple, o Intune não oferecerá mais o suporte do Portal da Empresa quando for instalado manualmente pelos usuários finais da loja de aplicativos. Essa alteração só é relevante quando você autentica com o Assistente de Configuração da Apple durante o registro. Além disso, essa alteração afeta apenas dispositivos iOS registrados via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Programa de registro de dispositivos (DEP) da Apple

Se os usuários instalarem o aplicativo Portal da Empresa pela loja de aplicativos e tentarem registrar esses dispositivos por meio do aplicativo, receberão um erro. Esses dispositivos só devem usar o Portal da Empresa quando ele for enviado por push, automaticamente, pelo Intune durante o registro. Os perfis de registro no Intune, no portal do Azure, serão atualizados para que você possa especificar como os dispositivos são autenticados, e se o usuário recebe o aplicativo Portal da Empresa. Se você quiser que os usuários de dispositivos DEP tenham o Portal da Empresa, especifique suas preferências em um perfil de registro. Além disso, a tela **Identifique o dispositivo** no aplicativo Portal da Empresa logo se tornará obsoleta.  
Para instalar o Portal da Empresa em dispositivos DEP já registrados, acesse Intune > Aplicativos cliente, e envie-o como um aplicativo gerenciado com políticas de configuração de aplicativo. Os detalhes sobre como executar essas etapas serão descritos em documentos futuros.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Os modelos administrativos estão em versão prévia pública e mudaram para o perfil de configuração próprio <!-- 3322847 -->
Os modelos administrativos no Intune (**Configuração do dispositivo** > **Modelos administrativos**) estão em versão prévia privada. Com esta atualização: Modelos administrativos incluem aproximadamente 300 configurações que podem ser gerenciadas no Intune. Anteriormente, essas configurações só existiam no editor de política de grupo.
Os modelos administrativos estão disponíveis na versão prévia pública. Os modelos administrativos estão mudando de **Configuração do dispositivo** > **Modelos administrativos** para **Configuração do dispositivo** > **Perfis** >**Criar perfil** > em **Plataforma**, escolha **Windows 10 e posterior**, em **Tipo de perfil**, escolha **Modelos administrativos**.
A criação de relatórios está habilitada. Aplica-se a: Windows 10 e posterior

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Modo Escuro do Portal da Empresa do Intune no macOS <!-- 3300524 -->
O Portal da Empresa do Intune no macOS agora dá suporte ao Modo Escuro para macOS. Quando você habilitar o Modo Escuro em um dispositivo macOS 10.14 ou superior, o Portal da Empresa ajustará sua aparência de acordo com as cores para refletir o modo.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações de APP (Política de Proteção de Aplicativo) do aplicativo para dados Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token de VPP da Apple usado por outro MDM <!-- 1488946 -->
O Intune detectará e mostrará detalhes se um token do VPP (Apple Volume Purchase Program) estiver sendo usado tanto pelo Intune quanto por outro MDM.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Dispositivos desativados no painel de conformidade de dispositivos <!-- 1981119 -->
Em uma atualização futura, os dispositivos desativados serão removidos do painel de conformidade de dispositivos. Com isso, seus números de conformidade serão alterados.

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.