---
title: "Definir as configurações de educação do Intune para Windows 10"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para definir configurações de educação do Windows 10 nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3acb45ccc9e67fb410a9511f138d1558a49fadf9
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Como definir configurações de educação do Windows 10 no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Os perfis de educação permitem que você especifique os detalhes de configuração do aplicativo Windows Take a Test, incluindo detalhes da conta e a URL do teste. Ao configurar isso, o aplicativo Take a Testa é aberto com o teste especificado, e nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.

Use as informações neste tópico para aprender as noções básicas sobre a configuração de perfis de restrição de dispositivo e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Criar um perfil de dispositivo que contém as configurações do perfil de educação

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.
5. Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.
6. Na lista suspensa **Tipos de perfil**, escolha **Perfil de educação**. 
7. Escolha Configurações > Configurar, em seguida, na folha **Take a Test**, configure o seguinte:
    - **Nome da conta de usuário** - Insira o nome de usuário da conta usada com Take a Test. Pode ser uma conta de domínio, uma conta do Azure Active Directory (AAD) ou uma conta de computador local.
    - **URL de avaliação** - Forneça a URL do teste o qual você deseja que os usuários realizem. Para saber mais, veja a documentação do Take a Test.
    - **Monitoramento de tela** - Especifique se você deseja ser capaz de monitorar a atividade da tela enquanto os usuários realizam um teste.
    - **Sugestão de texto** - Permita ou bloqueie sugestões de texto enquanto os usuários realizam um teste.
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).




