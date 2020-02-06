---
title: Solucionar problemas de ações de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Obtenha ajuda para solucionar problemas de ação do dispositivo.
keywords: ''
author: erikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ROBOTS: ''
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d4517d89e3b7365834e904c815b30a362540906
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755588"
---
# <a name="troubleshoot-device-actions-in-intune"></a>Solucionar problemas com ações do dispositivo no Intune

O Microsoft Intune tem muitas ações que ajudam você a gerenciar dispositivos. Este artigo fornece respostas para algumas perguntas comuns que podem ajudar você a solucionar problemas com ações do dispositivo.

## <a name="disable-activation-lock-action"></a>Ação Desabilitar o Bloqueio de Ativação

### <a name="i-clicked-the-disable-activation-lock-action-in-the-portal-but-nothing-happened-on-the-device"></a>Cliquei na ação "Desabilitar Bloqueio de Ativação" no portal, mas nada aconteceu no dispositivo.
Isso é esperado. Quando a ação Desabilitar Bloqueio de Ativação é iniciada, a Apple solicita um código atualizado do Intune. Você inserirá manualmente o código no campo de senha quando o dispositivo estiver na tela do Bloqueio de Ativação. Esse código é válido por 15 dias, sendo assim, certifique-se de clicar na ação e copiar o código antes de emitir o Apagamento.

### <a name="why-dont-i-see-the-disable-activation-lock-code-in-the-hardware-overview-blade-of-my-ios-device"></a>Por que não vejo o código da ação Desabilitar Bloqueio de Ativação na folha de visão geral do hardware de meu dispositivo iOS?
Os motivos mais prováveis incluem:
- O código expirou e foi limpo do serviço.
- O dispositivo não é supervisionado com a Política de Restrição de Dispositivo para permitir o Bloqueio de Ativação.

Você pode verificar o código no Explorador do Graph com a seguinte consulta:

```GET - https://graph.microsoft.com/beta/deviceManagement/manageddevices('deviceId')?$select=activationLockBypassCode.```

### <a name="why-is-the-disable-activation-lock-action-greyed-out-for-my-ios-device"></a>Por que a ação Desabilitar Bloqueio de Ativação está esmaecida para meu dispositivo iOS?
Os motivos mais prováveis incluem: 
- O código expirou e foi limpo do serviço.
- O dispositivo não é supervisionado com a Política de Restrição de Dispositivo para permitir o Bloqueio de Ativação.

### <a name="is-the-disable-activation-lock-code-case-sensitive"></a>O código da ação Desabilitar Bloqueio de Ativação diferencia maiúsculas de minúsculas?
Não. E você não precisa inserir os traços.

## <a name="remove-devices-action"></a>Ação Remover dispositivos

### <a name="how-do-i-tell-who-started-a-retirewipe"></a>Como saber quem iniciou uma ação Desativar/Apagar?
No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), acesse **Administração de locatários** > **Logs de auditoria** > marque a coluna **Iniciado por**.
Se você não vir uma entrada, o mais provável é que o usuário do dispositivo tenha iniciado a ação. Ele provavelmente usou o aplicativo Portal da Empresa ou portal.manage.microsoft.com.

### <a name="why-wasnt-my-application-uninstalled-after-using-retire"></a>Por que meu aplicativo não foi desinstalado depois de usar a ação Desativar?
Porque ele não era considerado um aplicativo gerenciado. Nesse contexto, um aplicativo gerenciado é um aplicativo que foi instalado usando o serviço do Intune. Isso inclui:
- O aplicativo foi implantado como Necessário
- O aplicativo foi implantado como Disponível e, em seguida, foi instalado pelo usuário final de dentro do aplicativo Portal da Empresa.

### <a name="why-is-wipe-grayed-out-for-android-enterprise-work-profile-devices"></a>Por que a ação Apagar está esmaecida para dispositivos Android Enterprise com Perfil de Trabalho?
Esse comportamento é esperado. O Google não permite a Redefinição de Fábrica de dispositivos com Perfil de Trabalho usando um Provedor de MDM.

### <a name="why-can-i-sign-back-into-my-office-apps-after-my-device-was-retired"></a>Por que posso entrar em meus aplicativos do Office após meu dispositivo ter sido desativado?
Porque desativar um dispositivo não revoga os tokens de acesso. Você pode usar políticas de Acesso Condicional para atenuar essa condição.

### <a name="how-can-i-monitor-a-retirewipe-action-after-it-was-issued"></a>Como posso monitorar uma ação Desativar/Apagar após sua emissão?
No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), acesse **Administração de locatários** > **Logs de auditoria**.

### <a name="why-do-wipes-sometimes-show-as-pending-indefinitely"></a>Por que as ações de apagar às vezes são mostradas como pendentes de forma indefinida?
Os dispositivos nem sempre relatam seu status para o serviço do Intune antes do início da redefinição. Sendo assim, a ação é mostrada como Pendente. Se você confirmou que a ação foi bem-sucedida, exclua o dispositivo do serviço.

### <a name="what-happens-if-i-start-a-retirewipe-on-an-offline-device-or-a-device-that-hasnt-communicated-with-the-service-in-a-while"></a>O que acontecerá se eu iniciar uma ação Desativar/Apagar em um dispositivo offline ou em um dispositivo que não se comunica com o serviço há algum tempo?
O dispositivo permanecerá no estado **Desativação/Apagamento Pendente** até o certificado do MDM expirar. O certificado do MDM tem duração de um ano após registro e é renovado automaticamente todo ano. Se fizer check-in antes que o certificado do MDM expire, o dispositivo será desativado/apagado. Se não fizer check-in antes que o certificado do MDM expire, o dispositivo não poderá fazer check-in no serviço. O dispositivo é removido automaticamente do Portal do Azure 180 dias após a expiração do certificado do MDM.


## <a name="reset-passcode-action"></a>Ação Redefinir Senha

### <a name="why-is-the-reset-passcode-action-greyed-out-on-my-android-device-admin-enrolled-device"></a>Por que a ação Redefinir Senha está esmaecida em meu dispositivo Android registrado no Administrador de Dispositivos?
Para combater casos de ransomware, o Google removeu o recurso de redefinição de senha da API do Administrador de Dispositivos (aplica-se a dispositivos Android versão 7.0 ou superiores).

### <a name="why-do-i-get-a-not-supported-message-when-i-issue-a-passcode-reset-to-my-android-80-or-later-work-profile-enrolled-device"></a>Por que recebo uma mensagem "Sem Suporte" ao emitir uma redefinição de senha para meu dispositivo Android 8.0 ou posterior registrado no Perfil de Trabalho?
Porque o Token de Redefinição não foi ativado no dispositivo. Para ativar o Token de Redefinição:
1. Você precisa exigir uma senha do Perfil de Trabalho em sua Política de Configuração.
2. O usuário final precisa definir uma senha apropriada do Perfil de Trabalho.
3. O usuário final precisa aceitar o prompt secundário para permitir a redefinição de senha.
Após essas etapas serem concluídas, você não deverá mais receber essa resposta.

### <a name="why-am-i-prompted-to-set-a-new-passcode-on-my-ios-device-when-i-issue-the-remove-passcode-action"></a>Por é solicitado que eu defina uma nova senha em meu dispositivo iOS quando eu emito a ação Remover Senha?
Porque uma de suas políticas de conformidade requer uma senha.

## <a name="next-steps"></a>Próximas etapas

Obtenha [ajuda do suporte da Microsoft](../fundamentals/get-support.md) ou use os [fóruns da comunidade](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
