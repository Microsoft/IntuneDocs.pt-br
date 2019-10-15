---
title: Adicionar configurações personalizadas a dispositivos Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Adicionar ou criar um perfil personalizado para dispositivos Android Enterprise criarem no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/01/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: baa202ba5fdb554af56724279456cf43961ff82d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735162"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Usar configurações personalizadas para dispositivos Android Enterprise no Microsoft Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos de perfil de trabalho do Android Enterprise usando um "perfil personalizado". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações de dispositivos e recursos que não são internos ao Intune.

Os perfis personalizados do Android Enterprise usam as configurações OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para controlar recursos em dispositivos Android Enterprise. Essas configurações geralmente são usadas pelos fabricantes de dispositivos móveis para controlar esses recursos.

O Intune dá suporte a um número limitado de perfis personalizados do Android Enterprise, incluindo:

- ./Vendor/MSFT/WiFi/Profile/SSID/Settings: [criar um perfil de Wi-Fi com uma chave pré-compartilhada](wi-fi-profile-shared-key.md) tem alguns exemplos.
- ./Vendor/MSFT/VPN/Profile/Name/PackageList: [criar um perfil de VPN por aplicativo](android-pulse-secure-per-app-vpn.md) tem alguns exemplos.
- ./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste: consulte o [exemplo](#example) (neste artigo).

Se você precisar de configurações adicionais, consulte [OEMConfig para Android Enterprise](android-oem-configuration-overview.md).

Este artigo mostra como criar um perfil personalizado para dispositivos Android Enterprise. Também fornece um exemplo de um perfil personalizado que bloqueia as ações de copiar e colar.

## <a name="create-the-profile"></a>Criar o perfil

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `android enterprise custom profile`
    - **Descrição:** insira uma descrição para o perfil
    - **Plataforma**: escolha **Android Enterprise**
    - **Tipo de perfil**: escolha **Personalizado**

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    - **Nome**: insira um nome exclusivo para que a configuração de OMA-URI possa ser facilmente encontrada.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
    - **OMA-URI**: insira o OMA-URI que você deseja usar como uma configuração.
    - **Tipo de dados**: escolha o tipo de dados que você usará para essa configuração de OMA-URI. Suas opções:

      - Cadeia de caracteres
      - Cadeia de caracteres (arquivo XML)
      - Data e hora
      - Inteiro
      - Ponto flutuante
      - Booliano
      - Base64 (arquivo)

    - **Valor** – insira o valor de dados que você deseja associar ao OMA-URI inserido. O valor depende do tipo de dados selecionado. Por exemplo, se você escolher **Data e hora**, selecione o valor em um seletor de data.

    Depois de adicionar algumas configurações, você pode selecionar **Exportar**. **Exportar** cria uma lista de todos os valores que você adicionou em um arquivo de valores separados por vírgulas (.csv).

5. Selecione **OK** para salvar suas alterações. Continue a adicionar mais configurações conforme necessário.
6. Quando terminar, escolha **OK** > **Criar** para criar o perfil do Intune. Ao concluir, seu perfil é mostrado na lista **Configuração do dispositivo – Perfis**.

## <a name="example"></a>Exemplo

Neste exemplo, você cria um perfil personalizado que restringe as ações de copiar e colar entre aplicativos pessoais e de trabalho em dispositivos Android Enterprise.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `android ent block copy paste custom profile`.
    - **Descrição:** insira uma descrição para o perfil.
    - **Plataforma**: escolha **Android Enterprise**.
    - **Tipo de perfil**: escolha **Personalizado**.

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    - **Nome**: insira algo parecido com `Block copy and paste`.
    - **Descrição**: insira algo parecido com `Blocks copy/paste between work and personal apps`.
    - **OMA-URI**: insira `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste`.
    - **Tipo de dados**: escolha **Boolean** para que o valor para esse OMA-URI seja **True** ou **False**.
    - **Valor**: escolha **Verdadeiro**.

5. Depois de inserir as configurações, seu ambiente deverá ter uma aparência semelhante à seguinte imagem:

    ![Bloquear ações de copiar e colar para o perfil de trabalho do Android.](./media/custom-settings-android-for-work/custom-policy-afw-copy-paste.png)

Quando você atribui esse perfil para dispositivos Android Enterprise gerenciados, as ações de copiar e colar estarão bloqueadas entre aplicativos nos perfis pessoais e corporativos.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md).

Veja como [criar o perfil em dispositivos Android](../custom-settings-android.md).