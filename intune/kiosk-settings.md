---
title: Configurações de quiosque para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos Windows 10 (e posterior) como quiosques de aplicativo único e de vários aplicativos, personalize o menu Iniciar, adicione aplicativos, mostre a barra de tarefas e configure um navegador da Web. Também configure dispositivos Windows Holographic for Business como quiosques de vários aplicativos no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 353c18affa41e56501a76bf695f95cbe95796e99
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203460"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Configurações de dispositivos Windows 10 (e posterior) para serem executados como um quiosque dedicado usando o Intune

Em dispositivos Windows 10, use o Intune para executar dispositivos como um quiosque, às vezes conhecido como um dispositivo dedicado. Um dispositivo no modo de quiosque pode executar um ou muitos aplicativos. Você pode mostrar e personalizar um menu Iniciar, adicionar aplicativos diferentes, incluindo aplicativos Win32, adicionar uma home page específica a um navegador da Web, entre outros. 

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos Windows 10 e posterior. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para definir seus dispositivos Windows 10 para que sejam executados no modo de quiosque.

O Intune oferece suporte a um único perfil de quiosque por dispositivo. Se você precisar de vários perfis de quiosque em um único dispositivo, poderá usar um [OMA-URI personalizado](custom-settings-windows-10.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-profile-create.md).

## <a name="kiosk-settings"></a>Configurações do quiosque

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Insira as seguintes propriedades:

   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: Selecione **Windows 10 e posterior**
   - **Tipo de perfil**: Selecione **Quiosque**

4. Selecione um **modo de quiosque**. O **Modo de quiosque** identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

    - **Não configurado** (padrão): A política não habilita o modo de quiosque.
    - **Quiosque de tela inteira e aplicativo único**: O dispositivo é executado como uma única conta de usuário e fica bloqueado com um único aplicativo da Loja. Assim, quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
    - **Quiosque de vários aplicativos**: O dispositivo executa vários aplicativos da Loja, aplicativos Win32 ou aplicativos da caixa de entrada do Windows usando a AUMID (ID do modelo de usuário do aplicativo). Somente os aplicativos que você adiciona ficam disponíveis no dispositivo.

        O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para os usuários ao possibilitar acesso somente aos aplicativos de que eles precisam. E também removendo da exibição os aplicativos de que eles não precisam.

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

- **Barra de tarefas do Windows**: Escolha **Mostrar** ou **Ocultar** a barra de tarefas. Por padrão, a barra de tarefas não é exibida.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Nos dispositivos Windows Holographic for Business, você pode configurar esses dispositivos para que sejam executados no modo de quiosque de aplicativo único ou de vários aplicativos. Não há suporte para alguns recursos no Windows Holographic for Business.

#### <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único
Quando você escolher o modo de quiosque de aplicativo único, insira as seguintes configurações:

- **Tipo de logon do usuário**: Selecione **Conta de usuário local** para inserir a conta de usuário local (do dispositivo) ou uma conta MSA (conta Microsoft) associada ao aplicativo de quiosque. Não há suporte para tipos de conta de usuário de **logon automático** no Windows Holographic for Business.

- **Tipo de aplicativo**: Selecione **Aplicativo da loja**.

- **Aplicativo a ser executado no modo de quiosque**: Escolha **Adicionar um aplicativo da loja** e selecione um aplicativo na lista.

    Não tem aplicativos listados? Adicione alguns usando as etapas em [Aplicativos cliente](apps-add.md).

    Selecione **OK** para salvar suas alterações.

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos
Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir. Quando você escolher o modo de quiosque de vários aplicativos, insira as seguintes configurações:

- **Definir o Windows 10 como destino em dispositivos no modo S**: Escolha **Não**. Não há suporte para o modo S no Windows Holographic for Business.

- **Tipo de logon do usuário**: Adicione uma ou mais contas de usuário que podem usar os aplicativos adicionados. Suas opções: 

  - **Logon automático**: Não compatível com o Windows Holographic for Business.
  - **Contas de usuário locais**: **Adicione** a conta de usuário local (do dispositivo). A conta inserida é usada para entrar no quiosque.
  - **Usuário ou grupo do Azure AD (Windows 10 versão 1803 e posterior)**: Exige as credenciais do usuário para entrar no dispositivo. Selecione **Adicionar** para escolher usuários ou grupos do Azure AD na lista. Você pode selecionar vários usuários e grupos. Marque **Selecionar** para salvar suas alterações.
  - **Visitante do HoloLens**: A conta do visitante é uma conta Convidado que não exige credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplicativos**: Adicione os aplicativos a serem executados no dispositivo de quiosque. Lembre-se, você pode adicionar vários aplicativos.

  - **Adicionar aplicativos da Loja**: Selecione um aplicativo existente adicionado usando [Aplicativos Cliente](apps-add.md). Se você não tiver qualquer aplicativo listado, poderá adquirir aplicativos e [adicioná-los ao Intune](store-apps-windows.md).
  - **Adicionar um aplicativo Win32**: Não compatível com o Windows Holographic for Business.
  - **Adicionar pela AUMID**: Use essa opção para adicionar aplicativos da caixa de entrada do Windows. Insira as seguintes propriedades: 

    - **Nome do aplicativo**: Obrigatório. Insira um nome para o aplicativo.
    - **AUMID (ID do modelo de usuário do aplicativo)**: Obrigatório. Insira a ID do modelo do usuário do aplicativo (AUMID) do aplicativo do Windows. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tamanho do bloco**: Obrigatório. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.

- **Configurações do navegador de quiosque**: Não compatível com o Windows Holographic for Business.

- **Usar layout alternativo da tela inicial**: Escolha **Sim** para inserir um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. Use esta opção se você precisar de mais personalização no seu menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) fornece algumas diretrizes e inclui um arquivo XML específico para dispositivos Windows Holographic for Business.

- **Barra de tarefas do Windows**: Não compatível com o Windows Holographic for Business.

## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Também é possível criar perfis de quiosque para dispositivos com [Android](device-restrictions-android.md#kiosk) e [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings).
