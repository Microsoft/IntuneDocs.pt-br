---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: fbe8cc0fc3e835ee5807dfbe56ea1aa3c728547e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184719"
---
# <a name="the-early-edition-for-microsoft-intune---november-2018"></a>A edição antecipada do Microsoft Intune – Novembro de 2018

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

<!-- 1811 start -->

### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Como desinstalar aplicativos em dispositivos iOS supervisionados corporativos <!-- 1281677 -->
Você poderá remover qualquer aplicativo em dispositivos iOS supervisionados corporativos. Você pode remover qualquer aplicativo definindo como destino grupos de usuários ou dispositivos com um tipo de atribuição de **Desinstalação**. Para dispositivos iOS não supervisionados ou pessoais, você continuará podendo remover apenas os aplicativos instalados usando o Intune.

### <a name="track-installation-of-office-proplus---2620217--"></a>Controlar a instalação do Office ProPlus <!--2620217-->
Você poderá acompanhar o progresso da instalação do [Office ProPlus](apps-add-office365.md) usando a [Página de Status de Registro](windows-enrollment-status.md).

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133--"></a>Suporte do Programa de Registro de Dispositivos do macOS para contas do Apple School Manager <!--3006133-->
O Intune dará suporte usando o Programa de Registro de Dispositivos em dispositivos macOS para contas do Apple School Manager.

### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Pausar temporariamente o modo de quiosque em dispositivos Android para fazer alterações <!-- 3041935 -->
Ao usar dispositivos Android no modo de quiosque de vários aplicativos, um administrador de TI talvez precise fazer alterações ao dispositivo. Uma nova configuração de quiosque de vários aplicativos que permitirá a um Administrador de TI pausar temporariamente o modo de quiosque usando um PIN e obter acesso a todo o dispositivo.
Para ver as configurações de quiosque atuais, confira [Configurações de quiosque do Android](android-kiosk-settings.md).

### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Definir tela de fundo personalizada no aplicativo de Tela Inicial Gerenciada <!-- 3041945 -->
Vamos adicionar uma configuração que permite que você personalize a aparência da tela de fundo do aplicativo Tela Inicial Gerenciada em dispositivos Android Enterprise de vários aplicativos em modo de quiosque.  Para configurar a **tela de fundo da URL Personalizada**, vá para o Intune no portal do Azure > Configuração do dispositivo. Selecione um perfil de configuração do dispositivo atual ou crie um novo para editar suas configurações de quiosque.

### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Habilitar o botão de página inicial virtual em dispositivos de quiosque do Android Enterprise <!-- 3042021 -->
Uma nova configuração permitirá que os usuários toquem em um botão de tecla no dispositivo para alternar entre o aplicativo Tela Inicial Gerenciada e outros aplicativos atribuídos no dispositivo de quiosque de vários aplicativos. Essa configuração é particularmente útil em cenários em que o aplicativo de quiosque do usuário não responde adequadamente ao botão "Voltar". Você poderá definir essa configuração para dispositivos Android de uso único e corporativos. Para habilitar ou desabilitar o **botão de Página inicial virtual**, vá para o Intune no portal do Azure > Configuração do dispositivo. Selecione um perfil de configuração do dispositivo atual ou crie um novo para editar suas configurações de quiosque.

### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Salvar e aplicar atribuição de política de proteção de aplicativo <!-- 3104570 -->
Você terá um melhor controle sobre suas atribuições de política de proteção de aplicativo. Ao salvar e aplicar suas atribuições de política de proteção de aplicativo, somente os usuários desejados serão diretamente afetados por uma política de atribuição de proteção do aplicativo.

### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Novas configurações do navegador Microsoft Edge para Windows 10 e posterior <!-- 3174639 -->
Uma nova configuração será adicionada para ajudar a controlar e gerenciar o navegador Microsoft Edge em seus dispositivos. Para obter uma lista das configurações atuais, confira [Restrição de dispositivo para Windows 10 (e mais recentes)](device-restrictions-windows-10.md#microsoft-edge-browser).

### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Aplicativos selecionados acompanhados na Página de Status de Registro<!-- 2531007 -->
Você poderá escolher quais aplicativos são acompanhados na Página de Status de Registro.

### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Atualização da interface do usuário de políticas de proteção de aplicativo do Intune <!-- 3251427 -->

As políticas de Proteção de Aplicativo do Intune permitem que você defina várias configurações de proteção de dados para aplicativos protegidos do Intune, como Word e Microsoft Outlook. Estamos mudando os rótulos de configuração e botão para tornar cada um mais fácil de entender. Os controles mudarão de controles do tipo **sim**/**não** para principalmente controles dos tipos **bloquear**/**permitir** e **desabilitar**/**habilitar**, enquanto os rótulos também serão atualizados para maior clareza. As configurações também serão reformatadas, portanto, a configuração e seu rótulo estão lado a lado no controle, fornecendo uma navegação melhor. As configurações padrão e o número de configurações permanecerão iguais, mas essa alteração permitirá que o usuário entenda, navegue e utilize as configurações mais facilmente para aplicar as políticas de proteção do aplicativo selecionadas.



<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Usar configurações recomendadas pela Microsoft com linhas de base de segurança <!-- 2055484 -->
O Intune integra-se a outros serviços que têm foco na segurança, incluindo o Windows Defender ATP e o Office 365 ATP. Os clientes estão solicitando uma estratégia comum e um conjunto coeso de fluxos de trabalho de segurança de ponta a ponta entre os serviços do Microsoft 365. Nossa meta é alinhar estratégias para criar soluções que façam a ponte entre operações de segurança e tarefas comuns do administrador. No Intune, nosso objetivo é atingir essa meta publicando um conjunto de "Linhas de base de segurança" recomendadas pela Microsoft (**Intune** > **Linhas de base de segurança**).  Um administrador poderá criar políticas de segurança diretamente com base nessas linhas de base e implantá-las para seus usuários. Eles também poderão personalizar as recomendações de melhores práticas para atender às necessidades de sua organização. O Intune garante que os dispositivos estejam em conformidade com essas linhas de base e notifica os administradores de usuários ou dispositivos que não estão em conformidade.

### <a name="scope-tags-for-apps---1081941---"></a>Marcas de escopo para aplicativos <!--1081941 -->
Você poderá criar marcas de escopo para limitar o acesso aos recursos do Intune. Adicione uma marca de escopo a uma atribuição de função e, em seguida, adicione a marca de escopo a um perfil de configuração. A função só terá acesso a recursos com perfis de configuração que tenham marcas de escopo correspondentes (ou nenhuma marca de escopo).
Para criar uma marca de escopo, escolha **Funções do Intune** > **Escopo (Marcas)** > **Criar**.
Para adicionar uma marca de escopo a uma atribuição de função, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de Política e Perfil** > **Atribuições** > **Escopo (Marcas)**.
Para adicionar uma marca de escopo a um perfil de configuração, escolha **Configuração do dispositivo** > **Perfis** > escolha um perfil > **Propriedades** > **Escopo (Marcas)**.

### <a name="tenant-health-dashboard----1124854---"></a>Painel de Integridade do Locatário <!-- 1124854 -->
A página Status do Locatário no Intune fornecerá informações de status do locatário em um único lugar. A página está dividida em quatro seções:  
- **Detalhes do locatário**: contém informações, como sua Autoridade de MDM, o total de dispositivos registrados no seu locatário e contagens de suas licenças. Esta seção também fornece a versão de serviço atual do seu locatário.
- **Status do conector**: contém informações para conectores configurados, como o VPP da Apple, Windows Store para Empresas e conectores de certificado. Com base em seu estado atual, os conectores são sinalizados como *Íntegro*, *Aviso* ou *Não íntegro*.
- **Integridade do serviço do Intune**: contém incidentes interrupções ativos do seu locatário. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office ([https://portal.office.com](https://portal.office.com)).
- **Notícias sobre o Intune**: contém mensagens ativas para seu locatário, que inclui itens como notificações de que seu locatário recebeu os recursos mais recentes do Intune. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Políticas de WIP implantadas sem o registro do usuário <!-- 1434452 -->
Políticas de WIP (Proteção de Informações do Windows) poderão ser implantadas sem que os usuários do MDM registrem seu dispositivo Windows 10. Essa configuração permite que as empresas protejam seus documentos corporativos com base na configuração do WIP, enquanto permitem que o usuário mantenha o gerenciamento dos seus próprios dispositivos Windows. Depois que os documentos forem protegidos com uma política de WIP, os dados protegidos poderão ser apagados seletivamente por um administrador do Intune. Selecionando o usuário e o dispositivo, e enviando uma solicitação de apagamento, todos os dados protegidos por meio da política de WIP ficarão inutilizáveis. No Intune no portal do Azure, selecione **Aplicativo móvel** > **Apagamento seletivo do aplicativo**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações de APP (Política de Proteção de Aplicativo) do aplicativo para dados Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token de VPP da Apple usado por outro MDM <!-- 1488946 -->
O Intune detectará e mostrará detalhes se um token do VPP (Apple Volume Purchase Program) estiver sendo usado tanto pelo Intune quanto por outro MDM.

### <a name="ios-and-macos-version-numbers-and-build-numbers-are-available-in-compliance-policies----1892471---"></a>Os números de build e números de versão do iOS e do macOS estão disponíveis nas políticas de conformidade <!-- 1892471 -->
Em **Conformidade do dispositivo** > **Conformidade do dispositivo**, as versões do sistema operacional iOS e macOS são mostradas e estão disponíveis para uso em políticas de conformidade. Em uma atualização futura, o número de build também será configurável em ambas as plataformas.

Quando são lançadas atualizações de segurança, a Apple normalmente mantém o número de versão no estado em que se encontra, mas atualiza o número de build. Ao usar o número de build em uma política de conformidade, você pode verificar facilmente se uma atualização de vulnerabilidade está instalada.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Dispositivos desativados no painel de conformidade de dispositivos <!-- 1981119 -->
Em uma atualização futura, os dispositivos desativados serão removidos do painel de conformidade de dispositivos. Com isso, seus números de conformidade serão alterados.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Alteração no processo de atualização de conectores locais <!-- 2277554 -->
Com base nos comentários dos clientes, a maneira em que as atualizações são feitas nos conectores locais será alterada. Depois que você instalar um conector local inicialmente, as atualizações passarão a ocorrer automaticamente. Essa alteração começará com o novo conector de certificado PFX para Microsoft Intune e, posteriormente, será distribuída a outros tipos de conectores locais. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Conferir a conformidade do Configuration Manager <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O Configuration Manager envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token do VPP ou de licença do Portal da Empresa quase acabando <!-- 2237572 -->
Se você usar o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem quase acabando.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.



