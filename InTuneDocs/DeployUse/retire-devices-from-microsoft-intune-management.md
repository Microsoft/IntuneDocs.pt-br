---
title: Desativar dispositivos | Microsoft Intune
description: "O Intune dá suporte ao apagamento seletivo e ao apagamento completo para remover o dispositivo do gerenciamento do Intune removendo suas políticas e o portal da empresa."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7bea7ba4ef59c6b1400414b59456e19dc1c152fb
ms.openlocfilehash: ad5e9453f8132d383f8c23886e48505769c7f44b


---

# Desativar dispositivos do gerenciamento do Intune

Quer os dispositivos sejam pessoais ou corporativos, chega o momento em que um dispositivo gerenciado precisa ser removido do gerenciamento do Intune. A desativação de dispositivo é relativamente simples. Você pode executar um apagamento seletivo ou completo em dispositivos gerenciados como dispositivos móveis. Você também pode desativar computadores gerenciados com o software cliente do Intune.

## Apagar dados e aplicativos dos dispositivos
Tanto o apagamento seletivo quanto o apagamento completo removem o dispositivo do gerenciamento do Intune removendo sua política e o portal da empresa, o que significa que o dispositivo deixa de ter as credenciais necessárias para fazer logon em recursos da empresa, como o Microsoft SharePoint, o email ou o Office 365.

O [apagamento seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) é a ação preferencial para funcionários que tiverem registrado seus próprios dispositivos no Intune, porque ela não afeta as informações pessoais no dispositivo. Somente dados corporativos são removidos.

Para dispositivos que precisam ser realocados, também é possível usar um [apagamento completo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), que redefine o dispositivo para as configurações padrão de fábrica.

## Para excluir dispositivos no portal do Active Directory do Azure

1.  Faça logon com suas credenciais da organização em [http://aka.ms/accessaad](http://aka.ms/accessaad) ou [https://portal.office.com](https://portal.office.com) e escolha **Centros de Administração** &gt; **Azure AD**.

2.  Se não tiver uma, crie uma assinatura do Azure. Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (clique no link de assinatura **Register your free Azure Active Directory** [Registrar seu Azure Active Directory gratuito]).

4.  Selecione **Active Directory** e selecione sua organização.

5.  Selecione a guia **Usuários** .

6.  Selecione o usuário cujos dispositivos que deseja excluir.

7.  Escolha **Dispositivos**.

8.  Selecione os dispositivos, conforme apropriado, e escolha **Excluir dispositivo**. O dispositivo será excluído na próxima vez que for sincronizado com o Active Directory. Em geral, isso ocorre em até 4 horas. Após a sincronização, o dispositivo é removido do gerenciamento. Isso remove um dispositivo do limite de dispositivos deste usuário.

## Desativar computadores gerenciados
Os computadores gerenciados com o software cliente do Intune podem ser removidos do gerenciamento por meio do console do administrador do Intune. Esse processo também desinstala o software cliente e exclui a política do Intune do computador. Veja informações sobre [como desativar computadores gerenciados com o software cliente do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Bloquear o acesso a um dispositivo
No caso de perda de dispositivo ou quando for necessário desativar um dispositivo devido à saída de um funcionário da empresa sem a devolução de um hardware de propriedade da empresa, também é possível [redefinir a senha e bloquear remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) o dispositivo. Isso impede que as informações da empresa sejam indevidamente utilizadas, embora você possa precisar dar baixa no dispositivo como perda.

Você também deseja revogar a licença da conta de usuário Intune do funcionário. Isso libera a licença, permitindo atribuí-la a uma nova conta de usuário.

## Desativar o hardware
Às vezes, é o próprio dispositivo que chegou ao fim da vida útil. Nesses casos, [redefini-lo para as configurações de fábrica](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) com um apagamento completo remove todos os dados e o dispositivo do Intune. Em seguida, você pode se desfazer do hardware de acordo com a política da empresa.

### Consulte também
[Ajudar a proteger os dados com apagamento completo ou seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO2-->


