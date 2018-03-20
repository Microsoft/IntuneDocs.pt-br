---
title: Conector do Skycure com o Microsoft Intune
titlesuffix: 
description: "Saiba como integrar o Intune à MTD (Defesa contra Ameaças Móveis) do Skycure para controlar o acesso de dispositivos móveis aos recursos corporativos."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b3148a24b077dfd491ce06fcf708a81de7d12dc1
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Conector de Defesa contra Ameaças Móveis do Skycure

É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:

-   Defesa física

-   Defesa de rede

-   Defesa do aplicativo

-   Defesa de vulnerabilidades

Você pode configurar políticas de acesso condicional com base na avaliação de risco do Skycure, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos, com base nas ameaças detectadas.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Como o Intune e o Skycure ajudam a proteger os recursos da empresa?

O aplicativo móvel do Skycure para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Skycure para avaliar o risco do dispositivo a ameaças móveis.

A política de conformidade do dispositivo do Intune inclui uma regra para a Defesa contra Ameaças Móveis do Skycure, que se baseia na avaliação de risco do Skycure. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

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

![Aplicativos mal-intencionados detectados](./media/skycure-arch-1.png)

**Concessão do acesso após a correção:**

![Acesso concedido após a correção depois de detectar aplicativos mal-intencionados](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](./media/skycure-arch-3.png)

**Concessão do acesso após a correção:**

![Acesso concedido após a correção](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/skycure-arch-5.png)

**Concessão do acesso após a correção:**

![Acesso concedido após correção para exemplo do Sharepoint](./media/skycure-arch-6.png)

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

- [Configurar a integração do Skycure com o Intune](skycure-mtd-connector-integration.md)

- [Adicionar e atribuir os aplicativos Skycure, o Microsoft Authenticator e a política de configuração do iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Criar uma política de conformidade do dispositivo do Skycure com o Intune](mtd-device-compliance-policy-create.md)

- [Habilitar o conector MTD do Skycure no Intune](mtd-connector-enable.md)
