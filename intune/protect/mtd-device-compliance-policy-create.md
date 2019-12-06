---
title: Criar política de conformidade de dispositivo de MTD com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Crie uma política de conformidade de dispositivo do Intune que usa os níveis de ameaça do parceiro de MTD para determinar se um dispositivo móvel pode acessar recursos da empresa.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 504c77fb56918cf97312e70f50b38356f9f7efef
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409690"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Criar uma política de conformidade de dispositivo de MTD (Defesa contra Ameaças Móveis) com o Intune

O Intune com MTD ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis. Você pode criar uma regra de política de conformidade do dispositivo Intune que avalia o risco para determinar se o dispositivo está em conformidade ou não. Em seguida, você poderá usar uma [política de acesso condicional](create-conditional-access-intune.md) para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

> [!NOTE]
> Essa informação se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

## <a name="before-you-begin"></a>Antes de começar

Como parte da configuração de MTD, você criou no console do parceiro de MTD uma política que classifica diversas ameaças como os níveis alto, médio e baixo. Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de conformidade de dispositivo Intune.

Pré-requisitos da política de conformidade do dispositivo com MTD:

- Configurar a integração do MTD com o Intune

## <a name="to-create-an-mtd-device-compliance-policy"></a>Para criar uma política de conformidade de dispositivo MTD

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivo** > **Políticas de conformidade** > **Criar política**.

3. Especifique um **Nome** e uma **Descrição** para a política de conformidade de dispositivo, selecione a **Plataforma** e depois selecione **Configurar** na seção **Configurações**.

4. No painel **política de conformidade**, escolha **Integridade do Dispositivo**.

5. No painel **Integridade do Dispositivo**, escolha o Nível de Ameaça Móvel na lista suspensa para **Exigir que o dispositivo esteja no ou abaixo do Nível de Ameaça do Dispositivo**.

   - **Protegido**: este é o nível mais seguro. O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível.

   - **Baixo**: O dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.

   - **Médio**: O dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.

   - **Alto**: Esse nível é o menos seguro. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis apenas para fins de relatório. É necessário ativar a MTD do aplicativo com esta configuração nos dispositivos.

6. Selecione **OK** duas vezes e, em seguida, selecione **Criar** para criar a política.

> [!IMPORTANT]
> Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, a avaliação de conformidade do dispositivo será avaliada e os dispositivos não compatíveis serão impedidos de acessar os recursos corporativos até que a ameaça seja resolvida no dispositivo.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>Para atribuir uma política de conformidade de dispositivo MTD

Para atribuir uma política de conformidade de dispositivo aos usuários:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivo** > **Políticas de conformidade**.

3. Selecione a política que você deseja atribuir aos usuários e selecione **Atribuições**. Use as opções disponíveis para *Incluir* e *Excluir* grupos para receber essa política.  

4. Selecione Salvar para concluir a atribuição. Quando você salva a atribuição, a política é implantada nos usuários selecionados, e seus dispositivos são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas

[Habilitar MTD com o Intune](mtd-connector-enable.md)
