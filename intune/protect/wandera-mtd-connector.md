---
title: Configurar a Segurança Móvel do Wandera com o Intune
titleSuffix: Intune on Azure
description: Como configurar a Segurança Móvel do Wandera com o Microsoft Intune para controlar o acesso de dispositivos móveis a seus recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7cc63be3c7c536cba67ef92288c12cc4032ae200
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508809"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Conector de Defesa contra Ameaças Móveis Wandera com o Intune  

Controle o acesso de dispositivos móveis a recursos corporativos, usando o acesso condicional com base na avaliação de risco realizada pelo Wandera. Wandera é uma solução de MTD (Defesa contra Ameaças Móveis) que se integra ao Microsoft Intune.  O risco é avaliado com base na telemetria coletada dos dispositivos pelo serviço Wandera, incluindo:
- Vulnerabilidades do sistema operacional
- Aplicativos mal-intencionados instalados
- Perfis de rede mal-intencionados
- Cryptojacking

Configure políticas de *acesso condicional* com base na avaliação de risco do Wandera, habilitada por meio das políticas de conformidade de dispositivo do Intune. A política de avaliação de risco pode permitir ou bloquear o acesso de dispositivos fora de conformidade aos recursos corporativos com base nas ameaças detectadas.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Como o Intune e a Defesa contra Ameaças Móveis Wandera ajudam a proteger os recursos da sua empresa?  

O aplicativo móvel do Wandera é instalado perfeitamente usando o Microsoft Intune. Ele captura o sistema de arquivos, a pilha da rede e a telemetria de dispositivos e aplicativos (quando disponível). Essas informações são sincronizadas com o serviço de nuvem Wandera para avaliar o risco de ameaças móveis no dispositivo. Essas classificações de nível de risco são configuráveis ​​para atender às suas necessidades no console do Wandera, o RADAR.

A política de conformidade no Intune inclui uma regra para a MTD com base na avaliação de risco do Wandera. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Para dispositivos que não estão em conformidade, o acesso a recursos como o Office 365 pode ser bloqueado. Os usuários em dispositivos bloqueados recebem orientação do aplicativo do Wandera para resolver o problema e recuperar o acesso.

## <a name="supported-platforms"></a>Plataformas com Suporte  

Há suporte para as seguintes plataformas no Wandera quando registradas no Intune:

- Android 5.0 e posterior  
- iOS 10.2 e posterior  

Para obter mais informações sobre plataforma e dispositivo, confira o [site do Wandera](https://www.wandera.com/why-wandera/features/device-support/).

## <a name="prerequisites"></a>Pré-requisitos  

- Assinatura do Microsoft Intune  
- Active Directory do Azure  
- Defesa contra Ameaças Móveis Wandera (anteriormente, Wandera Secure)  

Para obter mais informações, confira [Segurança Móvel do Wandera](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Cenários de exemplo

Estes são os cenários comuns ao usar a MTD Wandera com o Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados  

Quando aplicativos mal-intencionados, como malware, são detectados em dispositivos, você pode bloquear dispositivos de ferramentas comuns até que possa resolver a ameaça. Blocos comuns incluem:  
- Conectar-se ao email corporativo  
- Sincronizar arquivos corporativos com o aplicativo OneDrive for Work  
- Acessar aplicativos da empresa  

**Bloquear quando aplicativos mal-intencionados forem detectados**:

![Imagem conceitual de aplicativos mal-intencionados detectados](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Acesso concedido após a correção**: 

![Imagem conceitual do acesso concedido após a correção](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede  

Detecte ameaças à sua rede, como ataques man-in-the-middle, e proteja o acesso a redes Wi-Fi com base no risco do dispositivo.  

**Bloqueie o acesso à rede por meio de Wi-Fi**:  

![Bloquear o acesso à rede por meio de Wi-Fi](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Acesso concedido após a correção**:  

![Acesso concedido após a correção](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloqueie o SharePoint Online quando ameaças à rede forem detectadas**:  

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Acesso concedido após a correção**:  

![Acesso concedido após correção para exemplo do SharePoint](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Próximas etapas

- [Integrar Wandera com o Intune](wandera-mtd-connector-integration.md)
- [Configurar aplicativos Wandera](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Criar uma política de conformidade do dispositivo Wandera](mtd-device-compliance-policy-create.md)
- [Habilitar o conector MTD Wandera](mtd-connector-enable.md)