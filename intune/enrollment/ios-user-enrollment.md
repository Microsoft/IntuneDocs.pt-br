---
title: Registrar dispositivos iOS – Registro de usuário
titleSuffix: Microsoft Intune
description: Saiba como configurar o Registro de usuário do iOS e iPadOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e538204306ce80d6a13739fc981edf2748a622de
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713470"
---
# <a name="set-up-ios-and-ipados-user-enrollment-preview"></a>Configurar o Registro de usuário do iOS e iPadOS (versão prévia)

Você pode configurar o Intune para registrar dispositivos iOS e iPadOS usando o processo de Registro de usuário da Apple. O Registro de usuário fornece aos administradores um subconjunto simplificado de opções de gerenciamento em comparação com os outros métodos de registro.

Para obter mais informações sobre as opções disponíveis com o Registro de usuário, confira [Ações compatíveis com Registro de usuário, senhas e outras opções](ios-user-enrollment-supported-actions.md).

> [!NOTE]
> O suporte do Registro de usuário da Apple no Intune está em versão prévia atualmente.

## <a name="prerequisites"></a>Pré-requisitos
- [Autoridade de MDM (Gerenciamento de Dispositivo Móvel)](../fundamentals/mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [IDs gerenciadas da Apple](https://support.apple.com/guide/apple-business-manager/mdm1c9622977/web).

## <a name="create-a-user-enrollment-profile-in-intune"></a>Criar um perfil de Registro de usuário no Intune

Um perfil de registro define as configurações aplicadas a um grupo de dispositivos durante o registro. 

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Registro de dispositivos** > **Registro da Apple** > **Tipos de registro (visualização)**  > **Criar perfil** > **iOS**. Nesse perfil, você indicará qual experiência de registro os usuários finais do iOS e do iPadOS terão em dispositivos não registrados por meio de um método corporativo da Apple. Se você quiser fazer alterações, poderá editar esse perfil depois de criá-lo.

    ![Criar perfil de registro da Apple](./media/ios-user-enrollment/create-profile.png)

2. Na página **Noções Básicas**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices).

    ![Página de informações básicas](./media/ios-user-enrollment/basics-page.png)


3. Selecione **Avançar**.

4. Na página **Configurações**, você pode optar por fornecer aos usuários a opção de qual tipo de registro eles usarão. Como alternativa, você pode definir um padrão.

    ![Página de configurações](./media/ios-user-enrollment/settings-page.png)

    - Se você quiser que todos os usuários nesse perfil usem o Registro de usuário, siga estas etapas:
        1. Para **Exigir que o usuário selecione o tipo de dispositivo**, selecione **Não configurado**.
        2. Para **Tipo de registro padrão**, selecione **Registro de usuário**.
    - Se você quiser que todos os usuários nesse perfil usem o Registro de dispositivo, siga estas etapas:
        1. Para **Exigir que o usuário selecione o tipo de dispositivo**, selecione **Não configurado**.
        2. Para **Tipo de registro padrão**, selecione **Registro de dispositivo**.
    - Se você quiser dar a todos os usuários desse grupo a opção de qual tipo de registro usar, selecione **Obrigatório** em **Exigir que o usuário selecione o tipo de dispositivo**. Quando os usuários registram seus dispositivos, eles terão a opção de escolher entre **Sou proprietário deste dispositivo** e **(Empresa) é proprietária deste dispositivo**. Se eles escolherem o primeiro, o dispositivo será registrado usando o Registro de usuário. Se eles escolherem o segundo, o dispositivo será registrado usando o Registro de dispositivo. Se o usuário escolher **Sou proprietário deste dispositivo**, ele verá outra opção para proteger todo o dispositivo ou proteger somente aplicativos e dados relacionados ao trabalho. A seleção do usuário final quanto a ele ser o proprietário do dispositivo determina apenas qual tipo de registro é implementado no dispositivo. Essa escolha do usuário não é refletida no atributo de Propriedade de dispositivo no Intune. Para saber mais sobre a experiência do usuário, confira [Configurar o acesso do dispositivo iOS aos recursos de sua empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).
    
    > [!NOTE]
    > O aviso a seguir é impreciso e será removido da interface do usuário.
    > "Para o Acesso Condicional funcionar em dispositivos direcionados ao Registro de Usuário, será necessário enviar por push o aplicativo Azure Authenticator como um aplicativo necessário para esse grupo de usuários habilitar o logon único e o Workplace Join."
    > Como administrador, você não precisa realizar nenhuma ação para enviar por push o aplicativo autenticador para seus usuários. Os usuários serão instruídos dentro do Portal da Empresa a instalarem o aplicativo Authenticator para concluir o processo de Registro de usuário e garantir que esses cenários funcionem corretamente.

5. Selecione **Avançar**.

6. Na página **Atribuições**, escolha os grupos de usuários que contêm os usuários para os quais você deseja atribuir esse perfil. Você pode optar por atribuir o perfil a todos os usuários ou a grupos específicos. Todos os usuários nos grupos selecionados usarão o tipo de registro escolhido acima. Os grupos de dispositivos não são compatíveis com cenários de Registro de usuário porque o recurso é baseado em identidades de usuário, em vez de dispositivos. Você pode optar por atribuir o perfil a todos os usuários ou a grupos específicos.

    ![Página de atribuições](./media/ios-user-enrollment/assignments-page.png)

7. Selecione **Avançar**.

8. Na página **Examinar e criar**, examine suas escolhas e, em seguida, selecione **Criar** para atribuir o perfil aos usuários.

    ![Página de atribuições](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Prioridade do perfil

Depois de criar mais de um perfil de tipo de registro, é possível alterar a ordem de prioridade na qual eles são aplicados.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Registro de dispositivos** > **Registro da Apple** > **Tipos de registro (visualização)** .
2. Arraste e solte os perfis da lista na ordem que você deseja aplicá-los.

Em caso de conflitos entre os perfis de qualquer usuário, o perfil de maior prioridade é aplicado ao usuário.


