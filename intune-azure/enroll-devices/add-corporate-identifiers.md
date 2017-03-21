---
title: Adicionar identificadores IMEI ao Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como adicionar identificadores corporativos (números IMEI) ao Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

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

> [!IMPORTANT]
> Alguns dispositivos com Android possuem vários números IMEI. O Intune armazena um número IMEI por dispositivo. Se você importar um número IMEI, mas não for o IMEI armazenado pelo Intune, o dispositivo será classificado como um dispositivo pessoal em vez de um dispositivo da empresa. Se você importar vários números IMEI para um dispositivo, os números não armazenados exibirão **Desconhecido** como o status do registro.

**Para excluir uma lista .csv de identificadores corporativos**

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registrar dispositivos** e selecione **Identificadores de Dispositivo Corporativo**.

3. Escolha **Excluir**.

