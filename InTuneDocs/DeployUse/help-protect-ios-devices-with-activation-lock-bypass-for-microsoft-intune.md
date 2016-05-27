---
# required metadata

title: Ajudar a proteger dispositivos iOS com bypass de Bloqueio de Ativação para o Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ajude a proteger dispositivos iOS com bypass de Bloqueio de Ativação para o Microsoft Intune
O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 7.1 e posterior. O Bloqueio de Ativação é habilitado automaticamente quando o aplicativo Buscar meu iPhone for usado em um dispositivo. Depois que ele for habilitado, a ID da Apple e a senha do usuário deverão ser inseridas antes que qualquer pessoa possa:

-   Desligar o Buscar meu iPhone

-   Apagar o dispositivo

-   Reativar o dispositivo

## Como o Bloqueio de Ativação afeta você
Embora o Bloqueio de Ativação ajude a proteger dispositivos iOS e aumente a probabilidade de recuperação caso eles sejam perdidos e roubados, como administrador de TI, essa funcionalidade pode apresentar vários desafios. Por exemplo:

-   Um dos seus usuários configura o Bloqueio de Ativação em um dispositivo. O usuário sai da empresa e retorna o dispositivo. Sem a ID da Apple e a senha do usuário, não é possível reativar o dispositivo.

-   Você precisa de um relatório de todos os dispositivos que têm o Bloqueio de Ativação habilitado.

-   Durante uma atualização do dispositivo na sua organização, você deseja transferir alguns dispositivos para um outro departamento. Só é possível reatribuir dispositivos que não têm o Bloqueio de Ativação habilitado.

Para ajudar a resolver esses problemas, a Apple introduziu bypass de Bloqueio de Ativação no iOS 7.1. Isso permite remover o Bloqueio de Ativação de dispositivos supervisionados sem a ID Apple e a senha do usuário. Dispositivos supervisionados podem gerar um código de bypass de Bloqueio de Ativação específico do dispositivo, que é armazenado no servidor de ativação da Apple.

> [!TIP]
> O modo supervisionado para dispositivos iOS permite que você use a ferramenta Apple Configurator para bloquear um dispositivo para limitar a funcionalidade para fins comerciais específicos. O modo supervisionado geralmente é somente para dispositivos corporativos.

## Como o Intune ajuda você a gerenciar o Bloqueio de Ativação
O Intune pode solicitar o status de Bloqueio de Ativação de dispositivos supervisionados e não supervisionados que executam o iOS 7.1 e posterior. Para dispositivos supervisionados, o Intune pode recuperar o código de bypass de Bloqueio de Ativação e emiti-lo diretamente para o dispositivo. Se o dispositivo for apagado, você poderá acessá-lo diretamente usando o código como o nome de usuário e uma senha em branco).

**Os benefícios para o negócio são**:

-   O usuário obtém os benefícios de segurança do aplicativo Buscar meu iPhone.

-   É possível permitir que o usuário faça seu trabalho sabendo que, quando o dispositivo precisar ser realocado, será possível desativar ou desbloqueá-lo.

## Como usar o bypass de Bloqueio de Ativação do console do administrador do Intune
> [!IMPORTANT]
> Depois de efetuar bypass do Bloqueio de Ativação em um dispositivo, ele aplicará automaticamente um novo Bloqueio de Ativação se o aplicativo Buscar meu iPhone for aberto. Por isso, **é necessário estar em posse física do dispositivo antes de seguir este procedimento**.

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos de Propriedade Corporativa**.

2.  Selecione o dispositivo cujo Bloqueio de Ativação você deseja efetuar bypass. Escolha **Bypass de Bloqueio de Ativação**.

3.  Leia a mensagem de aviso. Escolha **Sim** para continuar.

Você pode examinar o status da solicitação de desbloqueio na página de detalhes do dispositivo.

## Como ver quais dispositivos estão usando o Bloqueio de Ativação
Você pode ver quais dispositivos estão usando o Bloqueio de Ativação de duas maneiras:

-   Execute **Relatórios de Inventário de Dispositivo Móvel**. Este relatório exibe as colunas **Status do Bloqueio de Ativação** e **Supervisionado** para indicar o estado de dispositivos. Os valores de **Supervisionado** são **Sim** ou **Não**, e os valores do **Status do Bloqueio de Ativação** são:

    -   Habilitado com o código de bypass

    -   Habilitado sem o código de bypass (dispositivo não supervisionado)

    -   Habilitado sem o código de bypass (dispositivo não pode ser alcançado)

    -   Não habilitado

    O campo **Status de Ativação do Bloqueio** fica em branco para dispositivos que não executam o iOS 7.1 ou posterior.

-   Selecione um dispositivo em uma exibição de grupos, você pode ver o status de Bloqueio de Ativação no painel de detalhes do dispositivo.

    Se você selecionar um dispositivo no nó **Todos os Dispositivos Corporativos** e o Bloqueio de Ativação estiver habilitado para o dispositivo, você também poderá ver o código de bypass. Esse código pode ser usado para emitir manualmente um bypass de Bloqueio de Ativação.

### Consulte também
[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md)
[Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


