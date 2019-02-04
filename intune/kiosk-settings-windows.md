---
title: Configurações de quiosque para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos Windows 10 (e posterior) como quiosques de aplicativo único e de vários aplicativos, personalize o menu Iniciar, adicione aplicativos, mostre a barra de tarefas e configure um navegador da Web no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 61cb1a3c9de10020381d62a2a7795d5ff728db22
ms.sourcegitcommit: 6f2f2fa70f4e47fa5ad2f3c536ba7116e1bd1d05
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55199414"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Configurações de dispositivos com Windows 10 (e posterior) para execução como um quiosque no Intune

Em dispositivos com Windows 10 e posterior, você pode configurar esses dispositivos para que sejam executados no modo de quiosque de aplicativo único ou de vários aplicativos.

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos Windows 10 e posterior. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para definir seus dispositivos Windows 10 e posterior para que sejam executados no modo de quiosque.

Como administrador do Intune, você pode criar e atribuir essas configurações aos dispositivos.

Para saber mais sobre o recurso de quiosque do Windows no Intune, confira [definir as configurações de quiosque](kiosk-settings.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie o perfil](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único

Quando você escolher o modo de quiosque de aplicativo único, insira as seguintes configurações:

- **Tipo de logon do usuário**: Os aplicativos que você adiciona são executados com a conta de usuário inserida. Suas opções:

  - **Logon automático (Windows 10, versão 1803 e posterior)**: Para quiosques em ambientes voltados ao público que não exigem a conexão do usuário, semelhante a uma conta Convidado. Essa configuração usa o [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Conta de usuário local**: Insira a conta de usuário local (do dispositivo). A conta inserida é usada para entrar no quiosque.

- **Tipo de aplicativo**: Selecione **Aplicativo da loja**.

- **Aplicativo a ser executado no modo de quiosque**: Escolha **Adicionar um aplicativo da loja** e selecione um aplicativo na lista.

    Não tem aplicativos listados? Adicione alguns usando as etapas em [Aplicativos cliente](apps-add.md).

    Selecione **OK** para salvar suas alterações.

- **Configurações do navegador de quiosque**: Essas configurações controlam um aplicativo de navegador da Web no quiosque. Lembre-se de obter o [Aplicativo de navegador de quiosque](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) da Loja, adicioná-lo ao Intune como um [Aplicativo Cliente](apps-add.md) e, em seguida, atribuir o aplicativo aos dispositivos de quiosque.

  Insira as seguintes configurações:

  - **URL padrão da home page**: Insira a URL padrão exibida quando o navegador de quiosque é aberto ou quando o navegador é reiniciado. Por exemplo, insira `http://bing.com` ou `http://www.contoso.com`.

  - **Botão Página Inicial**: **Mostre** ou **oculte** o botão de Página Inicial do navegador de quiosque. Por padrão, o botão não é exibido.

  - **Botões de navegação**: **Mostre** ou **oculte** os botões Voltar e Avançar. Por padrão, os botões de navegação não são exibidos.

  - **Botão Encerrar sessão**: **Mostre** ou **oculte** o botão Encerrar sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e abre a URL padrão. Por padrão, o botão não é exibido.

  - **Atualizar o navegador após tempo ocioso**: Insira o tempo ocioso (1 a 1.440 minutos) até que o navegador de quiosque seja reiniciado em um novo estado. Tempo ocioso é a quantidade de minutos desde a última interação do usuário. Por padrão, o valor fica vazio ou em branco, o que significa que não há qualquer tempo limite de ociosidade.

  - **Sites permitidos**: Use essa configuração para permitir que sites específicos sejam abertos. Em outras palavras, use esse recurso para restringir ou impedir sites da Web no dispositivo. Por exemplo, você pode permitir que todos os sites em `http://contoso.com*` sejam abertos. Por padrão, todos os sites são permitidos.
 
      Para permitir sites específicos, faça upload de um arquivo que inclua uma lista dos sites permitidos em linhas separadas. Se você não adicionar um arquivo, todos os sites serão permitidos. O Intune aceita o asterisco (*) como um caractere curinga.

      Seu arquivo de exemplo deverá ser semelhante à seguinte lista:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Selecione **OK** para salvar suas alterações.

## <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos

Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir.

Quando você escolher o modo de quiosque de vários aplicativos, insira as seguintes configurações:

- **Definir o Windows 10 como destino em dispositivos no modo S**: Escolha **Sim** para permitir aplicativos da loja e aplicativos AUMID (exceto aplicativos Win32) no perfil de quiosque. Escolha **Não** para permitir aplicativos da loja, aplicativos Win32 e aplicativos AUMID no perfil de quiosque. Ao escolher **Não**, esse perfil de quiosque não é implantado em dispositivos de modo S.

- **Tipo de logon do usuário**: Os aplicativos que você adiciona são executados com a conta de usuário inserida. Suas opções:

  - **Logon automático (Windows 10, versão 1803 e posterior)**: Para quiosques em ambientes voltados ao público que não exigem a conexão do usuário, semelhante a uma conta Convidado. Essa configuração usa o [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Conta de usuário local**: **Adicione** a conta de usuário local (do dispositivo). A conta inserida é usada para entrar no quiosque.
  - **Usuário ou grupo do Azure AD (Windows 10 versão 1803 e posterior)**: Selecione **Adicionar** para escolher usuários ou grupos do Azure AD na lista. Você pode selecionar vários usuários e grupos. Marque **Selecionar** para salvar suas alterações.
  - **Visitante do HoloLens**: A conta do visitante é uma conta Convidado que não exige credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplicativos**: Adicione os aplicativos a serem executados no dispositivo de quiosque. Lembre-se, você pode adicionar vários aplicativos.

  - **Adicionar aplicativo da loja**: Adicione um aplicativo da Microsoft Store para Empresas. Se você não tiver qualquer aplicativo listado, poderá adquirir aplicativos e [adicioná-los ao Intune](store-apps-windows.md). Por exemplo, você pode adicionar o navegador de quiosque, o Excel, o OneNote e muito mais.

  - **Adicionar um aplicativo Win32**: Um aplicativo Win32 é um aplicativo da área de trabalho tradicional, como o Visual Studio Code ou o Google Chrome. Insira as seguintes propriedades:

    - **Nome do aplicativo**: Obrigatório. Insira um nome para o aplicativo.
    - **Caminho local**: Obrigatório. Insira o caminho para o executável, como `C:\Program Files (x86)\Microsoft VS Code\Code.exe` ou `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **AUMID (ID do modelo de usuário do aplicativo)**: Insira a ID do modelo de usuário do aplicativo (AUMID) do aplicativo do Win32. Essa configuração determina o layout inicial do bloco na área de trabalho. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Tamanho do bloco**: Obrigatório. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.
  
  - **Adicionar pela AUMID**: Use essa opção para adicionar aplicativos da caixa de entrada do Windows, como o Bloco de notas ou a Calculadora. Insira as seguintes propriedades: 

    - **Nome do aplicativo**: Obrigatório. Insira um nome para o aplicativo.
    - **AUMID (ID do modelo de usuário do aplicativo)**: Obrigatório. Insira a ID do modelo do usuário do aplicativo (AUMID) do aplicativo do Windows. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tamanho do bloco**: Obrigatório. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.

  > [!TIP]
  > Após adicionar todos os aplicativos, você pode alterar a ordem de exibição clicando e arrastando os aplicativos na lista.  

  Selecione **OK** para salvar suas alterações.

- **Configurações do navegador de quiosque**: Essas configurações controlam um aplicativo de navegador da Web no quiosque. Certifique-se de implantar um aplicativo de navegador da Web para os dispositivos de quiosque usando [Aplicativos cliente](apps-add.md).

  Insira as seguintes configurações:

  - **URL padrão da home page**: Insira a URL padrão exibida quando o navegador de quiosque é aberto ou quando o navegador é reiniciado. Por exemplo, insira `http://bing.com` ou `http://www.contoso.com`.

  - **Botão Página Inicial**: **Mostre** ou **oculte** o botão de Página Inicial do navegador de quiosque. Por padrão, o botão não é exibido.

  - **Botões de navegação**: **Mostre** ou **oculte** os botões Voltar e Avançar. Por padrão, os botões de navegação não são exibidos.

  - **Botão Encerrar sessão**: **Mostre** ou **oculte** o botão Encerrar sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e abre a URL padrão. Por padrão, o botão não é exibido.

  - **Atualizar o navegador após tempo ocioso**: Insira o tempo ocioso (1 a 1.440 minutos) até que o navegador de quiosque seja reiniciado em um novo estado. Tempo ocioso é a quantidade de minutos desde a última interação do usuário. Por padrão, o valor fica vazio ou em branco, o que significa que não há qualquer tempo limite de ociosidade.

  - **Sites permitidos**: Use essa configuração para permitir que sites específicos sejam abertos. Em outras palavras, use esse recurso para restringir ou impedir sites da Web no dispositivo. Por exemplo, você pode permitir que todos os sites em `contoso.com*` sejam abertos. Por padrão, todos os sites são permitidos.

    Para permitir sites específicos, faça o upload de um arquivo .csv que inclua uma lista dos sites permitidos. Se você não adicionar um arquivo .csv, todos os sites serão permitidos.

  Selecione **OK** para salvar suas alterações.

- **Usar layout alternativo da tela inicial**: Escolha **Sim** para inserir um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. Use esta opção se você precisar de mais personalização no seu menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.

- **Barra de tarefas do Windows**: Escolha **Mostrar** ou **Ocultar** a barra de tarefas. Por padrão, a barra de tarefas não é exibida. Ícones, como o ícone de Wi-Fi, são mostrados, mas as configurações não podem ser alteradas pelos usuários finais.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Também é possível criar perfis de quiosque para dispositivos [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) e [Windows Holographic for Business](kiosk-settings-holographic.md).
