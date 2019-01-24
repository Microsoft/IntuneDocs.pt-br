---
title: Configurações de dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione, defina ou crie configurações em dispositivos iOS para restringir recursos, incluindo definir os requisitos de senha, controlar a tela bloqueada, usar aplicativos internos, adicionar aplicativos aprovados ou restritos, lidar com dispositivos Bluetooth, conectar-se à nuvem para backup e armazenamento, habilitar o modo de quiosque, adicionar domínios e controlar como os usuários interagem com o navegador da Web Safari no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune; seodec18
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 80eb088063522ba3acb293776064fd98846b9a3e
ms.sourcegitcommit: 8e3a20b2ad59d3a6789ee81b9cbe6d2c711da11d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2019
ms.locfileid: "54380499"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo iOS para permitir ou restringir recursos usando o Intune

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos iOS. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, permitir ou restringir aplicativos específicos e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos iOS.

## <a name="before-you-begin"></a>Antes de começar
[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md).

## <a name="general"></a>Geral

- **Compartilhar dados de uso**: Escolha **Bloquear** para impedir o dispositivo de enviar dados de diagnóstico e uso para a Apple. **Não configurado** permite o envio desses dados.
  - **Envio de dados de diagnóstico**: A opção **Bloquear** impede o usuário de alterar as configurações de envio de diagnóstico e análise do aplicativo em **Diagnóstico e Uso** (Configurações do dispositivo). Para usar essa configuração, o dispositivo deve estar no modo supervisionado (iOS 9.3.2 ou superior). **Não configurado** permite que o usuário altere as configurações do dispositivo.
- **Captura de tela**: Escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo. **Não configurado** permite que o usuário capture o conteúdo da tela como uma imagem.
  - **Observação de tela remota pelo aplicativo Classroom (somente supervisionado)**: Escolha **Bloquear** para impedir o aplicativo Classroom de exibir remotamente a tela no dispositivo. Para usar essa configuração, o dispositivo deve estar no modo supervisionado (iOS 9.3 ou superior). **Não configurado** permite que o aplicativo Classroom da Apple veja a tela.
  - **Observação de tela não solicitada pelo aplicativo Classroom (somente supervisionado)**: Se essa opção é definida como **Permitir**, os professores podem observar silenciosamente a tela dos dispositivos iOS dos alunos usando o aplicativo Classroom sem o conhecimento deles. Os dispositivos de alunos registrados em uma aula por meio do aplicativo Classroom concedem automaticamente a permissão ao professor do curso. **Não configurado** impede esse recurso.
- **Certificados TLS não confiáveis**: Escolha **Bloquear** para impedir certificados TLS não confiáveis no dispositivo. **Não configurado** permite certificados TLS.
- **Confiança em aplicativos empresariais**: Escolha **Bloquear** para remover o botão **Confiar em Desenvolvedor Empresarial** em Configurações > Geral > Perfis e Gerenciamento de Dispositivos no dispositivo. **Não configurado** permite que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Modificação de conta (somente supervisionado)**: Quando essa opção é definida como **Bloquear**, o usuário não pode atualizar as configurações específicas do dispositivo no aplicativo de configurações do iOS. Por exemplo, o usuário não pode criar novas contas de dispositivo ou alterar o nome de usuário ou a senha. **Não configurado** permite que os usuários alterem as configurações.
  Esse recurso também se aplica às configurações acessíveis pelo aplicativo Ajustes do iOS, como Mail, Contatos, Calendário, Twitter e mais. Esse recurso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo Ajustes do iOS, por exemplo, o aplicativo Microsoft Outlook.
- **Habilitando restrições nas configurações do dispositivo (somente supervisionado)**: Escolha **Bloquear** para impedir os usuários de habilitar restrições nas configurações do dispositivo. **Não configurado** permite que o usuário configure restrições de dispositivo (como controles parentais) no dispositivo.
- **Uso da opção Apagar todo o conteúdo e as configurações no dispositivo (somente supervisionado)**: Escolha **Bloquear** para que os usuários não possam usar a opção Apagar todo o conteúdo e as configurações no dispositivo (somente supervisionado). **Não configurado** fornece aos usuários acesso a essas configurações.
- **Modificação do nome do dispositivo (somente supervisionado)**: Escolha **Bloquear** para que o nome do dispositivo não possa ser alterado. **Não configurado** permite que o usuário altere o nome do dispositivo.
- **Modificação das configurações de notificação (somente supervisionado)**: Escolha **Bloquear** para que as configurações de notificação não possam ser alteradas. **Não configurado** permite que o usuário altere as configurações de notificação do dispositivo.
- **Modificação do papel de parede (somente supervisionado)**: A opção **Bloquear** impede que o papel de parede seja alterado. **Não configurado** permite que o usuário altere o papel de parede no dispositivo.
- **Modificação das configurações de confiança em aplicativos empresariais (somente supervisionado)**: A opção **Bloquear** impede o usuário de alterar as configurações de confiança em aplicativos empresariais nos dispositivos supervisionados. **Não configurado** permite que o usuário confie em aplicativos que não foram baixados da loja de aplicativos.
- **Alterações do perfil de configuração (somente supervisionado)**: A opção **Bloquear** impede alterações do perfil de configuração no dispositivo. **Não configurado** permite que o usuário instale perfis de configuração.
- **Bloqueio de Ativação (somente supervisionado)**: Escolha **Permitir** para habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados. O Bloqueio de Ativação dificulta a reativação de um dispositivo perdido ou roubado.
- **Bloquear remoção de aplicativo (somente supervisionado)**: Escolha **Bloquear** para impedir os usuários de remover aplicativos. **Não configurado** permite que os usuários removam aplicativos do dispositivo.
- **Bloquear Modo restrito de USB (somente supervisionado)**: Escolha **Bloquear** para desabilitar o Modo restrito de USB nos dispositivos supervisionados. O modo USB Restrito bloqueia a troca de dados de acessórios USB com um dispositivo que está bloqueado há mais de uma hora. **Não configurado** permite o modo USB Restrito.
- **Forçar data e hora automáticas (somente supervisionado)**: A opção **Exigir** força os dispositivos supervisionados a definir a Data e a Hora automaticamente. O fuso horário do dispositivo é atualizado quando o dispositivo está conectado à rede celular ou ao Wi-Fi e com os serviços de localização habilitados.
- **Exigir que os alunos solicitem permissão para sair do curso do Classroom (somente supervisionado)**: A opção **Exigir** força os alunos registrados em um curso não gerenciado que usam o aplicativo Classroom a solicitar a permissão do professor para sair do curso. Disponível apenas no iOS 11.3 e superior. **Não configurado** não força o aluno a pedir permissão.
- **Permitir atualizações de PKI aéreo**: Com a opção **Permitir**, os usuários podem receber atualizações de software sem conectar seus dispositivos a um computador.
- **Limitar o acompanhamento de anúncio**: Escolha **Limitar** para desabilitar o identificador de publicidade do dispositivo. **Não configurado** mantém habilitado.
- **Bloquear criação de VPN (somente supervisionado)**: A opção **Bloquear** impede os usuários de criar definições de configuração de VPN. **Não configurado** permite aos usuários criar VPNs no dispositivo.

## <a name="configurations-requiring-supervision"></a>Configurações que exigem supervisão

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

## <a name="password"></a>Senha

- **Senha**: Exige que o usuário final insira uma senha para acessar o dispositivo. Não configurado permite que os usuários acessem o dispositivo sem inserir uma senha.
  - **Senhas simples**: Escolha **Bloquear** para exigir senhas mais complexas. **Não configurado** permite senhas simples, como `0000` e `1234`.
  - **Tipo de senha necessária**: Escolha o tipo de senha exigido por sua organização. Suas opções:
    - **Padrão do dispositivo**
    - **Numérica**
    - **Alfanumérica**
  - **Número de caracteres não alfanuméricos na senha**: Insira o número de caracteres de símbolo, como `#` ou `@`, que precisa ser incluído na senha.
  - **Comprimento mínimo da senha**: Insira o tamanho mínimo que um usuário precisa inserir (entre 4 e 14 caracteres).
  - **Número de falhas de início de sessão antes de limpar o dispositivo**: Insira o número de falhas de entrada permitido antes do dispositivo ser apagado (entre 1 e 11).
  - **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**<sup>1</sup>: Insira por quanto tempo o dispositivo permanecerá ocioso antes que o usuário precise inserir novamente sua senha. Se o tempo inserido for maior do que o valor definido no dispositivo, o dispositivo ignorará o tempo inserido por você. Compatível com dispositivos iOS 8.0 e mais recentes.
  - **Máximo de minutos de inatividade até a tela ser bloqueada**<sup>1</sup>: Insira o número máximo de minutos de inatividade permitido no dispositivo até a tela ser bloqueada. Se o tempo inserido for maior do que o valor definido no dispositivo, o dispositivo ignorará o tempo inserido por você.
  - **Expiração da senha (dias)**: Insira o número de dias antes que a senha do dispositivo precise ser alterada.
  - **Evitar a reutilização de senhas anteriores**: Insira o número de novas senhas que precisam ser usadas até que uma antiga possa ser reutilizada.
  - **Desbloqueio por impressão digital**: Escolha **Bloquear** para impedir o uso de uma impressão digital para desbloquear o dispositivo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando uma impressão digital.
- **Modificação de senha (somente supervisionado)**: Escolha **Bloquear** para impedir que a senha seja alterada, adicionada ou removida. As alterações às restrições de senha são ignoradas em dispositivos supervisionados após o bloqueio desse recurso. **Não configurado** permite a adição, alteração ou remoção das senhas.
  - **Modificação de impressão digital (somente supervisionado)**: A opção **Bloquear** impede o usuário de alterar, adicionar ou remover impressões digitais do Touch ID. **Não configurado** permite que o usuário atualize as impressões digitais TouchID no dispositivo.
- **Bloquear o AutoPreenchimento de senha (somente supervisionado)**: Escolha **Bloquear** para impedir o uso do recurso AutoPreenchimento de Senhas no iOS. Escolher **Bloquear** também faz o seguinte:
  - Os usuários não receberão uma solicitação para usar uma senha salva no Safari ou em qualquer outro aplicativo.
  - As senhas fortes automáticas ficam desabilitadas, e o usuário não recebe sugestões de senhas fortes.

  **Não configurado** permite esses recursos.

- **Bloquear solicitações de proximidade de senha (somente supervisionado)**: Escolha **Bloquear** para que o dispositivo de um usuário não solicite senhas de dispositivos próximos. **Não configurado** permite essas solicitações de senha.
- **Bloquear o compartilhamento de senha (somente supervisionado)**: A opção **Bloquear** impede o compartilhamento de senhas entre dispositivos usando o AirDrop. **Não configurado** permite o compartilhamento das senhas.

<sup>1</sup>Se você definir as configurações **Máximo de minutos de inatividade até o bloqueio da tela** e **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**, elas são aplicadas em sequência. Por exemplo, se você definir o valor das duas configurações como **5** minutos, a tela desligará automaticamente após cinco minutos e o dispositivo será bloqueado após outros cinco minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo será bloqueado cinco minutos depois que o usuário desligar a tela.

## <a name="locked-screen-experience"></a>Experiência de tela bloqueada

- **Acesso ao Centro de Controle quando o dispositivo estiver bloqueado**: Escolha **Bloquear** para impedir o acesso ao aplicativo Centro de Controle quando o dispositivo estiver bloqueado. **Não configurado** permite que o usuário acesse o aplicativo Centro de Controle quando o dispositivo estiver bloqueado.
- **Notificações quando o dispositivo estiver bloqueado**: A opção **Bloquear** impede o acesso às notificações quando o dispositivo está bloqueado. **Não configurado** permite que o usuário acesse as notificações sem desbloquear o dispositivo.
- **Notificações da Carteira quando o dispositivo estiver bloqueado**: A opção **Bloquear** impede o acesso ao aplicativo Carteira quando o dispositivo está bloqueado. **Não configurado** permite ao usuário acessar o aplicativo Wallet enquanto o dispositivo estiver bloqueado.
- **Exibição Hoje quando o dispositivo está bloqueado**: A opção **Bloquear** impede o acesso à exibição Hoje quando o dispositivo está bloqueado. **Não configurado** permite que o usuário veja a visualização Hoje quando o dispositivo estiver bloqueado.

## <a name="app-store-doc-viewing-gaming"></a>Loja de Aplicativos, Exibição de Documentos, Jogos

- **App Store**: A opção **Bloquear** impede o acesso à App Store nos dispositivos supervisionados. **Não configurado** permite o acesso.
  - **Instalando aplicativos da App Store (somente supervisionado)**: Escolha **Bloquear** para bloquear a App Store na tela inicial do dispositivo. Os usuários finais podem continuar a usar o iTunes ou o Apple Configurator para instalar aplicativos. **Não configurado** permite a App Store na tela inicial.
  - **Downloads automáticos de aplicativo (somente supervisionado)**: Escolha **Bloquear** para impedir o download automático de aplicativos comprados em outros dispositivos. Isso não afeta as atualizações dos aplicativos existentes. **Não configurado** permite o download dos aplicativos comprados em outros dispositivos iOS para o dispositivo.
- **Senha para acessar a App Store**: **Exija** que o usuário insira uma senha antes de visitar a loja de aplicativos. **Não configurado** permite o acesso à loja de aplicativos sem inserir uma senha.
- **Compras no aplicativo**: Escolha **Bloquear** para impedir compras no aplicativo por meio da loja. **Não configurado** permite compras na loja em um aplicativo em execução.
- **Conteúdo adulto de música, podcast ou notícias do iTunes (somente supervisionado)**: Escolha **Bloquear** para impedir o conteúdo adulto de música, podcast ou notícias do iTunes. **Não configurado** permite ao dispositivo acessar o conteúdo classificado como adulto na loja.
- **Baixar conteúdo da iBook Store sinalizado como 'Erotismo'**: Escolha **Bloquear** para impedir os usuários de baixar uma mídia da iBook Store que esteja marcada como Erotismo. **Não configurado** permite que o usuário baixe livros da categoria "Erotismo".
- **Exibindo documentos corporativos em aplicativos não gerenciados**: A opção **Bloquear** impede a exibição de documentos não corporativos em aplicativos não gerenciados. **Não configurado** permite que documentos corporativos sejam exibidos em qualquer aplicativo. Por exemplo, você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como **Bloquear**. Após o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permite mais salvar.
  - **Permitir que aplicativos gerenciados gravem contatos em contas de contatos não gerenciadas**: Quando essa opção é definida como **Permitir**, os usuários podem adicionar ou sincronizar as informações de contato do Outlook de qualquer pessoa, incluindo contatos empresariais e corporativos, ao/com o aplicativo Contatos interno do dispositivo. Quando essa opção é definida como **Não configurado**, os usuários não podem adicionar contatos do Outlook ao aplicativo Contatos interno do dispositivo.
  
    Para usar essa configuração, defina a configuração **Exibindo documentos corporativos em aplicativos não gerenciados** como **Bloquear**.
  
- **Exibindo documentos não corporativos em aplicativos corporativos**: A opção **Bloquear** impede a exibição de documentos não corporativos em aplicativos corporativos. **Não configurado** permite que qualquer documento seja exibido em aplicativos gerenciados corporativos.
  - **Permitir que aplicativos não gerenciados leiam contas de contatos gerenciadas**: Quando essa opção é definida como **Permitir**, os usuários podem adicionar as informações de contato do aplicativo iContacts de qualquer pessoa ao Outlook. A opção **Não configurado** impede a leitura, incluindo a remoção de duplicatas, do aplicativo Contatos interno do dispositivo.
  
    Para usar essa configuração, defina a configuração **Exibindo documentos não corporativos em aplicativos corporativos** como **Bloquear**.
  
- **Tratar o AirDrop como um destino não gerenciado**: A opção **Exigir** força o AirDrop a ser considerado uma reprodução automática não gerenciada. Isso impede que os aplicativos gerenciados enviem dados usando o Airdrop. 
- **Adicionando amigos do Game Center (somente supervisionado)**: A opção **Bloquear** impede os usuários de adicionar amigos do Game Center. **Não configurado** permite que o usuário adicione amigos ao Game Center.
- **Game Center (somente supervisionado)**: **Bloqueie** o uso do aplicativo Game Center. **Não configurado** permite o uso do aplicativo Game Center no dispositivo.
- **Jogos para múltiplos jogadores (somente supervisionado)**: Escolha **Bloquear** para impedir jogos para múltiplos jogadores. **Não configurado** permite que o usuário execute jogos para vários participantes no dispositivo.
- **Região de classificação**: Escolha a região de classificação que deseja usar para downloads permitidos. E, em seguida, escolha as classificações permitidas para **Filmes** e **Programas de TV**.
- **Aplicativos**: Escolha a classificação de idade permitida dos aplicativos que os usuários podem baixar ou escolha **Permitir Todos os Aplicativos**.

## <a name="built-in-apps"></a>Aplicativos internos

- **Câmera**: Escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não configurado** permite o acesso à câmera do dispositivo.
  - **FaceTime**: Escolha **Bloquear** para impedir o acesso ao aplicativo FaceTime. **Não configurado** permite o acesso ao aplicativo FaceTime no dispositivo.
- **Siri**: A opção **Bloquear** impede o acesso à Siri. **Não configurado** permite o uso da assistente de voz Siri no dispositivo.
  - **Siri quando o dispositivo estiver bloqueado**: Escolha **Bloquear** para impedir o acesso à Siri quando o dispositivo estiver bloqueado. **Não configurado** permite o uso da assistente de voz Siri no dispositivo quando ele estiver bloqueado.
  - **Filtro de profanação da Siri (somente supervisionado)**: A opção **Exigir** impede que a Siri dite ou use linguagem imprópria.
  - **Siri para consultar o conteúdo da Internet gerado pelo usuário (somente supervisionado)**: A opção **Bloquear** impede que a Siri acesse sites para responder a perguntas. **Não configurado** permite que a Siri acesse conteúdo gerado pelo usuário na Internet.
- **Apple News (somente supervisionado)**: Escolha **Bloquear** para impedir o acesso ao aplicativo Apple News no dispositivo. **Não configurado** permite o uso do aplicativo Apple News.
- **iBooks Store (somente supervisionado)**: A opção **Bloquear** impede o acesso à iBooks Store. **Não configurado** permite aos usuários procurar e comprar livros na loja do iBooks.
- **Aplicativo Mensagens no dispositivo (somente supervisionado)**: Escolha **Bloquear** para que os usuários não possam usar o aplicativo Mensagens no dispositivo. **Não configurado** permite o uso do aplicativo Mensagens para enviar e ler mensagens de texto.
- **Podcasts (somente supervisionado)**: A opção **Bloquear** impede os usuários de usar o aplicativo Podcasts. **Não configurado** permite o uso do aplicativo Podcasts.
- **Serviço de Música (somente supervisionado)**: A opção **Bloquear** reverte o aplicativo Música para o modo clássico e desabilita o serviço de Música. **Não configurado** permite o uso do aplicativo Apple Music.
- **Serviço iTunes Radio (somente supervisionado)**: A opção **Bloquear** impede os usuários de usar o aplicativo iTunes Radio. **Não configurado** permite o uso do aplicativo iTunes Radio.
- **Alterações nas configurações do aplicativo Buscar Amigos (somente supervisionado)**: A opção **Bloquear** impede alterações nas configurações do aplicativo Buscar Amigos. **Não configurado** permite que o usuário altere as configurações do aplicativo Buscar Meus Amigos.
- **Pesquisa do Spotlight para retornar resultados da Internet (somente supervisionado)**: A opção **Bloquear** impede o Spotlight de retornar qualquer resultado de uma pesquisa na Internet. **Não configurado** permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.
- **Bloquear remoção de aplicativos do sistema no dispositivo (somente supervisionado)**: A opção **Bloquear** desabilita a capacidade de remover aplicativos do sistema no dispositivo. **Não configurado** permite que os usuários removam aplicativos do sistema.

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

- **Aplicativos proibidos**: Uma lista de aplicativos não gerenciados pelo Intune que você não deseja que sejam instalados no dispositivo. Se um usuário instalar um aplicativo dessa lista, você será notificado pelo Intune.
- **Aplicativos aprovados**: Uma lista de aplicativos que os usuários têm permissão para instalar. Para permanecer em conformidade, os usuários não devem instalar outros aplicativos. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente. Se um usuário instalar um aplicativo dessa lista, você será notificado pelo Intune.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar** a URL da iTunes App Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.

- Importar um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app url>, <app name>, <app publisher>`. Ou exporte uma lista existente que contém a lista de aplicativos restritos no mesmo formato.

> [!IMPORTANT]
> Os perfis de dispositivo que usam configurações de aplicativo restrito devem ser atribuídos a grupos de usuários.

## <a name="show-or-hide-apps-supervised-only"></a>Mostrar ou ocultar aplicativos (somente supervisionado)

Na lista para mostrar ou ocultar aplicativos, você pode configurar uma destas listas em dispositivos supervisionados que estão executando o iOS 9.3 ou posterior.

- **Aplicativos ocultos**: Insira uma lista de aplicativos ocultados dos usuários. Os usuários não podem exibir ou abrir esses aplicativos.
- **Aplicativos visíveis**: Insira uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar** a URL da iTunes App Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.

- Importar um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato `<app url>, <app name>, <app publisher>`. Ou exporte uma lista existente que contém a lista de aplicativos restritos no mesmo formato.

## <a name="wireless"></a>Sem fio

- **Roaming de dados**: Escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** permite o roaming de dados quando o dispositivo estiver em uma rede celular.
- **Busca global em segundo plano durante o roaming**: A opção **Bloquear** impede o uso do recurso de busca global em segundo plano durante o roaming na rede celular. **Não configurado** permite ao dispositivo buscar dados, como emails, durante roaming em uma rede celular.
- **Discagem de voz**: Escolha **Bloquear** para impedir os usuários de usar o recurso de discagem de voz no dispositivo. **Não configurado** permite a discagem por voz no dispositivo.
- **Roaming de voz**: Escolha **Bloquear** para impedir o roaming de voz na rede celular. **Não configurado** permite o roaming de voz quando o dispositivo estiver em uma rede celular.
- **Alterações nas configurações de uso dos dados da rede celular do aplicativo (somente supervisionado)**: Escolha **Bloquear** para impedir alterações nas configurações de uso dos dados da rede celular do aplicativo. **Não configurado** permite ao usuário controlar quais aplicativos têm permissão para usar dados de celular.
- **Hotspot pessoal**: A opção **Bloquear** impede que o dispositivo seja usado como um hotspot pessoal. Essa configuração pode não ser compatíveis com algumas operadoras. **Não configurado** permite o uso desse recurso.
- **Ingressar em redes Wi-Fi usando somente perfis de configuração (somente supervisionado)**: A opção **Exigir** força o dispositivo a usar somente as redes Wi-Fi configuradas por meio de perfis de configuração do Intune. **Não configurado** permite que o dispositivo use outras redes Wi-Fi.
- **Regras de uso da rede celular (somente aplicativos gerenciados)**: Defina os tipos de dados que poderão ser usados por aplicativos gerenciados quando estiverem em redes celulares. Suas opções:
  - **Bloquear uso de dados da rede celular**: Bloqueie o uso de dados da rede celular para **Todos os aplicativos gerenciados** ou use **Escolher aplicativos específicos**.
  - **Bloquear o uso de dados da rede celular durante o roaming**: Bloqueie o uso de dados da rede celular durante o roaming para **Todos os aplicativos gerenciados** ou use **Escolher aplicativos específicos**.

## <a name="connected-devices"></a>Dispositivos conectados

- **AirDrop (somente supervisionado)**: A opção **Bloquear** impede o uso do AirDrop no dispositivo. **Não configurado** permite o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
- **Emparelhamento do Apple Watch (somente supervisionado)**: A opção **Bloquear** impede o emparelhamento com um Apple Watch. **Não configurado** permite que o dispositivo emparelhe com um Apple Watch.
- **Detecção de pulso para um Apple Watch emparelhado**: A opção **Exigir** força um Apple Watch emparelhado a usar a detecção de pulso. Quando exigido, o Apple Watch não exibirá notificações quando não estiver sendo usado. 
- **Modificação do Bluetooth (somente supervisionado)**: A opção **Bloquear** impede o usuário final de alterar as configurações do Bluetooth no dispositivo. **Não configurado** permite que o usuário altere essas configurações.
- **Emparelhamento de host para controlar os dispositivos com os quais um dispositivo iOS pode ser emparelhado (somente supervisionado)**: A opção **Não configurado** permite o emparelhamento de host para que administrador possa controlar quais dispositivos podem ser emparelhados com um dispositivo iOS. **Bloquear** impede o emparelhamento do host.
- **Exigir uma senha de emparelhamento para solicitações de saída do AirPlay**: **Exija** uma senha de emparelhamento quando o usuário usar o AirPlay para transmitir conteúdo para outros dispositivos Apple. **Não configurado** permite que o usuário transmita conteúdo usando AirPlay sem inserir uma senha.
- **Bloquear o AirPrint (somente supervisionado)**: Escolha **Bloquear** para impedir o uso do recurso AirPrint no dispositivo. **Não configurado** permite que o usuário utilize o AirPrint.
  - **Bloquear o armazenamento das credenciais do AirPrint no Conjunto de Chaves (somente supervisionado)**: A opção **Bloquear** impede o uso do armazenamento do Conjunto de Chaves para o nome de usuário e a senha no dispositivo. **Não configurado** permite o armazenamento do nome de usuário e senha do AirPrint no aplicativo Keychain.
  - **Exigir um certificado TLS confiável para o AirPrint (somente supervisionado)**: A opção **Exigir** força o dispositivo a usar certificados confiáveis para comunicação de impressão do TLS.
  - **Bloquear a descoberta do iBeacon de impressoras do AirPrint (somente supervisionado)**: A opção **Bloquear** impede o phishing de beacons Bluetooth mal-intencionados do AirPrint em busca do tráfego de rede. **Não configurado** permite a publicidade de impressoras AirPrint no dispositivo.

## <a name="keyboard-and-dictionary"></a>Teclado e dicionário

- **Pesquisa de definição de palavra (somente supervisionado)**: A opção **Bloquear** impede o usuário de realçar uma palavra e, em seguida, pesquisar sua definição no dispositivo. **Não configurado** permite o acesso ao recurso de pesquisa de definição.
- **Teclados preditivos (somente supervisionado)**: A opção **Não configurado** permite o uso de teclados preditivos para sugerir palavras que talvez o usuário deseje saber. **Bloquear** impede esse recurso.
- **Correção automática (somente supervisionado)**: A opção **Não configurado** permite que o dispositivo corrija automaticamente palavras com ortografia incorreta. **Bloquear** impede o uso da correção automática.
- **Verificação ortográfica do teclado (somente supervisionado)**: A opção **Não configurado** permite o uso do verificador ortográfico no dispositivo. **Bloquear** permite a correção ortográfica.
- **Atalhos de teclado (somente supervisionado)**: A opção **Não configurado** permite o uso de atalhos de teclado no dispositivo. **Bloquear** impede o uso de atalhos de teclado.
- **Ditado (somente supervisionado)**: A opção **Bloquear** impede o usuário de usar a entrada de voz para inserir um texto. **Não configurado** permite que o utilizar a entrada por ditado.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Backup no iCloud**: A opção **Não configurado** permite que o usuário faça backup do dispositivo no iCloud. **Bloquear** impede que o usuário faça backup do dispositivo no iCloud.
- **Sincronização de documento com o iCloud (somente supervisionado)**: A opção **Não configurado** permite a sincronização de documento e chave-valor com o espaço de armazenamento do iCloud. **Bloquear** impede o iCloud de sincronizar documentos e dados.
- **Sincronização do fluxo de fotos com o iCloud**: A opção **Não configurado** permite que os usuários habilitem **Meu Fluxo de Fotos** em seus dispositivos para sincronização com o iCloud e disponibilizem as fotos em todos os dispositivos do usuário. **Bloquear** impede a sincronização de fluxo de fotos com o iCloud.
- **Backup criptografado**: **Exija** essa opção para que os backups de dispositivo sejam criptografados.
- **Biblioteca de Fotos do iCloud**: Defina essa opção como **Bloquear** para desabilitar o uso da Biblioteca de Fotos do iCloud para armazenar fotos e vídeos na nuvem. As fotos que não forem totalmente baixadas da Biblioteca de Fotos do iCloud para o dispositivo serão removidas do dispositivo. **Não configurado** permite o uso da Biblioteca de Fotos do iCloud.
- **Sincronização de aplicativos gerenciados com a nuvem**: A opção **Não configurado** permite que os aplicativos gerenciados pelo Intune sincronizem dados com a conta do iCloud do usuário. **Bloquear** impede essa sincronização de dados com o iCloud.
- **Fluxo de fotos compartilhado**: Escolha **Bloquear** para desabilitar o **Compartilhamento de Fotos do iCloud** no dispositivo. **Não configurado** permite a transmissão de fotos compartilhadas.
- **Continuação da atividade**: A opção **Não configurado** permite que o usuário continue o trabalho iniciado em um dispositivo iOS em outro dispositivo iOS ou macOS (Entrega). **Bloquear** impede o Handoff.
- **Bloquear a sincronização do Conjunto de Chaves do iCloud**: Escolha **Bloquear** para desabilitar a sincronização das credenciais armazenadas no Conjunto de Chaves com o iCloud. **Não configurado** permite que os usuários sincronizem essas credenciais.
- **Bloquear o Backup de Livros da Empresa**: Escolha **Bloquear** para impedir os usuários de fazer backup de livros da empresa. **Não configurado** permite que os usuários façam backup desses livros.
- **Bloquear a sincronização de metadados de livros da empresa (anotações e destaques)**: A opção **Bloquear** impede a sincronização de anotações e destaques em livros da empresa. **Não configurado** permite a sincronização.

## <a name="autonomous-single-app-mode-supervised-only"></a>Modo autônomo de único aplicativo (somente supervisionado)

Use essas opções para configurar dispositivos iOS para executar aplicativos específicos no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado. Ele só pode executar esse aplicativo. Por exemplo, adicione um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

Para adicionar aplicativos, você pode:

- Inserir o **Nome do aplicativo** e a **ID do pacote de aplicativo** e selecionar **Adicionar**. A [Referência da ID do pacote para aplicativos iOS nativos](#bundle-id-reference-for-built-in-ios-apps) (neste artigo) inclui alguns aplicativos com suas IDs.
- **Importar** um arquivo CSV com a lista de nomes de aplicativo e suas IDs de pacote. Ou **Exportar** uma lista existente que contém os aplicativos.

## <a name="kiosk-supervised-only"></a>Quiosque (somente supervisionado)

- **Aplicativo a ser executado no modo de quiosque**: Escolha o tipo de aplicativos que deseja executar no modo de quiosque. Suas opções: 
  - **Aplicativo da Loja**: Insira a URL de um aplicativo na iTunes App Store
  - **Aplicativo Gerenciado**: Escolha um aplicativo que você adicionou ao Intune
  - **Aplicativo Interno**: Insira a [ID do pacote](#bundle-id-reference-for-built-in-ios-apps) do aplicativo nativo

- **Toque assistencial**: **Exija** a configuração de acessibilidade Toque assistencial no dispositivo. Esse recurso ajuda os usuários proporcionando gestos na tela que podem ser difíceis. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Inverter cores**: **Exija** a configuração de acessibilidade Inverter Cores, para que os usuários com deficiências visuais possam alterar a exibição da tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Áudio mono**: **Exija** a configuração de acessibilidade Áudio mono no dispositivo. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **VoiceOver**: **Exija** a configuração de acessibilidade VoiceOver no dispositivo para ler o texto na tela em voz alta. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Zoom**: **Exija** a configuração de Zoom no dispositivo para permitir que os usuários usem o toque para ampliar a tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Bloqueio automático**: **Permita** o bloqueio automático do dispositivo. **Não configurado** desabilita esse recurso.
- **Botão de toque**: **Permita** a opção de botão de toque (mudo) no dispositivo. **Não configurado** desabilita esse recurso.
- **Rotação da tela**: **Permita** a alteração da orientação da tela quando o usuário girar o dispositivo. **Não configurado** desabilita esse recurso.
- **Botão Suspender tela**: Escolha **Permitir** para desabilitar o botão de ativação e suspensão da tela no dispositivo. **Não configurado** habilita esse recurso.
- **Toque**: A opção **Bloquear** desabilita a tela touch no dispositivo. **Não configurado** permite que o usuário utilize a tela sensível ao toque.
- **Botões de volume**: **Permita** o uso dos botões de volume no dispositivo. **Não configurado** desabilita os botões de volume.
- **Controle de toque assistencial**: Com a opção **Permitir**, os usuários podem usar a função de toque assistencial. **Não configurado** desabilita esse recurso.
- **Controle Inverter cores**: **Permita** alterações de inversão de cores para permitir que os usuários ajustem a função de inversão de cores. **Não configurado** desabilita esse recurso.
- **Falar o texto selecionado**: **Permita** as configurações de acessibilidade Falar Seleção no dispositivo. Esse recurso lê o texto que o usuário seleciona em voz alta. **Não configurado** desabilita esse recurso.
- **Controle de VoiceOver**: **Permita** alterações do VoiceOver para que os usuários possam atualizar a função VoiceOver, como a velocidade de leitura do texto na tela. **Não configurado** impede alterações ao VoiceOver.
- **Controle de zoom**: **Permita** alterações de zoom pelo usuário. **Não configurado** impede alterações de zoom.

> [!NOTE]
> Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar a ferramenta Apple Configurator ou o Programa de registro de dispositivos da Apple para colocar o dispositivo no modo supervisionado. Consulte o guia da Apple sobre como usar a ferramenta Apple Configurator.
> Se o aplicativo iOS que você especificar for instalado após a atribuição do perfil, o dispositivo não entrará no modo de quiosque após ser reiniciado.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referência de ID de Pacote para aplicativos iOS internos

Esta lista mostra a ID de pacote de alguns aplicativos iOS internos comuns. Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software.

| ID do Pacote                   | Nome do Aplicativo     | Editor |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Loja de aplicativos    | Apple     |
| com.apple.calculator        | Calculadora   | Apple     |
| com.apple.mobilecal         | Calendário     | Apple     |
| com.apple.camera            | Câmera       | Apple     |
| com.apple.mobiletimer       | Relógio        | Apple     |
| com.apple.compass           | Bússola      | Apple     |
| com.apple.MobileAddressBook | Contacts     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.mobileme.fmf1     | Buscar Amigos | Apple     |
| com.apple.mobileme.fmip1    | Buscar iPhone  | Apple     |
| com.apple.gamecenter        | Game Center  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Integridade       | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Email         | Apple     |
| com.apple.Maps              | Mapas         | Apple     |
| com.apple.MobileSMS         | Mensagens     | Apple     |
| com.apple.Music             | Música        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Anotações        | Apple     |
| com.apple.Numbers           | Números      | Apple     |
| com.apple.Pages             | Páginas        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotos       | Apple     |
| com.apple.podcasts          | Podcasts     | Apple     |
| com.apple.reminders         | Lembretes    | Apple     |
| com.apple.MobileSafari      | Safari       | Apple     |
| com.apple.Preferences       | Configurações     | Apple     |
| com.apple.stocks            | Bolsa       | Apple     |
| com.apple.tips              | Dicas         | Apple     |
| com.apple.videos            | Vídeos       | Apple     |
| com.apple.VoiceMemos        | VoiceMemos   | Apple     |
| com.apple.Passbook          | Carteira       | Apple     |
| com.apple.Bridge            | Assistir        | Apple     |
| com.apple.weather           | Clima      | Apple     |

## <a name="safari"></a>Safari

- **Safari (somente supervisionado)**: **Bloqueie** o uso do navegador Safari no dispositivo. **Não configurado** permite que os usuários utilizem o navegador Safari.
- **Preenchimento Automático**: A opção **Bloquear** desabilita o recurso de preenchimento automático do Safari no dispositivo. **Não configurado** permite que os usuários alterem as configurações de preenchimento automático no navegador da Web.
- **Cookies**: Escolha como lidar com os cookies no dispositivo. Suas opções:
  - Allow
  - Bloquear todos os cookies
  - Permitir cookies dos sites visitados
  - Permitir cookies do site atual
- **JavaScript**: A opção **Bloquear** impede a execução de scripts Java no navegador do dispositivo. **Não configurado** permite scripts Java.
- **Avisos de fraude**: **Exija** a exibição de avisos de fraude no navegador da Web do dispositivo. **Não configurado** desabilita esse recurso.
- **Pop-ups**: A opção **Bloquear** desabilita o bloqueador de pop-ups no navegador da Web. **Não configurado** permite o bloqueador de pop-up.

## <a name="domains"></a>Domínios

### <a name="unmarked-email-domains"></a>Domínios de email desmarcados

No campo **URL de Domínio de Email**, adicione uma ou mais URLs à lista. Quando os usuários finais receberem um email de um domínio diferente dos domínios inseridos por você, o email será marcado como não confiável no aplicativo Mail do iOS.

### <a name="managed-web-domains"></a>Domínios da web gerenciados

No campo **URL de Domínio na Web**, adicione uma ou mais URLs à lista. Quando os documentos são baixados dos domínios inseridos, eles são considerados gerenciados. Essa configuração só se aplica a documentos baixados usando o navegador Safari.

### <a name="safari-password-autofill-domains"></a>Domínios de preenchimento automático de senha do Safari

No campo **URL do Domínio**, adicione uma ou mais URLs à lista. Os usuários só podem salvar senhas da Web das URLs nesta lista. Essa configuração se aplica somente ao navegador Safari e aos dispositivos com iOS 9.3 e posteriores no modo supervisionado. Se você não especificar URLs, será possível salvar senhas de todos os sites.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Você também pode definir configurações e restrições de dispositivo em dispositivos [macOS](device-restrictions-macos.md).
