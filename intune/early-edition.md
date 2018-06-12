---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95ad588b084319cd8a0f5f5c5d92da0e892eed50
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745036"
---
# <a name="the-early-edition-for-microsoft-intune---june-2018"></a>A edição antecipada do Microsoft Intune – junho de 2018

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

<!-- 1806 start -->

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>Suporte para COSU (uso único de propriedade corporativa) para dispositivos Android <!-- 1630973 -->

O Intune oferecerá suporte a dispositivos com Android altamente gerenciados e bloqueados no estilo quiosque. Isso permite que os administradores bloqueiem ainda mais o uso de um dispositivo para um único aplicativo ou um conjunto pequeno de aplicativos, e impede que os usuários habilitem outros aplicativos ou executem outras ações no dispositivo.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>suporte do macOS para o Programa de Registro de Dispositivo da Apple <!-- 747651 -->

O Intune oferecerá suporte ao registro de dispositivos macOS no DEP (Programa de Registro de Dispositivos) da Apple. Para fazer isso:

1. Em deploy.apple.com, atribua números de série macOS a um servidor do MDM.
2. Importe os números de série para o Intune.
3. Crie um perfil do programa de registro específico para dispositivos macOS.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Alterações de nome do Google para Android for Work e Play for Work <!--842873 -->
O Intune atualizará a terminologia "Android for Work" para refletir as alterações de identidade visual do Google.  Os termos "Android for Work" e "Play for Work" não serão mais usados. Será usada uma terminologia diferente, dependendo do contexto:

- "Empresarial Android" refere-se à pilha de gerenciamento Android moderna geral.
- "Perfil de Trabalho" ou "Proprietário de Perfil" refere-se a dispositivos BYOD gerenciados com perfis de trabalho.
- "Google Play gerenciado" refere-se à loja de aplicativos do Google.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Monitorar o status de configuração de aplicativo do iOS por dispositivo <!-- 880037 eeready eestaged -->

Como o administrador do Microsoft Intune, você poderá monitorar o status de configuração de aplicativo do iOS para cada dispositivo gerenciado. No **Microsoft Intune**, no portal do Azure, selecione **Dispositivos** > **Todos os dispositivos**. Na lista de dispositivos gerenciados, selecione um dispositivo específico para exibir uma folha para o dispositivo. Na folha do dispositivo, selecione **Configuração de aplicativo**.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Teclados de terceiros podem ser bloqueados por configurações de APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune poderão bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivos. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Criar política de conformidade do dispositivo usando as configurações do Firewall em dispositivos macOS <!-- 1497640 -->
Quando você cria uma nova política de conformidade macOS (**Conformidade do dispositivo** > **Políticas** > **Criar política**  >  **Plataforma: macOS** > **Segurança do sistema**), haverá algumas novas configurações de **Firewall** disponíveis: 
- **Firewall**: configure como conexões de entrada são tratadas em seu ambiente.
- **Conexões de entrada**: **Bloquear** todas as conexões de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Essa configuração também bloqueia todos os serviços de compartilhamento.
- **Modo Furtivo**: **Habilite** o modo furtivo para impedir que o dispositivo responda a solicitações de investigação. O dispositivo continua a responder a solicitações de entrada para aplicativos autorizados.

Aplica-se a: macOS 10.12 e posteriores

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Usar sAMAccountName como o nome de usuário da conta para perfis de email <!-- 1500307 -->

Você poderá usar o **sAMAccountName** local como o nome de usuário da conta para perfis de email para Windows 10, iOS e Android. Você também será capaz de obter o domínio do atributo `domain` ou `ntdomain` no Azure AD (Azure Active Directory). Ou insira um domínio estático personalizado.

Para usar esse recurso, você deve sincronizar o atributo `sAMAccountName` do seu ambiente do Active Directory local com o Azure AD.

Aplica-se a: Android, iOS, Windows 10 e posteriores

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Exigir senha não biométrica na inicialização do aplicativo e tempo limite <!-- 1506985 -->

Ao exigir uma senha não biométrica na inicialização do aplicativo e após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Apagamento seletivo de dados de aplicativo da organização <!-- 1507030 -->
Os administradores poderão configurar um apagamento seletivo de dados da organização como uma nova ação quando as condições de configurações de Acesso APP (Políticas de Proteção do Aplicativo) não forem atendidas.  Esse recurso ajuda os administradores a proteger e remover automaticamente dados confidenciais de empresa de aplicativos com base em critérios previamente configurados.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Revogar um aplicativo iOS adquirido por meio do VPP <!-- 1777384 -->
Como o administrador do Microsoft Intune, você poderá revogar a licença para um aplicativo iOS selecionado adquirido por meio do VPP (programa de compra de volume). Você poderá notificar os usuários quando um aplicativo não estiver mais atribuído a eles. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. A contagem de licenças recuperadas será refletida no nó **Aplicativos Licenciados** na carga de trabalho de **Aplicativo** do Intune. Para obter mais informações relacionadas a aplicativos VPP iOS, veja [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>Revogar a licença de aplicativo VPP iOS <!-- 1863797 -->
Como administrador, você poderá recuperar uma licença de aplicativo de VPP iOS atribuída a um usuário ou dispositivo. Desinstalar um aplicativo VPP iOS também permitirá que você recupere a licença do aplicativo. Em seguida, você pode optar por atribuir a licença do aplicativo a outro usuário ou dispositivo. Para obter mais informações sobre licenças de aplicativo VPP iOS, consulte [Gerenciar aplicativos adquiridos por volume do iOS no Microsoft Intune](vpp-apps-ios.md).

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968 -->
Estamos adicionando novos recursos, com base nos comentários dos clientes, ao site Portal da Empresa. Você fará uma melhoria significativa na funcionalidade existente e na usabilidade dos seus dispositivos Android, iOS e Windows. Áreas do site, como detalhes do dispositivo, comentários e suporte e visão geral do dispositivo, receberão um design novo, moderno e responsivo. Você também verá:

- Fluxos de trabalho simplificados em todas as plataformas de dispositivo
- Fluxos de identificação e registro de dispositivo aprimorados
- Mensagens de erro mais úteis
- Linguagem mais amigável, menos jargão técnico
- Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos
- Maior acessibilidade para todos os usuários

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Editar suas implantações de aplicativo do Office 365 Pro Plus <!-- 2150145 -->
Como o administrador do Microsoft Intune, você terá maior capacidade de editar suas implantações de aplicativo do Office 365 Pro Plus. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Aplicativos**. Na lista de aplicativos, selecione o Pacote Office 365 Pro Plus.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Revisão por linha de identificadores de dispositivo corporativo duplicados carregados <!-- 2203794 -->
Ao carregar IDs corporativas, o Intune fornece uma lista de todas as duplicatas e dá a opção de substituir ou manter as informações existentes. O relatório será exibido se houver duplicatas depois que você escolher **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar Identificadores**. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Adicione manualmente identificadores de dispositivo corporativo <!-- 2203803 -->
Você poderá adicionar manualmente as IDs de dispositivo corporativo. Escolha **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar**.

### <a name="new-status-for-devices-in-device-configuration----2308882---"></a>Novo status para dispositivos na configuração do dispositivo <!-- 2308882 -->
Em **Configuração do dispositivo** > **Visão geral**, serão adicionados novos estados a seguir:
- bem-sucedido
- erro
- conflito
- pendente
- não aplicável Uma imagem que mostra a contagem de dispositivos de uma plataforma diferente também é mostrada. Por exemplo, se você estiver procurando em um perfil do iOS, o novo bloco mostrará a contagem de dispositivos não iOS que também estão atribuídos a esse ele. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>A conformidade do dispositivo é compatível com soluções de antivírus de terceiros <!-- 2325484 -->
Quando você cria uma política de conformidade do dispositivo (**Conformidade do dispositivo** > **Políticas** > **Criar política**  >  **Plataforma: Windows 10 e posteriores** > **Configurações** > **Segurança do sistema**), haverá novas opções de **Segurança do Dispositivo**: 
- **Antivírus**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antivírus registradas com a Central de Segurança do Windows, como Symantec. 
- **AntiSpyware**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antispyware registradas com a Central de Segurança do Windows, como Symantec. 

Aplica-se ao Windows 10 e posteriores 

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Suporte para perfis de VPN GlobalProtect da Palo Alto Networks <!-- 1333680 eeready ! -->

Com essa atualização, você pode escolher o GlobalProtect da Palo Alto Networks como um tipo de conexão VPN para perfis VPN no Intune (**Configuração do dispositivo** > **Perfis**  >  **Criar perfil** > **Tipo de perfil** > **VPN**). Nesta versão, há suporte para as seguintes plataformas: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Definir a conformidade de acordo com a localização do dispositivo <!-- 851881 ! -->
Em algumas situações, convém restringir o acesso aos recursos corporativos a uma localização específica, definida por uma conexão de rede. Você poderá criar uma política de conformidade (**Conformidade do dispositivo** > **Locais**) com base no endereço IP do dispositivo. Se o dispositivo sair do intervalo de IP, ele não poderá mais acessar os recursos corporativos.

Aplica-se a: dispositivos Android 6.0 e superiores, com o aplicativo Portal da Empresa atualizado

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Solução aprimorada de problemas de instalação do aplicativo <!-- 928990 -->
Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. Estamos enviando uma Visualização Pública dos nossos recursos de Solução de Problemas de Aplicativo. Você observará um novo nó em cada dispositivo individual com o nome **Aplicativos Gerenciados**. Ele lista os aplicativos que foram entregues por meio do MDM do Intune. Dentro do nó, você verá uma lista dos estados de instalação do aplicativo. Se você selecionar um aplicativo individual, verá o modo de exibição de solução de problemas desse aplicativo específico. Na exibição de solução de problemas, você verá o ciclo de vida completo do aplicativo, por exemplo, quando o aplicativo foi criado, modificado, direcionado e entregue a um dispositivo. Além disso, se a instalação do aplicativo não for bem-sucedida, você receberá o código de erro e uma mensagem útil sobre a causa do erro.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Exigir senha não biométrica na inicialização a frio do aplicativo e tempo limite <!-- 1506985 --> 

Ao exigir uma senha não biométrica na inicialização a frio do aplicativo e após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquear acesso do aplicativo com base em modelos e fornecedores de dispositivos não aprovados <!-- 1425689 ! -->
O administrador de TI do Intune será capaz de impor uma lista especificada de fabricantes Android e/ou modelos de iOS por meio das Políticas de Proteção de Aplicativo do Intune. O administrador de TI pode fornecer uma lista separada por ponto e vírgula de fabricantes para políticas do Android e de modelos de dispositivos para políticas do iOS. As Políticas de Proteção de Aplicativo do Intune servem apenas para Android e iOS. Haverá duas ações diferentes que podem ser executadas nessa lista especificada:
- Um bloqueio de acesso do aplicativo em dispositivos que não estão especificados.
- Ou uma limpeza seletiva de dados corporativos em dispositivos que não estão especificados. 

O usuário não conseguirá acessar o aplicativo direcionado se os requisitos por meio da política não forem atendidos. Com base nas configurações, o usuário pode ser bloqueado ou passar por uma limpeza seletiva dos dados corporativos no aplicativo. Em dispositivos iOS, esse recurso exige a participação de aplicativos (por exemplo, WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune para as configurações de versão mínima serem impostas aos aplicativos direcionados. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. No Android, esse recurso exige a versão mais recente do Portal da Empresa. 

Em dispositivos de usuário final, o cliente do Intune executaria uma ação com base em uma correspondência simples das cadeias de caracteres especificadas na folha do Intune para Políticas de Proteção de Aplicativo. Isso depende totalmente do valor informado pelo dispositivo. Por isso, o administrador de TI é incentivado a garantir que o comportamento desejado seja preciso. Isso pode ser feito testando essa configuração com base em vários fabricantes e modelos de dispositivo direcionados a um grupo de usuários pequeno. No Microsoft Intune, selecione **Aplicativos Móveis** > **Políticas de proteção de aplicativo** para exibir e adicionar as políticas de proteção de aplicativo. Para saber mais sobre políticas de proteção de aplicativo, confira [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Habilitar o modo de quiosque em dispositivos com Windows 10 <!-- 1560072 ! -->
Em dispositivos com Windows 10, você pode criar um perfil de configuração e habilitar o modo de quiosque (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** > **Restrições do Dispositivo** > **Quiosque**). Nesta atualização, a configuração **Quiosque (visualização)** é renomeada para **Quiosque (obsoleto)**. **Quiosque (obsoleto)** não é mais recomendado para uso, mas continuará a funcionar até a atualização de julho. **Quiosque (obsoleto)** é substituído pelo novo tipo de perfil **Quiosque** (**Criar perfil** > **Windows 10** > **Quiosque (versão prévia)**), que conterá as configurações de quiosques no Windows 10 RS4 e versões posteriores.

Aplica-se ao Windows 10 e posteriores.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Recuperar a AUMID (ID de modelo de usuário do aplicativo associado) para aplicativos da Microsoft Store para Empresas no modo de quiosque <!-- 1560077 ! -->
O Intune poderá recuperar as AUMIDs (IDs de modelo de usuário do aplicativo) para aplicativos WSfB (Microsoft Store para Empresas) a fim de melhorar a configuração do perfil de quiosque.

Para saber mais sobre aplicativos da Microsoft Store para Empresas, confira [Gerenciar aplicativos da Microsoft Store para Empresas](windows-store-for-business.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Ações de acesso para políticas de proteção de aplicativo <!-- 1483510 EEready -->
Logo, você poderá configurar políticas de proteção de aplicativo para apagar, bloquear ou avisar explicitamente os dispositivos não compatíveis. A ação mais recente, *apagar*, remove os dados corporativos de um dispositivo. Se ocorrer uma limpeza, o usuário do dispositivo receberá uma notificação sobre o motivo da limpeza e etapas de remediação. Para algumas configurações, como a versão mínima do sistema operacional, você poderá aplicar várias ações, como bloquear e apagar. Essas ações são disparadas quando o aplicativo é iniciado.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Novas informações de inventário para dispositivos com Windows <!-- 1333569 eeready -->

Para dispositivos com Windows, as seguintes informações de inventário estarão disponíveis por dispositivo na guia **Hardware** (**Grupos** > **Todos os dispositivos móveis** > **Dispositivos** > escolha o dispositivo do usuário > **Exibir Propriedades** > **Hardware**):
- TPM
- Integração com antivírus
- AntiSpyware
- Firewall
- UAC
- Bateria
- Nome do domínio

Para obter mais sobre como esses dados são recuperados pelo CSP, veja as entradas de DeviceGuard no artigo [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp).

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune e o navegador Microsoft Edge <!-- 1818969 -->
O navegador Microsoft Edge para dispositivos móveis (iOS e Android) agora dá suporte a políticas de proteção de aplicativos do Intune. Os usuários que entrarem com suas contas corporativas do Azure AD no aplicativo de navegador Microsoft Edge estarão protegidos pelo Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nova configuração de idioma/região ao configurar o OOBE para Autopilot <!-- 1821766 -->
Uma nova definição de configuração estará disponível para definição do idioma e da região para perfis do Autopilot durante a configuração inicial pelo usuário.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nova configuração para o teclado do dispositivo <!-- 1821768 -->
Uma nova configuração estará disponível para definição do teclado para perfis do Autopilot durante a configuração inicial pelo usuário.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Use o TeamViewer para compartilhar a tela de dispositivos iOS e MacOS <!-- 1985547 -->
No momento, você pode usar o TeamViewer para administrar remotamente [dispositivos Android e Windows gerenciados pelo Intune](device-profile-android-teamviewer.md).

Os administradores poderão se conectar ao TeamViewer e iniciar uma sessão de compartilhamento de tela com dispositivos iOS e macOS. Usuários do iPhone, iPad e macOS podem compartilhar suas telas ao vivo com qualquer desktop ou dispositivo móvel. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>O gráfico de perfil do dispositivo do usuário está de volta <!-- 2160133 -->
Durante o aprimoramento das contagens numéricas exibidas no gráfico de perfil do dispositivo (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral** ), o gráfico de usuário gráfico foi temporariamente removido.

Com essa atualização, o gráfico de usuário está de volta, e é exibido no Portal do Azure.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Atribua todos os usuários e dispositivos como grupos de escopo <!-- 2196803 -->
Você poderá atribuir todos os usuários e dispositivos aos grupos de escopo. Para fazer isso, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de política e perfil** > **Atribuições** > escolher uma atribuição > **Escopo (grupos)**.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Perfis do AutoPilot passando para grupo direcionado a <!-- 1877935 -->
No momento, perfis de implantação do AutoPilot podem ser atribuídos a dispositivos selecionados. Após o lançamento desse recurso, você fará o seguinte para atribuir esses perfis:
- Criar grupos (Azure AD) contendo dispositivos AutoPilot
- Atribua os perfis desejados a um grupo do Azure AD. O perfil AutoPilot agora será atribuído a dispositivos AutoPilot naquele grupo.

### <a name="management-name-field-will-be-editable----1875989---"></a>O campo Nome de gerenciamento poderá ser editado <!-- 1875989 -->
Você poderá editar o campo de nome de gerenciamento na folha **Propriedades** de um dispositivo. Para editar esse campo, escolha **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo > **Propriedades**. Use o campo de nome de gerenciamento para identificar exclusivamente um dispositivo.

<!-- 1804 start -->

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Adições às configurações das opções de segurança do dispositivo local <!-- 1403702 -->
Você poderá definir as configurações adicionais de Opções de Segurança de Dispositivo Local para dispositivos Windows 10. Configurações adicionais estarão disponíveis nas áreas de Cliente de Rede da Microsoft, Servidor de Rede Microsoft, Acesso e segurança de rede e Logon interativo. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estarão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de remoção de dispositivo**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Impedir aplicativos e experiências de consumidor em dispositivos Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Você poderá impedir a instalação de aplicativos e experiências de consumidor nos seus dispositivos Windows 10 Enterprise RS4 AutoPilot. Para ver esse recurso, vá para **Intune** > **Registro de dispositivo** > **Registro do Windows** > **Perfis do Windows AutoPilot** > **Criar Novo** > **Configurações de registro**. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Suporte ao Multiple Exchange Connector <!-- 2070451 -->

Você não fica mais limitado a um Microsoft Intune Exchange Connector por locatário. O Intune dá suporte a vários Exchange Connectors para que você possa configurar o acesso condicional do Intune com diversas organizações do Exchange local.

Com um conector do Exchange local do Intune, você pode gerenciar o acesso ao dispositivo para suas caixas de entrada do Exchange local com base em se um dispositivo é registrado no Intune e está em conformidade com as políticas de conformidade de dispositivo do Intune. Para configurar um conector, baixe o conector do Exchange local do Portal do Azure no Intune e instale-o em um servidor na sua organização do Exchange. No painel do Microsoft Intune, escolha **Acesso local** e, em **Configuração**, selecione **Conector do Exchange ActiveSync**. Baixe o conector local do Exchange local e instale-o em um servidor na sua organização do Exchange. Agora que não há mais o limite de um conector do Exchange por locatário, se você tiver organizações do Exchange adicionais, siga este mesmo processo para baixar e instalar um conector para cada organização do Exchange adicional.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Capacidade de implantar aplicativos LOB (aplicativo de linha de negócios) necessários para Todos os usuários em dispositivos do Windows 10 Desktop <!-- 1627835 RS4 -->
Os clientes poderão implantar os aplicativos de linha de negócios do Windows 10 necessários que deverão ser instalados em contextos de dispositivo. Isso permitirá que esses aplicativos estejam disponíveis para todos os usuários no dispositivo. Isso se aplica somente a dispositivos Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Registro do Portal da Empresa melhorado <!-- 1874230-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior poderão concluir a primeira etapa de registro sem sair do aplicativo.

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



