---
title: "O que acontece quando você instala o aplicativo Portal da Empresa e registra o dispositivo Windows no Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: arob98
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: noindex,nofollow
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 25d2708dbc514717affa54cba195e5fef7d602ba


---


# O que acontece quando você instala o aplicativo Portal da Empresa e registra o dispositivo Windows no Intune?

Quando você instala o aplicativo Portal da Empresa e o utiliza para registrar um dispositivo Windows ou Windows Phone, está habilitando seu administrador de TI para gerenciar seu dispositivo para manter os dados corporativos ou de estudante seguros, como descrito abaixo para dispositivos anteriores ao Windows 10. Para obter informações sobre dispositivos Windows 10, consulte [essa página](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## O que acontece com todos os dispositivos Windows após o registro
Quando você registra seu dispositivo Windows ou Windows Phone no Intune, pode:

-   Acessar a rede da empresa, além de seu email e arquivos de trabalho

-   Obter aplicativos da empresa do site do Portal da Empresa (para Windows 7 e Vista, pode obter os aplicativos da empresa apenas do site do Portal da Empresa)

-   Configurar automaticamente sua conta de email corporativo ou de estudante

-   Redefinir seu telefone para configurações de fábrica, caso ele seja perdido ou roubado

Ao registrar seu dispositivo, você permitirá que o seu administrador de TI realize ações como:

-   Redefinir o dispositivo de volta para as configurações padrão de fábrica. Essa ação será útil se o dispositivo for perdido ou roubado.

-   Remover todos os dados relacionados à empresa e aplicativos de negócios que foram instalados. Suas configurações pessoais e de dados não são removidas.

-   O seu administrador de TI pode obter um inventário de todo software instalado no computador, inclusive o software que você instalou pessoalmente.

-   Forçá-lo a ter uma senha ou PIN no dispositivo, o que pode bloquear seu acesso ao dispositivo ou redefinir seu dispositivo para a as configurações padrão do fabricante, o que pode incluir a exclusão de dados se houver muitas tentativas de inserção de senha incorreta.

-   Forçar que todos os dados no dispositivo sejam criptografados, o que ajuda a proteger os dados caso o dispositivo seja perdido ou roubado.

-   Exige que você aceite os termos e condições.

-   O administrador de TI pode aplicar políticas no computador. Por exemplo, talvez você precise definir uma senha ou PIN no computador. Se você inserir a senha incorreta por muitas vezes seguidas, o seu acesso ao computador poderá ser bloqueado ou todos os dados do disco rígido do seu computador poderão ser excluídos.

-   Desabilitar o cartão SD.

## O que acontece com todos os computadores Windows após o registro

-  Um software será instalado no computador para permitir que o administrador de TI gerencie o computador e que você acesse os recursos da empresa, como aplicativos e informações de suporte. O administrador de TI pode atualizar esse software automaticamente.

-  O Intune Endpoint Protection pode ser instalado no computador. Esse é o software que verifica a existência de vírus e malwares.

-  O seu administrador de TI pode obter um inventário de todo software instalado no computador, inclusive o software que você instalou pessoalmente.

-  Pode ser necessário que você aceite os termos e condições.

-  O administrador de TI pode coletar ou excluir os dados do disco rígido do seu computador. O administrador de TI também pode excluir o disco rígido inteiro.

-  O administrador de TI pode instalar aplicativos e atualizações no seu computador.

-  O administrador de TI pode aplicar políticas no computador. Por exemplo, talvez você precise definir uma senha ou PIN no computador. Se você inserir a senha incorreta muitas vezes seguidas, o seu acesso ao computador poderá ser bloqueado ou todos os dados do disco rígido do seu computador poderão ser excluídos.


## O que acontece a cada oito horas após o registro de dispositivo
Aproximadamente a cada oito horas, os dispositivos registrados vão:

-   Fazer download de quaisquer atualizações de aplicativos e políticas disponibilizadas pelo seu administrador de TI.

-   Enviar quaisquer atualizações de inventário de hardware.

-   Enviar quaisquer atualizações de inventário de aplicativos da empresa.

Para acessar as etapas para registrar, consulte [Enroll your Windows device in Intune](enroll-your-device-in-intune-windows.md) (Registrar o dispositivo Windows no Intune). Para saber mais sobre o seu administrador de TI pode ver no seu dispositivo, consulte [What can my IT admin see when I enroll my device in Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) (O que meu administrador de TI pode ver quando registro meu dispositivo no Intune?).

Se você tiver dúvidas, entre em contato com o administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).

### Consulte também
[Usando seu dispositivo Windows com o Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO3-->


