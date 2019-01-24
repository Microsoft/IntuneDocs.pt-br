---
title: Dados enviados pelo JAMF Pro ao Intune | Microsoft Intune
description: Lista de dados que o Jamf Pro envia ao Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5b58a92ed59d4485f06370672d8c335ff2fffcc7
ms.sourcegitcommit: 7c41f42d6e398ed46aa602ec8aaa4f39aaf92772
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54327917"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Dados enviados pelo Jamf Pro ao Intune

Quando você usa o [Jamf Pro](https://www.jamf.com) para gerenciar seus Macs de usuários finais com o Intune, o Jamf Pro captura informações de inventário sobre os dispositivos macOS gerenciados. O Jamf Pro reporta estas informações para o Intune:

* ID do dispositivo do Azure AD
* Estado de inventário do JAMF (estado de inventário de um computador com check-in realizado no Jamf Pro nas últimas 24 horas)
* Versão do SO
* ID do usuário do Azure AD
* Criptografado (FileVault 2)
* Status do gatekeeper
* Senha: número mínimo de conjuntos de caracteres
* Expiração da senha (dias)
* Tipo de senha - simples, alfanumérica ou desconhecido
* Impedir o logon automático
* Comprimento de senha obrigatório
* Senha: número de senhas anteriores para evitar a reutilização
* Proteção de integridade do sistema
* Hora do último check-in
* Tipo de arquitetura
* Slots de RAM disponíveis
* Capacidade da bateria
* ROM de inicialização
* Velocidade do barramento
* Tamanho do cache
* Nome do Dispositivo
* Junção de Domínios
* ID do Jamf
* Endereço MAC
* Marca
* Modelo
* Identificador de modelo
* Velocidade do NIC
* Número de núcleos
* Número de Processadores
* SO
* Plataforma
* Velocidade do Processador
* Tipo de Processador
* Endereço MAC secundário
* Número de Série
* Versão do SMC
* Total de RAM
* UDID
* Email do usuário


É possível remover um dispositivo gerenciado pelo Jamf do console do Intune selecionando **Excluir** na exibição **Todos os dispositivos**. A exclusão de dispositivos em massa pode ser habilitada selecionando vários aplicativos e clicando em **Excluir**.

Obtenha informações sobre como [remover um dispositivo gerenciado pelo Jamf nos documentos do Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Você também pode registrar um tíquete de suporte com o [Suporte do Jamf](https://www.jamf.com/support/) para obter suporte adicional. 

