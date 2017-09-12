---
title: "Configurar atualizações da edição do Windows 10 com o Intune"
titlesuffix: Azure portal
description: "Saiba como usar o Intune para fazer atualização dos dispositivos Windows 10 gerenciados para outra edição."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6bd4c4af168bc64acabc05fdaad93558ddd10a
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Como configurar as atualizações de edição do Windows 10 no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use as informações neste tópico para aprender a configurar um perfil de atualização da edição do Windows 10. Este perfil permite atualizar automaticamente os dispositivos que executam uma das seguintes versões do Windows 10 para uma edição diferente:

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 Mobile


Há suporte para os seguintes caminhos de atualização:

- Do Windows 10 Pro para Windows 10 Enterprise
- Do Windows 10 Home para Windows 10 Education
- Do Windows 10 Mobile para Windows 10 Mobile Enterprise
- Do Windows 10 Holographic Pro para o Windows 10 Holographic Enterprise


## <a name="before-you-start"></a>Antes de começar
Antes de começar a atualizar os dispositivos para a versão mais recente, você precisa de:

- Uma chave do produto (Product Key) que é válida para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para edições do Windows 10 Desktop). Você pode usar chaves MAK (Chaves de Ativação Múltipla) ou KMS (Servidor de Gerenciamento de Chaves) ou Um arquivo de licença da Microsoft que contém as informações de licenciamento para instalar a nova versão do Windows em todos os dispositivos de destino da política (para as edições Windows 10 Mobile e Windows 10 Holographic).
- Os dispositivos Windows 10 aos quais você atribuir a política devem ser registrados no Microsoft Intune. Você não pode usar a política de atualização de edição com computadores que executam o software cliente do Intune PC.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de atualização de edição.
5. Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.
6. Na lista suspensa **Tipo de perfil**, escolha **Atualização de edição**.
7. Na folha **Atualização de Edição**, configure o seguinte:
    - **Edição de partida da atualização** – Na lista suspensa, selecione a versão do Windows 10 que você deseja atualizar nos dispositivos.
    - **Edição de destino da atualização** – Na lista suspensa, selecione a versão do Windows 10 Desktop, Windows 10 Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos.
    - **Chave do Produto (Product Key)** – Especifique a chave do produto (Product Key) que você obteve da Microsoft, a qual pode ser usada para atualizar todos os dispositivos de destino do Windows 10 Desktop.<br>Depois de criar uma política que contém uma chave do produto (Product Key), não será possível editar essa chave mais tarde. Isso ocorre porque a chave é obscurecida por motivos de segurança. Para alterar a chave do produto (Product Key), você deve inserir a chave inteira novamente.
    - **Arquivo de Licença** – Escolha **Navegar** para selecionar o arquivo de licença que você obteve da Microsoft com as informações de licença para a edição do Windows Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil é criado e exibido na folha da lista de perfis.

## <a name="next-steps"></a>Próximas etapas

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

>[!NOTE]
>Se posteriormente você remover a atribuição de política, a versão do Windows no dispositivo não será revertida e continuará a funcionar normalmente.

