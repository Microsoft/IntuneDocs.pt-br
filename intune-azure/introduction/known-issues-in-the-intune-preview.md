---
title: "Problemas conhecidos na Visualização do Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: leia sobre os problemas conhecidos na versão prévia"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Problemas conhecidos na versão prévia do Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Use este tópico para saber mais sobre problemas conhecidos na versão prévia do Intune.

Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Se desejar solicitar que um novo recurso seja adicionado ao Intune, considere enviar um relatório em nosso site [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="administration-and-accounts"></a>Administração e contas

- Administradores globais (também conhecidos como administradores de locatários) podem continuar a executar tarefas de administração cotidianas sem uma licença separada do Intune ou EMS (Enterprise Mobility Suite). No entanto, se os administradores globais quiserem usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisarão de uma licença do Intune ou EMS, assim como qualquer outro usuário.

## <a name="apple-enrollment-profile-migration"></a>Migração de perfil de registro da Apple
- Nos próximos meses, o Intune permitirá gerenciar suas inscrições do Programa de Registro de Dispositivo Apple e do Apple Configurator por meio do novo Portal do Azure. Se você excluir o token do Programa de Registro de Dispositivo Apple e não carregar um token atualizado, o token original será restaurado no novo Portal do Azure como parte da migração de sua conta do Intune. Para remover esse token e evitar o registro de DEP, basta excluir o token no Portal do Azure. 

