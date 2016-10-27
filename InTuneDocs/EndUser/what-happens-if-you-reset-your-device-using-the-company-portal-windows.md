---
title: "O que acontece quando você redefine o dispositivo Windows usando o Portal da Empresa? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ee6e275-d1ec-4da3-bbef-d5da2c61a02a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08f31db90f324ef5f93076c4e13bfa5328a15adc
ms.openlocfilehash: b597e3557ec2c5661490b417e1d0459eb4e8b477


---


# O que acontece quando você redefine o dispositivo Windows usando o Portal da Empresa?

Quando você usa o aplicativo de Portal da Empresa ou o [site de Portal da Empresa](reset-your-device-cpwebsite.md) para redefinir o dispositivo do Windows, ele redefine o dispositivo para as configurações de fábrica e exclui todos os aplicativos, configurações e dados, incluindo seus dados pessoais. O que acontece em cada dispositivo depende do tipo de dispositivo que você tem e de como ele é usado, conforme descrito na tabela a seguir. Para obter instruções sobre como redefinir o dispositivo perdido ou roubado, consulte [Reset (erase) your lost or stolen device](reset-erase-your-lost-or-stolen-device-windows.md) (Redefinir (apagar) o dispositivo perdido ou roubado).

|Gerenciamento e configuração do dispositivo|Tipo de dispositivo|
|---------------------------------------|---------------|
|Seu administrador de TI gerencia seu dispositivo móvel|**Windows 10 e Windows Phone 8.1**</br>O dispositivo não aparecerá mais no Portal da Empresa e o Portal da Empresa tentará redefinir o dispositivo para as configurações padrão do fabricante. Os dados, os aplicativos e as configurações pessoais serão removidos. <br /><br />**Windows Mobile 10**: a única maneira de cancelar o registro de seu dispositivo para redefini-lo.|
|Seu dispositivo pode acessar somente o email da empresa|**Windows Phone 8.1**<br />Seu dispositivo não aparecerá mais no Portal da Empresa e sua conta de email da empresa será excluída e emails que não foram salvos serão excluídos.<br /><br />**Computadores com Windows 7 ou Windows Vista**<br />Você não poderá redefinir um computador que esteja executando o Windows 7 ou anterior e seja usado somente para email.<br /><br />**Computadores com Windows 8.1 e Windows 8**<br />Seu dispositivo não aparecerá mais no Portal da Empresa e sua conta de email da empresa será excluída e emails que não foram salvos serão excluídos.|
|PCs e laptops|**Computadores com Windows 8.1 e Windows 8**<br />Você não pode redefinir um computador que esteja executando o Windows 8 ou o Windows 8.1, a menos que ele seja usado somente para email.<br /><br />**Computadores com Windows 7 ou Windows Vista**<br />Não será possível redefinir um computador que esteja executando o Windows 7 ou anterior.|

Se você tiver dúvidas, entre em contato com o administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).





<!--HONumber=Oct16_HO2-->


