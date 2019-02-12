---
title: Conectar sua conta do Intune à sua conta do Android Enterprise
titlesuffix: Microsoft Intune
description: Saiba como conectar sua conta do Intune à sua conta do Android Enterprise.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 421d9c56f959fe30d35c0c55ce34017a7a0ba5a6
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838251"
---
# <a name="connect-your-intune-account-to-your-android-enterprise-account"></a>Conectar sua conta do Intune à sua conta do Android Enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Para dar suporte a dispositivos de [perfil de trabalho Android](android-work-profile-enroll.md), [dispositivos Android totalmente gerenciados](android-fully-managed-enroll.md) e [dispositivos Android dedicados](android-kiosk-enroll.md), você precisa conectar sua conta de locatário do Intune à sua conta corporativa do Android.  

> [!NOTE]
> Devido à interação entre os domínios da Google e da Microsoft, esta etapa pode exigir que você ajuste as configurações do navegador.  Verifique se "portal.azure.com" e "play.google.com" estão na mesma zona de segurança em seu navegador.

1. Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [configurar a autoridade de gerenciamento do dispositivo móvel](mdm-authority-set.md) como **Microsoft Intune**.
2. Entre no [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Android** > **Google Play Gerenciado**.  Se você estiver usando uma função de administrador do Intune personalizada, o acesso a isso exigirá permissões de Leitura e Atualização da Organização.
   
   ![Tela de registro do Android Enterprise](./media/android-work-bind.png)

3. Escolher **Concordo** para conceder permissão à Microsoft para [enviar informações de usuário e dispositivo ao Google](data-intune-sends-to-google.md). 
   
4. Escolha **Iniciar Google para conectar agora** para abrir o site do Google Play gerenciado. O site é aberto em uma nova guia em seu navegador.
  
5. Na página de entrada do Google, insira a conta do Google que será associada a todas as tarefas de gerenciamento do Android Enterprise para esse locatário. Essa é a conta do Google que os administradores de TI da sua empresa compartilham para gerenciar e publicar aplicativos no console do Google Play. Você pode usar uma conta do Google existente ou criar uma nova. A conta escolhida não deve estar associada a um domínio G Suite.
    
    > [!Note]
    > Se você estiver usando o navegador Microsoft Edge, clique em **Entrar** no canto superior direito para entrar em sua conta do Google.

6. Forneça o nome da sua empresa para **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o **Provedor EMM (Enterprise Mobility Management)**.

7. Aceite o contrato do Android e, em seguida, escolha **Confirmar**. Sua solicitação será processada.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Desconectar sua conta administrativa do Android Enterprise

É possível desabilitar o registro e o gerenciamento do Android Enterprise. Para fazer isso, primeiro desative os dispositivos registrados de perfil de trabalho do Android. Em seguida, escolha **Desconectar** no console de administração do Intune para remover do registro todos os dispositivos registrados de perfil de trabalho e de quiosque do Android. Isso também remove a relação entre a conta empresarial do Android e o Intune.

1. Como administrador do Intune, no [portal do Azure](https://portal.azure.com), escolha **Todos os Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Escolha **Registro de dispositivo** > **Registro do Android** > **Google Play gerenciado** > **Desconectar**.
3. Escolha **Sim** para desconectar e cancelar o registro de todos os dispositivos Android Enterprise do Intune.

## <a name="next-steps"></a>Próximas etapas

Depois de conectar-se à conta do Android Enterprise, você poderá [configurar dispositivos de perfil de trabalho Android](android-work-profile-enroll.md) e [configurar dispositivos de quiosque Android](android-kiosk-enroll.md).
