---
title: Adicionar configurações personalizadas a dispositivos Android no Microsoft Intune ‑ Azure | Microsoft Docs
description: Adicionar ou criar um perfil personalizado para dispositivos Android para criar um perfil de Wi-Fi com uma chave pré-compartilhada, criar um perfil de VPN por aplicativo ou permitir/bloquear aplicativos para dispositivos Samsung Knox Standard no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8137a806598facd540781702b1c2c359e89d6bda
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206781"
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

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um bom nome de perfil é o **perfil personalizado do Android**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Android**.
    - **Tipo de perfil**: selecione **personalizado**.

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    - **Nome**: Insira um nome exclusivo para que a configuração de OMA-URI possa ser facilmente encontrada.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
    - **OMA-URI**: insira o OMA-URI que você deseja usar como uma configuração.
    - **Tipo de dados**: Selecione o tipo de dados que você usará para essa configuração de OMA-URI. Suas opções:

      - Cadeia de caracteres
      - Cadeia de caracteres (arquivo XML)
      - Data e Hora
      - Inteiro
      - Ponto flutuante
      - Booliano
      - Base64 (arquivo)

    - **Valor**: insira o valor de dados que você deseja associar ao OMA-URI inserido. O valor depende do tipo de dados selecionado. Por exemplo, se você selecionar **Data e hora**, selecione o valor em um seletor de data.

    Depois de adicionar algumas configurações, você pode selecionar **Exportar**. **Exportar** cria uma lista de todos os valores que você adicionou em um arquivo de valores separados por vírgulas (.csv).

5. Selecione **OK** para salvar suas alterações. Continue a adicionar mais configurações conforme necessário.
6. Quando terminar, escolha **OK** > **Criar** para criar o perfil do Intune. Após a conclusão, seu perfil será mostrado na lista **Dispositivos – Perfis de configuração**.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Crie um [perfil personalizado em dispositivos Android Enterprise](custom-settings-android-for-work.md).
