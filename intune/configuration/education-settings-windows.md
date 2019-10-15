---
title: Configurações de educação do Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista com todas as configurações de educação para dispositivos Windows 10. Use essas configurações em um perfil de configuração do dispositivo com um aplicativo Take a Test, escolha como os usuários ou os alunos entram, monitore a tela durante o teste e muito mais no Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: kakyker
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 07d3488d509339fc48eb8449b12725b757775eb5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734681"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Configurar o aplicativo Take a Test em dispositivos com Windows 10 usando o Intune

O aplicativo fazer um teste permite que você administre com segurança testes online nos dispositivos Windows 10 de sua sala de aula. Para configurar o aplicativo fazer um teste, você precisará criar um perfil de configuração de dispositivo no Intune e definir as configurações de avaliação segura. Este artigo descreve as configurações que você encontrará para o aplicativo fazer um teste. 

Depois de configurar o perfil, atribua-o e implante-o para seus alunos. 

[Aplicativo Take a Test no Intune](education-settings-configure.md) fornece mais informações sobre esse recurso.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Configurações de Take a Test
Depois de criar um perfil de configuração de dispositivo, vá para **tipo de perfil** e selecione **avaliação segura (educação)** . Você encontrará as seguintes configurações do aplicativo fazer um teste. 


- **Tipo de conta**: escolha como os usuários entram no teste. Suas opções:
  - Conta do Azure AD
  - Conta de domínio
  - Conta local
  - Conta de convidado local: disponível somente em dispositivos que executam o Windows 10, versão 1903 e posterior.    
- **Nome de usuário da conta**: insira o nome de usuário da conta usada com o aplicativo Take a Test. Você pode inserir contas no seguinte formato:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Nome da conta**: para configurar um tipo de conta de convidado local, insira o nome da conta usada com o aplicativo fazer um teste. O nome da conta será exibido como um bloco na tela de entrada. Os alunos clicam no bloco para iniciar o teste.  
- **URL de avaliação**: forneça a URL do teste o qual você deseja que os usuários realizem. Para saber mais sobre como obter a URL, veja a [documentação do Take a Test](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Conexão de impressora**: escolha **exigir** para permitir apenas o acesso ao aplicativo fazer um teste de dispositivos que estão conectados a uma impressora. Essa configuração também torna o botão Imprimir do aplicativo disponível para Test-Takers. **Não configurado** permite que os alunos acessem o aplicativo de dispositivos que não estão conectados a uma impressora.  
- **Monitoramento de tela**: escolha **Permitir** para monitorar a atividade de tela, enquanto os usuários realizam um teste. **Não configurado** impede que você monitore a tela durante o teste.
- **Sugestões de texto**: escolha **Permitir** para que os participantes de teste possam ver sugestões de texto. **Não configurado** bloqueia sugestões de texto enquanto os usuários realizam um teste.

## <a name="next-steps"></a>Próximas etapas

[Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).