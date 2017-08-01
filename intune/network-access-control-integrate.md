---
title: "Integração de controle de acesso de rede com o Intune"
titleSuffix: Intune on Azure
description: "Integração de NAC (controle de acesso de rede) com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6037ec4638b487c0bae8fcecf2d9bd010e3bc59a
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integração de NAC (controle de acesso de rede) com o Intune

O Intune se integra com os parceiros de controle de acesso de rede para ajudar as organizações a proteger dados corporativos quando os dispositivos tentam acessar os recursos locais.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Como soluções do Intune e de NAC ajudam a proteger os recursos de sua organização?

Soluções NAC serão responsáveis por verificar o estado de conformidade e de registro do dispositivo com o Intune para tomar decisões de controle de acesso. Se o dispositivo não estiver registrado ou se estiver registrado e não for compatível com políticas de conformidade do dispositivo do Intune, o dispositivo deve ser redirecionado para o Intune para registro e/ou verificação de conformidade do dispositivo.

### <a name="example"></a>Exemplo

Se o dispositivo for registrado e estiver em conformidade com o Intune, a solução NAC deverá permitir que o dispositivo acesse os recursos corporativos. Por exemplo, o acesso dos usuários pode ser permitido ou negado ao tentar acessar os recursos de VPN ou Wi-Fi corporativo.

## <a name="nac-and-conditional-access"></a>NAC e acesso condicional

O NAC trabalha junto com o acesso condicional para fornecer as decisões de controle de acesso.

- Consulte [maneiras de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md) para obter mais detalhes.

## <a name="how-the-nac-integration-works"></a>Como funciona a integração de NAC

Veja essa visão geral de como a integração de NAC funciona quando integrado com o Intune, as três primeiras etapas explicam o processo de integração. Depois que a solução de NAC é integrada com o Intune, as etapas 4 a 9 descrevem a operação em andamento.

![Como o NAC funciona com o Intune](./media/ca-intune-common-ways-2.png)

1.  Registre a solução de parceiro NAC com o AAD (Azure Active Directory) e conceda permissões delegadas para a API de NAC do Intune.

2.  Configure a solução de parceiro NAC com as configurações adequadas, incluindo a URL de descoberta do Intune.

3.  Configure a solução de parceiro NAC para autenticação de certificado.

4.  O usuário se conecta ao ponto de acesso Wi-Fi corporativo ou faz uma solicitação de conexão VPN.

5.  A solução de parceiro NAC encaminha as informações do dispositivo para o Intune e pergunta ao Intune quais são os estados de conformidade e de registro do dispositivo.

6.  Se o dispositivo não estiver em conformidade ou não estiver registrado, a solução de parceiro NAC instrui o usuário a registrá-lo ou corrigir a conformidade do dispositivo.

7.  O dispositivo tenta verificar novamente a conformidade e/ou o estado do registro.

8.  Quando o dispositivo estiver registrado e em conformidade, a solução de parceiro NAC obtém o estado do Intune.

9.  A conexão é estabelecida com êxito, permitindo que o dispositivo acesse os recursos corporativos.

## <a name="next-steps"></a>Próximas etapas

-   [Integrar o Cisco ISE com o Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Integrar o Citrix NetScaler com o Intune](https://docs.citrix.com/netscaler-gateway/11-1/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Integrar o HP Aruba Clear Pass com o Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
