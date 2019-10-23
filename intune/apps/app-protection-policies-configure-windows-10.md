---
title: Configurar as políticas de proteção do aplicativo para Windows 10
titleSuffix: Microsoft Intune
description: Este tópico descreve como configurar políticas de proteção do aplicativo (APP) para dispositivos Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0e1ff8fd39d301bd685e9806c319f49e9189d7f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507407"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Habilite o MAM (gerenciamento de aplicativo móvel) para Windows 10 configurando o provedor de MAM no Microsoft Azure AD. Essa configuração permite definir o estado do registro ao criar uma nova política de WIP (Proteção de Informações do Windows) com o Intune. O estado do registro pode ser MAM ou MDM (gerenciamento de dispositivo móvel).

## <a name="to-configure-the-mam-provider"></a>Para configurar o provedor de MAM

1. Entre no Portal do Azure e escolha **Azure Active Directory.**

2. Escolha **Mobilidade (MDM e MAM)** , no grupo **Gerenciar**.

3. Clique em **Microsoft Intune**.

4. Defina as configurações no grupo **Restaurar as URLs padrão do MAM**, na folha **Configurar**.

   **Escopo de usuário do MAM**  
   Use o registro automático do MAM para gerenciar dados empresariais nos dispositivos Windows dos funcionários. O registro automático do MAM será configurado para cenários Traga seu próprio dispositivo.<ul><li>**Nenhum**<br>Selecione se nenhum usuário puder se registrar no MAM.</li><li>**Alguns**<br>Escolha os grupos do Microsoft Azure AD cujos usuários serão registrados no MAM.</li><li>**Todos**<br>Determine se todos os funcionários podem se registrar no MAM.</li></ul>

   **URL de Termos de uso do MAM**  
   A URL de termos de uso do MAM não é compatível com o Microsoft Intune. Essa caixa de entrada deve ser deixada em branco para que as políticas de proteção sejam aplicadas.

   **URL de Descoberta do MAM**  
   A URL do ponto de extremidade de registro do serviço MAM. O ponto de extremidade de registro é usado para registrar dispositivos de gerenciamento com o serviço MAM.

   **URL de Conformidade do MAM**  
   A URL de conformidade do MAM não é compatível com o Microsoft Intune. Essa caixa de entrada deve ser deixada em branco para que as políticas de proteção sejam aplicadas. 

5. Clique em **Salvar**.

## <a name="next-steps"></a>Próximas etapas

[Criar uma política de proteção de aplicativo WIP](windows-information-protection-policy-create.md)
