---
title: 'Início Rápido: definir um tamanho de senha obrigatório para dispositivos Android'
titlesuffix: Microsoft Intune
description: Neste início rápido, você usará o Microsoft Intune para definir o comprimento de senha obrigatório para dispositivos Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f925df731c3ddd45b13d976b0686d76d941c71e6
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2018
ms.locfileid: "49395268"
---
# <a name="quickstart-set-a-required-password-length-for-android-devices"></a>Início Rápido: definir um tamanho de senha obrigatório para dispositivos Android

Neste início rápido, você usará o Microsoft Intune para exigir que os usuários do Android da sua equipe de trabalho insiram uma senha de comprimento específico antes de conceder acesso às informações em seus dispositivos Android. 

> [!IMPORTANT]
> Além das configurações de senha, você também deve considerar outras configurações de segurança do sistema para proteger sua força de trabalho. Saiba mais em [Configurações de segurança do sistema](compliance-policy-create-android-for-work.md#system-security-settings).

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. O Intune encontra-se no portal do Azure, escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo
1. Depois de abrir a folha **Microsoft Intune**, selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
2. Adicione **Conformidade do Android** como o **Nome**. Além disso, adicione uma **Descrição**.
3. Para **Plataforma**, selecione **Android**. 
4. Selecione **Configurações** > **Segurança do Sistema** para exibir a folha **Segurança do Sistema** do Android.
5. Na seção **Senha**, próximo a **Exigir uma senha para desbloquear os dispositivos móveis**, clique em **Exigir**.
6. Próximo a **Comprimento mínimo da senha**, insira **6**.  

    ![Captura de tela da criação de um grupo no Microsoft Intune](./media/quickstart-set-password-length-android-01.png)

7. Quando terminar, clique em **OK** para fechar a folha **Segurança do Sistema**. 
8. Clique em **OK** para fechar a folha **Política de Conformidade do Android**. 
9. Clique em **Criar** para criar a política.

Após criar a política com sucesso, ela aparecerá na lista **Conformidade do dispositivo — Políticas**. 

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você usou o Intune para criar uma política de conformidade para os dispositivos Android da sua força de trabalho para exigir uma senha com pelo menos seis caracteres de comprimento.

> [!div class="nextstepaction"]
> [Configurar registro automático](quickstart-setup-auto-enrollment.md)
