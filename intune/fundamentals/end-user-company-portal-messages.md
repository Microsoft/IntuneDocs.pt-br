---
title: Mensagens do Portal da Empresa que os usuários podem ver nos dispositivos
titleSuffix: Microsoft Intune
description: Entenda as diferentes mensagens que usuários finais podem ver no Portal da Empresa.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/09/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57467d3d073666c1c22ac0a412f68a258d5b3d75
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414065"
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Ajudar usuários finais a compreender as mensagens do aplicativo do Portal da Empresa

> [!NOTE]
> As informações a seguir aplicam-se somente aos dispositivos com Android 6.0 e posteriores e iOS 10 e posteriores.

Entenda as diferentes mensagens de aplicativo que os usuários finais podem ver no Portal da Empresa. Essas mensagens de aplicativo normalmente são exibidas em diferentes momentos no processo de registro. Saiba o local em que as mensagens são exibidas, o que significam e o que acontece se os usuários negarem acesso. Além disso, saiba como melhor explicar as mensagens aos usuários.

- __Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?__
- __Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?__

> [!NOTE]
> Não vendemos os dados coletados por nossos serviços para terceiros por nenhum motivo.

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?

### <a name="where-it-appears"></a>Onde ele aparece

A mensagem **Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?** é exibida quando os usuários tocam em **Registrar** no aplicativo do Portal da Empresa enquanto estão registrando o dispositivo.

### <a name="what-it-means"></a>O que significa

Ao aceitar este aviso, os usuários permitirão que o IMEI e o número de telefone de seus dispositivos sejam enviados ao serviço do Intune. Eles aparecerão no console do administrador na página __Hardware__.

> [!NOTE]
> **O aplicativo de Portal da Empresa nunca faz ou gerencia chamadas telefônicas!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

Para ver a página **Hardware**, é necessário acessar **Grupos** > **Todos os dispositivos móveis** > **Dispositivos**. Selecione o dispositivo do usuário e vá para **Exibir Propriedades** > **Hardware**.

### <a name="what-happens-if-users-deny-access"></a>O que acontece se os usuários negarem o acesso

Se os usuários negarem acesso, eles poderão continuar a usar o aplicativo de Portal da Empresa e registrar o dispositivo. No entanto, o IMEI e o número de telefone do dispositivo estarão em branco na página __Hardware__ no console do administrador. Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibirá uma caixa de seleção **Nunca Perguntar Novamente**, que os usuários podem selecionar, interrompendo o aviso.

Se os usuários permitirem, mas posteriormente negarem o acesso, a mensagem será exibida na próxima vez que os usuários entrarem no aplicativo Portal da Empresa após o registro.

Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.

### <a name="how-to-explain-this-to-your-users"></a>Como explicar isso aos seus usuários

Peça para os usuários [registrarem seu dispositivo Android no Intune](/intune-user-help/enroll-device-android-company-portal) para obter mais informações.

## <a name="allow-company-portal-to-access-your-contacts"></a>Permitir que o Portal da Empresa acesse seus contatos?

### <a name="where-it-appears"></a>Onde ele aparece

A mensagem **Permitir que o Portal da Empresa acesse seus contatos?** é exibida quando os usuários tocam em **Registrar** no aplicativo do Portal da Empresa enquanto estão registrando o dispositivo.

### <a name="what-it-means"></a>O que significa

Ao aceitar este prompt, os usuários permitem que o Intune crie sua conta de trabalho e gerencie a identidade do Azure Active Directory que está registrada para o usuário no dispositivo.

> [!NOTE]
> **A Microsoft nunca acessa seus contatos!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

### <a name="what-happens-if-users-deny-access"></a>O que acontece se os usuários negarem o acesso

Se os usuários negarem o acesso, o dispositivo não será registrado no Intune e não poderá ser gerenciado. Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para interromper o prompt.

Se os usuários permitem, mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entrarem no aplicativo do Portal da Empresa após o registro.

Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.

### <a name="how-to-explain-this-to-your-users"></a>Como explicar isso aos seus usuários

Peça para os usuários [registrarem seu dispositivo Android no Intune](/intune-user-help/enroll-device-android-company-portal) para obter mais informações.  

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?

### <a name="where-it-appears"></a>Onde ele aparece

A mensagem **Permitir que o Portal da Empresa acesse fotos, mídia e arquivos em seu dispositivo?** é exibida quando os usuários tocam em **Enviar dados** para enviar logs ao administrador de TI.

### <a name="what-it-means"></a>O que significa

Ao aceitar este prompt, os usuários permitem que seus dispositivos gravem logs de dados no cartão SD do dispositivo. Isso também permite que os logs sejam movidos usando um cabo USB.   

> [!NOTE]
> **O aplicativo do Portal da Empresa nunca acessa fotos, mídia e arquivos dos usuários!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

### <a name="what-happens-if-users-deny-access"></a>O que acontece se os usuários negarem o acesso

Se os usuários negarem o acesso, eles ainda podem enviar logs de dados por email, mas os logs não serão copiados para o cartão SD do dispositivo.

Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente. Se os usuários permitirem, mas posteriormente negarem o acesso, a mensagem será exibida na próxima vez que os usuários tentarem enviar logs. Entretanto, se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Armazenamento** e ativar a permissão.


### <a name="how-to-explain-this-to-your-users"></a>Como explicar isso aos seus usuários

Peça aos usuários para [enviarem logs para o administrador de TI por email](/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>O suporte da sua empresa precisa lhe conceder acesso aos recursos da empresa

### <a name="where-it-appears"></a>Onde ele aparece

Se você não tiver adicionado o aplicativo Portal da Empresa à lista de **Aplicativos permitidos** ou de **Aplicativos isentos** e um usuário tentar entrar, a entrada falhará. A mensagem a seguir é exibida:

> **O suporte da sua empresa precisa lhe conceder acesso aos recursos da empresa**  
> Sua empresa está usando as políticas de Proteção de Informações do Windows para proteger seu dispositivo. O suporte da empresa deverá permitir que o Portal da Empresa acesse esses recursos.

### <a name="what-it-means"></a>O que significa

Adicione o Portal da Empresa à lista de **Aplicativos permitidos** ou de **Aplicativos isentos** na política de proteção do aplicativo WIP (Proteção de Informações do Windows). Para obter mais informações, consulte [Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune](../apps/windows-information-protection-policy-create.md).

## <a name="approve-a-ios-company-app-line-of-business-app-on-your-ios-device"></a>Aprovar um aplicativo iOS da empresa (aplicativo de linha de negócios) em seu dispositivo iOS 

### <a name="where-it-appears"></a>Onde ele aparece

Os aplicativos iOS desenvolvidos pela sua organização que não estão disponíveis na App Store, por padrão, não são confiáveis para seu dispositivo. Quando você instalar esses aplicativos usando o Portal da Empresa e iniciar o aplicativo, a seguinte mensagem será exibida:

![Mensagem do aplicativo iOS – Enterprise Developer Não Confiável](./media/end-user-company-portal-messages/end-user-company-portal-messages-01.png)

### <a name="what-it-means"></a>O que significa

Esta mensagem indica que você precisa alterar as configurações do dispositivo iOS para aprovar e instalar um aplicativo desenvolvido pela sua empresa em seu dispositivo iOS.

Após instalar esses aplicativos usando o Portal da Empresa e iniciar o aplicativo, siga estas etapas para aprovar o aplicativo após o download:

1. Após iniciar um aplicativo da empresa (aplicativo de linha de negócios) instalado, você verá a mensagem "Enterprise Developer Não Confiável". <br>
   Pressione **Cancelar**.
2. Navegue até **Configurações** > **Geral** > **Gerenciamento de Dispositivos**.

   ![Interface do usuário do dispositivo iOS – Gerenciamento de Dispositivos](./media/end-user-company-portal-messages/end-user-company-portal-messages-02.png)

3. Escolha **Perfil de Gerenciamento** > **Aplicativo empresarial**.
4. Escolha o nome do desenvolvedor.
5. Pressione **Confiar _nome do desenvolvedor_** .
6. Confirme o aplicativo marcando **Confiar** na mensagem pop-up de instalação do aplicativo.

   ![Interface do usuário do dispositivo iOS – Mensagem de confiança do aplicativo](./media/end-user-company-portal-messages/end-user-company-portal-messages-03.png)

    Você deve conseguir iniciar e usar o aplicativo da empresa.


## <a name="see-also"></a>Consulte também
[O que dizer a seus usuários finais sobre como usar o Intune](end-user-educate.md)
