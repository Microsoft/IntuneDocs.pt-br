---
title: "Gerenciar o Bloqueio de Ativação do iOS em dispositivos"
description: "O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 7.1 e posterior."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a05c8e6a45c57f5f6f0c90d5fbb48164cde34a1c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>Ajude a proteger dispositivos iOS com bypass de Bloqueio de Ativação para o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 8.0 e posteriores. O Bloqueio de Ativação é habilitado automaticamente quando um usuário abre o aplicativo Buscar meu iPhone em um dispositivo. Depois que ele for habilitado, a ID da Apple e a senha do usuário deverão ser inseridas antes que qualquer pessoa possa: 

-   Desligar o Buscar meu iPhone

-   Apagar o dispositivo

-   Reativar o dispositivo

## <a name="how-activation-lock-affects-you"></a>Como o Bloqueio de Ativação afeta você
Embora o Bloqueio de Ativação ajude a proteger dispositivos iOS e aumente a probabilidade de recuperação de um dispositivo perdido ou roubado, como administrador de TI, essa funcionalidade pode apresentar vários desafios. Por exemplo:

-   Um usuário configura o Bloqueio de Ativação em um dispositivo. O usuário sai da empresa e retorna o dispositivo. Sem a ID da Apple e a senha do usuário, não é possível reativar o dispositivo.

-   Você precisa de um relatório de todos os dispositivos que têm o Bloqueio de Ativação habilitado.

-   Você deseja transferir alguns dispositivos para um outro departamento durante uma atualização do dispositivo na sua organização. Só é possível reatribuir dispositivos que não têm o Bloqueio de Ativação habilitado.

Para ajudar a resolver esses problemas, a Apple introduziu bypass de Bloqueio de Ativação no iOS 7.1. Isso permite remover o Bloqueio de Ativação de dispositivos supervisionados sem a ID Apple e a senha do usuário. Dispositivos supervisionados podem gerar um código de bypass de Bloqueio de Ativação específico do dispositivo, que é armazenado no servidor de ativação da Apple.

> [!TIP]
> O modo supervisionado para dispositivos iOS permite que você use o Apple Configurator para bloquear um dispositivo e limitar a funcionalidade para fins comerciais específicos. O modo supervisionado geralmente é somente para dispositivos corporativos.

Você pode ler mais sobre o Bloqueio de Ativação [aqui](https://support.apple.com/en-us/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Como o Intune ajuda você a gerenciar o Bloqueio de Ativação
O Intune pode solicitar o status do Bloqueio de Ativação de dispositivos supervisionados que executam o iOS 8.0 e posterior. Somente para dispositivos supervisionados, o Intune pode recuperar o código de bypass de Bloqueio de Ativação e emiti-lo diretamente para o dispositivo. Se o dispositivo tiver sido apagado, será possível acessar diretamente o dispositivo usando um nome de usuário em branco e o código como a senha.

**Os benefícios para o negócio são**:

-   O usuário obtém os benefícios de segurança do aplicativo Buscar meu iPhone.

-   É possível permitir que usuários façam seu trabalho e saibam que, quando um dispositivo precisar ser realocado, será possível desativá-lo ou desbloqueá-lo.

## <a name="before-you-start"></a>Antes de começar

Antes de ignorar o bloqueio de ativação em dispositivos, deverá habilitá-lo primeiro. Para fazer isto:

1. Use as informações no tópico [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).
2. Na seção **Registro** da página de configurações, defina os parâmetros de **Permitir Bloqueio de Ativação quando o dispositivo estiver no modo supervisionado** como **Sim**.
3. Salve a política e implante-a nos dispositivos nos quais você deseja gerenciar o bypass do bloqueio de ativação.

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>Como usar o bypass de Bloqueio de Ativação do console do administrador do Intune
> [!IMPORTANT]
> Depois de efetuar bypass do Bloqueio de Ativação em um dispositivo, um novo Bloqueio de Ativação será aplicado automaticamente se o aplicativo Buscar meu iPhone for aberto. Por isso, **é necessário estar em posse física do dispositivo antes de seguir este procedimento**.

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos de Propriedade Corporativa**.

2.  Selecione o dispositivo cujo Bloqueio de Ativação você deseja efetuar bypass. Escolha **Bypass do Bloqueio de Ativação**.

3.  Leia a mensagem de aviso. Escolha **Sim** para continuar.

Você pode examinar o status da solicitação de desbloqueio na página de detalhes do dispositivo.

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>Como ver quais dispositivos estão usando o Bloqueio de Ativação
Você pode ver quais dispositivos estão usando o Bloqueio de Ativação de duas maneiras:

-   Execute **Relatórios de Inventário de Dispositivo Móvel**. Este relatório exibe as colunas **Status do Bloqueio de Ativação** e **Supervisionado** para indicar o estado de dispositivos. Os valores de **Supervisionado** são **Sim** ou **Não**, e os valores do **Status do Bloqueio de Ativação** são:

    -   Habilitado com o código de bypass

    -   Habilitado sem o código de bypass (dispositivo não supervisionado)

    -   Habilitado sem o código de bypass (dispositivo não pode ser alcançado)

    -   Não habilitado

    A caixa **Status do Bloqueio de Ativação** fica em branco para dispositivos que não executam o iOS 8.0 ou posterior.

-   Selecione um dispositivo em uma exibição de grupos para ver o status de Bloqueio de Ativação no painel de detalhes do dispositivo.

    Se selecionar um dispositivo no nó **Todos os Dispositivos Corporativos** e o Bloqueio de Ativação estiver habilitado para o dispositivo, você também poderá ver o código de bypass. Esse código pode ser usado para emitir manualmente um bypass de Bloqueio de Ativação.

    > [!IMPORTANT]
    >O Intune faz o inventário dos dispositivos para o Bloqueio de Ativação a cada sete dias. Por causa disso, os dispositivos podem não ser exibidos imediatamente com seu status de Bloqueio de Ativação no console do Intune.


### <a name="see-also"></a>Consulte também
[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md)
[Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)
