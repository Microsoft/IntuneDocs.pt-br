---
title: Implantar aplicativos
description: "Este tópico explica conceitos que você precisará compreender antes de iniciar a implantação de aplicativos com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 13c4046ed431dc25bda9a2facc59dbcb6d3e5ab5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="deploy-apps-with-microsoft-intune"></a>Implantar aplicativos com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico explica alguns dos conceitos que você precisa compreender antes de iniciar a implantação de aplicativos com o Microsoft Intune.


## <a name="app-deployment-actions"></a>Ações de implantação de aplicativo
Quando você implanta aplicativos, pode escolher uma das seguintes ações de implantação:

-   **Instalação obrigatória** – O aplicativo está instalado no dispositivo, sem necessidade de intervenção do usuário.

    > [!TIP]
    > Para dispositivos iOS que não estão no modo supervisionado, e para todos os dispositivos Android, o usuário deve aceitar a oferta do aplicativo antes que ele seja instalado.
    >
    >  Se um usuário desinstalar um aplicativo implantado como instalação obrigatória, o Intune reinstalará automaticamente o aplicativo após o próximo ciclo de inventário, que normalmente ocorre a cada sete dias.

-   **Instalação disponível** – O aplicativo é exibido no portal da empresa e os usuários podem instalá-lo sob demanda.

-   **Desinstalar** – O aplicativo é desinstalado do dispositivo.

-   **Não aplicável** – O aplicativo não será exibido no portal da empresa e não está instalado em nenhum dos dispositivos.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>Entender quais ações de implantação estão disponíveis para cada tipo de instalador

|Tipo de instalador|Instalação requerida|Instalação disponível|Desinstalar|Não aplicável|
|------------------|--------------------|---------------------|-------------|------------------|
|Pacote de aplicativos do Windows (implantado em um grupo de usuários)|Sim|Sim|Sim|Sim|
|Pacote do aplicativo do Windows (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
|Pacote de aplicativos para dispositivos móveis (implantado em um grupo de usuários)|Sim|Sim|Sim|Sim|
|Pacote de aplicativos para dispositivos móveis (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
|Windows Installer (implantado em um grupo de usuários)|Não|Sim|Não|Sim|
|Windows Installer (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
|Link externo (implantado em um grupo de usuários)|Não|Sim|Não|Sim|
|Link externo (implantado em um grupo de dispositivos)|Não|Não|Não|Não|
|Aplicativo iOS gerenciado da loja de aplicativos (implantado em um grupo de usuários)|Sim|Sim|Sim|Sim|
|Aplicativo iOS gerenciado da loja de aplicativos (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
> [!TIP]
> Ao implantar aplicativos, se você selecionar usuários e grupos de dispositivos, poderá implantar o aplicativo apenas como uma **Instalação disponível**.

## <a name="deployment-conflicts"></a>Conflitos de implantação
Quando duas implantações com a mesma ação de implantação são recebidas por um dispositivo, as seguintes regras se aplicam:

-   Implantações em um grupo de dispositivos têm precedência sobre as implantações para um grupo de usuários. No entanto, se um aplicativo for implantado em um grupo de usuários com a ação de implantação **disponível** e o mesmo aplicativo também for implantado em um grupo de dispositivos com uma ação de implantação de **não aplicável**, o aplicativo será disponibilizado no portal da empresa para os usuários instalarem.

-   Uma ação de instalação tem precedência sobre uma ação de desinstalação.

-   Se uma instalação obrigatória e uma instalação disponível forem recebidas por um dispositivo, as ações serão combinadas. Em outras palavras, o usuário pode instalar o aplicativo disponível do portal da empresa antes de iniciar a instalação obrigatória.


## <a name="next-steps"></a>Próximas etapas

Saiba como [implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md).
