---
title: Definir as configurações de educação do Intune para Windows 10
titleSuffix: Microsoft Intune
description: Saiba como usar o Intune para definir as configurações de educação do Windows 10 nos dispositivos gerenciados.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 413ad0bab32353fc6f5b401f9a7b910b6c5cb390
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31023301"
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Como definir configurações de educação do Windows 10 no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Os perfis de educação permitem que você especifique os detalhes de configuração do aplicativo Windows Take a Test, incluindo detalhes da conta e a URL do teste. Ao configurar isso, o aplicativo Take a Testa é aberto com o teste especificado, e nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.

Para obter detalhes sobre o aplicativo Fazer um Teste, consulte [Fazer testes no Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Criar um perfil de dispositivo que contém as configurações do perfil de educação

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
3. No painel de perfis, escolha **Criar perfil**.
4. No painel **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.
5. Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.
6. Na lista suspensa **Tipos de perfil**, escolha **Perfil de educação**. 
7. Escolha **Configurações > Configurar** e, em seguida, no painel **Take a Test**, configure o seguinte:
    - **Tipo de conta** – Selecione um tipo de conta no campo de lista suspensa.
    - **Nome da conta de usuário** - Insira o nome de usuário da conta usada com Take a Test. Pode ser uma conta de domínio, uma conta do Azure Active Directory (AAD) ou uma conta de computador local.
    - **URL de avaliação** - Forneça a URL do teste o qual você deseja que os usuários realizem. Para saber mais, veja a documentação do Take a Test.
    - **Monitoramento de tela** - Especifique se você deseja ser capaz de monitorar a atividade da tela enquanto os usuários realizam um teste.
    - **Sugestão de texto** - Permita ou bloqueie sugestões de texto enquanto os usuários realizam um teste.
8. Quando terminar, volte para o painel **Criar perfil** e pressione **Criar**.

O perfil será criado e aparecerá no painel da lista de perfis.

## <a name="next-steps"></a>Próximas etapas

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).



