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
ms.date: 03/26/2019
ms.author: erikje
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e9649a84650a555e964cd9200ed2295fee5efb9a
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74562305"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Início Rápido: Configurar o registro automático para dispositivos Windows 10

Neste Início Rápido, você configurará o Microsoft Intune para registrar automaticamente os dispositivos quando usuários específicos entrarem com dispositivos Windows 10.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Assinatura do Microsoft Intune – [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).
- Para concluir este início rápido, é preciso primeiro [criar um usuário](../fundamentals/quickstart-create-user.md) e [criar um grupo](../fundamentals/quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como Administrador global ou Administrador de Serviços do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="set-up-windows-10-automatic-enrollment"></a>Configurar o registro automático do Windows 10

Neste exemplo, você usará o registro de MDM para que dispositivos corporativos e traga seu próprio dispositivo podem ser registrados automaticamente. Você se inscreverá para uma assinatura do Azure Active Directory Premium.

1. No [portal do Azure](https://portal.azure.com), escolha o **Azure Active Directory** > **Mobility (MDM e MAM)** .
2. Selecione **Receber uma avaliação gratuita Premium para usar este recurso**. Esta opção permitirá o registro automático usando a avaliação Premium gratuita do Azure Active Directory. 

    ![Selecione a avaliação Premium gratuita do Azure Active Directory](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-01.png)

    Escolha a opção de avaliação gratuita do **Enterprise Mobility + Security E5**. Além disso, você deve optar por **Ativar** a avaliação gratuita.

    ![Escolha a avaliação gratuita do Enterprise Mobility + Security E5](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-02.png)

3. Selecione **Microsoft Intune**. 

    ![Escolha Microsoft Intune na lista](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

4. Selecione **Alguns** do **Escopo do usuário do MDM** para usar o registro automático do MDM para gerenciar dados empresariais em dispositivos Windows dos funcionários. O registro automático do MDM será configurado para cenários de traga seu próprio dispositivo e de dispositivos ingressados no AAD.

    ![Selecione 'Alguns' na lista Configurar](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

5. Escolha **Selecionar grupos** > **Testadores Contoso** > **Selecionar** como o grupo atribuído.

    ![Selecione o grupo a ser registrado](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

6. Selecione **Alguns** do **Escopo de usuários do MAM** para gerenciar dados em dispositivos da sua força de trabalho.
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
