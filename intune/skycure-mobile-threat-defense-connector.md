---
title: Conector do Symantec com o Microsoft Intune | Microsoft Intune
description: Saiba mais sobre como integrar o Intune ao Symantec Endpoint Protection Mobile para controlar o acesso a dispositivo móvel para seus recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/09/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 468988ca3d87d98ecc5a9a8201b8e3d14c4e1331
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235422"
---
# <a name="symantec-endpoint-protection-mobile-connector"></a>Conector do Symantec Endpoint Protection Mobile

É possível controlar o acesso de dispositivo móvel a recursos corporativos usando o acesso condicional baseado na avaliação de risco realizada pelo SEP Mobile (Symantec Endpoint Protection Mobile), uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos que executam o SEP Mobile, incluindo:

-   Defesa física

-   Defesa de rede

-   Defesa do aplicativo

-   Defesa de vulnerabilidades

É possível habilitar a avaliação de risco do SEP Mobile por meio de políticas de conformidade do dispositivo Intune e, em seguida, usar políticas de acesso condicional para permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base em ameaças detectadas.

## <a name="how-do-intune-and-sep-mobile-help-protect-your-company-resources"></a>Como o Intune e o SEP Mobile ajudam a proteger os recursos da empresa?

O aplicativo SEP Mobile para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Symantec para avaliar o risco do dispositivo a ameaças móveis.

A política de conformidade do dispositivo Intune inclui uma regra para dispositivos SEP Mobile, que se baseia na avaliação de risco do SEP Mobile. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Se o dispositivo for considerado não compatível, o acesso a recursos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários com dispositivos bloqueados recebem orientação do aplicativo SEP Mobile para resolver o problema e recuperar o acesso aos recursos corporativos.

O Intune dá suporte a dois modos de integração com o SEP Mobile:

-   **Configuração básica**, que é um modo somente leitura que permite a visibilidade do SEP Mobile para dispositivos no Intune.

-   **Integração total**, que permite ao SEP Mobile relatar detalhes dos incidentes de risco e segurança do dispositivo no Intune.

## <a name="sample-scenarios"></a>Cenários de exemplo

Confira alguns cenários comuns:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados

Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:

-   Conectar-se ao email corporativo

-   Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

-   Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Imagem conceitual de aplicativos mal-intencionados detectados](./media/symantec-arch-1.png)

**Concessão do acesso após a correção:**

![Imagem de Acesso concedido após a correção devido à detecção de aplicativos mal-intencionados](./media/symantec-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](./media/symantec-arch-3.png)

**Concessão do acesso após a correção:**

![Acesso concedido após a correção](./media/symantec-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/symantec-arch-5.png)

**Concessão do acesso após a correção:**

![Acesso concedido após correção para exemplo do Sharepoint](./media/symantec-arch-6.png)

## <a name="supported-platforms"></a>Plataformas com Suporte

-   **Android 4.1 e posterior**

-   **iOS 8 e posterior**

## <a name="pre-requisites"></a>Pré-requisitos

-   Azure Active Directory Premium

-   Assinatura do Microsoft Intune

-   Assinatura do Symantec Endpoint Protection Mobile

Para obter mais informações, consulte o [site da Symantec](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Próximas etapas

Estas são as etapas que precisam ser concluídas para integrar o Intune ao SEP Mobile:

- [Configurar a integração do SEP Mobile ao Intune](skycure-mtd-connector-integration.md)

- [Adicionar e atribuir os aplicativos SEP Mobile, o Microsoft Authenticator e a política de configuração do iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Criar uma política de conformidade do dispositivo SEP Mobile com o Intune](mtd-device-compliance-policy-create.md)

- [Habilitar o conector MTD do SEP Mobile no Intune](mtd-connector-enable.md)
