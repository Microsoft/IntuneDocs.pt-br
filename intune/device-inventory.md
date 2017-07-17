---
title: "Exibir o inventário de dispositivo do Intune"
titleSuffix: Intune on Azure
description: Saiba como exibir os dispositivos gerenciados com o Intune e entender seu hardware e seus aplicativos instalados.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dae92c117bcf8a4a8ff133ed613f9f77ea0c07c2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Como exibir o inventário de dispositivo do Intune
<a id="how-to-view-intune-device-inventory" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A carga de trabalho **Dispositivos** fornece informações sobre os dispositivos gerenciados, incluindo suas funcionalidades de hardware e os aplicativos instalados neles. 

Para exibir o inventário de dispositivo:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.

Agora, selecione uma das seguintes opções:

- **Visão geral** Obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executado.
- **Gerenciar** – Escolha **Todos os Dispositivos** para ver uma lista de todos os dispositivos gerenciados.
    Selecione um desses dispositivos na lista para abrir a folha <*nome do dispositivo*> **Visão geral** na qual você pode selecionar um destes:
    - **Visão geral** – Veja informações gerais sobre o dispositivo, incluindo seu nome, proprietário, se ele é um dispositivo BYOD, quando foi seu último check-in e muito mais.
    ![Visão geral do dispositivo](./media/device-overview.png)
    - **Hardware** – Consulte informações mais detalhadas sobre o dispositivo, inclusive o espaço de armazenamento livre, modelo e fabricante, entre outros.
    ![Inventário de hardware de dispositivo gerenciado](./media/hardware-inventory.png)
    - **Aplicativos descobertos** – Exibe uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.
    ![Nó Aplicativos descobertos](./media/detected-applications.png)
    - **Conformidade do dispositivo** – Exibe o estado de conformidade de todas as políticas de conformidade que foram atribuídas ao dispositivo.
    - **Configuração do dispositivo** – Exibe o estado de conformidade de todas as políticas de configuração do dispositivo que foram atribuídas a ele.
- **Monitorar** Escolha **Ações de Dispositivo** para ver uma lista de ações de dispositivo que foram realizadas em dispositivos gerenciados por você, bem como o estado atual dessas ações.
- **Instalação** > **Conector do TeamViewer** – Permite configurar a administração remota em dispositivos que usam o software do TeamViewer. Para ver mais detalhes, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](/intune/device-profile-android-teamviewer).


