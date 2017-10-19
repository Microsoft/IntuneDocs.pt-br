---
title: "Edição antecipada"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: abb5612545174e3fd134c38fb763e02d379b50d0
ms.sourcegitcommit: b330045a4f9a807e6e2772c4ed4e1e1148e1f1f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>A edição antecipada do Microsoft Intune – Outubro de 2017

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

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>O número de Versão do Aplicativo para linha de negócios no relatório de status de instalação do dispositivo <!-- 1233999 -->  
O relatório de status de instalação do dispositivo exibirá o número de versão do aplicativo para os aplicativos de linha de negócios iOS e Android. Você pode usar essas informações para solucionar problemas de seus aplicativos ou para localizar dispositivos que executam versões desatualizadas do aplicativo.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Cogerenciamento para dispositivos Windows 10  <!-- 124445 -->
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


### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Melhorias no fluxo de trabalho de configuração de dispositivo no Portal da Empresa <!--1490692-->  
Estamos melhorando o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para Android. A linguagem será mais fácil de usar e mais específica para sua empresa e vamos combinar as telas sempre que possível. 

### <a name="block-unsupported-samsung-knox-device-activation------1490695----"></a>Bloquear a ativação do dispositivo Samsung Knox sem suporte  <!--- 1490695 --->  
O aplicativo de Portal da Empresa tenta ativação Samsung KNOX somente durante o registro de MDM se o dispositivo aparecer na [lista de dispositivos KNOX com suporte](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Essa restrição ajuda a evitar erros de ativação do KNOX que impedem o registro de MDM. Dispositivos que não dão suporte à ativação de Samsung KNOX são registrados como dispositivos Android padrão. Um dispositivo Samsung pode ter alguns números de modelo que oferecem suporte a KNOX, enquanto outros não. Verifique a compatibilidade com Knox com o revendedor do dispositivo antes de adquirir e implantar dispositivos Samsung.

A seguinte lista contém modelos de dispositivos Samsung que não oferecem suporte a KNOX e que são registrados como dispositivos Android nativos pelo aplicativo Portal da Empresa para Android:

| **Nome do Dispositivo** | **Números de Modelos de Dispositivo** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN adicionado a dispositivos Windows 10 <!-- 1512457 -->  
O cliente poderá configurar o VPN da Citrix para seus dispositivos Windows 10. É possível escolher a VPN do Citrix na lista *Selecione um tipo de conexão* na folha **VPN da Base** ao configurar a VPN para Windows 10 e posterior.

> [!Note]
> A configuração do Citrix existia para iOS e Android.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Suporte para Google Play Protect no Android <!-- 908720  -->  
Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. O Intune oferecerá suporte aos recursos do Google Play Protect, incluindo atestado remoto do SafetyNet.  Os administradores podem definir requisitos de política de conformidade que exigem a configuração e a integridade do Google Play Protect. A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play.  O acesso condicional pode impedir que os usuários acessem recursos corporativos, se um dispositivo não for compatível com os requisitos do Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Impedir que os usuários de dispositivos com Android alterem a data e a hora de seus dispositivos <!-- 1333292 -->
Use uma [política de dispositivo personalizada do Android](custom-settings-android.md) para impedir que os usuários de dispositivos com Android alterem a data e a hora do dispositivo.
Para fazer isso, configure uma política personalizada do Android com o URI de configuração ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange, defina isso como **TRUE** e, em seguida, atribua-o aos grupos necessários.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Exibir as atribuições de política de proteção do aplicativo para solução de problemas <!--  1475003 -->
Nesta versão futura, a opção de **Política de proteção do aplicativo** será adicionada à lista suspensa **Atribuições** disponível na folha de solução de problemas. Agora você pode selecionar as políticas de proteção do aplicativo para ver as políticas de proteção de aplicativo atribuídas aos usuários selecionados.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Criar aplicativos iOS limitados a Apple App Stores regionais específicas <!-- 1281692 -->
Você poderá especificar a localidade do país durante a criação de um aplicativo gerenciado da Apple App Store.

> [!NOTE]  
> No momento, você só pode criar aplicativos gerenciados da Apple App Store que estão presentes na loja dos Estados Unidos.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Selecione o país da loja da Apple para sincronização de aplicativos VPP<!-- 1332311 -->  
Você poderá configurar a loja de um país do VPP (Volume Purchase Program) ao carregar seu token de VPP. O Intune sincroniza aplicativos VPP para todas as localidades da loja VPP especificada de um país.

> [!NOTE]  
> Atualmente, o Intune sincroniza apenas aplicativos VPP da loja VPP que correspondem à localidade do Intune na qual o locatário do Intune foi criado.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Atualizar usuário VPP do iOS e os aplicativos de dispositivo licenciados <!-- 1305564 -->  
Você poderá configurar o token de VPP do iOS para atualizar todos os aplicativos comprados para esse token por meio do serviço Intune. O Intune detectará as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará automaticamente ao dispositivo quando o dispositivo fizer check-in.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 1308838  -->
Estamos adicionando várias configurações novas ao perfil de restrição de dispositivo do Windows 10 Team para ajudar você a controlar dispositivos do Surface Hub.
Para saber mais sobre esse perfil, veja [Configurações de restrição de dispositivo do Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672(archived), 1119689 -->  
Você poderá criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Suporte remoto para Windows e dispositivos com Windows Mobile <!-- 1070473 -->    
O Intune poderá usar o software [TeamViewer](https://www.teamviewer.com), adquirido separadamente, para que você possa dar assistência remota a usuários que estão utilizando dispositivos com Windows e Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Verificar dispositivos com o Windows Defender <!-- 1280988  1280990   -->
Você poderá executar uma **Verificação rápida**, **Verificação completa** e **Atualizar assinaturas** com o Windows Defender Antivírus em dispositivos com Windows 10 gerenciados. Na folha de visão geral do dispositivo, escolha a ação a ser executada no dispositivo. Você precisará confirmar a ação antes de o comando ser enviado ao dispositivo. 

**Verificação rápida**: uma verificação rápida examina os locais em que o malware registra-se para começar, como as chaves do registro e pastas de inicialização conhecidas do Windows. Uma verificação rápida demora cerca de cinco minutos. Combinada com a configuração **Proteção sempre em tempo real**, que examina os arquivos quando eles são abertos, fechados e sempre que um usuário navega até uma pasta, uma verificação rápida ajuda a fornecer proteção contra malware que pode estar no sistema ou no kernel. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Verificação completa**: uma verificação completa pode ser útil em dispositivos que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa, e é útil para executar verificações sob demanda. A verificação completa pode demorar uma hora. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Atualizar assinaturas**: o comando para atualizar assinatura atualiza as definições e assinaturas de malware do Windows Defender. Isso ajuda a garantir o que Windows Defender Antivírus seja eficaz na detecção de malware. Esse recurso destina-se somente a dispositivos com Windows 10, com conectividade de internet pendente no dispositivo. 

### <a name="bitlocker-device-configuration----1397398---"></a>Configuração de dispositivo do BitLocker <!-- 1397398 -->  
**Criptografia Windows > Configurações de Base** incluirá uma nova configuração **Aviso para criptografia de outro disco** que permite que você desabilite o [prompt de aviso](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) para criptografia de outro disco que pode estar em uso no dispositivo do usuário.  A mensagem de aviso exige o consentimento do usuário antes de configurar o BitLocker no dispositivo e bloqueia a instalação do BitLocker até receber a confirmação do usuário final.  A nova configuração desabilita o aviso do usuário final.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->
A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquear a ação de copiar e colar entre perfis de trabalho e pessoais no Android for Work <!-- 1098994 -->   
Você poderá configurar o perfil de trabalho do Android for Work para bloquear a ação de copiar e colar entre os aplicativos pessoais e de trabalho. Encontre essa nova configuração no perfil **Restrições de dispositivo** para a plataforma **Android for Work** em **Configurações de perfil de trabalho**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho<!---1485783--->
Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Suplementos do MAM do Intune e Outlook para Android <!-- 1450688 -->
Em algumas semanas, a equipe do Office anunciará suplementos para o Outlook no Android. O conjunto de recursos desse suplemento já existe no Outlook no Windows, iOS, Web e Mac. Como os suplementos são gerenciados pelo Exchange, os usuários poderão copiar e compartilhar dados e mensagens entre o Outlook e aplicativos de suplementos não gerenciados, a menos que o acesso aos suplementos seja desativado pelo administrador do Exchange. 

Para gerenciar permissões de acesso do usuário aos suplementos, trabalhe com o administrador do Exchange para garantir que as políticas de proteção de dados de MAM se aplicam aos suplementos.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Se as políticas do Exchange já estiverem definidas para impedir o sideload ou a instalação de suplementos, não haverá a necessidade de continuar a leitura. Suas políticas de MAM serão aplicadas conforme o esperado. Se, no entanto, você tiver configurado as políticas de MAM para restringir operações de recortar, copiar e colar no Outlook no Android, e não tiver definido sua política de suplemento do Exchange, saiba que, por padrão, os usuários poderão instalar suplementos para o Outlook. Esses suplementos podem acessar o corpo e o assunto da mensagem, além de outras propriedades da mensagem. É possível desligar a capacidade do usuário de instalar suplementos fazendo com que o Administrador do Exchange remova as funções "Meus Aplicativos do Marketplace" e "Meus Aplicativos Personalizados".

A alteração da configuração no Exchange será aplicada no Outlook no Windows, iOS, Web, Mac e móvel. 

#### <a name="what-do-i-need-to-do"></a>O que eu preciso fazer?
Revise hoje suas políticas do Exchange. Informe sua equipe de TI e de suporte técnico. Entre em contato com nossa equipe de suporte se tiver perguntas ou dúvidas específicas. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->
Você poderá criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associa coleções de usuário e de entidades do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado.




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Ações para não conformidade <!--730266  846515 -->     
*Ações de não conformidade* são um novo recurso das políticas de conformidade que permite tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** estará disponível no espaço de trabalho **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10
<!--- 978575, 1308849, -->
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Suporte do Android for Work no Lookout <!-- 1087312 -->   
O conector do Intune com o Lookout dará suporte a dispositivos Android for Work ao usar o aplicativo Lookout for Work. Você pode implantar o aplicativo Lookout dentro ou fora do contêiner.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Proteção de Aplicativo do Intune e Ferramentas de Desenvolvimento do Citrix MDX <!-- 709185 -->
Você pode gerenciar dispositivos e aplicativos com uma combinação do Citrix XenMobile MDX e o Microsoft Intune. Isso permite que você gerencie aplicativos com políticas de proteção de aplicativo do Intune usando a tecnologia de mVPN da Citrix.

Você pode localizar um repositório de códigos que contém a Ferramenta de Encapsulamento de Aplicativo do Intune e o SDK de Aplicativo do Intune para iOS e Android, integrando com a tecnologia mVPN da Citrix MDX.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Novo parceiro de Defesa contra Ameaças Móveis   <!-- 954681 -->
Agora, é possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Zimperium, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como a integração com o Intune funciona?
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Zimperium. Você pode configurar políticas de acesso condicional de EMS com base na avaliação de risco do Zimperium habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade a recursos corporativos com base em ameaças detectadas.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->   
Você pode ter várias funções de CAS (Servidor de Acesso de Cliente) para o Exchange Connector local. Por exemplo, se o CAS principal falhar, o Exchange Connector recebe uma consulta para voltar a outros CASs. Esse recurso garante que o serviço não seja interrompido.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pacote de gerenciamento do System Center Operations Manager para Exchange Connector <!-- 885457 -->   
O pacote de gerenciamento do System Center Operations Manager para o Exchange Connector estará disponível para ajudá-lo a analisar os logs do Exchange Connector. Esse pacote de gerenciamento oferece diferentes maneiras de monitorar o Intune quando você precisar solucionar problemas.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fim do suporte para Android 4.3 e inferior <!---1171127, 1326920 --->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Os dispositivos que não forem atualizados até o início de outubro não poderão mais acessar o Portal da Empresa ou esses aplicativos. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.


## <a name="intune-apps"></a>Aplicativos do Intune

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Melhor orientação sobre a solicitação de acesso aos contatos em dispositivos Android <!--1484985-->   
O aplicativo de Portal da Empresa para Android normalmente exige que o usuário final aceite a permissão de Contatos. Se um usuário final recusar esse acesso, ele verá uma notificação no aplicativo que o alerta para conceder a permissão para acesso condicional.

### <a name="secure-startup-remediation-for-android---1490712--"></a>Correção de inicialização segura para Android <!--1490712-->     
Os usuários finais com dispositivos Android poderão tocar no motivo da não conformidade no aplicativo do Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema.


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirecionando usuários do macOS para nosso novo aplicativo do Portal da Empresa <!--1380728-->   
Quando um usuário final fizer o logon no site do Portal da Empresa para registrar seu dispositivo macOS, ele será direcionado a baixar o novo aplicativo do Portal da Empresa para macOS a fim de concluir o processo. Isso ocorre em dispositivos macOS usando OS X El Capitan 10.11 ou superior. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Suporte à autenticação baseada em certificado no Portal da Empresa para iOS <!--1029830-->
Adicionamos suporte para autenticação baseada em certificado (CBA) no aplicativo do Portal da Empresa para iOS. Os usuários com CBA inserem seus nomes de usuário, em seguida, tocam no link "Entrar com um certificado". O CBA já é compatível com os aplicativos do Portal da Empresa para Android e Windows. Você pode obter mais informações na página [entrar no aplicativo do Portal da Empresa](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->

### <a name="search-improvements-to-the-company-portal-website---1331697--"></a>Pesquisar aprimoramentos no site do Portal da Empresa <!--1331697-->  
Estamos melhorando os recursos de pesquisa do nosso aplicativo, começando com o [site do Portal da Empresa](https://portal.manage.microsoft.com). As pesquisas agora serão executadas em categorias de aplicativo, além dos campos de Nome e Descrição. Os resultados serão classificados, por padrão, em ordem decrescente de relevância. 

Usuários do iOS também receberão essa alteração, como o Portal da Empresa site também é usado como parte do aplicativo de Portal da Empresa para iOS. Os aplicativos de Portal da Empresa para Android e Windows receberão atualizações semelhantes nos próximos meses.

Ainda estamos ajustando maneira como a relevância é controlada, portanto, informe-nos como ele está funcionando usando o link "Comentários" na parte inferior do site do Portal da Empresa.

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->  
O aplicativo Portal da Empresa para Windows 10 permitirá que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->
Os aplicativos da empresa que foram disponibilizados com ou sem a inscrição no aplicativo Portal da Empresa Android podem ser instalados sem uma solicitação de inscrição.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>O Portal da Empresa do iOS exibe ícones grandes <!-- 1454593 -->
Estamos corrigindo um problema conhecido com o modo como o Portal da Empresa do iOS exibe ícones no bloco do aplicativo. Se você carregar ícones de aplicativo com 120 x 120 pixels ou maiores, eles serão exibidos no [site Portal da Empresa] (https://portal.manage.microsoft.com) e nas páginas de aplicativos do Portal da Empresa do iOS com o tamanho total do bloco de aplicativo.

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Suporte do Intune Managed Browser para iOS e Android <!-- 1374196 -->
A partir de outubro de 2017, o aplicativo do Intune Managed Browser no aplicativo do Android oferecerá suporte apenas a dispositivos que executam o Android 4.4 e versões posteriores. O aplicativo Intune Managed Browser no iOS oferecerá suporte apenas a dispositivos que executam o iOS 9.0 e versões posteriores. Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."




## <a name="notices"></a>Avisos

### <a name="device-and-app-management-integration----677972---"></a>Integração do gerenciamento de dispositivos e aplicativos <!-- 677972 -->   
Agora que o gerenciamento de dispositivo móvel do Intune (MDM) e o gerenciamento de aplicativo móvel (MAM) são ambos acessíveis do portal do Azure, o Intune começou integrar a experiência de administração de TI em torno do gerenciamento de aplicativo e dispositivo. Essas alterações têm o objetivo de simplificar seu dispositivo e a experiência de gerenciamento de aplicativo.

Saiba mais sobre as alterações de MDM e MAM anunciadas no [blog da equipe de suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->   
A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.


### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Novo caminho para dispositivos gerenciados na API do Graph <!-- 1586728 -->  
Na versão de serviço do Intune de outubro, estamos fazendo uma alteração no caminho usado para acessar os dispositivos gerenciados na versão beta da API do Graph.

| | |
|--|--|
| Caminho atual |  https://graph.microsoft.com/beta/managedDevices |
| Novo caminho | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Os dois caminhos funcionam durante o mês de outubro. Após o lançamento do serviço de outubro, somente o novo caminho funcionará.  Se você estiver usando a API do Graph para acessar os dispositivos gerenciados, atualize e verifique seus scripts e aplicativos com o novo caminho. Para obter outras alterações, verifique o [log mensal de alterações da API do Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/changelog).

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
