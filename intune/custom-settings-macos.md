---
title: Adicionar configurações personalizadas a dispositivos macOS no Microsoft Intune ‑ Azure | Microsoft Docs
titleSuffix: ''
description: Exporte configurações do macOS de ferramentas do Apple Configurator ou do Gerenciador de Perfis da Apple e, em seguida, importe-as para o Microsoft Intune. Essas configurações podem criar, usar e controlar configurações e recursos personalizados nos dispositivos macOS. Esse perfil personalizado pode ser atribuído ou distribuído para dispositivos macOS na sua organização para criar uma linha de base ou padrão.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3136088f307d8e2e83faaccafbda4ad2664c6f62
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183206"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Usar configurações personalizadas para dispositivos macOS no Microsoft Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos macOS usando um "perfil personalizado". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações de dispositivos e recursos que não são internos ao Intune.

Ao usar dispositivos macOS, há duas maneiras de obter as configurações personalizadas do Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Gerenciador de Perfis da Apple](https://support.apple.com/profile-manager)

Você pode usar essas ferramentas para exportar as configurações para um perfil de configuração. No Intune, você deve importar esse arquivo e, em seguida, atribuir o perfil aos seus usuários e dispositivos macOS. Uma vez atribuídas, as configurações são distribuídas e também criam uma linha de base ou padrão para macOS na sua organização.

Este artigo mostra como criar um perfil personalizado para dispositivos macOS. Também fornece algumas diretrizes sobre como usar o Apple Configurator e o Gerenciador de Perfis da Apple.

## <a name="before-you-begin"></a>Antes de começar

- Ao usar o **Apple Configurator** para criar o perfil de configuração, as configurações exportadas devem ser compatíveis com a versão do macOS nos dispositivos que você está usando. Para obter informações sobre como resolver configurações incompatíveis, pesquise **Referência de Perfil de Configuração** e **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

- Ao usar o **Gerenciador de Perfis da Apple**, não se esqueça de:

  - Habilitar o [gerenciamento de dispositivo móvel](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) no Gerenciador de Perfis.
  - Adicione [dispositivos macOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) no Gerenciador de Perfis.
  - Depois de adicionar um dispositivo no Gerenciador de Perfis, vá para **Na Biblioteca** > **Dispositivos** > selecione seu dispositivo > **Configurações**. Insira as configurações gerais, de segurança, de privacidade, de diretório e de certificado para o dispositivo.

    Baixe e salve esse arquivo. Você inserirá esse arquivo no perfil do Intune. 

  - As configurações exportadas do Gerenciador de Perfis da Apple devem ser compatíveis com a versão do macOS nos dispositivos que você está usando. Para obter informações sobre como resolver configurações incompatíveis, pesquise **Referência de Perfil de Configuração** e **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

## <a name="create-the-profile"></a>Criar o perfil

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `macos custom profile`.
    - **Descrição:** insira uma descrição para o perfil.
    - Para **Plataforma**, escolha **macOS**.
    - **Tipo de perfil**: escolha **Personalizado**.

4. Em **Configuração Personalizada**, insira as seguintes configurações:

    - **Nome do perfil de configuração personalizada**: insira um nome para a política. Esse nome é mostrado no dispositivo e no status do Intune.
    - **Arquivo do perfil de configuração**: navegue até o perfil de configuração que você criou usando o Apple Configurator ou o Gerenciador de Perfis da Apple. O arquivo importado é mostrado na área **Conteúdos do arquivo**.

5. Selecione **OK** > **Criar** para criar o perfil do Intune. Ao concluir, seu perfil é mostrado na lista **Configuração do dispositivo – Perfis**.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md).

Veja como [criar o perfil em dispositivos iOS](custom-settings-ios.md).