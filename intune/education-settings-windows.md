---
title: Configurações de educação do Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista com todas as configurações de educação para dispositivos Windows 10. Use essas configurações em um perfil de configuração do dispositivo com um aplicativo Take a Test, escolha como os usuários ou os alunos entram, monitore a tela durante o teste e muito mais no Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 61d8f5f66d424c434edf119ad7fe221c35ee35ae
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66042205"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Configurar o aplicativo Take a Test em dispositivos com Windows 10 usando o Intune

Este artigo mostra todas as configurações do aplicativo Take a Test de educação do Microsoft Intune que podem ser definidas para dispositivos que executam o Windows 10 e posterior. Usando esse aplicativo, os alunos podem entrar em um dispositivo e realizar um teste.

Essas configurações são adicionadas a um perfil de configuração do dispositivo e, em seguida, atribuídas ou implantadas em seus dispositivos usando o Microsoft Intune.

[Aplicativo Take a Test no Intune](education-settings-configure.md) fornece mais informações sobre esse recurso.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Configurações de Take a Test

- **Tipo de conta**: escolha como os usuários entram no teste. Suas opções:
  - Conta do Azure AD
  - Conta de domínio
  - Conta local
- **Nome de usuário da conta**: insira o nome de usuário da conta usada com o aplicativo Take a Test. Você pode inserir contas no seguinte formato:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **URL de avaliação**: forneça a URL do teste o qual você deseja que os usuários realizem. Para saber mais sobre como obter a URL, veja a [documentação do Take a Test](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Monitoramento de tela**: escolha **Permitir** para monitorar a atividade de tela, enquanto os usuários realizam um teste. **Não configurado** impede que você monitore a tela durante o teste.
- **Sugestão de texto**: escolha **Permitir** para que os participantes de teste possam ver sugestões de texto. **Não configurado** bloqueia sugestões de texto enquanto os usuários realizam um teste.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas talvez ainda não esteja fazendo nada. [Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
