---
title: Adicionar configurações personalizadas de dispositivos Windows Phone 8.1 no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione ou crie um perfil personalizado para usar as configurações de OMA-URI para dispositivos que executam o Windows Phone 8.1 no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cb54f5e4cede6141c87073a7dfb6570cf85e920b
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66042888"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Usar configurações personalizadas para dispositivos Windows Phone 8.1 no Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos Windows Phone 8.1 usando "perfis personalizados". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações e recursos de dispositivos que não são internos ao Intune.

Os perfis personalizados do Windows Phone 8.1 usam as configurações do OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir os diversos recursos. Essas configurações geralmente são usadas pelos fabricantes de dispositivos móveis para controlar os recursos do dispositivo.

Este artigo mostra como criar um perfil personalizado para dispositivos Windows Phone 8.1. 

## <a name="create-the-profile"></a>Criar o perfil

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `windows phone custom profile`.
    - **Descrição:** insira uma descrição para o perfil.
    - **Plataforma**: escolha **Windows Phone 8.1**.
    - **Tipo de perfil**: escolha **Personalizado**.

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    - **Nome**: insira um nome exclusivo para a configuração de OMA-URI para ajudar você a identificá-la na lista de configurações.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e qualquer outra informação relevante que ajude a localizar o perfil.
    - **OMA-URI** (com diferenciação de maiúsculas e minúsculas): insira o OMA-URI que você deseja usar como configuração.
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

Veja como criar um perfil personalizado em [dispositivos Windows 10](custom-settings-windows-10.md).
