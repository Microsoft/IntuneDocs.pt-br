---
title: "Exibir o inventário de dispositivo do Intune"
titleSuffix: Intune on Azure
description: Saiba como exibir os dispositivos gerenciados com o Intune e entender seu hardware e seus aplicativos instalados.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3618c5ee0b4a7ff0e7b6a4d6ed58f77a2af0ba66
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-view-intune-device-inventory"></a>Como exibir o inventário de dispositivo do Intune


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

>[!NOTE]
> O Intune coleta o inventário de aplicativos apenas em dispositivos de propriedade da empresa. Os aplicativos não são inventariados nos dispositivos pessoais. No caso de PCs com Windows 10, o Intune coleta apenas um inventário de aplicativos modernos em dispositivos de propriedade da empresa. O Intune não coleta informações sobre aplicativos Win32 no dispositivo.