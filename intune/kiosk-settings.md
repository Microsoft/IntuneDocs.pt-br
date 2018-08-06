---
title: Configurações de quiosque para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos Windows 10 (e posterior) como quiosques de aplicativo único e de vários aplicativos, incluindo a personalização do menu Iniciar, a adição de aplicativos, a barra de tarefas e a configuração de um navegador da Web. Também configure dispositivos Windows Holographic for Business como quiosques de vários aplicativos no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f10e7bb7a2e7c5e1d0e8b27517a62454e8bd630
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321599"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Configurações de quiosque para Windows 10 (e posteriores) no Intune

Perfis de quiosque são usados para configurar dispositivos Windows 10 para execução de um ou vários aplicativos. Quando você cria um perfil de quiosque, também escolhe se um menu Iniciar é mostrado se um navegador da Web é instalado e muito mais.

## <a name="kiosk-settings"></a>Configurações do quiosque

1. Selecione **Adicionar** para criar um ambiente de quiosque.
2. Insira um **Nome de configuração de quiosque** para o seu quiosque. Esse nome identifica um grupo de aplicativos, o layout desses aplicativos no menu inicial e os usuários atribuídos a essa configuração de quiosque.
3. Selecione o **Modo de quiosque**. **Modo de quiosque** Identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

    - **Não Configurado** (padrão): a política não habilita o modo de quiosque.
    - **Quiosque de aplicativo único de tela inteira**: o perfil permite que o dispositivo seja executado como uma conta de usuário única e bloqueia-a para um único aplicativo UWP (Plataforma Universal do Windows). Assim, quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
    - **Quiosque multiaplicativo**: o perfil permite que o dispositivo execute vários aplicativos UWP (Plataforma Universal do Windows) ou aplicativos Win32. Você também pode atribuir diferentes aplicativos para diferentes contas de usuário. Somente os aplicativos que você adiciona estão disponíveis ao usuário. O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para os usuários ao possibilitar acesso somente aos aplicativos de que eles precisam. E também removendo da exibição os aplicativos de que eles não precisam.

#### <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único
Insira as seguintes configurações:

- **Identificador de aplicativo UWP (Plataforma Universal do Windows)**: insira o **AUMID (ID do modelo de usuário do aplicativo)** do aplicativo de quiosque. Ou selecione um aplicativo gerenciado existente que você tenha adicionado usando [Aplicativos Móveis](apps-add.md).

    Consulte [Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Tipo de conta de usuário**: suas opções:

  - **Logon automático**: para quiosques em ambientes voltados para o público com logon automático habilitado, um usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `AzureAD\user@contoso.com`.
  - **Conta de usuário local**: insira a conta de usuário local (para o dispositivo) ou o logon da conta do Azure AD associado ao aplicativo de quiosque. Para contas ingressadas em domínios do Azure AD, especifique a conta usando o formato `domain\username@tenant.org`.

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos
Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir. 

[Quiosques de vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) usam uma configuração de quiosque que lista os aplicativos permitidos e outras configurações.

Insira as seguintes configurações:

- **Adicionar Aplicativo Win32**: um aplicativo Win32 é um aplicativo da área de trabalho tradicional. Insira o **Nome do aplicativo** e o **Identificador**. O **Identificador** é o nome do caminho totalmente qualificado do executável com relação ao dispositivo.
- **Adicionar aplicativos gerenciados**: selecione um aplicativo gerenciado existente que você adicionou usando [Aplicativos Móveis no Intune](apps-add.md).
- **Adicionar aplicativo por AUMID**: insira o [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplicativos da UWP).
- **Barra de tarefas**: escolha **Habilitar** (mostrar) na barra de tarefas ou mantenha-a como **Não configurada** (oculta) no quiosque.
- **Layout do menu Iniciar**: insira um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.

  [Criar um quiosque Windows 10 que executa vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) fornece mais detalhes sobre como usar e criar arquivos XML.

- **Tipo de conta de usuário**: adicione uma ou mais contas de usuário que podem usar os aplicativos que você adicionar. Quando a conta se conecta, apenas os aplicativos definidos na configuração estão disponíveis. A conta pode ser local para o dispositivo ou um logon de conta do Azure AD associado ao aplicativo de quiosque.

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `domain\user@tenant.com`.

## <a name="kiosk-web-browser-settings"></a>Configurações do navegador da Web de quiosque

Essas configurações controlam um aplicativo de navegador da Web no quiosque. Você deve ter implantado um aplicativo de navegador da Web para os dispositivos de quiosque usando [Aplicativos Móveis](apps-add.md).

1. Insira as seguintes configurações:

    - **URL da página inicial padrão**: insira a URL padrão que o navegador de quiosque abre quando o navegador é aberto ou reiniciado.

    - **Botão Página Inicial**: mostre (**Permitir**) ou oculte (**Não configurado**) o botão de página inicial do navegador de quiosque. Por padrão, o botão Não está configurado.

    - **Botão de navegação**: mostre (**Permitir**) ou oculte (**Não configurado**) os botões Avançar e Voltar. Por padrão, os botões de navegação Não estão configurados.

    - **Botão Encerrar sessão**: mostre (**Permitir**) ou oculte (**Não configurado**) o botão Encerrar sessão. Quando a opção é exibida, o usuário seleciona o botão e o aplicativo solicita o encerramento da sessão. Quando a opção é confirmada, o navegador limpa todos os dados de navegação (cookies, cache e assim por diante) e navega novamente para a URL padrão. Por padrão, o botão Não está configurado. 

    - **Atualizar o navegador quando o usuário exceder o limite de tempo ocioso**: insira a quantidade de tempo ocioso da sessão em minutos até que o navegador de quiosque reinicie em um estado novo. O valor é um inteiro de 1 a 1.440 minutos. Por padrão, o valor está vazio ou em branco, que significa que não há nenhum tempo limite de ociosidade.

    - **Sites bloqueados**: lista de URLs de sites bloqueados (com suporte a caracteres curinga). Use essa configuração para impedir que o navegador abra sites específicos. Você também pode **Importar** um arquivo .csv que contenha uma lista. Ou criar um arquivo .csv (**Exportar**) que contenha os sites que você adicionar.

    - **Exceções de site**: lista de exceções para URLs do site bloqueado (com suporte a caracteres curinga). Use essa configuração para permitir que o navegador abra sites específicos. Essas exceções são um subconjunto das URLs bloqueadas. Se uma URL estiver na lista de sites bloqueados e na lista de exceção do site, a exceção entrará em vigor.

    Você também pode **Importar** um arquivo .csv que contenha uma lista. Ou criar um arquivo .csv (**Exportar**) que contenha os sites que você adicionar.

2. Selecione **OK** para salvar suas alterações.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Nos dispositivos Windows Holographic for Business, você pode configurar esses dispositivos para que sejam executados no modo de quiosque de aplicativo único ou de vários aplicativos. 

#### <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único
Insira as seguintes configurações:

- **Identificador de aplicativo UWP (Plataforma Universal do Windows)**: insira o **AUMID (ID do modelo de usuário do aplicativo)** do aplicativo de quiosque. Ou selecione um aplicativo gerenciado existente que você tenha adicionado usando [Aplicativos Móveis](apps-add.md).

    Confira [Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) para obter a ID.

- **Tipo de conta de usuário**: selecione **Conta de usuário local** para inserir a conta de usuário local (do dispositivo) ou um logon de conta MSA (conta Microsoft) associado ao aplicativo de quiosque. Não há suporte para tipos de conta de usuário de **logon automático** no Windows Holographic for Business.

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos
Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir.

Insira as seguintes configurações:

- **Adicionar aplicativos gerenciados**: selecione um aplicativo gerenciado existente que você adicionou usando [Aplicativos Móveis no Intune](apps-add.md).
- **Adicionar aplicativo por AUMID**: insira o [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplicativos da UWP).
- **Layout do menu Iniciar**: insira um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) fornece algumas diretrizes e inclui um arquivo XML específico para dispositivos Windows Holographic for Business.
- **Tipo de conta de usuário**: adicione uma ou mais contas de usuário que podem usar os aplicativos que você adicionar. As opções compatíveis incluem: 
  - **Visitante do HoloLens**: a conta do visitante é uma conta convidado que não exige as credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).
  - **Usuários do Azure AD**: exige as credenciais do usuário para entrar no dispositivo. Use o formato `domain\user@tenant.com`.
  - **Contas de Usuário Locais**: exige as credenciais do usuário para entrar no dispositivo. 

Quando a conta se conecta, apenas os aplicativos definidos na configuração estão disponíveis.

## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
