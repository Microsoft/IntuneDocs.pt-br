---
title: "O que acontece quando você cancela o registro do dispositivo Windows no Intune? | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 7a04c458044bf5e3ec5e050da7cf80f8dc924221


---


# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a>O que acontece quando você cancela o registro do dispositivo Windows no Intune?

Use os links no lado direito desta página, em **Neste artigo**, para localizar informações sobre o tipo de dispositivo que você está usando.


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a>Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista

-   O dispositivo não aparece mais no Portal da Empresa e você não pode mais instalar aplicativos do Portal da Empresa.

-   Se você tiver instalado o software cliente do Intune, ele será removido do computador.

-   O software Intune Endpoint Protection será removido do computador. Se o computador tiver outro software de proteção contra vírus instalado que esteja desabilitado, esse software poderá ser habilitado novamente depois que o Intune Endpoint Protection for removido. Verifique o computador depois de removê-lo do Portal da Empresa.

    > [!IMPORTANT]
    > Se outro software de proteção contra vírus não for habilitado novamente ou não estiver instalado, o seu computador poderá ficar vulnerável a vírus e malware.

-   Configurações que foram alteradas no seu dispositivo quando ele foi adicionado (por exemplo, a desabilitação da câmera) não se aplicam mais.

-   O computador não recebe mais as atualizações automáticas de software ou de software antivírus do serviço Intune. No entanto, dependendo de como estiver configurado, seu computador ainda pode receber atualizações do Windows Server Update Services, Windows Update ou Microsoft Update.

Além disso, para Windows 8.1:

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Alguns aplicativos de email, como o Windows Mail, não podem mais acessar os emails da empresa armazenados no seu dispositivo.

-   Talvez você não consiga se conectar à sua rede da empresa usando o Wi-Fi ou uma rede virtual privada.

-   Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.

## <a name="windows-10-mobile-and-windows-phone-81"></a>Windows 10 Mobile e Windows Phone 8.1

-   O aplicativo de Portal da Empresa é desinstalado do seu dispositivo. isso significa que o dispositivo não aparece mais no Portal da Empresa e você não pode instalar aplicativos do site do Portal da Empresa ou do aplicativo de Portal da Empresa.

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.

    > [!IMPORTANT]
    > As únicas exceções a isso são as políticas de criptografia, que ainda se aplicam. Se a política da sua empresa exigiu que você criptografasse seu Windows Phone, a única maneira de descriptografar o telefone será redefini-lo usando o menu **Configurações**.

## <a name="windows-rt-running-windows-81"></a>Windows RT executando o Windows 8.1

-   O aplicativo de Portal da Empresa é desinstalado do seu dispositivo. Isso significa que o dispositivo não aparece mais no Portal da Empresa e você não pode instalar aplicativos do Portal da Empresa.

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.

-   Talvez você não consiga mais se conectar à sua rede da empresa usando o Wi-Fi ou uma rede virtual privada.

-   Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.

-   Alguns aplicativos de email, como o Windows Mail, não podem mais acessar os emails da empresa armazenados no seu dispositivo.

Quando você remover seu dispositivo Windows RT, acontecerá o seguinte:

-   O aplicativo de Portal da Empresa é desinstalado do seu dispositivo. Isso significa que o dispositivo não aparece mais no Portal da Empresa e você não pode instalar aplicativos do Portal da Empresa.

-   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

-   Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.

Se tiver dúvidas, entre em contato com o administrador de TI. Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO2-->


