---
title: Configurar políticas de atualização de software iOS no Microsoft Intune
titlesuffix: ''
description: Configure políticas de atualização do iOS para forçar dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 1d4223ae4feb417f77909b320cd0295347b44461
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Configurar políticas de atualização do iOS no Microsoft Intune

As políticas de atualização de software permitem forçar dispositivos iOS supervisionados a executarem o iOS 10.3 e posterior para instalar automaticamente a atualização de sistema operacional disponível mais recente. Esse recurso só está disponível para dispositivos supervisionados. Existe a opção de configurar os dias e horários em que não deseja que os dispositivos instalem a atualização. 

Quando o dispositivo fizer check-in, a cada 8 horas, aproximadamente, se uma atualização estiver disponível e não for durante um horário restrito, o dispositivo tentará baixar e instalar a atualização mais recente do sistema operacional. Não há nenhuma interação do usuário necessária para atualizar o dispositivo. A política não impediria que um usuário atualizasse o sistema operacional.

## <a name="configure-the-ios-update-policy"></a>Configurar a política de atualização do iOS
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Atualizações de software** > **Políticas de Atualização do iOS**.
4. No painel de políticas, escolha **Criar** e, em seguida, insira um nome e uma descrição para a política.
5. Selecione **Configurações** > **Configurar** e insira os detalhes de quando os dispositivos iOS não serão forçados a instalar a atualização mais recente. É possível configurar os dias da semana, o fuso horário, a hora de início e a hora de término.
6. Escolha **OK** para salvar esta configuração. Agora você retornou à página **Criar política de atualização**. Escolha **Criar** para criar a política e salvar suas configurações.

O perfil é criado e aparece no painel de lista de políticas de atualização do iOS. O Apple MDM não permite que a capacidade de impor que o dispositivo instale a atualização por um determinado tempo ou data. 

## <a name="change-the-restricted-times-for-the-policy"></a>Alterar as horas restritas da política

1.  Na folha **Atualizações do Software**, escolha **Políticas de Atualização do iOS**.
2.  Selecione a política de atualização do iOS que deseja atualizar.
3.  Selecione **Propriedades** e atualize as informações de horas restritas.
4.  Escolher os dias da semana
5.  Fuso horário no qual esta política será aplicada
6.  Hora de início e de término para as horas não autorizadas

## <a name="assign-an-ios-update-policy-to-users"></a>Atribuir uma política de atualização do iOS a usuários

Para atribuir uma política de atualização do iOS a usuários, escolha uma política que você configurou. As políticas existentes são encontradas no painel **Atualizações de software** > **Políticas de atualização do iOS**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. É aberto o painel no qual você pode selecionar grupos de segurança do Azure Active Directory e atribuí-los à política.
2. Escolha **Grupos selecionados** para abrir o painel que exibe os grupos de segurança do Azure AD. Determine quem tem acesso à política atribuindo os grupos a serem incluídos ou excluídos.
3. Escolha **Salvar** para implantar a política para os usuários.

Você aplicou a política aos seus usuários ou dispositivos. Os dispositivos usados pelos usuários que são afetados pela política são avaliados quanto à conformidade de atualizações. Essa política também é compatível com dispositivos sem usuários.

## <a name="monitor-ios-device-installation-failures"></a>Monitorar falhas de instalação do dispositivo iOS
<!-- 1352223 -->
O relatório **Falhas de instalação para dispositivos iOS** está disponível no painel **Atualizações de software**. No relatório, é possível exibir uma lista de dispositivos iOS supervisionados que foram afetados por uma política de atualização do iOS, que tentaram realizar uma atualização e não puderam ser atualizados. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. Dispositivos íntegros e atualizados não aparecerão na lista. Definimos "atualizado" como a atualização mais recente a que o próprio dispositivo pode dar suporte.

