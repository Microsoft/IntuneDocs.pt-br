---
title: "Especificar números IMEI | Microsoft Intune"
description: "O Microsoft Intune permite aos administradores importar números IMEI para plataformas de dispositivos móveis para ajudar a identificar dispositivos móveis corporativos"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 656c93771776fd317f2b8d91bc59125fba1eb0b9
ms.openlocfilehash: 8b19cb740ed34b479fa8c4f5e2c1d13f13cda1f4


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)
O Microsoft Intune permite aos administradores importar números IMEI (identidade de equipamentos móveis internacionais) para plataformas de dispositivos móveis usando números IMEI para ajudar a identificar dispositivos móveis corporativos. Depois que os dispositivos forem registrados no Intune, você poderá ver os dispositivos que importaram números IMEI em **Grupos** > **Visão Geral** > **Todos os Dispositivos**. **Grupo de dispositivos** exibe os dispositivos que importaram números IMEI como **Corporativo** na coluna **Propriedade**.

1. No [Console de administração do Microsoft Intune](http://manage.microsoft.com), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos da Pré-registrados da Empresa** &gt; **Por IMEI (todas as plataformas)** e escolha **Adicionar Dispositivos…**. Você pode adicionar dispositivos de duas maneiras:

    -   **Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv.

        |||
        |-|-|
        |&lt;IMEI nº 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
        |&lt;IMEI nº 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|
        Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Adicionar manualmente os detalhes do dispositivo** – insira o número IMEI e detalhes de até 15 dispositivos.

   O campo *Detalhes* é para uso administrativo. É possível especificar detalhes para ajudar a identificar o dispositivo na lista de dispositivos corporativos listados por ID de hardware. Essas informações não são enviadas para o dispositivo, mas serão exibidas no console do Intune.

2.   Escolha **Avançar**.
3.  No painel **Examinar Dispositivos**, você pode confirmar os números IMEI dos dispositivos importados. Você também pode decidir se deseja substituir **Detalhes** por números IMEI que estão sendo importados novamente. Você pode desmarcar a caixa de seleção **Substituir** para preservar os detalhes atuais. Escolha **Concluir** para importar os números IMEI.
4.  Os números IMEI importados e descrições são adicionados à lista **Por IMEI (todas as plataformas)**.

Quando o dispositivo com esse número IMEI é registrado no Intune, normalmente quando um usuário instala o aplicativo Portal da Empresa e conclui o processo de registro, o dispositivo é marcado como corporativo e aparece como registrado no grupo **Dispositivos IMEI**.



<!--HONumber=Nov16_HO3-->


