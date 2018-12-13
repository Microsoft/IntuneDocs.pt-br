---
title: Adicionar configurações de restrições de dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione, ajuste ou crie configurações em dispositivos iOS para definir os requisitos de senha, controlar a tela bloqueada, usar os aplicativos internos, adicionar aplicativos aprovados ou restritos, lidar com dispositivos Bluetooth, conectar-se à nuvem para backup e armazenamento, habilitar o modo de quiosque, adicionar domínios e controlar como os usuários interagem com o navegador Safari no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a677742c5d2f876c0714f13c4f62d059ced98584
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728966"
---
# <a name="ios-device-restrictions-settings-list-in-microsoft-intune"></a>Lista de configurações de restrições de dispositivo iOS no Microsoft Intune

Este artigo lista e descreve todas as configurações de restrição de dispositivo que você pode definir para dispositivos iOS. Essas configurações são adicionadas a um perfil de configuração do dispositivo e, em seguida, atribuídas ou implantadas em seus dispositivos iOS usando o Microsoft Intune.

## <a name="general"></a>Geral

- **Compartilhar dados de uso**: escolha **Bloquear** para impedir que o dispositivo envie dados de telemetria de diagnóstico e de uso para a Apple. **Não configurado** permite o envio desses dados.
  - **Envio de dados de diagnóstico**: **Bloquear** impede que o usuário altere as configurações de envio de diagnóstico e análise do aplicativo em **Diagnóstico e Uso** (Configurações do dispositivo). Para usar essa configuração, o dispositivo deve estar no modo supervisionado (iOS 9.3.2 ou superior). **Não configurado** permite que o usuário altere as configurações do dispositivo.
- **Captura de tela**: escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo. **Não configurado** permite que o usuário capture o conteúdo da tela como uma imagem.
  - **Observação de tela remota pelo aplicativo Classroom (apenas supervisionado)**: escolha **Bloquear** para impedir que o aplicativo Classroom observe remotamente a tela no dispositivo. Para usar essa configuração, o dispositivo deve estar no modo supervisionado (iOS 9.3 ou superior). **Não configurado** permite que o aplicativo Classroom da Apple veja a tela.
  - **Observação da tela não solicitada pelo aplicativo Classroom (apenas supervisionado)**: se for definido como **Permitir**, os professores podem observar silenciosamente a tela dos dispositivos iOS dos alunos usando o aplicativo Classroom sem o conhecimento dos alunos. Os dispositivos de alunos registrados em uma aula por meio do aplicativo Classroom concedem automaticamente a permissão ao professor do curso. **Não configurado** impede esse recurso.
- **Certificados TLS não confiáveis**: escolha **Bloquear** para impedir certificados TLS (Transport Layer Security) não confiáveis no dispositivo. **Não configurado** permite certificados TLS.
- **Relação de confiança do aplicativo empresarial**: escolha **Bloquear** para remover o botão **Trust Enterprise Developer** em Configurações > Geral > Perfis e Gerenciamento de Dispositivo no dispositivo. **Não configurado** permite que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Modificação de conta (apenas no modo supervisionado)**: quando definido como **Bloquear**, o usuário não pode atualizar as configurações específicas do dispositivo pelo aplicativo Ajustes do iOS. Por exemplo, o usuário não pode criar novas contas de dispositivo ou alterar o nome de usuário ou a senha. **Não configurado** permite que os usuários alterem as configurações.
  Esse recurso também se aplica às configurações acessíveis pelo aplicativo Ajustes do iOS, como Mail, Contatos, Calendário, Twitter e mais. Esse recurso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo Ajustes do iOS, por exemplo, o aplicativo Microsoft Outlook.
- **Habilitar restrições nas configurações do dispositivo (apenas no modo supervisionado)**: escolha **Bloquear** para impedir que usuários habilitem restrições nas configurações do dispositivo. **Não configurado** permite que o usuário configure restrições de dispositivo (como controles parentais) no dispositivo.
- **Usar a opção apagar todo o conteúdo e as configurações no dispositivo (apenas no modo supervisionado)**: escolha **Bloquear** para que os usuários não possam utilizar a opção para apagar todo o conteúdo e as configurações no dispositivo (somente no modo supervisionado). **Não configurado** fornece aos usuários acesso a essas configurações.
- **Modificação do nome do dispositivo (apenas no modo supervisionado)**: escolha **Bloquear** para que o nome do dispositivo não possa ser alterado. **Não configurado** permite que o usuário altere o nome do dispositivo.
- **Modificação das configurações de notificação (apenas no modo supervisionado)**: escolha **Bloquear** para que as configurações de notificação não possam ser alteradas. **Não configurado** permite que o usuário altere as configurações de notificação do dispositivo.
- **Modificação de papel de parede (apenas no modo supervisionado)**: **Bloquear** impede a alteração do papel de parede. **Não configurado** permite que o usuário altere o papel de parede no dispositivo.
- **Modificação de configurações de confiança do aplicativo empresarial (apenas no modo supervisionado)**: **Bloquear** impede que o usuário altere as configurações de confiança do aplicativo corporativo em dispositivos supervisionados. **Não configurado** permite que o usuário confie em aplicativos que não foram baixados da loja de aplicativos.
- **Alterações do perfil de configuração (supervisionado apenas)**: **Bloquear** impede alterações no perfil de configuração no dispositivo. **Não configurado** permite que o usuário instale perfis de configuração.
- **Bloqueio de Ativação (somente supervisionado)** escolha **Permitir** para habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados. O Bloqueio de Ativação dificulta a reativação de um dispositivo perdido ou roubado.
- **Bloquear remoção do aplicativo (somente supervisionada)**: escolha **Bloquear** para impedir que os usuários removam aplicativos. **Não configurado** permite que os usuários removam aplicativos do dispositivo.
- **Bloqueia o modo USB restrito (somente supervisionado)**: escolha **Bloquear** para desabilitar o modo USB Restrito em dispositivos supervisionados. O modo USB Restrito bloqueia a troca de dados de acessórios USB com um dispositivo que está bloqueado há mais de uma hora. **Não configurado** permite o modo USB Restrito.
- **Forçar data e hora automáticas (somente supervisionado)**: **Exigir** força os dispositivos supervisionados a definir automaticamente a data e a hora. O fuso horário do dispositivo é atualizado quando o dispositivo está conectado à rede celular ou ao Wi-Fi e com os serviços de localização habilitados.
- **Exigir que os alunos solicitem permissão para deixar o curso da Sala de Aula (somente supervisionado)**: **Exigir** força os alunos inscritos em um curso não gerenciado por meio do aplicativo Classroom solicitem permissão do professor para sair do curso. Disponível apenas no iOS 11.3 e superior. **Não configurado** não força o aluno a pedir permissão.
- **Permitir atualizações do PKI aéreo**: **Permitir** deixa os usuários receberem as atualizações de software sem precisar conectar os dispositivos a um computador.
- **Limitar acompanhamento de anúncio**: escolha **Limitar** para desabilitar o identificador de publicidade do dispositivo. **Não configurado** mantém habilitado.
- **Bloquear a criação de VPN (somente supervisionado)**: **Bloquear** impede que usuários criem definições de configuração de VPN. **Não configurado** permite aos usuários criar VPNs no dispositivo.

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

- **Senha**: exige que o usuário final insira uma senha para acessar o dispositivo. Não configurado permite que os usuários acessem o dispositivo sem inserir uma senha.
  - **Senhas simples**: escolha **Bloquear** para exigir senhas mais complexas. **Não configurado** permite senhas simples, como `0000` e `1234`.
  - **Tipo de senha necessária**: escolha o tipo de senha exigido por sua organização. Suas opções:
    - **Padrão do dispositivo**
    - **Numérica**
    - **Alfanumérica**
  - **Número de caracteres não alfanuméricos na senha**: insira o número de caracteres de símbolo, como `#` ou `@` que devem ser incluídos na senha.
  - **Comprimento mínimo da senha**: insira o comprimento mínimo que um usuário deve inserir (entre 4 e 14 caracteres).
  - **Número de falhas de entrada antes de apagar o dispositivo**: insira quantas falhas podem ocorrer antes de o dispositivo ser apagado (entre 1 e 11).
  - **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**<sup>1</sup>: insira por quanto tempo o dispositivo deve permanecer ocioso antes que o usuário tenha que digitar novamente a senha. Se o tempo inserido for maior do que o valor definido no dispositivo, o dispositivo ignorará o tempo inserido por você. Compatível com dispositivos iOS 8.0 e mais recentes.
  - **Máximo de minutos de inatividade até o bloqueio da tela**<sup>1</sup>: inserir o número máximo de minutos de inatividade permitido antes que a tela do dispositivo seja bloqueada. Se o tempo inserido for maior do que o valor definido no dispositivo, o dispositivo ignorará o tempo inserido por você.
  - **Expiração da senha (dias)**: insira o número de dias antes que a senha do dispositivo precise ser alterada.
  - **Evitar a reutilização de senhas anteriores**: insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada.
  - **Desbloqueio de impressão digital**: escolha **Bloquear** para impedir o uso de uma impressão digital para desbloquear o dispositivo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando uma impressão digital.
- **Modificação da senha (apenas no modo supervisionado)**: escolha **Bloquear** para impedir que a senha seja alterada, adicionada ou removida. As alterações às restrições de senha são ignoradas em dispositivos supervisionados após o bloqueio desse recurso. **Não configurado** permite a adição, alteração ou remoção das senhas.
  - **Modificação de impressão digital (apenas no modo supervisionado)**: escolha **Bloquear** para impedir que o usuário altere, adicione ou remova impressões digitais TouchID. **Não configurado** permite que o usuário atualize as impressões digitais TouchID no dispositivo.
- **Bloquear o AutoPreenchimento de senha (somente supervisionado)**: escolha **Bloquear** para evitar o uso do recurso Preenchimento Automático de Senhas no iOS. Escolher **Bloquear** também faz o seguinte:
  - Os usuários não receberão uma solicitação para usar uma senha salva no Safari ou em qualquer outro aplicativo.
  - As senhas fortes automáticas ficam desabilitadas, e o usuário não recebe sugestões de senhas fortes.

  **Não configurado** permite esses recursos.

- **Bloquear solicitações de proximidade de senha (somente supervisionado)**: escolha **Bloquear** para que um dispositivo de usuário não solicite senhas de dispositivos próximos. **Não configurado** permite essas solicitações de senha.
- **Bloquear o compartilhamento de senha (somente supervisionado)**: **Bloquear** impede o compartilhamento de senhas entre dispositivos usando o AirDrop. **Não configurado** permite o compartilhamento das senhas.

<sup>1</sup>Se você definir as configurações **Máximo de minutos de inatividade até o bloqueio da tela** e **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida**, elas são aplicadas em sequência. Por exemplo, se você definir o valor das duas configurações como **5** minutos, a tela desligará automaticamente após cinco minutos e o dispositivo será bloqueado após outros cinco minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo será bloqueado cinco minutos depois que o usuário desligar a tela.

## <a name="locked-screen-experience"></a>Experiência de tela bloqueada

- **Acesso ao centro de controle enquanto o dispositivo está bloqueado**: escolha **Bloquear** para impedir o acesso ao aplicativo Centro de Controle quando o dispositivo estiver bloqueado. **Não configurado** permite que o usuário acesse o aplicativo Centro de Controle quando o dispositivo estiver bloqueado.
- **Notificações enquanto o dispositivo está bloqueado**: **Bloquear** impede o acesso às notificações quando o dispositivo estiver bloqueado. **Não configurado** permite que o usuário acesse as notificações sem desbloquear o dispositivo.
- **Notificações do Wallet enquanto o dispositivo estiver bloqueado**: **Bloquear** impede o acesso ao aplicativo Wallet quando o dispositivo estiver bloqueado. **Não configurado** permite ao usuário acessar o aplicativo Wallet enquanto o dispositivo estiver bloqueado.
- **Exibição de hoje enquanto o dispositivo está bloqueado**: **Bloquear** impede o acesso à visualização Hoje quando o dispositivo estiver bloqueado. **Não configurado** permite que o usuário veja a visualização Hoje quando o dispositivo estiver bloqueado.

## <a name="app-store-doc-viewing-gaming"></a>Loja de Aplicativos, Exibição de Documentos, Jogos

- **Loja de aplicativos**: **Bloquear** impede o acesso à loja de aplicativos em dispositivos supervisionados. **Não configurado** permite o acesso.
  - **Instalando aplicativos da App Store (apenas no modo supervisionado)**: escolha **Bloquear** para bloquear a App Store na tela inicial do dispositivo. Os usuários finais podem continuar a usar o iTunes ou o Apple Configurator para instalar aplicativos. **Não configurado** permite a App Store na tela inicial.
  - **Downloads automáticos de aplicativos (somente no modo supervisionado)**: escolha **Bloquear** para impedir o download automático de aplicativos comprados em outros dispositivos. Isso não afeta as atualizações dos aplicativos existentes. **Não configurado** permite o download dos aplicativos comprados em outros dispositivos iOS para o dispositivo.
- **Senha para acessar a loja de aplicativos**: **Exigir** que o usuário insira uma senha antes de poder visitar a loja de aplicativos. **Não configurado** permite o acesso à loja de aplicativos sem inserir uma senha.
- **Compras no aplicativo**: escolha **Bloquear** para evitar compras no aplicativo a partir da loja. **Não configurado** permite compras na loja em um aplicativo em execução.
- **Conteúdo explícito de música, podcast ou notícias do iTunes (apenas no modo supervisionado)**: escolha **Bloquear** para impedir conteúdo explícito em músicas, podcasts ou notícias do iTunes. **Não configurado** permite ao dispositivo acessar o conteúdo classificado como adulto na loja.
- **Baixar o conteúdo da iBook Store sinalizado como "Erotismo"**: escolha **Bloquear** para impedir que os usuários baixem mídias da iBook Store marcadas como erotismo. **Não configurado** permite que o usuário baixe livros da categoria "Erotismo".
- **Exibindo documentos corporativos em aplicativos não gerenciados**: **Bloquear** impede a exibição de documentos não corporativos em aplicativos não gerenciados. **Não configurado** permite que documentos corporativos sejam exibidos em qualquer aplicativo. Por exemplo, você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como **Bloquear**. Após o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permite mais salvar.
- **Exibindo documentos não corporativos em aplicativos corporativos**: **Bloquear** impede a exibição de documentos não corporativos em aplicativos corporativos. **Não configurado** permite que qualquer documento seja exibido em aplicativos gerenciados corporativos.
- **Tratar o AirDrop como um destino não gerenciado**: **Exigir** força o AirDrop a ser considerado como um destino não gerenciado. Isso impede que os aplicativos gerenciados enviem dados usando o Airdrop. 
- **Adicionar amigos do Game Center (apenas no modo supervisionado)**: **Bloquear** impede os usuários de adicionar amigos ao Game Center. **Não configurado** permite que o usuário adicione amigos ao Game Center.
- **Game Center (apenas no modo supervisionado)**: **Bloquear** o uso do aplicativo Game Center. **Não configurado** permite o uso do aplicativo Game Center no dispositivo.
- **Jogos para múltiplos jogadores (apenas no modo supervisionado)**: escolha **Bloquear** para impedir jogos para vários participantes. **Não configurado** permite que o usuário execute jogos para vários participantes no dispositivo.
- **Região de classificações**: escolha a região de classificações que você quer usar para downloads permitidos. E, em seguida, escolha as classificações permitidas para **Filmes** e **Programas de TV**.
- **Aplicativos**: escolha a classificação de idade dos aplicativos que os usuários podem baixar ou escolha **Permitir todos os aplicativos**.

## <a name="built-in-apps"></a>Aplicativos internos

- **Câmera**: escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não configurado** permite o acesso à câmera do dispositivo.
  - **FaceTime**: **Bloquear** para impedir o acesso ao aplicativo FaceTime. **Não configurado** permite o acesso ao aplicativo FaceTime no dispositivo.
- **Siri**: **Bloquear** impede o acesso à Siri. **Não configurado** permite o uso da assistente de voz Siri no dispositivo.
  - **Siri enquanto o dispositivo está bloqueado**: escolha **Bloquear** para impedir o acesso à Siri quando o dispositivo estiver bloqueado. **Não configurado** permite o uso da assistente de voz Siri no dispositivo quando ele estiver bloqueado.
  - **Filtro de profanação da Siri (somente no modo supervisionado)**: **Exigir** impede que a Siri dite ou use linguagem ofensiva.
  - **Siri para consultar conteúdo gerado pelo usuário na Internet (somente no modo supervisionado)**: **Bloquear** impede que a Siri acesse sites para responder a perguntas. **Não configurado** permite que a Siri acesse conteúdo gerado pelo usuário na Internet.
- **Apple News (apenas no modo supervisionado)**: escolha **Bloquear** para impedir o acesso ao aplicativo Apple News no dispositivo. **Não configurado** permite o uso do aplicativo Apple News.
- **iBooks store (apenas no modo supervisionado)**: **Bloquear** impede o acesso à loja do iBooks. **Não configurado** permite aos usuários procurar e comprar livros na loja do iBooks.
- **Aplicativo de mensagens no dispositivo (apenas no modo supervisionado)**: escolha **Bloquear** para que os usuários não possam usar o aplicativo Mensagens no dispositivo. **Não configurado** permite o uso do aplicativo Mensagens para enviar e ler mensagens de texto.
- **Podcasts (apenas no modo supervisionado)**: **Bloquear** impede os usuários de utilizarem o aplicativo Podcasts. **Não configurado** permite o uso do aplicativo Podcasts.
- **Serviço de Música (apenas no modo supervisionado)**: **Bloquear** reverte o aplicativo Música para o modo clássico e desabilita o Apple Music. **Não configurado** permite o uso do aplicativo Apple Music.
- **Serviço do iTunes Radio (apenas no modo supervisionado)**: **Bloquear** impede que os usuários utilizem o aplicativo iTunes Radio. **Não configurado** permite o uso do aplicativo iTunes Radio.
- **Alterações nas configurações do aplicativo Find My Friends (apenas no modo supervisionados)**: **Bloquear** impede alterações nas configurações do aplicativo Buscar Meus Amigos. **Não configurado** permite que o usuário altere as configurações do aplicativo Buscar Meus Amigos.
- **Pesquisa de destaque para retornar resultados da Internet (somente no modo supervisionado)**: **Bloquear** impede que o Spotlight retorne qualquer resultado de uma pesquisa na Internet. **Não configurado** permite que a pesquisa do Spotlight se conecte à Internet para fornecer resultados de pesquisa.
- **Bloquear a remoção dos aplicativos do sistema do dispositivo (somente supervisionado)**: escolher **Bloquear** desabilita a capacidade de remover aplicativos do sistema do dispositivo. **Não configurado** permite que os usuários removam aplicativos do sistema.

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

- **Aplicativos proibidos**: uma lista de aplicativos não gerenciados pelo Intune que você não deseja que sejam instalados no dispositivo. Se um usuário instalar um aplicativo dessa lista, você será notificado pelo Intune.
- **Aplicativos aprovados**: uma lista de aplicativos que os usuários têm permissão de instalar. Para permanecer em conformidade, os usuários não devem instalar outros aplicativos. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente. Se um usuário instalar um aplicativo dessa lista, você será notificado pelo Intune.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar** a URL da iTunes App Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.

- Importar um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato <app url>, <app name> ou <app publisher>. Ou exporte uma lista existente que contém a lista de aplicativos restritos no mesmo formato.

> [!IMPORTANT]
> Os perfis de dispositivo que usam configurações de aplicativo restrito devem ser atribuídos a grupos de usuários.

## <a name="show-or-hide-apps-supervised-only"></a>Mostrar ou ocultar aplicativos (somente supervisionado)

Na lista para mostrar ou ocultar aplicativos, você pode configurar uma destas listas em dispositivos supervisionados que estão executando o iOS 9.3 ou posterior.

- **Aplicativos ocultos**: insira uma lista de aplicativos ocultos. Os usuários não podem exibir ou abrir esses aplicativos.
- **Aplicativos visíveis**: insira uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Para adicionar aplicativos a essas listas, você pode:

- **Adicionar** a URL da iTunes App Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Pastas de Trabalho da Microsoft, insira `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Para localizar a URL de um aplicativo, abra a iTunes App Store e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop` ou `Microsoft Word`. Selecione o aplicativo e copie a URL.

  Você também pode usar o iTunes para encontrar o aplicativo e, depois, usar a tarefa **Copiar Link** para obter a URL do aplicativo.

- Importar um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato <app url>, <app name> ou <app publisher>. Ou exporte uma lista existente que contém a lista de aplicativos restritos no mesmo formato.

## <a name="wireless"></a>Sem fio

- **Roaming de dados**: escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** permite o roaming de dados quando o dispositivo estiver em uma rede celular.
- **Busca global em segundo plano quando em roaming**: **Bloquear** impede o uso do recurso de busca global em segundo plano durante roaming em rede celular. **Não configurado** permite ao dispositivo buscar dados, como emails, durante roaming em uma rede celular.
- **Discagem de voz**: escolha **Bloquear** para impedir o uso do recurso de discagem por voz no dispositivo. **Não configurado** permite a discagem por voz no dispositivo.
- **Roaming de voz**: escolha **Bloquear** para impedir o roaming de voz pela rede celular. **Não configurado** permite o roaming de voz quando o dispositivo estiver em uma rede celular.
- **Alterações nas configurações de uso de dados para celular do aplicativo (apenas no modo supervisionado)**: escolha **Bloquear** para evitar alterações às configurações de uso de dados da rede celular do aplicativo. **Não configurado** permite ao usuário controlar quais aplicativos têm permissão para usar dados de celular.
- **Hotspot Pessoal**: **Bloquear** impede que o dispositivo seja usado como um ponto de acesso pessoal. Essa configuração pode não ser compatíveis com algumas operadoras. **Não configurado** permite o uso desse recurso.
- **Entrar nas redes Wi-Fi utilizando somente perfis de configuração (somente supervisionado)**: **Exigir** força o dispositivo a usar apenas as configurações de redes Wi-Fi por meio de perfis de configuração do Intune. **Não configurado** permite que o dispositivo use outras redes Wi-Fi.
- **Regras de uso da rede celular (somente aplicativos gerenciados)**: define os tipos de dados que os aplicativos gerenciados podem usar em redes celulares. Suas opções:
  - **Bloquear uso de dados da rede celular**: bloqueie o uso de dados da rede celular para **Todos os aplicativos gerenciados** ou **Escolha aplicativos específicos**.
  - **Bloquear uso de dados da rede celular enquanto estiver em roaming**: bloqueie o uso de dados da rede celular quando estiver em roaming para **Todos os aplicativos gerenciados** ou **Escolha aplicativos específicos**.

## <a name="connected-devices"></a>Dispositivos conectados

- **AirDrop (somente no modo supervisionado)**: **Bloquear** impede o uso do AirDrop no dispositivo. **Não configurado** permite o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
- **Emparelhamento do Apple Watch (apenas no modo supervisionado)**: **Bloquear** impede que o dispositivo emparelhe com um Apple Watch. **Não configurado** permite que o dispositivo emparelhe com um Apple Watch.
- **Detecção de pulso para Apple Watch pareado**: **Exigir** força um Apple Watch emparelhado a usar a detecção de pulso. Quando exigido, o Apple Watch não exibirá notificações quando não estiver sendo usado. 
- **Modificação de Bluetooth (apenas no modo supervisionado)**: **Bloquear** impede o usuário final de alterar as configurações de Bluetooth no dispositivo. **Não configurado** permite que o usuário altere essas configurações.
- **Emparelhamento de host para controlar os dispositivos que podem ser emparelhados com um dispositivo iOS (apenas no modo supervisionado)**: **Não configurado** permite o emparelhamento de host para que o administrador controle com quais dispositivos um dispositivo iOS pode emparelhar. **Bloquear** impede o emparelhamento do host.
- **Exigir uma senha de emparelhamento para solicitações de saída do AirPlay**: **Exigir** uma senha emparelhamento quando o usuário usar o AirPlay para transmitir o conteúdo para outros dispositivos da Apple. **Não configurado** permite que o usuário transmita conteúdo usando AirPlay sem inserir uma senha.
- **Bloquear o AirPrint (somente supervisionado)**: escolha **Bloquear** para impedir o uso do recurso AirPrint no dispositivo. **Não configurado** permite que o usuário utilize o AirPrint.
  - **Bloquear o armazenamento de credenciais do AirPrint em um Conjunto de Chaves (somente supervisionado)**: **Bloquear** impede o uso do armazenamento do Keychain para nome de usuário e senha no dispositivo. **Não configurado** permite o armazenamento do nome de usuário e senha do AirPrint no aplicativo Keychain.
  - **Exigir um certificado TLS confiável para AirPrint (somente supervisionado)**: **Exigir** força o dispositivo a usar certificados confiáveis para comunicação de impressão do TLS.
  - **Bloquear a descoberta de iBeacon de impressoras AirPrint (somente supervisionado)**: **Bloquear** impede que beacons Bluetooth mal-intencionados do AirPrint usem phishing para tráfego de rede. **Não configurado** permite a publicidade de impressoras AirPrint no dispositivo.

## <a name="keyboard-and-dictionary"></a>Teclado e dicionário

- **Pesquisa de definição de palavra (somente no modo supervisionado)**: **Bloquear** impede que o usuário realce uma palavra e, em seguida, pesquise sua definição no dispositivo. **Não configurado** permite o acesso ao recurso de pesquisa de definição.
- **Teclados preditivos (somente no modo supervisionado)**: **Não configurado** permite o uso de teclados preditivos que sugerem palavras úteis ao usuário. **Bloquear** impede esse recurso.
- **Correção automática (somente no modo supervisionado)**: **Não configurado** permite que o dispositivo corrija automaticamente palavras incorretas. **Bloquear** impede o uso da correção automática.
- **Correção ortográfica do teclado (somente no modo supervisionado)**: **Não configurado** permite o uso da correção ortográfica no dispositivo. **Bloquear** permite a correção ortográfica.
- **Atalhos do teclado (somente no modo supervisionado)**: **Não configurado** permite o uso de atalhos do teclado no dispositivo. **Bloquear** impede o uso de atalhos de teclado.
- **Ditado (somente supervisionado)**: **Bloquear** impede o uso da entrada de voz para inserir texto. **Não configurado** permite que o utilizar a entrada por ditado.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Backup no iCloud**: **Não configurado** permite ao usuário fazer backup do dispositivo no iCloud. **Bloquear** impede que o usuário faça backup do dispositivo no iCloud.
- **Sincronização de documento para iCloud (apenas no modo supervisado)**: **Não configurado** permite a sincronização de documentos e chave-valor para o espaço de armazenamento no iCloud. **Bloquear** impede o iCloud de sincronizar documentos e dados.
- **Sincronização do fluxo de fotos com o iCloud**: **Não configurado** permite que os usuários habilitem **Meu Compartilhamento** em seus dispositivos para sincronizar com o iCloud, e disponibilizem as fotos em todos os dispositivos do usuário. **Bloquear** impede a sincronização de fluxo de fotos com o iCloud.
- **Backup criptografado**: **Exigir** que quaisquer backups de dispositivo sejam criptografados.
- **Biblioteca de Fotos do iCloud**: defina como **Bloquear** para desabilitar o uso da Biblioteca de Fotos do iCloud para armazenar fotos e vídeos na nuvem. As fotos que não forem totalmente baixadas da Biblioteca de Fotos do iCloud para o dispositivo serão removidas do dispositivo. **Não configurado** permite o uso da Biblioteca de Fotos do iCloud.
- **Sincronização com a nuvem de aplicativos gerenciados**: **Não configurado** permite que os aplicativos gerenciados com o Intune sincronizem dados com a conta do iCloud do usuário. **Bloquear** impede essa sincronização de dados com o iCloud.
- **Fluxo de fotos compartilhadas**: escolha **Bloquear** para desabilitar os **Álbuns Compartilhados** no dispositivo. **Não configurado** permite a transmissão de fotos compartilhadas.
- **Continuação da atividade**: **Não configurado** permite que o usuário continue o trabalho iniciado em um dispositivo iOS em outro dispositivo iOS ou macOS (Handoff). **Bloquear** impede o Handoff.
- **Bloquear a sincronização do Conjunto de Chaves no iCloud**: escolha **Bloquear** para desabilitar a sincronização de credenciais armazenadas no Keychain com o iCloud. **Não configurado** permite que os usuários sincronizem essas credenciais.
- **Bloquear o Backup do Catálogo da Empresa**: escolha **Bloquear** para impedir os usuários de fazerem backup de livros corporativos. **Não configurado** permite que os usuários façam backup desses livros.
- **Bloquear a sincronização de metadados do catálogo da empresa (notas e destaques)**: **Bloquear** impede a sincronização de notas e grifos em livros corporativos. **Não configurado** permite a sincronização.

## <a name="autonomous-single-app-mode-supervised-only"></a>Modo autônomo de único aplicativo (somente supervisionado)

Use essas opções para configurar dispositivos iOS para executar aplicativos específicos no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado. Ele só pode executar esse aplicativo. Por exemplo, adicione um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

Para adicionar aplicativos, você pode:

- Inserir o **Nome do aplicativo** e a **ID do pacote de aplicativo** e selecionar **Adicionar**. A [Referência da ID do pacote para aplicativos iOS nativos](#bundle-id-reference-for-built-in-ios-apps) (neste artigo) inclui alguns aplicativos com suas IDs.
- **Importar** um arquivo CSV com a lista de nomes de aplicativo e suas IDs de pacote. Ou **Exportar** uma lista existente que contém os aplicativos.

## <a name="kiosk-supervised-only"></a>Quiosque (somente supervisionado)

- **Aplicativo a ser executado no modo de quiosque**: escolha o tipo de aplicativos que você deseja executar no modo de quiosque. Suas opções: 
  - **Aplicativo da loja**: insira a URL de um aplicativo na iTunes App Store
  - **Aplicativo gerenciado**: escolha um aplicativo que você adicionou ao Intune
  - **Aplicativo Interno**: insira a [ID do pacote](#bundle-id-reference-for-built-in-ios-apps) para o aplicativo nativo

- **Toque assistencial**: **Exigir** a configuração de acessibilidade AssistiveTouch no dispositivo. Esse recurso ajuda os usuários proporcionando gestos na tela que podem ser difíceis. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Inverter cores**: **Exigir** a configuração de acessibilidade Inversão de Cores, para que os usuários com deficiências visuais possam alterar a exibição da tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Áudio mono**: **Exigir** a configuração de acessibilidade Áudio Mono no dispositivo. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **VoiceOver**: **Exigir** a configuração de acessibilidade VoiceOver no dispositivo para ler o texto na tela em voz alta. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Zoom**: **Exigir** a configuração de Zoom no dispositivo para permitir que os usuários usem o toque para ampliar a tela. **Não configurado** não executa ou habilita esse recurso no modo de quiosque.
- **Bloqueio automático**: **Permitir** o bloqueio automático do dispositivo. **Não configurado** desabilita esse recurso.
- **Botão de toque**: **Permitir** a opção de botão de toque (mudo) no dispositivo. **Não configurado** desabilita esse recurso.
- **Rotação de tela**: **Permitir** a alteração da orientação da tela quando o usuário gira o dispositivo. **Não configurado** desabilita esse recurso.
- **Botão para colocar a tela em modo de suspensão**: escolha **Permitir** para desabilitar o botão de suspensão/ativação da tela no dispositivo. **Não configurado** habilita esse recurso.
- **Toque**: **Bloquear** desabilita a tela sensível ao toque no dispositivo. **Não configurado** permite que o usuário utilize a tela sensível ao toque.
- **Botões de volume**: **Permitir** o uso dos botões de volume no dispositivo. **Não configurado** desabilita os botões de volume.
- **Controle de toque assistencial**: **Permitir** deixa os usuários usarem a função AssistiveTouch. **Não configurado** desabilita esse recurso.
- **Controle Inverter cores**: **Permitir** habilita as configurações de inversão de cores para os usuários. **Não configurado** desabilita esse recurso.
- **Falar o texto selecionado**: **Permitir** as configurações de acessibilidade Falar Seleção no dispositivo. Esse recurso lê o texto que o usuário seleciona em voz alta. **Não configurado** desabilita esse recurso.
- **Controle VoiceOver**: **Permitir** alterações do VoiceOver para permitir que os usuários atualizem a função correspondente, como a velocidade de leitura do texto na tela. **Não configurado** impede alterações ao VoiceOver.
- **Controle de zoom**: **Permitir** alterações de zoom pelo usuário. **Não configurado** impede alterações de zoom.

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

- **Safari (apenas no modo supervisionado)**: **Bloquear** o uso do navegador Safari no dispositivo. **Não configurado** permite que os usuários utilizem o navegador Safari.
- **Preenchimento automático**: **Bloquear** desabilita o recurso de preenchimento automático do Safari no dispositivo. **Não configurado** permite que os usuários alterem as configurações de preenchimento automático no navegador da Web.
- **Cookies**: escolha como lidar com os cookies no dispositivo. Suas opções:
  - Permitir
  - Bloquear todos os cookies
  - Permitir cookies dos sites visitados
  - Permitir cookies do site atual
- **JavaScript**: **Bloquear** impede a execução de scripts em Java no navegador do dispositivo. **Não configurado** permite scripts Java.
- **Alertas de fraude**: **Exigir** a exibição de avisos de fraude no navegador da Web no dispositivo. **Não configurado** desabilita esse recurso.
- **Pop-ups**: **Bloquear** desabilita o bloqueador de pop-ups no navegador da Web. **Não configurado** permite o bloqueador de pop-up.

## <a name="domains"></a>Domínios

### <a name="unmarked-email-domains"></a>Domínios de email desmarcados

No campo **URL de Domínio de Email**, adicione uma ou mais URLs à lista. Quando os usuários finais receberem um email de um domínio diferente dos domínios inseridos por você, o email será marcado como não confiável no aplicativo Mail do iOS.

### <a name="managed-web-domains"></a>Domínios da web gerenciados

No campo **URL de Domínio na Web**, adicione uma ou mais URLs à lista. Quando os documentos são baixados dos domínios inseridos, eles são considerados gerenciados. Essa configuração só se aplica a documentos baixados usando o navegador Safari.

### <a name="safari-password-autofill-domains"></a>Domínios de preenchimento automático de senha do Safari

No campo **URL do Domínio**, adicione uma ou mais URLs à lista. Os usuários só podem salvar senhas da Web das URLs nesta lista. Essa configuração se aplica somente ao navegador Safari e aos dispositivos com iOS 9.3 e posteriores no modo supervisionado. Se você não especificar URLs, será possível salvar senhas de todos os sites.

## <a name="next-steps"></a>Próximas etapas

[Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
