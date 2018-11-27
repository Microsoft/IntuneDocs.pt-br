---
title: Início Rápido – Registrar seu dispositivo Windows 10 Desktop no Microsoft Intune
description: Início Rápido – Usar o Portal da Empresa para registrar seu dispositivo Windows 10 Desktop no Microsoft Intune.
services: microsoft-intune
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 658a7655-a6df-4dbe-b56c-22c7fc60e706
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: 13ffb9e7091b484c59f44802de675b1ab45b1c77
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183461"
---
# <a name="quickstart-enroll-your-windows-10-device"></a>Início Rápido: Registrar seu dispositivo Windows 10

Neste início rápido, primeiro você assumirá a função de um usuário do Intune e registrará seu dispositivo Windows 10 no Microsoft Intune. Em seguida, retornará para o Intune e confirmará o dispositivo registrado.

Registrar seus dispositivos no Microsoft Intune permite que dispositivos Windows 10 tenham acesso a dados protegidos da sua organização, incluindo email, arquivos e outros recursos. Isso vale para dispositivos com Windows 10 Desktop e Windows 10 Mobile. Registrar seus dispositivos ajuda a proteger o acesso para você e para sua organização e ajuda a manter dados de trabalho separados de dados pessoais.

> [!TIP]
> Saiba o que acontece quando você [registra seu dispositivo no Intune](/intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) e o que isso significa para as [informações no dispositivo](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Assinatura do Microsoft Intune – [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md)
- Para concluir este início rápido, você deve concluir as etapas para [configurar o registro automático no Intune](quickstart-setup-auto-enrollment.md).

## <a name="confirm-your-windows-10-desktop-version"></a>Confirmar sua versão do Windows 10 Desktop

Antes de registrar seu Windows 10 Desktop, você deve confirmar a versão do Windows que tem instalada.

1. Clique com o botão direito do mouse no ícone **Iniciar** do Windows e selecione **Configurações** para exibir as opções de Configurações do Windows.

   ![Captura de tela de Configurações do Windows – Sistema](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-01.png)

2. Selecione **Sistema** > **Sobre**. 

   ![Captura de tela das configurações do sistema](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-02.png)

    > [!TIP]
    > Você também pode digitar a frase "Sobre seu computador" na **barra de pesquisa** e selecionar **Sobre seu computador**.

3. Na janela **Configurações**, você verá uma lista das **Especificações do Windows** do seu computador. Dentro dessa lista, localize a **Versão**.

4. Confirme se a **versão** do Windows 10 é **1607 ou posterior**.

    > [!IMPORTANT]
    > As etapas apresentadas neste início rápido são para a versão **1607 ou posterior** do Windows 10, se a versão for **1511 ou anterior**, continue com [estas etapas](/intune-user-help/enroll-your-w10-device-your-account.md).

## <a name="enroll-windows-10-desktop"></a>Registrar o Windows 10 Desktop

1. Volte para as Configurações do Windows e selecione **Contas**.

   ![Captura de tela das configurações do sistema – Contas](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-03.png)

2. Selecione **Acessar trabalho ou escola** > **Conectar**.

    ![Selecione Acessar conta corporativa ou de estudante](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-04.png)

3. Entre no Intune com sua conta corporativa ou de estudante e selecione **Avançar**. Se você seguiu o início rápido [criar um usuário e atribuir uma licença], poderá entrar com a conta de usuário que você criou.

    > [!NOTE]
    > Se você configurar um ".onmicrosoft.com", a conta de usuário terá **.onmicrosoft.com** como parte do endereço dela. 

   ![Insira sua conta corporativa ou de estudante](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-05.png)

    Você verá uma mensagem que indica que sua empresa ou escola está registrando o dispositivo.

4. Quando você vir a página **Tudo pronto!**, selecione **Concluir**. Você terminou.

5. Agora você verá a conta adicionada como parte das configurações de **Acessar trabalho ou escola** em sua área de trabalho do Windows.

   ![Captura de tela da conta recém-adicionada](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-06.png)

    Se você seguiu as etapas anteriores, mas ainda não consegue acessar sua conta de email e seus arquivos corporativos ou de estudante, siga as etapas em [As etapas a serem seguidas se você vir Acessar conta corporativa ou de estudante](/intune-user-help/troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

## <a name="confirm-your-device-enrollment-in-intune"></a>Confirmar o registro de dispositivo no Intune

1. Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune.
2. Selecione **Dispositivos** para exibir os dispositivos registrados no Intune.
3. Verifique se você tem um dispositivo adicional registrado no Intune.

   ![Captura de tela dos dispositivos registrados no Intune](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-07.png)

## <a name="clean-up-resources"></a>Limpar os recursos

Para cancelar o registro do seu dispositivo Windows, confira [Remover o dispositivo Windows do gerenciamento](/intune-user-help/unenroll-your-device-from-intune-windows.md).

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você aprendeu como registrar um dispositivo Windows 10 no Intune. Saiba sobre as outras maneiras de registrar dispositivos em todas as plataformas. Para obter mais informações sobre como usar dispositivos com o Intune, confira [Usar dispositivos gerenciados para realizar o trabalho](/intune-user-help/use-managed-devices-to-get-work-done.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início Rápido: Configurar um tamanho de senha obrigatório para dispositivos Android](quickstart-set-password-length-android.md)