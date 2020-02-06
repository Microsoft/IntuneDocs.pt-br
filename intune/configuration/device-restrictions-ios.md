---
title: Configurações de dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione, defina ou crie configurações em dispositivos iOS para restringir recursos, o que inclui definir os requisitos de senha, controlar a tela bloqueada, usar aplicativos internos, adicionar aplicativos aprovados ou restritos, lidar com dispositivos Bluetooth, conectar-se à nuvem para backup e armazenamento, habilitar o modo de quiosque, adicionar domínios e controlar como os usuários interagem com o navegador da Web Safari no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/13/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f99479200e66b080e107475f0a031c5756da6051
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754568"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo iOS e iPadOS para permitir ou restringir recursos usando o Intune

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos iOS e iPadOS. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, permitir ou restringir aplicativos específicos e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos iOS.

> [!TIP]
> Essas configurações usam as configurações de MDM da Apple. Para obter mais informações sobre essas configurações, confira [Configurações de gerenciamento de dispositivo móvel da Apple](https://support.apple.com/guide/mdm/welcome/web) (abre o site da Apple).

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de configuração de restrições de dispositivo](../device-restrictions-configure.md).

> [!NOTE]
> Essas configurações se aplicam a diferentes tipos de registro, com algumas configurações sendo aplicadas a todas as opções de registro. Para obter mais informações sobre os diferentes tipos de registro, confira [Registro do iOS](../ios-enroll.md).

## <a name="general"></a>Geral

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: Todos os tipos de registro

- **Compartilhar dados de uso**: Escolha **Bloquear** para impedir o dispositivo de enviar dados de diagnóstico e uso para a Apple. **Não configurado** (padrão) permite que esses dados sejam enviados.

- **Captura de tela**: Escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo. No iOS 9.0 e mais recente, essa opção também bloqueia gravações de tela. **Não configurado** (padrão) permite que o usuário capture o conteúdo da tela como uma imagem ou um vídeo.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Certificados TLS não confiáveis**: Escolha **Bloquear** para impedir certificados TLS não confiáveis no dispositivo. **Não configurado** (padrão) permite certificados TLS.
- **Bloquear atualizações over-the-air do PKI**: **Bloquear** impede que os usuários recebam atualizações de software, a menos que o dispositivo esteja conectado a um computador. **Não configurado** (padrão): permite que um dispositivo receba atualizações de software sem estar conectado a um computador.
- **Limitar o acompanhamento de anúncio**: Escolha **Limitar** para desabilitar o identificador de publicidade do dispositivo. **Não configurado** (padrão) o mantém habilitado.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Modificação das configurações de envio de diagnósticos**: a opção **Bloquear** impede o usuário de alterar as configurações de envio de diagnóstico e análise do aplicativo em **Diagnóstico e Uso** (Configurações do dispositivo). **Não configurado** (padrão) permite que o usuário altere as configurações do dispositivo.

  Para usar essa configuração, defina a configuração **Compartilhar dados de uso** como **Bloquear**.

  Esse recurso aplica-se a:  
  - iOS 9.3.2 e mais recente

- **Observação de tela remota pelo aplicativo Classroom**: Escolha **Bloquear** para impedir o aplicativo Classroom de exibir remotamente a tela no dispositivo. **Não configurado** (padrão) permite que o aplicativo Classroom da Apple exiba a tela.

  Para usar essa configuração, defina a configuração **Captura de tela** como **Bloquear**.

  Esse recurso aplica-se a:  
  - iOS 9.3 e versões mais recentes

- **Observação da tela não solicitada pelo aplicativo Classroom**: Se essa opção é definida como **Permitir**, os professores podem observar silenciosamente a tela dos dispositivos iOS dos alunos usando o aplicativo Classroom sem o conhecimento deles. Os dispositivos de alunos registrados em uma aula por meio do aplicativo Classroom concedem automaticamente a permissão ao professor do curso. **Não configurado** (padrão) impede esse recurso.

  Para usar essa configuração, defina a configuração **Captura de tela** como **Bloquear**.

- **Confiança em aplicativos empresariais**: Escolha **Bloquear** para remover o botão **Confiar em Desenvolvedor Empresarial** em Configurações > Geral > Perfis e Gerenciamento de Dispositivos no dispositivo. **Não configurado** (padrão) permite que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Modificação de conta**: Quando essa opção é definida como **Bloquear**, o usuário não pode atualizar as configurações específicas do dispositivo no aplicativo de configurações do iOS. Por exemplo, o usuário não pode criar novas contas de dispositivo ou alterar o nome de usuário ou a senha. **Não configurado** (padrão) permite que os usuários alterem as configurações.

  Esse recurso também se aplica às configurações acessíveis pelo aplicativo Ajustes do iOS, como Mail, Contatos, Calendário, Twitter e mais. Esse recurso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo Ajustes do iOS, por exemplo, o aplicativo Microsoft Outlook.

- **Tempo de tela**: escolha a opção **Bloquear** para impedir que os usuários definam suas próprias restrições em Tempo de Tela (configurações do dispositivo). **Não configurado** permite que o usuário configure restrições de dispositivo (como controles parentais ou restrições de privacidade e conteúdo) no dispositivo.

  Essa configuração foi renomeada de **Habilitando restrições nas configurações do dispositivo**. Impacto dessa alteração:  
  
  - iOS 11.4.1 e versões anteriores: **Bloquear** impede que os usuários finais definam suas próprias restrições nas configurações do dispositivo. O comportamento é o mesmo; não há nenhuma alteração para os usuários finais.
  - iOS 12.0 e versões mais recentes: a opção **Bloquear** impede que os usuários finais configurem o próprio **Tempo de Tela** nas configurações do dispositivo (Configurações > Geral > Tempo de Tela), incluindo restrições de conteúdo e privacidade. Dispositivos atualizados para o iOS 12.0 não verão mais a guia Restrições nas configurações do dispositivo (Configurações > Geral > Gerenciamento de Dispositivo > Perfil de Gerenciamento > Restrições). Essas configurações estão no **Tempo de Tela**.
  
- **Uso da opção Apagar todo o conteúdo e as configurações do dispositivo**: escolha a opção **Bloquear** para que os usuários não possam usar a opção Apagar todo o conteúdo e as configurações no dispositivo. **Não configurado** (padrão) fornece aos usuários acesso a essas configurações.
- **Modificação do nome do dispositivo**: Escolha **Bloquear** para que o nome do dispositivo não possa ser alterado. **Não configurado** (padrão) permite que o usuário altere o nome do dispositivo.
- **Modificação das configurações de notificação**: Escolha **Bloquear** para que as configurações de notificação não possam ser alteradas. **Não configurado** (padrão) permite que o usuário altere as configurações de notificação do dispositivo.
- **Modificação de papel de parede**: A opção **Bloquear** impede que o papel de parede seja alterado. **Não configurado** (padrão) permite que o usuário altere o papel de parede do dispositivo.
- **Modificação das configurações de confiança de aplicativo empresarial**: A opção **Bloquear** impede o usuário de alterar as configurações de confiança em aplicativos empresariais nos dispositivos supervisionados. **Não configurado** (padrão) permite que o usuário confie em aplicativos que não foram baixados da loja de aplicativos.
- **Alterações no perfil de configuração**: A opção **Bloquear** impede alterações do perfil de configuração no dispositivo. **Não configurado** (padrão) permite que o usuário instale perfis de configuração.
- **Bloqueio de Ativação**: Escolha **Permitir** para habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados. O Bloqueio de Ativação dificulta a reativação de um dispositivo perdido ou roubado.
- **Bloquear a remoção de aplicativo**: Escolha **Bloquear** para impedir os usuários de remover aplicativos. **Não configurado** (padrão) permite que os usuários removam aplicativos do dispositivo.
- **Permitir acessórios USB enquanto o dispositivo estiver bloqueado**: **Permitir** deixa que os acessórios USB troquem dados com um dispositivo que tenha sido bloqueado por mais de uma hora. **Não configurado** (padrão) não atualiza o Modo restrito de USB no dispositivo, e os acessórios USB serão impedidos de transferir dados do dispositivo se estiverem bloqueados por mais de uma hora.
- **Forçar a data e hora automáticas**: A opção **Exigir** força os dispositivos supervisionados a definir a Data e a Hora automaticamente. O fuso horário do dispositivo é atualizado quando o dispositivo está conectado à rede celular ou ao Wi-Fi e com os serviços de localização habilitados.
- **Exigir que os alunos solicitem permissão para sair do curso do Classroom**: A opção **Exigir** força os alunos registrados em um curso não gerenciado que usam o aplicativo Classroom a solicitar a permissão do professor para sair do curso. **Não configurado** (padrão) não força o aluno a pedir permissão.

  Esse recurso aplica-se a:  
  - iOS 11.3 e mais recente

- **Permitir que o Classroom seja bloqueado para um aplicativo e bloqueie o dispositivo sem avisar**: a opção **Habilitar** permite que o professor bloqueie aplicativos ou bloqueie o dispositivo usando o aplicativo Classroom sem avisar o aluno. Bloquear aplicativos significa que o dispositivo pode acessar apenas aplicativos especificados pelo professor. **Não configurado** (padrão) impede que professores bloqueiem aplicativos ou dispositivos usando o aplicativo de Sala de Aula sem avisar o aluno.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Ingressar automaticamente nas aulas do Classroom sem avisar**: a opção **Habilitar** permite automaticamente que os alunos ingressem em uma aula que está no aplicativo Classroom sem avisar o professor. **Não configurado** (padrão) avisa o professor de que alunos desejam ingressar em uma aula que está no aplicativo de Sala de Aula.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Bloquear a criação de VPN**: A opção **Bloquear** impede os usuários de criar definições de configuração de VPN. **Não configurado** (padrão) permite aos usuários criar VPNs no dispositivo.
- **Modificação das configurações do eSIM**: **Bloquear** impede que os usuários removam ou adicionem um plano de celular ao eSIM no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações.

  Esse recurso aplica-se a:  
  - iOS 12.1 e mais recente

- **Adiar atualizações de software**: quando definido como **Não configurado** (padrão), as atualizações de software são exibidas no dispositivo conforme a Apple as libera. Por exemplo, se uma atualização do iOS é lançada pela Apple em uma data específica, essa atualização naturalmente aparece no dispositivo perto da data de lançamento.

  **Habilitar** permite que você atrase quando as atualizações de software são mostradas em dispositivos, de 0 a 90 dias. Essa configuração não controla quando as atualizações são ou não instaladas. 

  - **Atrasar a visibilidade das atualizações do software**: insira um valor de 0 a 90 dias. Quando o atraso expira, os usuários recebem uma notificação para atualizar para a versão mais antiga do sistema operacional que estava disponível quando o atraso foi disparado.

    Por exemplo, se iOS 12.a está disponível no dia **1º de janeiro** e **Atrasar a visibilidade** está definido como **5 dias**, iOS 12.a não é mostrado como uma atualização disponível em dispositivos do usuário final. No **sexto dia** após o lançamento, essa atualização está disponível e os usuários finais podem instalá-la.

    Essa configuração aplica-se a:  
    - iOS 11.3 e mais recente

## <a name="password"></a>Senha

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Senha**: a opção **Exigir** torna necessário que o usuário final insira uma senha para acessar o dispositivo. **Não configurado** (padrão) permite que os usuários acessem o dispositivo sem inserir uma senha.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

> [!IMPORTANT]
> Em dispositivos registrados de usuários, se você definir qualquer configuração de senha, as configurações de **Senhas simples** serão definidas automaticamente como **Bloquear**, e será aplicado um PIN de seis dígitos.
>
> Por exemplo, você define a configuração de **Expiração de senha** e envia por push essa política para os dispositivos registrados pelo usuário. Nos dispositivos, acontece o seguinte:
>
> - A configuração de **Expiração de senha** é ignorada.
> - Senhas simples, como `1111` ou `1234`, não são permitidas.
> - É aplicado um PIN de seis dígitos.

- **Senhas simples**: Escolha **Bloquear** para exigir senhas mais complexas. **Não configurado** permite senhas simples, como `0000` e `1234`.

- **Tipo de senha necessária**: Escolha o tipo de senha exigido por sua organização. Suas opções:
  - **Padrão do dispositivo**
  - **Numérica**
  - **Alfanumérica**
- **Número de caracteres não alfanuméricos na senha**: Insira o número de caracteres de símbolo, como `#` ou `@`, que precisa ser incluído na senha.

- **Comprimento mínimo da senha**: insira o tamanho mínimo que um usuário precisa inserir, entre 4 e 14 caracteres. Em dispositivos registrados pelo usuário, insira um tamanho entre 4 e 6 caracteres.
  
  > [!NOTE]
  > Em dispositivos registrados pelo usuário, os usuários podem definir um PIN que tenha mais de 6 dígitos. No entanto, um máximo de 6 dígitos é imposto no dispositivo. Por exemplo, um administrador define o tamanho mínimo como `8`. Em dispositivos registrados pelo usuário, os usuários só precisam definir um PIN de 6 dígitos. O Intune não força um PIN que tenha mais de 6 dígitos em dispositivos registrados pelo usuário.

- **Número de falhas de início de sessão antes de limpar o dispositivo**: insira o número de falhas de entrada permitido antes do dispositivo ser apagado (entre 4 e 11).
  
  O iOS tem uma segurança interna que pode afetar essa configuração. Por exemplo, o iOS pode atrasar o gatilho da política, dependendo do número de falhas de entrada. Ele também pode considerar a inserção repetida da mesma senha como uma única tentativa. O [guia de segurança do iOS](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) da Apple (abre o site da Apple) é um bom recurso e fornece detalhes mais específicos sobre senhas.
  
- **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**<sup>1</sup>: Insira por quanto tempo o dispositivo permanecerá ocioso antes que o usuário precise inserir novamente sua senha. Se o tempo inserido for maior do que o valor definido no dispositivo, o dispositivo ignorará o tempo inserido por você. Compatível com dispositivos iOS 8.0 e mais recentes.

- **Máximo de minutos de inatividade até a tela ser bloqueada**<sup>1</sup>: Insira o número máximo de minutos de inatividade permitido no dispositivo até a tela ser bloqueada.

  **Opções do iOS**:  

  - **Não configurado** (padrão): o Intune não afeta nessa configuração.
  - **Imediatamente**: a tela é bloqueada após 30 segundos de inatividade.
  - **1**: a tela é bloqueada após 1 minuto de inatividade.
  - **2**: a tela é bloqueada após 2 minutos de inatividade.
  - **3**: a tela é bloqueada após 3 minutos de inatividade.
  - **4**: a tela é bloqueada após 4 minutos de inatividade.
  - **5**: a tela é bloqueada após 5 minutos de inatividade.
    
  **Opções do iPadOS**:  

  - **Não configurado** (padrão): o Intune não afeta nessa configuração.
  - **Imediatamente**: a tela é bloqueada após 2 minutos de inatividade.
  - **2**: a tela é bloqueada após 2 minutos de inatividade.
  - **5**: a tela é bloqueada após 5 minutos de inatividade.
  - **10**: a tela é bloqueada após 10 minutos de inatividade.
  - **15**: a tela é bloqueada após 15 minutos de inatividade.

  Se um valor não se aplicar ao iOS ou ao iPadOS, a Apple usará o *menor* valor mais próximo. Por exemplo, se você inserir `4` minutos, os dispositivos iPadOS usarão `2` minutos. Se você inserir `10` minutos, os dispositivos iOS usarão `5` minutos. Essa é uma limitação da Apple.
  
  > [!NOTE]
  > A interface do usuário do Intune dessa configuração não separa os valores compatíveis com o iOS e o iPadOS. A interface do usuário poderá ser atualizada em uma versão futura.

- **Expiração da senha (dias)** : Insira o número de dias antes que a senha do dispositivo precise ser alterada.
- **Evitar a reutilização de senhas anteriores**: Insira o número de novas senhas que precisam ser usadas até que uma antiga possa ser reutilizada.
- **Desbloquear com Touch ID e Face ID**: escolha **Bloquear** para impedir o uso de uma impressão digital para desbloquear o dispositivo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando estes métodos.

  O bloqueio dessa configuração também impede o uso da autenticação com o Face ID para desbloquear o dispositivo.

  O Face ID se aplica ao:  
  - iOS 11.0 e mais recente

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Modificação de senha**: Escolha **Bloquear** para impedir que a senha seja alterada, adicionada ou removida. As alterações às restrições de senha são ignoradas em dispositivos supervisionados após o bloqueio desse recurso. **Não configurado** (padrão) permite a adição, alteração ou remoção das senhas.

  - **Modificação do Touch ID e do Face ID**: a opção **Bloquear** impede o usuário de alterar, adicionar ou remover impressões digitais do Touch ID e o Face ID. **Não configurado** (padrão) permite que o usuário atualize as impressões digitais TouchID e o Face ID no dispositivo.

    O bloqueio dessa configuração também impede que o usuário altere, adicione ou remova a autenticação com o Face ID.

    O Face ID se aplica ao:  
    - iOS 11.0 e mais recente

- **Bloquear o Preenchimento Automático de senha**: Escolha **Bloquear** para impedir o uso do recurso AutoPreenchimento de Senhas no iOS. Escolher **Bloquear** também tem o seguinte impacto:

  - Os usuários não receberão uma solicitação para usar uma senha salva no Safari ou em qualquer outro aplicativo.
  - As senhas fortes automáticas ficam desabilitadas, e o usuário não recebe sugestões de senhas fortes.

  **Não configurado** (padrão) permite esses recursos.

- **Bloquear solicitações de proximidade de senha**: Escolha **Bloquear** para que o dispositivo de um usuário não solicite senhas de dispositivos próximos. **Não configurado** (padrão) permite essas solicitações de senha.
- **Bloquear compartilhamento de senha**: A opção **Bloquear** impede o compartilhamento de senhas entre dispositivos usando o AirDrop. **Não configurado** (padrão) permite o compartilhamento das senhas.
- **Exigir a autenticação do Touch ID ou do Face ID para o Preenchimento Automático de informações de senha ou de cartão de crédito**: quando definido como **Exigir**, os usuários devem se autenticar usando TouchID ou FaceID antes que informações de senhas ou cartão de crédito possam ser automaticamente preenchidas no Safari e em outros aplicativos. **Não configurado** (padrão) permite aos usuários controlar esse recurso nas configurações do dispositivo.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente
  
<sup>1</sup> Se você definir as configurações **Máximo de minutos de inatividade até o bloqueio da tela** e **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**, elas serão aplicadas em sequência. Por exemplo, se você definir o valor das duas configurações como **5** minutos, a tela desligará automaticamente após cinco minutos e o dispositivo será bloqueado após outros cinco minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo será bloqueado cinco minutos depois que o usuário desligar a tela.

## <a name="locked-screen-experience"></a>Experiência de tela bloqueada

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Acesso ao Centro de Controle quando o dispositivo estiver bloqueado**: Escolha **Bloquear** para impedir o acesso ao aplicativo Centro de Controle quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite que o usuário acesse o aplicativo Centro de Controle quando o dispositivo estiver bloqueado.
- **Notificações quando o dispositivo estiver bloqueado**: A opção **Bloquear** impede o acesso às notificações quando o dispositivo está bloqueado. **Não configurado** (padrão) permite que o usuário acesse as notificações sem desbloquear o dispositivo.
- **Exibição Hoje quando o dispositivo está bloqueado**: A opção **Bloquear** impede o acesso à exibição Hoje quando o dispositivo está bloqueado. **Não configurado** (padrão) permite que o usuário veja a visualização Hoje quando o dispositivo estiver bloqueado.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Notificações da Carteira quando o dispositivo estiver bloqueado**: A opção **Bloquear** impede o acesso ao aplicativo Carteira quando o dispositivo está bloqueado. **Não configurado** (padrão) permite ao usuário acessar o aplicativo Wallet enquanto o dispositivo estiver bloqueado.

## <a name="app-store-doc-viewing-gaming"></a>Loja de Aplicativos, Exibição de Documentos, Jogos

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Exibindo documentos corporativos em aplicativos não gerenciados**: a opção **Bloquear** impede a exibição de documentos corporativos em aplicativos não gerenciados. **Não configurado** (padrão) permite que documentos corporativos sejam exibidos em qualquer aplicativo. Por exemplo, você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como **Bloquear**. Após o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permite mais salvar.


  > [!NOTE]
  > Quando essa configuração é bloqueada, os teclados de terceiros instalados por meio da App Store também são bloqueados.

  - **Permitir que aplicativos não gerenciados leiam contas de contatos gerenciadas**: Quando essa opção é definida como **Permitir**, aplicativos não gerenciados, como o aplicativo Contatos interno do iOS, podem ler e acessar informações de contato em aplicativos gerenciados, incluindo o aplicativo móvel do Outlook. **Não configurado** (padrão) impede a leitura, incluindo a remoção de duplicatas, do aplicativo Contatos interno do dispositivo.  
  
    Essa configuração permite ou impede a leitura de informações de contato. Ela não controla a sincronização de contatos entre os aplicativos.
  
    Para usar essa configuração, defina a configuração **Exibindo documentos corporativos em aplicativos não gerenciados** como **Bloquear**.

  Para obter mais informações sobre essas duas configurações e o impacto delas na sincronização de exportação de contatos do Outlook para o iOS, confira [Dica de suporte: usar as configurações de perfil personalizado do Intune com o aplicativo nativo Contatos do iOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453).

- **Tratar o AirDrop como um destino não gerenciado**: A opção **Exigir** força o AirDrop a ser considerado uma reprodução automática não gerenciada. Isso impede que os aplicativos gerenciados enviem dados usando o Airdrop. 
- **Exibindo documentos não corporativos em aplicativos corporativos**: A opção **Bloquear** impede a exibição de documentos não corporativos em aplicativos corporativos. **Não configurado** (padrão) permite que qualquer documento seja exibido em aplicativos gerenciados corporativos.

  A configuração **Bloquear** também impede a sincronização da exportação de contatos no Outlook para o iOS. Para obter mais informações, confira [Dica de suporte: como habilitar a sincronização de contatos do Outlook para o iOS com controles de MDM do iOS 12](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Exigir a senha da iTunes Store para todas as compras**: a opção **Exigir** exige que o usuário insira a senha da ID da Apple para cada compra no aplicativo ou no iTunes. A opção **Não configurado** (padrão) permite compras sem solicitar uma senha a cada vez.
- **Compras no aplicativo**: Escolha **Bloquear** para impedir compras no aplicativo por meio da loja. **Não configurado** (padrão) permite compras na loja em um aplicativo em execução.
- **Baixar conteúdo da iBook Store sinalizado como 'Erotismo'** : Escolha **Bloquear** para impedir os usuários de baixar uma mídia da iBook Store que esteja marcada como Erotismo. **Não configurado** (padrão) permite que o usuário baixe livros da categoria "Erotismo".
- **Permitir que aplicativos gerenciados gravem contatos em contas de contatos não gerenciadas**: quando essa opção é definida como **Permitir**, os aplicativos gerenciados, como o aplicativo móvel do Outlook, podem salvar ou sincronizar informações de contato, incluindo contatos comerciais e corporativos, no aplicativo Contatos interno do iOS. Quando essa opção é definida como **Não configurado** (padrão), os aplicativos gerenciados não podem salvar informações de contato no aplicativo Contatos interno do iOS no dispositivo nem sincronizar essas informações com ele.
  
  Para usar essa configuração, defina a configuração **Exibindo documentos corporativos em aplicativos não gerenciados** como **Bloquear**.

- **Região de classificação**: Escolha a região de classificação que deseja usar para downloads permitidos. E, em seguida, escolha as classificações permitidas para **Filmes**, **Programas de TV** e **Aplicativos**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **App Store**: A opção **Bloquear** impede o acesso à App Store nos dispositivos supervisionados. **Não configurado** (padrão) permite o acesso.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

  - **Instalação de aplicativos da App Store**: Escolha **Bloquear** para bloquear a App Store na tela inicial do dispositivo. Os usuários finais podem continuar a usar o iTunes ou o Apple Configurator para instalar aplicativos. **Não configurado** (padrão) permite a App Store na tela inicial.
  - **Downloads de aplicativo automáticos**: Escolha **Bloquear** para impedir o download automático de aplicativos comprados em outros dispositivos. Isso não afeta as atualizações dos aplicativos existentes. **Não configurado** (padrão) permite o download dos aplicativos comprados em outros dispositivos iOS para o dispositivo.

- **Conteúdo adulto de música, podcast ou notícias do iTunes**: Escolha **Bloquear** para impedir o conteúdo adulto de música, podcast ou notícias do iTunes. **Não configurado** (padrão) permite ao dispositivo acessar conteúdo classificado como adulto na loja. O iOS 13 e mais recente pode exigir apenas dispositivos supervisionados. 

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Adição de amigos no Game Center**: A opção **Bloquear** impede os usuários de adicionar amigos do Game Center. **Não configurado** (padrão) permite que o usuário adicione amigos ao Game Center.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Game Center**: **Bloqueie** o uso do aplicativo Game Center. **Não configurado** (padrão) permite o uso do aplicativo Game Center no dispositivo.
- **Jogo para vários participantes**: Escolha **Bloquear** para impedir jogos para múltiplos jogadores. **Não configurado** (padrão) permite que o usuário execute jogos para vários participantes no dispositivo.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Acesso à unidade de rede no aplicativo Arquivos**: usando o protocolo SMB, os dispositivos podem acessar arquivos ou outros recursos em um servidor de rede. A opção **Desabilitar** impede o acesso a arquivos em uma unidade SMB de rede. **Não configurado** (padrão) permite o acesso.

  Esse recurso aplica-se a:  
  - iOS e iPadOS 13.0 e mais recente

## <a name="built-in-apps"></a>Aplicativos internos

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Siri**: A opção **Bloquear** impede o acesso à Siri. **Não configurado** (padrão) permite o uso da assistente de voz Siri no dispositivo.
  - **Siri quando o dispositivo estiver bloqueado**: Escolha **Bloquear** para impedir o acesso à Siri quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite o uso da assistente de voz Siri no dispositivo quando ele estiver bloqueado.

- **Avisos de fraude do Safari**: **Exija** a exibição de avisos de fraude no navegador da Web do dispositivo. **Não configurado** (padrão) desabilita esse recurso.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Pesquisa de Destaque para retornar resultados da Internet**: A opção **Bloquear** impede o Spotlight de retornar qualquer resultado de uma pesquisa na Internet. **Não configurado** (padrão) permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.

- **Cookies do Safari**: Escolha como lidar com os cookies no dispositivo. Suas opções:
  - Allow
  - Bloquear todos os cookies
  - Permitir cookies dos sites visitados
  - Permitir cookies do site atual

- **JavaScript do Safari**: A opção **Bloquear** impede a execução de scripts Java no navegador do dispositivo. A opção **Não configurado** (padrão) permite scripts Java.

- **Pop-ups do Safari**: A opção **Bloquear** desabilita o bloqueador de pop-ups no navegador da Web. A opção **Não configurado** (padrão) permite o bloqueador de pop-ups.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Câmera**: Escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não configurado** (padrão) permite o acesso à câmera do dispositivo.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

  - **FaceTime**: Escolha **Bloquear** para impedir o acesso ao aplicativo FaceTime. **Não configurado** (padrão) permite o acesso ao aplicativo FaceTime no dispositivo.

    No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Filtro de profanidade da Siri**: A opção **Exigir** impede que a Siri dite ou use linguagem imprópria.

  Para usar essa configuração, defina a configuração **Siri** como **Bloquear**.

- **Usar a Siri para consultar o conteúdo da Internet gerado pelo usuário**: A opção **Bloquear** impede que a Siri acesse sites para responder a perguntas. **Não configurado** (padrão) permite que a Siri acesse conteúdo gerado pelo usuário na Internet.

  Para usar essa configuração, defina a configuração **Siri** como **Bloquear**.

- **Apple News**: Escolha **Bloquear** para impedir o acesso ao aplicativo Apple News no dispositivo. **Não configurado** (padrão) permite o uso do aplicativo Apple News.
- **iBooks Store**: A opção **Bloquear** impede o acesso à iBooks Store. **Não configurado** (padrão) permite aos usuários procurar e comprar livros na iBooks Store.
- **Aplicativo de mensagens no dispositivo**: a opção **Bloquear** impede que os usuários usem o aplicativo Mensagens no iMessage. Se o dispositivo der suporte a mensagens de texto, o usuário ainda poderá enviar e receber mensagens de texto usando o SMS. A opção **Não configurado** (padrão) permite usar o aplicativo Mensagens para enviar e ler mensagens pela Internet.
- **Podcasts**: A opção **Bloquear** impede os usuários de usar o aplicativo Podcasts. **Não configurado** (padrão) permite o uso do aplicativo Podcasts.
- **Serviço de música**: A opção **Bloquear** reverte o aplicativo Música para o modo clássico e desabilita o serviço de Música. **Não configurado** (padrão) permite o uso do aplicativo Apple Music.
- **Serviço iTunes Radio**: A opção **Bloquear** impede os usuários de usar o aplicativo iTunes Radio. **Não configurado** (padrão) permite o uso do aplicativo iTunes Radio.
- **iTunes Store**: a opção **Não configurado** (padrão) permite o iTunes nos dispositivos. A opção **Bloquear** impede que os usuários usem o iTunes no dispositivo. 

  Esse recurso aplica-se a:  
  - iOS 4.0 e mais recente

- **Buscar meu iPhone**: a opção **Não configurado** (padrão) permite o uso do recurso do aplicativo Buscar para obter a localização aproximada do dispositivo. A opção **Bloquear** impede esse recurso no aplicativo Buscar. 

  Esse recurso aplica-se a:  
  - iOS 13.0 e iPadOS 13.0 e mais recente

- **Buscar meus Amigos**: a opção **Não configurado** (padrão) permite usar o recurso do aplicativo Buscar para encontrar a família e os amigos em um dispositivo Apple ou no iCloud.com. A opção **Bloquear** impede esse recurso no aplicativo Buscar.

  Esse recurso aplica-se a:  
  - iOS 13.0 e iPadOS 13.0 e mais recente

- **Alterações nas configurações do aplicativo Buscar meus amigos**: A opção **Bloquear** impede alterações nas configurações do aplicativo Buscar Amigos. **Não configurado** (padrão) permite que o usuário altere as configurações do aplicativo Buscar meus amigos.

- **Pesquisa de Destaque para retornar resultados da Internet**: A opção **Bloquear** impede o Spotlight de retornar qualquer resultado de uma pesquisa na Internet. **Não configurado** (padrão) permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.

- **Bloquear a remoção de aplicativos do sistema do dispositivo**: A opção **Bloquear** desabilita a capacidade de remover aplicativos do sistema no dispositivo. **Não configurado** (padrão) permite que os usuários removam aplicativos do sistema.

- **Safari**: **Bloqueie** o uso do navegador Safari no dispositivo. **Não configurado** (padrão) permite que os usuários utilizem o navegador Safari.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Preenchimento Automático do Safari**: A opção **Bloquear** desabilita o recurso de preenchimento automático do Safari no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações de preenchimento automático no navegador da Web.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

## <a name="restricted-apps"></a>Aplicativos restritos

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Lista de tipos de aplicativos restritos**: crie uma lista de aplicativos que os usuários não têm permissão para instalar nem usar. Suas opções:

  - **Não configurado** (padrão): não há restrições do Intune. Os usuários têm acesso aos aplicativos que você atribui e aos aplicativos internos.
  - **Aplicativos proibidos**: aplicativos não gerenciados pelo Intune que você não deseja que sejam instalados no dispositivo. Os usuários não são impedidos de instalar um aplicativo proibido. Porém, se um usuário instalar um aplicativo dessa lista, ele será relatado no Intune.
  - **Aplicativos aprovados**: aplicativos que os usuários têm permissão para instalar. Os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente. Os usuários não são impedidos de instalar um aplicativo que não esteja na lista aprovada. Porém, se eles fizerem isso, isso será relatado no Intune.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar** a URL da iTunes App Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` ou `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.

- **Importar** um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app url>, <app name>, <app publisher>`. Ou **exporte** uma lista existente que contenha a lista de aplicativos restritos no mesmo formato.

> [!IMPORTANT]
> Os perfis de dispositivo que usam configurações de aplicativo restrito devem ser atribuídos a grupos de usuários.

## <a name="show-or-hide-apps"></a>Mostrar ou ocultar aplicativos

Aplica-se aos dispositivos que executam o iOS 9.3 ou mais recente.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Lista de tipos de aplicativos**: crie uma lista de aplicativos a serem mostrados ou ocultados. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple apresenta uma lista de [aplicativos internos da Apple](https://support.apple.com/HT208094). Suas opções:

  - **Aplicativos ocultos**: Insira uma lista de aplicativos ocultados dos usuários. Os usuários não podem exibir ou abrir esses aplicativos.
  
    A Apple impede que alguns aplicativos nativos sejam ocultados. Por exemplo, você não pode ocultar os aplicativos **Configurações** ou **Carteira** no dispositivo. A opção [Excluir aplicativos internos da Apple](https://support.apple.com/HT208094) lista os aplicativos que podem ser ocultados.
  
  - **Aplicativos visíveis**: Insira uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

- **URL do Aplicativo**: insira a URL do aplicativo da loja do aplicativo que deseja mostrar ou ocultar. Por exemplo:

  - Para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` ou `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`. 

  - Para adicionar o aplicativo Microsoft Word, insira `https://itunes.apple.com/de/app/microsoft-word/id586447913` ou `https://apps.apple.com/de/app/microsoft-word/id586447913`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.
  
  Para obter mais informações sobre como localizar uma ID do pacote, confira [Como localizar a ID do pacote de um aplicativo iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).

- **ID de Lote de Aplicativo**: insira a [ID de lote](bundle-ids-built-in-ios-apps.md) de aplicativos do aplicativo que você deseja. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple apresenta uma lista de [aplicativos internos da Apple](https://support.apple.com/HT208094).
- **Nome do aplicativo**: insira o nome do aplicativo que você deseja. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple apresenta uma lista de [aplicativos internos da Apple](https://support.apple.com/HT208094).
- **Editor**: insira o editor do aplicativo que você deseja.

Para adicionar aplicativos, você pode:

- **Adicionar**: selecione essa opção para criar sua lista de aplicativos.
- **Importar** um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app url>, <app name>, <app publisher>`. Ou **Exportar** para criar uma lista de aplicativos restritos que você adicionou, no mesmo formato.

## <a name="wireless"></a>Sem fio

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

Observação necessária para Roaming de Dados (dica ou observação importante para ajudar em caso de confusão do cliente): essa configuração não será exibida no perfil de gerenciamento do dispositivo de destino. Isso ocorre porque essa configuração é tratada como uma ação de dispositivo remoto e toda vez que o estado de roaming de dados for alterado no dispositivo, ele se tornará bloqueado novamente pelo serviço do Intune. Mesmo que ele não esteja no perfil de gerenciamento, ele estará funcionando se for exibido como êxito no relatório no console de administração. 
- **Roaming de dados**: Escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** (padrão) permite o roaming de dados quando o dispositivo está em uma rede celular.

  > [!IMPORTANT]
  > Essa configuração é tratada como uma ação de dispositivo remoto. Portanto, ela não é mostrada no perfil de gerenciamento no dispositivo. Toda vez que o status de roaming de dados é alterado no dispositivo, o **Roaming de dados** é bloqueado pelo serviço do Intune. No Intune, se o status do relatório mostrar êxito, saiba que ele está funcionando, mesmo que a configuração não seja mostrada no perfil de gerenciamento no dispositivo.

- **Busca global em segundo plano durante o roaming**: A opção **Bloquear** impede o uso do recurso de busca global em segundo plano durante o roaming na rede celular. **Não configurado** (padrão) permite ao dispositivo buscar dados, como emails, durante roaming em uma rede celular.
- **Discagem de voz**: Escolha **Bloquear** para impedir os usuários de usar o recurso de discagem de voz no dispositivo. **Não configurado** (padrão) permite a discagem por voz no dispositivo.
- **Roaming de voz**: Escolha **Bloquear** para impedir o roaming de voz na rede celular. **Não configurado** (padrão) permite o roaming de voz quando o dispositivo está em uma rede celular.
- **Hotspot pessoal**: A opção **Bloquear** desativa o ponto de acesso pessoal no dispositivo dos usuários a cada sincronização do dispositivo. Essa configuração pode não ser compatíveis com algumas operadoras. **Não configurado** (padrão) mantém a configuração de ponto de acesso pessoal como o padrão definido pelo usuário.

  > [!IMPORTANT]
  > Essa configuração é tratada como uma ação de dispositivo remoto. Portanto, ela não é mostrada no perfil de gerenciamento no dispositivo. Toda vez que o status de hotspot pessoal é alterado no dispositivo, o **Hotspot Pessoal** é bloqueado pelo serviço do Intune. No Intune, se o status do relatório mostrar êxito, saiba que ele está funcionando, mesmo que a configuração não seja mostrada no perfil de gerenciamento no dispositivo.

- **Regras de uso da rede celular (somente aplicativos gerenciados)** : Defina os tipos de dados que poderão ser usados por aplicativos gerenciados quando estiverem em redes celulares. Suas opções:
  - **Bloquear uso de dados da rede celular**: Bloqueie o uso de dados da rede celular para **Todos os aplicativos gerenciados** ou use **Escolher aplicativos específicos**.
  - **Bloquear o uso de dados da rede celular durante o roaming**: Bloqueie o uso de dados da rede celular durante o roaming para **Todos os aplicativos gerenciados** ou use **Escolher aplicativos específicos**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Alterações nas configurações de uso de dados para celular do aplicativo**: Escolha **Bloquear** para impedir alterações nas configurações de uso dos dados da rede celular do aplicativo. **Não configurado** (padrão) permite ao usuário controlar quais aplicativos têm permissão para usar dados de celular.
- **Alterações nas configurações do plano do celular**: a opção **Bloquear** impede que os usuários alterem as configurações no plano de celular. **Não configurado** (padrão) permite que os usuários façam alterações.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Modificação do Hotspot Pessoal pelo usuário**: quando essa opção é definida como **Bloquear**, o usuário não pode alterar a configuração de hotspot pessoal. A opção **Não configurado** (padrão) permite que os usuários finais habilitem ou desabilitem os hotspots pessoais.

  Se você bloquear essa configuração e bloquear a configuração **Hotspot Pessoal**, o hotspot pessoal será desativado.

  Esse recurso aplica-se a:  
  - iOS 12.2 e mais recente

- **Ingressar nas redes Wi-Fi usando somente perfis de configuração**: A opção **Exigir** força o dispositivo a usar somente as redes Wi-Fi configuradas por meio de perfis de configuração do Intune. **Não configurado** (padrão) permite que o dispositivo use outras redes Wi-Fi.

  Quando essa opção é definida como **Exigir**, verifique se o dispositivo tem um perfil de Wi-Fi. Se você não atribuir um perfil de Wi-Fi, essa configuração poderá impedir que o dispositivo se conecte à Internet. Em outras palavras, se esse perfil de restrições de dispositivo for atribuído antes de um perfil de Wi-Fi, o dispositivo poderá ser impedido de se conectar à Internet.
  
  Se ele não puder se conectar, cancele o registro do dispositivo e registre-se novamente com um perfil de Wi-Fi. Em seguida, defina essa configuração como **Exigir** em um perfil de restrições de dispositivo e atribua o perfil ao dispositivo.

- **Wi-Fi sempre ativado**: quando essa opção é definida como **Exigir**, o Wi-Fi fica ativo no aplicativo Configurações. Ele não pode ser desativado em Configurações nem no Centro de Controle, mesmo quando o dispositivo está no modo avião. A opção **Não configurado** (padrão) permite que o usuário controle a ativação ou a desativação do Wi-Fi.

  A definição dessa configuração não impede que os usuários selecionem uma rede Wi-Fi.

  Esse recurso aplica-se a:  
  - iOS e iPadOS 13.0 e mais recente

## <a name="connected-devices"></a>Dispositivos conectados

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Detecção de pulso para um Apple Watch emparelhado**: A opção **Exigir** força um Apple Watch emparelhado a usar a detecção de pulso. Quando exigido, o Apple Watch não exibirá notificações quando não estiver sendo usado. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Exigir uma senha de emparelhamento para solicitações de saída do AirPlay**: **Exija** uma senha de emparelhamento quando o usuário usar o AirPlay para transmitir conteúdo para outros dispositivos Apple. **Não configurado** (padrão) permite que o usuário transmita conteúdo usando AirPlay sem inserir uma senha.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **AirDrop**: A opção **Bloquear** impede o uso do AirDrop no dispositivo. **Não configurado** (padrão) permite o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
- **Emparelhamento do Apple Watch**: A opção **Bloquear** impede o emparelhamento com um Apple Watch. **Não configurado** (padrão) permite que o dispositivo emparelhe com um Apple Watch.
- **Modificação do Bluetooth**: A opção **Bloquear** impede o usuário final de alterar as configurações do Bluetooth no dispositivo. **Não configurado** (padrão) permite que o usuário altere as configurações.
- **Emparelhamento de host para controlar os dispositivos que podem ser emparelhados com um dispositivo iOS**: a opção **Não configurado** (padrão) permite o emparelhamento de host para que administrador possa controlar quais dispositivos podem ser emparelhados com um dispositivo iOS. **Bloquear** impede o emparelhamento do host.
- **Bloquear o AirPrint**: Escolha **Bloquear** para impedir o uso do recurso AirPrint no dispositivo. **Não configurado** (padrão) permite que o usuário use o AirPrint.
  - **Bloquear o armazenamento de credenciais do AirPrint em um Conjunto de chaves**: A opção **Bloquear** impede o uso do armazenamento do Conjunto de Chaves para o nome de usuário e a senha no dispositivo. **Não configurado** (padrão) permite o armazenamento do nome de usuário e senha do AirPrint no aplicativo Keychain.
  - **Exigir um certificado TLS confiável para AirPrint**: A opção **Exigir** força o dispositivo a usar certificados confiáveis para comunicação de impressão do TLS.
  - **Bloquear a descoberta de iBeacon de impressoras AirPrint**: A opção **Bloquear** impede o phishing de beacons Bluetooth mal-intencionados do AirPrint em busca do tráfego de rede. **Não configurado** (padrão) permite a publicidade de impressoras AirPrint no dispositivo.
- **Bloquear a configuração de novos dispositivos próximos**: a opção **Bloquear** desabilita o aviso para configurar novos dispositivos que estão nas proximidades. **Não configurado** (padrão) permite avisos para os usuários conectarem-se a outros dispositivos da Apple nas proximidades.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Acesso a arquivos na unidade USB**: os dispositivos podem se conectar e abrir arquivos em uma unidade USB. A opção **Desabilitar** impede o acesso do dispositivo à unidade USB no aplicativo Arquivos quando um USB está conectado ao dispositivo. A desabilitação desse recurso também impede que os usuários finais transfiram arquivos para uma unidade USB conectada a um iPad. A opção **Não configurado** (padrão) permite o acesso a uma unidade USB no aplicativo Arquivos.

  Esse recurso aplica-se a:  
  - iOS e iPadOS 13.0 e mais recente

## <a name="keyboard-and-dictionary"></a>Teclado e dicionário

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Pesquisa de definição de palavra**: A opção **Bloquear** impede o usuário de realçar uma palavra e, em seguida, pesquisar sua definição no dispositivo. **Não configurado** (padrão): permite o acesso ao recurso de pesquisa de definição.
- **Teclados preditivos**: a opção **Não configurado** (padrão) permite o uso de teclados preditivos para sugerir palavras que talvez o usuário deseje saber. **Bloquear** impede esse recurso.
- **Correção automática**: a opção **Não configurado** (padrão) permite que o dispositivo corrija automaticamente palavras com ortografia incorreta. **Bloquear** impede o uso da correção automática.
- **Verificação ortográfica do teclado**: a opção **Não configurado** (padrão) permite o uso do verificador ortográfico no dispositivo. **Bloquear** permite a correção ortográfica.
- **Atalhos de teclado**: a opção **Não configurado** (padrão) permite o uso de atalhos de teclado no dispositivo. **Bloquear** impede o uso de atalhos de teclado.
- **Ditado**: A opção **Bloquear** impede o usuário de usar a entrada de voz para inserir um texto. **Não configurado** (padrão) permite que o usuário use a entrada por ditado.
- **QuickPath**: a opção **Não configurado** (padrão) permite que os usuários usem o QuickPath, o que permite uma entrada contínua no teclado do dispositivo. Os usuários podem digitar algo passando o dedo pelas chaves para criar palavras. A opção **Bloquear** impede que os usuários usem o QuickPath. 

  Esse recurso aplica-se a:  
  - iOS 13.0 e iPadOS 13.0 e mais recente

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Backup criptografado**: **Exija** essa opção para que os backups de dispositivo sejam criptografados.
- **Sincronização de aplicativos gerenciados com a nuvem**: A opção **Não configurado** (padrão) permite que os aplicativos gerenciados pelo Intune sincronizem dados com a conta do iCloud do usuário. **Bloquear** impede essa sincronização de dados com o iCloud.
- **Bloquear o Backup de Livros da Empresa**: Escolha **Bloquear** para impedir os usuários de fazer backup de livros da empresa. **Não configurado** (padrão) permite que os usuários façam backup desses livros.
- **Bloquear a sincronização de metadados de livros da empresa (anotações e destaques)** : A opção **Bloquear** impede a sincronização de anotações e destaques em livros da empresa. A opção **Não configurado** (padrão) permite a sincronização.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Sincronização do fluxo de fotos com o iCloud**: A opção **Não configurado** (padrão) permite que os usuários habilitem **Meu Fluxo de Fotos** em seus dispositivos para sincronização com o iCloud e disponibilizem as fotos em todos os dispositivos do usuário. **Bloquear** impede a sincronização de fluxo de fotos com o iCloud. O bloqueio desse recurso pode causar perda de dados. 
- **Biblioteca de Fotos do iCloud**: Defina essa opção como **Bloquear** para desabilitar o uso da Biblioteca de Fotos do iCloud para armazenar fotos e vídeos na nuvem. As fotos que não forem totalmente baixadas da Biblioteca de Fotos do iCloud para o dispositivo serão removidas do dispositivo. **Não configurado** (padrão) permite o uso da Biblioteca de Fotos do iCloud.
- **Fluxo de fotos compartilhado**: Escolha **Bloquear** para desabilitar o **Compartilhamento de Fotos do iCloud** no dispositivo. **Não configurado** (padrão) permite a transmissão de fotos compartilhadas.
- **Entrega**: a opção **Não configurado** (padrão) permite que os usuários iniciem o trabalho em um dispositivo iOS e, em seguida, continuem o trabalho iniciado em outro dispositivo iOS ou macOS. **Bloquear** impede o Handoff.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Backup no iCloud**: A opção **Não configurado** (padrão) permite que o usuário faça backup do dispositivo no iCloud. **Bloquear** impede que o usuário faça backup do dispositivo no iCloud.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Bloquear a sincronização de documentos do iCloud**: A opção **Não configurado** (padrão) permite a sincronização de documento e chave-valor com o espaço de armazenamento do iCloud. **Bloquear** impede o iCloud de sincronizar documentos e dados.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

- **Bloquear a sincronização do Conjunto de Chaves do iCloud**: Escolha **Bloquear** para desabilitar a sincronização das credenciais armazenadas no Conjunto de Chaves com o iCloud. **Não configurado** (padrão) permite que os usuários sincronizem essas credenciais.

  No iOS 13.0 em diante, essa configuração exige dispositivos supervisionados.

## <a name="autonomous-single-app-mode"></a>Modo autônomo de aplicativo único

Use essas opções para configurar dispositivos iOS para executar aplicativos específicos no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado. Ele só pode executar esse aplicativo. Por exemplo, adicione um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Nome do aplicativo**: Insira o nome do aplicativo que você deseja.
- **ID de Lote de Aplicativo**: Insira a [ID de lote](bundle-ids-built-in-ios-apps.md) do aplicativo que você deseja.
- **Adicionar**: selecione essa opção para criar sua lista de aplicativos.

Também é possível **Importar** um arquivo CSV com a lista de nomes de aplicativo e suas IDs de pacote. Ou **Exportar** uma lista existente que contém os aplicativos.

## <a name="kiosk"></a>Quiosque

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Aplicativo a ser executado no modo de quiosque**: Escolha o tipo de aplicativos que deseja executar no modo de quiosque. Suas opções:
  - **Não configurado** (padrão): As configurações de quiosque não são aplicadas. O dispositivo não é executado no modo de quiosque.
  - **Aplicativo da Loja**: Insira a URL de um aplicativo na iTunes App Store.
  - **Aplicativo Gerenciado**: Escolha um aplicativo que você adicionou ao Intune.
  - **Aplicativo Interno**: Insira a [ID de lote](bundle-ids-built-in-ios-apps.md) do aplicativo nativo.

- **Toque assistencial**: **Exija** a configuração de acessibilidade Toque assistencial no dispositivo. Esse recurso ajuda os usuários proporcionando gestos na tela que podem ser difíceis. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Inverter cores**: **Exija** a configuração de acessibilidade Inverter Cores, para que os usuários com deficiências visuais possam alterar a exibição da tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Áudio mono**: **Exija** a configuração de acessibilidade Áudio mono no dispositivo. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Controle de voz**: a opção **Exigir** habilita o controle de voz no dispositivo e permite que os usuários controlem totalmente o sistema operacional usando comandos da Siri. A opção **Não configurado** desabilita o controle de voz no dispositivo.

  Essa configuração aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e mais recente
  
  > [!TIP]
  > Se você tiver aplicativos LOB disponíveis para a sua organização e eles não estiverem prontos para o **Controle de Voz** no primeiro dia de lançamento do iOS 13.0, recomendamos que você mantenha essa configuração como **Não configurado**.

- **VoiceOver**: **Exija** a configuração de acessibilidade VoiceOver no dispositivo para ler o texto na tela em voz alta. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Zoom**: **Exija** a configuração de Zoom no dispositivo para permitir que os usuários usem o toque para ampliar a tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Bloqueio automático**: a opção **Bloquear** impede o bloqueio automático do dispositivo. **Não configurado** permite o uso desse recurso.
- **Botão de toque**: A opção **Bloquear** desabilita a opção de alternar toque (mudo) no dispositivo. **Não configurado** permite o uso desse recurso.
- **Rotação da tela**: A opção **Bloquear** impede a alteração da orientação da tela quando o usuário gira o dispositivo. **Não configurado** permite o uso desse recurso.
- **Botão Suspender tela**: Escolha a opção **Bloquear** para desabilitar o botão de ativação e suspensão da tela no dispositivo. **Não configurado** permite o uso desse recurso.
- **Toque**: A opção **Bloquear** desabilita a tela touch no dispositivo. **Não configurado** permite que o usuário utilize a tela sensível ao toque.
- **Botões de volume**: a opção **Bloquear** impede o uso dos botões de volume no dispositivo. A opção **Não configurado** permite os botões de volume.
- **Controle de toque assistencial**: Com a opção **Permitir**, os usuários podem usar a função de toque assistencial. **Não configurado** desabilita esse recurso.
- **Controle Inverter cores**: **Permita** alterações de inversão de cores para permitir que os usuários ajustem a função de inversão de cores. **Não configurado** desabilita esse recurso.
- **Falar o texto selecionado**: **Permita** as configurações de acessibilidade Falar Seleção no dispositivo. Esse recurso lê o texto que o usuário seleciona em voz alta. **Não configurado** desabilita esse recurso.
- **Modificação do controle de voz**: a opção **Permitir** permite que os usuários alterem o estado do controle de voz nos dispositivos. A opção **Não configurado** impede que os usuários alterem o estado do controle de voz nos dispositivos.

  Essa configuração aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e versões mais recentes

- **Controle de VoiceOver**: **Permita** alterações do VoiceOver para que os usuários possam atualizar a função VoiceOver, como a velocidade de leitura do texto na tela. **Não configurado** impede alterações ao VoiceOver.
- **Controle de zoom**: **Permita** alterações de zoom pelo usuário. **Não configurado** impede alterações de zoom.

> [!NOTE]
> Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar a ferramenta Apple Configurator ou o Programa de registro de dispositivos da Apple para colocar o dispositivo no modo supervisionado. Consulte o guia da Apple sobre como usar a ferramenta Apple Configurator.
> Se o aplicativo iOS que você especificar for instalado após a atribuição do perfil, o dispositivo não entrará no modo de quiosque após ser reiniciado.

## <a name="domains"></a>Domínios

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Domínios de email desmarcados** > **URL de domínio de email**: adicione uma ou mais URLs à lista. Quando os usuários finais receberem um email de um domínio diferente dos domínios inseridos por você, o email será marcado como não confiável no aplicativo Mail do iOS.

- **Domínios Web gerenciados** > **URL do Domínio Web**; adicione uma ou mais URLs à lista. Quando os documentos são baixados dos domínios inseridos, eles são considerados gerenciados. Essa configuração só se aplica a documentos baixados usando o navegador Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Domínios de preenchimento automático de senha do Safari** > **URL de domínio**: adicione uma ou mais URLs à lista. Os usuários só podem salvar senhas da Web das URLs nesta lista. Essa configuração se aplica somente ao navegador Safari e aos dispositivos no modo supervisionado. Se você não inserir URLs, será possível salvar senhas de todos os sites.

  Essa configuração aplica-se a:  
  - iOS 9.3 e mais recente

## <a name="settings-that-require-supervised-mode"></a>Configurações que exigem o modo supervisionado

O modo supervisionado do iOS só pode ser habilitado durante a instalação inicial do dispositivo por meio do Programa de Registro de Dispositivos da Apple ou usando o Apple Configurator. Após habilitar o modo supervisionado, o Intune pode configurar um dispositivo com a seguinte funcionalidade:

- Bloqueio de aplicativo (modo de aplicativo único) 
- Proxy HTTP global 
- Desabilitar o Bloqueio de Ativação 
- Modo autônomo de aplicativo único 
- Filtro de conteúdo da Web 
- Definir tela de fundo e tela de bloqueio 
- Push de aplicativo silencioso 
- VPN sempre ativado 
- Permitir instalação de aplicativo gerenciada exclusivamente 
- iBookstore 
- iMessages 
- Game Center 
- AirDrop 
- AirPlay 
- Emparelhamento de host 
- Sincronização de nuvem 
- Pesquisa do Spotlight 
- Entrega 
- Apagar dispositivo 
- Interface do usuário de restrições 
- Instalação de perfis de configuração pela interface do usuário 
- News 
- Atalhos de teclado 
- Modificações de senha 
- Alterações do nome do dispositivo 
- Downloads de aplicativo automáticos 
- Alterações na confiança de aplicativo da empresa 
- Apple Music 
- Recebimento de email 
- Emparelhar com Apple Watch 

> [!NOTE]
> A Apple confirmou que certas configurações mudarão para “somente supervisionadas” em 2019. É recomendável levar isso em consideração ao usar estas configurações em vez de esperar a Apple migrá-las para somente supervisionado:
>
> - Instalação do aplicativo pelos usuários finais
> - Remoção de aplicativo
> - FaceTime
> - Safari
> - iTunes
> - Conteúdo explícito
> - Documentos e dados do iCloud
> - Jogo para vários participantes
> - Adicionar amigos do Game Center
> - Siri

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](../device-profile-monitor.md).

Você também pode restringir recursos e configurações de dispositivos em dispositivos [macOS](device-restrictions-macos.md).
