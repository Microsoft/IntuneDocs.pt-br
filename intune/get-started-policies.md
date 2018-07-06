---
title: Introdução às políticas no Microsoft Intune – Azure | Microsoft Docs
description: Crie políticas para ajudar a proteger dados corporativos e gerenciar os dispositivos que os usuários finais usam para acessar os recursos da empresa. Em seguida, atribua as políticas a grupos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271517"
---
# <a name="get-started-with-creating-policies"></a>Introdução à criação de políticas

As políticas do Intune são uma ótima maneira de registrar dispositivos e garantir que eles estão em conformidade com as políticas corporativas. As políticas de conformidade ajudam a gerenciar tipos de dispositivos especializados, como quiosques corporativos e dispositivos pessoais (Traga seu próprio), tablets e dispositivos sem usuário.

![Painel de conformidade com poucos dados](/intune/media/generic-compliance-dashboard.png)

Os dispositivos móveis podem ser gerenciados com políticas de conformidade, incluindo:

* Controlar o número de dispositivos que um usuário registra no Intune
* Gerenciar as configurações do dispositivo, como criptografia no nível do dispositivo, tamanho da senha e uso da câmera
* Entregar aplicativos, perfis de email, perfis de VPN e muito mais
* Avaliar critérios no nível do dispositivo para as políticas de conformidade de segurança

As políticas de conformidade são criadas para cada plataforma, como iOS, Android, Windows e muito mais. Para este exercício, use o iOS. As seguintes políticas estão disponíveis para dispositivos iOS:

* Configuração de senha ou PIN
* Criptografia de dispositivo
* Dispositivo com jailbreak
* Perfil de email
* Versão mínima do SO
* Versão máxima do SO

## <a name="create-a-policy"></a>Criar uma política

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
4. Insira um **Nome** e uma **Descrição** de política. 
5. Para a **Plataforma**, selecione **iOS**.
6. Em **Configurações**, selecione **Segurança do Sistema** e, em seguida, defina **Exigir uma senha para desbloquear os dispositivos móveis** como **Exigir**. 

    Defina também outras regras, como: 
    - **Comprimento mínimo da senha**
    - **Tipo de senha necessária**
    - **Número de caracteres não alfanuméricos na senha**
    
    Depois de concluir a configuração da política, selecione **OK**.
  
7. Volte para **Criar política** e selecione **Criar**. Esta etapa cria a política e lista a política em **Conformidade do dispositivo** > **Políticas**.
8. Selecione a nova política e escolha **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
Escolha Grupos selecionados para ver os grupos de segurança existentes do Azure AD. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolher **Salvar** para implantar a política para os usuários.

Para estar em conformidade com a nova política corporativa, após alguns minutos, seu dispositivo registrado solicitará uma senha atualizada. Verifique manualmente a atualização no **aplicativo do Portal da Empresa para iOS**. Abra o aplicativo do Portal da Empresa, selecione o nome do dispositivo e, em seguida, selecione **Sincronizar**.

> [!NOTE]
> As novas políticas aplicadas a um grupo de dispositivos dinâmicos podem levar até oito horas para serem aplicadas a todos os dispositivos do grupo.

## <a name="next-steps"></a>Próximas etapas

[Introdução ao registro de dispositivos](get-started-enroll.md) – aprenda a experiência de registro passando por uma experiência completa de registro de um dispositivo iOS.

## <a name="learn-more"></a>Saiba mais

* [Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)
* [Maneiras comuns de usar as políticas de acesso condicional com o Intune](conditional-access-intune-common-ways-use.md)
