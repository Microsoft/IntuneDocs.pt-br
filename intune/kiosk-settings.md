---
title: Configurações de quiosque para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos Windows 10 (e posteriores) como quiosques de aplicativo único e de vários aplicativos, incluindo a personalização do menu Iniciar, a adição de aplicativos, a barra de tarefas e a configuração de um navegador da Web. Também configure dispositivos Windows Holographic for Business como quiosques de vários aplicativos no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d749d51f0ae146b68be8abb3a59a0504aea1180
ms.sourcegitcommit: cfce9318b5b5a3005929be6eab632038a12379c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51298132"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Configurações de quiosque para Windows 10 (e posteriores) no Intune

Nos dispositivos Windows 10, você pode usar o Intune para executar esses dispositivos como um quiosque. O quiosque pode executar um único aplicativo ou vários. Você também pode exibir e personalizar um menu Iniciar, adicionar aplicativos diferentes, incluindo aplicativos Win32, adicionar uma página inicial específica a um navegador da Web e muito mais. 

Use as etapas neste artigo para criar um quiosque de aplicativo único ou de vários aplicativos no Intune.

O Intune oferece suporte a um único perfil de quiosque por dispositivo. Se você precisar de vários perfis de quiosque em um único dispositivo, poderá usar um [OMA-URI personalizado](custom-settings-windows-10.md).

## <a name="kiosk-settings"></a>Configurações do quiosque

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Digite as seguintes propriedades:

   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição:** insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: selecione **Windows 10 e posteriores**
   - **Tipo de perfil**: selecione **Quiosque (versão prévia)**

4. Selecione um **modo de quiosque**. O **Modo de quiosque** identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

    - **Não Configurado** (padrão): a política não habilita o modo de quiosque.
    - **Aplicativo único, quiosque de tela inteira**: o dispositivo é executado como uma única conta de usuário e fica bloqueado com um único aplicativo da Loja. Assim, quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
    - **Quiosque de vários aplicativos**: o dispositivo executa vários aplicativos da Loja, aplicativos do Win32 ou aplicativos básicos do Windows usando a ID de modelo de usuário do aplicativo (AUMID). Somente os aplicativos que você adiciona ficam disponíveis no dispositivo.

        O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para os usuários ao possibilitar acesso somente aos aplicativos de que eles precisam. E também removendo da exibição os aplicativos de que eles não precisam.

## <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único
Quando você escolher o modo de quiosque de aplicativo único, insira as seguintes configurações:

- **Tipo de logon do usuário**: os aplicativos que você adiciona são executados com a conta de usuário inserida. Suas opções:

  - **Logon automático (Windows 10 versão 1803 e posteriores)**: para quiosques em ambientes públicos que não exigem que o usuário faça logon, similar a uma conta de convidado. Essa configuração usa o [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Conta de usuário local**: insira a conta de usuário local (para o dispositivo). A conta inserida é usada para entrar no quiosque.

- **Tipo de aplicativo**: selecione **Aplicativo da Loja**.

- **Aplicativo a ser executado no modo de quiosque**: escolha **Adicionar um aplicativo da loja** e selecione um aplicativo na lista.

    Não tem aplicativos listados? Adicione alguns usando as etapas em [Aplicativos cliente](apps-add.md).

    Selecione **OK** para salvar suas alterações.

- **Configurações do navegador do quiosque**: essas configurações controlam um aplicativo de navegador da Web no quiosque. Certifique-se de obter o [Aplicativo de navegador quiosque](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) da Loja, adicione-o ao Intune como um [Aplicativo cliente](apps-add.md) e atribua o aplicativo aos dispositivos de quiosque.

  Insira as seguintes configurações:

  - **URL da home page padrão**: insira a URL padrão a exibir quando o navegador de quiosque abrir ou quando o navegador reiniciar. Por exemplo, insira `http://bing.com` ou `http://www.contoso.com`.

  - **Botão Página Inicial**: **Exibir** ou **Ocultar** o botão de página inicial do navegador de quiosque. Por padrão, o botão não é exibido.

  - **Botões de navegação**: **Exibir** ou **Ocultar** os botões Voltar e Avançar. Por padrão, os botões de navegação não são exibidos.

  - **Botão Encerrar sessão**: **Exibir** ou **Ocultar** o botão para encerrar a sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e abre a URL padrão. Por padrão, o botão não é exibido.

  - **Atualizar o navegador após tempo ocioso**: insira a quantidade de tempo ocioso (1 a 1440 minutos) até que o navegador do quiosque seja reiniciado em um estado novo. Tempo ocioso é a quantidade de minutos desde a última interação do usuário. Por padrão, o valor fica vazio ou em branco, o que significa que não há qualquer tempo limite de ociosidade.

  - **Sites permitidos**: use essa configuração para permitir que sites específicos sejam abertos. Em outras palavras, use esse recurso para restringir ou impedir sites da Web no dispositivo. Por exemplo, você pode permitir que todos os sites em `http://contoso.com*` sejam abertos. Por padrão, todos os sites são permitidos.
 
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

- **Direcionar o Windows 10 em dispositivos no modo S**: escolha **Sim** para permitir aplicativos da loja e aplicativos AUMID (exclui aplicativos Win32) no perfil de quiosque. Escolha **Não** para permitir aplicativos da loja, aplicativos Win32 e aplicativos AUMID no perfil de quiosque. Ao escolher **Não**, esse perfil de quiosque não é implantado em dispositivos de modo S.

- **Tipo de logon do usuário**: os aplicativos que você adiciona são executados com a conta de usuário inserida. Suas opções:

  - **Logon automático (Windows 10 versão 1803 e posteriores)**: para quiosques em ambientes públicos que não exigem que o usuário faça logon, similar a uma conta de convidado. Essa configuração usa o [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Conta de usuário local**: **adicione** a conta de usuário local (para o dispositivo). A conta inserida é usada para entrar no quiosque.
  - **Usuário ou grupo do Azure AD (versão do Windows 10 1803 e posteriores)**: selecione **Adicionar** para escolher usuários ou grupos do Azure AD na lista. Você pode selecionar vários usuários e grupos. Marque **Selecionar** para salvar suas alterações.
  - **Visitante do HoloLens**: a conta do visitante é uma conta convidado que não exige as credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplicativos**: adicione os aplicativos a serem executados no dispositivo de quiosque. Lembre-se, você pode adicionar vários aplicativos.

  - **Adicionar aplicativo da Loja**: adicione um aplicativo da Microsoft Store para Empresas. Se você não tiver qualquer aplicativo listado, poderá adquirir aplicativos e [adicioná-los ao Intune](store-apps-windows.md). Por exemplo, você pode adicionar o navegador de quiosque, o Excel, o OneNote e muito mais.

  - **Adicionar aplicativo Win32**: um aplicativo Win32 é um aplicativo de área de trabalho tradicional, como o Visual Studio Code ou o Google Chrome. Digite as seguintes propriedades:

    - **Nome do aplicativo**: necessário. Insira um nome para o aplicativo.
    - **Caminho local**: necessário. Insira o caminho para o executável, como `C:\Program Files (x86)\Microsoft VS Code\Code.exe` ou `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **AUMID (ID do modelo de usuário do aplicativo)**: insira a AUMID (ID do modelo de usuário do aplicativo) do aplicativo Win32. Essa configuração determina o layout inicial do bloco na área de trabalho. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Tamanho do bloco**: necessário. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.
  
  - **Adicionar por AUMID**: use esta opção para adicionar aplicativos básicos do Windows, como o Bloco de Notas ou a Calculadora. Digite as seguintes propriedades: 

    - **Nome do aplicativo**: necessário. Insira um nome para o aplicativo.
    - **Modelo de usuário do aplicativo AUMID (ID)**: necessário. Insira a ID do modelo do usuário do aplicativo (AUMID) do aplicativo do Windows. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tamanho do bloco**: necessário. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.

  > [!TIP]
  > Após adicionar todos os aplicativos, você pode alterar a ordem de exibição clicando e arrastando os aplicativos na lista.  

  Selecione **OK** para salvar suas alterações.

- **Configurações do navegador do quiosque**: essas configurações controlam um aplicativo de navegador da Web no quiosque. Certifique-se de implantar um aplicativo de navegador da Web para os dispositivos de quiosque usando [Aplicativos cliente](apps-add.md).

  Insira as seguintes configurações:

  - **URL da home page padrão**: insira a URL padrão a exibir quando o navegador de quiosque abrir ou quando o navegador reiniciar. Por exemplo, insira `http://bing.com` ou `http://www.contoso.com`.

  - **Botão Página Inicial**: **Exibir** ou **Ocultar** o botão de página inicial do navegador de quiosque. Por padrão, o botão não é exibido.

  - **Botões de navegação**: **Exibir** ou **Ocultar** os botões Voltar e Avançar. Por padrão, os botões de navegação não são exibidos.

  - **Botão Encerrar sessão**: **Exibir** ou **Ocultar** o botão para encerrar a sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e abre a URL padrão. Por padrão, o botão não é exibido.

  - **Atualizar o navegador após tempo ocioso**: insira a quantidade de tempo ocioso (1 a 1440 minutos) até que o navegador do quiosque seja reiniciado em um estado novo. Tempo ocioso é a quantidade de minutos desde a última interação do usuário. Por padrão, o valor fica vazio ou em branco, o que significa que não há qualquer tempo limite de ociosidade.

  - **Sites permitidos**: use essa configuração para permitir que sites específicos sejam abertos. Em outras palavras, use esse recurso para restringir ou impedir sites da Web no dispositivo. Por exemplo, você pode permitir que todos os sites em `contoso.com*` sejam abertos. Por padrão, todos os sites são permitidos.

    Para permitir sites específicos, faça o upload de um arquivo .csv que inclua uma lista dos sites permitidos. Se você não adicionar um arquivo .csv, todos os sites serão permitidos.

  Selecione **OK** para salvar suas alterações.

- **Usar layout alternativo do menu Iniciar**: escolha **Sim** para inserir um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. Use esta opção se você precisar de mais personalização no seu menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.

- **Barra de tarefas do Windows**: escolha **Exibir** ou **Ocultar** a barra de tarefas. Por padrão, a barra de tarefas não é exibida.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Nos dispositivos Windows Holographic for Business, você pode configurar esses dispositivos para que sejam executados no modo de quiosque de aplicativo único ou de vários aplicativos. Não há suporte para alguns recursos no Windows Holographic for Business.

#### <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único
Quando você escolher o modo de quiosque de aplicativo único, insira as seguintes configurações:

- **Tipo de logon de usuário**: selecione **Conta de usuário local** para inserir a conta de usuário local (do dispositivo) ou uma conta Microsoft (MSA) associada ao aplicativo de quiosque. Não há suporte para tipos de conta de usuário de **logon automático** no Windows Holographic for Business.

- **Tipo de aplicativo**: selecione **Aplicativo da Loja**.

- **Aplicativo a ser executado no modo de quiosque**: escolha **Adicionar um aplicativo da loja** e selecione um aplicativo na lista.

    Não tem aplicativos listados? Adicione alguns usando as etapas em [Aplicativos cliente](apps-add.md).

    Selecione **OK** para salvar suas alterações.

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos
Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir. Quando você escolher o modo de quiosque de vários aplicativos, insira as seguintes configurações:

- **Direcionar o Windows 10 em dispositivos no modo S**: escolha **Não**. Não há suporte para o modo S no Windows Holographic for Business.

- **Tipo de logon de usuário**: adicione uma ou mais contas de usuário que podem usar os aplicativos que você adicionar. Suas opções: 

  - **Logon automático**: não tem suporte no Windows Holographic for Business.
  - **Contas de usuário local**: **adicione** a conta de usuário local (para o dispositivo). A conta inserida é usada para entrar no quiosque.
  - **Usuário ou grupo do Azure AD (Windows 10, versão 1803 e posteriores)**: exige que as credenciais do usuário façam login no dispositivo. Selecione **Adicionar** para escolher usuários ou grupos do Azure AD na lista. Você pode selecionar vários usuários e grupos. Marque **Selecionar** para salvar suas alterações.
  - **Visitante do HoloLens**: a conta do visitante é uma conta convidado que não exige as credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplicativos**: adicione os aplicativos a serem executados no dispositivo de quiosque. Lembre-se, você pode adicionar vários aplicativos.

  - **Adicionar aplicativos da Loja**: selecione um aplicativo existente que você adicionou usando [Aplicativos cliente](apps-add.md). Se você não tiver qualquer aplicativo listado, poderá adquirir aplicativos e [adicioná-los ao Intune](store-apps-windows.md).
  - **Adicionar aplicativo Win32**: não tem suporte no Windows Holographic for Business.
  - **Adicionar por AUMID**: use essa opção para adicionar aplicativos básicos do Windows. Digite as seguintes propriedades: 

    - **Nome do aplicativo**: necessário. Insira um nome para o aplicativo.
    - **Modelo de usuário do aplicativo AUMID (ID)**: necessário. Insira a ID do modelo do usuário do aplicativo (AUMID) do aplicativo do Windows. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tamanho do bloco**: necessário. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.

- **Configurações do navegador do quiosque**: não tem suporte no Windows Holographic for Business.

- **Usar layout alternativo do menu Iniciar**: escolha **Sim** para inserir um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. Use esta opção se você precisar de mais personalização no seu menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) fornece algumas diretrizes e inclui um arquivo XML específico para dispositivos Windows Holographic for Business.

- **Barra de tarefas do Windows**: não tem suporte no Windows Holographic for Business.



## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
