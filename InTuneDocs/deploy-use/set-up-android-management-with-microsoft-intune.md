---
title: Configurar o gerenciamento do Android | Microsoft Docs
description: "Habilitar o MDM (gerenciamento de dispositivo móvel) para dispositivos Android e KNOX Standard com o Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 4042a22ecfbab7970ea4b3dab8ee6a82b0da5f78
ms.lasthandoff: 04/24/2017


---

# <a name="set-up-android-device-management"></a>Configurar o gerenciamento de dispositivo Android

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Como administrador do Intune, você pode habilitar o gerenciamento de dispositivos Android, incluindo dispositivos Samsung Knox Standard, por meio do Portal da Empresa. Os usuários podem registrar seus dispositivos usando o aplicativo de Portal da Empresa disponível no Google Play.

Por padrão, os dispositivos Android têm permissão para se registrarem no Intune. Para bloquear o registro de dispositivos Android, entre no [Portal de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador. Escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Regras de Registro** e desmarque a caixa de seleção **Permitir Dispositivos Android**.

1.  **Configurar Intune**<br>
    Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](prerequisites-for-enrollment.md#step-2-set-mdm-authority) como **Microsoft Intune** e configure o MDM.

2.  **Registro do Android habilitado**<br>
    Nenhuma configuração adicional no console do Intune é necessária para habilitar o registro de dispositivo móvel Android.

3.  **Informe aos usuários como registrar seus dispositivos para obter acesso aos recursos da empresa.**

    Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android). O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.

    Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:
  - [Recursos sobre a experiência do usuário final com o Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Diretrizes do usuário final para dispositivos com Android](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Devido à ausência da Google Play Store na China, os dispositivos Android devem obter o Portal da Empresa nos marketplaces de aplicativos chineses. O aplicativo do Portal da Empresa para Android estará disponível para download nas seguintes lojas:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

O aplicativo de Portal da Empresa para Android usa o Google Play Services para se comunicar com o serviço Microsoft Intune. Como o Google Play Services ainda não está disponível na China, a execução de qualquer uma das seguintes tarefas pode levar até 8 horas para ser concluída. 

|Console de Administração do Intune| Aplicativo do Portal da Empresa do Intune para Android |Site do Portal da Empresa do Intune|   
|---|---|---|
|Apagamento completo| Remover um dispositivo remoto| Remover dispositivo (local e remoto)|
|Apagamento seletivo| Redefinir dispositivo| Redefinir o dispositivo|
|Implantações de aplicativo novo ou atualizado| Instalar aplicativos de linha de negócios disponíveis| Redefinição de senha de dispositivo|
|Bloqueio remoto|||
|Redefinição de senha|||

### <a name="see-also"></a>Consulte também
[Pré-requisitos para registrar dispositivos no Microsoft Intune](prerequisites-for-enrollment.md)

