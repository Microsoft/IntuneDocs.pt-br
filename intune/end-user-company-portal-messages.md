---
title: "Mensagens do Portal da Empresa que os usuários podem ver no Android"
description: "Descreve as mensagens do aplicativo Portal da Empresa que os usuários finais do Intune podem ver."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.openlocfilehash: f1a5c8a15007a38942fe543e6c1062bf957a481c
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Ajudar usuários finais a compreender as mensagens do aplicativo do Portal da Empresa

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> As informações a seguir aplicam-se somente aos dispositivos com Android 6.0 e posteriores.

Em pontos diferentes no processo de registro, os usuários finais verão duas mensagens diferentes que podem ser motivo de preocupação.

- __Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?__
- __Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?

### <a name="where-it-appears"></a>Onde ele aparece
A mensagem **Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?** é exibida quando os usuários tocam em **Registrar** no aplicativo do Portal da Empresa enquanto estão registrando o dispositivo.

### <a name="what-it-means"></a>O que significa
Ao aceitar este aviso, os usuários permitirão que o IMEI e o número de telefone de seus dispositivos sejam enviados ao serviço do Intune. Eles aparecerão no console do administrador na página __Hardware__.

> [!NOTE]
> **O aplicativo de Portal da Empresa nunca faz ou gerencia chamadas telefônicas!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

Para ver a página **Hardware**, vá para **Grupos** > **Todos os dispositivos móveis** > **Dispositivos**. Selecione o dispositivo do usuário e vá para **Exibir Propriedades** > **Hardware**.

### <a name="what-happens-if-users-deny-access"></a>O que acontece se os usuários negarem o acesso
Se os usuários negarem acesso, eles poderão continuar a usar o aplicativo de Portal da Empresa e registrar o dispositivo. No entanto, o IMEI e o número de telefone do dispositivo estarão em branco na página __Hardware__ no console do administrador. Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para interromper o prompt.

Se os usuários permitem, mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entrarem no aplicativo do Portal da Empresa após o registro.

Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.

### <a name="how-to-explain-this-to-your-users"></a>Como explicar isso aos seus usuários
Peça para os usuários [registrarem seu dispositivo Android no Intune](/intune-user-help/enroll-your-device-in-intune-android) para obter mais informações.

## <a name="allow-company-portal-to-access-your-contacts"></a>Permitir que o Portal da Empresa acesse seus contatos?

### <a name="where-it-appears"></a>Onde ele aparece
A mensagem **Permitir que o Portal da Empresa acesse seus contatos?** é exibida quando os usuários tocam em **Registrar** no aplicativo do Portal da Empresa enquanto estão registrando o dispositivo.

### <a name="what-it-means"></a>O que significa
Ao aceitar este prompt, os usuários permitem que o Intune crie sua conta de trabalho e gerencie a identidade do Azure Active Directory que está registrada para o usuário no dispositivo.

> [!NOTE]
> **A Microsoft nunca acessa seus contatos!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

### <a name="what-happens-if-users-deny-access"></a>O que acontece se os usuários negarem o acesso
Se os usuários negarem o acesso, seu dispositivo não será registrado no Intune e não poderá ser gerenciado. Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para interromper o prompt.

Se os usuários permitem, mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entrarem no aplicativo do Portal da Empresa após o registro.

Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.

### <a name="how-to-explain-this-to-your-users"></a>Como explicar isso aos seus usuários
Peça para os usuários [registrarem seu dispositivo Android no Intune](/intune-user-help/enroll-your-device-in-intune-android) para obter mais informações.

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?

### <a name="where-it-appears"></a>Onde ele aparece
A mensagem **Permitir que o Portal da Empresa acesse fotos, mídia e arquivos em seu dispositivo?** é exibida quando os usuários tocam em **Enviar dados** para enviar logs ao administrador de TI.

### <a name="what-it-means"></a>O que significa
Ao aceitar este prompt, os usuários permitem que seu dispositivo grave logs de dados no cartão SD do dispositivo e que habilite esses logs a serem movidos usando um cabo USB.   

> [!NOTE]
> **O aplicativo do Portal da Empresa nunca acessa fotos, mídia e arquivos dos usuários!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

### <a name="what-happens-if-users-deny-access"></a>O que acontece se os usuários negarem o acesso
Se os usuários negarem o acesso, eles ainda podem enviar logs de dados por email, mas os logs não serão copiados para o cartão SD do dispositivo.

Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente. Se os usuários permitirem, mas posteriormente negarem o acesso, a mensagem será exibida na próxima vez que os usuários tentarem enviar logs. Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Armazenamento** e ativar a permissão.


### <a name="how-to-explain-this-to-your-users"></a>Como explicar isso aos seus usuários
Peça aos usuários para [enviarem logs para o administrador de TI por email](/intune-user-help/send-logs-to-your-it-admin-by-email-android). Você também pode pedir que eles [enviem logs para o administrador de TI por cabo](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) se quiser permitir que eles comparem os dois métodos.

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>O suporte da sua empresa precisa lhe conceder acesso aos recursos da empresa

### <a name="where-it-appears"></a>Onde ele aparece
Se você não tiver adicionado o aplicativo de Portal da Empresa à lista de **Aplicativos permitidos** ou de **Aplicativos isentos** e um usuário tentar entrar, a entrada falhará. A mensagem a seguir é exibida:

> **O suporte da sua empresa precisa lhe conceder acesso aos recursos da empresa**  
> Sua empresa está usando as políticas de Proteção de Informações do Windows para proteger seu dispositivo. O suporte da empresa precisará certificar-se de que eles permitem que o Portal da Empresa acesse essas informações.

### <a name="what-it-means"></a>O que significa

Adicione o Portal da Empresa à lista de **Aplicativos permitidos** ou de **Aplicativos isentos** na política de proteção do aplicativo WIP (Proteção de Informações do Windows). Para obter mais informações, consulte [Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).

### <a name="see-also"></a>Consulte também
[O que dizer a seus usuários finais sobre como usar o Intune](end-user-educate.md)
