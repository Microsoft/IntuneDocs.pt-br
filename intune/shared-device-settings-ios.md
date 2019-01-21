---
title: Personalizar a tela de bloqueio em dispositivos iOS usando o Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Conheça as configurações do Microsoft Intune que você pode usar para exibir informações na tela de bloqueio de dispositivos iOS usando as definições de configuração de dispositivo compartilhado para o iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f4d75d795421c761398f349c324b498fd21ca01
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203069"
---
# <a name="add-custom-messages-to-lock-screen-and-login-window-on-ios-devices-using-microsoft-intune"></a>Adicionar mensagens personalizadas à tela de bloqueio e à janela de logon em dispositivos iOS usando o Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Microsoft Intune que você pode usar para exibir informações na tela de bloqueio e na janela de logon de dispositivos iOS. 

Use essas configurações para exibir uma mensagem ou um texto personalizado na janela de logon e na tela de bloqueio. Por exemplo, insira uma mensagem "Em caso de perda, devolver a" e informações da tag do ativo.

Essa configuração dá suporte a dispositivos supervisionados que executam o iOS 9.3 e posterior.

## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Digite um **Nome** e uma **Descrição** para o perfil.
4. Em **Plataforma**, selecione **iOS**. Em **Tipo de perfil**, selecione **Recursos do dispositivo**.
5. Em **Configurações**, selecione **Mensagem da Tela de Bloqueio (somente supervisionado)**. Defina as seguintes configurações:

    - **Informações da tag do ativo**: Insira informações sobre a tag do ativo do dispositivo. Por exemplo, insira `123xyz`.

        O texto inserido é mostrado na janela de logon e na tela de bloqueio do dispositivo.

    - **Nota de rodapé da tela de bloqueio**: Em caso de perda ou roubo do dispositivo, insira uma observação que pode ajudar na devolução do dispositivo. Insira qualquer texto desejado no campo. Por exemplo, insira algo como `If found, call Contoso at ...`.

    Os tokens de dispositivo também podem ser usados para adicionar informações específicas do dispositivo a esses campos. Por exemplo, para mostrar o número de série, insira `Serial Number: {{serialnumber}}`. Na tela de bloqueio, o texto mostra algo semelhante a `Serial Number 123456789ABC`. Ao inserir variáveis, lembre-se de usar chaves `{{ }}`. [Tokens de configuração de aplicativo](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) inclui uma lista das variáveis que podem ser usadas. Use também `deviceName` ou qualquer outro valor específico do dispositivo.

6. Quando terminar, selecione **OK** > **OK** > **Criar**. Seu perfil será mostrado na lista.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
