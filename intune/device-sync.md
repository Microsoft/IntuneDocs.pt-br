---
title: "Sincronizar dispositivos com o Microsoft Intune – Azure | Micrososft Docs"
description: "Sincronize dispositivos registrados ou gerenciados com o Microsoft Intune para obter as políticas e ações mais recentes. Inclui as etapas para sincronizar usando o portal do Azure e lista os códigos de erro que permitem tentar novamente."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d2d13ce2ed06549a6cd09fd766a0072b15fcd067
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions---intune"></a>Sincronizar dispositivos para obter as políticas e ações mais recentes – Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Sincronizar** força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele. Esse recurso pode ajudá-lo a validar e a solucionar problemas das políticas que você atribuiu, imediatamente, sem precisar esperar o próximo check-in agendado.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Sincronizar um dispositivo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtrar pelo **Intune** e escolha **Microsoft Intune**. 
3. Em **Intune**, selecione **Dispositivos** e escolha **Todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, escolha um dispositivo, escolha **Mais** e, em seguida, selecione a ação **Sincronizar**.
5. Selecione **Sim** para confirmar.


## <a name="retryable-error-codes"></a>Códigos de erro que permitem tentar novamente

Quando um administrador executar a ação do dispositivo **Sincronizar**, os aplicativos iOS e Android que tiverem falhado e gerado um código de erro que permite tentar novamente ainda estarão disponíveis para o dispositivo. No entanto, os aplicativos que tiverem gerado um código de erro que não permite tentar novamente deverão esperar sete dias para ficar novamente disponíveis para o dispositivo.


| Código de erro  | Descrição sugerida | Permite tentar novamente |
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

## <a name="next-step"></a>Próxima etapa

Escolha **Ações do dispositivo** para ver o status da ação de sincronização. 
