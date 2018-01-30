---
title: "Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10"
titlesuffix: Azure portal
description: "Provedor de instalação do gerenciamento de aplicativos móveis (MAM) no Azure AD"
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3254adc66c5fd5dc991364c3a33aabef8ac2030b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Habilite o MAM (gerenciamento de aplicativo móvel) para Windows 10 configurando o provedor de MAM no Microsoft Azure AD. Essa configuração permite definir o estado do registro ao criar uma nova política de WIP (Proteção de Informações do Windows) com o Intune. O estado do registro pode ser MAM ou MDM (gerenciamento de dispositivo móvel).

> [!NOTE]
> Dispositivos com um estado de registro de MAM precisam ser ingressados no Azure AD.

## <a name="to-configure-the-mam-provider"></a>Para configurar o provedor de MAM

1. Entre no Portal do Azure e escolha **Azure Active Directory.**

2. Escolha **Mobilidade (MDM e MAM)**, no grupo **Gerenciar**.

3. Clique em **Microsoft Intune**.

4. Defina as configurações no grupo **Restaurar as URLs padrão do MAM**, na folha **Configurar**.

    **Escopo de usuário do MAM**  
      Use o registro automático do MAM para gerenciar dados empresariais nos dispositivos Windows dos funcionários. O registro automático do MAM será configurado para cenários Traga seu próprio dispositivo.<ul><li>**Nenhum**<br>Determine se todos os funcionários podem se registrar no MAM.</li><li>**Alguns**<br>Escolha os grupos do Microsoft Azure AD cujos usuários serão registrados no MAM.</li><li>**Todos**<br>Determine se todos os funcionários podem se registrar no MAM.</li></ul>

    **URL de Termos de uso do MAM**  
     A URL do ponto de extremidade dos termos de uso do serviço MAM. O ponto de extremidade dos termos de uso é usado para exibir os termos de serviço para usuários finais antes de registrar os dispositivos deles para gerenciamento. O texto dos termos de uso informa os usuários sobre as políticas que serão impostas no dispositivo móvel.

    **URL de Descoberta do MAM**  
    A URL do ponto de extremidade de registro do serviço MAM. O ponto de extremidade de registro é usado para registrar dispositivos de gerenciamento com o serviço MAM.

    **URL de Conformidade do MAM**  
      A URL do ponto de extremidade compatível do serviço MAM. Quando um usuário tiver acesso negado a um recurso de um dispositivo não compatível, será exibido um link para a URL de conformidade. Os usuários podem navegar nesta URL hospedada pelo serviço MAM para entender por que o dispositivo é considerado incompatível. Os usuários também podem iniciar a correção de autoatendimento para que os dispositivos deles se tornem compatíveis e possam continuar a acessar recursos.

5.  Clique em **Salvar**.

## <a name="next-steps"></a>Próximas etapas

[Criar uma política de proteção de aplicativo WIP](windows-information-protection-policy-create.md)
