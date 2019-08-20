---
title: Configurações de recurso de dispositivo macOS no Microsoft Intune – Azure | Microsoft Docs
description: Confira as definições para configurar dispositivos macOS para AirPrint e personalizar a janela Logon para mostrar ou ocultar botões para ligar/desligar no Microsoft Intune. Confira as etapas para obter o endereço IP, o caminho e as configurações de porta de um servidor do AirPrint em sua rede. Use essas configurações em um perfil de configuração de dispositivos para configurar os recursos do dispositivo macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63f2832dd321425efe8092f1bb12dd0d479ef71b
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69549927"
---
# <a name="macos-device-feature-settings-in-intune"></a>Configurações de recursos do dispositivo macOS no Intune

O Intune inclui algumas configurações internas para personalizar recursos em seus dispositivos macOS. Este artigo lista essas configurações e descreve o que cada uma faz. Ele também lista as etapas para obter o endereço IP, o caminho e a porta das impressoras AirPrint usando o aplicativo Terminal (emulador).

Esse recurso aplica-se a:

- macOS

Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para criar uma faixa, escolher como os usuários entram, adicionar um servidor AirPrint e mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos macOS.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo macOS](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **Endereço IP**: insira o endereço IPv4 ou IPv6 da impressora. Se você usar nomes de host para identificar impressoras, poderá obter o endereço IP executando ping dela no aplicativo Terminal. [Obter o endereço IP e o caminho](#get-the-ip-address-and-path) (neste artigo) fornece mais detalhes.
- **Caminho**: insira o caminho da impressora. Geralmente, o caminho é `ipp/print` para impressoras na rede. [Obter o endereço IP e o caminho](#get-the-ip-address-and-path) (neste artigo) fornece mais detalhes.
- **Porta** (iOS 11.0 e posterior): insira a porta de escuta do destino do AirPrint. Se você deixar essa propriedade em branco, o AirPrint usará a porta padrão.
- **TLS** (iOS 11.0 e posterior): selecione **Habilitar** para proteger conexões do AirPrint com o protocolo TLS.

**Adicione** o servidor do AirPrint. Você pode adicionar vários servidores do AirPrint.

- **Importar** (opcional): também é possível **Importar** um arquivo separado por vírgula (.csv) que inclui uma lista de impressoras AirPrint. Além disso, depois de adicionar impressoras AirPrint no Intune, você pode **Exportar** essa lista.

Selecione **OK** para salvar as configurações.

### <a name="get-the-ip-address-and-path"></a>Obter o endereço IP e o caminho

Para adicionar servidores AirPrinter, você precisa ter o endereço IP da impressora, o caminho do recurso e a porta. As etapas a seguir mostram como obter essas informações.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o **Terminal** (em **/Applications/Utilities**).
2. No aplicativo Terminal, digite `ippfind` e escolha Enter.

    Observe as informações da impressora. Por exemplo, pode retornar algo semelhante a `ipp://myprinter.local.:631/ipp/port1`. A primeira parte é o nome da impressora. A última parte (`ipp/port1`) é o caminho do recurso.

3. No Terminal, digite `ping myprinter.local` e escolha Enter.

   Anote o endereço IP. Por exemplo, pode retornar algo semelhante a `PING myprinter.local (10.50.25.21)`.

4. Use os valores do endereço IP e do caminho de recursos. Neste exemplo, o endereço IP é `10.50.25.21` e o caminho do recurso é `/ipp/port1`.

## <a name="login-items"></a>Itens de logon

- **Arquivos, pastas e aplicativos personalizados**: **adicione** o caminho de um arquivo, pasta, aplicativo personalizado ou aplicativo de sistema que você deseja abrir quando um usuário entrar no dispositivo. Aplicativos de sistema ou aplicativos criados ou personalizados para sua organização normalmente estão na `Applications` pasta, com um caminho semelhante a. `/Applications/AppName.app` 

  Você pode adicionar vários arquivos, pastas e aplicativos. Por exemplo, insira:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Ao adicionar qualquer aplicativo, pasta ou arquivo, certifique-se de inserir o caminho correto. Nem todos os itens estão na `Applications` pasta. Se um usuário mover um item de um local para outro, o caminho será alterado. Este item movido não será aberto quando o usuário entrar.

## <a name="login-window"></a>Janela de logon

### <a name="window-layout"></a>Layout da janela

- **Mostrar informações adicionais na barra de menus**: quando a área de tempo é selecionada na barra de menus, **Permitir** mostra o nome do host e a versão do macOS. **Não configurado** (padrão) não mostra essas informações na barra de menus.
- **Faixa**: insira uma mensagem mostrada na tela de entrada no dispositivo. Por exemplo, insira as informações de sua organização, uma mensagem de boas-vindas, informações sobre achados e perdidos e assim por diante.
- **Escolher formato de logon**: escolha como os usuários entram no dispositivo. Suas opções:
  - **Solicitar usuário e senha** (padrão): exige que os usuários insiram um nome de usuário e senha.
  - **Listar todos os usuários, solicitar senha**: exige que os usuários selecionem o nome de usuário em uma lista de usuários e, em seguida, insiram sua senha. Configure também:

    - **Usuários locais**: **Ocultar** não mostra as contas de usuário local na lista de usuários, que podem incluir as contas de administrador e padrão. Somente as contas de usuário de rede e do sistema são mostradas. **Não configurado** (padrão) mostra as contas de usuário local na lista de usuários.
    - **Contas móveis**: **Ocultar** não mostra contas móveis na lista de usuários. **Não configurado** (padrão) mostra as contas móveis na lista de usuários. Algumas contas móveis podem ser mostradas como usuários de rede.
    - **Usuários de rede**: selecione **Mostrar** para listar os usuários de rede na lista de usuários. **Não configurado** (padrão) não mostra as contas de usuário de rede na lista de usuários.
    - **Usuários administradores**: **Ocultar** não mostra as contas de usuário administrador na lista de usuários. **Não configurado** (padrão) mostra as contas de usuário administrador na lista de usuários.
    - **Outros usuários**: selecione **Mostrar** para listar **Outros...** usuários na lista de usuários. **Não configurado** (padrão) não mostra outras contas de usuário na lista de usuários.

### <a name="login-screen-power-settings"></a>Configurações de energia da tela de logon

- **Botão Desligar**: **Ocultar** não mostra o botão de desligamento na tela de entrada. **Não configurado** (padrão) mostra o botão de desligamento.
- **Botão Reiniciar**: **Ocultar** não mostra o botão de reinicialização na tela de entrada. **Não configurado** (padrão) mostra o botão de reinicialização.
- **Botão Suspender**: **Ocultar** não mostra o botão de suspensão na tela de entrada. **Não configurado** (padrão) mostra o botão de suspensão.

### <a name="other"></a>Outros

- **Desabilitar logon do usuário do Console**: **Desabilitar** oculta a linha de comando do macOS usada para entrar. Para usuários comuns, **Desabilite** esta configuração. **Não configurado** (padrão) permite que usuários avançados entrem usando a linha de comando do macOS. Para entrar no modo de console, os usuários inserem `>console` no campo Nome de usuário e devem se autenticar na janela do console.

### <a name="apple-menu"></a>Menu Apple

Depois que os usuários entram nos dispositivos, as seguintes configurações afetam o que eles podem fazer.

- **Desabilitar Desligar**: **Desabilitar** impede que os usuários selecionem a opção **Desligamento** após a entrada do usuário. **Não configurado** (padrão) permite que os usuários selecionem o item de menu **Desligamento** no dispositivo.
- **Desabilitar Reiniciar**: **Desabilitar** impede que os usuários selecionem a opção **Reiniciar** após a entrada do usuário. **Não configurado** (padrão) permite que os usuários selecionem o item de menu **Reinicialização** no dispositivo.
- **Desabilitar Desligamento**: **Desabilitar** impede que os usuários selecionem **Desligamento** após a entrada do usuário. **Não configurado** (padrão) permite que os usuários selecionem o item de menu **Desligar** no dispositivo.
- **Desabilitar Logoff** (macOS 10.13 e posterior): **Desabilitar** impede que os usuários selecionem a opção **Logoff** após a entrada do usuário. **Não configurado** (padrão) permite que os usuários selecionem o item de menu **Logoff** no dispositivo.
- **Desabilitar Bloquear Tela** (macOS 10.13 e posterior): **Desabilitar** impede que os usuários selecionem a opção **Bloquear Tela** após a entrada do usuário. **Não configurado** (padrão) permite que os usuários selecionem o item de menu **Bloquear tela** no dispositivo.

Selecione **OK** para salvar as configurações.

## <a name="next-steps"></a>Próximas etapas

- Exiba todas as configurações para dispositivos [iOS](ios-device-features-settings.md).
- [Atribua este perfil](device-profile-assign.md) aos seus grupos e [monitore seu status](device-profile-monitor.md).
