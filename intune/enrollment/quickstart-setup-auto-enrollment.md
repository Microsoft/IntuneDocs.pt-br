---
title: Início Rápido – Configurar o registro automático no Intune
description: Início Rápido – Configurar o registro automático para dispositivos Windows 10 no Intune.
services: microsoft-intune
author: ErikjeMS
manager: dougeby
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e5cc7cf3661caa2b2640d9370d26402b7702d36b
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540989"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Início Rápido: Configurar o registro automático para dispositivos Windows 10

Neste Início Rápido, você configurará o Microsoft Intune para registrar automaticamente os dispositivos quando usuários específicos entrarem com dispositivos Windows 10.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Assinatura do Microsoft Intune – [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).
- Para concluir este início rápido, é preciso primeiro [criar um usuário](../fundamentals/quickstart-create-user.md) e [criar um grupo](../fundamentals/quickstart-create-group.md).

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Entre no Intune no Gerenciador de Ponto de Extremidade da Microsoft

Entre no [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como Administrador global ou Administrador de serviços do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="set-up-windows-10-automatic-enrollment"></a>Configurar o registro automático do Windows 10

Neste exemplo, você usará o registro de MDM para que dispositivos corporativos e traga seu próprio dispositivo podem ser registrados automaticamente. Você se inscreverá para uma assinatura do Azure Active Directory Premium.

1. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Todos os serviços** > **M365 Azure Active Directory** > **Azure Active Directory** > **Mobilidade (MDM e MAM)** .
2. Selecione **Receber uma avaliação gratuita Premium para usar este recurso**. Esta opção permitirá o registro automático usando a avaliação Premium gratuita do Azure Active Directory. 

    ![Selecione a avaliação Premium gratuita do Azure Active Directory](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-01.png)

3. Escolha a opção de avaliação gratuita do **Enterprise Mobility + Security E5**. 
4. Clique em **Avaliação gratuita** > **Ativar** a avaliação gratuita.

    ![Escolha a avaliação gratuita do Enterprise Mobility + Security E5](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-02.png)

    > [!NOTE]
    > A ativação pode demorar até um minuto. 

3. Selecione **Microsoft Intune** para configurar o Intune. 

    ![Escolha Microsoft Intune na lista](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

4. Selecione **Alguns** do **Escopo do usuário do MDM** para usar o registro automático do MDM para gerenciar dados empresariais em dispositivos Windows dos funcionários. O registro automático do MDM será configurado para cenários de traga seu próprio dispositivo e de dispositivos ingressados no AAD.

    ![Selecione 'Alguns' na lista Configurar](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

5. Clique em **Selecionar grupos** > **Testadores Contoso** > **Selecionar** como o grupo atribuído.

    ![Selecione o grupo a ser registrado](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

6. Selecione **Alguns** do **Escopo de usuários do MAM** para gerenciar dados em dispositivos da sua força de trabalho.

    ![Selecione o grupo a ser registrado](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-06.png)

7. Escolha **Selecionar grupos** > **Testadores Contoso** > **Selecionar** como o grupo atribuído. 
8. Use os valores padrão para os valores de configuração restantes.
9. Selecione **Salvar**.

## <a name="clean-up-resources"></a>Limpar os recursos

Para reconfigurar o registro automático do Intune, confira [Configurar o registro para dispositivos Windows](windows-enroll.md).

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você aprendeu como configurar o registro automático para dispositivos Windows 10. Para obter mais informações sobre o registro de dispositivo, confira [O que é o registro de dispositivo?](device-enrollment.md)

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Registrar seu dispositivo Windows 10](../quickstart-enroll-windows-device.md)
