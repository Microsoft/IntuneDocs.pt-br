---
title: Enviar logs para o suporte de sua empresa de dispositivos Windows 10 | Microsoft Docs
description: Registrar um dispositivo Windows 10 1511 no Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e88fa55391ace4f8a86416412489ca055083503
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502040"
---
# <a name="send-logs-to-your-company-support-from-the-settings-app-for-windows-10"></a>Enviar logs para o suporte de sua empresa no aplicativo de Configurações para Windows 10

Use o aplicativo Configurações para solucionar problemas do Portal da Empresa para Windows 10. Caso tenha problemas ao usar o aplicativo no dispositivo Windows 10, envie um email à equipe de suporte para obter ajuda. Os eventos e erros que ocorrem no aplicativo Portal da Empresa são salvos em seu dispositivo em um documento especial chamado de _log de diagnóstico_. Eles podem conter insights adicionais sobre o erro e, quando exportados, são úteis para as equipes de suporte.

1. Para abrir o aplicativo **Configurações**, acesse o menu **Iniciar** > **Configurações**. Pesquise também *configurações* na barra de pesquisa.
2. Acesse **Contas** > **Acessar conta corporativa ou de estudante**.
3. Selecione **Exportar arquivos de log de gerenciamento**.

   ![A “tela Acessar conta corporativa ou de estudante”, que apresenta a opção Exportar abaixo do cabeçalho “Configurações relacionadas”.](./media/w10-export-logs.png)

4. Os logs serão salvos em **C:\Users\Public\Public Documents\MDMDiagnostics**. Dois arquivos serão criados: um é o log em si e o outro é um documento especial que permite ao administrador examinar os logs em programas diferentes, como o Microsoft Excel. Anexe ambos os arquivos a um email e envie o email para o administrador. Se você fizer isso mais de uma vez, basta escolher os arquivos do dia em que os logs foram criados. 

Talvez você também precise enviar os [logs do aplicativo do Portal da Empresa](send-logs-to-your-it-admin-cp-windows.md) para fornecer ao suporte de sua empresa mais ajuda ao tentar solucionar os problemas que eles podem encontrar. 

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
