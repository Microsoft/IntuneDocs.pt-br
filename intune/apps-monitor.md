---
title: "Como monitorar informações e atribuições de aplicativo"
titlesuffix: Azure portal
description: "Depois de atribuir um aplicativo a usuários ou dispositivos, use essas informações para ajudar a monitorar seu status."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0298fc255b3c11a12b5bf225968d6f2303192053
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Como monitorar atribuições e informações de aplicativo com o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune fornece várias maneiras nas quais você pode monitorar as propriedades dos aplicativos que gerencia, além de seu status de atribuição.

1. Entre no Portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
3. Na carga de trabalho **Aplicativos Móveis**, escolha **Aplicativos** no grupo **Gerenciar**.
5. Na folha de lista de aplicativos, escolha um aplicativo. Você verá a folha <*nome do aplicativo*> **Status de instalação do dispositivo**.

## <a name="app-overview-blade"></a>Folha de visão geral de aplicativos

É possível usar a folha <*nome do aplicativo*> **Status de instalação do dispositivo** para examinar os detalhes sobre o status de um aplicativo em seu ambiente.

### <a name="essentials"></a>Essentials

A seção **Fundamentos** contém as seguintes informações sobre o aplicativo:

 - **Editor**  
Editor do aplicativo.
 - **Sistema operacional**  
O sistema operacional do aplicativo (Windows, iOS, Android, etc.)
 - **Criar**  
A hora em que esta revisão foi criada.
 - **Atribuído**  
**Sim** ou **Não** se o aplicativo tiver sido atribuído.

### <a name="status"></a>Status
Cada gráfico mostra as contagens para o seguintes status:

 - **Instalado**  
O número de aplicativos instalados.
 - **Não instalados**  
O número de aplicativos não instalados.
 - **Instalação pendente**  
O número de aplicativos no processo de instalação.
 - **Falha**  
O número de instalações com falha.
 - **Desconhecida**  
O número de aplicativos com um status desconhecido.

### <a name="device-status"></a>Status do dispositivo

Status do dispositivo. Um gráfico de rosca que exibe o status de instalação do aplicativo em dispositivos. Clique no gráfico para abrir uma lista de detalhes sobre o status do dispositivo. A tabela de detalhes inclui as seguintes colunas:

 - **Nome do dispositivo**  
Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos.
 - **Nome de usuário**  
O nome do usuário.
 - **Plataforma**  
O sistema operacional do dispositivo (Windows, iOS, Android, etc.)
 - **Versão**  
O número de versão do aplicativo. Para aplicativos de linha de negócios, é exibido o número de versão completo do aplicativo. O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800)
 - **Status**  
O status do aplicativo.
 - **Detalhes do status**  
Os detalhes do status.
 - **Último check-in**  
Data da última sincronização do dispositivo com o Intune.


### <a name="user-status"></a>Status do usuário

Status do usuário. Um gráfico de rosca que exibe o status de instalação do aplicativo para usuários. Clique no gráfico para abrir uma lista de detalhes sobre o status do dispositivo. A tabela de detalhes inclui as seguintes colunas:
 - **Nome**  
O nome do usuário no Azure AD.
 - **Nome de usuário**  
O nome exclusivo do usuário.
 - **Instalações**  
Número de instalações de aplicativos usadas pelo usuário.
 - **Falhas**  
Número de instalação com falha pelo usuário.
 - **Não instalados**  
Número de aplicativos não instalados pelo usuário.


## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como trabalhar com os dados do Intune, consulte [Usar o Intune Data Warehouse](reports-nav-create-intune-reports.md).