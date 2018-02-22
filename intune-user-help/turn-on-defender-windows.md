---
title: Ligar o Windows Defender | Microsoft Docs
description: Saiba como ligar o Windows Defender para acessar os recursos da empresa.
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope:
- User help
ROBOTS: 
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 09d147b3f952b60bf24f2a1bc8441e5909a93090
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2018
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a>Ligar o Windows Defender para acessar recursos da empresa

Seu trabalho ou escola deseja garantir que os dispositivos que acessam seus recursos estão protegidos. Há algumas maneiras como é possível usar o [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx), proteção interna do Windows para software mal-intencionado.

Há algumas configurações que talvez precisem ser alteradas no Windows Defender para corrigir problemas de acesso. Essas etapas podem exigir que você acesse alguns locais diferentes em seu computador.

## <a name="turn-on-windows-defender"></a>Ligar o Windows Defender

1. Em **Iniciar**, abra **Painel de Controle**.
2. Abra **Ferramentas Administrativas** > **Editar política de grupo**. Isso abrirá o **Editor de Política de Grupo Local** em uma nova janela.
3. Abra **Configuração do Computador** > **Modelos Administrativos** > **Componentes do Windows** > **Windows Defender Antivírus**. A configuração **Desligar o Windows Defender Antivírus** está embaixo das pastas de outras configurações. 
4. Abra **Desligar o Windows Defender Antivírus** e certifique-se que está definido como **Desabilitado** ou **Não configurado**.

## <a name="turn-on-real-time-protection"></a>Ligar Proteção em tempo real

Certifique-se de que a Proteção em tempo real está ativada acessando **Iniciar** e pesquisando **Central de Segurança do Windows Defender**. Selecione **Configurações da proteção contra vírus e ameaças** e confirme que **Proteção em tempo real** e **Proteção entregue na nuvem** estão **Ativadas**. Se essas opções não estão sendo exibidas, faça o seguinte para habilitá-las:

1. Em **Iniciar**, abra **Painel de Controle**.
2. Abra **Ferramentas Administrativas** > **Editar política de grupo**. Isso abrirá o **Editor de Política de Grupo Local** em uma nova janela.
3. Abra **Configuração do Computador** > **Modelos Administrativos** > **Componentes do Windows** > **Central de Segurança do Windows Defender** > **Proteção contra vírus e ameaças**.
4. Abra a configuração **Área de proteção contra vírus e ameaças** e defina-a como **Desabilitada**.

## <a name="update-your-antivirus-definitions"></a>Atualizar suas definições de antivírus

Acesse **Iniciar** e pesquisando **Central de Segurança do Windows Defender** para verificar se suas definições de antivírus estão atualizadas . Selecione **Atualizações de proteção** e **Verificar se há atualizações** para certificar-se de que seu dispositivo tem proteção atual contra vírus. Se essa opção não for exibida, siga as etapas em [Ativar a proteção em tempo real](turn-on-defender-windows.md#turn-on-real-time-protection)

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter suas informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
