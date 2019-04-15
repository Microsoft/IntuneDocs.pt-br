---
title: Ignorar o Bloqueio de Ativação do iOS com o Intune
titleSuffix: Microsoft Intune
description: Saiba como usar o Intune para ignorar o Bloqueio de Ativação do iOS para acessar dispositivos bloqueados.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 406a08788663603340ab4af78217a07e68e66604
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "59568590"
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
>Depois que você ignorar o Bloqueio de Ativação em um dispositivo, se o aplicativo Localizar meu iPhone for iniciado, um novo Bloqueio de Ativação será aplicado automaticamente. Por isso, **é necessário estar em posse física do dispositivo antes de seguir este procedimento**.

A ação de dispositivo remoto **Ignorar Bloqueio de Ativação** do Intune remove o Bloqueio de Ativação de um dispositivo iOS sem a necessidade da ID da Apple e da senha do usuário. Depois que você ignorar o Bloqueio de Ativação, o dispositivo ativará o Bloqueio de Ativação novamente quando o aplicativo Localizar meu iPhone for iniciado. Ignore o Bloqueio de Ativação apenas se tiver acesso físico ao dispositivo.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.
3. Na folha **Intune**, selecione **Dispositivos**.
4. Na folha **Dispositivos**, selecione **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, selecione a ação de dispositivo remoto **Ignorar Bloqueio de Ativação**.
6. Vá para a seção “Hardware” do dispositivo e, em seguida, copie o valor do **código de bypass do Bloqueio de Ativação** em **Acesso Condicional**.

    >[!NOTE]
    >Copie o código de bypass antes de apagar o dispositivo. Se você redefinir as configurações do dispositivo antes de copiar o código, o código será removido do Azure.

7.  Acesse a folha **Visão Geral** do dispositivo e, em seguida, selecione **Apagar**.
8.  Depois que o dispositivo for reiniciado, você deverá inserir a *ID da Apple* e a *senha*. Deixe o campo *ID* em branco e, em seguida, insira o **código de bypass** para a *senha*. Isso remove a conta do dispositivo. 


## <a name="next-steps"></a>Próximas etapas

Examine o status da solicitação de desbloqueio na página de detalhes do dispositivo na carga de trabalho **Gerenciar dispositivos**.
