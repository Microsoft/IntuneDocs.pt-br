---
title: Adicionar identificadores IMEI ao Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como adicionar identificadores corporativos (números IMEI) ao Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: e0a853c34c6d38e8fae6f4712ba6c2b767e5d0ba
ms.lasthandoff: 03/22/2017

---

# <a name="add-corporate-identifiers"></a>Adicionar identificadores corporativos

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Como administrador de TI, você pode criar e importar um arquivo de valores separados por vírgulas (.csv) que lista os números IMEI (Identidade de equipamentos móveis internacionais) para identificar dispositivos corporativos. Cada número IMEI pode ter detalhes especificados na lista para fins administrativos.

## <a name="create-a-csv-file"></a>Criar um arquivo .csv
Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione o identificador IMEI à coluna esquerda e os detalhes à coluna direita. Os detalhes são limitados a 128 caracteres. O limite atual é de 500 linhas por arquivo .csv.

**Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv.

|||
|-|-|
|&lt;IMEI nº 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
|&lt;IMEI nº 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**Para adicionar uma lista .csv de identificadores corporativos**

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registrar dispositivos** e selecione **Identificadores de Dispositivo Corporativo**.

3. Se você estiver importando um arquivo com novos detalhes que substituirão os existentes, selecione **Substituir os detalhes para os identificadores existentes** para que os novos detalhes substituam os existentes.

4. Navegue até o arquivo CSV IMEI e selecione **Adicionar**.

> [!IMPORTANT]
> Alguns dispositivos com Android possuem vários números IMEI. O Intune armazena um número IMEI por dispositivo. Se você importar um número IMEI, mas não for o IMEI armazenado pelo Intune, o dispositivo será classificado como um dispositivo pessoal em vez de um dispositivo da empresa. Se você importar vários números IMEI para um dispositivo, os números não armazenados exibirão **Desconhecido** como o status do registro.

Depois de importados, esses dispositivos podem ou não ser registrados, e têm um estado de **Registrado** ou**Não contatado**. **Não contatado** significa que o dispositivo nunca se comunicou com o serviço do Intune.

## <a name="delete-a-csv-list"></a>Excluir uma lista .csv

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registrar dispositivos** e selecione **Identificadores de Dispositivo Corporativo**.

3. Escolha **Excluir**.

Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

