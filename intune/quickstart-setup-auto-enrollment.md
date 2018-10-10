---
title: Início Rápido – Configurar o registro automático no Intune
description: Início Rápido – Configurar o registro automático para dispositivos Windows 10 no Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 3b713f090fb6ada884a269e286f55f6e1b1087c4
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581507"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Início Rápido: configurar o registro automático para dispositivos Windows 10

Neste Início Rápido, você configurará o Microsoft Intune para registrar automaticamente os dispositivos quando usuários específicos entrarem com dispositivos Windows 10.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir este início rápido, é preciso primeiro [criar um usuário](quickstart-create-user.md) e [criar um grupo](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune.

## <a name="set-up-windows-10-automatic-enrollment"></a>Configurar o registro automático do Windows 10

Neste exemplo, você usará o registro de MDM para que dispositivos corporativos e traga seu próprio dispositivo podem ser registrados automaticamente.

1. No Azure, escolha o **Azure Active Directory** > **Mobility (MDM e MAM)** > **Microsoft Intune** > **Alguns**.
![Navegador](media/quickstart-setup-auto-enrollment/setup-automatic-enrollment-win10.png)
2. Escolha **Selecionar grupos** > **Testadores Contoso** > **Selecione**.
3. Use os valores padrão para as seguintes URLs:
    - URL dos termos de uso do MDM
    - URL de descoberta do MDM
    - URL da conformidade do MDM
4. Selecione **Salvar**.
5. Entrar como um usuário do grupo em um dispositivo do Windows 10 e siga os prompts.

## <a name="clean-up-resources"></a>Limpar os recursos

Para reconfigurar o registro automático do Intune, confira [Configurar o registro para dispositivos Windows](windows-enroll.md).

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você aprendeu como configurar o registro automático para dispositivos Windows 10. Saiba sobre as outras maneiras de registrar dispositivos em todas as plataformas.

> [!div class="nextstepaction"]
> [Artigo O que é o registro de dispositivo?](device-enrollment.md)