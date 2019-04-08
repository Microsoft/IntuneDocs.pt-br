---
title: Restrições de dispositivo do Microsoft Intune para o Windows 10 Team
titleSuffix: ''
description: Saiba mais sobre as restrições de dispositivo disponíveis para dispositivos que executam o Windows 10 Team.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f82950259746010c347e5dafa832a7335026721c
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799304"
---
# <a name="microsoft-intune-windows-10-team-device-restriction-settings"></a>Configurações de restrição de dispositivo do Windows 10 Team no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações de restrições de dispositivo do Microsoft Intune que podem ser definidas para dispositivos que executam o Windows 10 Team.


## <a name="apps-and-experience"></a>Aplicativos e experiência

- **Ativar tela quando alguém estiver no recinto** – Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.
- **Informações de reunião exibidas na tela de Boas-Vindas** – habilite essa opção para escolher as informações que serão exibidas no bloco Reuniões da tela de Boas-Vindas. Você pode:
    - **Mostrar somente organizador e hora**
    - **Mostrar organizador, hora e assunto (o assunto é oculto para reuniões privadas)**
- **URL da imagem de fundo da tela de Boas-Vindas** – Habilite essa configuração para exibir uma tela de fundo personalizada na tela de **Boas-Vindas** dos dispositivos com Windows 10 Team da URL especificada.<br>A imagem deve estar no formato PNG e a URL deve começar com **https://**.

## <a name="azure-operational-insights"></a>Insights operacionais do Azure

- **Insights Operacionais do Azure** – O Insights Operacionais do Azure, que faz parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.
Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Workspace** e uma **Chave do Workspace**.

## <a name="maintenance"></a>Manutenção

- **Janela de manutenção para atualizações** – Configura a o intervalo em que atualizações podem ocorrer no dispositivo. Você pode configurar a **Hora de início** do intervalo e sua **Duração em horas** (de 1 a 5 horas).

## <a name="wireless-projection"></a>Projeção sem fio

- **PIN para projeção sem fio** – Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.
- **Projeção sem fio Miracast** – selecione essa opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.
- **Canal de projeção sem fio Miracast** – Escolha o canal Miracast que será usado para estabelecer a conexão.


## <a name="next-steps"></a>Próximas etapas

Use as informações em [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md) para salvar e atribuir o perfil a usuários e dispositivos.
