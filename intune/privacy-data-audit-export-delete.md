---
title: Auditar, exportar ou excluir dados pessoais
description: Saiba como auditar, exportar ou excluir dados pessoais.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 96990be0-eb1e-43a4-a0e4-09c7dbdc2bf4
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c6bb00dc966503439b1553b4167e05b2a630b02a
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71080170"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Auditar, exportar ou excluir dados pessoais no Intune

Os administradores do Intune podem usar logs de auditoria para acompanhar as atividades que envolvem dados pessoais. Os administradores também podem exportar e excluir dados pessoais.

[!INCLUDE [GDPR-related guidance](./includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Auditar dados pessoais

Os logs de auditoria fornecem aos administradores de locatários um registro das atividades que geram uma alteração no Microsoft Intune. Os logs de auditoria estão disponíveis para muitas atividades de gerenciamento e, normalmente, criam, atualizam (editam), excluem e atribuem ações. As tarefas remotas que geram eventos de auditoria também podem ser examinadas. Esses logs de auditoria podem conter dados pessoais de usuários cujos dispositivos estão registrados no Intune.  

Para fins de segurança, o Intune pode manter logs de auditoria de ações do usuário e do dispositivo por um período de um ano. Esses logs são excluídos automaticamente após o período de retenção de um ano.

Para examinar os logs de auditoria, confira [Logs de auditoria das atividades do Intune](monitor-audit-logs.md). 

Os administradores não podem excluir os logs de auditoria.

Esses eventos de auditoria são retidos por um ano. Os administradores de locatários podem solicitar os logs de auditoria usando [este formulário de solicitação de suporte](https://privacy.microsoft.com/en-US/privacy-questions?).

## <a name="export-personal-data"></a>Exportar dados pessoais

Os administradores podem exportar dados pessoais do usuário final, incluindo contas, dados de serviço e logs associados para cumprir as solicitações de Direitos de Titulares dos Dados. Cabe a você e sua organização decidir se deve ou não fornecer ao titular dos dados uma cópia dos dados pessoais ou se você tem um motivo comercial legítimo para retê-los. Caso decida fornecê-los, você poderá fornecê-los com uma cópia do documento real, uma versão redigida adequadamente ou uma captura de tela das partes que você considerou apropriado compartilhar.

Para exportar os dados pessoais de um usuário, você pode usar: 
- a folha Dispositivo de MDM do Intune para exportar uma lista de dispositivos. Copie também os dados do dispositivo diretamente.
- o [script Export-IntuneData.ps1](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Excluir os dados pessoais do usuário final

Há três maneiras de remover os dados pessoais do gerenciamento do Intune:
- Excluir o usuário do Azure Active Directory
- Restaurar o dispositivo para as configurações de fábrica
- Autorremoção de usuário

### <a name="delete-a-user-from-intune"></a>Excluir um usuário do Intune

Para excluir os dados pessoais de um usuário final do Intune, um administrador precisa [excluir o usuário do AAD (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user). Quando o usuário é excluído do AAD (exclusão irreversível), o Intune recebe o sinal de exclusão do AAD e, em seguida, inicia automaticamente a limpeza de todos os dados pessoais desse usuário do serviço Intune. As informações do usuário serão excluídas do serviço Intune no prazo de até 30 dias após a ação de remoção.

### <a name="reset-device-to-factory-settings"></a>Restaurar o dispositivo para as configurações de fábrica
A restauração para as configurações de fábrica restaura todas as configurações de dados pessoais e corporativos para as configurações originais de fábrica. Ela é útil para fornecer um dispositivo para o próximo funcionário. Os arquivos de usuário, os aplicativos instalados pelo usuário e as configurações não padrão são removidas, e esses dados são excluídos do serviço Intune no prazo de até 30 dias após a ação de remoção.

### <a name="user-self-removal-from-intune-management"></a>Autorremoção de usuário do gerenciamento do Intune
Os usuários podem remover seus dispositivos pessoais [Android, Apple ou Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android) do gerenciamento do Intune sem a assistência do administrador.   

### <a name="retire"></a>Desativar
A ação **Desativar** remove os dados provisionados pelo Intune, como aplicativos da empresa, dados sobre aplicativos gerenciados pelo Intune, configurações de política e perfis de email que foram provisionados por meio do Intune. Essa ação deixa os dados pessoais do usuário no dispositivo.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Excluir um locatário do Microsoft Intune

Se um cliente de locatário do Intune cancela sua conta do Intune, todos os dados de locatário são excluídos no prazo de até 180 dias depois que o cliente fecha a conta do Intune. Se o locatário do AAD está associado a outras assinaturas empresariais da Microsoft (Azure, Office 365), somente os Dados do Cliente do Intune são excluídos. O recurso de locatário do AAD é mantido para uso por outras assinaturas. Se a conta do Intune for a única assinatura associada ao locatário do AAD, o locatário será excluído e todos os recursos e os Dados do Cliente também serão excluídos.

### <a name="delete-a-user-in-a-hybrid-mobile-device-management-mdm-environment"></a>Excluir um usuário em um ambiente de MDM (gerenciamento de dispositivo móvel) híbrido
Quando você tem um ambiente de MDM híbrido (Intune integrado ao Configuration Manager), você precisa concluir as ações a seguir (em ordem) para excluir um usuário e removê-lo completamente do Active Directory local, do Configuration Manager e do Intune.

1. Exclua o usuário do Active Directory (AD) local. Isso impedirá que o usuário seja sincronizado com o Azure AD e também descoberto pela descoberta do Configuration Manager. 
2. Exclua o usuário do console do Configuration Manager para remover o usuário e os dados associados do Configuration Manager. No console, acesse **Ativo e Conformidade** > **Usuários**, clique com o botão direito do mouse no usuário a ser excluído e clique em **Excluir**.
3. [Exclua o usuário do AAD](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user), o que remove o usuário e os dados associados do Azure Active Directory e do Intune ao mesmo tempo. Quando o usuário é excluído do AAD (exclusão irreversível), o Intune recebe o sinal de exclusão do AAD e, em seguida, inicia automaticamente a limpeza de todos os dados pessoais desse usuário do serviço Intune. As informações do usuário serão excluídas do serviço Intune no prazo de até 30 dias após a ação de remoção.

> [!Important]
>A integração de novos clientes MDM híbridos foi preterida. Para obter mais informações, confira a postagem no blog [Migrar do Gerenciamento de dispositivo móvel híbrido para o Intune no Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150).

## <a name="next-steps"></a>Próximas etapas

Descubra como [auditar, exportar ou excluir](privacy-data-audit-export-delete.md) dados pessoais no Intune.
