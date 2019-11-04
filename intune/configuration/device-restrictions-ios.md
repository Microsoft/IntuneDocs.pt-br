---
title: Configurações de dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione, defina ou crie configurações em dispositivos iOS para restringir recursos, o que inclui definir os requisitos de senha, controlar a tela bloqueada, usar aplicativos internos, adicionar aplicativos aprovados ou restritos, lidar com dispositivos Bluetooth, conectar-se à nuvem para backup e armazenamento, habilitar o modo de quiosque, adicionar domínios e controlar como os usuários interagem com o navegador da Web Safari no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/31/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6dbe26dba4e78e9f5f29a5adedffa3de1df662a6
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414687"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo iOS e iPadOS para permitir ou restringir recursos usando o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos iOS e iPadOS. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, permitir ou restringir aplicativos específicos e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos iOS.

> [!TIP]
> Essas configurações usam as configurações de MDM da Apple. Para obter mais informações sobre essas configurações, consulte [configurações de gerenciamento de dispositivo móvel da Apple](https://support.apple.com/guide/mdm/welcome/web) (abre o site da Apple).

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de configuração de restrições de dispositivo](../device-restrictions-configure.md).

> [!NOTE]
> Essas configurações se aplicam a diferentes tipos de registro, com algumas configurações sendo aplicadas a todas as opções de registro. Para obter mais informações sobre os diferentes tipos de registro, consulte [registro do IOS](../ios-enroll.md).

## <a name="general"></a>Geral

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Compartilhar dados de uso**: escolha **Bloquear** para impedir que o dispositivo envie dados de telemetria de diagnóstico e de uso para a Apple. **Não configurado** (padrão) permite que esses dados sejam enviados.

- **Captura de tela**: escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo. No iOS 9,0 e mais recente, ele também bloqueia gravações de tela. **Não configurado** (padrão) permite que o usuário capture o conteúdo da tela como uma imagem ou um vídeo.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Certificados TLS não confiáveis**: escolha **Bloquear** para impedir certificados TLS (Transport Layer Security) não confiáveis no dispositivo. **Não configurado** (padrão) permite certificados TLS.
- **Permitir atualizações do PKI aéreo**: **Permitir** deixa os usuários receberem as atualizações de software sem precisar conectar os dispositivos a um computador.
- **Limitar acompanhamento de anúncio**: escolha **Limitar** para desabilitar o identificador de publicidade do dispositivo. **Não configurado** (padrão) o mantém habilitado.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Modificação de configurações de envio de diagnóstico**: **Bloquear** impede que o usuário altere as configurações de envio de diagnóstico e análise do aplicativo em **Diagnóstico e Uso** (Configurações do dispositivo). **Não configurado** (padrão) permite que o usuário altere as configurações do dispositivo.

  Para usar essa configuração, defina a configuração **compartilhar dados de uso** como **Bloquear**.

  Esse recurso aplica-se a:  
  - iOS 9.3.2 e mais recente

- **Observação de tela remota pelo aplicativo Classroom**: escolha **Bloquear** para impedir que o aplicativo Classroom observe remotamente a tela no dispositivo. **Não configurado** (padrão) permite que o aplicativo Classroom da Apple exiba a tela.

  Para usar essa configuração, defina a configuração de **captura de tela** como **Bloquear**.

  Esse recurso aplica-se a:  
  - iOS 9.3 e mais recente

- **Observação da tela não solicitada pelo aplicativo Classroom**: se for definido como **Permitir**, os professores poderão observar silenciosamente a tela dos dispositivos iOS dos alunos usando o aplicativo Classroom sem o conhecimento dos alunos. Os dispositivos de alunos registrados em uma aula por meio do aplicativo Classroom concedem automaticamente a permissão ao professor do curso. **Não configurado** (padrão) impede esse recurso.

  Para usar essa configuração, defina a configuração de **captura de tela** como **Bloquear**.

- **Relação de confiança do aplicativo empresarial**: escolha **Bloquear** para remover o botão **Trust Enterprise Developer** em Configurações > Geral > Perfis e Gerenciamento de Dispositivo no dispositivo. **Não configurado** (padrão) permite que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Modificação de conta**: quando definido como **Bloquear**, o usuário não pode atualizar as configurações específicas do dispositivo pelo aplicativo Ajustes do iOS. Por exemplo, o usuário não pode criar novas contas de dispositivo ou alterar o nome de usuário ou a senha. **Não configurado** (padrão) permite que os usuários alterem as configurações.

  Esse recurso também se aplica às configurações acessíveis pelo aplicativo Ajustes do iOS, como Mail, Contatos, Calendário, Twitter e mais. Esse recurso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo Ajustes do iOS, por exemplo, o aplicativo Microsoft Outlook.

- **Tempo de tela**: escolha **Bloquear** para impedir que os usuários definam suas próprias restrições em Tempo de Tela (configurações de dispositivo). **Não configurado** permite que o usuário configure restrições de dispositivo (como controles parentais ou restrições de privacidade e conteúdo) no dispositivo.

  Essa configuração foi renomeada de **Habilitando restrições nas configurações do dispositivo**. Impacto dessa alteração:  
  
  - iOS 11.4.1 e anterior: **Bloquear** impede que os usuários finais definam suas próprias restrições nas configurações do dispositivo. O comportamento é o mesmo; não há nenhuma alteração para os usuários finais.
  - iOS 12.0 e mais recente: **Bloquear** impede que os usuários finais configurem o próprio **Tempo de Tela** nas configurações do dispositivo (Configurações > Geral > Tempo de Tela), incluindo restrições de conteúdo e privacidade. Dispositivos atualizados para o iOS 12.0 não verão mais a guia Restrições nas configurações do dispositivo (Configurações > Geral > Gerenciamento de Dispositivo > Perfil de Gerenciamento > Restrições). Essas configurações estão no **Tempo de Tela**.
  
- **Usar a opção apagar todo o conteúdo e as configurações no dispositivo**: escolha **Bloquear** para que os usuários não possam utilizar a opção para apagar todo o conteúdo e as configurações no dispositivo. **Não configurado** (padrão) fornece aos usuários acesso a essas configurações.
- **Modificação do nome do dispositivo**: escolha **Bloquear** para que o nome do dispositivo não possa ser alterado. **Não configurado** (padrão) permite que o usuário altere o nome do dispositivo.
- **Modificação das configurações de notificação**: escolha **Bloquear** para que as configurações de notificação não possam ser alteradas. **Não configurado** (padrão) permite que o usuário altere as configurações de notificação do dispositivo.
- **Modificação de papel de parede**: **Bloquear** impede a alteração do papel de parede. **Não configurado** (padrão) permite que o usuário altere o papel de parede do dispositivo.
- **Modificação de configurações de confiança do aplicativo empresarial**: **Bloquear** impede que o usuário altere as configurações de confiança do aplicativo corporativo em dispositivos supervisionados. **Não configurado** (padrão) permite que o usuário confie em aplicativos que não foram baixados da loja de aplicativos.
- **Alterações do perfil de configuração**: **Bloquear** impede alterações no perfil de configuração no dispositivo. **Não configurado** (padrão) permite que o usuário instale perfis de configuração.
- **Bloqueio de Ativação**: escolha **Permitir** para habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados. O Bloqueio de Ativação dificulta a reativação de um dispositivo perdido ou roubado.
- **Bloquear a remoção de aplicativo**: escolha **Bloquear** para impedir que os usuários removam aplicativos. **Não configurado** (padrão) permite que os usuários removam aplicativos do dispositivo.
- **Bloqueia o modo USB Restrito**: escolha **Bloquear** para desabilitar o modo USB Restrito em dispositivos supervisionados. O modo USB Restrito impede a troca de dados de acessórios USB com um dispositivo que está bloqueado há mais de uma hora. **Não configurado** (padrão) permite o modo USB Restrito.
- **Forçar data e hora automáticas**: **Exigir** força os dispositivos supervisionados a definir automaticamente a data e a hora. O fuso horário do dispositivo é atualizado quando o dispositivo está conectado à rede celular ou ao Wi-Fi e com os serviços de localização habilitados.
- **Exigir que os alunos solicitem permissão para deixar o curso do Classroom**: **Exigir** força os alunos inscritos em um curso não gerenciado por meio do aplicativo Classroom a solicitarem permissão do professor para sair do curso. **Não configurado** (padrão) não força o aluno a pedir permissão.

  Esse recurso aplica-se a:  
  - iOS 11.3 e mais recente

- **Permitir que o Classroom bloqueie um aplicativo e bloqueie o dispositivo sem solicitar**: **Habilitar** permite que o professor bloqueie aplicativos ou o dispositivo usando o aplicativo Classroom sem avisar o aluno. Bloquear aplicativos significa que o dispositivo pode acessar apenas aplicativos especificados pelo professor. **Não configurado** (padrão) impede que professores bloqueiem aplicativos ou dispositivos usando o aplicativo de Sala de Aula sem avisar o aluno.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Ingressar automaticamente em aulas do Classroom sem avisar**: **Habilitar** automaticamente permite que os alunos ingressem em uma aula que está no aplicativo Classroom sem avisar o professor. **Não configurado** (padrão) avisa o professor de que alunos desejam ingressar em uma aula que está no aplicativo de Sala de Aula.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Bloquear a criação de VPN**: **Bloquear** impede que usuários criem definições de configuração de VPN. **Não configurado** (padrão) permite aos usuários criar VPNs no dispositivo.
- **Modificar configurações do eSIM**: **Bloquear** impede que os usuários removam ou adicionem um plano de celular ao eSIM no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações.

  Esse recurso aplica-se a:  
  - iOS 12.1 e mais recente

- **Adiar atualizações de software**: quando definido como **Não configurado** (padrão), as atualizações de software são exibidas no dispositivo conforme a Apple as libera. Por exemplo, se uma atualização do iOS é lançada pela Apple em uma data específica, essa atualização naturalmente aparece no dispositivo perto da data de lançamento.

  **Habilitar** permite que você atrase quando as atualizações de software são mostradas em dispositivos, de 0 a 90 dias. Essa configuração não controla quando as atualizações são ou não instaladas. 

  - **Atrasar a visibilidade de atualizações de software**: insira um valor de 0 a 90 dias. Quando o atraso expira, os usuários recebem uma notificação para atualizar para a versão mais antiga do sistema operacional que estava disponível quando o atraso foi disparado.

    Por exemplo, se iOS 12.a está disponível no dia **1º de janeiro** e **Atrasar a visibilidade** está definido como **5 dias**, iOS 12.a não é mostrado como uma atualização disponível em dispositivos do usuário final. No **sexto dia** após o lançamento, essa atualização está disponível e os usuários finais podem instalá-la.

    Essa configuração aplica-se a:  
    - iOS 11.3 e mais recente

## <a name="password"></a>Senha

> [!NOTE]
> Em uma versão futura, essas configurações de senha na interface do usuário do Intune estão sendo atualizadas para corresponder ao tipo de registro.

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Senha**: **Exigir** que o usuário final insira uma senha para acessar o dispositivo. **Não configurado** (padrão) permite que os usuários acessem o dispositivo sem inserir uma senha.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

> [!IMPORTANT]
> Em dispositivos registrados de usuários, se você definir qualquer configuração de senha, as configurações de **Senhas simples** serão definidas automaticamente como **Bloquear**, e será aplicado um PIN de seis dígitos.
>
> Por exemplo, você define a configuração de **Expiração de senha** e envia por push essa política para os dispositivos registrados pelo usuário. Nos dispositivos, acontece o seguinte:
>
> - A configuração de **Expiração de senha** é ignorada.
> - Senhas simples, como `1111` ou `1234`, não são permitidas.
> - É aplicado um PIN de seis dígitos.

- **Senhas simples**: escolha **Bloquear** para exigir senhas mais complexas. **Não configurado** permite senhas simples, como `0000` e `1234`.

- **Tipo de senha necessária**: escolha o tipo de senha exigido por sua organização. Suas opções:
  - **Padrão do dispositivo**
  - **Numérica**
  - **Alfanumérica**
- **Número de caracteres não alfanuméricos na senha**: insira o número de caracteres de símbolo, como `#` ou `@` que devem ser incluídos na senha.

- **Comprimento mínimo da senha**: insira o comprimento mínimo que um usuário deve inserir, entre 4 e 14 caracteres. Em dispositivos registrados pelo usuário, insira um comprimento entre 4 e 6 caracteres.
  
  > [!NOTE]
  > Para dispositivos registrados pelo usuário, os usuários podem definir um PIN maior que 6 dígitos. No entanto, no máximo seis dígitos são impostos no dispositivo. Por exemplo, um administrador define o comprimento mínimo para `8`. Em dispositivos registrados pelo usuário, os usuários só precisam definir um PIN de 6 dígitos. O Intune não força um PIN maior que 6 dígitos em dispositivos registrados pelo usuário.

- **Número de falhas de entrada antes de apagar o dispositivo**: insira quantas falhas podem ocorrer antes de o dispositivo ser apagado (entre 4 e 11).
  
  o iOS tem segurança interna que pode afetar essa configuração. Por exemplo, o iOS pode atrasar o disparo da política dependendo do número de falhas de entrada. Ele também pode considerar a inserção repetida da mesma senha como uma única tentativa. O [Guia de segurança do IOS](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) da Apple (abre o site da Apple) é um bom recurso e fornece detalhes mais específicos sobre as senhas.
  
- **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**<sup>1</sup>: insira por quanto tempo o dispositivo deve permanecer ocioso antes que o usuário tenha que digitar novamente a senha. Se o tempo inserido for maior do que o valor definido no dispositivo, o dispositivo ignorará o tempo inserido por você. Compatível com dispositivos iOS 8.0 e mais recentes.

- **Máximo de minutos de inatividade até o bloqueio da tela**<sup>1</sup>: inserir o número máximo de minutos de inatividade permitido antes que a tela do dispositivo seja bloqueada.

  **Opções do IOS**:  

  - **Não configurado** (padrão): o Intune não toca nessa configuração.
  - **Imediatamente**: bloqueios de tela após 30 segundos de inatividade.
  - **1**: bloqueios de tela após 1 minuto de inatividade.
  - **2**: bloqueios de tela após 2 minutos de inatividade.
  - **3**: bloqueios de tela após 3 minutos de inatividade.
  - **4**: bloqueios de tela após 4 minutos de inatividade.
  - **5**: bloqueios de tela após 5 minutos de inatividade.
    
  **Opções de iPadOS**:  

  - **Não configurado** (padrão): o Intune não toca nessa configuração.
  - **Imediatamente**: a tela é bloqueada após 2 minutos de inatividade.
  - **2**: bloqueios de tela após 2 minutos de inatividade.
  - **5**: bloqueios de tela após 5 minutos de inatividade.
  - **10**: bloqueios de tela após 10 minutos de inatividade.
  - **15**: bloqueios de tela após 15 minutos de inatividade.

  Se um valor não se aplicar ao iOS ou iPadOS, a Apple usará o *menor valor mais* próximo. Por exemplo, se você inserir `4` minutos, os dispositivos iPadOS usarão `2` minutos. Se você inserir `10` minutos, os dispositivos iOS usarão `5` minutos. Essa é uma limitação da Apple.
  
  > [!NOTE]
  > A interface do usuário do Intune para essa configuração não separa os valores com suporte para iOS e iPadOS. A interface do usuário pode ser atualizada em uma versão futura.

- **Expiração da senha (dias)** : insira o número de dias antes que a senha do dispositivo precise ser alterada.
- **Evitar a reutilização de senhas anteriores**: insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada.
- **ID de toque e desbloqueio de ID facial**: escolha **Bloquear** para impedir o uso de uma impressão digital ou uma face para desbloquear o dispositivo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando estes métodos.

  O bloqueio dessa configuração também impede o uso da autenticação de Faceid para desbloquear o dispositivo.

  A ID de face se aplica a:  
  - iOS 11.0 e mais recente

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Modificação da senha**: escolha **Bloquear** para impedir que a senha seja alterada, adicionada ou removida. As alterações às restrições de senha são ignoradas em dispositivos supervisionados após o bloqueio desse recurso. **Não configurado** (padrão) permite a adição, alteração ou remoção das senhas.

  - **Modificação de ID de toque e ID de face**: o **bloco** impede que o usuário altere, adicione ou remova as impressões digitais Touchid e a ID facial. **Não configurado** (padrão) permite que o usuário atualize as impressões digitais TouchID e o Face ID no dispositivo.

    O bloqueio dessa configuração também impede que o usuário altere, adicione ou remova a autenticação de Faceid.

    A ID de face se aplica a:  
    - iOS 11.0 e mais recente

- **Bloquear o AutoPreenchimento de senha**: escolha **Bloquear** para evitar o uso do recurso de Preenchimento Automático de Senhas no iOS. Escolher **Bloquear** também tem o seguinte impacto:

  - Os usuários não receberão uma solicitação para usar uma senha salva no Safari ou em qualquer outro aplicativo.
  - As senhas fortes automáticas ficam desabilitadas, e o usuário não recebe sugestões de senhas fortes.

  **Não configurado** (padrão) permite esses recursos.

- **Bloquear solicitações de proximidade de senha**: escolha **Bloquear** para que um dispositivo de usuário não solicite senhas de dispositivos próximos. **Não configurado** (padrão) permite essas solicitações de senha.
- **Bloquear o compartilhamento de senha**: **Bloquear** impede o compartilhamento de senhas entre dispositivos usando o AirDrop. **Não configurado** (padrão) permite o compartilhamento das senhas.
- **Exigir autenticação de Touch ID ou Face ID para AutoPreenchimento de informações de senha ou cartão de crédito**: quando definido como **Exigir**, os usuários devem se autenticar usando TouchID ou FaceID antes que informações de senhas ou cartão de crédito possam ser automaticamente preenchidas no Safari e em outros aplicativos. **Não configurado** (padrão) permite aos usuários controlar esse recurso nas configurações do dispositivo.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente
  
<sup>1</sup>Se você definir as configurações **Máximo de minutos de inatividade até o bloqueio da tela** e **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**, elas são aplicadas em sequência. Por exemplo, se você definir o valor das duas configurações como **5** minutos, a tela desligará automaticamente após cinco minutos e o dispositivo será bloqueado após outros cinco minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo será bloqueado cinco minutos depois que o usuário desligar a tela.

## <a name="locked-screen-experience"></a>Experiência de tela bloqueada

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Acesso ao centro de controle enquanto o dispositivo está bloqueado**: escolha **Bloquear** para impedir o acesso ao aplicativo Centro de Controle quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite que o usuário acesse o aplicativo Centro de Controle quando o dispositivo estiver bloqueado.
- **Notificações enquanto o dispositivo está bloqueado**: **Bloquear** impede o acesso às notificações quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite que o usuário acesse as notificações sem desbloquear o dispositivo.
- **Exibição de hoje enquanto o dispositivo está bloqueado**: **Bloquear** impede o acesso à visualização Hoje quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite que o usuário veja a visualização Hoje quando o dispositivo estiver bloqueado.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Notificações do Wallet enquanto o dispositivo estiver bloqueado**: **Bloquear** impede o acesso ao aplicativo Wallet quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite ao usuário acessar o aplicativo Wallet enquanto o dispositivo estiver bloqueado.

## <a name="app-store-doc-viewing-gaming"></a>Loja de Aplicativos, Exibição de Documentos, Jogos

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Exibição de documentos corporativos em aplicativos não gerenciados**: **Bloquear** impede a exibição de documentos corporativos em aplicativos não gerenciados. **Não configurado** (padrão) permite que documentos corporativos sejam exibidos em qualquer aplicativo. Por exemplo, você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como **Bloquear**. Após o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permite mais salvar.

  - **Permitir que aplicativos não gerenciados leiam de contas de contatos gerenciados**: quando definido como **permitir**, aplicativos não gerenciados, como o aplicativo interno do IOS Contacts, podem ler e acessar informações de contato de aplicativos gerenciados, incluindo o aplicativo móvel do Outlook. **Não configurado** (padrão) impede a leitura, incluindo a remoção de duplicatas, do aplicativo Contatos interno do dispositivo.  
  
    Essa configuração permite ou impede a leitura de informações de contato. Ele não controla a sincronização de contatos entre os aplicativos.
  
    Para usar essa configuração, defina a configuração **Exibindo documentos corporativos em aplicativos não gerenciados** como **Bloquear**.

  Para obter mais informações sobre essas duas configurações e seu impacto sobre a sincronização de exportação de contato do Outlook para iOS, consulte [dica de suporte: usar configurações de perfil personalizado do Intune com o aplicativo de contatos nativos do IOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453).

- **Tratar o AirDrop como um destino não gerenciado**: **Exigir** força o AirDrop a ser considerado como um destino não gerenciado. Isso impede que os aplicativos gerenciados enviem dados usando o Airdrop. 
- **Exibindo documentos não corporativos em aplicativos corporativos**: **Bloquear** impede a exibição de documentos não corporativos em aplicativos corporativos. **Não configurado** (padrão) permite que qualquer documento seja exibido em aplicativos gerenciados corporativos.

  A configuração para **Bloquear** também impede a sincronização de exportação de contato no Outlook para Ios. Para obter mais informações, consulte [dica de suporte: Habilitando a sincronização de contatos do Outlook Ios com controles de MDM iOS12](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Exigir senha da iTunes Store para todas as compras**: **exige** que o usuário insira a senha da ID da Apple para cada compra no aplicativo ou iTunes. **Não configurado** (padrão) permite compras sem solicitar uma senha a cada vez.
- **Compras no aplicativo**: escolha **Bloquear** para evitar compras no aplicativo a partir da loja. **Não configurado** (padrão) permite compras na loja em um aplicativo em execução.
- **Baixar o conteúdo da iBook Store sinalizado como "Erotismo"** : escolha **Bloquear** para impedir que os usuários baixem mídias da iBook Store marcadas como erotismo. **Não configurado** (padrão) permite que o usuário baixe livros da categoria "Erotismo".
- **Permitir que aplicativos gerenciados gravem contatos em contas de contatos não gerenciados**: quando definido como **permitir**, aplicativos gerenciados, como o aplicativo móvel do Outlook, podem salvar ou sincronizar informações de contato, incluindo contatos comerciais e corporativos, para os contatos internos do IOS aplicação. Quando definido como **não configurado** (padrão), os aplicativos gerenciados não podem salvar ou sincronizar informações de contato com o aplicativo interno de contatos do Ios no dispositivo.
  
  Para usar essa configuração, defina a configuração **Exibindo documentos corporativos em aplicativos não gerenciados** como **Bloquear**.

- **Região de classificações**: escolha a região de classificações que você quer usar para downloads permitidos. E, em seguida, escolha as classificações permitidas para **Filmes**, **Programas de TV** e **Aplicativos**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Loja de aplicativos**: **Bloquear** impede o acesso à loja de aplicativos em dispositivos supervisionados. **Não configurado** (padrão) permite o acesso.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

  - **Instalar aplicativos da App Store**: escolha **Bloquear** para bloquear a App Store na tela inicial do dispositivo. Os usuários finais podem continuar a usar o iTunes ou o Apple Configurator para instalar aplicativos. **Não configurado** (padrão) permite a App Store na tela inicial.
  - **Downloads automáticos de aplicativos**: escolha **Bloquear** para impedir o download automático de aplicativos comprados em outros dispositivos. Isso não afeta as atualizações dos aplicativos existentes. **Não configurado** (padrão) permite o download dos aplicativos comprados em outros dispositivos iOS para o dispositivo.

- **Conteúdo explícito de música, podcast ou notícias do iTunes**: escolha **Bloquear** para impedir conteúdo explícito em músicas, podcasts ou notícias do iTunes. **Não configurado** (padrão) permite ao dispositivo acessar conteúdo classificado como adulto na loja. o iOS 13 e mais recente podem exigir apenas dispositivos supervisionados. 

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Adicionar amigos do Game Center**: **Bloquear** impede os usuários de adicionar amigos ao Game Center. **Não configurado** (padrão) permite que o usuário adicione amigos ao Game Center.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Game Center**: **Bloquear** o uso do aplicativo Game Center. **Não configurado** (padrão) permite o uso do aplicativo Game Center no dispositivo.
- **Jogos para vários jogadores**: escolha **Bloquear** para evitar jogos com vários participantes. **Não configurado** (padrão) permite que o usuário execute jogos para vários participantes no dispositivo.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Acesso à unidade de rede no aplicativo de arquivos**: usando o protocolo SMB, os dispositivos podem acessar arquivos ou outros recursos em um servidor de rede. **Desabilitar** impede o acesso a arquivos em uma unidade SMB de rede. **Não configurado** (padrão) permite o acesso.

  Esse recurso aplica-se a:  
  - iOS e iPadOS 13,0 e mais recentes

## <a name="built-in-apps"></a>Aplicativos internos

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Siri**: **Bloquear** impede o acesso à Siri. **Não configurado** (padrão) permite o uso da assistente de voz Siri no dispositivo.
  - **Siri enquanto o dispositivo está bloqueado**: escolha **Bloquear** para impedir o acesso à Siri quando o dispositivo estiver bloqueado. **Não configurado** (padrão) permite o uso da assistente de voz Siri no dispositivo quando ele estiver bloqueado.

- **Alertas de fraude do Safari**: **Exigir** a exibição de avisos de fraude no navegador da Web no dispositivo. **Não configurado** (padrão) desabilita esse recurso.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Pesquisa do Spotlight retorna resultados da Internet**: **Bloquear** impede que o Spotlight retorne qualquer resultado de uma pesquisa na Internet. **Não configurado** (padrão) permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.

- **Cookies do Safari**: escolha como lidar com os cookies no dispositivo. Suas opções:
  - Allow
  - Bloquear todos os cookies
  - Permitir cookies dos sites visitados
  - Permitir cookies do site atual

- **JavaScript do Safari**: **Bloquear** impede a execução de scripts em Java no navegador do dispositivo. **Não configurado** (padrão) permite scripts java.

- **Pop-ups do Safari**: **Bloquear** desabilita o bloqueador de pop-ups no navegador da Web. **Não configurado** (padrão) permite o bloqueador de pop-ups.

- **Registro em log do lado do servidor para comandos Siri**: quando definido como **desabilitado**, o registro em log de Siri do servidor é desativado. Ele também pode impedir o registro de solicitações de usuário em servidores Siri. **Não configurado** (padrão) registra os comandos Siri no lado do servidor. Essa configuração não depende da configuração Siri que está sendo bloqueada ou não configurada.

  Esse recurso aplica-se a:  
  - iOS 12.2 e mais recente

  > [!NOTE]
  > A configuração **log do lado do servidor para comandos Siri** é preterida pela Apple. Em uma versão futura, essa configuração é removida do console do Intune.
  >
  > Atualmente, essa configuração não tem nenhum efeito nos dispositivos, mesmo que a configuração seja mostrada nos perfis gerenciamento dispositivos. Para excluir essa configuração de qualquer política, abra a política, faça uma alteração secundária e, em seguida, salve a política. A política é atualizada e a configuração é excluída dos dispositivos.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Câmera**: escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não configurado** (padrão) permite o acesso à câmera do dispositivo.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

  - **FaceTime**: **Bloquear** para impedir o acesso ao aplicativo FaceTime. **Não configurado** (padrão) permite o acesso ao aplicativo FaceTime no dispositivo.

    A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Filtro de profanação da Siri**: **Exigir** impede que a Siri dite ou use linguagem ofensiva.

  Para usar essa configuração, defina a configuração **Siri** como **Bloquear**.

- **Siri para consultar conteúdo gerado pelo usuário na Internet**: **Bloquear** impede que a Siri acesse sites para responder a perguntas. **Não configurado** (padrão) permite que a Siri acesse conteúdo gerado pelo usuário na Internet.

  Para usar essa configuração, defina a configuração **Siri** como **Bloquear**.

- **Apple News**: escolha **Bloquear** para impedir o acesso ao aplicativo Apple News no dispositivo. **Não configurado** (padrão) permite o uso do aplicativo Apple News.
- **IBooks Store**: **Bloquear** impede o acesso à iBooks Store. **Não configurado** (padrão) permite aos usuários procurar e comprar livros na iBooks Store.
- **Aplicativo de mensagens no dispositivo**: **Bloquear** impede que os usuários usem o aplicativo mensagens para IMessage. Se o dispositivo der suporte a mensagens de texto, o usuário ainda poderá enviar e receber mensagens de texto usando o SMS. **Não configurado** (padrão) permite usar o aplicativo mensagens para enviar e ler mensagens pela Internet.
- **Podcasts**: **Bloquear** impede os usuários de usar o aplicativo Podcasts. **Não configurado** (padrão) permite o uso do aplicativo Podcasts.
- **Serviço de Música**: **Bloquear** reverte o aplicativo Música para o modo clássico e desabilita o serviço de Música. **Não configurado** (padrão) permite o uso do aplicativo Apple Music.
- **Serviço do iTunes Radio**: **Bloquear** impede que os usuários utilizem o aplicativo iTunes Radio. **Não configurado** (padrão) permite o uso do aplicativo iTunes Radio.
- **iTunes Store**: **não configurado** (padrão) permite o iTunes nos dispositivos. **Bloquear** impede que os usuários usem o iTunes no dispositivo. 

  Esse recurso aplica-se a:  
  - iOS 4.0 e mais recente

- **Localizar meu iPhone**: **não configurado** (padrão) permite usar o recurso Localizar meu aplicativo para obter o local aproximado do dispositivo. **Bloquear** impede esse recurso na localização de meu aplicativo. 

  Esse recurso aplica-se a:  
  - iOS 13,0 e iPadOS 13,0 e mais recentes

- **Localizar meus amigos**: **não configurado** (padrão) permite usar o recurso Localizar meu aplicativo para encontrar a família e os amigos de um dispositivo Apple ou icloud.com. **Bloquear** impede esse recurso na localização de meu aplicativo.

  Esse recurso aplica-se a:  
  - iOS 13,0 e iPadOS 13,0 e mais recentes

- **Alterações nas configurações do aplicativo Buscar meus amigos**: **Bloquear** impede alterações nas configurações do aplicativo Buscar meus amigos. **Não configurado** (padrão) permite que o usuário altere as configurações do aplicativo Buscar meus amigos.

- **Pesquisa do Spotlight retorna resultados da Internet**: **Bloquear** impede que o Spotlight retorne qualquer resultado de uma pesquisa na Internet. **Não configurado** (padrão) permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.

- **Bloquear a remoção dos aplicativos do sistema do dispositivo**: escolher **Bloquear** desabilita a capacidade de remover aplicativos do sistema do dispositivo. **Não configurado** (padrão) permite que os usuários removam aplicativos do sistema.

- **Safari**: **bloqueie** o uso do navegador Safari no dispositivo. **Não configurado** (padrão) permite que os usuários utilizem o navegador Safari.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Preenchimento Automático do Safari**: **Bloquear** desabilita o recurso de preenchimento automático do Safari no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações de preenchimento automático no navegador da Web.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

## <a name="restricted-apps"></a>Aplicativos restritos

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Tipo de lista de aplicativos restritos**: Crie uma lista de aplicativos que os usuários não têm permissão para instalar ou usar. Suas opções:

  - **Não configurado** (padrão): não há restrições do Intune. Os usuários têm acesso aos aplicativos que você atribui e aos aplicativos internos.
  - **Aplicativos proibidos**: aplicativos não gerenciados pelo Intune que você não deseja que sejam instalados no dispositivo. Os usuários não são impedidos de instalar um aplicativo proibido. Mas se um usuário instalar um aplicativo dessa lista, ele será relatado no Intune.
  - **Aplicativos aprovados**: aplicativos que os usuários têm permissão de instalar. Os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente. Os usuários não são impedidos de instalar um aplicativo que não esteja na lista aprovada. Mas, se isso for feito, ele será relatado no Intune.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar** a URL da iTunes App Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` ou `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.

- **Importar** um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app url>, <app name>, <app publisher>`. Ou **exporte** uma lista existente que contenha a lista de aplicativos restritos no mesmo formato.

> [!IMPORTANT]
> Os perfis de dispositivo que usam configurações de aplicativo restrito devem ser atribuídos a grupos de usuários.

## <a name="show-or-hide-apps"></a>Mostrar ou ocultar aplicativos

Aplica-se a dispositivos que executam o iOS 9,3 ou mais recente.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Tipo de lista de aplicativos**: Crie uma lista de aplicativos para mostrar ou ocultar. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple tem uma lista de [aplicativos da Apple internos](https://support.apple.com/HT208094). Suas opções:

  - **Aplicativos ocultos**: insira uma lista de aplicativos ocultos. Os usuários não podem exibir ou abrir esses aplicativos.
  - **Aplicativos visíveis**: insira uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

- **URL do aplicativo**: Insira a URL do aplicativo da loja do aplicativo que você deseja mostrar ou ocultar. Por exemplo:

  - Para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` ou `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`. 

  - Para adicionar o aplicativo Microsoft Word, digite `https://itunes.apple.com/de/app/microsoft-word/id586447913` ou `https://apps.apple.com/de/app/microsoft-word/id586447913`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.
  
  Para obter mais informações sobre como localizar uma ID de pacote, consulte [como encontrar a ID de pacote para um aplicativo IOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).

- **ID do pacote de aplicativos**: insira a [ID do pacote](bundle-ids-built-in-ios-apps.md) do aplicativo desejado. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple tem uma lista de [aplicativos da Apple internos](https://support.apple.com/HT208094).
- **Nome do aplicativo**: insira o nome do aplicativo desejado. Você pode mostrar ou ocultar aplicativos internos e aplicativos de linha de negócios. O site da Apple tem uma lista de [aplicativos da Apple internos](https://support.apple.com/HT208094).
- **Editor**: insira o editor do aplicativo desejado.

Para adicionar aplicativos, você pode:

- **Adicionar**: Selecione para criar sua lista de aplicativos.
- **Importar** um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app url>, <app name>, <app publisher>`. Ou, **Exportar** para criar uma lista de aplicativos restritos que você adicionou, no mesmo formato.

## <a name="wireless"></a>Sem fio

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Roaming de dados**: escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** (padrão) permite o roaming de dados quando o dispositivo está em uma rede celular.
- **Busca global em segundo plano quando em roaming**: **Bloquear** impede o uso do recurso de busca global em segundo plano durante roaming em rede celular. **Não configurado** (padrão) permite ao dispositivo buscar dados, como emails, durante roaming em uma rede celular.
- **Discagem de voz**: escolha **Bloquear** para impedir o uso do recurso de discagem por voz no dispositivo. **Não configurado** (padrão) permite a discagem por voz no dispositivo.
- **Roaming de voz**: escolha **Bloquear** para impedir o roaming de voz pela rede celular. **Não configurado** (padrão) permite o roaming de voz quando o dispositivo está em uma rede celular.
- **Ponto de Acesso Pessoal**: **Bloquear** desativa o ponto de acesso pessoal no dispositivo dos usuários a cada sincronização do dispositivo. Essa configuração pode não ser compatíveis com algumas operadoras. **Não configurado** (padrão) mantém a configuração de ponto de acesso pessoal como o padrão definido pelo usuário.
- **Regras de uso da rede celular (somente aplicativos gerenciados)** : define os tipos de dados que os aplicativos gerenciados podem usar em redes celulares. Suas opções:
  - **Bloquear uso de dados da rede celular**: bloqueie o uso de dados da rede celular para **Todos os aplicativos gerenciados** ou **Escolha aplicativos específicos**.
  - **Bloquear uso de dados da rede celular enquanto estiver em roaming**: bloqueie o uso de dados da rede celular quando estiver em roaming para **Todos os aplicativos gerenciados** ou **Escolha aplicativos específicos**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Alterações nas configurações de uso de dados para celular do aplicativo**: escolha **Bloquear** para evitar alterações às configurações de uso de dados da rede celular do aplicativo. **Não configurado** (padrão) permite ao usuário controlar quais aplicativos têm permissão para usar dados de celular.
- **Alterações às configurações de plano de celular**: **Bloquear** impede que os usuários alterem as configurações no plano de celular. **Não configurado** (padrão) permite que os usuários façam alterações.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Modificação do usuário de hotspot pessoal**: quando definido como **Bloquear**, o usuário não pode alterar a configuração de hotspot pessoal. **Não configurado** (padrão) permite que os usuários finais habilitem ou desabilitem seus hotspots pessoais.

  Se você bloquear essa configuração e bloquear a configuração de ponto de interrupção **pessoal** , o hotspot pessoal será desativado.

  Esse recurso aplica-se a:  
  - iOS 12.2 e mais recente

- **Entrar nas redes Wi-Fi utilizando somente perfis de configuração**: **Exigir** força o dispositivo a usar apenas as configurações de redes Wi-Fi por meio de perfis de configuração do Intune. **Não configurado** (padrão) permite que o dispositivo use outras redes Wi-Fi.
- **Wi-Fi sempre ativado**: quando definido como **exigir**, o Wi-Fi permanece no aplicativo de configurações. Ele não pode ser desativado em configurações ou no centro de controle, mesmo quando o dispositivo está no modo avião. **Não configurado** (padrão) permite que o usuário controle a ativação ou desativação do Wi-Fi.

  Definir essa configuração não impede que os usuários selecionem uma rede Wi-Fi.

  Esse recurso aplica-se a:  
  - iOS e iPadOS 13,0 e mais recentes

## <a name="connected-devices"></a>Dispositivos conectados

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Detecção de pulso para Apple Watch pareado**: **Exigir** força um Apple Watch emparelhado a usar a detecção de pulso. Quando exigido, o Apple Watch não exibirá notificações quando não estiver sendo usado. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Exigir uma senha de emparelhamento para solicitações de saída do AirPlay**: **Exigir** uma senha emparelhamento quando o usuário usar o AirPlay para transmitir o conteúdo para outros dispositivos da Apple. **Não configurado** (padrão) permite que o usuário transmita conteúdo usando AirPlay sem inserir uma senha.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **AirDrop**: **Bloquear** impede o uso do AirDrop no dispositivo. **Não configurado** (padrão) permite o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
- **Emparelhamento de Apple Watch**: **Bloquear** impede o emparelhamento com um Apple Watch. **Não configurado** (padrão) permite que o dispositivo emparelhe com um Apple Watch.
- **Modificação de Bluetooth**: **Bloquear** impede o usuário final de alterar as configurações de Bluetooth no dispositivo. **Não configurado** (padrão) permite que o usuário altere as configurações.
- **Emparelhamento de host para controlar os dispositivos que podem ser emparelhados com um dispositivo iOS**: **Não configurado** (padrão) permite o emparelhamento de host para que o administrador controle com quais dispositivos um dispositivo iOS pode emparelhar. **Bloquear** impede o emparelhamento do host.
- **Bloquear AirPrint**: escolha **Bloquear** para impedir o uso do recurso AirPrint no dispositivo. **Não configurado** (padrão) permite que o usuário use o AirPrint.
  - **Bloquear o armazenamento de credenciais do AirPrint em um Conjunto de Chaves**: **Bloquear** impede o uso do armazenamento do Keychain para nome de usuário e senha no dispositivo. **Não configurado** (padrão) permite o armazenamento do nome de usuário e senha do AirPrint no aplicativo Keychain.
  - **Exigir um certificado TLS confiável para AirPrint**: **Exigir** força o dispositivo a usar certificados confiáveis para comunicação de impressão do TLS.
  - **Bloquear a descoberta de iBeacon de impressoras AirPrint**: **Bloquear** impede que beacons Bluetooth mal-intencionados do AirPrint usem phishing para tráfego de rede. **Não configurado** (padrão) permite a publicidade de impressoras AirPrint no dispositivo.
- **Bloquear configuração de novos dispositivos nas proximidades**: **Bloquear** desabilita o aviso para configurar novos dispositivos que estão nas proximidades. **Não configurado** (padrão) permite avisos para os usuários conectarem-se a outros dispositivos da Apple nas proximidades.

  Esse recurso aplica-se a:  
  - iOS 11.0 e mais recente

- **Acesso a arquivos na unidade USB**: os dispositivos podem se conectar e abrir arquivos em uma unidade USB. **Desabilitar** impede o acesso do dispositivo à unidade USB no aplicativo arquivos quando um USB está conectado ao dispositivo. Desabilitar esse recurso também impede que os usuários finais transfiram arquivos para uma unidade USB conectada a um iPad. **Não configurado** (padrão) permite o acesso a uma unidade USB no aplicativo arquivos.

  Esse recurso aplica-se a:  
  - iOS e iPadOS 13,0 e mais recentes

## <a name="keyboard-and-dictionary"></a>Teclado e dicionário

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Pesquisa de definição de palavra**: **Bloquear** impede que o usuário realce uma palavra e, em seguida, pesquise sua definição no dispositivo. **Não configurado** (padrão): permite o acesso ao recurso de pesquisa de definição.
- **Teclados preditivos**: **Não configurado** (padrão) permite o uso de teclados preditivos que sugerem palavras úteis ao usuário. **Bloquear** impede esse recurso.
- **Correção automática**: **Não configurado** (padrão) permite que o dispositivo corrija automaticamente palavras incorretas. **Bloquear** impede o uso da correção automática.
- **Verificação ortográfica do teclado**: **não configurado** (padrão) permite o uso do verificador ortográfico no dispositivo. **Bloquear** permite a correção ortográfica.
- **Atalhos de teclado**: **não configurado** (padrão) permite o uso de atalhos de teclado no dispositivo. **Bloquear** impede o uso de atalhos de teclado.
- **Ditado**: **Bloquear** impede o usuário de usar a entrada de voz para inserir texto. **Não configurado** (padrão) permite que o usuário use a entrada por ditado.
- **QuickPath**: **não configurado** (padrão) permite que os usuários usem o QuickPath, que permite uma entrada contínua no teclado do dispositivo. Os usuários podem digitar passando o dedo pelas chaves para criar palavras. **Bloquear** impede que os usuários usem o QuickPath. 

  Esse recurso aplica-se a:  
  - iOS 13,0 e iPadOS 13,0 e mais recentes

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Backup criptografado**: **Exigir** que quaisquer backups de dispositivo sejam criptografados.
- **Sincronização com a nuvem de aplicativos gerenciados**: **Não configurado** (padrão) permite que os aplicativos gerenciados com o Intune sincronizem dados com a conta do iCloud do usuário. **Bloquear** impede essa sincronização de dados com o iCloud.
- **Bloquear o Backup do Catálogo da Empresa**: escolha **Bloquear** para impedir os usuários de fazerem backup de livros corporativos. **Não configurado** (padrão) permite que os usuários façam backup desses livros.
- **Bloquear a sincronização de metadados do catálogo da empresa (notas e destaques)** : **Bloquear** impede a sincronização de notas e grifos em livros corporativos. **Não configurado** (padrão) permite a sincronização.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Sincronização do fluxo de fotos com o iCloud**: **Não configurado** (padrão) permite que os usuários habilitem **Meu Compartilhamento de Fotos** em seus dispositivos para sincronizar com o iCloud e disponibilizem as fotos em todos os dispositivos do usuário. **Bloquear** impede a sincronização de fluxo de fotos com o iCloud. O bloqueio desse recurso pode causar perda de dados. 
- **Biblioteca de Fotos do iCloud**: defina como **Bloquear** para desabilitar o uso da Biblioteca de Fotos do iCloud para armazenar fotos e vídeos na nuvem. As fotos que não forem totalmente baixadas da Biblioteca de Fotos do iCloud para o dispositivo serão removidas do dispositivo. **Não configurado** (padrão) permite o uso da Biblioteca de Fotos do iCloud.
- **Fluxo de fotos compartilhadas**: escolha **Bloquear** para desabilitar os **Álbuns Compartilhados** no dispositivo. **Não configurado** (padrão) permite a transmissão de fotos compartilhadas.
- **Entrega**: **não configurado** (padrão) permite que os usuários iniciem o trabalho em um dispositivo IOS e, em seguida, continuem o trabalho iniciado em outro dispositivo IOS ou MacOS. **Bloquear** impede o Handoff.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Backup no iCloud**: **Não configurado** (padrão) permite ao usuário fazer backup do dispositivo no iCloud. **Bloquear** impede que o usuário faça backup do dispositivo no iCloud.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Bloquear sincronização de documento para iCloud**: **Não configurado** (padrão) permite a sincronização de documentos e chave-valor para o espaço de armazenamento no iCloud. **Bloquear** impede o iCloud de sincronizar documentos e dados.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

- **Bloquear a sincronização do Conjunto de Chaves no iCloud**: escolha **Bloquear** para desabilitar a sincronização de credenciais armazenadas no Keychain com o iCloud. **Não configurado** (padrão) permite que os usuários sincronizem essas credenciais.

  A partir do iOS 13,0, essa configuração requer dispositivos supervisionados.

## <a name="autonomous-single-app-mode"></a>Modo autônomo de aplicativo único

Use essas opções para configurar dispositivos iOS para executar aplicativos específicos no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado. Ele só pode executar esse aplicativo. Por exemplo, adicione um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Nome do aplicativo**: insira o nome do aplicativo desejado.
- **ID do pacote de aplicativos**: insira a [ID do pacote](bundle-ids-built-in-ios-apps.md) do aplicativo desejado.
- **Adicionar**: Selecione para criar sua lista de aplicativos.

Também é possível **Importar** um arquivo CSV com a lista de nomes de aplicativo e suas IDs de pacote. Ou **Exportar** uma lista existente que contém os aplicativos.

## <a name="kiosk"></a>Quiosque

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Aplicativo a ser executado no modo de quiosque**: escolha o tipo de aplicativos que você deseja executar no modo de quiosque. Suas opções:
  - **Não configurado** (padrão): configurações de quiosque não são aplicadas. O dispositivo não é executado no modo de quiosque.
  - **Aplicativo da loja**: insira a URL de um aplicativo na iTunes App Store.
  - **Aplicativo gerenciado**: escolha um aplicativo que você adicionou ao Intune.
  - **Aplicativo Interno**: insira a [ID do pacote](bundle-ids-built-in-ios-apps.md) para o aplicativo nativo.

- **Toque assistencial**: **Exigir** a configuração de acessibilidade AssistiveTouch no dispositivo. Esse recurso ajuda os usuários proporcionando gestos na tela que podem ser difíceis. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Inverter cores**: **Exigir** a configuração de acessibilidade Inversão de Cores, para que os usuários com deficiências visuais possam alterar a exibição da tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Áudio mono**: **Exigir** a configuração de acessibilidade Áudio Mono no dispositivo. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Controle de voz**: **requer** habilitar o controle de voz no dispositivo e permite que os usuários CONTROLEM totalmente o sistema operacional usando comandos Siri. **Não configurado** desabilita o controle de voz no dispositivo.

  Essa configuração aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e mais recente
  
  > [!TIP]
  > Se você tiver aplicativos LOB disponíveis para sua organização e eles não estiverem no **controle de voz** pronto no dia 0 quando versões Ios 13,0, recomendamos que você deixe essa configuração como **não configurada**.

- **VoiceOver**: **Exigir** a configuração de acessibilidade VoiceOver no dispositivo para ler o texto na tela em voz alta. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Zoom**: **Exigir** a configuração de Zoom no dispositivo para permitir que os usuários usem o toque para ampliar a tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Bloqueio automático**: **Bloquear** impede o bloqueio automático do dispositivo. **Não configurado** permite o uso desse recurso.
- **Botão de toque**: **Bloquear** desabilita o botão toque (mudo) no dispositivo. **Não configurado** permite o uso desse recurso.
- **Rotação de tela**: **Bloquear** impede a alteração da orientação da tela quando o usuário gira o dispositivo. **Não configurado** permite o uso desse recurso.
- **Botão para colocar a tela em modo de suspensão**: escolha **Bloquear** para desabilitar o botão de suspensão/ativação da tela no dispositivo. **Não configurado** permite o uso desse recurso.
- **Toque**: **Bloquear** desabilita a tela sensível ao toque no dispositivo. **Não configurado** permite que o usuário utilize a tela sensível ao toque.
- **Botões de volume**: **bloco** impede o uso dos botões de volume no dispositivo. **Não configurado** permite os botões de volume.
- **Controle de toque assistencial**: **Permitir** deixa os usuários usarem a função AssistiveTouch. **Não configurado** desabilita esse recurso.
- **Controle Inverter cores**: **permita** alterações à inversão de cores para permitir que os usuários ajustem a função de inversão de cores. **Não configurado** desabilita esse recurso.
- **Falar o texto selecionado**: **Permitir** as configurações de acessibilidade Falar Seleção no dispositivo. Esse recurso lê o texto que o usuário seleciona em voz alta. **Não configurado** desabilita esse recurso.
- **Modificação de controle de voz**: **permite que** os usuários alterem o estado do controle de voz em seus dispositivos. **Não configurado** impede que os usuários alterem o estado do controle de voz em seus dispositivos.

  Essa configuração aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e mais recente

- **Controle VoiceOver**: **Permitir** alterações do VoiceOver para permitir que os usuários atualizem a função correspondente, como a velocidade de leitura do texto na tela. **Não configurado** impede alterações ao VoiceOver.
- **Controle de zoom**: **Permitir** alterações de zoom pelo usuário. **Não configurado** impede alterações de zoom.

> [!NOTE]
> Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar a ferramenta Apple Configurator ou o Programa de registro de dispositivos da Apple para colocar o dispositivo no modo supervisionado. Consulte o guia da Apple sobre como usar a ferramenta Apple Configurator.
> Se o aplicativo iOS que você especificar for instalado após a atribuição do perfil, o dispositivo não entrará no modo de quiosque após ser reiniciado.

## <a name="domains"></a>Domínios

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Domínios de email desmarcados** > **URL do Domínio de Email**: adicione uma ou mais URLs à lista. Quando os usuários finais receberem um email de um domínio diferente dos domínios inseridos por você, o email será marcado como não confiável no aplicativo Mail do iOS.

- **Domínios Web gerenciados** > **URL do Domínio Web**; adicione uma ou mais URLs à lista. Quando os documentos são baixados dos domínios inseridos, eles são considerados gerenciados. Essa configuração só se aplica a documentos baixados usando o navegador Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Domínios de preenchimento automático de senha do Safari** > **URL do Domínio**: adicione uma ou mais URLs à lista. Os usuários só podem salvar senhas da Web das URLs nesta lista. Essa configuração se aplica somente ao navegador Safari e aos dispositivos no modo supervisionado. Se você não inserir URLs, será possível salvar senhas de todos os sites.

  Essa configuração aplica-se a:  
  - iOS 9.3 e mais recente

## <a name="settings-that-require-supervised-mode"></a>Configurações que exigem o modo supervisionado

O modo supervisionado do iOS só pode ser habilitado durante a instalação inicial do dispositivo por meio do Programa de Registro de Dispositivos da Apple ou usando o Apple Configurator. Após habilitar o modo supervisionado, o Intune pode configurar um dispositivo com a seguinte funcionalidade:

- Bloqueio de aplicativo (modo de aplicativo único) 
- Proxy HTTP global 
- Ignorar Bloqueio de ativação 
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
> - Adicionar amigos no Game Center
> - Siri

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](../device-profile-monitor.md).

Você também pode restringir recursos e configurações de dispositivos em dispositivos [macOS](device-restrictions-macos.md).
