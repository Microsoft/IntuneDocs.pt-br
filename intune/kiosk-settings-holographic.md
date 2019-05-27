---
title: Configurações do Kiosk do Windows Holographic for Business no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos Windows Holographic for Business como quiosques de aplicativo único e de vários aplicativos, personalize o menu Iniciar, adicione aplicativos, mostre a barra de tarefas e configure um navegador da Web no Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: aef2db158e0572c1eec056a1d6e33b4b97aea77a
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66047028"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Configurações do dispositivo Windows Holographic for Business para ser executado como um quiosque no Intune

Nos dispositivos Windows Holographic for Business, você pode configurar esses dispositivos para que sejam executados no modo de quiosque de aplicativo único ou de vários aplicativos. Não há suporte para alguns recursos no Windows Holographic for Business.

Este artigo lista e descreve as diferentes configurações que você pode controlar nos dispositivos Windows Holographic for Business. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para definir seus dispositivos Windows Holographic for Business para que sejam executados no modo de quiosque.

Como administrador do Intune, você pode criar e atribuir essas configurações aos dispositivos.

Para saber mais sobre o recurso de quiosque do Windows no Intune, confira [definir as configurações de quiosque](kiosk-settings.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie o perfil](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único

Quando você escolher o modo de quiosque de aplicativo único, insira as seguintes configurações:

- **Tipo de logon de usuário**: selecione **Conta de usuário local** para inserir a conta de usuário local (do dispositivo) ou uma conta Microsoft (MSA) associada ao aplicativo de quiosque. Não há suporte para tipos de conta de usuário de **logon automático** no Windows Holographic for Business.

- **Tipo de aplicativo**: selecione **Aplicativo da Loja**.

- **Aplicativo a ser executado no modo de quiosque**: escolha **Adicionar um aplicativo da loja** e selecione um aplicativo na lista.

    Não tem aplicativos listados? Adicione alguns usando as etapas em [Aplicativos cliente](apps-add.md).

    Selecione **OK** para salvar suas alterações.

## <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos

Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir. Quando você escolher o modo de quiosque de vários aplicativos, insira as seguintes configurações:

- **Direcionar o Windows 10 em dispositivos no modo S**: escolha **Não**. Não há suporte para o modo S no Windows Holographic for Business.

- **Tipo de logon de usuário**: adicione uma ou mais contas de usuário que podem usar os aplicativos que você adicionar. Suas opções: 

  - **Logon automático**: não tem suporte no Windows Holographic for Business.
  - **Contas de usuário local**: **adicione** a conta de usuário local (para o dispositivo). A conta inserida é usada para entrar no quiosque.
  - **Usuário ou grupo do Azure AD (Windows 10, versão 1803 e posteriores)** : exige que as credenciais do usuário façam login no dispositivo. Selecione **Adicionar** para escolher usuários ou grupos do Azure AD na lista. Você pode selecionar vários usuários e grupos. Marque **Selecionar** para salvar suas alterações.
  - **Visitante do HoloLens**: a conta do visitante é uma conta convidado que não exige as credenciais do usuário nem autenticação, conforme descrito em [Conceitos do modo de computador compartilhado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplicativos**: adicione os aplicativos a serem executados no dispositivo de quiosque. Lembre-se, você pode adicionar vários aplicativos.

  - **Adicionar aplicativos da Loja**: selecione um aplicativo existente que você adicionou usando [Aplicativos cliente](apps-add.md). Se você não tiver qualquer aplicativo listado, poderá adquirir aplicativos e [adicioná-los ao Intune](store-apps-windows.md).
  - **Adicionar aplicativo Win32**: não tem suporte no Windows Holographic for Business.
  - **Adicionar por AUMID**: use essa opção para adicionar aplicativos básicos do Windows. Insira as seguintes propriedades: 

    - **Nome do aplicativo**: necessário. Insira um nome para o aplicativo.
    - **Modelo de usuário do aplicativo AUMID (ID)** : necessário. Insira a ID do modelo do usuário do aplicativo (AUMID) do aplicativo do Windows. Para obter a ID, confira [Encontrar a ID do modelo de usuário de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tamanho do bloco**: necessário. Escolha um tamanho de bloco de aplicativo: Pequeno, Médio, Largo ou Grande.

- **Configurações do navegador do quiosque**: não tem suporte no Windows Holographic for Business.

- **Usar layout alternativo do menu Iniciar**: escolha **Sim** para inserir um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. Use esta opção se você precisar de mais personalização no seu menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) fornece algumas diretrizes e inclui um arquivo XML específico para dispositivos Windows Holographic for Business.

- **Barra de tarefas do Windows**: não tem suporte no Windows Holographic for Business.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Também é possível criar perfis de quiosque para dispositivos [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) e [Windows 10 e posterior](kiosk-settings-windows.md).
