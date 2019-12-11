---
title: Remova o dispositivo do gerenciamento se você tiver recusado os termos de uso | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 169007541bccfc3e26184ac71197265931afbfdd
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508112"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Remova seu dispositivo do gerenciamento se você tiver recusado os "Termos de uso"

Se você tiver recusado os Termos de Uso ao tentar entrar no aplicativo Portal da Empresa, você será impedido de entrar no aplicativo Portal da Empresa em tentativas futuras. Portanto, precisará usar estas instruções de "solução alternativa" para remover seu dispositivo do Intune.

Ao desinstalar o aplicativo de Portal da Empresa, você também remove o dispositivo do Intune. O dispositivo não poderá mais acessar recursos da empresa. Para obter mais informações sobre o que acontece quando você remove um dispositivo do gerenciamento, veja [O que acontece quando você cancela o registro do dispositivo no Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Antes de desinstalar o aplicativo Portal da Empresa, você precisa acessar a configuração **Administradores do Dispositivo** e desligar **Portal da Empresa**. As etapas podem diferir um pouco, dependendo de qual dispositivo Android você tem.

## <a name="removing-the-device-from-the-company-portal-app"></a>Removendo o dispositivo do aplicativo Portal da Empresa

Para remover seu dispositivo do Intune e desinstalar o aplicativo do Portal da Empresa:

1. Vá para **Configurações** &gt; **Segurança &amp; Bloqueio de Tela** &gt; **Administradores do dispositivo**.

    A conclusão desta etapa cancela imediatamente o registro de seu dispositivo.

2. Desmarque a caixa de seleção ao lado ou desligue o **Portal da Empresa**.

    Agora você pode desinstalar o aplicativo Portal da Empresa.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Removendo os dados coletados pelo aplicativo Portal da Empresa

Para remover todos os dados que o aplicativo Portal da Empresa para Android armazena no seu dispositivo:

- Limpe os dados do aplicativo em Aplicativos -> Clique no aplicativo -> botão "Limpar dados"
- Exclua a pasta '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal'


Ainda precisa de ajuda? Entre em contato com o suporte de sua empresa (consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obter as informações de contato) ou escreva para a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">equipe de Android da Microsoft</a>.
