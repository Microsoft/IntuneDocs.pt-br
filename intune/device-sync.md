---
title: Sincronizar dispositivos com o Intune
titlesuffix: Azure portal
description: "Saiba como sincronizar dispositivos com o Intune para obter as políticas e ações mais recentes."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8a8bb4729314819b23d69f0ccf6f6c093f29801f
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Sincronize dispositivos com o Intune para obter as políticas e ações mais recentes


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Sincronizar** força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>Como sincronizar um dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota **Sincronizar**.
7. Escolha **Sim** para confirmar a ação.


## <a name="retriable-error-codes"></a>Códigos de erro passíveis de repetição

Quando um administrador executar a ação **Sincronizar** dispositivo, os aplicativos iOS e Android que falharem mas gerarem um código de erro passível de repetição ficarão disponíveis para o dispositivo. No entanto, os aplicativos que gerarem um código de erro não passível de repetição deverão esperar sete dias para que possam ficar disponíveis para o dispositivo.


| Código de erro  | Descrição sugerida                                                                                                                  | Passível de repetição |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Ocorreu um erro desconhecido.                                                                                                             | Não        |
| 2016330897 | Sua conexão com o Intune atingiu o tempo limite. Reinicie a conexão                                                                             | Sim       |
| 2016330896 | Você perdeu a conexão com a Internet. Reinicie a conexão.                                                                            | Sim       |
| 2016330895 | Você perdeu a conexão com a Internet. Reinicie a conexão.                                                                            | Sim       |
| 2016330894 | Você perdeu a conexão com a Internet. Reinicie a conexão.                                                                            | Sim       |
| 2016330893 | Você perdeu a conexão com a Internet. Reinicie a conexão.                                                                            | Sim       |
| 2016330892 | O roaming internacional está desabilitado.                                                                                                     | Não        |
| 2016330891 | A conexão de dados de celular para este dispositivo não pode ser acessada enquanto está sendo feita uma chamada telefônica. Aguarde a conclusão da chamada telefônica. | Sim       |
| 2016330890 | A rede de celular deste dispositivo. Esses dispositivos não podem ser usados no momento.                                                   | Não        |
| 2016330889 | Falha da conexão segura. Reinicie a conexão.                                                                                   | Sim       |
| 2016330888 | Falha da avaliação de confiança do servidor.                                                                                                | Não        |

## <a name="next-steps"></a>Próximas etapas

Escolha **Ações de Dispositivo** para ver o status da ação de sincronização. 
