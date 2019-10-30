---
title: Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Intune
titleSuffix: Microsoft Intune
description: Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15d986bc5017a44571c6194f9c6b53167b671349
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72794414"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Criar uma política de proteção de aplicativo com a Defesa contra Ameaças Móveis com o Intune

> [!NOTE] 
> Este artigo aplica-se a todos os parceiros de MTD (Defesa contra Ameaças Móveis) que dão suporte a políticas de proteção de aplicativo: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

O Intune com MTD ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis. Você pode criar uma política de proteção do aplicativo do Intune que avalia o risco para determinar se o dispositivo tem permissão para acessar dados corporativos ou não. 

## <a name="before-you-begin"></a>Antes de começar

Como parte da configuração de MTD, você criou no console do parceiro de MTD uma política que classifica diversas ameaças como os níveis alto, médio e baixo. Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de proteção de aplicativo do Intune.

Pré-requisitos para a política de proteção de aplicativo com MTD:

- Configurar a integração da MTD com o Intune. Sem essa integração, a política de proteção do aplicativo de MTD não terá nenhum efeito.

## <a name="to-create-an-mtd-app-protection-policy"></a>Para criar uma política de proteção de aplicativo MTD

1. Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2. No **Painel do Azure**, escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** e o **Painel do Intune** se abrirá.

4. No **Painel do Intune**, escolha **Aplicativos cliente** e, em seguida, escolha **Políticas de proteção do aplicativo** na seção **Gerenciar**.

5. Escolha **Criar política**, digite o **Nome**, a **Descrição** e selecione a **Plataforma**. 

6. No painel **Inicialização condicional**, na tabela **Condições do dispositivo**, escolha o Nível de Ameaça Móvel na lista suspensa abaixo de **Nível máximo permitido de ameaça ao dispositivo**.

    a.  **Protegido**: este é o nível mais seguro. O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível.

    b.  **Baixo**: O dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.

    c.  **Médio**: O dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.

    d.  **Alto**: Esse nível é o menos seguro. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis apenas para fins de relatório. É necessário ativar a MTD do aplicativo com esta configuração nos dispositivos.

7. Clique em **Salvar** duas vezes e escolha **Criar**.

## <a name="to-assign-an-mtd-app-protection-policy"></a>Para atribuir uma política de proteção de aplicativo MTD

Para atribuir uma política de conformidade de dispositivo aos usuários, escolha uma política previamente configurada por você. As políticas existentes podem ser encontradas no painel **Conformidade do dispositivo – políticas**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Essa ação abre o painel para selecionar **Grupos de Segurança do Azure Active Directory** e atribuí-los à política.

2. Escolha **Selecionar grupos a serem incluídos** para abrir o painel que exibe os Grupos de Segurança do Azure AD. Escolher **Selecionar** implanta a política para os usuários.

> [!NOTE] 
> Você aplicou a política para os usuários. Os dispositivos usados pelos usuários que são alvo da política são avaliados quanto ao acesso a dados corporativos nos aplicativos de destino por meio da proteção de aplicativo do Intune.

## <a name="next-steps"></a>Próximas etapas  

- Siava mais sobre a [Defesa contra Ameaças Móveis](~/protect/mobile-threat-defense.md) no Microsoft Intune.
