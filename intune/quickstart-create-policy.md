---
title: 'Início Rápido: adicionar uma política de conformidade do dispositivo para dispositivos Windows 10'
description: Use esse início rápido para criar políticas para ajudar a proteger dados corporativos e gerenciar os dispositivos que os usuários finais usam para acessar os recursos da empresa. Em seguida, atribua as políticas a grupos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73e1e0a27d128d567a924e6f2b343026b11f1a44
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581508"
---
# <a name="quickstart-add-a-device-compliance-policy-for-a-windows-10-device"></a>Início Rápido: adicionar uma política de conformidade do dispositivo para dispositivos Windows 10
Uma política de conformidade de dispositivos do Intune para Windows especifica as regras e configurações que dispositivos Windows precisam cumprir para serem considerados em conformidade. Você pode usar essas políticas com [acesso condicional](https://docs.microsoft.com/intune/conditional-access) para permitir ou bloquear o acesso aos recursos da empresa. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade.

Nesse início rápido, você criará uma política de conformidade do dispositivo para um dispositivo Windows 10 e atribuirá um grupo de dispositivos à política.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
- Para concluir este início rápido, é preciso primeiro [criar um usuário](quickstart-create-user.md) e [criar um grupo](quickstart-create-group.md).


## <a name="sign-in-to-intune"></a>Entrar no Intune
Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo
1. Selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
2. Digite **Conformidade do Windows 10** em **Nome** e **Exemplos de política de conformidade para Windows 10** para **Descrição**.
3. Para **Plataforma**, selecione **Windows 10 e posterior**.
4. Em **Configurações**, selecione **Segurança do Sistema** e, em seguida, defina **Exigir uma senha para desbloquear os dispositivos móveis** como **Exigir**. Depois de concluir a configuração da política, selecione **OK**.
   ![Política de conformidade](/intune/media/quickstart-create-policy/compliance-policy.png)
5. Feche o painel **Política de conformidade do Windows 10**. 
6. No painel **Criar política**, selecione **Criar**. Esta etapa cria a política e lista a política em **Conformidade do dispositivo** > **Políticas**.
7. Selecione a nova política e escolha **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
8. Escolha **Grupos selecionados** para ver os grupos de segurança existentes do Microsoft Azure AD. Selecione **Testadores Contoso** e escolha **Salvar** para implantar a política para usuários no grupo. Se não tiver criado esse grupo em [criar um grupo](quickstart-create-group.md), você poderá usar o grupo de sua escolha. 

## <a name="clean-up-resources"></a>Limpar os recursos
Quando ela não for mais necessária, exclua a política. Para fazer isso, selecione a política **de conformidade do Windows 10** e clique em **Excluir**. 

## <a name="next-steps"></a>Próximas etapas
Neste início rápido, você criou e atribuiu uma política simples de conformidade do dispositivo. Para registrar um dispositivo Windows 10 que receberá a política, continue com o início rápido para configurar o registro automático. 
 
> [!div class="nextstepaction"]
> [Configurar registro automático](quickstart-setup-auto-enrollment.md)