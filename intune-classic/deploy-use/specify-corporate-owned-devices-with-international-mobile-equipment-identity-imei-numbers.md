---
title: "Especificar números IMEI"
description: "O Microsoft Intune permite aos administradores importar números IMEI para plataformas de dispositivos móveis para ajudar a identificar dispositivos móveis corporativos"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9038670a4c0b4bf52868ba739336dd35366eed2f
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune permite aos administradores importar números IMEI (identidade de equipamentos móveis internacionais) para plataformas de dispositivos móveis usando números IMEI para ajudar a identificar dispositivos móveis corporativos. Depois que os dispositivos forem registrados no Intune, você poderá ver os dispositivos que importaram números IMEI em **Grupos** > **Visão Geral** > **Todos os Dispositivos**. **Grupo de dispositivos** exibe os dispositivos que importaram números IMEI como **Corporativo** na coluna **Propriedade**.

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos da Pré-registrados da Empresa** &gt; **Por IMEI (todas as plataformas)** e escolha **Adicionar Dispositivos…**. Você pode adicionar dispositivos de duas maneiras:

    -   **Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv. O campo de detalhes é limitado a 128 caracteres. 

        |||
        |-|-|
        |&lt;IMEI nº 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
        |&lt;IMEI nº 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|
        Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

        ```
        01234567890123,device details
        02234567890123,device details
        ```

    -   **Adicionar manualmente os detalhes do dispositivo** – insira o número IMEI e detalhes de até 15 dispositivos.

   O campo *Detalhes* é para uso administrativo. É possível especificar detalhes para ajudar a identificar o dispositivo na lista de dispositivos corporativos listados por ID de hardware. Essas informações não são enviadas para o dispositivo, mas serão exibidas no console do Intune.

2.   Escolha **Avançar**.
3.  No painel **Examinar Dispositivos**, você pode confirmar os números IMEI dos dispositivos importados. Você também pode decidir se deseja substituir **Detalhes** por números IMEI que estão sendo importados novamente. Você pode desmarcar a caixa de seleção **Substituir** para preservar os detalhes atuais. Escolha **Concluir** para importar os números IMEI.
4.  Os números IMEI importados e descrições são adicionados à lista **Por IMEI (todas as plataformas)**.

> [!IMPORTANT]
> Se você estiver importando números IMEI para dispositivos Android, lembre-se de que alguns dispositivos Android podem ter vários números IMEI. Se você importar um número IMEI, mas não for o IMEI relatado para o Intune pelo dispositivo, o dispositivo será classificado como um dispositivo pessoal em vez de um dispositivo da empresa.

Quando o dispositivo com esse número IMEI é registrado no Intune, normalmente quando um usuário instala o aplicativo Portal da Empresa e conclui o processo de registro, o dispositivo é marcado como corporativo e aparece como registrado no grupo **Dispositivos IMEI**.

>[!NOTE]
> Quando sua organização tiver migrado para o novo Portal do Azure em um futuro próximo, você verá uma alteração nesse recurso. No console do administrador do Intune existente, os administradores podem aceitar detalhes associados de um CSV carregado e substituir os detalhes existentes para identificadores de hardware individuais. No novo Portal do Azure, você poderá substituir automaticamente os detalhes para todos os identificadores de hardware ou ignorar todos os novos detalhes para identificadores existentes.

Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
