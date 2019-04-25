---
title: Criar política de conformidade de dispositivo de MTD com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Crie uma política de conformidade de dispositivo do Intune que usa os níveis de ameaça do parceiro de MTD para determinar se um dispositivo móvel pode acessar recursos da empresa.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fe3561bd664842e79f50f738307ce6a026464565
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513215"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Criar uma política de conformidade de dispositivo de MTD (Defesa contra Ameaças Móveis) com o Intune

> [!NOTE] 
> Essa informação se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

O Intune com MTD ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis. Você pode criar uma regra de política de conformidade do dispositivo Intune que avalia o risco para determinar se o dispositivo está em conformidade ou não. Em seguida, você poderá usar uma [política de acesso condicional](create-conditional-access-intune.md) para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Como parte da configuração de MTD, você criou no console do parceiro de MTD uma política que classifica diversas ameaças como os níveis alto, médio e baixo. Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de conformidade de dispositivo Intune.

Pré-requisitos da política de conformidade do dispositivo com MTD:

-   Configurar a integração do MTD com o Intune

## <a name="to-create-an-mtd-device-compliance-policy"></a>Para criar uma política de conformidade de dispositivo MTD

1.  Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2.  No **Painel do Azure**, escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3.  Escolha **Intune** e o **Painel do Intune** se abrirá.

4. No **Painel do Intune**, escolha **Conformidade do dispositivo** e selecione **Políticas** na seção **Gerenciar**.

5.  Escolha **Criar política**, insira o **Nome** e a **Descrição** da conformidade do dispositivo, selecione a **Plataforma**, escolha **Configurar** na seção **Configurações**.

6.  No painel **política de conformidade**, escolha **Integridade do Dispositivo**.

7.  No painel **Integridade do Dispositivo**, escolha o Nível de Ameaça Móvel na lista suspensa abaixo de **Exigir que o dispositivo esteja no Nível de Ameaças do Dispositivo ou abaixo**.

    a.  **Protegido**: este é o nível mais seguro. O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível.

    b.  **Baixo**: O dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.

    c.  **Médio**: O dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.

    d.  **Alto**: Esse nível é o menos seguro. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis apenas para fins de relatório. É necessário ativar a MTD do aplicativo com esta configuração nos dispositivos.

8.  Clique em **OK** duas vezes e escolha **Criar**.

> [!IMPORTANT]
> Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, a avaliação de conformidade do dispositivo será avaliada e os dispositivos que não compatíveis serão impedidos de acessar os recursos corporativos até que a ameaça seja resolvida no dispositivo.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>Para atribuir uma política de conformidade de dispositivo MTD

Para atribuir uma política de conformidade de dispositivo aos usuários, escolha uma política previamente configurada por você. As políticas existentes podem ser encontradas no painel **Conformidade do dispositivo – políticas**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Essa ação abre o painel para selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.

2. Escolha **Selecionar grupos a serem incluídos** para abrir o painel que exibe os grupos de segurança do Azure AD.  Escolher **Selecionar** implanta a política para os usuários.

    > [!NOTE] 
    > Você aplicou a política para os usuários. Os dispositivos usados pelos usuários que são direcionados pela política são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas

- [Habilitar MTD com o Intune](mtd-connector-enable.md)
