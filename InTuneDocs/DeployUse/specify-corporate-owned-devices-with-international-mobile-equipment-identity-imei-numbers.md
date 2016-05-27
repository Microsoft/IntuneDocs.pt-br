---
# required metadata

title: Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional) | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)
O Microsoft Intune permite aos administradores importar números IMEI para plataformas de dispositivos móveis com números IMEI para ajudar a identificar dispositivos móveis corporativos. Depois de registrado no Intune, dispositivos com números IMEI importados são marcados como corporativos, que podem ser usados para a aplicação de políticas que são diferentes das que foram aplicadas a dispositivos de propriedade pessoal.

1. No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os dispositivos corporativos pré-registrados** &gt; **Por IMEI (Todas as plataformas)** e clique em **Adicionar dispositivos…**. Você pode adicionar dispositivos de duas maneiras:

    -   **Carregar um arquivo CSV contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, com limite de 5000 dispositivos ou 5 MB por arquivo csv.

        |||
        |-|-|
        |&lt;Nº IMEI 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
        |&lt;Nº IMEI 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|
        Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Adicionar manualmente os detalhes do dispositivo** - insira o número IMEI e detalhes de até cinco dispositivos

   *Detalhes* são para uso administrativo para que você possa identificar qual número IMEI está associado um dispositivo. Essas informações não são enviadas para o dispositivo, mas serão exibidas no console do Intune.

2.   Clique em **Avançar**.
3.  No painel **Examinar Dispositivos**, você pode confirmar quais números IMEI do dispositivo são importados. Você também pode decidir se deseja substituir **Detalhes** por números IMEI que estão sendo importados novamente. Você pode desmarcar a caixa de seleção **Substituir** para preservar os detalhes atuais. Clique em **Concluir** para importar os números IMEI.
4.  Os números IMEI adicionados e descrições são adicionados à lista **Por IMEI (todas as plataformas)**.

Quando o dispositivo com esse número IMEI é registrado, normalmente quando um usuário instala o aplicativo Portal da Empresa e conclui o processo de registro, o dispositivo é marcado como corporativo e aparece como registrado no grupo **Dispositivos IMEI**.


<!--HONumber=May16_HO1-->


