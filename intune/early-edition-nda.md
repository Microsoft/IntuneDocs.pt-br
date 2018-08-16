---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f9849b2c327397c0b8945ee42d9fca7f9f46250
ms.sourcegitcommit: 58cddb08b64bd60f041eff46ff215e83e13db4e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40001903"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>A edição antecipada do Microsoft Intune – agosto de 2018

> [!Note]
> Notificação sobre o NDA: as alterações a seguir estão em desenvolvimento para o Intune. Essas informações são compartilhadas nos termos do NDA de forma muito limitada. Não poste nenhuma dessas informações em mídia social nem em sites públicos, como Twitter, UserVoice, Reddit e assim por diante. 

A **edição antecipada** fornece uma lista de recursos, compartilhados nos termos do NDA, que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não tweet, poste no UserVoice nem compartilhe de nenhuma outra forma essas informações fora de sua empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>O Windows Hello será direcionado a usuários e dispositivos <!-- 1106609 -->
Quando você cria uma política do [Windows Hello para Empresas](windows-hello.md), ela se aplica a todos os usuários da organização (abrange o locatário). Com esta atualização, a política também pode ser aplicada a usuários ou dispositivos específicos usando uma política de configuração do dispositivo (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Proteção de Identidade** > **Windows Hello para Empresas**).

No Intune no portal do Azure, as definições e configurações do Windows Hello estarão presentes no **Registro de dispositivos** e na **Configuração do dispositivo**. O **Registro de dispositivos** é direcionado a toda a organização (abrange o locatário) e dá suporte ao Windows Autopilot (OOBE). A **Configuração do dispositivo** é direcionada a usuários e dispositivos usando uma política que é aplicada durante o check-in.

Aplica-se a:  
- Windows 10 e posterior
- Windows Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Controlar o modo S em dispositivos Windows 10 e posteriores – versão prévia pública <!-- 1958649 -->
Você poderá criar um perfil de configuração do dispositivo que remove um dispositivo Windows 10 do modo S ou impedir que os usuários removam o dispositivo do modo S. Este recurso estará em Intune > **Configuração do dispositivo** > **Perfis** >  **Windows 10 e posteriores** > **Atualização de edição e alternância de modo**.
[Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) (Introdução ao Windows 10 no modo S) fornece mais informações sobre o modo S.
Aplica-se a: Windows 10 e posteriores (1809 e posteriores)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Atualizações modernas de suporte a VPN para iOS <!-- 2459928, 1819876, and 2650856 -->
Uma atualização futura dará suporte aos seguintes clientes VPN do iOS: 
- F5 Access (versão 3.0.1 e posterior)
- SSO da Citrix
- GlobalProtect da Palo Alto Networks (versão 5.0 ou superiores). Também em uma futura atualização:
- Os tipos de conexão do **F5 Access** existentes serão renomeados para **F5 Access Herdado** (devido a atualizações de identidade visual da F5)
- Os tipos de conexão do **GlobalProtect da Palo Alto Networks** serão renomeados para **GlobalProtect da Palo Alto Networks Herdado** (devido a atualizações de identidade visual da Palo Alto). 

Os perfis existentes com esses tipos de conexão continuam a funcionar com o cliente VPN herdado. Se você estiver usando o Cisco AnyConnect Herdado, o F5 Access Herdado, a VPN da Citrix ou o GlobalProtect da Palo Alto Networks Herdado com o iOS, passe a usar os novos aplicativos. Faça isso assim que possível para garantir que o acesso VPN esteja disponível para dispositivos iOS após a atualização para o iOS 12.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Bloquear o Portal da Empresa no modo de aplicativo único até a conexão do usuário <!--1067692 --> 
Caso você autentique um usuário por meio do Portal da Empresa e não pelo Assistente de Configuração durante o registro no DEP, há a opção de executar o Portal da Empresa no modo de aplicativo único. Essa opção bloqueia o dispositivo imediatamente depois que o Assistente de Configuração é concluído para que o usuário precise entrar para acessar o dispositivo. Esse processo garante que a integração do dispositivo seja concluída e ele não fique órfão em um estado sem nenhum usuário vinculado.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>Marcas de escopo para políticas <!--1081974 eeready-->

Você poderá criar marcas de escopo para limitar o acesso aos recursos do Intune. Adicione uma marca de escopo a uma atribuição de função e, em seguida, adicione a marca de escopo a um perfil de configuração. A função só terá acesso a recursos com perfis de configuração que tenham marcas de escopo correspondentes (ou nenhuma marca de escopo).
Para criar uma marca de escopo, escolha **Funções do Intune** > **Escopo (Marcas)** > **Criar**.
Para adicionar uma marca de escopo a uma atribuição de função, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de Política e Perfil** > **Atribuições** > **Escopo (Marcas)**.
Para adicionar uma marca de escopo a um perfil de configuração, escolha **Configuração do dispositivo** > **Perfis** > escolha um perfil > **Propriedades** > **Escopo (Marcas)**.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Atribuir um usuário e nome amigável a um dispositivo do Autopilot <!--1346521 -->
Uma versão prévia pública futura permitirá que os administradores atribuam um usuário a um único dispositivo Autopilot.  Os administradores também poderão atribuir nomes amigáveis para saudar o usuário durante a configuração do dispositivo com o Autopilot.

Aplica-se a: Windows Insider 1809 ou builds posteriores (durante a versão prévia).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token de VPP da Apple usado por outro MDM <!-- 1488946 -->
O Intune detectará e mostrará detalhes se um token do VPP (Apple Volume Purchase Program) estiver sendo usado tanto pelo Intune quanto por outro MDM.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Suporte de túnel de pacote para perfis VPN por aplicativo iOS para tipos de conexão personalizados e do Pulse Secure <!-- 1520957 -->
Ao usar perfis VPN por aplicativo iOS, você poderá usar o túnel de camada do aplicativo (proxy de aplicativo) ou o túnel no nível do pacote (túnel de pacote). Essas opções estarão disponíveis com os seguintes tipos de conexão:
- VPN personalizado
- Pulse Secure. Se você não tiver certeza de qual valor usar, confira a documentação do seu provedor VPN.
Aplica-se a: iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Zscaler é uma conexão disponível para perfis VPN no iOS <!-- 1769858 eeready -->
Quando você cria um perfil de configuração do dispositivo VPN no iOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** plataforma > Tipo de perfil **VPN**), há vários tipos de conexão, incluindo Cisco, Citrix e outros. Uma atualização futura adiciona o Zscaler como um tipo de conexão. 
[Configurações de VPN para dispositivos que executam o iOS](vpn-settings-ios.md) lista os tipos de conexão disponíveis.

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Bloquear registros de dispositivos Windows pessoais <!-- 1849498 -->
Você poderá impedir que dispositivos Windows pessoais sejam registrados com o [gerenciamento de dispositivo móvel](windows-enroll.md) no Intune. Os dispositivos registrados com o [agente Intune PC](manage-windows-pcs-with-microsoft-intune.md) não podem ser bloqueados com esse recurso.
Para ver esse recurso, escolha **Registro de dispositivos** > **Restrições de dispositivo**.
A habilitação dessa restrição não terá nenhum efeito nos dispositivos já registrados.
Depois que uma restrição é habilitada, o Intune faz uma verificação para saber se cada nova solicitação de registro do Windows é autorizada como um registro corporativo. Os métodos a seguir se qualificam como autorizados como um registro corporativo:
- O usuário do registro está usando uma [conta de gerenciador de registros de dispositivos]( device-enrollment-manager-enroll.md).
- O dispositivo deve ser registrado por meio do [Windows Autopilot](enrollment-autopilot.md).
- O número IMEI do dispositivo está listado em **Registro de dispositivos** > **[Identificadores de dispositivo corporativo]( corporate-identifiers-add.md)**).
- O dispositivo está sendo registrado por meio de um [pacote de provisionamento em massa](windows-bulk-enroll.md).
- O dispositivo está sendo registrado por meio do [registro automático do SCCM para o cogerenciamento](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management).

Os registros não autorizados serão bloqueados. Os seguintes registros são marcados como corporativos pelo Intune, mas como eles não oferecem o controle por dispositivo do administrador do Intune, eles serão bloqueados:
- [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [ingresso no Azure Active Directory durante a instalação do Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [ingresso no Azure Active Directory na instalação do Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).

Os seguintes métodos de registro pessoais também serão bloqueados:
- [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [Adicionar Conta Corporativa nas Configurações do Windows](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).
- A opção [Somente registro do MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) nas Configurações do Windows.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Especificar os padrões de nome de computador em um perfil do Autopilot <!--1849855-->
Você pode especificar um modelo de nome de computador para gerar e definir o [nome do computador](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) durante o registro do Autopilot. É necessário especificar isso no perfil do Autopilot, localizado em **Registro de dispositivos** > **Registro do Windows** > **Serviço de Implantação do Windows Autopilot** > **Perfis**. Somente caracteres alfanuméricos e hifens podem ser usados.
Aplica-se a: Windows Insider 1809 ou builds posteriores (durante a versão prévia).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>O número de versão e o número de build do iOS são mostrados <!-- 1892471 -->
Em **Conformidade de dispositivos** > **Conformidade de dispositivos**, a versão do sistema operacional iOS é mostrada. Em uma atualização futura, o número de build também será mostrado.
Quando são lançadas atualizações de segurança, a Apple normalmente mantém o número de versão no estado em que se encontra, mas atualiza o número de build. Exibindo o número de build, você pode verificar facilmente se uma atualização de vulnerabilidade está instalada.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Ocultar as opções de alteração de conta na página de entrada e na página de erro de domínio da empresa <!--1901669 --> para os perfis do Windows Autopilot
Uma versão prévia pública incluirá novas opções de perfil do Windows Autopilot para os administradores ocultarem as opções de alteração de conta na página de entrada e na página de erro de domínio da empresa. Para ocultar essas opções, é necessário configurar uma Identidade Visual da Empresa no Azure Active Directory. Aplica-se a: Windows Insider 1809 ou builds posteriores (durante a versão prévia).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Atraso quando as atualizações de software do iOS são mostradas no dispositivo <!-- 1949583 -->
Em Intune > **Atualizações de Software** > **Atualizar políticas do iOS**, você pode configurar os dias e horários em que não deseja que sejam instaladas atualizações nos dispositivos. Em uma atualização futura, você poderá atrasar quando uma atualização de software é mostrada visivelmente no dispositivo, de 1 a 90 dias. 
[Configurar políticas de atualização do iOS no Microsoft Intune](software-updates-ios.md) lista as configurações atuais.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Dispositivos desativados no painel de conformidade de dispositivos <!-- 1981119 -->
Em uma atualização futura, os dispositivos desativados serão removidos do painel de conformidade de dispositivos. Com isso, seus números de conformidade serão alterados.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968 -->
Novos recursos serão adicionados, com base nos comentários dos clientes, ao site Portal da Empresa. Você fará uma melhoria significativa na funcionalidade existente e na usabilidade dos seus dispositivos Android, iOS e Windows. Áreas do site, como detalhes do dispositivo, comentários e suporte e visão geral do dispositivo, receberão um design novo, moderno e responsivo. Você também verá:
- Fluxos de trabalho simplificados em todas as plataformas de dispositivo
- Fluxos de identificação e registro de dispositivo aprimorados
- Mensagens de erro mais úteis
- Linguagem mais amigável, menos jargão técnico
- Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos
- Maior acessibilidade para todos os usuários

### <a name="office-365-proplus-version----2213968-eeready---"></a>Versão do Office 365 ProPlus <!-- 2213968 eeready -->
Ao atribuir os aplicativos do Office 365 ProPlus a dispositivos Windows 10 usando o Intune, você poderá selecionar a versão do Office. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos** > **Adicionar Aplicativo**. Em seguida, selecione **Office 365 ProPlus Suite (Windows 10)** na lista suspensa **Tipo**. Selecione **Configurações do Pacote de Aplicativos** para exibir a folha associada. Defina o **Canal de Atualização** para um valor, como **Mensal**. Opcionalmente, remova outras versões do Office (msi) dos dispositivos de usuário final, selecionando **Sim**. Selecione **Específico** para instalar uma versão específica do Office para o canal selecionado em dispositivos de usuário final. Neste ponto, você pode selecionar a **Versão específica** do Office a ser usada. As versões disponíveis serão alteradas ao longo do tempo. Portanto, quando você cria uma nova implantação, as versões disponíveis podem ser mais recentes, e determinadas versões mais antigas podem não estar disponíveis. As implantações atuais continuarão a implantar a versão mais antiga, mas a lista de versões será atualizada continuamente por canal. Para mais informações, confira [Visão geral dos canais de atualização do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Configurar o perfil para ignorar algumas telas durante a execução do Assistente de Configuração <!-- 2276470 -->
Ao criar um perfil de registro do macOS, você poderá configurá-lo para ignorar qualquer uma das telas a seguir quando um usuário executar o Assistente de Configuração:
- Migração do Android
- Tom de Exibição
- Privacidade
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Alteração no processo de atualização de conectores locais <!-- 2277554 -->
Com base nos comentários dos clientes, a maneira em que as atualizações são feitas nos conectores locais será alterada. Depois que você instalar um conector local inicialmente, as atualizações passarão a ocorrer automaticamente. Essa alteração começará com o novo conector de certificado PFX para Microsoft Intune e, posteriormente, será distribuída a outros tipos de conectores locais. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Suporte para registrar configuração de DNS para VPN do Windows 10 <!-- 2282852 -->
Você poderá configurar perfis VPN do Windows 10 para registrar dinamicamente os endereços IP atribuídos à interface VPN com o DNS interno, sem precisar usar perfis personalizados.
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md) lista as configurações de perfil VPN disponíveis. 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>Restringir aplicativos e bloquear o acesso aos recursos da empresa nos dispositivos iOS e Android for Work <!-- 2451462 -->
Em **Conformidade de dispositivos** > **Políticas** > **Criar política** > **Android for Work** > **Segurança do Sistema**, haverá uma nova configuração **Aplicativos restritos**. Essa nova configuração usa uma política de conformidade para bloquear o acesso aos recursos da empresa quando determinados aplicativos estão instalados no dispositivo. O dispositivo é considerado não compatível até que os aplicativos restritos sejam removidos dele.
Aplica-se a: 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>Exportar as políticas de conformidade do Portal Clássico do Azure para um arquivo .csv <!-- 2469637 -->
As políticas de conformidade criadas no Portal Clássico do Azure serão preteridas.  Quando isso acontecer, você poderá examinar e excluir todas as políticas existentes. Não será possível atualizá-las. Você pode exportar as políticas como um arquivo .csv (arquivo separado por vírgula). Em seguida, use os detalhes no arquivo para recriar essas políticas no Intune no portal do Azure.
> [!IMPORTANT]
> Quando o Portal Clássico do Azure for desativado, você não poderá mais acessar suas políticas e nem as visualizar. Portanto, exporte-as e recrie-as no portal do Azure antes que o Portal Clássico do Azure seja desativado.

### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Alterar a terminologia para "desativar" e "apagar" <!-- 2175759 -->
Para ficar consistente com a API do Graph, os termos a seguir serão alterados na documentação e na interface do usuário do Intune:
- **Remover os dados da empresa** será alterado para **desativar**
- **Redefinição de fábrica** será alterado para **apagar**



<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Mais oportunidades de sincronização no aplicativo Portal da Empresa para Windows <!-- 2683177 -->
O aplicativo Portal da Empresa para Windows está adicionando uma ação de sincronização do dispositivo às listas de atalhos do menu Iniciar e da barra de tarefas do Windows. Clique em qualquer um dos locais para sincronizar rapidamente seus dispositivos e obter acesso a recursos corporativos.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Redefinir senhas de dispositivo por meio do Portal da Empresa para Windows 10 <!-- 2101282 --> 
Em breve seus funcionários poderão redefinir o PIN ou a senha do dispositivo usando diretamente o aplicativo Portal da Empresa para Windows 10. Essa funcionalidade estará disponível em dispositivos locais e remotos gerenciados pelo Intune compatíveis com redefinições de senha. Dependendo do tipo de dispositivo, uma solicitação feita para um dispositivo remoto removerá a senha atual do dispositivo ou criará uma senha temporária. Os usuários que solicitam uma redefinição de um dispositivo local serão redirecionados ao aplicativo de Configurações do dispositivo.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Novas experiências de navegação no aplicativo Portal da Empresa para Windows <!-- 2317227 -->  
Ao navegar ou pesquisar aplicativos no aplicativo Portal da Empresa para Windows, você poderá alternar entre a exibição **Blocos** existente e a exibição **Detalhes** recém-adicionada. A nova exibição lista detalhes do aplicativo, como nome, editor, data de publicação e status da instalação.  

A página **Aplicativos** apresenta uma nova exibição **Instalados** que permite ver detalhes sobre as instalações de aplicativos concluídas e em andamento. Deseja compartilhar comentários ou ideias sobre as novas alterações? Envie-nos comentários no aplicativo Portal da Empresa.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Melhoria na experiência do aplicativo Portal da Empresa para os usuários gerentes de registros de dispositivo <!-- 675800 -->
Quando um DEM (gerente de registros de dispositivo) entra no aplicativo Portal da Empresa para Windows, o aplicativo lista apenas o dispositivo em execução atual do DEM. Essa melhoria reduz os tempos limite que ocorriam anteriormente quando o aplicativo tentava carregar todos os dispositivos registrados pelo DEM.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Usar licenças de dispositivo VPP para pré-provisionar o Portal da Empresa durante o registro no DEP <!-- 1608345 -->
Você poderá usar licenças de dispositivo do VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante os registros no DEP (Programa de registro de dispositivos). Para fazer isso, quando você criar ou editar um perfil de registro, especifique o token VPP que deseja usar para instalar o Portal da Empresa. Verifique se o token não expira e se você tem licenças suficientes para o aplicativo de Portal da Empresa. Caso o token for expirar ou for executado sem licenças, o Intune enviará por push o Portal da Empresa da App Store (uma ID da Apple será solicitada).

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Extensões de arquivo de aplicativos de LOB (linha de negócios) do Windows <!-- 1884873 -->
As extensões de arquivo para aplicativos de LOB do Windows agora incluem *.msi*, *.appx*, *.appxbundle*, *.msix* e *.msixbundle*. Você pode adicionar um aplicativo no Microsoft Intune selecionando **Aplicativos móveis** > **Aplicativos** > **Adicionar**. O painel **Adicionar aplicativo** é exibido permitindo que você selecione o **Tipo de aplicativo**. Para aplicativos de LOB do Windows, selecione aplicativo de **Linha de negócios** como o tipo de aplicativo, selecione o **Arquivo de pacote do aplicativo** e, em seguida, insira um arquivo de instalação com a extensão apropriada.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pacote de configuração do Windows Defender ATP adicionado automaticamente ao perfil de configuração <!-- 2144658 -->
Ao usar dispositivos de [Proteção Avançada contra Ameaças e integração](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) no Intune, no momento, você baixa um pacote de configuração e adiciona-o ao perfil de configuração. Em uma atualização futura, o Intune obterá automaticamente o pacote da Central de Segurança do Windows Defender e o adicionará ao seu perfil.

Aplica-se ao Windows 10 e posteriores.

### <a name="check-for-sccm-compliance----2192052---"></a>Verificar a conformidade com o SCCM <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o SCCM (System Center Configuration Manager) (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O SCCM envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do SCCM retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No SCCM, esse requisito tem o estado "Instalar". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token do VPP ou de licença do Portal da Empresa quase acabando <!-- 2237572 -->
Se você usar o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem quase acabando.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Confirmação necessária para excluir o token do VPP que está sendo usado para o pré-provisionamento do Portal da Empresa <!-- 2237634 -->
Será necessária uma confirmação para excluir um token do VPP (Volume Purchase Program) se ele estiver sendo usado para pré-provisionar o Portal da Empresa durante o registro no DEP.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Configurações de segurança adicionais para o Windows Installer <!-- 2282430 -->
Você poderá permitir que os usuários controlem as instalações de aplicativo. Se habilitadas, as instalações que, de outra forma, poderiam ser interrompidas devido a uma violação de segurança teriam permissão para continuar. Você poderá instruir o Windows Installer a usar permissões elevadas quando ele instalar um programa em um sistema. Além disso, você poderá permitir que os itens da WIP (Proteção de Informações do Windows) sejam indexados e os metadados sobre eles, armazenados em um local não criptografado. Quando a política for desabilitada, os itens protegidos pela WIP não serão indexados e não serão exibidos nos resultados da Cortana ou no Explorador de Arquivos. A funcionalidade dessas opções estará desabilitada por padrão. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Teclados de terceiros podem ser bloqueados por configurações de APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune poderão bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivos. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Exigir senha não biométrica na inicialização do aplicativo e tempo limite <!-- 1506985 -->

Ao exigir uma senha não biométrica na inicialização do aplicativo e após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Visualizar uma nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968 -->
Estamos adicionando novos recursos, com base nos comentários dos clientes, ao site do Portal da Empresa e ao catálogo de aplicativos iOS. Você fará uma melhoria significativa na funcionalidade existente e na usabilidade dos seus dispositivos Android, iOS e Windows. Áreas do site, como detalhes do dispositivo, comentários e suporte e visão geral do dispositivo, receberão um design novo, moderno e responsivo. Você também verá:

- Fluxos de trabalho simplificados em todas as plataformas de dispositivo
- Fluxos de identificação e registro de dispositivo aprimorados
- Mensagens de erro mais úteis
- Linguagem mais amigável, menos jargão técnico
- Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos
- Maior acessibilidade para todos os usuários

Atualmente, a atualização está em versão prévia. Registre-se para participar da versão prévia em http://aka.ms/webcpflighting

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Exigir senha não biométrica na inicialização a frio do aplicativo e tempo limite <!-- 1506985 --> 

Ao exigir uma senha não biométrica na inicialização a frio do aplicativo e após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Capacidade de implantar aplicativos LOB (aplicativo de linha de negócios) necessários para Todos os usuários em dispositivos do Windows 10 Desktop <!-- 1627835 RS4 -->
Os clientes poderão implantar os aplicativos de linha de negócios do Windows 10 necessários que deverão ser instalados em contextos de dispositivo. Isso permitirá que esses aplicativos estejam disponíveis para todos os usuários no dispositivo. Isso se aplica somente a dispositivos Windows 10 Desktop.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Atualizando a experiência de Ajuda e Comentários no aplicativo Portal da Empresa para Android <!--1631531 -->

Atualizaremos as experiências de Ajuda e Comentários no aplicativo Portal da Empresa para Android para alinhá-las às práticas recomendadas para aplicativos Android. Atualizaremos o aplicativo Portal da Empresa para Android nos próximos meses para dividir o item de menu **Ajuda e Comentários** nos itens **Ajuda** e **Enviar Comentário** separados. A página **Ajuda** conterá com uma seção de **Perguntas Frequentes** e um botão **Suporte por Email** para instruir os usuários finais a carregar logs para a Microsoft e enviar email para o suporte da empresa descrevendo o problema. **Enviar Comentários** guiará o usuário por um envio de comentários padrão da Microsoft, que solicitará ao usuário escolher entre “Gosto de algo”, “ Não gosto de algo” ou “Tenho uma ideia”.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.



