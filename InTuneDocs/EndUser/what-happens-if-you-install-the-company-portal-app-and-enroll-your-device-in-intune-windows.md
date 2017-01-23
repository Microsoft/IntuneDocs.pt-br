---
title: "O que acontece quando você instala o aplicativo Portal da Empresa e registra o dispositivo Windows no Intune? | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: ae372c141ffd98d280715c454057284c4bd3d6e9


---


# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-windows-device-in-intune"></a>O que acontece quando você instala o aplicativo Portal da Empresa e registra o dispositivo Windows no Intune?

Quando você instala o aplicativo Portal da Empresa e o utiliza para registrar um dispositivo Windows ou Windows Phone, está permitindo que o seu administrador de TI gerencie seu dispositivo para ajudar manter os dados corporativos ou de estudante seguros. Este tópico descreve o que acontece para dispositivos anteriores ao Windows 10. Para dispositivos Windows 10, consulte o [tópico relacionado](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## <a name="what-happens-to-all-windows-devices-after-enrollment"></a>O que acontece com todos os dispositivos Windows após o registro
Registre seu dispositivo Windows ou Windows Phone no Intune permite que você:

-   acessar a rede da empresa, bem como seu email e arquivos de trabalho.

-   Obter aplicativos da empresa do site do Portal da Empresa. (Para Windows 7 e Windows Vista, você pode obter aplicativos da empresa somente do site do Portal da Empresa).

-   Configurar automaticamente sua conta de email corporativo ou de estudante.

-   Redefinir seu telefone para as configurações de fábrica, caso ele seja perdido ou roubado.

Ao registrar seu dispositivo, você permitirá que o seu administrador de TI realize ações como:

-   Redefinir o dispositivo de volta para as configurações padrão de fábrica. Essa ação será útil se o dispositivo for perdido ou roubado.

-   Remova somente os arquivos relacionados à empresa e aplicativos de negócios. *Suas configurações e dados pessoais não são removidos.*

-   O seu administrador de TI ver o software instalado no dispositivo, inclusive o software que você instalou pessoalmente.

-   Definir requisitos do dispositivo, como exigir que você tenha uma senha de dispositivo ou PIN para ajudar a proteger dados da empresa. O administrador de TI também pode limitar quantas vezes você pode inserir uma senha incorreta e pode travá-lo no dispositivo se você tentar muitas vezes.

-   Exige a criptografia os dados no dispositivo para ajudar a proteger os dados da empresa, caso o dispositivo seja perdido ou roubado.

-   Exige que você aceite os termos e condições.

-   Impede que você tire fotos de dados relacionados à empresa.

## <a name="what-happens-to-all-windows-pcs-after-enrollment"></a>O que acontece com todos os computadores Windows após o registro

-  Um software será instalado no computador para permitir que o administrador de TI gerencie o computador e que você acesse os recursos da empresa, como aplicativos e informações de suporte. O administrador de TI pode atualizar esse software automaticamente.

-  O Intune Endpoint Protection pode ser instalado no computador. Este software verifica a existência de vírus e malwares.

-  O administrador de TI pode coletar ou excluir os dados do disco rígido do seu computador.

-  O administrador de TI pode instalar aplicativos e atualizações no seu computador.

## <a name="what-happens-every-eight-hours-after-device-enrollment"></a>O que acontece a cada oito horas após o registro de dispositivo
Aproximadamente a cada oito horas, os dispositivos registrados vão:

-   Baixar atualizações de aplicativos e políticas disponibilizadas pelo seu administrador de TI.

-   Enviar quaisquer atualizações de inventário de hardware.

-   Enviar quaisquer atualizações de inventário de aplicativos da empresa.

Se tiver dúvidas, entre em contato com o administrador de TI. Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO2-->


