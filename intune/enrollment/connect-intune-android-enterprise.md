---
title: Conecte sua conta do Intune à sua conta do Google Play Gerenciado.
titleSuffix: Microsoft Intune
description: Saiba como conectar sua conta do Intune à sua conta do Google Play Gerenciado.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0fad076b33bed5375dd8e53dd401a2c9c4c39237
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505564"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Conectar sua conta do Intune à sua conta do Google Play Gerenciado

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Para dar suporte a [perfil de trabalho do Android Enterprise](android-work-profile-enroll.md), [Android Enterprise totalmente gerenciado](android-fully-managed-enroll.md) e [dispositivos dedicados com Android Enterprise](android-kiosk-enroll.md), você precisa conectar sua conta de locatário do Intune à sua conta do Google Play Gerenciado.  

Para facilitar a configuração e o uso do gerenciamento do Android Enterprise, ao se conectar ao Google Play, o Intune adicionará automaticamente quatro aplicativos comuns relacionados ao Android Enterprise ao console do administrador do Intune. Os quatro aplicativos do Android Enterprise são os seguintes:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – usado para cenários totalmente gerenciados pelo Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : ajudará você a entrar em suas contas se usar a verificação de dois fatores.
- **[Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – usado para cenários de perfil de trabalho das Políticas de Proteção do Aplicativo (APP) e do Android Enterprise.
- [Tela inicial gerenciada](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – usado para cenários dedicados/quiosques do Android Enterprise.

> [!NOTE]
> Devido à interação entre os domínios da Google e da Microsoft, esta etapa pode exigir que você ajuste as configurações do navegador.  Verifique se "portal.azure.com" e "play.google.com" estão na mesma zona de segurança em seu navegador.

1. Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [configurar a autoridade de gerenciamento do dispositivo móvel](../fundamentals/mdm-authority-set.md) como **Microsoft Intune**.
2. Entre no [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Android** > **Google Play Gerenciado**.  Se você estiver usando uma função de administrador do Intune personalizada, o acesso a isso exigirá permissões de Leitura e Atualização da Organização.
   
   ![Tela de registro do Android Enterprise](./media/connect-intune-android-enterprise/android-work-bind.png)

3. Escolher **Concordo** para conceder permissão à Microsoft para [enviar informações de usuário e dispositivo ao Google](../protect/data-intune-sends-to-google.md). 
   
4. Escolha **Iniciar Google para conectar agora** para abrir o site do Google Play gerenciado. O site é aberto em uma nova guia em seu navegador.
  
5. Na página de entrada do Google, insira a conta do Google que será associada a todas as tarefas de gerenciamento do Android Enterprise para esse locatário. Essa é a conta do Google que os administradores de TI da sua empresa compartilham para gerenciar e publicar aplicativos no console do Google Play. Você pode usar uma conta do Google existente ou criar uma nova. A conta escolhida não deve estar associada a um domínio G Suite.
    
    > [!Note]
    > Se você estiver usando o navegador Microsoft Edge, clique em **Entrar** no canto superior direito para entrar em sua conta do Google.

6. Forneça o nome da sua empresa para **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o **Provedor EMM (Enterprise Mobility Management)** .

7. Aceite o contrato do Android e, em seguida, escolha **Confirmar**. Sua solicitação será processada.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Desconectar sua conta administrativa do Android Enterprise

É possível desabilitar o registro e o gerenciamento do Android Enterprise. Para fazer isso, primeiro você deve desativar os dispositivos Android Enterprise registrados, incluindo dispositivos de perfil de trabalho, dispositivos dedicados e dispositivos totalmente gerenciados. Em seguida, escolha **Desconectar** no console de administração do Intune para remover do registro todos os dispositivos registrados de perfil de trabalho Android Enterprise, dispositivos dedicados e dispositivos totalmente gerenciados do registro. Isso também remove a relação entre a conta do Google Play Gerenciado e o Intune.

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) como administrador do Intune.
2. Escolha **Registro de dispositivo** > **Registro do Android** > **Google Play gerenciado** > **Desconectar**.
3. Escolha **Sim** para desconectar e cancelar o registro de todos os dispositivos Android Enterprise do Intune.

## <a name="next-steps"></a>Próximas etapas

Depois de conectar-se à conta do Google Play Gerenciado, você poderá [configurar dispositivos de perfil de trabalho Android Enterprise](android-work-profile-enroll.md), [configurar dispositivos dedicados com Android Enterprise](android-kiosk-enroll.md) e [configurar dispositivos totalmente gerenciados do Android Enterprise](android-kiosk-enroll.md)
