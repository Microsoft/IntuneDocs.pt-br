---
title: "Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis com o Intune"
titlesuffix: Azure portal
description: "Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis no Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 23155cbb84c2d170f1b0216981621e35fd3ac0f1
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Criar uma política de conformidade de dispositivo de MTD (Defesa contra Ameaças Móveis) com o Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

O Intune com MTD ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis. Você pode criar uma regra de política de conformidade do dispositivo Intune que avalia o risco para determinar se o dispositivo está em conformidade ou não. Em seguida, é possível usar uma política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Como parte da configuração de MTD, no console do parceiro de MTD, foi criada uma política que classifica diversas ameaças como os níveis alto, médio e baixo. Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de conformidade de dispositivo Intune.

Pré-requisitos da política de conformidade do dispositivo com MTD:

-   Configurar a integração do MTD com o Intune

## <a name="to-create-a-mtd-device-compliance-policy"></a>Para criar uma política de conformidade de dispositivo MTD

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

    d.  **Alto**: esta é a opção menos segura. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis apenas para fins de relatório. É necessário ativar a MTD do aplicativo com esta configuração nos dispositivos.

8.  Clique em **OK** duas vezes e escolha **Criar**.

> [!IMPORTANT]
> Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade do dispositivo será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar os recursos corporativos até que a ameaça seja resolvida no dispositivo.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>Atribuir uma política de conformidade de dispositivo MTD

Para atribuir uma política de conformidade de dispositivo aos usuários, escolha uma política previamente configurada por você. As políticas existentes podem ser encontradas na folha **Políticas de conformidade de dispositivo**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.

2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.  Escolher **Selecionar** implanta a política para os usuários.

    > [!NOTE] 
    > Você aplicou a política para os usuários. A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.

## <a name="next-steps"></a>Próximas etapas

- [Habilitar MTD com o Intune](mtd-connector-enable.md)