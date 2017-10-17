---
title: Desativar dispositivos
description: "O Intune dá suporte ao apagamento seletivo e ao apagamento completo para remover o dispositivo do gerenciamento do Intune removendo suas políticas e o portal da empresa."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d304e0d27b6aa1ee568bc71272781f44efdce121
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="retire-devices-from-intune-management"></a>Desativar dispositivos do gerenciamento do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Quer os dispositivos sejam pessoais ou corporativos, chega o momento em que um dispositivo gerenciado precisa ser removido do gerenciamento do Intune.

Os dispositivos nunca serão removidos do Intune sem a intervenção do usuário, mesmo se eles não tiverem sido conectados ao serviço Intune por um período.

Você pode ter que desativar um dispositivo por diversos motivos:

-   O usuário deixa uma empresa de maneira planejada (partida "gerenciada")
-   O usuário parte abruptamente (é demitido, pede demissão etc.).
-   Perda de dispositivo
-   Realocação de um dispositivo (mudança para outro usuário, reutilização para uma finalidade diferente etc.)

Você pode executar um apagamento seletivo ou completo em um dispositivo gerenciado como um dispositivo móvel ou bloquear um dispositivo e redefinir a senha. Apagando o dispositivo, você libera a assinatura do usuário para adicionar um dispositivo diferente. Você também pode desativar computadores gerenciados com o software cliente do Intune.

## <a name="wipe-data-and-apps-from-devices"></a>Apagar dados e aplicativos dos dispositivos
O apagamento seletivo e o apagamento completo removem o dispositivo do gerenciamento do Intune, removendo sua política e o portal da empresa. Como resultado, o dispositivo não tem mais as credenciais necessárias para entrar em recursos da empresa como o Microsoft SharePoint, email ou Office 365.

O [apagamento seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) é a ação preferencial para funcionários que tiverem registrado seus próprios dispositivos no Intune, porque ela não afeta as informações pessoais no dispositivo. Somente dados corporativos são removidos.

Para dispositivos que precisam ser realocados, também é possível usar um [apagamento completo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), que redefine o dispositivo para as configurações padrão de fábrica.

### <a name="removing-user-licenses-and-managed-devices"></a>Removendo licenças de usuário e dispositivos gerenciados
Quando você remover uma licença de usuário, os dispositivos registrados do usuário não serão mais registrados. Como prática recomendada, você deve usar o apagamento seletivo para remover os dados da empresa de dispositivos gerenciados antes de remover a licença do Intune para um usuário. Quando você remover a licença de usuário, o dispositivo não pode ser alvo de ações remotas.

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Para excluir dispositivos no portal do Active Directory do Azure

1.  Entre com suas credenciais da organização em [http://aka.ms/accessaad](http://aka.ms/accessaad) ou [https://portal.office.com](https://portal.office.com) e escolha **Centros de Administração** &gt; **Azure AD**.

2.  Se não tiver uma, crie uma assinatura do Azure. Isso não deve exigir um cartão de crédito ou pagamento se você tiver uma conta paga. Escolha o link de assinatura **Registrar seu Azure Active Directory gratuito**.

4.  Escolha **Active Directory** e escolha sua organização.

5.  Escolha a guia **Usuários**.

6.  Selecione o usuário cujos dispositivos deseja excluir.

7.  Escolha **Dispositivos**.

8.  Escolha os dispositivos, conforme apropriado e escolha **Excluir dispositivo**. O dispositivo será excluído na próxima vez que for sincronizado com o Active Directory. Normalmente, isso ocorre em até quatro horas. Após a sincronização, o dispositivo é removido do gerenciamento. Isso remove um dispositivo do limite de dispositivos deste usuário.

## <a name="retire-managed-computers"></a>Desativar computadores gerenciados
Computadores gerenciados com o software cliente do Intune podem ser removidos do gerenciamento por meio do console do administrador do Intune. Esse processo também desinstala o software cliente e exclui a política do Intune do computador. Veja informações sobre [como desativar computadores gerenciados com o software cliente do Intune](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="block-access-a-device"></a>Bloquear o acesso a um dispositivo
Se um dispositivo for perdido ou quando for necessário desativar um dispositivo devido à saída de um funcionário da empresa sem a devolução de um hardware de propriedade da empresa, também será possível [redefinir a senha e bloquear remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) o dispositivo. Isso impede que as informações da empresa sejam indevidamente utilizadas, embora você possa precisar dar baixa no dispositivo como perda.

Você também deseja revogar a licença da conta de usuário Intune do funcionário. Isso libera a licença, permitindo atribuí-la a uma nova conta de usuário.

## <a name="retire-hardware"></a>Desativar o hardware
Às vezes, é o próprio dispositivo que chegou ao fim da vida útil. Nesses casos, [redefini-lo para as configurações de fábrica](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) com um apagamento completo remove todos os dados e o dispositivo do Intune. Em seguida, você pode se desfazer do hardware de acordo com a política da empresa.

### <a name="see-also"></a>Consulte também
[Ajudar a proteger os dados com apagamento completo ou seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)
