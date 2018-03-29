---
title: Exibir seus dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Exiba os detalhes do dispositivo, incluindo sistemas operacionais, espaço de armazenamento, fabricante e modelo. Obtenha uma lista de aplicativos instalados, verifique as políticas de conformidade e configure o TeamViewer com o Microsoft Intune no Azure. Semelhante à exibição de inventário dos dispositivos que você gerencia.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaaf3e9807a8eab66c24f4d1bb3c3c5ea9f4cfe0
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="see-device-details-in-intune"></a>Consultar detalhes do dispositivo no Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O recurso **Dispositivos** fornece detalhes adicionais sobre os dispositivos que você gerencia, incluindo o hardware e os aplicativos instalados. 

Este artigo mostra como exibir todos os dispositivos e suas propriedades no portal do Azure.

## <a name="view-your-device-details"></a>Exibir os detalhes do dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos**. Em Dispositivos, há várias opções:

   - **Visão geral**: obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executa.
   - **Gerenciar**: para ver uma lista de todos os dispositivos gerenciados, escolha **Todos os dispositivos** ou **Dispositivos do Azure AD**.
    Selecione um dos dispositivos na lista. Esta etapa abre a **Visão Geral do**<*nome do dispositivo*> , na qual você pode selecionar o seguinte:
     - **Visão geral**: veja o nome do dispositivo, o proprietário, se ele é um dispositivo BYOD (traga seu próprio dispositivo), quando foi feito seu check-in e outros detalhes.
     - **Hardware**: consulte o espaço livre de armazenamento, o modelo, o fabricante e outros detalhes sobre o dispositivo.
     - **Aplicativos descobertos**: veja uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.
     - **Conformidade do dispositivo**: exibe o estado de todas as políticas de conformidade que foram atribuídas ao dispositivo.
     - **Configuração do dispositivo**: exibe o estado de conformidade de todas as políticas de configuração de dispositivo atribuídas ao dispositivo.
   - **Monitor**: escolha **Ações do dispositivo** para ver uma lista das ações executadas nos dispositivos que você gerencia e seus estados atuais. **Logs de auditoria** – mostram o status de diferentes tarefas.
   - **Instalação** > **Conector do TeamViewer**: configure a administração remota nos dispositivos usando o software TeamViewer. Para ver mais detalhes, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](device-profile-android-teamviewer.md).

O Intune coleta uma lista de aplicativos que estão somente em dispositivos corporativos. Os aplicativos não são verificados em dispositivos pessoais. Em computadores Windows 10, são listados apenas os aplicativos modernos para dispositivos corporativos. O Intune não coleta informações sobre aplicativos Win32 no dispositivo. Dependendo da operadora usada pelos dispositivos, nem todos os aplicativos podem ser coletados.

## <a name="next-steps"></a>Próximas etapas
Veja o que mais você pode fazer para [gerenciar seus dispositivos](device-management.md) com o Intune.
