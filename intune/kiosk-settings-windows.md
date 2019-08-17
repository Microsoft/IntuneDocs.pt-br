---
title: Configurações de quiosque para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos Windows 10 (e posterior) como quiosques de aplicativo único e de vários aplicativos, personalize o menu Iniciar, adicione aplicativos, mostre a barra de tarefas e configure um navegador da Web no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6fb1111a7f660e8c59f45fb1893364dcadd34dca
ms.sourcegitcommit: 6a8de7bb4870ea19aa08db1f188ea7b5e8a387dd
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69487747"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Configurações de dispositivos com Windows 10 (e posterior) para execução como um quiosque no Intune

Em dispositivos com Windows 10 e posterior, você pode configurar esses dispositivos para que sejam executados no modo de quiosque de aplicativo único ou de vários aplicativos.

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos Windows 10 e posterior. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para definir seus dispositivos Windows 10 e posterior para que sejam executados no modo de quiosque.

Como administrador do Intune, você pode criar e atribuir essas configurações aos dispositivos.

Para saber mais sobre o recurso de quiosque do Windows no Intune, confira [definir as configurações de quiosque](kiosk-settings.md).

## <a name="before-you-begin"></a>Antes de começar

- [Crie o perfil](kiosk-settings.md#create-the-profile).

- Este perfil de quiosque está diretamente relacionado ao perfil de restrições do dispositivo você cria usando as [Configurações de quiosque do Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser). Para resumir:

  1. Crie este perfil de quiosque para executar o dispositivo no modo de quiosque.
  2. Crie o [perfil de restrições de dispositivo](device-restrictions-windows-10.md#microsoft-edge-browser) e configure recursos e configurações específicos permitidos no Microsoft Edge.

> [!IMPORTANT] 
> Atribua esse perfil de quiosque aos mesmos dispositivos que seu [perfil do Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único

Executa apenas um aplicativo no dispositivo.

- **Selecione um modo de quiosque**: escolha **aplicativo único, quiosque de tela inteira**.

- **Tipo de logon do usuário**: os aplicativos que você adiciona são executados com a conta de usuário inserida. Suas opções:

  - **Logon automático (Windows 10 versão 1803 e posteriores)** : para uso em quiosques em ambientes públicos que não exigem que o usuário se conecte, similar a uma conta convidado. Essa configuração usa o [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Conta de usuário local**: insira a conta de usuário local (para o dispositivo). A conta em que você entra no quiosque.

- **Tipo de aplicativo**: selecione o tipo de aplicativo. Suas opções:

  - **Adicionar navegador do Microsoft Edge**: selecione **Navegador do Microsoft Edge** e escolha o **tipo de modo de quiosque do Edge**:

    - **Sinalização digital/interativa**: abre uma tela inteira de URL e mostra somente o conteúdo naquele site. [Configurar sinais digitais](https://docs.microsoft.com/windows/configuration/setup-digital-signage) fornece mais informações sobre esse recurso.
    - **Navegação pública (InPrivate)** : executa uma versão limitada com várias guias do Microsoft Edge. Os usuários podem procurar publicamente ou encerrar sua sessão de navegação.

    Para obter mais informações sobre essas opções, veja [Implantar o modo de quiosque do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Essa configuração habilita o navegador Microsoft Edge no dispositivo. Para definir configurações específicas do Microsoft Edge, crie um perfil de configuração do dispositivo (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma > **Restrições de Dispositivo** >  **Navegador Microsoft Edge**). O [Navegador Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) lista e descreve as configurações disponíveis.

  - **Adicionar navegador de quiosque**: selecione **Configurações do navegador de quiosque**. Essas configurações controlam um aplicativo de navegador da Web no quiosque. Verifique se você obteve o [aplicativo de navegador de quiosque](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) da loja, adicione-o ao Intune como um [aplicativo cliente](apps-add.md). Em seguida, atribua o aplicativo aos dispositivos de quiosque.

    Insira as seguintes configurações:

    - **URL da home page padrão**: insira a URL padrão a exibir quando o navegador de quiosque abrir ou quando o navegador reiniciar. Por exemplo, insira `http://bing.com` ou `http://www.contoso.com`.

    - **Botão Página Inicial**: **Exibir** ou **Ocultar** o botão de página inicial do navegador de quiosque. Por padrão, o botão não é exibido.

    - **Botões de navegação**: **Exibir** ou **Ocultar** os botões Voltar e Avançar. Por padrão, os botões de navegação não são exibidos.

    - **Botão Encerrar sessão**: **Exibir** ou **Ocultar** o botão para encerrar a sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e abre a URL padrão. Por padrão, o botão não é exibido.

    - **Atualizar o navegador após tempo ocioso**: insira a quantidade de tempo ocioso (1 a 1440 minutos) até que o navegador do quiosque seja reiniciado em um estado novo. Tempo ocioso é a quantidade de minutos desde a última interação do usuário. Por padrão, o valor fica vazio ou em branco, o que significa que não há qualquer tempo limite de ociosidade.

    - **Sites permitidos**: use essa configuração para permitir que sites específicos sejam abertos. Em outras palavras, use esse recurso para restringir ou impedir sites da Web no dispositivo. Por exemplo, você pode permitir que todos os sites em `http://contoso.com*` sejam abertos. Por padrão, todos os sites são permitidos.

      Para permitir sites específicos, faça upload de um arquivo que inclua uma lista dos sites permitidos em linhas separadas. Se você não adicionar um arquivo, todos os sites serão permitidos. O Intune dá suporte ao `*` (asterisco) como um caractere curinga.

      Seu arquivo de exemplo deverá ser semelhante à seguinte lista:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`

    > [!NOTE]
    > Os quiosques do Windows 10 com o logon automático habilitado usando o navegador de quiosque da Microsoft devem usar uma licença offline da Microsoft Store para empresas. Esse requisito é porque o logon automático usa uma conta de usuário local sem credenciais de Azure Active Directory (AD). Portanto, as licenças online não podem ser avaliadas. Para obter mais informações, confira [Distribuir aplicativos offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Adicionar aplicativo da Store**: selecione **Adicionar um aplicativo da Store** e escolha um aplicativo na lista.

    Não tem aplicativos listados? Adicione alguns usando as etapas em [Aplicativos cliente](apps-add.md).

## <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos

Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir. Se um aplicativo tiver uma dependência de outro aplicativo, ambos deverão ser incluídos na lista de aplicativos permitidos. Por exemplo, o Internet Explorer de 64 bits tem uma dependência do Internet Explorer de 32 bits, portanto, você deve permitir tanto "C:\Program Files\internet explorer\iexplore.exe" quanto "C:\Program Files (x86)\Internet Explorer\iexplore.exe". 

- **Selecionar um modo de quiosque**: escolha **Quiosque de vários aplicativos**.

- **Definir o Windows 10 como destino em dispositivos no modo S**:
  - **Sim**: permite aplicativos da loja e aplicativos AUMID (exceto aplicativos Win32) no perfil de quiosque.
  - **Não**: permite aplicativos da loja, aplicativos Win32 e aplicativos AUMID no perfil de quiosque. Esse perfil de quiosque não é implantado em dispositivos de modo S.

- **Tipo de logon do usuário**: os aplicativos que você adiciona são executados com a conta de usuário inserida. Suas opções:

  - **Logon automático (Windows 10 versão 1803 e posteriores)** : para uso em quiosques em ambientes públicos que não exigem que o usuário se conecte, similar a uma conta convidado. Essa configuração usa o [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Conta de usuário local**: **adicione** a conta de usuário local (para o dispositivo). A conta em que você entra no quiosque.
  - **Usuário ou grupo do Azure AD (versão do Windows 10 1803 e posteriores)** : selecione **Adicionar** para escolher usuários ou grupos do Azure AD na lista. Você pode selecionar vários usuários e grupos. Marque **Selecionar** para salvar suas alterações.
  - **Visitante do HoloLens**: a conta do visitante é uma conta convidado que não exige as credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Navegador e Aplicativos**: adicione os aplicativos a serem executados no dispositivo de quiosque. Lembre-se, você pode adicionar vários aplicativos.

  - **Navegadores**

    - **Adicionar Microsoft Edge**: o Microsoft Edge é adicionado à grade de aplicativos e todos os aplicativos podem ser executados nesse quiosque. Escolha o **tipo de modo de quiosque do Microsoft Edge**:

      - **Modo normal (versão completa do Microsoft Edge)** : executa uma versão completa do Microsoft Edge com todos os recursos de navegação. O estado e os dados do usuário são salvos entre sessões.
      - **Navegação pública (InPrivate)** : executa uma versão com várias guias do Microsoft Edge InPrivate com uma experiência personalizada para quiosques executados no modo de tela inteira.

      Para obter mais informações sobre essas opções, veja [Implantar o modo de quiosque do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Essa configuração habilita o navegador Microsoft Edge no dispositivo. Para definir configurações específicas do Microsoft Edge, crie um perfil de configuração do dispositivo (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma > **Restrições de Dispositivo** >  **Navegador Microsoft Edge**). O [Navegador Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) lista e descreve as configurações disponíveis.

    - **Adicionar navegador do quiosque**: essas configurações controlam um aplicativo de navegador da Web no quiosque. Certifique-se de implantar um aplicativo de navegador da Web para os dispositivos de quiosque usando [Aplicativos cliente](apps-add.md).

      Insira as seguintes configurações:

      - **URL da home page padrão**: insira a URL padrão a exibir quando o navegador de quiosque abrir ou quando o navegador reiniciar. Por exemplo, insira `http://bing.com` ou `http://www.contoso.com`.

      - **Botão Página Inicial**: **Exibir** ou **Ocultar** o botão de página inicial do navegador de quiosque. Por padrão, o botão não é exibido.

      - **Botões de navegação**: **Exibir** ou **Ocultar** os botões Voltar e Avançar. Por padrão, os botões de navegação não são exibidos.

      - **Botão Encerrar sessão**: **Exibir** ou **Ocultar** o botão para encerrar a sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e abre a URL padrão. Por padrão, o botão não é exibido.

      - **Atualizar o navegador após tempo ocioso**: insira a quantidade de tempo ocioso (1 a 1440 minutos) até que o navegador do quiosque seja reiniciado em um estado novo. Tempo ocioso é a quantidade de minutos desde a última interação do usuário. Por padrão, o valor fica vazio ou em branco, o que significa que não há qualquer tempo limite de ociosidade.

      - **Sites permitidos**: use essa configuração para permitir que sites específicos sejam abertos. Em outras palavras, use esse recurso para restringir ou impedir sites da Web no dispositivo. Por exemplo, você pode permitir que todos os sites em `contoso.com*` sejam abertos. Por padrão, todos os sites são permitidos.

        Para permitir sites específicos, faça o upload de um arquivo .csv que inclua uma lista dos sites permitidos. Se você não adicionar um arquivo .csv, todos os sites serão permitidos.

      > [!NOTE]
      > Os quiosques do Windows 10 com o logon automático habilitado usando o navegador de quiosque da Microsoft devem usar uma licença offline da Microsoft Store para empresas. Esse requisito é porque o logon automático usa uma conta de usuário local sem credenciais de Azure Active Directory (AD). Portanto, as licenças online não podem ser avaliadas. Para obter mais informações, confira [Distribuir aplicativos offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Aplicativos**

    - **Adicionar aplicativo da Loja**: adicione um aplicativo da Microsoft Store para Empresas. Se você não tiver qualquer aplicativo listado, poderá adquirir aplicativos e [adicioná-los ao Intune](store-apps-windows.md). Por exemplo, você pode adicionar o navegador de quiosque, o Excel, o OneNote e muito mais.

    - **Adicionar aplicativo Win32**: um aplicativo Win32 é um aplicativo de área de trabalho tradicional, como o Visual Studio Code ou o Google Chrome. Insira as seguintes propriedades:

      - **Nome do aplicativo**: necessário. Insira um nome para o aplicativo.
      - **Caminho local**: necessário. Insira o caminho para o executável, como `C:\Program Files (x86)\Microsoft VS Code\Code.exe` ou `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **AUMID (ID do modelo de usuário do aplicativo)** : insira a AUMID (ID do modelo de usuário do aplicativo) do aplicativo Win32. Essa configuração determina o layout inicial do bloco na área de trabalho. Para obter essa ID, consulte [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).

    - **Adicionar por AUMID**: use esta opção para adicionar aplicativos básicos do Windows, como o Bloco de Notas ou a Calculadora. Insira as seguintes propriedades:

      - **Nome do aplicativo**: necessário. Insira um nome para o aplicativo.
      - **Modelo de usuário do aplicativo AUMID (ID)** : necessário. Insira a ID do modelo do usuário do aplicativo (AUMID) do aplicativo do Windows. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

    - **AutoLaunch**: opcional. Escolha um aplicativo para AutoLaunch quando o usuário entra. É possível definir AutoLaunch apenas para um único aplicativo.
    - **Tamanho do bloco**: necessário. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.

  > [!TIP]
  > Após adicionar todos os aplicativos, você pode alterar a ordem de exibição clicando e arrastando os aplicativos na lista.  

- **Usar layout alternativo do menu Iniciar**: escolha **Sim** para inserir um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. Use esta opção se você precisar de mais personalização no seu menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.

- **Barra de tarefas do Windows**: escolha **Exibir** ou **Ocultar** a barra de tarefas. Por padrão, a barra de tarefas não é exibida. Ícones, como o ícone de Wi-Fi, são mostrados, mas as configurações não podem ser alteradas pelos usuários finais.

- **Permitir Acesso à Pasta de Downloads**: escolha **Sim** para permitir que os usuários acessem a pasta Downloads no Windows Explorer. Por padrão, o acesso à pasta de Downloads está desabilitado. Esse recurso é comumente usado para os usuários finais para acessar itens baixados de um navegador.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Também é possível criar perfis de quiosque para dispositivos [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) e [Windows Holographic for Business](kiosk-settings-holographic.md).
