---
title: "Localizar um PFN (Nome de Família de Pacotes) para VPN por aplicativo | Microsoft Docs"
description: "Localize um PFN para que você possa configurar uma VPN por aplicativo."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: b0006416f2b078c8c0cf5eb14ccea4749604e1dc


---

# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Localizar um PFN (nome da família de pacotes) para a configuração de VPN por aplicativo

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Há duas maneiras de localizar um PFN para que você possa configurar uma VPN por aplicativo.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Localizar um PFN para um aplicativo que está instalado em um computador Windows 10

Se o aplicativo no qual você está trabalhando já estiver instalado em um computador Windows 10, você poderá usar o cmdlet do PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) para obter o PFN.

A sintaxe para Get-AppxPackage é:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
Você precisará executar o PowerShell como administrador para recuperar o PFN.

Por exemplo, para obter informações sobre todos os aplicativos universais instalados no computador, use `Get-AppxPackage`.

Para obter informações sobre um aplicativo do qual você sabe o nome, ou parte do nome, use `Get-AppxPackage *<app_name>`. Observe o uso do caractere curinga, particularmente útil se você não tiver certeza do nome completo do aplicativo. Por exemplo, para obter as informações sobre o OneNote, use `Get-AppxPackage *OneNote`.


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



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>Localizar um PFN se o aplicativo não estiver instalado em um computador

1.  Vá para https://www.microsoft.com/pt-br/store/apps.
2.  Insira o nome do aplicativo na barra de pesquisa. No nosso exemplo, pesquise o OneNote.
3.  Escolha o link para o aplicativo. Observe que a URL tem uma série de letras no final. No nosso exemplo, a URL tem esta aparência: `https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`.
4.  Em uma guia diferente, cole a URL a seguir, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Substitua `<app id>` pela ID do aplicativo obtida em https://www.microsoft.com/pt-br/store/apps – a série de letras no final da URL na etapa 3. Em nosso exemplo do OneNote, você colaria: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

O Microsoft Edge exibe as informações que você deseja. No Internet Explorer, selecione **Abrir** para ver as informações. O valor PFN é fornecido na primeira linha. Veja os resultados para nosso exemplo:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Dec16_HO2-->


