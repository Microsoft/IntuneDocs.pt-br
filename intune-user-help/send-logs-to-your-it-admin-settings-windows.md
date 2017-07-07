---
title: Enviar logs para o administrador de TI de dispositivos Windows 10 | Microsoft Docs
description: Registrar um dispositivo Windows 10 1511 no Intune
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: be9976f03bf749222ca372040d4d936e6a8fd26b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="send-logs-to-your-it-admin-from-the-settings-app-for-windows-10"></a>Enviar logs para o administrador de TI no aplicativo de Configurações do Windows 10

Se você receber um erro enquanto estiver usando o dispositivo Windows 10 gerenciado por sua empresa, poderá ajudar o administrador de TI a solucionar o problema enviando informações a ele por email. Essas informações são mantidas em seu dispositivo, em um documento especial chamado _log de diagnóstico_.

1.  Abra o aplicativo **Configurações** do Windows acessando o **menu Iniciar** e selecionando o botão **Configurações**. Também é possível pesquisar “configurações” na barra de pesquisa.
2.  Acesse **Contas** > **Acessar conta corporativa ou de estudante**.
3.  Selecione “Exportar arquivos de log de gerenciamento”.

  ![A “tela Acessar conta corporativa ou de estudante”, que apresenta a opção Exportar abaixo do cabeçalho “Configurações relacionadas”.](./media/w10-export-logs.png)

4. Os logs serão salvos em **C:\Users\Public\Public Documents\MDMDiagnostics**. Dois arquivos serão criados: um é o log em si e o outro é um documento especial que permite ao administrador examinar os logs em programas diferentes, como o Microsoft Excel. Anexe ambos os arquivos a um email e envie o email para o administrador. Se você fizer isso mais de uma vez, basta escolher os arquivos do dia em que os logs foram criados. 

Talvez você também precise enviar os [logs do aplicativo do Portal da Empresa](send-logs-to-your-it-admin-cp-windows.md) para fornecer ao administrador de TI mais ajuda ao tentar solucionar os problemas encontrados. 

Ainda precisa de ajuda? Entre em contato com o administrador de TI. Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).
