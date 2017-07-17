---
title: "Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis com o Intune"
titleSuffix: Intune on Azure
description: "Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis no Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1354d3170f007af2a4bf7f5b2f233a186175c621
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Criar uma política de conformidade de dispositivo de MTD (Defesa contra Ameaças Móveis) com o Intune
<a id="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune" class="xliff"></a>

O Intune com MTD ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis. Você pode criar uma regra de política de conformidade do dispositivo Intune que avalia o risco para determinar se o dispositivo está em conformidade ou não. Em seguida, é possível usar uma política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

## Antes de começar
<a id="before-you-begin" class="xliff"></a>

Como parte da configuração de MTD, no console do parceiro de MTD, foi criada uma política que classifica diversas ameaças como os níveis alto, médio e baixo. Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de conformidade de dispositivo Intune.

Pré-requisitos da política de conformidade do dispositivo com MTD:

-   Configurar a integração do MTD com o Intune

-   Habilitar o conector do MTD no Intune

## Para criar uma política de conformidade de dispositivo MTD
<a id="to-create-a-mtd-device-compliance-policy" class="xliff"></a>

1.  Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2.  No **Painel do Azure**, escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3.  Escolha **Intune** e o **Painel do Intune** se abrirá.

4. No **Painel do Intune**, escolha **Conformidade do dispositivo** e selecione **Políticas** na seção **Gerenciar**.

5.  Escolha **Criar política**, insira o **Nome** e a **Descrição** da conformidade do dispositivo, selecione a **Plataforma**, escolha **Configurar** na seção **Configurações**.

6.  Na folha **política de conformidade**, escolha **Integridade do Dispositivo**.

7.  Na folha **Integridade do Dispositivo**, escolha o Nível de Ameaça Móvel na lista suspensa abaixo de **Exigir que o dispositivo esteja no Nível de Defesa contra Ameaças Móveis ou abaixo dele**.

    a.  **Seguro**: este é o mais seguro. O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como fora de conformidade.

    b.  **Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.

    c.  **Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.

    d.  **Alto**: esta é a opção menos segura. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis do Skycure apenas para fins de relatório.

8.  Clique em **OK** duas vezes e escolha **Criar**.

> [!IMPORTANT]
> Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade do dispositivo será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar os recursos corporativos até que a ameaça seja resolvida no dispositivo.

## Atribuir uma política de conformidade de dispositivo MTD
<a id="to-assign-a-mtd-device-compliance-policy" class="xliff"></a>

Para atribuir uma política de conformidade de dispositivo aos usuários, escolha uma política previamente configurada por você. As políticas existentes podem ser encontradas na folha **Políticas de conformidade de dispositivo**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.

2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.  Escolher **Selecionar** implanta a política para os usuários.

    > [!NOTE] 
    > Você aplicou a política para os usuários. A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.