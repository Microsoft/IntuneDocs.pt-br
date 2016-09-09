---
title: "O que acontece quando você cancela o registro do dispositivo Windows no Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38301b4e6964550008b08e99bf7016f1cc2561c3
ms.openlocfilehash: cb7510d92019f27e15ecc7d8666df3f4e09c8707


---


# O que acontece quando você cancela o registro do dispositivo Windows no Intune?

Para obter informações adicionais sobre o que acontece use o link, mostrado na seção “Nesse Artigo” acima, que corresponde ao tipo de dispositivo que você está usando.

- [Windows 10 Mobile, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 ou Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows RT que executa o Windows 8.1 ou Windows RT](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   O dispositivo não aparecerá mais no Portal da Empresa, e você não poderá mais instalar aplicativos do Portal da Empresa.

-   Se você tiver instalado o software cliente do Intune, ele será removido do computador.

-   O software Intune Endpoint Protection será removido do computador. Se o computador tiver outro software de proteção contra vírus instalado que esteja desabilitado, esse software poderá ser habilitado novamente depois que o Intune Endpoint Protection for removido. Você deverá verificar o computador depois de removê-lo do Portal da Empresa.

    > [!IMPORTANT]
    > Se outro software de proteção contra vírus não for habilitado novamente ou não estiver instalado, o seu computador poderá ficar vulnerável a vírus e malware.

-   As configurações alteradas no seu dispositivo quando ele foi adicionado (por exemplo, a desabilitação da câmera) não se aplicarão mais.

-   O computador não receberá mais as atualizações automáticas de software ou de software antivírus do serviço Intune. No entanto, dependendo de como estiver configurado, seu computador ainda poderá receber atualizações do Windows Server Update Services, Windows Update ou Microsoft Update.

Além disso, para Windows 8.1:

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Alguns aplicativos de correspondência, como Windows Mail, não poderão mais acessar os emails da empresa armazenados no seu dispositivo.

-   Talvez você não consiga se conectar à sua rede da empresa usando o Wi-Fi ou uma rede virtual privada.

-   Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.

## Windows 10 mobile, Windows Phone 8.1 ou Windows Phone 8

-   O aplicativo Portal da Empresa é desinstalado do dispositivo, o que significa que o dispositivo não aparecerá mais no Portal da Empresa, e você não poderá mais instalar aplicativos do aplicativo Portal da Empresa ou do site Portal da Empresa.

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Quaisquer configurações alteradas no seu dispositivo quando ele foi adicionado, por exemplo a desabilitação da câmera ou a solicitação de uma senha de determinado tamanho, não se aplicarão mais.

    > [!IMPORTANT]
    > As únicas exceções a isso são as políticas de criptografia, que ainda se aplicarão. Se a política da sua empresa solicitou a criptografia do seu Windows Phone, a única maneira de retirar a criptografia do seu telefone será redefini-lo usando o menu **Configurações** no seu Windows Phone.

## Windows RT que executa o Windows 8.1 ou Windows RT

-   O aplicativo Portal da Empresa é desinstalado do dispositivo, o que significa que o dispositivo não aparecerá mais no Portal da Empresa, e você não poderá mais instalar aplicativos do Portal da Empresa.

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Quaisquer configurações alteradas no seu dispositivo quando ele foi adicionado, por exemplo a desabilitação da câmera ou a solicitação de uma senha de determinado tamanho, não se aplicarão mais.

-   Talvez você não consiga mais se conectar à sua rede da empresa usando o Wi-Fi ou uma rede virtual privada.

-   Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.

-   Alguns aplicativos de correspondência, como Windows Mail, não poderão mais acessar os emails da empresa armazenados no seu dispositivo.

Quando você remover seu dispositivo Windows RT, acontecerá o seguinte:

-   O aplicativo Portal da Empresa é desinstalado do dispositivo, o que significa que o dispositivo não aparecerá mais no Portal da Empresa, e você não poderá mais instalar aplicativos do Portal da Empresa.

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Quaisquer configurações alteradas no seu dispositivo quando ele foi adicionado, por exemplo a desabilitação da câmera ou a solicitação de uma senha de determinado tamanho, não se aplicarão mais.

Se você tiver dúvidas, entre em contato com o administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).




<!--HONumber=Aug16_HO5-->


