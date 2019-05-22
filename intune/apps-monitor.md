---
title: Monitorar informações e atribuições de aplicativo
titleSuffix: Microsoft Intune
description: Depois de atribuir um aplicativo a usuários ou dispositivos, use essas informações para ajudá-lo a monitorar o status do aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b3cba546be350f47c1a57f47b8eddf85323dc74
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567225"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorar atribuições e informações de aplicativo com o Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune fornece várias maneiras de monitorar as propriedades dos aplicativos que você gerencia e de gerenciar o status de atribuição do aplicativo.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No menu **Intune**, selecione **Aplicativos clientes**.
4. Na seção **Gerenciar** do menu, selecione **Aplicativos**.
5. Na lista de aplicativos, selecione um aplicativo para monitorar. Em seguida, você verá o painel de aplicativos com uma visão geral do status do dispositivo e do status do usuário.

> [!NOTE]
> Os aplicativos da Android Store que são implantados como **Disponível** e aplicativos de LOB Android implantados como **Disponível com ou sem registro** não relatam seu status de instalação.

## <a name="app-overview-pane"></a>Painel de visão geral do aplicativo

No painel de aplicativo, você pode examinar os detalhes sobre o status de um aplicativo em seu ambiente.

### <a name="essentials"></a>Essentials
A seção **Fundamentos** contém as seguintes informações sobre o aplicativo:

 | **Detalhes do aplicativo**            | **Descrição**                                                      |
|------------------------|------------------------------------------------------------------|
| **Editor**          | O editor do aplicativo.                                            |
| **Sistema operacional**   | O sistema de operacional do aplicativo (Windows, iOS, Android e assim por diante). |
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
> O número de aplicativos descobertos pode não corresponder à contagem do status de instalação de aplicativos. Possibilidades de inconsistências incluem:
>    - Uma alteração de direcionamento de um aplicativo gerenciado instalado pode fazer com que a contagem de instalações na folha de status diminua, mas continue a ser informada nos aplicativos detectados.
>    - O direcionamento de várias instâncias do mesmo aplicativo em um locatário resultará em contagens diferentes devido à potencial sobreposição de usuários ou dispositivos. Cada instância do aplicativo contará usuários sobrepostos, mas os aplicativos detectados terão contagens duplicadas.
>    - Os aplicativos detectados e status de aplicativos são coletados em intervalos de tempo diferentes, o que pode causar uma discrepância na contagem de aplicativos.
> 
> Além disso, lembre-se de que os aplicativos Android implantados como **Disponível com ou sem registro** relatam apenas o status de instalação do aplicativo para dispositivos registrados. O status de instalação do aplicativo não está disponível para dispositivos que não estão registrados no Intune.

### <a name="device-install-status"></a>Status de instalação do dispositivo

Uma lista de status do dispositivo é exibida quando você seleciona **Status de instalação do dispositivo** na seção **Monitorar** do menu. A tabela de detalhes inclui as seguintes colunas:

| **Coluna de dispositivo**      | **Descrição**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome do dispositivo**      | Nome do dispositivo em plataformas que permitem nomear um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo não está disponível para nenhum outro dispositivo.                                                                       |
| **Nome de usuário**        | O nome do usuário.                                                                                                                                                                                                                                      |
| **Plataforma**         | O sistema operacional do dispositivo (Windows, iOS, Android etc.).                                                                                                                                                                                           |
| **Versão**          | O número de versão do aplicativo. Para aplicativos LOB (linha de negócios), é exibido o número completo de versão do aplicativo. O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800). Para aplicativos da Store, nenhuma versão é mostrada. |
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

- Para saber mais sobre como trabalhar com os dados do Intune, veja [Usar o Intune Data Warehouse](reports-nav-create-intune-reports.md).
- Para saber mais sobre políticas de configuração de aplicativo, consulte [Políticas de configuração de aplicativo para o Intune](app-configuration-policies-overview.md).
