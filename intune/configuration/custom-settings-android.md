---
title: Adicionar configurações personalizadas a dispositivos Android no Microsoft Intune ‑ Azure | Microsoft Docs
description: Adicionar ou criar um perfil personalizado para dispositivos Android para criar um perfil de Wi-Fi com uma chave pré-compartilhada, criar um perfil de VPN por aplicativo ou permitir/bloquear aplicativos para dispositivos Samsung Knox Standard no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6150359843e5e089226717dd07f3d932ab21f6d6
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735097"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Use configurações personalizadas para dispositivos Android no Microsoft Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos Android usando um "perfil personalizado". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações de dispositivos e recursos que não são internos ao Intune.

Os perfis personalizados do Android usam as configurações do OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir os diversos recursos em dispositivos Android. Essas configurações geralmente são usadas pelos fabricantes de dispositivos móveis para controlar esses recursos.

Usando um perfil personalizado, é possível definir e atribuir as seguintes configurações do Android. As configurações a seguir não são internas ao Intune:

- [Criar um perfil de Wi-Fi com uma chave pré-compartilhada](/intune/wi-fi-profile-shared-key)
- [Criar um perfil de VPN por aplicativo](/intune/android-pulse-secure-per-app-vpn)
- [Permitir e bloquear aplicativos para dispositivos Samsung KNOX Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Somente as configurações listadas podem ser definidas em um perfil personalizado. Dispositivos Android não expõem uma lista completa das configurações de OMA-URI que é possível configurar. Se você quiser ver mais configurações, vote em mais configurações no [site Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

Este artigo mostra como criar um perfil personalizado para dispositivos Android.

## <a name="create-the-profile"></a>Criar o perfil

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `android custom profile`.
    - **Descrição:** insira uma descrição para o perfil.
    - **Plataforma**: escolha **Android**.
    - **Tipo de perfil**: escolha **Personalizado**.

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

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md).

Veja como [criar o perfil em dispositivos Android Enterprise](custom-settings-android-for-work.md).
