---
# required metadata

title: Registrar dispositivos iOS corporativos no Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos iOS corporativos no Microsoft Intune
O Microsoft Intune dá suporte ao registro de dispositivos iOS corporativos usando o DEP (Programa de Registro do Dispositivo) da Apple ou a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) executada em um computador Mac.

Você pode registrar dispositivos iOS com registro corporativo de três maneiras:

-   **Configurar o assistente de registro** – Redefine o dispositivo para os padrões de fábrica e o prepara para a instalação do novo usuário do dispositivo. Esse método requer que o administrador de USB conecte o dispositivo iOS a um computador Mac executando o Apple Configurator para pré-configurar o registro. Os dispositivos são, então, entregues aos usuários que executam o processo do Assistente de configuração, configurando o dispositivo com suas credenciais corporativas ou de estudante e concluindo o processo de registro. [Registrar dispositivos iOS usando o Apple Configurator e Assistente de configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Registro direto** – Cria um arquivo compatível com Apple Configurator para uso durante a preparação do dispositivo. O dispositivo registrado não recebe redefinição de fábrica, mas não fica associado a nenhum usuário. Esse método requer que o administrador de USB conecte o dispositivo iOS a um computador Mac executando o Apple Configurator para registrar o dispositivo. [Registrar dispositivos iOS usando o registro direto do Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **DEP(Programa de Registro do Dispositivo)** – Implanta um perfil de registro sem fio em dispositivos comprados através do Programa de Registro de Dispositivo da Apple. Quando o usuário executa o Assistente de configuração do dispositivo, o dispositivo é registrado no Intune.  Registros de dispositivos feitos pelo DEP não podem ser desfeitos pelos usuários. [Registrar dispositivos iOS no Programa de Registro de Dispositivos](ios-device-enrollment-program-in-microsoft-intune.md)




### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


