---
# required metadata

title: Cancelar o registro de dispositivo do Intune se você recusou os Termos de Uso | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Cancelar o registro de dispositivo do Intune se você recusou os Termos de Uso

A melhor maneira de cancelar o registro do seu dispositivo Android é aceitar os Termos de Uso, entrar no aplicativo Portal da Empresa e, em seguida, usar [estas instruções](unenroll-your-device-from-intune-android.md) para cancelar o registro. No entanto, se você recusou os Termos de Uso ao tentar entrar no aplicativo Portal da Empresa, você será impedido de entrar no aplicativo Portal da Empresa em tentativas futuras. Portanto, você precisa usar essas instruções de "solução alternativa" para cancelar o registro de seu dispositivo.

Quando você desinstala o aplicativo Portal da Empresa, você está também cancelamento o registro do seu dispositivo no Intune, o que significa que o dispositivo não poderá acessar os recursos da empresa.  Para obter mais informações sobre o que acontece quando você cancela o registro, confira [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md) (O que acontece quando você cancela o registro do seu dispositivo do Intune?).

Antes de desinstalar o aplicativo Portal da Empresa, você precisa acessar a configuração **Administradores do Dispositivo** e desligar **Portal da Empresa**. As etapas podem diferir um pouco, dependendo de qual dispositivo Android você tem.

Para cancelar o registro do seu dispositivo do Intune e desinstalar o aplicativo Portal da Empresa:

1.  Vá para **Configurações** &gt; **Segurança &amp; Bloqueio de Tela** &gt; **Administradores do dispositivo**.

    A conclusão desta etapa cancela imediatamente o registro de seu dispositivo.

2.  Desmarque a caixa de seleção ao lado ou desligue o **Portal da Empresa**.

    Agora você pode desinstalar o aplicativo Portal da Empresa.

Ainda precisa de ajuda? Entre em contato com seu administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).

### Consulte também
[Usando seu dispositivo Android com o Intune](using-your-android-device-with-intune.md)

<!--HONumber=Jun16_HO2-->


