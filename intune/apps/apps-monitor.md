---
title: Monitorar informações e atribuições de aplicativo
titleSuffix: Microsoft Intune
description: Depois de atribuir um aplicativo a usuários ou dispositivos, use essas informações para ajudá-lo a monitorar o status do aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2bd5b26073611d9ff974d4a53f7794919e8672c7
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513530"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorar atribuições e informações de aplicativo com o Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune fornece várias maneiras de monitorar as propriedades dos aplicativos que você gerencia e de gerenciar o status de atribuição do aplicativo.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos**.
3. Na lista de aplicativos, selecione um aplicativo para monitorar. Em seguida, você verá o painel de aplicativos com uma visão geral do status do dispositivo e do status do usuário.

> [!NOTE]
> Os aplicativos da Android Store implantados como **Disponíveis** não relatam o próprio status de instalação.
>
> Para aplicativos do Google Play Gerenciado implantados em dispositivos de perfil de trabalho do Android Enterprise, você pode exibir o status e o número de versão do aplicativo instalado em um dispositivo usando o Intune. 

## <a name="app-overview-pane"></a>Painel de visão geral do aplicativo

No painel de aplicativo, você pode examinar os detalhes sobre o status de um aplicativo em seu ambiente.

### <a name="essentials"></a>Essentials
A seção **Fundamentos** contém as seguintes informações sobre o aplicativo:

 | **Detalhes do aplicativo**            | **Descrição**                                                      |
|------------------------|------------------------------------------------------------------|
| **Editor**          | O editor do aplicativo.                                            |
| **Sistema operacional**   | O sistema de operacional do aplicativo (Windows, iOS/iPadOS, Android e assim por diante). |
| **Criado**             | A data e hora em que essa revisão foi criada. <b>**Observação**: esse valor de data é atualizado quando um administrador de TI altera os metadados do aplicativo, como a categoria de aplicativo ou a descrição do aplicativo.                        |
| **Atribuído**           | Se o aplicativo foi atribuído (**Sim** ou **Não**).                  |

### <a name="device-and-user-status-graphs"></a>Grafos de status do dispositivo e do usuário
Os gráficos mostram o número de aplicativos para o seguinte status:

| **Status do dispositivo**       | **Descrição**                                       |
|-----------------------|-------------------------------------------------------|
| **Instalado**         | O número de aplicativos instalados.                         |
| **Não instalados**     | O número de aplicativos não instalados.                     |
| **Falha**            | O número de instalações com falha.                   |
| **Instalação pendente**   | O número de aplicativos que estão no processo de instalação. |
| **Não aplicável**           | O número de aplicativos para os quais o status não é aplicável.            |

> [!NOTE]
> Lembre-se de que os aplicativos Android (.APK) de linha de negócios implantados como **Disponível com ou sem registro** relatam apenas o status de instalação do aplicativo para dispositivos registrados. O status de instalação do aplicativo não está disponível para dispositivos que não estão registrados no Intune.

### <a name="device-install-status"></a>Status de instalação do dispositivo

Uma lista de status do dispositivo é exibida quando você seleciona **Status de instalação do dispositivo** na seção **Monitorar** do menu. A tabela de detalhes inclui as seguintes colunas:

| **Coluna de dispositivo**      | **Descrição**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome do dispositivo**      | Nome do dispositivo em plataformas que permitem nomear um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo não está disponível para nenhum outro dispositivo.                                                                       |
| **Nome de usuário**        | O nome do usuário.                                                                                                                                                                                                                                      |
| **Plataforma**         | O sistema operacional do dispositivo (Windows, iOS/iPadOS, Android etc.).                                                                                                                                                                                           |
| **Versão**          | O número de versão do aplicativo. Para aplicativos de linha de negócios e da Microsoft Store para Empresas, é exibido o número completo da versão do aplicativo. O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800). Para aplicativos padrão da Loja, nenhuma versão é exibida. |
| **Status**           | O status do aplicativo.                                                                                                                                                                                                                                     |
| **Detalhes do status**   | Os detalhes do status.                                                                                                                                                                                                                                     |
| **Último check-in**    | A data da última sincronização do dispositivo com o Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Status de instalação do usuário

Uma lista de status do usuário é exibida quando você seleciona **Status de instalação do usuário** na seção **Monitorar** do menu. A tabela de detalhes inclui as seguintes colunas:

| **Coluna do usuário**     | **Descrição**                           |
|---------------------|-------------------------------------------|
| **Nome**            | O nome do usuário no Azure Active Directory.         |
| **Nome de usuário**       | O nome exclusivo do usuário.              |
| **Instalações**   | O número de aplicativos instalados pelo usuário. |
| **Falhas**        | O número de instalações de aplicativo com falha para o usuário.     |
| **Não instalados**   | O número de aplicativos não instalados pelo usuário. |


## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como trabalhar com os dados do Intune, veja [Usar o Intune Data Warehouse](../reports-nav-create-intune-reports.md).
- Para saber mais sobre políticas de configuração de aplicativo, consulte [Políticas de configuração de aplicativo para o Intune](app-configuration-policies-overview.md).
