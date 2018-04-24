---
title: Conector da defesa contra ameaças móveis do Skycure
description: Proteja o acesso aos recursos da empresa com base no risco do dispositivo, da rede e do aplicativo usando o conector de Defesa contra Ameaças Móveis do Skycure e o Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f79e793ec6931d6497c6b66eee98aea39786e962
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Conector de Defesa contra Ameaças Móveis do Skycure

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:

-   Defesa física

-   Defesa de rede

-   Defesa do aplicativo

-   Defesa de vulnerabilidades

Você pode configurar políticas de acesso condicional com base na avaliação de risco do Skycure, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos, com base nas ameaças detectadas.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Como o Intune e o Skycure ajudam a proteger os recursos da empresa?

O aplicativo móvel do Skycure para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Skycure para avaliar o risco do dispositivo a ameaças móveis.

A política de conformidade do dispositivo do Intune inclui uma regra para defesa contra ameaças móveis do Skycure, que tem base na avaliação de risco do Skycure. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Se o dispositivo for considerado não compatível, o acesso a recursos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários com dispositivos bloqueados recebem orientação do aplicativo móvel do Skycure para resolver o problema e recuperar o acesso aos recursos corporativos.

O Intune dá suporte a dois modos de integração com o Skycure:

-   **Configuração básica**, que é um modo somente leitura que permite a visibilidade do Skycure para dispositivos no Intune.

-   **Integração total**, que permite ao Skycure relatar detalhes dos incidentes de risco e segurança do dispositivo no Intune.

## <a name="sample-scenarios"></a>Cenários de exemplo

Confira alguns cenários comuns:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados

Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:

-   Conectar-se ao email corporativo

-   Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

-   Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Aplicativos mal-intencionados detectados](../media/mtp/skycure-arch-1.png)

**Concessão do acesso após a correção:**

![Acesso concedido a aplicativos mal-intencionados detectado](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](../media/mtp/skycure-arch-3.png)

**Concessão do acesso após a correção:**

![Acesso concedido após a correção](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](../media/mtp/skycure-arch-5.png)

**Concessão do acesso após a correção:**

![Acesso concedido após correção para exemplo do Sharepoint](../media/mtp/skycure-arch-6.png)

## <a name="supported-platforms"></a>Plataformas com Suporte

-   **Android 4.1 e posterior**

-   **iOS 8 e posterior**

## <a name="pre-requisites"></a>Pré-requisitos

-   Azure Active Directory Premium

-   Assinatura do Microsoft Intune

-   Assinatura da Defesa contra Ameaças Móveis do Skycure

Para saber mais, veja o [site do Skycure](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Próximas etapas

Estas são as etapas que precisam ser concluídas para integrar o Intune ao Skycure:

1.  [Configurar o Skycure para usar o SS (Logon Único) do Azure Active Directory](/intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Baixar política de configuração de aplicativo iOS do Skycure](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Adicionar os aplicativos Skycure, o Microsoft Authenticator e a política de configuração do iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Implantar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [Configurar a integração do Skycure com o Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure no Intune](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
