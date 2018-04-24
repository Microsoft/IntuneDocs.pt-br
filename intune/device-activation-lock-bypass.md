---
title: Ignorar o Bloqueio de Ativação do iOS com o Intune
titlesuffix: Microsoft Intune
description: Saiba como usar o Intune para ignorar o Bloqueio de Ativação do iOS para acessar dispositivos bloqueados.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a8c14e523d33c9e0994134ff1ef468b290b3992
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Ignorar o Bloqueio de ativação em dispositivos iOS supervisionados com o Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 8.0 e posteriores. O Bloqueio de Ativação é habilitado automaticamente quando um usuário abre o aplicativo Buscar meu iPhone em um dispositivo. Depois que ele for habilitado, a ID da Apple e a senha do usuário deverão ser inseridas antes que qualquer pessoa possa:

- Desligar o Buscar meu iPhone
- Apagar o dispositivo
- Reativar o dispositivo

## <a name="how-activation-lock-affects-you"></a>Como o Bloqueio de Ativação afeta você

Embora o Bloqueio de Ativação ajude a proteger dispositivos iOS e aumente a probabilidade de recuperação de um dispositivo perdido ou roubado, como administrador de TI, essa funcionalidade pode apresentar vários desafios. Por exemplo:

- Um usuário configura o Bloqueio de Ativação em um dispositivo. O usuário sai da empresa e retorna o dispositivo. Sem a ID da Apple e a senha do usuário, não é possível reativar o dispositivo.
- Você precisa de um relatório de todos os dispositivos que têm o Bloqueio de Ativação habilitado.
- Você deseja transferir alguns dispositivos para um outro departamento durante uma atualização do dispositivo na sua organização. Só é possível reatribuir dispositivos que não têm o Bloqueio de Ativação habilitado.

Para ajudar a resolver esses problemas, a Apple introduziu bypass de Bloqueio de Ativação no iOS 7.1. O bypass de Bloqueio de Ativação permite remover o Bloqueio de Ativação de dispositivos supervisionados sem a ID da Apple e a senha do usuário. Dispositivos supervisionados podem gerar um código de bypass de Bloqueio de Ativação específico do dispositivo, que é armazenado no servidor de ativação da Apple.

>[!TIP]
>O modo supervisionado para dispositivos iOS permite que você use o Apple Configurator para bloquear um dispositivo e limitar a funcionalidade para fins comerciais específicos. Geralmente, o modo supervisionado é usado apenas em dispositivos corporativos.

Leia mais sobre o Bloqueio de Ativação no [site da Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Como o Intune ajuda você a gerenciar o Bloqueio de Ativação
O Intune pode solicitar o status do Bloqueio de Ativação de dispositivos supervisionados que executam o iOS 8.0 e posterior. Somente para dispositivos supervisionados, o Intune pode recuperar o código de bypass de Bloqueio de Ativação e emiti-lo diretamente para o dispositivo. Se o dispositivo tiver sido apagado, será possível acessar diretamente o dispositivo usando um nome de usuário em branco e o código como a senha.

**Os benefícios de negócios de usar o Intune para gerenciar o Bloqueio de Ativação são:**

- O usuário obtém os benefícios de segurança do aplicativo Buscar meu iPhone.
- É possível permitir que usuários façam seu trabalho e saibam que, quando um dispositivo precisar ser realocado, será possível desativá-lo ou desbloqueá-lo.

## <a name="before-you-start"></a>Antes de começar
Antes de usar o bypass de Bloqueio de Ativação nos dispositivos, é necessário habilitá-lo seguindo estas instruções:

1. Configure um perfil de restrição de dispositivo do Intune para o iOS usando as informações em [Como definir as configurações de restrição de dispositivo](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. Nas [Configurações de restrição de dispositivo para iOS](device-restrictions-ios.md), nas configurações **Geral**, habilite a opção **Bloqueio de ativação**.
3. Salve o perfil e, em seguida, [atribua-o](device-profile-assign.md) aos dispositivos nos quais você deseja gerenciar o bypass do Bloqueio de Ativação.


## <a name="how-to-use-activation-lock-bypass"></a>Como usar o bypass do Bloqueio de Ativação

>[!IMPORTANT]
>Depois de efetuar o bypass do Bloqueio de Ativação em um dispositivo, se o aplicativo Buscar iPhone estiver aberto, um novo Bloqueio de Ativação será aplicado automaticamente. Por isso, **é necessário estar em posse física do dispositivo antes de seguir este procedimento**.

A ação remota de dispositivo **Ignorar Bloqueio de Ativação** do Intune remove o bloqueio de ativação de um dispositivo iOS sem a ID da Apple e a senha do usuário. Depois de fazer o bypass do bloqueio de ativação, o dispositivo ativa-o novamente quando inicia o aplicativo o Localizar Meu iPhone. Faça bypass do bloqueio de ativação apenas se você tiver acesso físico ao dispositivo.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo iOS supervisionado, escolha **...Mais** e, em seguida, escolha a ação remota de dispositivo **Bypass de Bloqueio de Ativação**.

## <a name="next-steps"></a>Próximas etapas

Examine o status da solicitação de desbloqueio na página de detalhes do dispositivo na carga de trabalho **Gerenciar dispositivos**.
