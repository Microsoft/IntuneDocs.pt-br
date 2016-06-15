---
# required metadata

title: O que acontece quando você redefine o dispositivo usando o Portal da Empresa? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1ee6e275-d1ec-4da3-bbef-d5da2c61a02a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# O que acontece quando você redefine o dispositivo usando o Portal da Empresa?

Quando você usar o aplicativo Portal da Empresa ou o site Portal da Empresa para redefinir o dispositivo Windows, alguns aplicativos e configurações no dispositivo poderão ser excluídos, inclusive alguns dados pessoais. O que acontece em cada dispositivo depende do tipo de dispositivo que você tem e de como ele é usado, conforme descrito na tabela a seguir. Para obter instruções sobre como redefinir o dispositivo perdido ou roubado, consulte [Reset (erase) your lost or stolen device](reset-erase-your-lost-or-stolen-device-windows.md) (Redefinir (apagar) o dispositivo perdido ou roubado).

|Gerenciamento e configuração do dispositivo|Tipo de dispositivo|
|---------------------------------------|---------------|
|Seu administrador de TI gerencia seu dispositivo móvel|**Windows 10, Windows Phone 8.1 e Windows Phone 8**</br>O dispositivo não aparecerá mais no Portal da Empresa e o Portal da Empresa tentará redefinir o dispositivo para as configurações padrão do fabricante. Os dados, os aplicativos e as configurações pessoais serão removidos.<br /><br />**Windows RT**<br />Você não poderá redefinir um dispositivo Windows RT, a menos que ele seja usado somente para email.|
|Seu dispositivo pode acessar somente o email da empresa|**Windows Phone 8.1 e Windows Phone 8**<br />Seu dispositivo não aparecerá mais no Portal da Empresa e sua conta de email da empresa será excluída e emails que não foram salvos serão excluídos.<br /><br />**Windows RT**<br />Seu dispositivo não aparecerá mais no Portal da Empresa e sua conta de email da empresa será excluída e emails que não foram salvos serão excluídos.<br /><br />**Computadores com Windows 7 ou Windows Vista**<br />Você não poderá redefinir um computador que esteja executando o Windows 7 ou anterior e seja usado somente para email.<br /><br />**Computadores com Windows 8.1 e Windows 8**<br />Seu dispositivo não aparecerá mais no Portal da Empresa e sua conta de email da empresa será excluída e emails que não foram salvos serão excluídos.|
|PCs e laptops|**Computadores com Windows 8.1 e Windows 8**<br />Você não pode redefinir um computador que esteja executando o Windows 8 ou o Windows 8.1, a menos que ele seja usado somente para email.<br /><br />**Computadores com Windows 7 ou Windows Vista**<br />Não será possível redefinir um computador que esteja executando o Windows 7 ou anterior.|

Se você tiver dúvidas e não for possível encontrar informações de contato do administrador de TI, veja se ele está listado no [site do Portal da Empresa](http://portal.manage.microsoft.com).

### Consulte também
[Usando seu dispositivo Windows com o Intune](using-your-windows-device-with-intune.md)

<!--HONumber=Jun16_HO1-->


