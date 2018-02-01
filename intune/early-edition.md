---
title: "Edição antecipada"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d4bcabc4d1af4554a3e3bea875be45f9376b4ef7
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>A edição antecipada do Microsoft Intune – fevereiro de 2018

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


<!-- 1802 start -->


### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 -->

O Intune dará suporte para o registro de dispositivos de até 100 contas diferentes do DEP (Programa de registro de dispositivos) da Apple ou do Apple School Manager. Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Relatórios de status de ameaça e status da integridade do Windows Defender <!--854704 -->

Compreender o status da integridade e das ameaças do Windows Defender é essencial para gerenciar computadores Windows.  O Intune adicionará novos relatórios e ações ao status e à integridade do agente do Windows Defender. Usando um relatório de acúmulo de status na carga de trabalho de Conformidade do Dispositivo, você poderá ver os dispositivos que precisam de:

- atualização de assinatura
- reinício
- intervenção manual
- verificação completa
- outros estados de agente que requerem intervenção

Em alguns casos, ações de correção remota podem ser adotadas, como disparar uma atualização de assinatura.  O relatório também indica o número de computadores cujo status relatado é **Limpo**.

Um relatório de análise para cada categoria de status lista os computadores individuais que precisam de atenção ou aqueles cujo estado relatado é **Limpo**.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Exceções de protocolo para aplicativos <!--1035509 eeready-->

Você poderá criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune para abrir aplicativos não gerenciados específicos. Esses aplicativos devem ser confiáveis para a TI. Exceto pelas exceções que você criar, a transferência de dados ainda ficará restrita a aplicativos gerenciados pelo Intune quando sua política de transferência de dados estiver definida como **somente aplicativos gerenciados**. É possível criar as restrições usando protocolos (iOS) ou pacotes (Android).

Por exemplo, é possível adicionar o pacote do Webex como uma exceção à política de transferência de dados de MAM. Isso permitirá que links do Webex em uma mensagem de email gerenciada do Outlook sejam abertos diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>Personalize os temas do Portal da Empresa com códigos hexadecimais <!--1049561 eeready-->

Você poderá personalizar a cor do tema nos aplicativos do Portal da Empresa usando códigos hexadecimais. Ao inserir o código hexadecimal, o Intune determinará a cor do texto que fornece o maior nível de contraste entre a cor do texto e a cor da tela de fundo segundo os [padrões WCAG 2.0](http://www.w3.org/TR/WCAG20). É possível visualizar a cor do texto e o logotipo da empresa em relação à cor em **Aplicativos móveis** > **Portal da Empresa**. 

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Selecione as categorias de dispositivo usando as configurações de Acesso Corporativo ou de Estudante <!-- 1058963 --> 
Se você tiver habilitado o [mapeamento do grupo de dispositivos](https://docs.microsoft.com/en-us/intune/device-group-mapping), os usuários no Windows 10 receberão uma solicitação para selecionar uma categoria de dispositivo após o registro por meio do botão **Conectar** em **Configurações** > **Contas** > **Acesso corporativo ou de estudante** ou durante a configuração inicial pelo usuário.

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Novas configurações do Windows Defender Credential Guard adicionadas às configurações do Endpoint Protection <!--1102252 --> 

Novas configurações do [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] serão adicionadas à **Configuração do dispositivo** > **Perfis** > **Endpoint Protection**. As configurações a seguir serão adicionadas: 

- Nível de Segurança da Plataforma: especifique se o Nível de Segurança da Plataforma está habilitado na próxima reinicialização. A segurança baseada em virtualização requer a Inicialização Segura. A segurança baseada em virtualização pode, opcionalmente, ser habilitada com o uso de proteções de DMA (acesso direto à memória). Proteções de DMA exigem suporte de hardware e serão habilitadas somente em dispositivos configurados corretamente.
- Segurança baseada em virtualização: especifique se a segurança baseada em virtualização será habilitada na próxima reinicialização. 
- Windows Defender Credential Guard: ative o Credential Guard com a segurança baseada em virtualização para ajudar a proteger as credenciais na próxima reinicialização quando o Nível de Segurança de Plataforma com Inicialização Segura e a Segurança Baseada em Virtualização estiverem habilitadas. As opções disponíveis incluem **Desabilitada**, **Habilitada com o bloqueio UEFI**, **Habilitada sem bloqueio** e **Não configurada**. 
  - A opção "Desabilitada" desativará o Credential Guard remotamente se ele estiver habilitado com a opção "Habilitada sem bloqueio".

  - A opção "Habilitada com o bloqueio UEFI" garante que o Credential Guard não possa ser desabilitado com a chave do Registro ou usando a Política de Grupo. Para desabilitar o Credential Guard após usar essa configuração, você precisa definir a Política de Grupo como "Desabilitada" e remover a funcionalidade de segurança em cada computador, com um usuário presente fisicamente, para limpar a configuração persistente na UEFI. Enquanto a configuração da UEFI persistir, o Credential Guard estará habilitado.

  - A opção "Habilitada sem bloqueio" permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, pelo menos, o Windows 10 (versão 1511).

  - A opção "Não configurada" deixa a configuração de política indefinida. A Política de Grupo não grava a configuração de política no Registro e, por isso, não tem impacto sobre computadores ou usuários. Se houver uma configuração atual no registro, ela não será modificada.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>Sincronize e implante aplicativos em pacotes esparsos na Windows Store para Empresas <!--1222672 -->
Aplicativos offline comprados na Windows Store para Empresas serão sincronizados com o Portal do Intune. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. Aplicativos offline são instalados pelo Intune, e não pela loja.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Redefina senhas de dispositivos Android O <!-- 1238299 -->
Você poderá redefinir as senhas de dispositivos Android O registrados. Quando você envia uma solicitação de "Redefinir senha" a um dispositivo Android O, ele define uma nova senha de desbloqueio de dispositivo ou um desafio de perfil gerenciado para o usuário atual. A senha ou o desafio é enviado, dependendo de o dispositivo ter um proprietário do perfil ou um proprietário do dispositivo, e entra em vigor imediatamente.

### <a name="local-device-security-option-settings----1251887---"></a>Configurações de opção de segurança do dispositivo local <!-- 1251887 -->
Você poderá habilitar configurações de segurança em dispositivos Windows 10 usando as novas configurações de Opção de segurança do dispositivo Local. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Novas configurações de impressora para perfis de educação <!-- 1308900 -->

Para perfis de educação, novas configurações estarão disponíveis na categoria **Impressoras**: **Impressoras**, **Impressora padrão**, **Adicionar novas impressoras**. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Novas configurações de privacidade para restrições de dispositivo <!--1308926 -->

Duas novas configurações de privacidade estarão disponíveis para dispositivos:

- **Publicar as atividades do usuário**: defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas.

- **Apenas atividades locais**: defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Suporte do Portal da Empresa para macOS para registros que usam o Gerenciador de Registros do Dispositivo <!-- 1352411 -->

Os usuários poderão usar o Gerenciador de Registros do Dispositivo ao fazer o registro no Portal da Empresa para macOS.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Novas configurações para o navegador Edge <!--1469166 -->

Duas novas configurações estarão disponíveis para dispositivos com o navegador Edge: **Caminho para o arquivo de favoritos** e **Alterações aos favoritos**. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dados criptografados de WIP (Proteção de Informações do Windows) nos resultados da pesquisa do Windows <!-- 1469193 -->

Uma nova configuração na política de WIP (Proteção de Informações do Windows) permitirá que você controle se os dados criptografados por WIP estarão incluídos nos resultados da pesquisa do Windows.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Suporte para aplicativo de LOB (linha de negócios) do macOS <!-- 1473977 -->
O Intune fornecerá a capacidade de instalação aplicativos de LOB para macOS. Aplicativos de LOB são aplicativos em que você forneça o arquivo de instalação e usa o Intune para instalar o aplicativo no dispositivo. Como parte do suporte para aplicativos de LOB para macOS, você precisa usar a Ferramenta de Disposição do Aplicativo do Microsoft Intune para macOS para pré-processar aplicativos de LOB (linha de negócios) para macOS.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Defina configurações de conta do recurso para Surface Hubs <!-- 1475674 -->

Você poderá definir remotamente configurações de conta do recurso para Surface Hubs.

A conta do recurso é usada por um Surface Hub para autenticar no Skype/Exchange a fim de ingressar em uma reunião. Você poderá criar uma conta do recurso exclusiva para que o Surface Hub possa aparecer na reunião como aparece na sala de conferência. Por exemplo, uma conta do recurso como **Sala de conferência B41/6233**.

> [!NOTE]
> - Se deixar os campos em branco, você substituirá os atributos configurados anteriormente no dispositivo.
>
> - As propriedades de conta do recurso podem ser alteradas dinamicamente no Surface Hub. Por exemplo, se a rotação de senha estiver ativada. Portanto, é possível que os valores no console do Azure levem algum tempo para refletir a realidade do dispositivo. 
>
>   Para entender o que está configurado atualmente no Surface Hub, os dados da conta do recurso podem ser incluídas no inventário de hardware (que já tem um intervalo de sete dias) ou como propriedades somente leitura. Para aumentar a precisão após a ação remota ter ocorrido, você pode obter o estado dos parâmetros imediatamente após a execução da ação para atualizar a conta/parâmetros no Surface Hub.

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

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Consultar as restrições de registro por usuário <!-- 1634444 -->
Na folha de solução de problemas, você poderá ver as restrições de registro que estão em vigor para cada usuário.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Configurando um aplicativo móvel do MSI com autoatualização <!-- 1740840 -->
Você poderá configurar um aplicativo móvel do MSI conhecido com autoatualização para ignorar o processo de verificação de versão. Essa funcionalidade é útil para evitar entrar na condição de corrida. Por exemplo, isso pode ocorrer quando o aplicativo que está passando pela atualização automática do desenvolvedor também está sendo atualizado pelo Intune. As duas atualizações podem tentar impor uma versão do aplicativo no cliente do Windows, o que poderia criar um conflito.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Acréscimos às configurações de Segurança do sistema para políticas de conformidade do Windows 10 e posteriores <!--1704133 -->

Acréscimos às configurações de conformidade do Windows 10 estarão disponíveis, incluindo a necessidade de um Firewall e do Windows Defender Antivírus.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos para Android Enterprise <!-- 1813081 -->
Durante a atribuição de aplicativo e após selecionar um tipo de atribuição, o Android Enterprise (anteriormente conhecido como Android for Work) dará suporte à funcionalidade de exclusão.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Conjuntos relacionados de licenças de aplicativo compatíveis com o Intune <!-- 1864117 -->
O Intune no Portal do Azure dará suporte a conjuntos relacionados de licenças de aplicativo como um único item de aplicativo na interface do usuário. Além disso, qualquer aplicativo licenciado offline sincronizado da Microsoft Store para Empresas será consolidado em uma única entrada de aplicativo e qualquer detalhe de implantação dos pacotes individuais será migrado para essa única entrada. Para exibir conjuntos relacionados de licenças de aplicativo no Portal do Azure, selecione **Licenças de aplicativo** na folha **Aplicativos móveis**.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nova opção de autenticação de usuário para registro em massa da Apple <!-- 747625 -->
O Intune dará a você a opção para autenticar dispositivos usando o aplicativo do Portal da Empresa para os seguintes métodos de registro:

- Programa de Registro do Dispositivo da Apple
- Apple School Manager
- Registro do Apple Configurator

Com a opção do Portal da Empresa, a autenticação multifator do Azure Active Directory pode ser imposta sem bloquear esses métodos de registro.

Com a opção do Portal da Empresa, o Intune ignora a autenticação do usuário no Assistente de Configuração do iOS para registro de afinidade de usuário. Isso significa que o dispositivo e registrado inicialmente como um dispositivo sem usuário e, portanto, não receberá as configurações ou políticas dos grupos de usuários. Receberá apenas as configurações e políticas dos grupos de dispositivos. No entanto, o Intune instalará automaticamente o aplicativo do Portal da Empresa no dispositivo. O primeiro usuário a iniciar e entrar no aplicativo do Portal da Empresa será associado ao dispositivo no Intune. Nesse momento, o usuário receberá as configurações e políticas de seus grupos de usuários. A associação do usuário não pode ser alterada sem um novo registro.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 -->
O Intune dará suporte para o registro de dispositivos de até 100 contas diferentes do DEP (Programa de registro de dispositivos) da Apple ou do Apple School Manager. Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Selecione as categorias de dispositivo usando as configurações de Acesso Corporativo ou de Estudante <!-- 1058963 -->
Se você tiver habilitado o [mapeamento do grupo de dispositivos](https://docs.microsoft.com/en-us/intune/device-group-mapping), os usuários no Windows 10 receberão uma solicitação para selecionar uma categoria de dispositivo após o registro por meio do botão **Conectar** em **Configurações** > **Contas** > **Acesso corporativo ou de estudante** ou durante a configuração inicial pelo usuário.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Direcionamento de políticas de conformidade para dispositivos em grupos de dispositivo <!--1307012 -->

Você poderá direcionar políticas de conformidade para usuários em grupos de usuários. Você poderá direcionar políticas de conformidade para dispositivos em grupos de dispositivos.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos <!-- 1406920 -->

Durante a atribuição do aplicativo e após a seleção de um tipo de atribuição, você poderá selecionar os grupos a serem incluídos, bem como os grupos para exclusão.

### <a name="remote-erase-command-support----1438084---"></a>Suporte ao comando "Erase" remoto <!-- 1438084 -->

Os administradores poderão emitir um comando Erase remotamente.

> [!IMPORTANT]
> O comando erase não pode ser revertido e deve ser usado com cuidado.

O comando erase remove todos os dados, incluindo o sistema operacional, de um dispositivo. Também remove o dispositivo do gerenciamento do Intune. Nenhum aviso é emitido para o usuário, e a remoção ocorre imediatamente após a emissão do comando.

Você poderá configurar um PIN de recuperação com seis dígitos. Este PIN pode ser usado para desbloquear o dispositivo apagado e, nesse momento, a reinstalação do sistema operacional começará. Após o início da remoção, o PIN aparecerá em uma barra de status na folha de visão geral do dispositivo no Intune. O PIN permanecerá enquanto a remoção estiver em andamento. Após a conclusão da remoção, o dispositivo desaparecerá totalmente do gerenciamento do Intune. Anote o PIN de recuperação para que a pessoa que estiver restaurando o dispositivo possa usá-lo.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dados criptografados de WIP (Proteção de Informações do Windows) nos resultados da pesquisa do Windows <!-- 1469193 -->

Uma nova configuração na política de WIP (Proteção de Informações do Windows) permitirá que você controle se os dados criptografados por WIP estarão incluídos nos resultados da pesquisa do Windows.

### <a name="website-learning-mode----1631908---"></a>Modo de Aprendizado do Site <!-- 1631908 -->

Intune apresentará uma extensão do modo de Aprendizado do WIP (Proteção de Informações do Windows). Além de exibir informações sobre aplicativos habilitados para WIP, você poderá exibir um resumo dos dispositivos que compartilharam dados de trabalho com sites. Com essas informações, é possível determinar quais sites devem ser adicionados às políticas de WIP de grupo e de usuário.

### <a name="updates-to-compliance-emails---1637547---"></a>Atualizações nos emails de conformidade <!--1637547 -->

Quando um email é enviado para informar sobre um dispositivo sem conformidade, os detalhes sobre o dispositivo sem conformidade serão incluídos. O artigo a seguir será atualizado para indicar esse fato: [Automatizar ações para não conformidade](#actions-for-noncompliance).

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertas para tokens expirados e tokens que expirarão em breve<!-- 1639263 -->
A página de visão geral mostrará alertas para tokens expirados e tokens que expirarão em breve. Ao clicar em um alerta de um único token, você será levado até a página de detalhes do token.  Se você clicar no alerta com vários tokens, será levado até uma lista com todos os tokens e seu status. Os administradores devem renovar seus tokens antes da data de expiração.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impressão remota em uma rede segura <!-- 1709994  -->
As soluções de impressão móvel sem fio do PrinterOn permitirão aos usuários imprimir remotamente de qualquer lugar, e a qualquer momento, em uma rede segura. O PrinterOn será integrado ao SDK do Aplicativo do Intune para iOS e Android. Você poderá direcionar políticas de proteção de aplicativo para esse aplicativo por meio da folha **Políticas de proteção do aplicativo** do Intune no console do administrador. Os usuários finais poderão baixar o aplicativo "PrinterOn para Microsoft" através da Play Store ou iTunes para uso no ecossistema do Intune.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Aprovar o aplicativo do Portal da Empresa para Android for Work <!--1797090 -->
Se sua organização usa o Android for Work, você precisará aprovar manualmente o aplicativo do Portal da Empresa para Android, para que ele continue recebendo atualizações automáticas da loja Google Play gerenciada.

### <a name="faceid-on-ios-devices----1807377---"></a>FaceID em dispositivos iOS <!-- 1807377 -->
Agora, as políticas de proteção de aplicativo do Intune permitem uma configuração que controla o FaceID em dispositivos iOS. Essa configuração é para dispositivos que permitem a funcionalidade FaceID (atualmente, somente no iPhone X). Essa configuração é separada dos controles TouchID permitidos no momento. As organizações têm a capacidade de escolher se desejam confiar no FaceID como um prompt de PIN válido como uma alternativa aos controles TouchID.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>API do Microsoft Graph para Intune – Disponibilidade Geral <!-- 1833289 -->
As APIs do Intune no Microsoft Graph fornecerão acesso programático aos dados e métodos para automatização de ações administrativas para o serviço do Intune.  Com a **Disponibilidade Geral** dessas APIs, clientes, parceiros e desenvolvedores poderão aproveitar as APIs para integração com soluções internas ou comerciais relacionadas ao suporte, ou que exigem o suporte, do Intune ou de outros serviços da Microsoft disponíveis por meio do Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Revogação de aplicativos do Programa de Compra por Volume do iOS <!-- 820863 -->
Para um determinado dispositivo que tem um ou mais aplicativos VPP (Programa de Compra por Volume) do iOS, você poderá revogar a licença do aplicativo com base no dispositivo associada ao dispositivo. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. Para saber mais, confira [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Revogar licenças para um token de Programa de Compra por Volume do iOS<!-- 820870 -->
Você poderá revogar a licença de todos os aplicativos VPP (Programa de Compra por Volume) do iOS para um determinado Token de VPP.

### <a name="new-ios-device-action------1244701---"></a>Nova ação do dispositivo iOS <!-- 1244701 -->
Você pode desligar os dispositivos supervisionados com o iOS 10.3. Essa ação desliga o dispositivo imediatamente sem avisar o usuário final. A ação **Desligar (somente supervisionado)** pode ser encontrada nas propriedades do dispositivo quando você seleciona um dispositivo na carga de trabalho **Dispositivo**.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>O Intune fornece a operação de Movimentação da Conta <!-- 1573558, 1579830 -->
A **Movimentação da Conta** migra um locatário da ASU (Unidade de Escala do Azure) para outra. A **Movimentação da Conta** pode ser usada para os cenários iniciados pelo cliente, quando você liga para a equipe de suporte do Intune solicitando-a, e também pode ser um cenário controlado pela Microsoft, no qual a Microsoft precisa fazer ajustes no serviço no back-end. Durante a **Movimentação da Conta**, o locatário entra no modo somente leitura (ROM). As operações de serviço como inscrever, renomear dispositivos, atualizar status de conformidade falharão durante o período de ROM.



<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **integrado** tornará mais fácil para você criar e atribuir os aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>A resolução de conflitos de atribuição foi alterada para aplicativos da iOS store <!-- 1480316 -->
Os usuários finais podem perceber alguma alteração na disponibilidade de aplicativos iOS store. No momento, um aplicativo que foi atribuído a dois grupos com um conflito entre **Necessário e Disponível** e **Não Aplicável**, é resolvido para **Necessário e Disponível**. Com a alteração, um aplicativo com este conflito é resolvido para **Não Aplicável**.

A alteração elimina a confusão quando um aplicativo é atribuído a vários grupos com propósitos de aplicativo diferentes.

Se você gostaria de ter seu aplicativo disponível no Portal do Operador de informações e no Portal da Empresa antes do lançamento do serviço em novembro, você tem duas opções:

1. Remover a atribuição **Não Aplicável** de seu grupo.
2. Criar um novo grupo que não inclui membros com a finalidade **Necessário e Disponível** atribuída e atribuir esse grupo como **Não Aplicável**.

Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

> [!Note]
> Após o lançamento você não poderá exibir ou modificar atribuições de aplicativo de Gerenciamento de Dispositivo Móvel (MDM) no console do Intune clássico. No entanto, você pode usar o console do Azure ou a API do Graph Intune para fazer atribuições de seu aplicativo.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurar um PIN de aplicativo iOS <!-- 1586774 -->
Em breve, você poderá exigir um PIN para aplicativos iOS determinados. Você pode configurar o requisito e a data de vencimento do PIN em dias por meio do portal do Azure. Quando necessário, um usuário deverá definir e usar um novo PIN antes de receber o acesso a um aplicativo iOS. Apenas os aplicativos iOS que têm a proteção de aplicativo habilitada com o SDK de Aplicativo do Intune oferecerão suporte a esse recurso.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!--1412866-->

Será lançada uma atualização principal da experiência do usuário para o aplicativo Portal da Empresa para iOS. A atualização apresentará uma reformulação visual completa, incluindo uma aparência modernizada com melhorias de acessibilidade e usabilidade. Todas as funcionalidades atuais do Portal da Empresa para iOS serão mantidas.

Estamos oferecendo uma versão de pré-lançamento do aplicativo Portal da Empresa para iOS atualizado por meio do programa Apple TestFlight para que você use e forneça comentários. Inscreva-se em https://aka.ms/intune_ios_cp_testflight para obter acesso ao TestFlight. 

![imagens chamativas do novo aplicativo portal da empresa para ios](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirecionando usuários do macOS para nosso novo aplicativo do Portal da Empresa <!--1380728-->   
Quando um usuário final fizer o logon no site do Portal da Empresa para registrar seu dispositivo macOS, ele será direcionado a baixar o novo aplicativo do Portal da Empresa para macOS a fim de concluir o processo. Isso ocorre em dispositivos macOS usando OS X El Capitan 10.11 ou superior. 


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Suporte do Intune Managed Browser para iOS e Android <!-- 1374196 -->
A partir de outubro de 2017, o aplicativo do Intune Managed Browser no aplicativo do Android oferecerá suporte apenas a dispositivos que executam o Android 4.4 e versões posteriores. O aplicativo Intune Managed Browser no iOS oferecerá suporte apenas a dispositivos que executam o iOS 9.0 e versões posteriores. Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais com dispositivos Android recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."



## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.



### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


