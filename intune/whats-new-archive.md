---
title: O que há de novo m meses anteriores no Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Veja comunicados mais antigos da página de novidades do Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0cfcc64418c105e92187cb8eb229f955a7d58681
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850344"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Novidades do Microsoft Intune – meses anteriores

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="march-2018"></a>Março de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Alertas para a expiração de aplicativos de LOB (linha de negócios) do iOS para Microsoft Intune <!-- 748789 -->

No Portal do Azure, o Intune o alertará sobre aplicativos de linha de negócios iOS que estão prestes a expirar. Após carregar uma nova versão do aplicativo de linha de negócios iOS, o Intune remove a notificação de expiração da lista de aplicativos. Esta notificação de expiração somente ficará ativa para aplicativos de linha de negócios iOS recém-carregados. Um aviso aparecerá 30 dias antes da expiração do perfil de provisionamento de aplicativo do iOS LOB. Quando expirar, o alerta mudará para Expirado.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Personalize os temas do Portal da Empresa com códigos hexadecimais <!--1049561 -->

Você pode personalizar a cor do tema nos aplicativos do Portal da Empresa usando códigos hexadecimais. Ao inserir o código hexadecimal, o Intune determina a cor do texto que oferece o maior nível de contraste entre a cor do texto e a cor da tela de fundo. É possível visualizar a cor do texto e o logotipo da empresa em relação à cor em **Aplicativos clientes** > **Portal da Empresa**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos para Android Enterprise <!-- 1813081 -->

Android Enterprise (anteriormente conhecido como Android for Work) é compatível com a inclusão e a exclusão de grupos, mas não com grupos internos de **Todos os Usuários** e **Todos os Dispositivos** pré-criados. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Gerenciamento de dispositivos

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome----2258071---"></a>Exportar todos os dispositivos para arquivos CSV no IE, no Microsoft Edge ou no Chrome <!-- 2258071 -->
Em **Dispositivos** > **Todos os Dispositivos**, você pode **Exportar** os dispositivos para uma lista formatada em CSV. Os usuários do IE (Internet Explorer) com >10.000 dispositivos podem exportar com êxito seus dispositivos para vários arquivos. Cada arquivo tem até 10.000 dispositivos.

Os usuários do Microsoft Edge e do Chrome com > 30.000 dispositivos podem exportar com êxito seus dispositivos para vários arquivos. Cada arquivo tem até 30.000 dispositivos.

[Gerenciar dispositivos](device-management.md) fornece mais detalhes sobre o que você pode fazer com os dispositivos que gerencia.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Novos aprimoramentos de segurança no serviço do Intune <!-- 1637539 -->   

Apresentamos uma alternância do Intune no Azure que os clientes autônomos do Intune podem usar para tratar os dispositivos sem qualquer política atribuída como **Em conformidade** (recurso de segurança desligado) ou tratar esses dispositivos como **Não em conformidade** (recurso de segurança ligado). Isso garantirá acesso aos recursos somente após a avaliação de conformidade do dispositivo.

Esse recurso afeta você de maneira diferente dependendo se você já tem políticas de conformidade atribuídas ou não.

- Se você for uma conta nova ou existente e não tiver nenhuma política de conformidade atribuída aos seus dispositivos, a alternância será definida automaticamente como **Em conformidade**. O recurso está desligado como uma configuração padrão no console. Não há nenhum impacto ao usuário final.
- Se você for uma conta existente e tiver qualquer dispositivo com uma política de conformidade atribuída, a alternância será definida automaticamente como **Não em conformidade**. O recurso está ligado como uma configuração padrão conforme a atualização de março é implantada.

Se você usar políticas de conformidade com CA (Acesso Condicional) e o recurso estiver ativado, os dispositivos que não tiverem pelo menos uma política de conformidade atribuída agora serão bloqueados pelo CA. Os usuários finais associados a esses dispositivos, que anteriormente tinham permissão de acesso ao email, perderão o acesso, a menos que você atribua pelo menos uma política de conformidade a todos os dispositivos.   

Observe que, embora o status de alternância padrão seja exibido na interface do usuário imediatamente com as atualizações do serviço do Intune feitas em março, esse status de alternância não é imposto imediatamente. Alterações feitas à alternância não terá impacto sobre a conformidade do dispositivo até habilitarmos sua conta para ter uma alternância operando. Você será informado por meio do Centro de Mensagens quando terminamos de habilitar sua conta. Isso pode levar alguns dias depois que o serviço do Intune for atualizado para março.

**Informações adicionais**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Detecção de jailbreak avançada <!-- 846515 -->

A detecção de jailbreak avançada é uma nova configuração de conformidade que melhora a maneira como o Intune avalia os dispositivos desbloqueados por jailbreak. A configuração faz com que o dispositivo faça check-in no Intune com mais frequência, o que utiliza os serviços de localização do dispositivo e afeta o uso da bateria.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Redefina senhas de dispositivos Android O <!-- 1238299 -->
Você poderá redefinir senhas para dispositivos com Android 8.0 registrados com perfis de Trabalho. Quando você envia uma solicitação de "Redefinir senha" a um dispositivo Android 8.0, ele define uma nova senha de desbloqueio de dispositivo ou um desafio de perfil gerenciado para o usuário atual. A senha ou o desafio é enviado e entra em vigor imediatamente.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Direcionamento de políticas de conformidade para dispositivos em grupos de dispositivo <!--1307012 -->

Você pode direcionar políticas de conformidade para usuários em grupos de usuários. Com essa atualização, você pode direcionar políticas de conformidade para dispositivos em grupos de dispositivo. Dispositivos de destino como parte de grupos de dispositivos não receberão as ações de conformidade.

#### <a name="new-management-name-column----1333586---"></a>Coluna Novo nome de gerenciamento <!-- 1333586 -->
 Uma nova coluna chamada **Nome de gerenciamento** está disponível na folha de dispositivos. Este é um nome não editável gerado automaticamente atribuído por dispositivo, com base na seguinte fórmula:
- Nome padrão para todos os dispositivos: <username><em><devicetype></em><enrollmenttimestamp>
- Para dispositivos adicionados em massa: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Esta é uma coluna opcional na folha de dispositivos. Ele não está disponível por padrão e você poderá acessá-lo apenas por meio do seletor de colunas. O nome do dispositivo não é afetado por essa nova coluna.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Os dispositivos iOS solicitam um PIN a cada 15 minutos <!--1550837 -->
Depois que uma política de conformidade ou de configuração for aplicada a um dispositivo iOS, os usuários serão solicitados a definir um PIN a cada 15 minutos. Os usuários são notificados continuamente até que um PIN seja definido.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Agendar suas atualizações automáticas <!--1805514 -->
Com o Intune, você controla como instalar atualizações automáticas usando as [configurações do Grupo de Atualização do Windows](windows-update-for-business-configure.md). Com essa atualização, você pode agendar atualizações recorrentes, incluindo semana, dia e hora.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Use o nome totalmente diferenciado como assunto para o certificado SCEP <!--2221763 -->
Quando você cria um perfil de certificado SCEP, você inserir o Nome do assunto. Com essa atualização, você pode usar o nome totalmente diferenciado como a entidade. Para **Nome do assunto**, selecione **Personalizado** e, em seguida, digite `CN={{OnPrem_Distinguished_Name}}`. Para usar a variável `{{OnPrem_Distinguished_Name}}`, sincronize o atributo de usuário `onpremisesdistingishedname` usando o [Azure AD (Active Directory) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) com seu Azure AD.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Habilitar compartilhamento de contatos por Bluetooth – Android for Work <!--1098983 -->
Por padrão, o Android impede que contatos no perfil de trabalho sejam sincronizados com dispositivos Bluetooth. Como resultado, os contatos do perfil de trabalho não são exibidos nas informações sobre a chamada para dispositivos Bluetooth.

Com essa atualização, há uma nova configuração em **Android for Work** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
- Compartilhamento de contatos por Bluetooth

O administrador do Intune pode configurar essas configurações para habilitar o compartilhamento. Isso é útil ao emparelhar um dispositivo com um dispositivo Bluetooth baseado em carro que exibe as informações sobre a chamada para uso não assistido. Quando habilitados, os contatos de perfil de trabalho são exibidos. Quando não habilitados, os contatos de perfil de trabalho não serão exibidos.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Configurar o Gatekeeper para controlar a origem do download do aplicativo macOS <!-- 1690459 -->

Você pode configurar o Gatekeeper para proteger os dispositivos de aplicativos, controlando de que local os aplicativos podem ser baixados. Você pode configurar as seguintes fontes de download: **Mac App Store**, **Mac App Store e desenvolvedores identificados** ou **Qualquer lugar**. Você também pode configurar se os usuários podem instalar um aplicativo usando CTRL + clique para substituir esses controles do Gatekeeper.

Essas configurações podem ser encontradas em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Configurar o firewall do aplicativo Mac <!-- 1690461 -->

Você pode configurar o firewall do aplicativo Mac. Você pode usar isso para controlar as conexões por aplicativo, em vez de por porta. Isso facilita obter os benefícios da proteção de firewall e ajuda a impedir que aplicativos indesejáveis assumam o controle de portas de rede abertas para aplicativos legítimos.

Esse recurso pode ser encontrado em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

Depois de habilitar a configuração de Firewall, você pode configurar o firewall usando duas estratégias:

- Bloquear todas as conexões de entrada

   É possível bloquear todas as conexões de entrada para os dispositivos de destino. Se você optar por fazer isso, as conexões de entrada serão bloqueadas para todos os aplicativos.

- Permitir ou bloquear aplicativos específicos

   Você pode permitir ou bloquear que aplicativos específicos recebam conexões de entrada. Você também pode habilitar o modo furtivo para impedir respostas para as solicitações de sondagem.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Códigos de erro e mensagens detalhados <!-- 1376342 -->

Em Configuração do Dispositivo, há mensagens e códigos de erro mais detalhados disponíveis para visualização. Esse relatório aprimorado mostra as configurações, o estado dessas configurações e os detalhes sobre como solucionar problemas.

##### <a name="more-information"></a>Mais informações

- Bloquear todas as conexões de entrada

   Isso impede que todos os serviços de compartilhamento (como Compartilhamento de arquivos e Compartilhamento de tela) recebam conexões de entrada. Os serviços do sistema que ainda têm permissão para receber conexões de entrada são:
  - configd – implementa DHCP e outros serviços de configuração de rede
  - mDNSResponder – implementa o Bonjour
  - racoon – implementa IPsec

    Para usar os serviços de compartilhamento, verifique se **Conexões de entrada** está definido como **Não configurado** (não **Bloqueado**).

- Modo furtivo

   Habilite esta opção para impedir que o computador responda às solicitações de sondagem. O computador ainda responde a solicitações de entrada para aplicativos autorizados. Solicitações inesperadas, como o ICMP (ping), são ignoradas.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Desabilitar verificações na reinicialização do dispositivo <!--1805490 -->
Com o Intune, você tem controle para [gerenciar atualizações de software](windows-update-for-business-configure.md). Com essa atualização, a propriedade <strong>Reiniciar verificações</strong> está disponível e habilitada por padrão. Para ignorar as verificações típicas que ocorrem quando você reinicia um dispositivo (como usuários ativos, níveis de bateria e assim por diante), selecione <strong>Ignorar</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Novos canais do Windows 10 Insider Preview disponíveis para anéis de implantação <!-- 1746293 -->
Agora você tem a opção de selecionar os seguintes canais de serviço do Windows 10 Insider Preview ao criar um anel de implantação do Windows 10:
- Build do Windows Insider &#8208; rápido
- Build do Windows Insider &#8208; lento
- Liberar build do Windows Insider 

Para obter mais informações sobre esses canais, consulte [Gerenciar builds do Insider Preview](https://insider.windows.com/for-business-organization-admin/).   
Para obter mais informações sobre como criar canais de implantação no Intune, consulte [Gerenciar atualizações de software no Intune](windows-update-for-business-configure.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Novas configurações do Windows Defender Exploit Guard <!-- 1631893 -->

Seis novas configurações de <strong>Redução da Superfície de Ataque</strong> e funcionalidades expandidas de <strong>Acesso controlado a pastas: Agora, os recursos de proteção de pasta</strong> estão disponíveis. Essas configurações podem ser encontradas em: Configuração do dispositivo\Perfis\
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

|              Nome da configuração               |                                                              Opções de configuração                                                              | Descrição |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Proteção de pasta (já implementada) | Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> <strong>Novo</strong><br>Bloquear modificação de disco, Auditar modificação de disco |             |

Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: Impeça que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

### <a name="intune-apps"></a>Aplicativos do Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o aplicativo Intune Managed Browser e dar suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->

Usando o Azure AD (Azure Active Directory), agora você pode restringir o acesso a sites em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure. Para obter mais informações, consulte [Controles de acesso no acesso condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aplicativo Portal da empresa para atualizações visuais do Android <!--976944 -->

Atualizamos o aplicativo Portal da Empresa para Android para seguir as diretrizes do [Design de Material](https://material.io/) do Android. É possível ver as imagens dos novos ícones no artigo [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Registro do Portal da Empresa melhorado <!-- 1874230 eeready-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior agora podem concluir a primeira etapa de registro sem sair do aplicativo.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>Agora o HoloLens e o Surface Hub são exibidos nas listas de dispositivos <!--1725868 -->
Adicionamos suporte para mostrar dispositivos HoloLens e Surface Hub registrados no Intune no aplicativo Portal da Empresa para Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Categorias personalizadas de livros para livros eletrônicos do VPP (Volume Purchase Program) <!-- 1488911 -->
Você pode criar categorias de livros eletrônicos personalizadas e atribuir livros eletrônicos do VPP a essas categorias personalizadas. Os usuários finais poderão ver as categorias de livro eletrônico recém-criadas e os livros atribuídos às categorias. Para obter mais informações, consulte [Gerenciar aplicativos e livros comprados por volume com o Microsoft Intune](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Mudanças de suporte para a opção de comentários do aplicativo Portal da Empresa para Windows <!-- 2070166 -->
A partir de 30 de abril de 2018, a opção **Enviar Comentários** no aplicativo Portal da Empresa para Windows funcionará apenas em dispositivos que executam a Atualização de Aniversário do Windows 10 (1607) e posterior. Não há mais suporte para a opção de enviar comentários ao usar o aplicativo Portal da Empresa para Windows com:  
- Windows 10, versão 1507  
- Windows 10, versão 1511  
- Windows Phone 8.1 

Se o seu dispositivo estiver executando no Windows 10 RS1 ou posterior, baixe a versão mais recente do aplicativo Portal da Empresa do Windows na Store. Se você estiver executando uma versão sem suporte, continue a enviar comentários por meio destes canais: 
- Aplicativo Hub de Comentários no Windows 10
- Email WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Novas configurações do Windows Defender Application Guard <!-- 1631890 -->

- **Habilitar aceleração de elementos gráficos**: Os administradores podem habilitar um processador de gráficos virtual para o Windows Defender Application Guard. Essa configuração permite que a CPU descarregue a renderização de gráficos no vGPU. Isso pode melhorar o desempenho ao trabalhar com sites com uso intenso de gráficos ou ao assistir a vídeos dentro do contêiner.

- **SaveFilestoHost**: Os administradores podem permitir que arquivos sejam passados do Microsoft Edge em execução no contêiner para o sistema de arquivos do host. Ativar essa configuração permite que os usuários baixem arquivos do Microsoft Edge no contêiner para o sistema de arquivos do host.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Políticas de proteção MAM definidas como destino com base no estado de gerenciamento <!-- 1665993 -->
Você pode ter como destino políticas de MAM com base no estado de gerenciamento do dispositivo:
- **Dispositivos Android** – você poderá ter como destino dispositivos não gerenciados, dispositivos gerenciados pelo Intune e Perfis do Android Enterprise gerenciados pelo Intune (anteriormente Android for Work).
- **Dispositivos iOS** – você poderá ter como destino dispositivos não gerenciados (somente MAM) ou dispositivos gerenciados pelo Intune.

    > [!NOTE]
    > - O suporte do iOS para essa funcionalidade será implantado em abril de 2018.

Para obter mais informações, consulte [Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Melhorias à linguagem no aplicativo Portal da Empresa para Windows <!-- 1683758 -->
Melhoramos a linguagem no Portal da Empresa para Windows 10 para ser mais amigável e específica para sua empresa. Para ver algumas amostras de imagens do que já fizemos, consulte [novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Novas adições aos nossos documentos sobre privacidade do usuário <!-- 1440709 -->
Como parte dos nossos esforços para dar aos usuários finais mais controle sobre seus dados e privacidade, publicamos as atualizações aos documentos que explicam como exibir e remover dados armazenados localmente usando os aplicativos do Portal da Empresa. Você pode encontrar essas atualizações no:

- **Android**: [Como remover seu dispositivo Android do Intune](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, se o usuário tiver recusado os termos de uso**: [Remover o gerenciamento do seu dispositivo se você tiver recusado os "Termos de uso"](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [Remover seu dispositivo iOS do Intune](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [Remover seu dispositivo Windows do Intune](/intune-user-help/unenroll-your-device-from-intune-windows)

## <a name="february-2018"></a>Fevereiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 -->

Agora o Intune é compatível com o registro de dispositivos de até 100 contas diferentes do [DEP (Programa de registro de dispositivos) da Apple](device-enrollment-program-enroll-ios.md) ou do [Apple School Manager](apple-school-manager-set-up-ios.md). Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Consultar as restrições de registro por usuário <!-- 1634444 eeready wnready -->
Agora, na folha **Solucionar Problemas**, é possível ver as [restrições de registro](enrollment-restrictions-set.md) que estão em vigor para cada usuário ao selecionar **Restrições de registro** na lista **Atribuições**.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nova opção de autenticação de usuário para registro em massa da Apple <!-- 747625 eeready -->

> [!NOTE]
> Os novos locatários veem essa opção imediatamente. Para locatários existentes, esse recurso será distribuído durante o mês de abril. Até essa implantação estar concluída, talvez você não tenha acesso aos novos recursos.

Agora o Intune oferece a opção para autenticar dispositivos usando o aplicativo Portal da Empresa para os seguintes métodos de registro:

- Programa de Registro do Dispositivo da Apple
- Apple School Manager
- Registro do Apple Configurator

Com a opção do Portal da Empresa, a autenticação multifator do Azure Active Directory pode ser imposta sem bloquear esses métodos de registro.

Com a opção do Portal da Empresa, o Intune ignora a autenticação do usuário no Assistente de Configuração do iOS para registro de afinidade de usuário. Isso significa que o dispositivo é registrado inicialmente como um dispositivo sem usuário e, portanto, não recebe as configurações ou políticas de grupos de usuários. Ele recebe apenas as configurações e políticas de grupos de dispositivos. No entanto, o Intune instalará automaticamente o aplicativo do Portal da Empresa no dispositivo. O primeiro usuário a iniciar e entrar no aplicativo do Portal da Empresa será associado ao dispositivo no Intune. Nesse momento, o usuário receberá as configurações e políticas de seus grupos de usuários. A associação do usuário não pode ser alterada sem um novo registro.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 eeready -->

Agora o Intune é compatível com o registro de dispositivos de até 100 contas diferentes do DEP (Programa de registro de dispositivos) da Apple ou do Apple School Manager. Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impressão remota em uma rede segura <!-- 1709994  -->
As soluções de impressão móvel sem fio do PrinterOn permitirão aos usuários imprimir remotamente de qualquer lugar, e a qualquer momento, em uma rede segura. O PrinterOn será integrado ao SDK do Aplicativo do Intune para iOS e Android. Você poderá direcionar políticas de proteção de aplicativo para esse aplicativo por meio da folha **Políticas de proteção do aplicativo** do Intune no console do administrador. Os usuários finais poderão baixar o aplicativo "PrinterOn para Microsoft" através da Play Store ou iTunes para uso no ecossistema do Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Suporte do Portal da Empresa para macOS para registros que usam o Gerenciador de Registros do Dispositivo <!-- 1352411 -->

Agora os usuários podem fazer registro no Portal da Empresa para macOS usando o Gerenciador de Registros do Dispositivo.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Relatórios de status de ameaça e status da integridade do Windows Defender <!--854704 -->

Compreender o status da integridade e das ameaças do Windows Defender é essencial para gerenciar computadores Windows.  Com essa atualização, o Intune adiciona novos relatórios e ações ao status e à integridade do agente do Windows Defender. Usando um relatório de acúmulo de status na [carga de trabalho de Conformidade do Dispositivo](compliance-policy-monitor.md), você pode ver os dispositivos que precisam do seguinte:
- atualização de assinatura
- Reiniciar
- intervenção manual
- verificação completa
- outros estados de agente que requerem intervenção

Um relatório de análise para cada categoria de status lista os computadores individuais que precisam de atenção ou aqueles cujo estado relatado é **Limpo**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Novas configurações de privacidade para restrições de dispositivo <!--1308926 -->
Agora [duas novas configurações de privacidade](device-restrictions-windows-10.md#privacy) estão disponíveis para dispositivos:
- **Publicar atividades do usuário**: Defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas.
- **Apenas atividades locais**: Defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais.

#### <a name="new-settings-for-the-microsoft-edge-browser---1469166---"></a>Novas configurações para o navegador Microsoft Edge <!--1469166 -->
Agora, há [duas novas configurações](device-restrictions-windows-10.md#microsoft-edge-browser) disponíveis para dispositivos com o navegador Microsoft Edge: **Caminho para o arquivo de favoritos** e **Alterações aos Favoritos**.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="protocol-exceptions-for-applications---1035509---"></a>Exceções de protocolo para aplicativos <!--1035509 -->

Agora você pode criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune para abrir aplicativos não gerenciados específicos. Esses aplicativos devem ser confiáveis para a TI. Exceto pelas exceções que você cria, a transferência de dados ainda fica restrita a aplicativos gerenciados pelo Intune quando sua política de transferência de dados estiver definida como **somente aplicativos gerenciados**. É possível criar as restrições usando protocolos (iOS) ou pacotes (Android).

Por exemplo, é possível adicionar o pacote do Webex como uma exceção à política de transferência de dados de MAM. Isso permitirá que links do Webex em uma mensagem de email gerenciada do Outlook sejam abertos diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados. Para obter mais informações, consulte [Exceções à política transferência de dados para aplicativos](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dados criptografados de WIP (Proteção de Informações do Windows) nos resultados da pesquisa do Windows <!-- 1469193 -->
Uma configuração na política de WIP (Proteção de Informações do Windows) agora permite que você controle se os dados criptografados por WIP são incluídos nos resultados da pesquisa do Windows. Defina essa opção da política de proteção de aplicativo por meio da seleção de **Permitir que o indexador do Windows Search pesquise itens criptografados** nas **Configurações avançadas** da política de Proteção de Informações do Windows. A política de proteção do aplicativo deve ser definida para a plataforma *Windows 10* e a política de aplicativo **Estado do registro** deve ser definida como **Com registro**. Para obter mais informações, consulte [Permitir que o indexador do Windows Search pesquise itens criptografados](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Configurando um aplicativo móvel do MSI com autoatualização <!-- 1740840 -->
Você pode configurar um aplicativo móvel do MSI com atualização automática conhecido para ignorar o processo de verificação de versão. Essa funcionalidade é útil para evitar entrar em uma condição de corrida. Por exemplo, esse tipo de condição de corrida poderá ocorrer se o aplicativo que está sendo automaticamente atualizado pelo desenvolvedor também for atualizado pelo Intune. As duas atualizações podem tentar impor uma versão do aplicativo em um cliente do Windows, o que poderia criar um conflito. Para esses aplicativos do MSI atualizados automaticamente, você pode configurar a opção **Ignorar a versão do aplicativo** na folha **Informações do aplicativo**. Quando essa configuração é definida como **Sim**, Microsoft Intune ignora a versão do aplicativo instalada no cliente do Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Conjuntos relacionados de licenças de aplicativo compatíveis com o Intune <!-- 1864117 -->
Agora o Intune no Portal do Azure é compatível com conjuntos relacionados de licenças de aplicativo como um único item de aplicativo na interface do usuário. Além disso, qualquer aplicativo licenciado offline sincronizado da Microsoft Store para Empresas será consolidado em uma única entrada de aplicativo e qualquer detalhe de implantação dos pacotes individuais será migrado para essa única entrada. Para exibir conjuntos de licenças de aplicativo relacionados no portal do Azure, selecione **Licenças de aplicativo** na folha **Aplicativos clientes**.

### <a name="device-configuration"></a>Configuração do dispositivo
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Extensões de arquivo da WIP (Proteção de Informações do Windows) para criptografia automática <!-- 1463582 -->
Uma configuração na política da WIP (Proteção de Informações do Windows) agora permite que você especifique quais extensões de arquivo são criptografadas automaticamente ao copiar de um compartilhamento de SMB (protocolo SMB) dentro do limite corporativo, como definido na política da WIP.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Definir as configurações de conta do recurso para Surface Hubs

Você já pode definir remotamente configurações de conta do recurso para Surface Hubs.

A conta do recurso é usada por um Surface Hub para autenticar no Skype/Exchange a fim de ingressar em uma reunião.
Você poderá criar uma conta do recurso exclusiva para que o Surface Hub possa aparecer na reunião como aparece na sala de conferência.
Por exemplo, uma conta do recurso como **Sala de conferência B41/6233**.

> [!NOTE]
> - Se deixar os campos em branco, você substituirá os atributos configurados anteriormente no dispositivo.
>
> - As propriedades de conta do recurso podem ser alteradas dinamicamente no Surface Hub. Por exemplo, se a rotação de senha estiver ativada. Portanto, é possível que os valores no console do Azure levem algum tempo para refletir a realidade do dispositivo.
>
>   Para entender o que está configurado atualmente no Surface Hub, os dados da conta do recurso podem ser incluídas no inventário de hardware (que já tem um intervalo de sete dias) ou como propriedades somente leitura. Para aumentar a precisão após a ação remota ter ocorrido, você pode obter o estado dos parâmetros imediatamente após a execução da ação para atualizar a conta/parâmetros no Surface Hub.

##### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Execução de conteúdo executável protegido por senha no email|Bloquear, Auditoria, Não configurado|Impedir que arquivos executáveis protegidos por senha baixados por email sejam executados.|
|Proteção avançada contra ransomware|Habilitado, Auditoria, Não configurado|Usar proteção agressiva contra ransomware.|
|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows|Habilitado, Auditoria, Não configurado|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows (lsass.exe).|
|Criação de processo de comandos WMI e PSExec|Bloquear, Auditoria, Não configurado|Bloquear criações de processo provenientes de comandos PSExec e WMI.|
|Processos não assinados e não confiáveis executados de um USB|Bloquear, Auditoria, Não configurado|Bloquear processos não assinados e não confiáveis executados de um USB.|
|Arquivos executáveis que não atendem um critério de prevalência, idade ou lista confiável|Bloquear, Auditoria, Não configurado|Bloquear a execução de arquivos executáveis a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.|

##### <a name="controlled-folder-access"></a>Acesso controlado à pasta

|              Nome da configuração               |                                                              Opções de configuração                                                              | Descrição |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Proteção de pasta (já implementada) | Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> <strong>Novo</strong><br>Bloquear modificação de disco, Auditar modificação de disco |             |

Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: Impeça que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Acréscimos às configurações de Segurança do sistema para políticas de conformidade do Windows 10 e posteriores <!--1704133-->

Acréscimos às configurações de conformidade do Windows 10 já estão disponíveis, incluindo a necessidade de um Firewall e do Windows Defender Antivírus.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Suporte para aplicativos offline da Microsoft Store para Empresas <!--1222672-->
Aplicativos offline comprados na Microsoft Store para Empresas agora estão sincronizados com o Portal do Azure. Você pode implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Impedir que os usuários finais adicionem ou removam contas manualmente no perfil de trabalho <!-- 1728700 -->

Agora, ao implantar o aplicativo Gmail em um perfil Android for Work, você pode impedir que usuários finais adicionem ou removam contas manualmente no perfil de trabalho, usando a configuração **Adicionar e remover contas** no perfil de restrições de dispositivo do Android for Work.


## <a name="january-2018"></a>Janeiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertas para tokens expirados e tokens que expirarão em breve<!-- 1639263 -->
A página de visão geral agora mostra alertas para tokens expirados e tokens que expirarão em breve. Ao clicar em um alerta de um único token, você será levado até a página de detalhes do token.  Se você clicar no alerta com vários tokens, será levado até uma lista com todos os tokens e seu status. Os administradores devem renovar seus tokens antes da data de expiração.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Suporte ao comando "Erase" remoto para dispositivos macOS <!-- 1438084 -->

Os administradores podem emitir um comando Erase remotamente para dispositivos macOS.

> [!IMPORTANT]
> O comando erase não pode ser revertido e deve ser usado com cuidado.

O comando erase remove todos os dados, incluindo o sistema operacional, de um dispositivo. Também remove o dispositivo do gerenciamento do Intune. Nenhum aviso é emitido para o usuário, e a remoção ocorre imediatamente após a emissão do comando.

Você deve configurar um PIN de recuperação de seis dígitos. Este PIN pode ser usado para desbloquear o dispositivo apagado e, nesse momento, a reinstalação do sistema operacional começará. Após o início da remoção, o PIN aparecerá em uma barra de status na folha de visão geral do dispositivo no Intune. O PIN permanecerá enquanto a remoção estiver em andamento. Após a conclusão da remoção, o dispositivo desaparecerá totalmente do gerenciamento do Intune. Anote o PIN de recuperação para que a pessoa que estiver restaurando o dispositivo possa usá-lo.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Revogar licenças para um token de Programa de Compra por Volume do iOS<!-- 820870 -->
Você pode revogar a licença de todos os aplicativos do VPP (Apple Volume Purchase Program) do iOS para um determinado Token de VPP.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Revogação de aplicativos do Programa de Compra por Volume do iOS <!-- 820863 -->
Para um determinado dispositivo que tem um ou mais aplicativos do VPP (Apple Volume Purchase Program) do iOS, você pode revogar a licença do aplicativo com base no dispositivo associada ao dispositivo. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. Para saber mais, confira [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **Interno** facilita a criação e atribuição de aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos <!-- 1406920 -->

Durante a atribuição de aplicativo e após a seleção de um tipo de atribuição, você pode selecionar os grupos a serem incluídos e os grupos a serem excluídos.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Você pode atribuir uma política de configuração de aplicativo para grupos por meio da inclusão e exclusão de atribuições <!-- 1480316 -->

Você pode atribuir uma política de configuração de aplicativo a um grupo de usuários e dispositivos usando uma combinação de atribuições de inclusão e exclusão. As atribuições de podem ser escolhidas como uma seleção personalizada de grupos ou como um grupo virtual. Um grupo virtual pode incluir **Todos os usuários**, **Todos os dispositivos** ou **Todos os Usuários + Todos os Dispositivos**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672(archived), 1119689 -->  
Você pode criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>As Políticas de Acesso Condicional para o Intune só estão disponíveis no Portal do Azure <!-- 1737088 1634311 -->

Começando por esta versão, você deve configurar e gerenciar suas políticas de Acesso Condicional no [Portal do Azure](https://portal.azure.com), em **Azure Active Directory** > **Acesso Condicional** . Para sua conveniência, você também pode acessar essa folha do Intune no portal do Azure em **Intune** > **Acesso Condicional**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Atualizações nos emails de conformidade <!--1637547 -->

Quando um email é enviado para informar sobre um dispositivo não compatível, os detalhes sobre esse dispositivo são incluídos.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nova funcionalidade para a ação "Resolver" para dispositivos Android <!--1583480-->

O aplicativo Portal da Empresa para Android está expandindo a ação "Resolver" para **Atualizar configurações do dispositivo** a fim de resolver [problemas de criptografia de dispositivo](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Bloqueio remoto disponível no aplicativo de Portal da Empresa para Windows 10 <!--676506-->
Agora, os usuários finais podem bloquear remotamente seus dispositivos do aplicativo do Portal da Empresa para Windows 10. Isso não será exibido para o dispositivo local que ele estiver usando ativamente.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Resolução facilitada de problemas de conformidade para o aplicativo do Portal da Empresa para Windows 10 <!--676546-->
Os usuários finais com dispositivos Windows poderão tocar no motivo da não conformidade no aplicativo Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema.

## <a name="december-2017"></a>Dezembro de 2017

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nova configuração automática de reimplantação <!-- 1469168 -->
Essa configuração de **Reimplantação automática** permite que usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **Ctrl+Win+R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento. Essa configuração pode ser encontrada em Windows 10 > Restrições de dispositivo > Geral > Reimplantação automática. Para obter mais detalhes, confira [Configurações de restrição de dispositivo do Intune para Windows 10](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Suporte para as edições de origem adicionais na política de atualização de edição do Windows 10 <!-- 903672,  1119689 -->
Agora você pode usar a política de atualização de edição do Windows 10 para atualizar de edições adicionais do Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud etc.). Antes desta versão, os caminhos de atualização de edição com suporte eram mais limitados. Para obter detalhes, confira [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Novas definições do perfil de configuração de dispositivo da WDSC (Central de Segurança do Windows Defender) <!-- 1335507 -->

O Intune adiciona uma nova seção de configurações de perfil de configuração de dispositivo sob a Proteção de ponto de extremidade chamada **Central de Segurança do Windows Defender**. Os administradores de TI podem configurar quais pilares do aplicativo Central de Segurança do Windows Defender os usuários finais podem acessar. Se um administrador de TI ocultar um pilar no aplicativo Central de Segurança do Windows Defender, todas as notificações relacionadas ao pilar oculto não serão exibidas no dispositivo do usuário.

Estes são os pilares que os administradores podem ocultar nas configurações do perfil de configuração de dispositivo da Central de Segurança do Windows Defender:
- Proteção contra vírus e ameaças
- Desempenho e integridade do dispositivo
- Proteções de firewall e rede
- Controle de aplicativo e navegador
- Opções da família

Os administradores de TI também podem personalizar quais notificações os usuários recebem. Por exemplo, você pode configurar se os usuários recebem todas as notificações geradas por pilares visíveis na WDSC, ou apenas as notificações críticas. As notificações não críticas incluem resumos periódicos de atividades do Windows Defender Antivírus e notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas. Além disso, você também pode personalizar o conteúdo da própria notificação, por exemplo, você pode fornecer informações de contato da TI para incorporar as notificações que aparecem nos dispositivos dos usuários.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Suporte a vários conectores para manipulação de certificado SCEP e PFX <!-- 1361755 -->

Agora, os clientes que usam o conector NDES local para fornecer certificados para dispositivos podem configurar vários conectores em um único locatário.

Essa nova capacidade dá suporte ao seguinte cenário:

- **Alta disponibilidade**

Cada conector NDES efetua o pull de solicitações de certificado do Intune.  Se um conector NDES ficar offline, o outro conector poderá continuar processando solicitações.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Nome da entidade do cliente pode usar a variável AAD_DEVICE_ID <!-- 1468599 -->

Agora, ao criar um perfil de certificado SCEP no Intune, você pode usar a variável AAD_DEVICE_ID ao compilar o nome de entidade personalizado.   Quando o certificado é solicitado usando esse perfil SCEP, a variável é substituída pela ID do dispositivo AAD do dispositivo que está fazendo a solicitação de certificado.


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Gerenciar dispositivos macOS inscritos em Jamf com o mecanismo de conformidade do dispositivo do Intune <!-- 1592747 -->
Agora, você pode usar Jamf para enviar informações de estado do dispositivo macOS ao Intune, que, em seguida, avaliará a conformidade com as políticas definidas no console do Intune. Com base no estado de conformidade do dispositivo, bem como em outras condições (como local, risco de usuário etc.), o acesso condicional imporá a conformidade para dispositivos macOS que estão acessando aplicativos de nuvem e locais conectados com o Azure AD, incluindo o Office 365. Saiba mais sobre [como configurar a integração com Jamf](conditional-access-integrate-jamf.md) e [impor a conformidade para dispositivos gerenciados por Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nova ação do dispositivo iOS <!-- 1424701 -->

Agora, você pode desligar os dispositivos supervisionados com o iOS 10.3. Essa ação desliga o dispositivo imediatamente sem avisar o usuário final. A ação **Desligar (somente supervisionado)** pode ser encontrada nas propriedades do dispositivo quando você seleciona um dispositivo na carga de trabalho **Dispositivo**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Não permitir alterações de data/hora para dispositivos Samsung Knox<!-- 1468103 -->

Adicionamos um novo recurso que permite o bloqueio de alterações de data e hora em dispositivos Samsung Knox. Encontre isso nos **Perfis de configuração do dispositivo** > **Restrições de dispositivo (Android)** > **Geral**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Conta de recurso do Surface Hub com suporte <!-- 1566442  -->

Uma nova ação de dispositivo foi adicionada para que os administradores possam definir e atualizar a conta do recurso associada a um Surface Hub.

A conta do recurso é usada por um Surface Hub para autenticar com o Skype/Exchange a fim de ingressar em uma reunião. Você pode criar uma conta de recurso exclusiva para que o Surface Hub apareça na reunião como aparece na sala de conferência. Por exemplo, a conta do recurso pode aparecer como *Sala de conferência B41/6233*. A conta do recurso (conhecida como conta de dispositivo) para o Surface Hub normalmente precisa ser configurada para o local da sala de conferência, e quando outros parâmetros de conta de recurso precisam ser alterados.

Quando os administradores querem atualizar a conta do recurso em um dispositivo, eles devem fornecer as credenciais atuais do Active Directory/Azure Active Directory associadas ao dispositivo. Se a rotação de senha estiver ativada para o dispositivo, os administradores deverão acessar o Azure Active Directory para localizar a senha.

> [!NOTE]
> Todos os campos são enviados em um pacote, e substituem todos os campos que foram previamente configurados. Os campos vazios também são substituídos pelos campos existentes.

Veja a seguir as configurações que os administradores podem definir:

- **Conta de recurso**
   - **Usuário do Active Directory**

      Nomededomínio\nomedeusuário ou Nome UPN (UPN): user@domainname.com

   - **Senha**

- **Parâmetros opcionais da conta de recurso** (devem ser definidos usando a conta de recurso especificada)

   - **Período de rotação de senha**

     Certifique-se de que a senha da conta seja atualizada automaticamente pelo Surface Hub toda semana por motivos de segurança. Para configurar os parâmetros após essa habilitação, a conta no Azure Active Directory deve ter a senha redefinida primeiro.

   - **Endereço SIP (protocolo de iniciação de sessão)**

     Usado somente quando a descoberta automática falha.

   - **Email**

     Endereço de email da conta de recurso/do dispositivo.

   - **Exchange Server**

     Exigido somente quando a descoberta automática falha.

   - **Sincronização do calendário**

     Especifica se a sincronização de calendário, e outros serviços de servidor do Exchange, está habilitada. Por exemplo: sincronização de reunião.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalar aplicativos do Office em dispositivos macOS <!-- 1494311 -->
Agora, você pode instalar aplicativos do Office em dispositivos macOS. Esse novo tipo de aplicativo permitirá que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Esses aplicativos também são fornecidos com o MAU (Microsoft AutoUpdate), para ajudar a manter seus aplicativos seguros e atualizados.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Excluir um token de Programa de Compra por Volume do iOS <!-- 820879 -->
Você pode excluir o token do VPP (Programa de Compra por Volume) do iOS usando o console. Isso pode ser necessário quando houver instâncias duplicadas de um token VPP.

### <a name="intune-apps"></a>Aplicativos do Intune


### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Uma nova coleção de entidade chamada Usuário Atual é limitada a usuários ativos no momento <!-- 1667026 -->

A coleção de entidades **Usuários** contém todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

Em contraste, a nova coleção de entidade **Usuário Atual** contém apenas os usuários que não foram removidos. A coleção de entidade **Usuário Atual** contém apenas usuários ativos no momento. Para saber mais sobre a coleção de entidade **usuário atual**, veja [Referência para a entidade de usuário atual](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>APIs do Graph atualizadas <!-- 1736360 -->

Nesta versão, atualizamos algumas das APIs do Graph para Intune que estão na versão beta. Confira o [log de alterações mensal da API do Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) para saber mais.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>O Intune é compatível com aplicativos negados pela WIP (Proteção de Informações da Windows)<!-- 1479103 -->
Você pode especificar aplicativos negados no Intune. Se um aplicativo for negado, ele será impedida de acessar informações corporativas, efetivamente o oposto da lista de aplicativos permitidos. Para obter mais informações, consulte [Lista de negações recomendados para a Proteção de Informações do Windows](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="november-2017"></a>Novembro de 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Solucionar problemas de registro  <!-- 746324 -->

Agora o workspace **Solução de problemas** mostra problemas de registro do usuário. Os detalhes sobre o problema e as etapas de correção sugeridas podem ajudar os administradores e os operadores de suporte técnico a solucionar problemas. Determinados problemas de registro não são capturados e alguns erros podem não ter as sugestões de correção.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrições de registro atribuídas pelo grupo <!-- 747598 -->

Como administrador do Intune, agora é possível [criar restrições personalizadas de registro de Tipo de dispositivo e de Limite de dispositivos para grupos de usuários](enrollment-restrictions-set.md).

O Portal do Azure do Intune permite criar até 25 instâncias de cada tipo de restrição que podem ser atribuídas a grupos de usuários. Restrições atribuídas a grupos substituem as restrições padrão.

Todas as instâncias de um tipo de restrição são mantidas em uma lista estritamente ordenada. Essa ordem define um valor de prioridade para resolução de conflitos. Um usuário afetado por mais de uma instância de restrição é restringido apenas pela instância com o valor de prioridade mais elevado. Você pode alterar a prioridade de uma determinada instância arrastando-a para uma posição diferente na lista.

Essa funcionalidade será lançada com a migração das configurações de Android for Work no menu de registro do Android for Work para o menu de Restrições de Registro. Como esta migração pode levar vários dias, sua conta pode ser atualizada para outras partes do lançamento de novembro antes que você veja uma atribuição de grupo habilitada para Restrições de Registro.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Suporte para vários conectores do Serviço de Registro de Dispositivo de Rede (NDES) <!-- 1528104 -->

O NDES permite a execução de dispositivos móveis sem credenciais de domínio para obter certificados baseados no protocolo SCEP.
Nesta atualização, há suporte a vários conectores NDES.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gerenciar dispositivos Android for Work independentemente dos dispositivos Android <!-- 1490731 EEready-->

O Intune é compatível com gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

Por padrão, as configurações de dispositivos Android for Work são as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.

Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

Ao trabalhar com as novas configurações, considere os seguintes pontos:

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

### <a name="google-play-protect-support-on-android----908720---"></a>Suporte para Google Play Protect no Android <!-- 908720 -->

Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. Agora o Intune é compatível com os recursos do Google Play Protect, incluindo atestado remoto do SafetyNet. Os administradores podem definir requisitos de política de conformidade que exigem que o Google Play Protect esteja configurado e íntegro.
A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play. Se um dispositivo não for compatível com os requisitos do Google Play Protect, o acesso condicional poderá impedir que os usuários acessem recursos corporativos.

- Saiba [Como criar uma política de conformidade do dispositivo para habilitar o Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocolo de texto permitido em Aplicativos gerenciados <!-- 1414050  -->

Aplicativos gerenciados pelo SDK do Aplicativo do Intune podem enviar mensagens SMS.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Relatório de instalação de aplicativos atualizado para incluir o status de Instalação pendente<!-- 1249446 -->  

O relatório **Status de instalação do aplicativo**, acessível para cada aplicativo por meio da lista **Aplicativo** na carga de trabalho **Aplicativos clientes**, agora contém uma contagem de **Instalação pendente** para Usuários e Dispositivos.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API do inventário de aplicativos iOS 11 para detecção de ameaças móveis <!-- 1391759 -->

O Intune coleta informações do inventário de aplicativos de dispositivos pessoais e corporativos e as disponibiliza para provedores de MTD (Detecção de Ameaça Móvel) para efetuar fetch, como Lookout for Work. É possível coletar um inventário de aplicativos dos usuários de dispositivos iOS 11+.

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

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrar usuários e dispositivos do MDM híbrido para o <!-- 1463747 wnready --> autônomo do Intune
Novos processos e ferramentas já estão disponíveis para mover os usuários e seus dispositivos do MDM híbrido para o Intune no Portal do Azure, permitindo que você realize as seguintes tarefas:
- Copiar perfis e políticas do console do Configuration Manager para o Intune no portal do Azure
- Mover um subconjunto de usuários ao Intune no portal do Azure enquanto mantém o restante no MDM híbrido
- Migrar os dispositivos para o Intune no portal do Azure sem necessidade de registrá-los novamente

Consulte os detalhes em [Migrar usuários e dispositivos do MDM híbrido para o Intune autônomo](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->
Após o Exchange Connector criar uma conexão com o Exchange usando o CAS especificado, o conector terá a capacidade de descobrir outros CASs. Se o CAS primário ficar não disponível, o conector realizará o failover em outro CAS, se houver um disponível, até que o CAS primário fique disponível. Para obter detalhes, confira [Suporte de alta disponibilidade do Exchange Connector local](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Reiniciar remotamente o dispositivo iOS (somente supervisionado) <!-- 1424595 -->

Agora é possível disparar um dispositivo iOS 10.3+ supervisionado para reiniciar usando uma ação do dispositivo. Para obter mais informações sobre como usar a ação de reinício de dispositivo, consulte [Reiniciar remotamente dispositivos com o Intune](device-restart.md).

> [!Note]
> Este comando requer um dispositivo supervisionado e o direito de acesso de **Bloqueio de Dispositivo**. O dispositivo é reiniciado imediatamente. Dispositivos iOS protegidos por senha não serão reconectados a uma rede Wi-Fi após a reinicialização; Após a reinicialização, é possível que eles não se comuniquem com o servidor.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Suporte para logon único para iOS <!-- 1333645 -->  

Você pode usar o Logon Único para usuários do iOS. Os aplicativos iOS que são codificados para exigir credenciais do usuário no conteúdo do Logon Único são compatíveis com essa atualização de configuração de conteúdo. Você também pode usar o UPN e a ID de Dispositivo do Intune para configurar o Nome da entidade e o Realm. Para obter detalhes, consulte [Configurar o Intune para logon único de dispositivo iOS](sso-ios.md).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Adicionar "Encontrar meu iPhone" para dispositivos pessoais <!--1427287-->
Agora você pode exibir se os dispositivos iOS têm o Bloqueio de Ativação ligado. Esse recurso podia ser encontrado anteriormente no portal clássico do Intune.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Bloquear dispositivos macOS gerenciados remotamente com o Intune <!-- 1437691 -->

É possível bloquear um dispositivo macOS perdido e definir um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

Para obter mais informações, consulte [Bloquear dispositivos gerenciados remotamente com o Intune](device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Novos detalhes do perfil de SCEP com suporte <!-- 1559808 -->

Agora os administradores podem definir configurações adicionais ao criar um perfil SCEP em plataformas Windows, iOS, macOS e Android.  Os administradores podem definir o IMEI, o número ou o nome comum incluindo email no formato de nome do assunto.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Manter dados durante uma redefinição de fábrica <!--1588489 -->
Ao restaurar o Windows 10 versão 1709 e posterior para as configurações de fábrica, uma nova funcionalidade estará disponível. Os administradores poderão especificar se o registro de dispositivo e outros dados provisionados serão mantidos em um dispositivo por meio de uma redefinição de fábrica.

Os seguintes dados são mantidos após a redefinição de fábrica:
- Contas do usuário associadas ao dispositivo
- Estado do computador (ingresso no domínio, ingressado no Azure Active Directory)
- Registro do MDM
- Aplicativos instalados pelo OEM (aplicativos do Win32 e da loja)
- Perfil de usuário
- Dados do usuário de fora do perfil do usuário
- Logon automático do usuário

Os dados a seguir não são mantidos:
- Arquivos do usuário
- Aplicativos instalados pelo usuário (aplicativos do Win32 e da loja)
- Configurações do dispositivo não padrão


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>As atribuições de anel de atualização do Windows 10 são exibidas <!-- 1621837 -->
Quando estiver **solucionando problemas** para o usuário que estiver sendo exibido, será possível ver as atribuições de anéis de atualização do Windows 10.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Configurações de frequência do relatório da Proteção Avançada contra Ameaças do Windows Defender <!-- 1455974  -->
O serviço de Proteção Avançada contra Ameaças (WDATP) do Windows Defender permite que os administradores gerenciem a frequência dos relatórios para dispositivos gerenciados. Com a nova opção de **Agilizar a frequência de relatórios de telemetria**, o WDATP coleta dados e avalia os riscos com mais frequência. O padrão para relatórios otimiza a velocidade e o desempenho. Aumentar a frequência de emissão de relatórios pode ser importante para dispositivos de alto risco. Essa configuração pode ser encontrada no perfil **Windows Defender ATP** nas **Configurações do dispositivo**.

### <a name="audit-updates----1412961---"></a>Atualizações de auditoria <!-- 1412961 -->  
A auditoria do Intune fornece um registro das operações de alteração relacionadas ao Intune.  Todas as operações de criação, atualização, exclusão e de tarefa remota são capturadas e mantidas por um ano.  O portal do Azure fornece uma exibição dos últimos 30 dias de dados de auditoria em cada carga de trabalho e pode ser filtrado.  Uma API do Graph correspondente permite a recuperação dos dados de auditoria armazenados para o último ano.

A auditoria é encontrada no grupo **MONITOR**. Há um item de menu de **Logs de Auditoria** para cada carga de trabalho.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>O aplicativo Portal da Empresa para macOS está disponível <!--1541700-->
O Portal da Empresa do Intune no macOS tem uma experiência atualizada, que foi otimizada para exibir corretamente todas as informações e notificações de conformidade que seus usuários precisam para todos os dispositivos inscritos. E, após a implantação do Portal da Empresa do Intune em um dispositivo, o Microsoft AutoUpdate para macOS fornecerá as atualizações. Baixe o novo Portal da Empresa do Intune para macOS fazendo logon no site do Portal da Empresa do Intune em um dispositivo macOS.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Agora, o Microsoft Planner faz parte da lista MAM (gerenciamento de aplicativo móvel) de aplicativos aprovados <!-- 1248473 -->
O aplicativo Microsoft Planner para iOS e Android agora faz parte dos aplicativos aprovados para MAM (gerenciamento de aplicativo móvel). O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários.
- Saiba mais sobre a [lista MAM de aplicativos aprovados](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Frequência de atualização de requisito por VPN por aplicativo em dispositivos iOS <!-- 1547061 -->  
Agora, os administradores podem remover os requisitos de acordo com a VPN do aplicativo para aplicativos em dispositivos iOS; os dispositivos afetados serão após o próximo check-in no Intune, o que geralmente ocorre em 15 minutos.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Suporte para o pacote de gerenciamento do System Center Operations Manager para o conector do Exchange <!-- 885457 -->
O pacote de gerenciamento do SCOM (System Center Operations Manager) para o conector do Exchange está disponível para ajudar você a analisar os logs do conector do Exchange. Com esse recurso, você terá diferentes maneiras de monitorar o serviço quando houver necessidade de solucionar problemas.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogerenciamento para dispositivos Windows 10  <!-- 1243445 -->
O cogerenciamento é uma solução que fornece uma ponte do gerenciamento tradicional para o moderno e um caminho para fazer a transição usando uma abordagem em fases. Na sua base, o cogerenciamento é uma solução na qual os dispositivos Windows 10 são gerenciados simultaneamente pelo Configuration Manager e pelo Microsoft Intune, e também podem ser ingressados no AD (Active Directory) e no Azure AD (Azure Active Directory).  Essa configuração lhe fornece um caminho para modernizar ao longo do tempo, no ritmo que seja adequado para sua organização se você não puder mover tudo de uma só vez.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Restringir o registro do Windows por versão do sistema operacional <!-- 245498 -->
Como administrador do Intune, agora é possível especificar uma versão mínima e uma máxima do Windows 10 para registros de dispositivo. É possível definir essas restrições na folha **Configurações de Plataforma**.

Agora o Intune continuará dando suporte ao registro de computadores e telefones Windows 8.1. Contudo, apenas versões do Windows 10 podem ser definidas com limites mínimo e máximo. Para permitir o registro de dispositivos 8.1, deixe o limite mínimo vazio.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alertas para dispositivos não atribuídos do Windows AutoPilot <!-- 1631236 -->
Um novo alerta está disponível para dispositivos não atribuídos do Windows AutoPilot na página **Microsoft Intune** > **Registro de Dispositivo** > **Visão geral**. Este alerta mostra quantos dispositivos do programa AutoPilot não têm perfis de implantação do AutoPilot atribuídos. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows AutoPilot e informações detalhadas sobre eles. Para obter mais informações, consulte [Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Botão Atualizar para a Lista de dispositivos    <!-- 1333581 -->
Como a Lista de dispositivos não é atualizada automaticamente, é possível usar o novo botão Atualizar para atualizar os dispositivos exibidos na lista.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Suporte para AC (Autoridade de Certificação) da Nuvem Symantec  <!-- 1333638 -->    
O Intune agora é compatível com a AC da Nuvem Symantec, que permite que o Conector de Certificado do Intune emita certificados PKCS da AC da Nuvem Symantec para dispositivos gerenciados pelo Intune. Se você já está usando o Conector de Certificado do Intune com a AC (Autoridade de Certificação) da Microsoft, é possível usar a configuração do Conector de Certificado do Intune existente para adicionar a compatibilidade com a AC da Symantec.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Novos itens adicionados ao inventário de aplicativos   <!--1404455 -->
Os novos itens a seguir já estão disponíveis para o [inventário realizado por dispositivos registrados](device-inventory.md):

- Endereço MAC Wi-Fi
- Espaço de armazenamento total
- Espaço livre total
- MEID
- Operadora do assinante

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Definir o acesso para aplicativos pelo patch de segurança do Android mínimo no dispositivo<!-- 1278463 -->   
Um administrador pode definir o patch mínimo de segurança do Android que deve ser instalado no dispositivo para obter acesso a um aplicativo gerenciado em uma conta gerenciada.

> [!Note]  
> Este recurso só restringe os patches de segurança lançados pela Google no Android 6.0 + dispositivos.

### <a name="app-conditional-launch-support----1193313---"></a>Suporte de inicialização condicional do aplicativo <!-- 1193313 -->
Os administradores de TI agora poderão definir um requisito por meio do portal de administração do Azure para impor uma senha em vez de um PIN numérico por meio do gerenciamento de aplicativo móvel (MAM) quando o aplicativo iniciar. Se configurado, o usuário precisa definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. Esta versão do Intune permitirá esse recurso **somente no iOS**. O Intune dá suporte à senha de uma maneira semelhante ao PIN numérico, ele define um comprimento mínimo, permitindo caracteres e sequências repetidas. Esse recurso exige a participação de aplicativos (ou seja, WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune ao código desse recurso em vigor para as configurações de senha a serem impostas aos aplicativos de destino.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>O número de Versão do Aplicativo para linha de negócios no relatório de status de instalação do dispositivo <!-- 1233999 -->
Com esta versão, o relatório de status de instalação do dispositivo exibe o número de versão do aplicativo para aplicativos de linha de negócios para iOS e Android. Você pode usar essas informações para solucionar problemas de seus aplicativos ou para localizar dispositivos que executam versões desatualizadas do aplicativo.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Os administradores agora podem definir as configurações de Firewall em um dispositivo usando um perfil de configuração do dispositivo <!-- 951708 -->   
Os administradores podem ativar o firewall para dispositivos e também configurar vários protocolos para redes públicas, privadas e de domínio.  Essas configurações de firewall podem ser encontradas no perfil "Endpoint Protection".

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>O Windows Defender Application Guard ajuda a proteger dispositivos contra sites não confiáveis, conforme definido pela sua organização <!-- 958257 -->   
Os administradores podem definir sites como "confiáveis" ou "corporativos" usando um fluxo de trabalho da Proteção de Informações do Windows ou o novo perfil "Limite de rede" nas configurações do dispositivo. Caso sejam exibidos com o Microsoft Edge, os sites que não estão listados no limite de rede confiável de um dispositivo Windows 10 de 64 bits serão abertos em um navegador de um computador virtual do Hyper-V.

O Application Guard pode ser encontrado nos perfis de configuração do dispositivo, no perfil "Endpoint Protection". A partir daí, os administradores podem configurar a interação entre o navegador virtualizado e o computador host, sites não confiáveis e sites confiáveis e dados de armazenamento gerados no navegador virtualizado. Para usar o Application Guard em um dispositivo, um limite de rede deve estar configurado primeiro. É importante definir somente um limite de rede para um dispositivo.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>O Windows Defender Application Control no Windows 10 Enterprise fornece modo para confiar somente em aplicativos autorizados <!-- 1031096 -->    
Com milhares de novos arquivos mal-intencionados criados diariamente, usar a detecção baseada em assinatura de antivírus para combater o malware poderá deixar de fornecer uma defesa adequada contra novos ataques. Ao usar o Windows Defender Application Control no Windows 10 Enterprise, é possível alterar a configuração do dispositivo de um modo no qual os aplicativos sejam confiáveis, a menos que sejam bloqueados por um antivírus ou outra solução de segurança, para um modo no qual o sistema operacional confie somente em aplicativos autorizados por sua empresa. Atribua confiança a aplicativos no Windows Defender Application Control.

Com o Intune, é possível configurar políticas de controle de aplicativo no modo "somente auditoria" ou no modo de imposição. Os aplicativos não são bloqueados durante a execução no modo “somente auditoria”. O modo "somente auditoria" registra todos os eventos em logs do cliente local. Também é possível configurar se somente componentes do Windows e aplicativos da Microsoft Store podem ser executados ou se aplicativos adicionais com boa reputação, conforme definido pelo Intelligent Security Graph, podem ser executados.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>O Windows Defender Exploit Guard é um novo conjunto de recursos de prevenção contra intrusões para o Windows 10 <!-- 1063615 -->   
O Windows Defender Exploit Guard inclui regras personalizadas para reduzir a capacidade de exploração de aplicativos, impede ameaças à macro e ao script, bloqueia automaticamente conexões de rede para endereços IP de baixa reputação e pode proteger dados do ransomware e ameaças desconhecidas. O Windows Defender Exploit Guard consiste nos seguintes componentes:

- A **Redução da Superfície de Ataque (ASR)** fornece regras que permitem impedir ameaças a email, macro e script.
- O **acesso controlado a pastas** bloqueia automaticamente o acesso ao conteúdo de pastas protegidas.
- O **Filtro de Rede** bloqueia a conexão de saída de qualquer aplicativo para IP/domínio de baixa reputação
- O **Exploit Protection** fornece memória, fluxo de controle e restrições de políticas que podem ser usados para proteger um aplicativo contra explorações.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10 <!-- 790537 -->

A extensão de gerenciamento do Intune permite que você carregue scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão complementa as funcionalidades MDM (Gerenciamento de Dispositivo Móvel) do Windows 10 e torna fácil para você passar para um gerenciamento moderno. Para obter detalhes, consulte [Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10](intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Novas configurações de restrição de dispositivo para Windows 10      <!-- 1308850 -->
-    Mensagens (somente celular) – Desabilite testes ou mensagens MMS
-    Senha – As configurações para habilitar o FIPS e o uso dos dispositivos secundários Windows Hello para autenticação 
-    Tela – Configurações para ativar ou desativar o dimensionamento do GDI para aplicativos herdados

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Restrições de dispositivo do modo de quiosque do Windows 10 <!-- 1308872 -->   
É possível restringir os usuários do dispositivo Windows 10 ao modo de quiosque, que limita os usuários a um conjunto de aplicativos predefinidos.  Para fazer isso, crie um perfil de restrição de dispositivo Windows 10 e defina as configurações de Quiosque.

O modo de quiosque dá suporte a dois modos: **único aplicativo** (permite que um usuário execute apenas um aplicativo) ou **multiaplicativo** (permite o acesso a um conjunto de aplicativos).  Você define o nome do dispositivo e da conta de usuário, o que determina os aplicativos com suporte).  Quando o usuário está conectado, ele estará limitado aos aplicativos definidos.  Para obter mais informações, consulte [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

O modo de quiosque requer:

- O Intune deve ser a autoridade MDM.
- Os aplicativos já devem estar instalados no dispositivo de destino.
- O dispositivo deve ser [adequadamente provisionado](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Novo perfil de configuração do dispositivo para criar limites de rede <!-- 1311967 -->   
Um novo perfil de configuração de dispositivo chamado **Limite de rede** pode ser encontrado com seus outros perfis de configuração de dispositivo. Use esse perfil para definir os recursos online que você deseja que sejam considerados corporativos e confiáveis. Você deve definir um limite de rede para um dispositivo *antes* que os recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows, possam ser usados no dispositivo. É importante definir somente um limite de rede para cada dispositivo.

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

**Extensão de tempo limite para verificação de arquivo pela nuvem**  

| | |
|--|--|
| Número de segundos (0-50) | Especifique o máximo de tempo para o Windows Defender Antivírus bloquear um arquivo enquanto aguarda um resultado da nuvem. O tempo padrão é de 10 segundos: qualquer tempo adicional especificado aqui (até 50 segundos) será adicionado a esses 10 segundos. Na maioria dos casos, a verificação leva muito menos tempo do que o máximo. Estender o tempo permite que a nuvem investigue completamente os arquivos suspeitos. É recomendável que você habilite essa configuração e especifique pelo menos 20 segundos adicionais. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN adicionado a dispositivos Windows 10 <!-- 1512457 -->  
É possível configurar uma VPN Citrix para seus dispositivos Windows 10. É possível escolher a VPN do Citrix na lista *Selecione um tipo de conexão* na folha **VPN da Base** ao configurar a VPN para Windows 10 e posterior.

> [!Note]
> A configuração do Citrix existia para iOS e Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>As conexões Wi-Fi são compatíveis com chaves pré-compartilhadas no iOS <!-- 1550823 -->
Os clientes podem configurar perfis Wi-Fi para usar PSK (chaves pré-compartilhadas) para conexões WPA/WPA2 Personal em dispositivos iOS. Esses perfis são enviados por push para o dispositivo do usuário quando o dispositivo é registrado no Intune.

Quando o perfil tiver sido enviado por push para o dispositivo, a próxima etapa dependerá da configuração do perfil.  Se estiver configurado para se conectar automaticamente, ele se conectará quando a rede for a próxima necessária.  Quando o perfil se conecta manualmente, o usuário deve ativar a conexão manualmente.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Acesso aos logs de aplicativos gerenciados para iOS <!-- 1469920 -->
Agora os usuários finais com o Browser gerenciado instalado podem exibir o status de gerenciamento de todos os aplicativos publicados da Microsoft e enviar logs para solucionar problemas dos seus aplicativos iOS gerenciados.

Saiba como habilitar o modo de solução de problemas no Managed Browser em um dispositivo iOS, consulte [How to access to managed app logs using the Managed Browser on iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) (Como acessar logs de aplicativos gerenciados usando o Managed Browser no iOS).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Aprimoramentos no fluxo de trabalho de configuração de dispositivo no Portal da Empresa para iOS na versão 2.9.0 <!-- 1417174 -->

O fluxo de trabalho de configuração de dispositivo foi melhorado no aplicativo Portal da Empresa para iOS. A linguagem é mais fácil de usar e combinamos as telas sempre que possível. A linguagem é mais específica à sua empresa ao usar o nome da empresa em todo o texto de configuração. Veja esse fluxo de trabalho atualizado na  [página de novidades da interface do usuário do aplicativo](whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entidade de usuário contém dados mais recentes do usuário no modelo de dados do Data Warehouse <!-- 1544273 -->
A primeira versão do modelo de dados do Intune Data Warehouse continha somente dados históricos recentes do Intune. Os criadores de relatório não podiam capturar o estado atual de um usuário. Nesta atualização, a **Entidade do usuário** é preenchida com os dados mais recentes do usuário.


## <a name="october-2017"></a>Outubro de 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>O número de versão do aplicativo de linha de negócios Android e iOS é visível <!-- 1380712 -->

Aplicativos no Intune agora exibem o número de versão para aplicativos de linha de negócios iOS e Android. O número é exibido no portal do Azure na lista de aplicativos e na folha de visão geral do aplicativo. Os usuários finais podem ver o número do aplicativo no aplicativo do Portal da Empresa e no portal da web.

__Número de versão completo__ O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800)

O número de versão completa tem dois componentes:

 - **Versão**  
   O número de versão é o número de versão legível do aplicativo. Isso é usado pelos usuários finais para identificar versões diferentes do aplicativo.

 - **Número de build**  
    O número de build é um número interno que pode ser usado na detecção do aplicativo e para gerenciar o aplicativo de forma programática. O número de build se refere a uma iteração do aplicativo que referencia alterações no código.

Saiba mais sobre os números de versão e desenvolvimento de aplicativos de linha de negócios em [Introdução ao SDK de Aplicativo do Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integração do gerenciamento de dispositivos e aplicativos <!-- 677972 -->   
Agora que o gerenciamento de dispositivo móvel do Intune (MDM) e o gerenciamento de aplicativo móvel (MAM) são ambos acessíveis do portal do Azure, o Intune começou integrar a experiência de administração de TI em torno do gerenciamento de aplicativo e dispositivo. Essas alterações têm o objetivo de simplificar seu dispositivo e a experiência de gerenciamento de aplicativo.

Saiba mais sobre as alterações de MDM e MAM anunciadas no [blog da equipe de suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Novos alertas de registro para dispositivos Apple <!-- 1471790 -->
A página de visão geral de registro mostrará alertas úteis para administradores de TI sobre o gerenciamento de dispositivos Apple. Os alertas serão exibido na página Visão geral de quando o certificado de push de MDM da Apple estiver expirando ou já tiver expirado; quando o token do Programa de Registro de Dispositivos estiver expirando ou já tiver expirado; e quando houver dispositivos não atribuídos no Programa de Registro de Dispositivo.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Substituição do token de suporte para a configuração de aplicativo sem registro de dispositivo <!-- 1080364 -->

Você pode usar tokens de valores dinâmicos nas configurações de aplicativo para aplicativos em dispositivos que não estão registrados. Para obter mais informações, consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Atualizações para o aplicativo Portal da Empresa para Windows 10 <!--1299474-->
A página Configurações no aplicativo Portal da Empresa para Windows 10 foi atualizada para tornar as configurações e as ações de usuário pretendidas mais consistentes em todas as configurações. Ela também foi atualizada para corresponder ao layout de outros aplicativos do Windows. Encontre imagens de antes/depois na página [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para dispositivos com Windows 10 <!--1337920-->
Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para Windows 10. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela **Sobre**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Solicitações de comentários para o aplicativo Portal da Empresa para Android <!--1165249-->
O aplicativo Portal da Empresa para Android agora solicita comentários do usuário final. Estes comentários são enviados diretamente para a Microsoft e fornecem aos usuários finais uma oportunidade de avaliar o aplicativo na loja pública do Google Play. Os comentários não são obrigatórios, e podem ser ignorados facilmente para que os usuários possam continuar usando o aplicativo.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ajudando seus usuários com o aplicativo de Portal da Empresa para Android <!-- 1573324, 1573150, 1558616, 1564878 -->

O aplicativo de Portal da Empresa para Android adicionou instruções para os usuários finais a fim de ajudá-los a compreender e, quando possível, resolver automaticamente novos casos de uso.
- Os usuários finais serão direcionados para o [Portal do Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) para remover um dispositivo se tiverem atingido o número máximo de dispositivos que eles têm permissão para adicionar.
- Os usuários finais recebem etapas a serem seguidas para ajudá-los a [corrigir erros de ativação em dispositivos Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) ou a [desligar o modo de economia de energia](/intune-user-help/power-saving-mode-android). Se nenhuma dessas soluções resolver o problema, fornecemos uma explicação de como [enviar logs para a Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nova ação “Resolver” disponível para dispositivos Android <!-- 1583480 -->

O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android atualmente dá suporte a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indicador de progresso de configuração do dispositivo no Portal da Empresa para Android <!-- 1565657 -->
O aplicativo Portal da Empresa para Android mostra um indicador de progresso de configuração do dispositivo quando o usuário estiver inscrevendo seu dispositivo. O indicador mostra novos status, começando com "Configurando seu dispositivo...", depois "Registrando seu dispositivo..." e "Concluindo o registro de seu dispositivo...", em seguida, "Concluindo a configuração de seu dispositivo...".

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Suporte à autenticação baseada em certificado no Portal da Empresa para iOS <!--1029830-->
Adicionamos suporte para autenticação baseada em certificado (CBA) no aplicativo do Portal da Empresa para iOS. Os usuários com CBA inserem seus nomes de usuário, em seguida, tocam no link "Entrar com um certificado". O CBA já é compatível com os aplicativos do Portal da Empresa para Android e Windows. Você pode obter mais informações na página [entrar no aplicativo do Portal da Empresa](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->

Os aplicativos da empresa que foram disponibilizados com ou sem o registro no aplicativo do Portal da Empresa Android agora podem ser instalados sem um aviso de registro.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune----747617---"></a>Suporte do Programa Windows AutoPilot Deployment no Microsoft Intune  <!-- 747617  -->
Agora você pode usar o Microsoft Intune com o programa Windows AutoPilot Deployment para capacitar os usuários a provisionarem dispositivos corporativos sem envolver TI. Você pode personalizar a OOBE (configuração inicial pelo usuário) e orientar os usuários a ingressarem seus dispositivos no Azure AD e a se registrarem no Intune. Trabalhando juntos, o Microsoft Intune e o Windows AutoPilot eliminam a necessidade de implantar, manter e gerenciar imagens do sistema operacional. Para obter detalhes, consulte [Enroll Windows devices using Windows AutoPilot Deployment Program](https://docs.microsoft.com/intune/enrollment-autopilot) (Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment).

### <a name="quick-start-for-device-enrollment----1425655---"></a>Início rápido para o registro de dispositivo  <!-- 1425655 --> 
O início rápido agora está disponível para o **Registro de dispositivo** e fornece uma tabela de referências para gerenciamento de plataformas e a configuração do processo de registro. Uma breve descrição de cada item e links para a documentação com instruções passo a passo fornece uma documentação útil para simplificar a introdução.

### <a name="device-categorization----1427491---"></a>Categorização de dispositivo <!-- 1427491 -->
O gráfico de plataforma de dispositivos registrados da folha **Dispositivos > Visão geral** organiza os dispositivos pela plataforma, incluindo Windows Mobile, Windows, macOS, iOS e Android.  Os dispositivos que executam outros sistemas operacionais são agrupados em "Outros".  Isso inclui dispositivos fabricados pela Blackberry, NOKIA e outras.  

Para saber quais dispositivos são afetados em seu locatário, escolha **Gerenciar > Todos os dispositivos** e, em seguida, use **Filtrar** para limitar o campo **SO**.

### <a name="zimperium---new-mobile-threat-defense-partner-----954681---"></a>Zimperium – Novo parceiro de Defesa contra Ameaças Móveis   <!-- 954681 -->  
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Zimperium, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como funciona a integração com o Intune
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Zimperium. Você pode configurar políticas de acesso condicional de EMS com base na avaliação de risco do Zimperium habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade a recursos corporativos com base em ameaças detectadas.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10  <!--- 978575, 1308849, -->  
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Suporte remoto para dispositivos Windows e Windows Mobile  <!-- 1070473 -->  
O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, que permite dar assistência remota a usuários que executam dispositivos Windows e Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988-1280990---"></a>Verificar dispositivos com o Windows Defender <!-- 1280988  1280990   -->
Agora você pode executar uma **Verificação rápida**, uma **Verificação completa** e **Atualizar assinaturas** com o Windows Defender Antivírus em dispositivos Windows 10 gerenciados. Na folha de visão geral do dispositivo, escolha a ação a ser executada no dispositivo. Você precisará confirmar a ação antes de o comando ser enviado ao dispositivo. 

**Exame rápido**: Uma verificação rápida examina os locais onde o malware registra-se para começar, como as chaves do Registro e pastas de inicialização conhecidas do Windows. Uma verificação rápida demora cerca de cinco minutos. Combinada com a configuração **Proteção sempre em tempo real**, que examina os arquivos quando eles são abertos, fechados e sempre que um usuário navega até uma pasta, uma verificação rápida ajuda a fornecer proteção contra malware que pode estar no sistema ou no kernel. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Exame completo**: Um exame completo pode ser útil em dispositivos que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa, e é útil para executar verificações sob demanda. A verificação completa pode demorar uma hora. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Atualizar assinaturas**: O comando para atualizar assinatura atualiza as definições e assinaturas de malware do Windows Defender. Isso ajuda a garantir o que Windows Defender Antivírus seja eficaz na detecção de malware. Esse recurso destina-se somente a dispositivos com Windows 10, com conectividade de internet pendente no dispositivo. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>O botão Habilitar/Desabilitar foi removido da página Autoridade de certificação do Intune do Portal do Azure do Intune  <!-- 1400455 -->
 Estamos eliminando uma etapa extra da configuração do Certificate Connector no Intune. No momento, você pode baixar o Certificate Connector e habilitá-lo no console do Intune. No entanto, se você desabilitar o conector no console do Intune, o conector continuará a emitir certificados.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A partir de outubro, o botão Habilitar/Desabilitar não aparecerá mais na página Autoridade de certificação no Portal do Azure. A funcionalidade do conector permanece a mesma. Os certificados ainda são implantados nos dispositivos registrados no Intune. Você ainda pode baixar e instalar o Certificate Connector. Para interromper a emissão de certificados, agora você pode desinstalar o Certificate Connector em vez de desabilitá-lo.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se o Certificate Connector já estiver desabilitado, você deverá desinstalá-lo.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10 Team   <!--- 1308838 -->
Nesta versão, foram adicionadas várias novas configurações ao perfil de restrição de dispositivo do Windows 10 Team para ajudar a controlar dispositivos do Surface Hub.

Para saber mais sobre esse perfil, veja [Configurações de restrição de dispositivo do Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time----1333292---"></a>Impedir que os usuários de dispositivos com Android alterem a data e a hora de seus dispositivos  <!-- 1333292 -->
Use uma [política de dispositivo personalizada do Android](custom-settings-android.md) para impedir que os usuários de dispositivos com Android alterem a data e a hora do dispositivo.

Para fazer isso, configure uma política personalizada do Android com o URI de configuração ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Defina isso como **TRUE** e, em seguida, atribua-o aos grupos necessários.

### <a name="bitlocker-device-configuration---1397398---"></a>Configuração de dispositivo do BitLocker <!-- 1397398 -->
A seção **Criptografia do Windows > Configurações Base** inclui uma nova configuração **Aviso para criptografia de outro disco** que permite que você desabilite o [prompt de aviso](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) para a criptografia de outro disco que possa estar em uso no dispositivo do usuário.  A mensagem de aviso exige o consentimento do usuário final antes de instalar o BitLocker no dispositivo e bloqueia a instalação do BitLocker até receber a confirmação do usuário final.  A nova configuração desabilita o aviso ao usuário final.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Os aplicativos do Volume Purchase Program for Business agora serão sincronizadas ao seu locatário do Intune <!-- 800882 -->  
Os desenvolvedores de terceiros podem distribuir aplicativos de forma privada para membros autorizados do VPP (Volume Purchase Program) for Business especificados no iTunes Connect. Esses membros do VPP for Business podem entrar na App Store do Volume Purchase Programa e adquirir seus aplicativos.

Com esta versão, os aplicativos do VPP for Business comprados pelo usuário final passarão a ser sincronizados com seus locatários do Intune.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Selecione o país da loja da Apple para sincronização de aplicativos VPP<!-- 1332311 -->  
Você pode configurar o país da loja do VPP (Programa de Compra por Volume) ao carregar seu token de VPP. O Intune sincroniza aplicativos VPP para todas as localidades da loja VPP especificada de um país.

> [!NOTE]  
> Atualmente, o Intune sincroniza apenas aplicativos VPP da loja VPP que correspondem à localidade do Intune na qual o locatário do Intune foi criado.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquear a ação de copiar e colar entre perfis de trabalho e pessoais no Android for Work <!-- 1098994 -->
Com esta versão, é possível configurar o perfil de trabalho para Android for Work para bloquear a ação de copiar e colar entre aplicativos pessoais e de trabalho. Encontre essa nova configuração no perfil **Restrições de dispositivo** para a plataforma **Android for Work** em **Configurações de perfil de trabalho**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Criar aplicativos iOS limitados a Apple App Stores regionais específicas <!-- 1281692 -->
Você poderá especificar a localidade do país durante a criação de um aplicativo gerenciado da Apple App Store.

> [!Note]  
> No momento, você só pode criar aplicativos gerenciados da Apple App Store que estão presentes na loja dos Estados Unidos.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Atualizar usuário VPP do iOS e os aplicativos de dispositivo licenciados <!-- 1305564 -->  
Você poderá configurar o token de VPP do iOS para atualizar todos os aplicativos comprados para esse token por meio do serviço Intune. O Intune detectará as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará automaticamente ao dispositivo quando o dispositivo fizer check-in.

Para obter as etapas para definir um token do VPP e habilitar as atualizações automáticas, consulte [Como gerenciar aplicativos iOS comprados por meio de um Volume Purchase Program com o Microsoft Intune] (/intune/vpp-aplicativos-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->
Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Examinar a conformidade da política para anéis de atualização do Windows 10 <!-- 1067886 -->
Você poderá examinar um relatório da política de seus grupos de atualização do Windows 10 em Atualizações de software > Por estado de implantação do grupo de atualização. O relatório da política inclui o status da implantação para os anéis de atualização que você configurou. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions----1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS   <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** está disponível no workspace **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting----1475003---"></a>Exibir as atribuições de política de proteção do aplicativo para solução de problemas <!--  1475003 -->
Nesta versão futura, a opção de **Política de proteção do aplicativo** será adicionada à lista suspensa **Atribuições** disponível na folha de solução de problemas. Agora você pode selecionar as políticas de proteção do aplicativo para ver as políticas de proteção de aplicativo atribuídas aos usuários selecionados.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Melhorias no fluxo de trabalho de configuração de dispositivo no Portal da Empresa <!--1490692-->
Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para Android. A linguagem é mais fácil de usar e mais específica para sua empresa e combinamos as telas sempre que possível. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Melhor orientação sobre a solicitação de acesso aos contatos em dispositivos Android <!--1484985-->

O aplicativo de Portal da Empresa para Android normalmente exige que o usuário final aceite a permissão de Contatos. Se um usuário final recusar esse acesso, ele verá uma notificação no aplicativo que o alerta para conceder a permissão para acesso condicional. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Correção de inicialização segura para Android <!--1490712-->

Os usuários finais com dispositivos Android poderão tocar no motivo da não conformidade no aplicativo do Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Notificações por push adicionais para usuários finais no aplicativo Portal da Empresa para Android Oreo <!--1475932-->

Os usuários finais verão notificações adicionais para indicar a eles quando o aplicativo Portal da Empresa para Android Oreo estiver executando tarefas em segundo plano, como recuperação de políticas do serviço Intune. Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas em seu dispositivo. Isso faz parte da [otimização geral da interface do usuário do Portal da Empresa](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) para o aplicativo Portal da Empresa para Android Oreo. 

Há mais otimizações para novos elementos de interface do usuário que estão habilitados no Android Oreo.  Os usuários finais verão notificações adicionais que indicarão a eles quando o Portal da Empresa estiver executando tarefas em segundo plano, tais como recuperação das políticas do serviço Intune.  Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas no dispositivo deles.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho<!-- 1485783 -->

Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. 

Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->

A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment----1490695---"></a>Bloquear o registro de dispositivo Samsung Knox sem suporte  <!-- 1490695 -->

O aplicativo Portal da Empresa tenta registrar apenas os dispositivos Samsung Knox com suporte. Para evitar erros de ativação de Knox que impedem o registro do MDM, o registro do dispositivo será tentado somente se ele aparecer na [lista de dispositivos publicada pela Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Os dispositivos Samsung podem ter números de modelo que oferecem suporte a Knox, enquanto outros não. Verifique a compatibilidade com KNOX com o revendedor do dispositivo antes de adquirir e implantar. Você pode encontrar a lista completa de dispositivos verificados nas [configurações de política do Android e Samsung Knox Standard](supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Fim do suporte para Android 4.3 e inferior <!-- 1171126, 1326920 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informar aos usuários finais quais informações de dispositivo podem ser vistas em dispositivo registrados <!--1165314-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo em todos os aplicativos Portal da Empresa. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente do artigo [Quais informações sua empresa pode ver?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Isso será distribuído em todos os aplicativos de Portal da Empresa em um futuro próximo. Anunciamos isso para iOS em [setembro](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).

## <a name="september-2017"></a>Setembro de 2017

### <a name="intune-supports-ios-11---1428975--"></a>O Intune dá suporte ao iOS 11 <!--1428975-->
O Intune dá suporte ao iOS 11. Isso foi anunciado anteriormente no [blog de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!-- 1164477 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->
O aplicativo Portal da Empresa para Windows 10 permite que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para iOS <!--739894-->

Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para iOS. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela Sobre.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Permitir que os usuários finais acessem o aplicativo de Portal da Empresa para Android sem registro <!---1169910--->

Em breve, os usuários finais não precisarão registrar seu dispositivo para acessar o aplicativo de Portal da Empresa para Android. Os usuários finais em organizações que estão usando as Políticas de Proteção de Aplicativo deixarão de receber solicitações para registrar seu dispositivo quando abrirem o aplicativo de Portal da Empresa. Os usuários finais também poderão instalar aplicativos do Portal da Empresa sem registrar o dispositivo. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Frases mais fáceis de entender para o aplicativo Portal da Empresa para Android <!---1396349--->  

O processo de inscrição para o aplicativo Portal da Empresa para Android foi simplificado com o novo texto a fim de facilitar a inscrição dos usuários. Se você tiver a documentação de inscrição personalizada, atualize-o para refletir as novas telas. Você pode encontrar as imagens de amostra na nossa página [Atualizações da interface do usuário para aplicativos de usuário final do Intune](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Aplicativo Portal da Empresa do Windows 10 adicionado à política de permissão da Proteção de Informações do Windows <!-- 677129 -->

O aplicativo Portal da Empresa do Windows 10 foi atualizado para dar suporte à WIP (Proteção de Informações do Windows). O aplicativo pode ser adicionado à política de permissão do WIP. Com essa alteração, o aplicativo não precisa mais ser adicionado à lista **Isento**.


## <a name="august-2017"></a>Agosto de 2017

### <a name="improvements-to-device-overview----1404453---"></a>Melhorias na visão geral de dispositivos <!-- 1404453 -->  
Com as melhorias, agora a visão geral de dispositivos exibe os dispositivos registrados, mas exclui os dispositivos gerenciados pelo Exchange ActiveSync. Os dispositivos do Exchange ActiveSync não têm as mesmas opções de gerenciamento que os dispositivos registrados. Para exibir o número de dispositivos registrados e o número de dispositivos registrados por plataforma no Intune, no portal do Azure, acesse **Dispositivos** > **Visão geral**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Melhorias no inventário de dispositivos coletado pelo Intune
<!-- 961134, 1104426, 1281327, 1333543 --> Nesta versão, fizemos as seguintes melhorias nas informações de inventário coletadas pelos dispositivos gerenciados por você:
 
-   Para dispositivos Android, agora você pode adicionar uma coluna no inventário de dispositivos que mostra o nível de patch mais recente para cada dispositivo. Adicione a coluna **Nível de patch de segurança** à sua lista de dispositivos para ver essa informação.
-   Ao filtrar a exibição de dispositivos, agora você pode filtrar os dispositivos pela data de registro. Por exemplo, você pode exibir somente os dispositivos que foram registrados após uma data especificada.
-   Fizemos melhorias no filtro usado pelo item **Última data de check-in**.
-   Na lista de dispositivos, agora você pode exibir o número de telefone dos dispositivos corporativos.
Além disso, você pode usar o painel de filtro para pesquisar dispositivos por número de telefone.

Para obter mais detalhes sobre o inventário de dispositivos, consulte [Como exibir o inventário de dispositivo do Intune](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Suporte a acesso condicional para dispositivos macOS 
<!-- 720172 --> Agora você pode definir uma política de acesso condicional que exige que os dispositivos Mac sejam registrados no Intune e estejam em conformidade com as políticas de conformidade do dispositivo. Por exemplo, os usuários podem baixar o aplicativo de Portal da Empresa Intune para macOS e registrar seus dispositivos Mac no Intune. O Intune avaliar se o dispositivo Mac está em conformidade ou não com requisitos como PIN, criptografia, versão do sistema operacional e integridade do sistema.

- Saiba mais sobre [suporte a acesso condicional para dispositivos macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>O aplicativo Portal da Empresa para macOS está em visualização pública <!---1484796--->
O aplicativo Portal da Empresa para macOS agora está disponível como parte da visualização pública para acesso condicional no Enterprise Mobility + Security. Essa versão é compatível com macOS 10.11 e superior. Obtenha-a em [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Novas configurações de restrição de dispositivo para Windows 10    
<!--1063965, 1308850  --> Nesta versão, adicionamos novas configurações ao [perfil de restrição de dispositivo Windows 10](/intune/device-restrictions-windows-10) nas seguintes categorias:

-   Windows Defender SmartScreen
-   Loja de aplicativos

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Atualizações no perfil de dispositivo de Endpoint Protection do Windows 10 para configurações do BitLocker
<!--1459533 -->     Nesta versão, fizemos as seguintes melhorias no modo de funcionamento das configurações do BitLocker em um perfil de dispositivo de Endpoint Protection do Windows 10:
 
-   Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **BitLocker com chip do TPM não compatível**, anteriormente, quando você selecionava **Bloquear**, na verdade, o BitLocker era permitido. Agora isso foi corrigido para bloquear o BitLocker quando essa opção está selecionada.
-   Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **Agente de recuperação de dados baseada em certificado**, agora você pode bloquear explicitamente o agente de recuperação de dados baseada em certificado. No entanto, por padrão, o agente é permitido.
-   Em **Configurações de unidade de dados fixa do BitLocker**, na configuração **Agente de recuperação de dados**, agora você pode bloquear explicitamente o agente de recuperação de dados.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nova experiência conectada para usuários do Portal da Empresa para Android e para usuários da Política de Proteção de Aplicativo <!-- 621669 -->
Os usuários finais agora podem procurar aplicativos, gerenciar dispositivos e exibir as informações de contato de TI usando o aplicativo Portal da Empresa Android sem inscrever os respectivos dispositivos Android. Além disso, se um usuário final já usa um aplicativo protegido pelas Políticas de Proteção de Aplicativo do Intune, ele não recebe mais uma solicitação para registrar o dispositivo ao iniciar o Portal da Empresa para Android.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nova configuração no aplicativo Portal da Empresa para Android para ativar/desativar a otimização de bateria <!--1405990-->
A página **Configurações** no aplicativo Portal da Empresa para Android tem uma nova configuração que permite que os usuários desliguem facilmente a otimização da bateria para os aplicativos Portal da Empresa e Microsoft Authenticator. O nome do aplicativo mostrado na configuração variará dependendo de qual aplicativo gerencia a conta de trabalho. É recomendável que os usuários desliguem a otimização da bateria para melhorar o desempenho dos aplicativos de trabalho que sincronizam dados e emails. 

### <a name="multi-identity-support-for-onenote-for-ios----1234281---"></a>Suporte a várias identidades do OneNote para iOS      <!-- 1234281 -->
Os usuários finais agora podem usar contas diferentes (trabalho e pessoal) com o Microsoft OneNote para iOS. As políticas de proteção de aplicativo podem ser aplicadas aos dados corporativos em blocos de anotações de trabalho sem afetar os blocos de anotações pessoais. Por exemplo, uma política pode permitir que um usuário localize informações em blocos de anotações de trabalho, mas impedirá que o usuário copie e cole dados corporativos do bloco de anotações de trabalho para um bloco de anotações pessoal.
 
- Saiba mais sobre os aplicativos que dão suporte à [proteção de aplicativo e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Novas configurações para permitir e bloquear aplicativos em dispositivos Samsung Knox Standard
<!-- 1305423 822899-->  
Nessa versão, estamos adicionando novas [configurações de restrições de dispositivo](device-restrictions-android.md) que permitem especificar as seguintes listas de aplicativo:
 
- Aplicativos que os usuários têm permissão para instalar
- Aplicativos que os usuários são impedidos de executar
- Aplicativos que ficam ocultados do usuário no dispositivo  
Você pode especificar o aplicativo por URL, nome de pacote ou na lista de aplicativos gerenciados.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link da nova interface do usuário da política de acesso condicional com base no aplicativo do Azure AD no Intune
<!-- 1016201 --> Agora os administradores de TI podem definir políticas condicionais baseadas no aplicativo por meio da nova interface do usuário de política de acesso condicional na carga de trabalho do Azure AD. O acesso condicional com base no aplicativo na seção Proteção de Aplicativo do Intune no Portal do Azure por enquanto continuará lá e a implementação será feita em conjunto. Também há um link de conveniência para a nova interface do usuário da política de acesso condicional na carga de trabalho do Intune.

- Saiba mais sobre o [acesso condicional com base no aplicativo no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## <a name="july-2017"></a>Julho de 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version-----1333256-1245463----"></a>Restringir a restrição de registro de dispositivo Android e iOS por versão do sistema operacional  <!--- 1333256,  1245463 --->
O Intune agora dá suporte à restrição do registro de iOS e Android por número de versão do sistema operacional. Agora, em **Restrição de Tipo de Dispositivo**, o administrador de TI pode definir uma configuração de plataforma para restringir o registro entre os valores mínimo e máximo do sistema operacional. As versões do sistema operacional Android devem ser especificadas como Major.Minor.Build.Rev, em que Minor, Build e Rev são opcionais. Versões do iOS devem ser especificadas como Major.Minor.Build, em que Minor e Build são opcionais. Saiba mais sobre as [restrições de registro de dispositivo](enrollment-restrictions-set.md).

>[!NOTE]
>Não restringe o registro por meio dos programas de registro da Apple ou do Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment-----1333272-1333275-1245709---"></a>Restringir o registro de dispositivos de propriedade pessoal Android, iOS e macOS  <!--- 1333272,  1333275, 1245709 --->
O Intune pode restringir o registro de dispositivos pessoais colocando em uma lista de permissões os números IMEI dos dispositivos corporativos. Agora, o Intune expandiu essa funcionalidade para iOS, Android e macOS usando os números de série do dispositivo. Ao carregar os números de série para o Intune, você pode pré-declarar os dispositivos como corporativos. Usando as restrições de registro, você pode bloquear dispositivos pessoais (BYOD), permitindo somente o registro de dispositivos de propriedade corporativa. Saiba mais sobre as [restrições de registro de dispositivo](enrollment-restrictions-set.md).

Para importar os números de série, acesse **Registro de dispositivo** > **Identificadores de dispositivo corporativo**, clique em **Adicionar** e, em seguida, carregue um arquivo .CSV (sem cabeçalho, duas colunas de número de série e detalhes como números IMEI). Para restringir os dispositivos pessoais, acesse **Registro de dispositivo** > **Restrições de registro**. Em **Restrições de tipo de dispositivo**, selecione o **Padrão** e, em seguida, escolha **Configurações da Plataforma**. Você pode **Permitir** ou **Bloquear** dispositivos pessoais para iOS, Android e macOS.


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nova ação de dispositivo para forçar os dispositivos a sincronizarem com o Intune <!-- 711369 -->
Nessa versão, adicionamos uma nova ação de dispositivo que força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.
Para ver mais detalhes, consulte [Sincronizar o dispositivo](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível <!-- 777100 -->
Uma nova política está disponível no workspace de Atualizações de software, em que você pode forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Para obter detalhes, consulte [Configurar políticas de atualização do iOS](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner----954651-1172027---"></a>Check Point SandBlast Mobile – novo parceiro de Defesa contra Ameaças Móveis  <!-- 954651, 1172027 -->
É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional baseado na avaliação de risco realizada pelo Checkpoint SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como a integração com o Intune funciona?
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Checkpoint SandBlast Mobile. É possível configurar políticas de acesso condicional de EMS com base na avaliação de risco do Checkpoint SandBlast Mobile habilitada por meio das políticas de conformidade de dispositivo do Intune. Você pode permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base nas ameaças detectadas.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Implantar um aplicativo como ele está disponível na Microsoft Store para Empresas <!-- 748101 -->
Com essa versão, os administradores agora podem atribuir o Microsoft Store para Empresas como ele está disponível. Quando definido como disponível, os usuários finais podem instalar o aplicativo do site ou do aplicativo do Portal da Empresa sem serem redirecionados para a Microsoft Store.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 1-->
Fizemos várias atualizações na interface do usuário do [site Portal da Empresa](https://portal.manage.microsoft.com) para aprimorar a experiência do usuário final.

- __Aprimoramentos para blocos de aplicativo__:  Os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente com base na cor dominante do ícone (caso seja possível detectá-la). Quando aplicável, essa tela de fundo substituirá a borda cinza que era visível anteriormente em blocos de aplicativos.

    O site do Portal da Empresa exibe ícones grandes sempre que possível em uma versão futura. É recomendável que os administradores de TI publiquem aplicativos usando ícones de alta resolução com um tamanho mínimo de 120x120 pixels. 

- __Alterações de navegação__: Os itens da barra de navegação foram movidos para o menu hambúrguer na parte superior esquerda. A página Categorias foi removida. Os usuários agora podem filtrar o conteúdo por categoria durante a navegação.

- __Atualizações de Aplicativos em Destaque__: Adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque na página inicial.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Suporte para iBooks no site do Portal da Empresa <!--1231841-->
Adicionamos uma página dedicada ao site do Portal da Empresa que permite aos usuários procurar e baixar iBooks. 


### <a name="additional-help-desk-troubleshooting-details-----applies-to-1263399-1326964-1341642----"></a>Detalhes adicionais da solução de problemas de suporte técnico <!---  Applies to 1263399, 1326964, 1341642 --->
O Intune atualizou a exibição de solução de problemas e aprimorou as informações que ele fornece aos administradores e à equipe de suporte técnico. Agora, é exibida uma tabela **Atribuições** que resume todas as atribuições do usuário com base em associação a um grupo. Essa lista inclui:
- Aplicativos móveis
- Políticas de conformidade
- Perfis de configuração

Além disso, a tabela **Dispositivos** agora inclui as colunas **Tipo de ingresso no Azure AD** e **Em conformidade com o Azure AD**. Para obter mais informações, consulte [ajudar os usuários a solucionar problemas](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune Data Warehouse (Visualização Pública)
O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do locatário. É possível acessar os dados usando um arquivo do Power BI (PBIX), um link OData compatível com várias ferramentas de análise ou interagindo com a API REST. Para obter mais informações, consulte [Usar o Intune Data Warehouse](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modos claro e escuros disponíveis para o aplicativo de Portal da Empresa para Windows 10 <!---676547--->
Os usuários finais poderão personalizar o modo de cores para o aplicativo de Portal da Empresa para Windows 10. O usuário poderá fazer a alteração na seção Configurações do aplicativo de Portal da Empresa. A alteração será exibida depois que o usuário reiniciar o aplicativo. Para Windows 10 versão 1607 e posteriores, o modo de aplicativo padrão será o da configuração do sistema. Para Windows 10 versão 1511 e anteriores, o modo de aplicativo padrão será o da configuração do sistema.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Habilitar que os usuários finais marquem seu grupo de dispositivos no aplicativo de Portal da Empresa para Windows 10 <!---807046-->
Os usuários finais agora podem selecionar a grupo seu dispositivo pertence marcando-o diretamente de no aplicativo de Portal da Empresa para Windows 10.



## <a name="june-2017"></a>Junho de 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Novo acesso de administração baseada em funções para administradores do Intune   <!-- 1099990 -->  
Uma nova função de administrador de acesso condicional está sendo adicionada para exibir, criar, modificar e excluir políticas de Acesso Condicional do Azure AD. Anteriormente, somente os administradores globais e os administradores de segurança tinham essa permissão. Os administradores do Intune podem receber essa permissão de função para ter acesso às políticas de acesso condicional.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Marcar dispositivos de propriedade corporativa com o número de série <!-- 1215070 -->  
O Intune agora dá suporte ao upload dos números de série de iOS, macOS e Android como Identificadores de Dispositivo Corporativo. No momento, não é possível usar números de série para bloquear o registro de dispositivos pessoais, pois os números de série não são verificados durante o registro. O bloqueio de dispositivos pessoais pelo número de série será liberado em breve.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Novas ações remotas para dispositivos iOS <!-- 854689 -->
Neste lançamento, adicionamos duas novas ações remotas para dispositivos iPad compartilhados, que gerenciam o aplicativo Classroom da Apple:

-   [Fazer logoff do usuário atual](device-logout-user.md) – Faz logoff do usuário atual de um dispositivo iOS escolhido.
-   [Remover usuário](device-remove-user.md) – Exclui um usuário escolhido do cache local de um dispositivo iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Suporte para iPads compartilhados com o aplicativo Sala de aula do iOS <!-- 1044681 -->
Nessa versão, expandimos o suporte do gerenciamento do aplicativo Classroom iOS para incluir os alunos que fazem logon em iPads compartilhados usando suas IDs da Apple gerenciadas.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Alterações para aplicativos internos do Microsoft Intune <!-- 1332306 -->
Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.
No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos. Você pode continuar a atribuir esses aplicativos conforme necessário.
Planejamos adicionar em um lançamento posterior, um método mais fácil para selecionar e atribuir aplicativos internos no Portal do Azure.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Instalação mais fácil de aplicativos do Office 365 <!--- 1121362 --->
O novo tipo de aplicativo do **Office 365 ProPlus** facilitará a atribuição de aplicativos do Office 365 ProPlus 2016 aos dispositivos gerenciados que executam a versão mais recente do Windows 10. Além disso, você também poderá instalar o Microsoft Project e o Microsoft Visio se tiver licenças para eles. Os aplicativos que você desejar serão agrupados e aparecerão como um aplicativo na lista de aplicativos no console do Intune.
Para obter mais informações, consulte [Como adicionar aplicativos do Office 365 para Windows 10](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Suporte para aplicativos offline da Microsoft Store para Empresas <!--- 777044 --->
Aplicativos offline comprados na Microsoft Store para Empresas agora serão sincronizados com o Portal do Azure. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>O Microsoft Teams agora faz parte da lista de AC baseada em aplicativos de aplicativos aprovados   <!-- 1257019 -->
O aplicativo Microsoft Teams para iOS e Android fará parte dos aplicativos aprovados para as políticas de acesso condicional baseado em aplicativos do Exchange e do SharePoint Online. O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários que usam o acesso condicional baseado em aplicativos.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Navegador gerenciado e integração de proxy de aplicativo <!-- 1287310 -->
O Navegador Gerenciado do Intune agora pode ser integrado ao serviço de Proxy de aplicativo do Azure AD para permitir que os usuários acessem os sites da Web internos, mesmo quando estão trabalhando remotamente. Os usuários do navegador simplesmente inserem a URL normalmente e o Managed Browser encaminha a solicitação através do gateway Web do proxy de aplicativo. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Novas definições de configuração de aplicativo para o Intune Managed Browser <!-- 682951 -->
Nesta versão, adicionamos configurações adicionais para o aplicativo Intune Managed Browser para iOS e Android. Agora você pode usar uma política de configuração de aplicativo para configurar a página inicial padrão e os indicadores do navegador.
Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Configurações do BitLocker para Windows 10  <!-- 951707 -->
Agora você pode definir as configurações do BitLocker para dispositivos Windows 10 usando um novo perfil de dispositivo do Intune. Por exemplo, você pode exigir que os dispositivos sejam criptografados e também definir outras configurações que são aplicadas quando o BitLocker é ativado.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Nesta versão, adicionamos novas configurações para o perfil de restrição de dispositivo do Windows 10 nas seguintes categorias:

-  Windows Defender
-  Celular e conectividade
-  Experiência na tela bloqueada
-  Privacidade
-  Pesquisar
-  Destaque do Windows
-  Navegador Microsoft Edge

Para obter mais informações sobre as configurações do Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>O aplicativo de Portal da Empresa para Android agora tem uma nova experiência do usuário final para as Políticas de Proteção do Aplicativo <!--1305217-->
Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**. A intenção é impedir que os usuários finais passem desnecessariamente pelo processo de inscrição quando eles só precisam acessar os aplicativos que dão suporte a Políticas de Proteção do Aplicativo, um recurso de gerenciamento de aplicativo móvel do Intune. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569-->
De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo. Esta ação remove o dispositivo do gerenciamento do Intune para que o aplicativo possa ser removido do dispositivo pelo usuário. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) e na [documentação do usuário final do Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505-->
O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703). Isso reduzirá o problema de atraso das instalações de aplicativos durante o estado de "Sincronização Pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938--->
O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados. A nova experiência fornece instruções passo a passo que guiam o usuário pelo processo de inscrição no Azure Active Directory (exigido para recursos de Acesso Condicional) e inscrição de MDM (exigido para os recursos de gerenciamento de dispositivo). A experiência guiada estará acessível na home page do Portal da Empresa. Os usuários podem continuar a usar o aplicativo se não concluírem o registro e inscrição, mas enfrentarão uma funcionalidade limitada.

Esta atualização só fica visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Os consoles de administrador do Microsoft Intune e do Acesso Condicional estão disponíveis
Anunciamos a disponibilidade geral do novo Intune nos consoles de administrador do Portal do Azure e do Acesso Condicional. Por meio do Intune no Portal do Azure, agora você pode gerenciar todas as funcionalidades MAM e MDM do Intune em uma única experiência de administrador consolidada e aproveitar o agrupamento e direcionamento do Azure AD. O acesso condicional no Azure reúne funcionalidades avançadas no Azure AD e no Intune em um único console unificado. Além disso, de uma experiência administrativa, a migração para a plataforma Azure permite o uso de navegadores modernos.

O Intune agora está visível sem o rótulo **versão prévia** no Portal do Azure em portal.azure.com.

No momento, nenhuma ação é necessária para os clientes existentes, a menos que você tenha recebido uma de uma série de mensagens no centro de mensagens solicitando uma ação de sua parte para que possamos migrar seus grupos. Talvez você também tenha recebido um aviso do centro de mensagens informando que a migração está levando mais tempo devido a bugs no nosso lado. Continuaremos trabalhando incessantemente para migrar os clientes afetados.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS
Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS
Os usuários de dispositivos iOS poderão ver nosso novo seletor de conta ao entrarem no Portal da Empresa, caso usem suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft. Para saber mais, veja [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

## <a name="may-2017"></a>Maio de 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950-->
Agora você pode alterar a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. No console do Configuration Manager, [altere a autoridade de MDM](/sccm/mdm/deploy-use/change-mdm-authority) em Definir como Configuration Manager (híbrido), como Microsoft Intune (autônomo) ou vice-versa.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notificação aprimorada para PINs de inicialização do Samsung Knox <!--1087143-->
Quando os usuários finais precisarem definir um PIN de inicialização em dispositivos Samsung Knox para ficarem em conformidade com a criptografia, a notificação exibida para eles os levará para o local exato no aplicativo de Configurações quando a notificação for tocada.  Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Suporte para o ASM (Apple School Manager) com iPad compartilhado <!-- 748864, 770395-->

O Intune agora dá suporte ao uso do ASM (Apple School Manager) no lugar do Programa de registro de dispositivos da Apple para fornecer o registro pronto para uso de dispositivos iOS. A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS). Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> A configuração de iPads Compartilhados para trabalhar com o aplicativo Sala de aula exige configurações de Educação do iOS no Azure que ainda não estão disponíveis.  Essa funcionalidade será adicionada em breve.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Fornecer assistência remota para dispositivos Android usando o TeamViewer <!-- 675418 -->

O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android. Para obter mais informações, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Novas condições de políticas de proteção de aplicativo para MAM <!-- 679864 -->

Agora você pode definir um requisito para o MAM sem os usuários do registro, que impõe as seguintes políticas:

- Versão mínima do aplicativo
- Versão mínima do sistema operacional
- Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)

Esse recurso está disponível no Android e no iOS. O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune. No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK. O usuário não poderá acessar o aplicativo direcionado se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos três diferentes níveis mencionados acima. Neste ponto, o usuário poderá remover sua conta (para aplicativos de várias identidades), fechar o aplicativo ou atualizar a versão do sistema operacional ou do aplicativo.

Defina também outras configurações para fornecer uma notificação sem bloqueio que recomenda uma atualização do sistema operacional ou do aplicativo. Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.

Para obter mais informações, consulte [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md) e [Configurações da política de proteção de aplicativo do Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Definir as configurações de aplicativo para o Android for Work <!-- 621621 -->
Alguns aplicativos Android da loja dão suporte a opções de configuração gerenciada que permitem a um administrador de TI controlar como um aplicativo é executado no perfil de trabalho. Com o Intune, agora você pode exibir as configurações com suporte em um aplicativo e defini-las no Portal do azure com um designer de configuração ou um editor de JSON. Para obter mais informações, consulte [Usar configurações de aplicativo para o Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nova funcionalidade de configuração de aplicativo para MAM sem registro <!-- 677969 -->
Agora você pode criar políticas de configuração de aplicativo por meio do MAM sem um canal de registro. Esse recurso é equivalente às políticas de configuração de aplicativo disponíveis na configuração de aplicativo do MDM (gerenciamento de dispositivo móvel). Para obter um exemplo de configuração de aplicativo que usa o MAM sem registro, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Configurar listas de permissões e bloqueios de URLs para o Managed Browser <!-- 682960 -->
Agora você pode configurar uma lista de permissões e bloqueios de domínios e URLs para o Intune Managed Browser usando definições de configuração de aplicativo no portal do Azure. Essas configurações podem ser definidas independentemente de estarem sendo usadas em um dispositivo gerenciado ou não gerenciado. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Exibição de assistência técnica da política de proteção de aplicativo <!-- 1069473 -->
Os usuários da assistência técnica de TI agora podem verificar o status da licença do usuário e o status dos aplicativos da política de proteção de aplicativo atribuídos aos usuários na folha Solução de Problemas. Para obter detalhes, consulte [Solução de problemas](./help-desk-operators.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Controlar visitas ao site em dispositivos iOS <!-- 723832 -->
Agora você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois seguintes métodos:

- Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.

- Permita que apenas sites especificado sejam acessados pelo navegador Safari. Para cada site que você especificar são criados indicadores no Safari.

Para obter mais informações, consulte [Configurações de filtro de conteúdo da Web para dispositivos iOS](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 -->
Para aplicativos implantados em perfis de trabalho de dispositivos Android for Work, agora é possível configurar o estado de permissões em aplicativos individuais.  Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.  Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone. Esse recurso permite definir permissões em nome do usuário final.  É possível configurar permissões para a) negar automaticamente sem notificar o usuário; b) aprovar automaticamente sem notificar o usuário ou c) solicitar que o usuário aceite ou recuse. Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definir PIN específico do aplicativo para dispositivos Android for Work <!-- 728976, 1102534 -->
Dispositivos Android 7.0 e superior com um perfil de trabalho gerenciados como um dispositivo Android for Work possibilitam ao administrador definir uma política de senha que se aplica somente aos aplicativos no perfil de trabalho.  As opções incluem:

- Definir apenas uma política de senha em todo o dispositivo – essa é a senha que o usuário deve usar para desbloquear seu dispositivo inteiro.
- Definir apenas uma política de senha de perfil de trabalho – os usuários deverão inserir uma senha sempre que um aplicativo for aberto no perfil de trabalho.
- Definir uma política de dispositivo e de perfil de trabalho – o administrador de TI tem a opção de definir uma política de senha de dispositivo e uma política de senha de perfil de trabalho em diferentes níveis (por exemplo, um PIN de quatro dígitos para desbloquear o dispositivo, mas um PIN de seis dígitos para abrir um aplicativo de trabalho).

Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Isso está disponível somente no Android 7.0 e superior.  Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Novas configurações para dispositivos Windows 10 <!-- 978585 -->
Adicionamos novas [configurações de restrição de dispositivos Windows](device-restrictions-windows-10.md) que controlam recursos como vídeos sem fio, descoberta de dispositivo, alternância de tarefas e mensagens de erro do cartão SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Atualizações da configuração de certificado <!-- 918991 and 823198 -->
Ao criar um perfil de certificado SCEP, em <strong>Formato do nome da entidade</strong>, a opção <strong>Personalizado</strong> está disponível para dispositivos iOS, Android e Windows. Antes dessa atualização, o campo <strong>Personalizado</strong> estava disponível apenas para dispositivos iOS. Para obter mais informações, consulte [Criar perfil de certificado SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile).

Ao criar um perfil de certificado PKCS, em **Nome alternativo da entidade**, o **Atributo personalizado do Azure AD** está disponível. A opção **Departamento** fica disponível quando você seleciona **Atributo personalizado do Azure AD**. Para obter mais informações, confira [Criar um perfil de certificado PKCS](certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Configurar vários aplicativos que podem ser executados quando um dispositivo Android está no modo de quiosque <!-- 662059 -->
Anteriormente, quando um dispositivo Android estava no modo de quiosque, era possível configurar apenas um aplicativo que tinha permissão para ser executado. Agora é possível configurar vários aplicativos usando a ID do aplicativo, a URL da loja ou selecionando um aplicativo Android já gerenciado. Para obter mais informações, consulte [Configurações do modo de quiosque](device-restrictions-android.md#kiosk).



## <a name="april-2017"></a>Abril de 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Suporte para gerenciamento do aplicativo Sala de Aula da Apple
Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads. Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.
Para obter detalhes, confira [Definir as configurações de educação do iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->
Agora, os aplicativos Android na Play Store, que são compatíveis com opções de configuração gerenciada, podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nova política de Android para PINs complexos <!-- 722069 -->
Agora, você pode definir um tipo de [senha](device-restrictions-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Suporte adicional para dispositivos Android for Work
- **Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 -->

  Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 -->

  Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

Para saber mais, confira [Restrições de dispositivo para Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->
Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](lob-apps-ios.md) (arquivos .ipa) e [Android](lob-apps-android.md) (arquivos .apk) a usuários ou dispositivos.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](home-screen-settings-ios.md). Essa política altera o layout da Tela inicial, mas não implanta nenhum aplicativo.

- **Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](air-print-settings-ios-macos.md) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](airplay-settings-ios.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão. Para obter mais informações, consulte [Ativar o modo perdido em dispositivos iOS](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->
Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](app-notification-settings-ios.md) para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->
Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->
Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](device-restrictions-ios.md#domains):

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 -->
Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->
Agora você pode [sincronizar os livros](vpp-apps-ios.md) adquiridos na loja de programa adquirido por volume da Apple com o Intune e atribuí-los aos usuários.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gerenciamento de vários usuários para dispositivos Samsung Knox Standard <!-- 971988 -->
Agora há suporte para dispositivos que executam o Samsung Knox Standard para o [gerenciamento de vários usuários](android-enroll.md) pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e obtêm as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->
Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](device-restrictions-windows-10.md), como suporte adicional ao navegador Microsoft Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->
Adicionamos suporte para o [gerenciamento de vários usuários](windows-enroll.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Começar do zero para PCs com Windows 10<!-- 1004830 -->
Agora há uma [nova ação de dispositivo para começar do zero](device-fresh-start.md) disponível em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->
Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](edition-upgrade-configure-windows-10.md) para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->
Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para o logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte para cenários de autoatendimento e de Portal da Empresa no momento.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 -->
Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal de solução de problemas de suporte técnico <!-- 907448 -->
O novo [portal de solução de problemas](help-desk-operators.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

## <a name="march-2017"></a>Março de 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Suporte para o Modo Perdido do iOS<!--431695-->
Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**. Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.

O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido. Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.

O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](device-management.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->
Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->
Agora você pode atribuir aplicativos de linhas de negócios da loja para os usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="new-compliance-reports---846671--"></a>Novos relatórios de conformidade <!--846671-->
Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários. Você pode exibir informações sobre

- Estado de conformidade geral de dispositivos
- Estado de conformidade para uma configuração individual
- Estado de conformidade para uma política individual

Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as políticas que afetam esse dispositivo.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal do Azure. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


## <a name="february-2017"></a>Fevereiro de 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](device-enrollment.md).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Exibir todas as ações em dispositivos gerenciados <!--677150-->
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Exibir categorias de dispositivos <!--814654-->
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Definir as configurações do Windows Update para Empresas <!--776716-->

O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10. Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](windows-update-for-business-configure.md).
