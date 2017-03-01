---
title: "Adicionar identificadores IMEI ao Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como adicionar identificadores corporativos (números IMEI) ao Microsoft Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 8667f063de65fd5fa86149ac124b236a432eecef
ms.lasthandoff: 02/15/2017

---

# <a name="add-corporate-identifiers"></a>Adicionar identificadores corporativos

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

É possível criar uma lista de números de identidade de equipamentos de móveis internacional (IMEI) para identificar os dispositivos corporativos. Esses dispositivos podem ou não podem ser registrados e têm um estado de "Registrado" ou "Não contatado". "Não contatado" significa que o dispositivo nunca faz check-in no serviço do Intune.

Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione o identificador IMEI à coluna esquerda e os detalhes à coluna direita. O máximo atual para a lista é de 500 linhas.

Em um editor de texto, a lista .csv é semelhante a:

01 234567 890123, detalhes do dispositivo</br>
02 234567 890123, detalhes do dispositivo

**Para adicionar uma lista .csv de identificadores corporativos**

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registrar dispositivos** e selecione **Identificadores de Dispositivo Corporativo**.

3. Se você estiver importando um arquivo com novos detalhes que substituirão os existentes, selecione **Substituir os detalhes para os identificadores existentes** para que os novos detalhes substituam os existentes.

4. Navegue até o arquivo CSV IMEI e selecione **Adicionar**.

**Para excluir uma lista .csv de identificadores corporativos**

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registrar dispositivos** e selecione **Identificadores de Dispositivo Corporativo**.

3. Escolha **Excluir**.

