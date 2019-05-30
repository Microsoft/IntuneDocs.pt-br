---
title: Configurações de dispositivo multiusuário ou compartilhado no Microsoft Intune – Azure | Microsoft Docs
description: Adicione e use dispositivos Windows 10 e Windows Holographic for Business que são compartilhados ou usados por vários usuários no Microsoft Intune. Veja uma lista de todas as configurações e o que elas fazem nos dispositivos, incluindo o Microsoft HoloLens. Controle contas Convidado, gerencie contas e exclua contas inativas, permita ou impeça o salvamento no armazenamento local, defina opções de energia e suspensão, escolha quando as atualizações são instaladas e use dispositivos em ambientes educacionais em um perfil de configuração do dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0a5064a9065dba75f3594f2e6bb6fb36b42be2e2
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044971"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Controlar o acesso, contas e recursos de energia em um computador compartilhado ou em dispositivos multiusuário usando o Intune

Os dispositivos que têm vários usuários são chamados de dispositivos compartilhados e são uma parte comum das soluções de MDM (gerenciamento de dispositivo móvel). Usando o Microsoft Intune, você pode personalizar dispositivos compartilhados que executam as seguintes plataformas:

- Windows 10 Professional e mais recente
- Windows 10 Enterprise e mais recente
- Windows Holographic for Business, como o HoloLens

Por exemplo, as escolas têm dispositivos que normalmente são usados por muitos alunos. Com essa configuração, o administrador do Intune na escola pode ativar o recurso Computador Compartilhado para permitir um usuário por vez. Os alunos não podem alternar entre diferentes contas conectadas no dispositivo. Quando o aluno sai do serviço, você também opta por remover todas as configurações específicas do usuário.

Os usuários finais podem entrar nesses dispositivos compartilhados com uma conta Convidado. Depois que os usuários entrarem, as credenciais serão armazenadas em cache. Conforme eles usam o dispositivo, os usuários finais só obtém acesso aos recursos que você permite. Por exemplo, você escolhe quando o dispositivo entra no modo de suspensão, se os usuários podem ver e salvar arquivos localmente, habilita ou desabilita as configurações de gerenciamento de energia, entre outros. Você também controla se a conta Convidado é excluída quando o usuário se desconecta ou exclui contas inativas quando um limite é atingido.

Este artigo mostra como criar um perfil de configuração e inclui links para as configurações disponíveis com suas descrições.

Quando o perfil é criado no Intune, você implanta ou atribui o perfil a grupos de dispositivos em sua organização. Você também pode atribuir esse perfil a grupos de dispositivos com tipos de dispositivo e versões de sistema operacional mistas.

## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Insira as seguintes propriedades:

   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: Selecione **Windows 10 e posterior**.
   - **Tipo de perfil**: Selecione **Dispositivo multiusuário compartilhado**.

4. Defina as configurações para o [Windows 10 e posterior](shared-user-device-settings-windows.md) ou o [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).

5. Selecione **OK** > **Criar** para salvar suas alterações.

Seu perfil foi criado e é mostrado na lista, mas não está fazendo nada ainda. Lembre-se de [atribuir o perfil](device-profile-assign.md) a grupos de dispositivos em sua organização.

## <a name="next-steps"></a>Próximas etapas

- Confira todas as configurações do [Windows 10 e mais recente](shared-user-device-settings-windows.md) e do [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- [Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
