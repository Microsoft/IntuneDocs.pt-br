---
title: Sincronizar dispositivos com o Microsoft Intune – Azure | Micrososft Docs
description: Sincronize dispositivos registrados ou gerenciados com o Microsoft Intune para obter as políticas e ações mais recentes. Inclui as etapas a serem sincronizadas usando o portal do Azure e lista os códigos de erro que permitem tentar novamente.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b766f9f92fb5d0e8cedfbebbac7246f48b90a6a2
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846121"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Sincronizar dispositivos com o Intune para obter as políticas e ações mais recentes


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Sincronizar** força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele. Esse recurso pode ajudá-lo a validar e a solucionar problemas das políticas que você atribuiu, imediatamente, sem precisar esperar o próximo check-in agendado.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Sincronizar um dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre **Intune** e, em seguida, selecione **Microsoft Intune**. 
3. Em **Intune**, selecione **Dispositivos** > **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, selecione um dispositivo, **Mais** e, em seguida, **Sincronizar**.
5. Para confirmar, selecione **Sim**.

Escolha **Dispositivos** > **Ações do dispositivo** para ver o status da ação de sincronização.

## <a name="retryable-error-codes"></a>Códigos de erro que permitem tentar novamente

Quando um administrador executa a ação do dispositivo **Sincronizar**, os aplicativos iOS e Android que tiverem falhado e gerado um código de erro que permite tentar novamente ainda estarão disponíveis para o dispositivo. No entanto, os aplicativos que tiverem gerado um código de erro que não permite tentar novamente deverão esperar sete dias para ficar novamente disponíveis para o dispositivo.


| Código do erro  | Descrição sugerida | Permite tentar novamente |
|---|---|---|
| 2016330898 | Ocorreu um erro desconhecido. | Não |
| 2016330897 | Sua conexão com o Intune atingiu o tempo limite. Reinicie a conexão. | Sim |
| 2016330896 | Você perdeu a conexão com a Internet. Reinicie a conexão. | Sim |
| 2016330895 | Você perdeu a conexão com a Internet. Reinicie a conexão. | Sim |
| 2016330894 | Você perdeu a conexão com a Internet. Reinicie a conexão. | Sim |
| 2016330893 | Você perdeu a conexão com a Internet. Reinicie a conexão. | Sim|
| 2016330892 | O roaming internacional está desabilitado. | Não|
| 2016330891 | A conexão de dados de celular para este dispositivo não pode ser acessada enquanto está sendo feita uma chamada telefônica. Aguarde a conclusão da chamada telefônica. | Sim|
| 2016330890 | A rede de celular deste dispositivo. Esses dispositivos não podem ser usados no momento. | Não|
| 2016330889 | Falha da conexão segura. Reinicie a conexão. | Sim|
| 2016330888 | Falha da avaliação de confiança do servidor. | Não|

## <a name="next-steps"></a>Próximas etapas

Você pode [verificar os detalhes](device-inventory.md) do dispositivo.
 
