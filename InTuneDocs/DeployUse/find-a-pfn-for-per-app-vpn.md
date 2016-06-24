---
# required metadata

title: Localizar um PFN (nome de família de pacote) para VPN por aplicativo | Microsoft Intune
description:
keywords:
author: nbigman
manager: [ALIAS]
ms.date: 05/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: tycast
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Localizar um PFN (nome de família de produtos) para a configuração de VPN por aplicativo

Há duas maneiras de localizar um PFN para que você possa configurar uma VPN por aplicativo.

## Localizar um PFN para um aplicativo que está instalado em um computador Windows 10 

Se o aplicativo no qual você está trabalhando já estiver instalado em um computador Windows 10, você poderá usar o cmdlet do PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) para obter o PFN.

A sintaxe para Get-AppxPackage é:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Observação: você precisará executar o PowerShell como administrador para recuperar o PFN

Por exemplo, para obter informações sobre todos os aplicativos universais instalados no computador use `Get-AppxPackage`.

Para obter informações sobre um aplicativo que você sabe o nome, ou parte do nome, use `Get-AppxPackage *<app_name>`. Observe o uso do caractere curinga, particularmente útil se você não tiver certeza do nome completo do aplicativo. Por exemplo, para obter as informações do OneNote, use `Get-AppxPackage *OneNote`.


Eis aqui as informações recuperadas do OneNote:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## Localizar um PFN se o aplicativo não estiver instalado em um computador

1.  Vá para https://www.microsoft.com/pt-br/store/apps
2.  Insira o nome do aplicativo na barra de pesquisa. No nosso exemplo, pesquise o OneNote.
3.  Clique no link para o aplicativo. Observe que a URL que você acessar tem uma série de letras no final. No nosso exemplo, a URL tem esta aparência:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  Em uma guia diferente, cole a seguinte URL, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`, (substituindo `<app id>` pela ID do aplicativo obtida em https://www.microsoft.com/pt-br/store/appss) a série de letras no final da URL na etapa 3. Em nosso exemplo do OneNote, você deve colar: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

No Edge, as informações que você deseja são exibidas; no Internet Explorer, clique em **Abrir** para ver as informações. O valor PFN é fornecido na primeira linha. Aqui está a aparência dos resultados do nosso exemplo:
 

`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Jun16_HO1-->


