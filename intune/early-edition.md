---
title: "Edição antecipada"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9a2c104200518af31fd05e6b8abe853377767aa9
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>A edição antecipada do Microsoft Intune – Março de 2018

A **edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não compartilhe essas informações fora da empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
>As seguintes alterações estão em desenvolvimento para o Intune. Para obter mais informações sobre os novos recursos híbridos, confira a [página Novidades sobre híbridos](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Suporte ao Multiple Exchange Connector <!-- 2070451 -->

Você não fica mais limitado a um Microsoft Intune Exchange Connector por locatário. O Intune dá suporte a vários Exchange Connectors para que você possa configurar o acesso condicional do Intune com diversas organizações do Exchange local.

Com um conector do Exchange local do Intune, você pode gerenciar o acesso ao dispositivo para suas caixas de entrada do Exchange local com base em se um dispositivo é registrado no Intune e está em conformidade com as políticas de conformidade de dispositivo do Intune. Para configurar um conector, baixe o conector do Exchange local do Portal do Azure no Intune e instale-o em um servidor na sua organização do Exchange. No painel do Microsoft Intune, escolha **Acesso local** e, em **Configuração**, selecione **Conector do Exchange ActiveSync**. Baixe o conector local do Exchange local e instale-o em um servidor na sua organização do Exchange. Agora que não há mais o limite de um conector do Exchange por locatário, se você tiver organizações do Exchange adicionais, siga este mesmo processo para baixar e instalar um conector para cada organização do Exchange adicional.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Suporte futuro para novo cliente Cisco AnyConnect para iOS <!-- 1333708 -->

Os novos perfis de VPN criados para Cisco AnyConnect para iOS funcionam com o Cisco AnyConnect 4.0.7x e superior. Perfis existentes de VPN do Cisco AnyConnect do iOS serão rotulado como **Cisco Legacy AnyConnect** e continuarão a funcionar com o Cisco AnyConnect 4.0.5x como fazem atualmente.

> [!NOTE]
> Essa mudança afeta apenas o iOS. Continuará existindo apenas uma opção de Cisco AnyConnect para Android, Android for Work e macOS. 

#### <a name="more-information"></a>Mais informações

Você precisa criar um novo perfil de VPN do Cisco AnyConnect do iOS para dar suporte ao novo aplicativo, pois o novo aplicativo Cisco AnyConnect e o aplicativo Cisco Legacy AnyConnect são aplicativos separados. Se você estiver gerenciando o cliente AnyConnect em seu ambiente, também será necessário implantar o aplicativo Cisco AnyConnect. Para concluir uma atualização, você também precisa excluir o perfil de VPN do Cisco Legacy AnyConnect e remover o aplicativo Cisco Legacy AnyConnect. 

Integração de NAC (Controle de Acesso à Rede) não funcionará para o novo cliente AnyConnect na versão inicial. Estamos trabalhando com a Cisco para fornecer integração a NAC em uma futura versão do Intune.

### <a name="enhanced-jailbreak-detection----846515---"></a>Detecção de jailbreak avançada <!-- 846515 -->

A detecção de jailbreak avançada é uma nova configuração de conformidade que melhorará a maneira como o Intune avalia os dispositivos desbloqueados por jailbreak. A configuração fará com que o dispositivo faça check-in com o Intune com mais frequência, o que usará os serviços de localização do dispositivo e afetará o uso da bateria.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Capacidade de implantar aplicativos LOB (aplicativo de linha de negócios) necessários para Todos os usuários em dispositivos do Windows 10 Desktop <!-- 1627835 RS4 -->
Os clientes poderão implantar os aplicativos de linha de negócios do Windows 10 necessários que deverão ser instalados em contextos de dispositivo. Isso permitirá que esses aplicativos estejam disponíveis para todos os usuários no dispositivo. Isso se aplica somente a dispositivos Windows 10 Desktop. 

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Expiração de aplicativos de LOB (linha de negócios) para o Microsoft Intune <!-- 748789 -->
No Portal do Azure, o Intune alertará sobre aplicativos de linha de negócios que estão prestes a expirar. Após carregar uma nova versão do aplicativo de linha de negócios, o Intune removerá a notificação de expiração da lista de aplicativos.

### <a name="company-portal-enrollment-improved----1874230--"></a>Registro do Portal da Empresa melhorado <!-- 1874230-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior poderão concluir a primeira etapa de registro sem sair do aplicativo.

### <a name="new-management-name-column----1333586---"></a>Coluna Novo nome de gerenciamento <!-- 1333586 -->
Uma nova coluna chamada **Nome de gerenciamento** será adicionada à folha de dispositivos. Este é um nome não editável gerado automaticamente atribuído por dispositivo, com base na seguinte fórmula: 
- Nome padrão para todos os dispositivos: <username>_<devicetype>_<enrollmenttimestamp>
- Para dispositivos adicionados em massa: <PackageId/ProfileId>_<DeviceType>_<EnrollmentTime> 
 
Esta é uma coluna opcional na folha de dispositivos. Ele não estará disponível por padrão e só será possível acessá-lo por meio do seletor de colunas. O nome do dispositivo não é afetado por essa nova coluna.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Novas definições do perfil de configuração de dispositivo de notificações da Central de Segurança do Windows Defender <!-- 1631906 -->

Três novas definições serão adicionadas ao perfil de configuração de dispositivo de notificações do WDSC (Central de Segurança do Windows Defender).

Os administradores poderão:

- Ocultar o pilar de Identidade
- Ocultar o pilar de Hardware e suas subconfigurações
- Ocultar o pilar de Ransomware (restauração de arquivo do Onedrive for Business)

Quando você ocultar essas colunas do aplicativo WDSC, os usuários finais não poderão definir essas configurações e todas as notificações associadas aos componentes ocultos deixarão de ser geradas.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Políticas de MAM afetadas com base no estado de gerenciamento <!-- 1665993 -->

Você poderá afetar políticas de MAM com base no estado de gerenciamento do dispositivo:

- **Dispositivos iOS** – Você poderá afetar dispositivos não gerenciados (somente MAM) ou dispositivos gerenciados pelo Intune.
- **Dispositivos Android** – Você poderá afetar dispositivos não gerenciados, dispositivos gerenciados pelo Intune e Perfis Empresariais Android gerenciados pelo Intune (anteriormente Android for Work).

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>Configurar o Gatekeeper para controlar a origem do download do aplicativo macOS <!-- 1690459-->

Você poderá configurar o Gatekeeper para proteger os dispositivos de aplicativos, controlando de onde os aplicativos podem ser baixados. Você poderá configurar as seguintes fontes de download: **Mac App Store**, **Mac App Store e desenvolvedores identificados** ou **De qualquer lugar**. Você também poderá configurar se os usuários podem instalar um aplicativo usando CTRL + clique para substituir esses controles do Gatekeeper.

Essas configurações podem ser encontradas em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Configurar o firewall do aplicativo Mac <!-- 1690461 -->

Você poderá configurar o firewall de aplicativo Mac. Você pode usar isso para controlar as conexões por aplicativo, em vez de por porta. Isso facilita obter os benefícios da proteção de firewall e ajuda a impedir que aplicativos indesejáveis assumam o controle de portas de rede abertas para aplicativos legítimos.
 
Esse recurso pode ser encontrado em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

Depois de habilitar a configuração de Firewall, você pode configurar o firewall usando duas estratégias:

- Bloquear todas as conexões de entrada

   É possível bloquear todas as conexões de entrada para os dispositivos de destino. Se você optar por fazer isso, as conexões de entrada serão bloqueadas para todos os aplicativos. 

- Permitir ou bloquear aplicativos específicos

   Você pode permitir ou bloquear que aplicativos específicos recebam conexões de entrada. Você também pode habilitar o modo furtivo para impedir respostas para as solicitações de sondagem.
 
#### <a name="more-information"></a>Mais informações

- Bloquear todas as conexões de entrada

   Isso impede que todos os serviços de compartilhamento (como Compartilhamento de arquivos e Compartilhamento de tela) recebam conexões de entrada. Os serviços do sistema que ainda têm permissão para receber conexões de entrada são:
   - configd – implementa DHCP e outros serviços de configuração de rede
   - mDNSResponder – implementa o Bonjour
   - racoon – implementa IPsec

   Para usar os serviços de compartilhamento, verifique se **Conexões de entrada** está definido como **Não configurado** (não **Bloqueado**).

- Modo furtivo

   Habilite esta opção para impedir que o computador responda às solicitações de sondagem. O computador ainda responde a solicitações de entrada para aplicativos autorizados. Solicitações inesperadas, como o ICMP (ping), são ignoradas.
 

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Atualizando a experiência de Ajuda e Comentários no aplicativo Portal da Empresa para Android <!--1631531 -->

Atualizaremos a experiência de Ajuda e de Comentários no aplicativo Portal da Empresa para Android a fim de alinhá-lo com as práticas recomendadas para aplicativos Android. Estaremos atualizando o aplicativo Portal da Empresa para Android nos próximos meses para dividir o item de menu **Ajuda e Comentários** nos itens **Ajuda** e **Enviar comentários** separados. A página **Ajuda** conterá com uma seção de **Perguntas Frequentes** e um botão **Suporte por Email** para instruir os usuários finais a carregar logs para a Microsoft e enviar email para o suporte da empresa descrevendo o problema. **Enviar Comentários** guiará o usuário por um envio de comentários padrão da Microsoft, que solicitará ao usuário escolher entre “Gosto de algo”, “ Não gosto de algo” ou “Tenho uma ideia”.

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Categorias personalizadas de livros para livros eletrônicos do VPP (Volume Purchase Program) <!-- 1488911 -->
Você poderá criar categorias de livros eletrônicos personalizada e atribuir livros eletrônicos do VPP para essas categorias personalizadas. Os usuários finais poderão ver as categorias de livro eletrônico recém-criadas e os livros atribuídos às categorias.

#### <a name="company-portal-for-android-visual-updates---976944---"></a>Portal da empresa para atualizações visuais do Android <!--976944 -->

Estamos atualizando o aplicativo Portal da Empresa para Android para seguir as diretrizes do [Design de Material](https://material.io/) do Android. Publicaremos as imagens dos novos ícones para o artigo [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) quando o aplicativo for lançado. 


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Novo gráfico de tendência de falha de registro e tabela de motivos de falhas<!-- 1471783 -->

Na página Visão geral do registro, você poderá exibir a tendência de falhas de registro e as cinco principais causas de falhas. Ao clicar no gráfico ou na tabela, você poderá analisar os detalhes para encontrar dicas de solução de problemas e sugestões de correção.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Personalize os temas do Portal da Empresa com códigos hexadecimais <!--1049561 -->

Você poderá personalizar a cor do tema nos aplicativos do Portal da Empresa usando códigos hexadecimais. Ao inserir o código hexadecimal, o Intune determinará a cor do texto que fornece o maior nível de contraste entre a cor do texto e a cor da tela de fundo segundo os [padrões WCAG 2.0](http://www.w3.org/TR/WCAG20). É possível visualizar a cor do texto e o logotipo da empresa em relação à cor em **Aplicativos móveis** > **Portal da Empresa**. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Novas configurações do Windows Defender Credential Guard adicionadas às configurações do Endpoint Protection <!--1102252 --> 

Novas configurações do [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] serão adicionadas à **Configuração do dispositivo** > **Perfis** > **Endpoint Protection**. As configurações a seguir serão adicionadas: 

- Nível de Segurança da Plataforma: especifique se o Nível de Segurança da Plataforma está habilitado na próxima reinicialização. A segurança baseada em virtualização requer a Inicialização Segura. A segurança baseada em virtualização pode, opcionalmente, ser habilitada com o uso de proteções de DMA (acesso direto à memória). Proteções de DMA exigem suporte de hardware e serão habilitadas somente em dispositivos configurados corretamente.
- Segurança baseada em virtualização: especifique se a segurança baseada em virtualização será habilitada na próxima reinicialização. 
- Windows Defender Credential Guard: ative o Credential Guard com a segurança baseada em virtualização para ajudar a proteger as credenciais na próxima reinicialização quando o Nível de Segurança de Plataforma com Inicialização Segura e a Segurança Baseada em Virtualização estiverem habilitadas. As opções disponíveis incluem **Desabilitada**, **Habilitada com o bloqueio UEFI**, **Habilitada sem bloqueio** e **Não configurada**. 
  - A opção "Desabilitada" desativará o Credential Guard remotamente se ele estiver habilitado com a opção "Habilitada sem bloqueio".

  - A opção "Habilitada com o bloqueio UEFI" garante que o Credential Guard não possa ser desabilitado com a chave do Registro ou usando a Política de Grupo. Para desabilitar o Credential Guard após usar essa configuração, você precisa definir a Política de Grupo como "Desabilitada" e remover a funcionalidade de segurança em cada computador, com um usuário presente fisicamente, para limpar a configuração persistente na UEFI. Enquanto a configuração da UEFI persistir, o Credential Guard estará habilitado.

  - A opção "Habilitada sem bloqueio" permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, pelo menos, o Windows 10 (versão 1511).

  - A opção "Não configurada" deixa a configuração de política indefinida. A Política de Grupo não grava a configuração de política no Registro e, por isso, não tem impacto sobre computadores ou usuários. Se houver uma configuração atual no registro, ela não será modificada.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Redefina senhas de dispositivos Android O <!-- 1238299 -->
Você poderá redefinir as senhas de dispositivos Android O registrados. Quando você envia uma solicitação de "Redefinir senha" a um dispositivo Android O, ele define uma nova senha de desbloqueio de dispositivo ou um desafio de perfil gerenciado para o usuário atual. A senha ou o desafio é enviado, dependendo de o dispositivo ter um proprietário do perfil ou um proprietário do dispositivo, e entra em vigor imediatamente.

### <a name="local-device-security-option-settings----1251887---"></a>Configurações de opção de segurança do dispositivo local <!-- 1251887 -->
Você poderá habilitar configurações de segurança em dispositivos Windows 10 usando as novas configurações de Opção de segurança do dispositivo Local. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Novas configurações de impressora para perfis de educação <!-- 1308900 -->

Para perfis de educação, novas configurações estarão disponíveis na categoria **Impressoras**: **Impressoras**, **Impressora padrão**, **Adicionar novas impressoras**. 

### <a name="ios-app-provisioning-configuration----1581650---"></a>Configuração de provisionamento de aplicativos iOS <!-- 1581650 -->
Você poderá atribuir perfis de provisionamento de aplicativos iOS para impedir que os aplicativos expirem incluindo ou excluindo grupos de segurança.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Novas configurações do Windows Defender Exploit Guard <!-- 631893 -->

Seis novas configurações de **Redução da Superfície de Ataque** e funcionalidades expandidas de **Acesso controlado a pastas: Proteção de pasta** estarão disponíveis. Essas configurações podem ser encontradas em: Configuração do dispositivo\Perfis\
Criar perfil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Proteção avançada contra ransomware|Habilitado, Auditoria, Não configurado|Usar proteção agressiva contra ransomware.|
|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows|Habilitado, Auditoria, Não configurado|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows (lsass.exe).|
|Criação de processo de comandos WMI e PSExec|Bloquear, Auditoria, Não configurado|Bloquear criações de processo provenientes de comandos PSExec e WMI.|
|Processos não assinados e não confiáveis executados de um USB|Bloquear, Auditoria, Não configurado|Bloquear processos não assinados e não confiáveis executados de um USB.|
|Arquivos executáveis que não atendem um critério de prevalência, idade ou lista confiável|Bloquear, Auditoria, Não configurado|Bloquear a execução de arquivos executáveis a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.|

#### <a name="controlled-folder-access"></a>Acesso controlado à pasta

|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Proteção de pasta (já implementada)|Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> **Novo**<br>Bloquear modificação de disco, Auditar modificação de disco|
Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: impedir que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Novas configurações do Windows Defender Application Guard <!-- 1631890 -->

- **Habilitar aceleração de elementos gráficos**

Os administradores poderão habilitar um processador de gráficos virtual para o Windows Defender Application Guard. Essa configuração permite que a CPU descarregue a renderização de gráficos no vGPU. Isso pode melhorar o desempenho ao trabalhar com sites com uso intenso de gráficos ou ao assistir a vídeos dentro do contêiner.

- **SaveFilestoHost**

Os administradores poderão permitir que arquivos sejam passados do Microsoft Edge em execução no contêiner para o sistema de arquivos do host. Ativar essa configuração permitirá que os usuários baixem arquivos do Microsoft Edge no contêiner para o sistema de arquivos do host.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos para Android Enterprise <!-- 1813081 -->
Durante a atribuição de aplicativo e após selecionar um tipo de atribuição, o Android Enterprise (anteriormente conhecido como Android for Work) dará suporte à funcionalidade de exclusão.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Direcionamento de políticas de conformidade para dispositivos em grupos de dispositivo <!--1307012 -->

Você poderá direcionar políticas de conformidade para usuários em grupos de usuários. Você poderá direcionar políticas de conformidade para dispositivos em grupos de dispositivos.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurar um PIN de aplicativo iOS <!-- 1586774 -->
Em breve, você poderá exigir um PIN para aplicativos iOS determinados. Você pode configurar o requisito e a data de vencimento do PIN em dias por meio do portal do Azure. Quando necessário, um usuário deverá definir e usar um novo PIN antes de receber o acesso a um aplicativo iOS. Apenas os aplicativos iOS que têm a proteção de aplicativo habilitada com o SDK de Aplicativo do Intune oferecerão suporte a esse recurso.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>Redirecionando usuários do macOS para o novo aplicativo Portal da Empresa <!--1380728-->   
Quando um usuário final fizer o logon no site do Portal da Empresa para registrar seu dispositivo macOS, ele será direcionado a baixar o novo aplicativo do Portal da Empresa para macOS a fim de concluir o processo. Isso ocorre em dispositivos macOS usando OS X El Capitan 10.11 ou superior. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais com dispositivos Android recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."



## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.



### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


