---
title: Como monitorar informações e atribuições de aplicativo
titlesuffix: Microsoft Intune
description: Depois de atribuir um aplicativo a usuários ou dispositivos, use essas informações para ajudar a monitorar seu status.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01b7972a6a4dbb641f4c656190324d8572f9010c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Como monitorar atribuições e informações de aplicativo com o Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune fornece várias maneiras nas quais você pode monitorar as propriedades dos aplicativos que gerencia, além de seu status de atribuição.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado no grupo **Monitoramento + Gerenciamento**.
3. Escolha **Aplicativos móveis** e, em seguida, escolha **Aplicativos** no grupo **Gerenciar**.
5. Na lista de aplicativos, selecione um aplicativo que você deseja monitorar. Em seguida, você verá a folha de aplicativos com uma visão geral do status do dispositivo e o status do usuário.

## <a name="app-overview-blade"></a>Folha de visão geral de aplicativos

É possível usar a folha de aplicativos específica para examinar detalhes sobre o status de um aplicativo em seu ambiente.

### <a name="essentials"></a>Essentials
A seção **Fundamentos** contém as seguintes informações sobre o aplicativo:

 | **Detalhes do aplicativo**            | **Descrição**                                                      |
|------------------------|------------------------------------------------------------------|
| **Editor**          | Editor do aplicativo.                                            |
| **Sistema operacional**   | O sistema operacional do aplicativo (Windows, iOS, Android, etc.) |
| **Criado**             | A data e hora em que essa revisão foi criada.                         |
| **Atribuído**           | **Sim** ou **Não** se o aplicativo tiver sido atribuído.                  |

### <a name="device-and-user-status-graphs"></a>Grafos de status do dispositivo e do usuário
Os grafos mostram o número do status a seguir:

| **Status do dispositivo**       | **Descrição**                                       |
|-----------------------|-------------------------------------------------------|
| **Instalado**         | O número de aplicativos instalados.                         |
| **Não instalados**     | O número de aplicativos não instalados.                     |
| **Falha**            | O número de instalações com falha.                   |
| **Instalação pendente**   | O número de aplicativos no processo de instalação. |
| **Não aplicável**           | O número de aplicativos em que o status não é aplicável.            |

### <a name="device-install-status"></a>Status de instalação do dispositivo

Uma lista de status do dispositivo é exibida quando você seleciona **Status de instalação do dispositivo** na seção **Monitorar**. A tabela de detalhes inclui as seguintes colunas:

| **Coluna de dispositivo**      | **Descrição**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome do dispositivo**      | Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome com base em outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos.                                                                       |
| **Nome de usuário**        | O nome do usuário.                                                                                                                                                                                                                                      |
| **Plataforma**         | O sistema operacional do dispositivo (Windows, iOS, Android, etc.)                                                                                                                                                                                           |
| **Versão**          | O número de versão do aplicativo. Para aplicativos de linha de negócios, é exibido o número de versão completo do aplicativo. O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800) |
| **Status**           | O status do aplicativo.                                                                                                                                                                                                                                     |
| **Detalhes do status**   | Os detalhes do status.                                                                                                                                                                                                                                     |
| **Último check-in**    | Data da última sincronização do dispositivo com o Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Status de instalação do usuário

Uma lista de status de usuário é exibida quando você seleciona **Status de instalação do usuário** na seção **Monitorar**. A tabela de detalhes inclui as seguintes colunas:

| **Coluna de usuário**     | **Descrição**                           |
|---------------------|-------------------------------------------|
| **Nome**            | O nome do usuário no Azure AD.         |
| **Nome de usuário**       | O nome exclusivo do usuário.              |
| **Instalações**   | Número de instalações de aplicativos usadas pelo usuário. |
| **Falhas**        | Número de instalação com falha pelo usuário.     |
| **Não instalados**   | Número de aplicativos não instalados pelo usuário. |


## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como trabalhar com os dados do Intune, consulte [Usar o Intune Data Warehouse](reports-nav-create-intune-reports.md).
- Para saber mais sobre políticas de configuração de aplicativo, consulte [Políticas de configuração de aplicativo para o Intune](app-configuration-policies-overview.md).