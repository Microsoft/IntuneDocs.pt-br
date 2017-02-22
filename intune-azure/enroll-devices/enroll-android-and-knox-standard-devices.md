---
title: "Registrar dispositivos Android no Intune| Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como registrar dispositivos Android na versão prévia do Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Registrar dispositivos Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Como administrador do Intune, você pode habilitar o gerenciamento de dispositivos Android, incluindo dispositivos Samsung Knox Standard, por meio do Portal da Empresa. Os usuários podem registrar seus dispositivos usando o aplicativo de Portal da Empresa disponível no Google Play.

## <a name="prerequisite"></a>Pré-requisito

Você deve definir a autoridade MDM como **Microsoft Intune** para se preparar para gerenciar dispositivos móveis. Consulte [Definir a autoridade MDM](set-mdm-authority.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel, portanto você pode já ter definido isso. 

## <a name="set-up-android-enrollment"></a>Configurar registro do Android

Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard. 

Para ver a configuração para permitir ou bloquear o registro de dispositivos Android, acesse a folha do Intune no Portal do Azure e escolha **Registro** > **Restrições de Registro**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Android no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


