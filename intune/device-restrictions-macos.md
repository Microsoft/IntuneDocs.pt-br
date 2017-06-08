---
title: "Configurações de restrição de dispositivo do Intune para macOS"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as configurações do Intune que você pode usar para controlar as configurações do dispositivo e as funcionalidades dos dispositivos macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c120c6af93234e153e4fb845942726a51bee98df
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo macOS no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="password"></a>Senha
-     **Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
    -     **Tipo de senha necessária** – Especifique se a senha usada pode ser apenas Numérica ou se deve ser Alfanumérica (conter letras e números). Essa configuração só tem suporte no Mac OS X versão 10.10.3 e posterior.
    -     **Número de caracteres não alfanuméricos na senha** – Especifique o número de caracteres complexos necessários na senha (**0** a **4**).<br>Um caractere complexo é um símbolo, como **?**.
    -     **Tamanho mínimo da senha** – Insira o tamanho mínimo da senha que um usuário deve configurar (entre **4** e **16** caracteres).
    -     **Senhas simples** – Permita o uso de senhas simples como **0000** ou **1234**.
    -     **Máximo de minutos após o bloqueio de tela antes da senha ser exigida** – Especifique quanto tempo o computador deverá ficar inativo antes da senha ser necessária para desbloqueá-lo.
    -     **Máximo de minutos de inatividade para o bloqueio de tela** – Especifique o período que um computador deve permanecer ocioso antes da tela ser bloqueada.
    -     **Expiração de senha (dias)** – Especifique o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** a **255** dias).
    -     **Impedir a reutilização de senhas anteriores** – Especifique o número de senhas usadas anteriormente que não podem ser reutilizadas (de **1** a **24**).

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a ID do pacote do aplicativo (por exemplo *com.apple.calculator*).


