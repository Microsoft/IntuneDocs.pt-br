---
title: "Edição antecipada"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d612f0e3ff3f38d51488818916479e8291c9e453
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>A edição antecipada do Microsoft Intune – Novembro de 2017

A **edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não compartilhe essas informações fora da empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
>As seguintes alterações estão em desenvolvimento para o Intune. Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->


## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure


### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **integrado** tornará mais fácil para você criar e atribuir os aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Suporte para logon único para iOS <!-- 1333645 -->  
Você poderá usar o Logon Único para usuários do iOS. Os aplicativos iOS que são codificados para exigir credenciais do usuário no conteúdo do Logon Único são compatíveis com essa atualização de configuração de conteúdo. Você também pode usar o UPN e a ID de Dispositivo do Intune para configurar o Nome da entidade e o Realm.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API do inventário de aplicativos iOS 11 para detecção de ameaças móveis <!-- 1391759 -->
O Intune coleta informações do inventário de aplicativos em dispositivos pessoais e corporativos e as disponibiliza para provedores de Detecção de Ameaça Móvel (MTD) para efetuar o fetch, como Lookout for Work. Você poderá coletar o inventário de aplicativos dos usuários de dispositivos iOS 11+.

**Inventário de aplicativos**  
Inventários de dispositivos pessoais e corporativos iOS 11+ são enviados para o provedor de serviços de MTD. Os dados de inventário de aplicativos incluem:

 - ID do aplicativo
 - Versão de Aplicativo
 - Versão Curta do Aplicativo
 - Nome do Aplicativo
 - Tamanho do Pacote do Aplicativo
 - Tamanho Dinâmico do Aplicativo
 - O Aplicativo é validado ou não
 - O Aplicativo é gerenciado ou não

### <a name="audit-updates----1412961---"></a>Atualizações de auditoria <!-- 1412961 -->  
A auditoria do Intune fornece um registro das operações de alteração relacionadas ao Intune.  Todas as operações de criação, atualização, exclusão e de tarefa remota são capturadas e mantidas por um ano.  O portal do Azure fornece uma exibição dos últimos 30 dias de dados de auditoria em cada carga de trabalho e pode ser filtrado.  Uma API do Graph correspondente permite a recuperação dos dados de auditoria armazenados para o último ano. 

A auditoria é encontrada no grupo **MONITOR**. Há um item de menu de **Logs de Auditoria** para cada carga de trabalho.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocolo de texto permitido em Aplicativos gerenciados <!-- 1414050  -->
Aplicativos gerenciados pelo SDK do Aplicativo do Intune poderão enviar mensagens SMS.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Reiniciar remotamente o dispositivo iOS (somente supervisionado) <!-- 1424595 -->
Você poderá disparar um dispositivo iOS 10.3+ supervisionado para reiniciar usando uma ação do dispositivo. Para obter mais informações sobre como usar a ação de reinício de dispositivo, consulte [Reiniciar remotamente dispositivos com o Intune](device-restart.md).

> [!Note]  
> Este comando requer um dispositivo supervisionado e o direito de acesso de **Bloqueio de Dispositivo**. O dispositivo é reiniciado imediatamente. Dispositivos iOS protegidos por senha não serão reconectados a uma rede Wi-Fi após a reinicialização; Após a reinicialização, é possível que eles não se comuniquem com o servidor.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Bloquear dispositivos macOS gerenciados remotamente com o Intune <!-- 1437691 -->
Você poderá bloquear um dispositivo macOS perdido e definir um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

Para obter mais informações, consulte [Bloquear dispositivos gerenciados remotamente com o Intune](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Configurações de frequência do relatório da Proteção Avançada contra Ameaças do Windows Defender <!--- 1455974  --->
O serviço de Proteção Avançada contra Ameaças (WDATP) do Windows Defender permite que os administradores gerenciem a frequência dos relatórios para dispositivos gerenciados. Com a nova opção de **Agilizar a frequência de relatórios de telemetria**, o WDATP coleta dados e avalia os riscos com mais frequência. O padrão para relatórios otimiza a velocidade e o desempenho. Aumentar a frequência de emissão de relatórios pode ser importante para dispositivos de alto risco. Essa configuração pode ser encontrada no perfil **Windows Defender ATP** nas **Configurações do dispositivo**.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>A resolução de conflitos de atribuição foi alterada para aplicativos da iOS store <!-- 1480316 -->
Os usuários finais podem perceber alguma alteração na disponibilidade de aplicativos iOS store. No momento, um aplicativo que foi atribuído a dois grupos com um conflito entre **Necessário e Disponível** e **Não Aplicável**, é resolvido para **Necessário e Disponível**. Com a alteração, um aplicativo com este conflito é resolvido para **Não Aplicável**.

A alteração elimina a confusão quando um aplicativo é atribuído a vários grupos com propósitos de aplicativo diferentes.

Se você gostaria de ter seu aplicativo disponível no Portal do Operador de informações e no Portal da Empresa antes do lançamento do serviço em novembro, você tem duas opções:

1. Remover a atribuição **Não Aplicável** de seu grupo.
2. Criar um novo grupo que não inclui membros com a finalidade **Necessário e Disponível** atribuída e atribuir esse grupo como **Não Aplicável**.

Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

> [!Note]
> Após o lançamento você não poderá exibir ou modificar atribuições de aplicativo de Gerenciamento de Dispositivo Móvel (MDM) no console do Intune clássico. No entanto, você pode usar o console do Azure ou a API do Graph Intune para fazer atribuições de seu aplicativo.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Gerenciar dispositivos Android for Work independentemente dos dispositivos Android <!-- 1490731 -->
O Intune oferecerá suporte ao gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

Por padrão, as configurações de dispositivos Android for Work serão as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.
 
Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

Ao trabalhar com as novas configurações, considere o seguinte:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Se você nunca integrou o registro de Android for Work antes
A plataforma Android for Work está bloqueada nas restrições de Tipo de Dispositivo padrão. Após integrar o recurso, você poderá permitir que dispositivos se registrem com Android for Work. Para fazer isso, altere o padrão ou crie uma nova restrição de Tipo de Dispositivo para substituir a restrição padrão de Tipo de Dispositivo.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Se você tiver integrado o registro de Android for Work
Se você já tiver integrado antes, sua situação dependerá da configuração que escolher:

| Setting | Status de Android for Work na Restrição de Tipo de Dispositivo padrão | Anotações |
| --- | --- | --- |
| **Gerenciar todos os dispositivos como Android** | Bloqueado | Todos os dispositivos Android devem se registrar sem o Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work** | Permitido | Todos os dispositivos que oferecem suporte ao Android for Work devem ser registrados com Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work somente para os usuários nestes grupos** | Bloqueado | Uma política de Restrição de Tipo de Dispositivo separada foi criada para substituir o padrão. Essa política define os grupos que você selecionou anteriormente para permitir o registro Android for Work. Usuários dentro dos grupos selecionados ainda poderão registrar seus dispositivos Android for Work. Todos os outros usuários são impedidos de se registrar com o Android for Work. |

Em todos os casos, a norma pretendida é preservada. Nenhuma ação é necessária de sua parte para manter a permissão global ou por grupo do Android for Work em seu ambiente.

Essas alterações começarão a distribuição com a atualização de novembro, mas podem levar tempo para serem executadas em sua conta. Você receberá uma notificação de confirmação no portal do Office 365 quando essas alterações entrarem em vigor para a sua conta.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Suporte para vários conectores do Serviço de Registro de Dispositivo de Rede (NDES) <!-- 1528104 -->
O NDES permite a execução de dispositivos móveis sem credenciais de domínio para obter certificados baseados no protocolo SCEP. Com essa atualização, vários conectores NDES terão suporte.

### <a name="new-scep-profile-details-supported----1559808---"></a>Novos detalhes do perfil de SCEP com suporte <!-- 1559808 -->
Os administradores poderão definir configurações adicionais ao criar um perfil de SCEP em plataformas Android, Windows, iOS e macOS.  Os administradores podem definir o IMEI, o número ou o nome comum incluindo email no formato de nome do assunto.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurar um PIN de aplicativo iOS <!-- 1586774 -->
Em breve, você poderá exigir um PIN para aplicativos iOS determinados. Você pode configurar o requisito e a data de vencimento do PIN em dias por meio do portal do Azure. Quando necessário, um usuário deverá definir e usar um novo PIN antes de receber o acesso a um aplicativo iOS. Apenas os aplicativos iOS que têm a proteção de aplicativo habilitada com o SDK de Aplicativo do Intune oferecerão suporte a esse recurso.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Manter dados durante uma redefinição de fábrica <!-- 1588489 -->
Estamos adicionando o suporte a uma nova funcionalidade de redefinição de Fábrica do Windows. Agora, os administradores puderem especificar se o registro de dispositivo e outros dados fornecidos serão mantidos em um dispositivo após uma redefinição de fábrica. 
 
Os seguintes dados são mantidos após a redefinição de fábrica:
- Contas do usuário associadas ao dispositivo
- Estado do computador (ingresso no domínio, AADJ)
- Registro do MDM
- Aplicativos instalados pelo OEM (aplicativos do Win32 e da loja)
- Perfil de usuário
- Dados do usuário de fora do perfil do usuário
- Logon automático do usuário
 
Os dados a seguir não são preservados:
- Arquivos do usuário
- Aplicativos instalados pelo usuário (aplicativos do Win32 e da loja)
- Configurações do dispositivo não padrão 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>O status de instalação do aplicativo agora informa um gráfico de barras <!-- 1249446 -->  
O relatório de **Status de instalação do aplicativo** acessível para cada aplicativo por meio da lista de **Aplicativos** na carga de trabalho de **Aplicativos móveis** em breve serão renderizados como um gráfico de barras.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Adicionar "Encontrar meu iPhone" para dispositivos pessoais <!--1427287-->
Você poderá exibir se os dispositivos iOS têm o Bloqueio de Ativação ativado. Esse recurso podia ser encontrado anteriormente no portal clássico do Intune.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrições de registro atribuídas pelo grupo <!-- 747598 -->
Como um administrador do Intune, você poderá criar restrições personalizadas de registro de Tipo de Dispositivo e de Limite do Dispositivo para grupos de usuários.
 
O Portal do Azure do Intune permite criar até 25 instâncias de cada tipo de restrição que podem ser atribuídas a grupos de usuários. Restrições atribuídas a grupos substituem as restrições padrão.
 
Todas as instâncias de um tipo de restrição são mantidas em uma lista estritamente ordenada. Essa ordem define um valor de prioridade para resolução de conflitos. Um usuário afetado por mais de uma instância de restrição é restringido apenas pela instância com o valor de prioridade mais elevado. Você pode alterar a prioridade de uma determinada instância arrastando-a para uma posição diferente na lista. 
 
Essa funcionalidade será lançada com a migração das configurações de Android for Work no menu de registro do Android for Work para o menu de Restrições de Registro. Como esta migração pode levar vários dias, sua conta pode ser atualizada para outras partes do lançamento de novembro antes que você veja uma atribuição de grupo habilitada para Restrições de Registro.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Atribuições de anel de atualização do Windows 10 são exibidas <!-- 1621837 -->
Quando estiver **solucionando problemas,** para o usuário que estiver sendo exibido, você poderá ver todas as atribuições de anéis de atualização do Windows 10.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Solucionar problemas de registro  <!--- 746324 --->  
O espaço de trabalho da Solução de Problemas mostrará problemas de registro do usuário. Os detalhes sobre o problema e as etapas de correção sugeridas podem ajudar os administradores e os operadores de suporte técnico a solucionar problemas. Determinados problemas de registro não são capturados e alguns erros podem não ter as sugestões de correção.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Os administradores agora podem definir as configurações de Firewall em um dispositivo usando um perfil de configuração do dispositivo <!-- 951708 -->   
Os administradores podem ativar o firewall para dispositivos e também configurar vários protocolos para redes públicas, privadas e de domínio.  Essas configurações de firewall podem ser encontradas no perfil "Endpoint Protection".

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>O Windows Defender Application Guard ajuda a proteger dispositivos contra sites não confiáveis, conforme definido pela sua organização <!-- 958257 -->   
Os administradores podem definir sites como "confiáveis" ou "corporativos" usando um fluxo de trabalho da Proteção de Informações do Windows ou o novo perfil "Limite de rede" nas configurações do dispositivo. Os sites que não estão listados no limite de rede confiável de um dispositivo Windows 10 de 64 bits, caso sejam exibidos com o Microsoft Edge, serão abertos em um navegador com um computador virtual do Hyper-V.

O Application Guard pode ser encontrado nos perfis de configuração do dispositivo, no perfil "Endpoint Protection". A partir daí, os administradores podem configurar a interação entre o navegador virtualizado e o computador host, sites não confiáveis e sites confiáveis e dados de armazenamento gerados no navegador virtualizado. Para usar o Application Guard em um dispositivo, um limite de rede deve estar configurado primeiro. É importante definir somente um limite de rede para um dispositivo.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>O Windows Defender Application Guard no Windows 10 Enterprise fornece modo para confiar somente em aplicativos autorizados <!-- 1031096 -->    
Com milhares de novos arquivos mal-intencionados criados diariamente, usar a detecção baseada em assinatura de antivírus para combater o malware poderá deixar de fornecer uma defesa adequada contra novos ataques. Ao usar o Windows Defender Application Guard no Windows 10 Enterprise, é possível alterar a configuração do dispositivo de um modo no qual os aplicativos sejam confiáveis, a menos que sejam bloqueados por um antivírus ou outra solução de segurança, para um modo no qual o sistema operacional confie somente em aplicativos autorizados por sua empresa. Você atribui confiança aos aplicativos no Windows Defender Application Guard.

Com o Intune, é possível configurar políticas de controle de aplicativo no modo "somente auditoria" ou no modo de imposição. Os aplicativos não serão bloqueados durante a execução no modo "somente auditoria". O modo "somente auditoria" registra todos os eventos em logs do cliente local. Você também pode configurar se somente os componentes do Windows e os aplicativos da Windows Store podem ser executados ou se os aplicativos adicionais com boa reputação, conforme definido pelo Gráfico de Segurança Inteligente, poderão ser executados.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nova página de status de registro para registros do Windows 10 <!--1063201-->    
Agora é possível configurar uma mensagem que aparece quando os usuários registram dispositivos Windows 10. Use a **Tela de Status de Registro** para configurar uma mensagem personalizada e um hiperlink para serem exibidos aos usuários finais quando registrarem seus dispositivos Windows 10.  A **Tela de Status de Registro** também oferece aos usuários finais uma visão sobre o andamento das configurações de política que estão sendo aplicadas ao seu dispositivo.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>O Windows Defender Exploit Guard é um novo conjunto de recursos de prevenção contra intrusões para o Windows 10 <!-- 1063615 -->   
O Windows Defender Exploit Guard inclui regras personalizadas para reduzir a capacidade de exploração de aplicativos, impede ameaças à macro e ao script, bloqueia automaticamente conexões de rede para endereços IP de baixa reputação e pode proteger dados do ransomware e ameaças desconhecidas. O Windows Defender Exploit Guard consiste nos seguintes componentes:

- A **Redução da Superfície de Ataque (ASR)** fornece regras que permitem impedir ameaças a email, macro e script.
- O **acesso controlado a pastas** bloqueia automaticamente o acesso ao conteúdo de pastas protegidas.
- O **Filtro de Rede** bloqueia a conexão de saída de qualquer aplicativo para IP/domínio de baixa reputação
- O **Exploit Protection** fornece memória, fluxo de controle e restrições de políticas que podem ser usados para proteger um aplicativo contra explorações.

### <a name="app-conditional-launch-support----1193313---"></a>Suporte de inicialização condicional do aplicativo <!-- 1193313 -->
Os administradores de TI agora poderão definir um requisito por meio do portal de administração do Azure para impor uma senha em vez de um PIN numérico por meio do gerenciamento de aplicativo móvel (MAM) quando o aplicativo iniciar. Se configurado, o usuário será obrigado a definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. Esta versão do Intune permitirá esse recurso **somente no iOS**. O Intune dá suporte à senha de uma maneira semelhante ao PIN numérico, ele define um comprimento mínimo, permitindo caracteres e sequências repetidas. Este recurso requer a participação de aplicativos (como WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de aplicativos do Intune com o código para esse recurso em vigor para as configurações de senha a serem impostas aos aplicativos de destino.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>O número de versão do aplicativo de linha de negócios no relatório de instalação de dispositivo <!-- 1233999 -->  
O relatório de status de instalação do dispositivo exibirá o número de versão do aplicativo para os aplicativos de linha de negócios iOS e Android. Você pode usar essas informações para solucionar problemas de seus aplicativos ou para localizar dispositivos que executam versões desatualizadas do aplicativo.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogerenciamento para dispositivos Windows 10  <!-- 1243445 -->
O cogerenciamento é uma solução que fornece uma ponte do gerenciamento tradicional para o moderno e um caminho para fazer a transição usando uma abordagem em fases. Na sua base, o cogerenciamento é uma solução na qual os dispositivos Windows 10 são gerenciados simultaneamente pelo Configuration Manager e pelo Microsoft Intune, e também podem ser ingressados no AD (Active Directory) e no Azure AD (Azure Active Directory).  Essa configuração lhe fornece um caminho para modernizar ao longo do tempo, no ritmo que seja adequado para sua organização se você não puder mover tudo de uma só vez.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Definir o acesso para aplicativos pelo patch de segurança do Android mínimo no dispositivo<!-- 1278463 -->   
Um administrador poderá definir o patch de segurança do Android mínimo que deve ser instalado no dispositivo para obter acesso a um aplicativo gerenciado em uma conta gerenciada.

> [!Note]  
> Este recurso só restringe os patches de segurança lançados pela Google no Android 6.0 + dispositivos.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Novas configurações de restrição de dispositivo para Windows 10      <!-- 1308850 -->
-    Mensagens (somente celular) – Desabilite testes ou mensagens MMS
-    Senha – As configurações para habilitar o FIPS e o uso dos dispositivos secundários Windows Hello para autenticação 
-    Tela – Configurações para ativar ou desativar o dimensionamento do GDI para aplicativos herdados


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Restrições de dispositivo do modo de quiosque do Windows 10 <!-- 1308872 -->   
Você poderá restringir os usuários de dispositivos Windows 10 para o modo de quiosque, o que limita os usuários a um conjunto de aplicativos predefinidos.  Para fazer isso, crie um perfil de restrição de dispositivo Windows 10 e defina as configurações de Quiosque.

O modo de quiosque dá suporte a dois modos: **único aplicativo** (permite que um usuário execute apenas um aplicativo) ou **multiaplicativo** (permite o acesso a um conjunto de aplicativos).  Você define o nome do dispositivo e da conta de usuário, o que determina os aplicativos com suporte).  Quando o usuário está conectado, ele estará limitado aos aplicativos definidos.  Para obter mais informações, consulte [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

O modo de quiosque requer:

- O Intune deve ser a autoridade MDM.
- Os aplicativos já devem estar instalados no dispositivo de destino.
- O dispositivo deve ser [adequadamente provisionado](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Novo perfil de configuração do dispositivo para criar limites de rede <!-- 1311967 -->   
Criamos um perfil de configuração de dispositivo chamado **Limite de rede** que pode ser encontrado com seus outros perfis de configuração de dispositivo. Use esse perfil para definir os recursos online que você deseja que sejam considerados corporativos e confiáveis. Você deve definir um limite de rede para um dispositivo *antes* que os recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows, possam ser usados no dispositivo. É importante definir somente um limite de rede para cada dispositivo.

Você pode definir recursos de nuvem da empresa, intervalos de endereços IP e servidores proxy internos que você deseja que sejam considerados confiáveis. Depois de definido, um limite de rede pode ser consumido por outros recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Duas configurações adicionais para o Windows Defender Antivírus <!-- 1338409 -->  
**Nível de bloqueio de arquivo**

| | |
|---|---|
| Não configurado | **Não Configurado** usa o nível de bloqueio padrão do Windows Defender Antivírus e fornece detecção de alta segurança sem aumentar o risco de detectar arquivos legítimos. |
| Alta | **Alto** se aplica um alto nível de detecção.
| Alta +  | **Alto +** fornece um alto nível com medidas de proteção adicional que podem afetar o desempenho do cliente.
| Tolerância zero  | A **Tolerância zero** bloqueia todos os executáveis desconhecidos. |

Embora seja pouco provável, configurar como **Alto** pode fazer com que alguns arquivos legítimos sejam detectados.
É recomendável definir o nível de bloqueio do Arquivo para padrão, **Não configurado**.

**Extensão de tempo limite para verificação do arquivo pela nuvem**  

| | |
|--|--|
| Número de segundos (0-50) | Especifique o máximo de tempo para o Windows Defender Antivírus bloquear um arquivo enquanto aguarda um resultado da nuvem. O tempo padrão é de 10 segundos: qualquer tempo adicional especificado aqui (até 50 segundos) será adicionado a esses 10 segundos. Na maioria dos casos, a verificação leva muito menos tempo do que o máximo. Estender o tempo permite que a nuvem investigue completamente os arquivos suspeitos. É recomendável que você habilite essa configuração e especifique pelo menos 20 segundos adicionais. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Suporte para AC (Autoridade de Certificação) da Nuvem Symantec  <!-- 1333638 -->    
O Intune agora dá suporte à AC da Nuvem Symantec, que permite que o Conector de Certificado do Intune emita os certificados PKCS da AC da Nuvem Symantec para dispositivos gerenciados pelo Intune. Se você já estiver usando o Conector de Certificado do Intune com a AC (Autoridade de Certificação) da Microsoft, será possível aproveitar a configuração do Conector de Certificado do Intune existente para adicionar o suporte de AC da Symantec.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN adicionado a dispositivos Windows 10 <!-- 1512457 -->  
O cliente poderá configurar o VPN da Citrix para seus dispositivos Windows 10. É possível escolher a VPN do Citrix na lista *Selecione um tipo de conexão* na folha **VPN da Base** ao configurar a VPN para Windows 10 e posterior.

> [!Note]
> A configuração do Citrix existia para iOS e Android.



<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Suporte para Google Play Protect no Android <!-- 908720  -->  
Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. O Intune oferecerá suporte aos recursos do Google Play Protect, incluindo atestado remoto do SafetyNet.  Os administradores podem definir requisitos de política de conformidade que exigem a configuração e a integridade do Google Play Protect. A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play.  O acesso condicional pode impedir que os usuários acessem recursos corporativos, se um dispositivo não for compatível com os requisitos do Google Play Protect. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672(archived), 1119689 -->  
Você poderá criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Ações para não conformidade <!--730266  846515 -->     
*Ações de não conformidade* são um novo recurso das políticas de conformidade que permite tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Suporte do Android for Work no Lookout <!-- 1087312 -->   
O conector do Intune com o Lookout dará suporte a dispositivos Android for Work ao usar o aplicativo Lookout for Work. Você pode implantar o aplicativo Lookout dentro ou fora do contêiner.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Proteção de Aplicativo do Intune e Ferramentas de Desenvolvimento do Citrix MDX <!-- 709185 -->
Você pode gerenciar dispositivos e aplicativos com uma combinação do Citrix XenMobile MDX e o Microsoft Intune. Isso permite que você gerencie aplicativos com políticas de proteção de aplicativo do Intune usando a tecnologia de mVPN da Citrix.

Você pode localizar um repositório de códigos que contém a Ferramenta de Encapsulamento de Aplicativo do Intune e o SDK de Aplicativo do Intune para iOS e Android, integrando com a tecnologia mVPN da Citrix MDX.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->   
Você pode ter várias funções de CAS (Servidor de Acesso de Cliente) para o Exchange Connector local. Por exemplo, se o CAS principal falhar, o Exchange Connector recebe uma consulta para voltar a outros CASs. Esse recurso garante que o serviço não seja interrompido.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pacote de gerenciamento do System Center Operations Manager para Exchange Connector <!-- 885457 -->   
O pacote de gerenciamento do System Center Operations Manager para o Exchange Connector estará disponível para ajudá-lo a analisar os logs do Exchange Connector. Esse pacote de gerenciamento oferece diferentes maneiras de monitorar o Intune quando você precisar solucionar problemas.





## <a name="intune-apps"></a>Aplicativos do Intune

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ajudando seus usuários com o aplicativo de Portal da Empresa para Android <!---1573324, 1573150, 1558616, 1564878--->
O aplicativo de Portal da Empresa para Android está adicionando instruções para os usuários finais para ajudá-los a compreender e, quando possível, resolver automaticamente novos casos de uso. 

- Uma nova mensagem será exibida que explica que foi implantada uma política de conformidade para criptografia, mas o [fabricante do dispositivo não está criptografando o dispositivo](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) de acordo com as [diretrizes recomendadas do Google] (https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, booliano).
- Os usuários finais serão direcionados para o (portal do Azure Active Directory) [https://account.activedirectory.windowsazure.com/r/#/profile] para remover um dispositivo se tiverem atingido o número máximo de dispositivos que eles têm permissão para adicionar. 
- Os usuários finais devem seguir as etapas para ajudá-los a [corrigir erros de ativação em dispositivos Samsung KNOX](https://go.microsoft.com/fwlink/?linkid=859718) ou [desligar o modo de economia de energia](/intune-user-help/power-saving-mode-android). Se nenhuma dessas soluções resolver o problema, fornecemos uma explicação de como [enviar logs para a Microsoft](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nova ação “Resolver” disponível para dispositivos Android <!---1583480--->
O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android atualmente dá suporte a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [criptografia do dispositivo](/intune-user-help/encrypt-your-device-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirecionando usuários do macOS para nosso novo aplicativo do Portal da Empresa <!--1380728-->   
Quando um usuário final fizer o logon no site do Portal da Empresa para registrar seu dispositivo macOS, ele será direcionado a baixar o novo aplicativo do Portal da Empresa para macOS a fim de concluir o processo. Isso ocorre em dispositivos macOS usando OS X El Capitan 10.11 ou superior. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->
Os aplicativos da empresa que foram disponibilizados com ou sem a inscrição no aplicativo Portal da Empresa Android podem ser instalados sem uma solicitação de inscrição.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Suporte do Intune Managed Browser para iOS e Android <!-- 1374196 -->
A partir de outubro de 2017, o aplicativo do Intune Managed Browser no aplicativo do Android oferecerá suporte apenas a dispositivos que executam o Android 4.4 e versões posteriores. O aplicativo Intune Managed Browser no iOS oferecerá suporte apenas a dispositivos que executam o iOS 9.0 e versões posteriores. Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."




## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.




### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
