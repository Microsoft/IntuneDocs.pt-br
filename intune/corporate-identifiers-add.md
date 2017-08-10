---
title: Adicionar identificadores IMEI ao Intune
titleSuffix: Intune on Azure
description: "Saiba como adicionar identificadores corporativos (números IMEI) ao Microsoft Intune. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b38bf2da70537d07a050fa21be9a2a3062ca84b
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="add-corporate-identifiers"></a>Adicionar identificadores corporativos

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, você pode criar e importar um arquivo de valores separados por vírgulas (.csv) que relaciona números IMEI (International Mobile Equipment Identifier) ou números de série. O Intune usa esses identificadores para especificar a propriedade dos dispositivos como corporativos. Você pode declarar números IMEI em todas as plataformas com suporte. Somente é possível declarar o número de série para dispositivos iOS e Android. Cada número IMEI ou de série pode ter detalhes especificados na lista para fins administrativos.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Saiba como localizar o número de série de um dispositivo Apple](https://support.apple.com/HT204308).<br>
[Saiba como localizar o número de série do dispositivo Android](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Adicionar identificadores corporativos
Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione os números de série ou IMEI à coluna esquerda e os detalhes à coluna direita. Apenas um tipo de ID, IMEI ou número de série, pode ser importado para o mesmo arquivo .csv. Os detalhes limitam-se a 128 caracteres e são exclusivamente para uso administrativo. O dispositivo não exibe detalhes. O limite atual é de 500 linhas por arquivo .csv.

**Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv.

|||
|-|-|
|&lt;ID nº 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
|&lt;ID nº 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|

Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Alguns dispositivos com Android possuem vários números IMEI. O Intune lê somente um número IMEI por dispositivo registrado. Quando você importa um número IMEI, mas ele não está inventariado pelo Intune, o dispositivo é classificado como pessoal em vez de um dispositivo de propriedade da empresa. Se importar vários números IMEI para um dispositivo, os números não inventariados exibirão **Desconhecido** como status do registro.<br>
>Observe também: não há garantia de que os números de série para Android sejam exclusivos ou estejam presentes. Verifique junto ao fornecedor do dispositivo para saber se o número de série é uma ID de dispositivo confiável.
>Os números de série informados pelo dispositivo no Intune podem não corresponder à ID exibida nos menus Configurações ou Sobre do dispositivo Android. Verifique o tipo de número de série informado pelo fabricante do dispositivo.


**Para adicionar uma lista .csv de identificadores corporativos**

1. No portal do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e, em seguida, clique em **Adicionar**.

 ![Captura de tela de espaço de trabalho do identificador de dispositivo corporativo com o botão Adicionar realçado.](./media/add-corp-id.png)

2. Na folha **Adicionar identificadores**, especifique o tipo de identificador: **IMEI** ou **Número de série**. Você pode especificar se números importados anteriormente devem **substituir os detalhes para os identificadores existentes**.

3. Clique no ícone de pasta e especifique o caminho para a lista que quer importar. Navegue para o arquivo .csv e selecione **Adicionar**. Clique em **Atualizar** para ver os novos identificadores de dispositivo.

Os dispositivos importados não são necessariamente registrados. Os dispositivos podem apresentar o estado de **Registrado** ou **Não contatado**. **Não contatado** significa que o dispositivo nunca se comunicou com o serviço do Intune.

## <a name="delete-corporate-identifiers"></a>Excluir identificadores corporativos

1. No portal do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e escolha **Excluir**.

3. Na folha **Excluir Identificadores**, navegue para o arquivo .csv de IDs de dispositivo para excluir e, em seguida, clique em **Excluir**.

## <a name="imei-specifications"></a>Especificações do IMEI
Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
