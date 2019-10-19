---
title: Adicionar configurações personalizadas a dispositivos iOS no Microsoft Intune ‑ Azure | Microsoft Docs
titleSuffix: ''
description: Exporte configurações do iOS de ferramentas do Apple Configurator ou do Gerenciador de Perfis da Apple e, em seguida, importe-as para o Microsoft Intune. Essas configurações podem criar, usar e controlar configurações e recursos personalizados nos dispositivos iOS. Esse perfil personalizado pode ser atribuído ou distribuído para dispositivos iOS na sua organização para criar uma linha de base ou padrão.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfe795a812572fa92c51a23b9e15b7fe48254174
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72495775"
---
# <a name="use-custom-settings-for-ios-devices-in-microsoft-intune"></a>Usar configurações personalizadas para dispositivos iOS no Microsoft Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos iOS usando "perfis personalizados". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações e recursos de dispositivos que não são internos ao Intune.

Ao usar dispositivos iOS, há duas maneiras de obter as configurações personalizadas para o Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Gerenciador de Perfis da Apple](https://support.apple.com/profile-manager)

Você pode usar essas ferramentas para exportar as configurações para um perfil de configuração. No Intune, você deve importar esse arquivo e, em seguida, atribuir o perfil aos seus usuários e dispositivos iOS. Depois de atribuídas, as configurações são distribuídas. Eles também criam uma linha de base ou padrão para iOS em sua organização.

Este artigo fornece algumas diretrizes sobre como usar o Apple Configurator e o Apple Profile Manager e descreve as propriedades que você pode configurar.

## <a name="before-you-begin"></a>Antes de começar

[Crie o perfil](device-profile-create.md).

## <a name="what-you-need-to-know"></a>O que você precisa saber

- Ao usar o **Apple Configurator** para criar o perfil de configuração, as configurações exportadas devem ser compatíveis com a versão do iOS nos dispositivos. Para obter informações sobre como resolver configurações incompatíveis, pesquise **Referência de Perfil de Configuração** e **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

- Ao usar o **Gerenciador de Perfis da Apple**, não se esqueça de:

  - Habilitar o [gerenciamento de dispositivo móvel](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) no Gerenciador de Perfis.
  - Adicione [dispositivos iOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) no Gerenciador de Perfis.
  - Depois de adicionar um dispositivo no Gerenciador de Perfis, vá para **Na Biblioteca** > **Dispositivos** > selecione seu dispositivo > **Configurações**. Insira as configurações gerais para o dispositivo.

    Baixe e salve esse arquivo. Você inserirá esse arquivo no perfil do Intune.

  - As configurações exportadas do Gerenciador de Perfis da Apple devem ser compatíveis com a versão do iOS nos dispositivos. Para obter informações sobre como resolver configurações incompatíveis, pesquise **Referência de Perfil de Configuração** e **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

## <a name="custom-configuration-profile-settings"></a>Definições do perfil de configuração personalizada

- **Nome do perfil de configuração personalizada**: insira um nome para a política. Esse nome é mostrado no dispositivo e no status do Intune.
- **Arquivo do perfil de configuração**: navegue até o perfil de configuração que você criou usando o Apple Configurator ou o Gerenciador de Perfis da Apple. O arquivo importado é mostrado na área **Conteúdos do arquivo**.

  Você também pode adicionar tokens de dispositivo aos seus arquivos de configuração personalizados. Os tokens de dispositivo são usados para adicionar informações específicas do dispositivo. Por exemplo, para mostrar o número de série, insira `{{serialnumber}}`. No dispositivo, o texto é exibido de forma semelhante a `123456789ABC` que é exclusivo para cada dispositivo. Ao inserir variáveis, lembre-se de usar chaves `{{ }}`. [Tokens de configuração de aplicativo](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) inclui uma lista das variáveis que podem ser usadas. Use também `deviceid` ou qualquer outro valor específico do dispositivo.

  > [!NOTE]
  > As variáveis não são validadas na interface do usuário e diferenciam maiúsculas de minúsculas. Como resultado, você pode ver perfis salvos com uma entrada incorreta. Por exemplo, se você digitar `{{DeviceID}}` em vez de `{{deviceid}}`, a cadeia de caracteres literal será mostrada no lugar do ID exclusivo do dispositivo. Certifique-se de inserir as informações corretas.

Selecione **OK** > **Criar** para salvar suas alterações. O perfil é criado e exibido na lista de perfis.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md).

Veja como [criar o perfil em dispositivos macOS](custom-settings-macos.md). 
