---
title: "Problemas conhecidos na Visualização do Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: leia sobre os problemas conhecidos na versão prévia"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 08e2f65bcd600489f6599d37e5ef56c205176cd7
ms.lasthandoff: 04/25/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Problemas conhecidos na versão prévia do Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Use este tópico para saber mais sobre problemas conhecidos na versão prévia do Intune.

Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Se desejar solicitar que um novo recurso seja adicionado ao Intune, considere enviar um relatório em nosso site [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Os grupos criados pelo Intune durante a migração podem afetar a funcionalidade de outros produtos da Microsoft

Ao migrar do Intune clássico para o Portal do Azure, você poderá ver um novo grupo chamado **Todos os Usuários - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Observe que esse grupo contém todos os usuários em seu Azure Active Directory, não apenas os usuários licenciados do Intune. Isso pode causar problemas com outros produtos da Microsoft se você espera que alguns usuários novos ou existentes não sejam membros de quaisquer grupos.

### <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>A alteração de grupos criados pelo Intune durante a migração atrasará a migração

Em preparação para a migração, os grupos são copiados do Intune para o Azure AD. Quaisquer alterações adicionais feitas no portal clássico do Intune serão atualizadas no grupo do Azure AD. No entanto, quaisquer alterações feitas no Azure AD não serão sincronizadas novamente com o console clássico do Intune. Isso pode resultar na falha de sua migração para o Portal do Azure e atrasos na migração.

### <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>As políticas de conformidade do Intune não aparecerão no novo console 

Quaisquer políticas de conformidade criadas no portal clássico do Intune são migradas, mas não são exibidas no Portal do Azure. Isso ocorre devido a alterações de design no portal do Azure. As políticas de conformidade criadas no portal clássico do Intune ainda são impostas, mas você deve poder ler e editá-las no portal clássico.
Além disso, novas políticas de conformidade criadas no Portal do Azure não estarão visíveis no portal clássico.
Para saber mais, veja [O que é a conformidade do dispositivo](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance).




### <a name="administration-and-accounts"></a>Administração e contas

Administradores globais (também conhecidos como administradores de locatários) podem continuar a executar tarefas de administração cotidianas sem uma licença separada do Intune ou EMS (Enterprise Mobility Suite). No entanto, se os administradores globais quiserem usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisarão de uma licença do Intune ou EMS, assim como qualquer outro usuário.

### <a name="apple-enrollment-profile-migration"></a>Migração de perfil de registro da Apple
Nos próximos meses, o Intune permitirá gerenciar suas inscrições do Programa de Registro de Dispositivo Apple e do Apple Configurator por meio do novo Portal do Azure. Se você excluir o token do Programa de Registro de Dispositivo Apple e não carregar um token atualizado, o token original será restaurado no novo Portal do Azure como parte da migração de sua conta do Intune. Para remover esse token e evitar o registro de DEP, basta excluir o token no Portal do Azure. 

