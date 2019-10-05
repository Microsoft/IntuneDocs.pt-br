---
title: Configurações de dispositivo compartilhado do Windows 10 – Microsoft Intune – Azure | Microsoft Docs
description: Adicione e use o Windows 10 para configurar dispositivos que são compartilhados ou usados por vários usuários no Microsoft Intune. Confira uma lista de todas as configurações e o que elas fazem nos dispositivos, incluindo o Microsoft Surface. Controle contas Convidado, gerencie contas e exclua contas inativas, permita ou impeça o salvamento no armazenamento local, defina opções de energia e suspensão, escolha quando as atualizações são instaladas e use dispositivos em ambientes educacionais em um perfil de configuração do dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/01/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67393f83ecd76250e01deef3eee20aa1206b3f99
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734278"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Configurações do Windows 10 e posterior para gerenciar dispositivos compartilhados usando o Intune

Dispositivos Windows 10 e posterior, como o Microsoft Surface, podem ser usados por muitos usuários. Os dispositivos que têm vários usuários são chamados de dispositivos compartilhados e são uma parte das soluções de MDM (gerenciamento de dispositivo móvel).

Usando o Microsoft Intune, os usuários finais podem entrar nesses dispositivos compartilhados com uma conta Convidado. Conforme eles usam o dispositivo, eles só obtém acesso aos recursos que você permite. Como administrador do Intune, você configura o acesso, escolhe quando as contas são excluídas, controla as configurações de gerenciamento de energia, entre outros, para seus dispositivos Windows 10 compartilhados.

Este artigo lista e descreve as configurações usadas em um perfil de configuração do dispositivo Windows 10 (e posterior). Quando o perfil é criado no Intune, você implanta ou atribui o perfil a grupos de dispositivos em sua organização. Você também pode atribuir esse perfil a grupos de dispositivos com tipos de dispositivo e versões de sistema operacional mistas.

Para obter mais informações sobre este recurso no Intune, confira [Controlar o acesso, contas e recursos de energia em um computador compartilhado ou em dispositivos multiusuário](shared-user-device-settings.md). Para obter mais informações sobre o CSP do Windows, confira [CSP do SharedPC](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp).

## <a name="before-your-begin"></a>Antes de começar

[Crie o perfil](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Configurações de dispositivo multiusuário compartilhado

- **Modo de PC compartilhado**: escolha **Habilitar** para ligar o modo de computador compartilhado. Nesse modo, apenas um usuário entra no dispositivo por vez. Nenhum outro usuário poderá entrar enquanto o primeiro usuário não sair. A opção **Não configurado** (padrão) mantém essa configuração não gerenciada pelo Intune e não envia por push nenhuma política para controlar essa configuração em um dispositivo.
- **Conta convidado**: escolha a criação de uma opção de Convidado na tela de entrada. As contas Convidado não exigem credenciais do usuário nem autenticação. Essa configuração cria uma conta local sempre que ela é usada. Suas opções:
  - **Convidado**: cria uma conta Convidado localmente no dispositivo.
  - **Domínio**: cria uma conta Convidado no Azure AD (Active Directory).
  - **Convidado e domínio**: cria uma conta Convidado localmente no dispositivo e no Azure AD (Active Directory).
- **Gerenciamento de conta**: definido para **Habilitar** para excluir automaticamente as contas locais criadas por convidados e as contas do AD e do Azure AD. Quando um usuário se desconecta do dispositivo ou quando a manutenção do sistema é executada, essas contas são excluídas. Quando essa opção estiver habilitada, também defina:
  - **Exclusão da Conta**: escolha quando as contas são excluídas: **no limite de espaço de armazenamento**, **no limite de espaço de armazenamento e no limite inativo** ou **imediatamente depois do logoff**. Insira também:
    - **Iniciar limite de exclusão (%)** : insira um percentual (0 a 100) de espaço em disco. Quando o espaço total de disco/armazenamento fica abaixo do valor inserido, as contas armazenadas em cache são excluídas. Ele exclui continuamente as contas para recuperar o espaço em disco. As contas que estão inativas por mais tempo são excluídas primeiro.
    - **Parar limite de exclusão (%)** : insira um percentual (0 a 100) de espaço em disco. Quando o espaço total de disco/armazenamento atende ao valor inserido, a exclusão é interrompida.

  Defina essa opção como **Desabilitar** para manter as contas locais, do AD e do Azure AD criadas por convidados.

- **Armazenamento Local**: escolha **Habilitado** para impedir que os usuários salvem e exibam arquivos no disco rígido do dispositivo. Escolha **Desabilitado** para permitir que os usuários vejam e salvem arquivos localmente usando o Explorador de Arquivos. A opção **Não configurado** (padrão) mantém essa configuração não gerenciada pelo Intune e não envia por push nenhuma política para controlar essa configuração em um dispositivo.
- **Políticas de Energia**: quando essa opção é definida como **Habilitado**, os usuários não podem desligar a hibernação, não podem substituir todas as ações de suspensão (como o fechamento da tampa) e não podem alterar as configurações de energia. Quando essa opção é definida como **Desabilitado**, os usuários podem hibernar o dispositivo, podem fechar a tampa para suspender o dispositivo e alterar as configurações de energia. A opção **Não configurado** (padrão) mantém essa configuração não gerenciada pelo Intune e não envia por push nenhuma política para controlar essa configuração em um dispositivo.
- **Tempo limite de suspensão (em segundos)** : insira o número de segundos inativos (0 a 100) antes de o dispositivo entrar no modo de suspensão. Se você não definir um tempo, o dispositivo entrará em suspensão após 60 minutos.
- **Entre quando o computador for ativado**: defina essa opção como **Habilitado** para exigir que os usuários entrem com uma senha quando o dispositivo sair do modo de suspensão. Escolha **Desabilitado** para que os usuários não precisem inserir seus nomes de usuário e suas senhas. A opção **Não configurado** (padrão) mantém essa configuração não gerenciada pelo Intune e não envia por push nenhuma política para controlar essa configuração em um dispositivo.
- **Hora de início da manutenção (em minutos após a meia-noite)** : insira a hora em minutos (0-1440) de quando executar tarefas de manutenção automáticas, como o Windows Update. A hora de início padrão é meia-noite ou zero (`0`) minutos. Altere a hora de início inserindo uma hora de início em minutos a partir da meia-noite. Por exemplo, caso deseje que a manutenção seja iniciada às 2h, insira `120`. Caso deseje que a manutenção seja iniciada às 20h, insira `1200`.
- **Políticas de educação**: escolha **Habilitado** para usar as configurações recomendadas para dispositivos usados em escolas, que são mais restritivas. Escolha **Desabilitado** para que as políticas de educação recomendadas e padrão não sejam usadas. A opção **Não configurado** (padrão) mantém essa configuração não gerenciada pelo Intune e não envia por push nenhuma política para controlar essa configuração em um dispositivo.

  Para obter mais informações sobre as ações das políticas de educação, confira [Recomendações de configuração do Windows 10 para clientes de educação](https://docs.microsoft.com/education/windows/configure-windows-for-education).

> [!TIP]
> [Configurar um PC compartilhado ou convidado](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc) (abre outro site de docs) é uma excelente funcionalidade nesse recurso do Windows 10, incluindo conceitos e políticas de grupo que podem ser definidas no modo compartilhado.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
- Confira as configurações do [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
