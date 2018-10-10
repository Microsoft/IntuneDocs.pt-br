---
title: Adicionar identificadores empresariais ao Intune
titlesuffix: Microsoft Intune
description: Saiba como adicionar identificadores empresariais (método de registro, IMEI e número de série) ao Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e46951be5048e0bcf2af5b2d4320744f6d6e47e8
ms.sourcegitcommit: 3785e506ef5fbc474b3e09e87412d4b673bbdbb8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46541948"
---
# <a name="identify-devices-as-corporate-owned"></a>Identificar dispositivos como corporativos

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como um administrador do Intune, você pode identificar dispositivos como corporativos para refinar a identificação e gerenciamento. O Intune pode executar tarefas de gerenciamento adicionais e coletar informações adicionais como o número de telefone completo e um inventário de aplicativos de dispositivos corporativos. Você também pode definir restrições de dispositivo para bloquear o registro de dispositivos que não sejam corporativos.

No momento do registro, o Intune atribui automaticamente status corporativos em dispositivos que são:

- O dispositivo foi registrado com uma conta do [gerenciador de registros de dispositivo](device-enrollment-manager-enroll.md) (todas as plataformas)
- O dispositivo foi registrado com o [Programa de Registro de Dispositivos](device-enrollment-program-enroll-ios.md) da Apple, o [Apple School Manager](apple-school-manager-set-up-ios.md) ou o [Apple Configurator](apple-configurator-enroll-ios.md) (somente iOS)
- [O dispositivo foi identificado como corporativo antes do registro](#identify-corporate-owned-devices-with-imei-or-serial-number) com um números IMEI (identificação internacional de equipamento móvel) (todas as plataformas com números IMEI) ou com um número de série (iOS e Android)
- Adicionado ao Azure Active Directory como um dispositivo Windows 10 Enterprise
- Configurados como Corporativo na [lista das propriedades do dispositivo](#change-device-ownership)

Após o registro, você pode [alterar a configuração de propriedade](#change-device-ownership) entre **Pessoal** e **Corporativo**.

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identificar dispositivos corporativos com IMEI ou número de série

Como administrador do Intune, você pode criar e importar um arquivo .csv (valores separados por vírgula) que liste os números IMEI ou os números de série. O Intune usa esses identificadores para especificar a propriedade do dispositivo como corporativo durante o registro. Você pode declarar números IMEI em todas as plataformas com suporte. Somente é possível declarar o número de série para dispositivos iOS, macOS e Android. Cada número IMEI ou de série pode ter detalhes especificados na lista para fins administrativos.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Saiba como localizar o número de série de um dispositivo Apple](https://support.apple.com/HT204308).<br>
[Saiba como localizar o número de série do seu dispositivo Android](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers-by-using-a-csv-file"></a>Adicionar identificadores corporativos usando um arquivo .csv
Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho. Adicione os números de série ou IMEI à coluna esquerda e os detalhes à coluna direita. Apenas um tipo de ID, IMEI ou número de série, pode ser importado para o mesmo arquivo .csv. Os detalhes limitam-se a 128 caracteres e são exclusivamente para uso administrativo. O dispositivo não exibe detalhes. O limite atual é de 5 mil linhas por arquivo .csv.

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
>A tentativa de fazer upload de um arquivo com números de série que contêm pontos (.) causará uma falha no upload. Não há suporte para números de série com pontos.

### <a name="upload-a-csv-list-of-corporate-identifiers"></a>Carregar uma lista .csv de identificadores corporativos

1. No [Intune no portal do Azure](https://portal.azure.com), escolha **Registro de dispositivos** > **Identificadores de dispositivo corporativo** > **Adicionar** > **Carregar arquivo CSV**.

   ![Espaço de trabalho do identificador de dispositivo corporativo com o botão Adicionar realçado](./media/add-corp-id.png)

2. Na folha **Adicionar identificadores**, especifique o tipo de identificador: **IMEI** ou **Número de série**.

3. Clique no ícone de pasta e especifique o caminho para a lista que quer importar. Navegue até o arquivo .csv e escolha **Adicionar**. 

4. Se o arquivo .csv contiver identificadores corporativos que já estejam no Intune, mas tenham detalhes diferentes, o pop-up **Examinar identificadores duplicados** será exibido. Selecione os identificadores que você deseja substituir no Intune e escolha **OK** para adicionar os identificadores. Para cada identificador, somente a primeira duplicata será comparada.

## <a name="manually-enter-corporate-identifiers"></a>Inserir os identificadores corporativos manualmente

1. No [Intune no portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** > **Identificadores de dispositivo corporativo** > **Adicionar** > **Inserir manualmente**.

2. Na folha **Adicionar identificadores**, especifique o tipo de identificador: **IMEI** ou **Número de série**.

3. Insira o **Identificador** e os **Detalhes** de cada identificador que você deseja adicionar. Ao terminar de inserir os identificadores, escolha **Adicionar**.

5. Se você inserir identificadores corporativos que já estejam no Intune, mas tenham detalhes diferentes, o pop-up **Examinar identificadores duplicados** será exibido. Selecione os identificadores que você deseja substituir no Intune e escolha **OK** para adicionar os identificadores. Para cada identificador, somente a primeira duplicata será comparada.

Clique em **Atualizar** para ver os novos identificadores de dispositivo.

Os dispositivos importados não são necessariamente registrados. Os dispositivos podem apresentar o estado de **Registrado** ou **Não contatado**. **Não contatado** significa que o dispositivo nunca se comunicou com o serviço do Intune.

## <a name="delete-corporate-identifiers"></a>Excluir identificadores corporativos

1. No [Intune no portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** > **Identificadores de dispositivo corporativo**.
2. Selecione os identificadores de dispositivo que você deseja excluir e escolha **Excluir**.
3. Confirme a exclusão.

Excluir um identificador corporativo para um dispositivo registrado não altera a propriedade do dispositivo. Para alterar a propriedade de um dispositivo, acesse **Dispositivos** selecione o dispositivo, escolha **Propriedades** e altere a **Propriedade do dispositivo**.

## <a name="imei-specifications"></a>Especificações do IMEI
Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Alterar a propriedade do dispositivo

As propriedades do dispositivo exibem **Propriedade** para o registro de cada dispositivo no Intune. Como administrador, você pode especificar os dispositivos como **Pessoais** ou **Corporativos**.

**Para alterar a propriedade do dispositivo:**
1. No [Intune no portal do Azure](https://portal.azure.com), acesse **Dispositivos** e escolha o dispositivo.
2. Escolha **Propriedades**.
3. Especifique a **Propriedade do dispositivo** como **Pessoal** ou **Corporativo**.

   ![Propriedades do dispositivo mostrando as opções Propriedade do dispositivo e Categoria do dispositivo](./media/device-properties.png)
