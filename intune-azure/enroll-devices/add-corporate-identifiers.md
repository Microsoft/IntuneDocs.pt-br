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
ms.sourcegitcommit: 15415f9f31d520d66257df3a7e134e4b1de8467c
ms.openlocfilehash: 8c9e6b39ee01697d993e5738ec35e8a64fc8e236
ms.lasthandoff: 04/07/2017

---

# <a name="add-corporate-identifiers"></a>Adicionar identificadores corporativos

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Como administrador de TI, você pode criar e importar um arquivo de valores separados por vírgulas (.csv) que lista os números IMEI (Identidade de equipamentos móveis internacionais) para identificar dispositivos corporativos. Cada número IMEI pode ter detalhes especificados na lista para fins administrativos.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Adicionar identificadores corporativos
Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione o identificador IMEI à coluna esquerda e os detalhes à coluna direita. Os detalhes limitam-se a 128 caracteres e são exclusivamente para uso administrativo. O dispositivo não exibe detalhes. O limite atual é de 500 linhas por arquivo .csv.

**Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv. 

|||
|-|-|
|&lt;IMEI nº 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
|&lt;IMEI nº 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|

Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Alguns dispositivos com Android possuem vários números IMEI. O Intune armazena um número IMEI por dispositivo. Se você importar um número IMEI, mas não for o IMEI armazenado pelo Intune, o dispositivo será classificado como um dispositivo pessoal em vez de um dispositivo da empresa. Se você importar vários números IMEI para um dispositivo, os números não armazenados exibirão **Desconhecido** como o status do registro.

**Para adicionar uma lista .csv de identificadores corporativos**

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e, em seguida, clique em **Adicionar**.

3. Na folha **Adicionar Identificadores**, especifique o tipo de identificador, **IMEI**. Você pode especificar se números importados anteriormente devem **substituir os detalhes para os identificadores existentes**.  

4. Clique no ícone de pasta e especifique o caminho para a lista que quer importar. Navegue até o arquivo CSV IMEI e selecione **Adicionar**.

Depois de importados, esses dispositivos podem ou não ser registrados, e têm um estado de **Registrado** ou**Não contatado**. **Não contatado** significa que o dispositivo nunca se comunicou com o serviço do Intune.

## <a name="delete--corporate-identifiers"></a>Excluir identificadores corporativos

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e escolha **Excluir**.

3. Na folha **Excluir Identificadores**, navegue para o arquivo .csv de IDs de dispositivo para excluir e, em seguida, clique em **Excluir**.

## <a name="imei-specifications"></a>Especificações do IMEI
Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

