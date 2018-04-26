---
title: Integração de controle de acesso de rede com o Microsoft Intune – Azure | Microsoft Docs
description: Soluções de NAC (controle de acesso) à rede verificam o registro e a conformidade para dispositivos com o Intune. NAC inclui determinados comportamentos e funciona com acesso condicional. Veja as etapas para integração e obtenha uma lista de soluções de parceiros.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf796afcfc42f2cdf778713f4dceadb2597a12e2
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integração de NAC (controle de acesso de rede) com o Intune

O Intune se integra com os parceiros de controle de acesso de rede para ajudar as organizações a proteger dados corporativos quando os dispositivos tentam acessar os recursos locais.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Como soluções do Intune e de NAC ajudam a proteger os recursos de sua organização?

Soluções NAC verificam o registro do dispositivo e o estado de conformidade com o Intune para tomar decisões de controle de acesso. Se o dispositivo não estiver registrado ou se estiver registrado e não for compatível com políticas de conformidade do dispositivo do Intune, o dispositivo deverá ser redirecionado para o Intune para registro e/ou verificação de conformidade do dispositivo.

### <a name="example"></a>Exemplo

Se o dispositivo for registrado e estiver em conformidade com o Intune, a solução NAC deverá permitir que o dispositivo acesse os recursos corporativos. Por exemplo, o acesso dos usuários pode ser permitido ou negado ao tentar acessar os recursos de VPN ou Wi-Fi corporativo.

## <a name="feature-behaviors"></a>Comportamentos do recurso

Dispositivos que estão realizando sincronizações ativamente com o Intune não podem mudar de **Em conformidade** / **Não em conformidade** para **Não Sincronizado** (ou **Desconhecido**). O estado **Desconhecido** é reservado para dispositivos recém-registrados que ainda não foram avaliados quanto à conformidade.

Para dispositivos com acesso bloqueado aos recursos, o serviço responsável pelo bloqueio deve redirecionar todos os usuários para o [portal de gerenciamento](https://portal.manage.microsoft.com) a fim de determinar por que o dispositivo está bloqueado.  Se os usuários visitarem essa página, seus dispositivos serão reavaliados sincronicamente para fins de conformidade.

## <a name="nac-and-conditional-access"></a>NAC e acesso condicional

O NAC trabalha junto com o acesso condicional para fornecer decisões de controle de acesso. Para obter mais detalhes, consulte [Maneiras comuns de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Como funciona a integração de NAC

A lista a seguir é uma visão geral sobre como funciona a integração de NAC quando integrada ao Intune. As três primeiras etapas, 1 a 3, explicam o processo de integração. Depois que a solução de NAC estiver integrada ao Intune, as etapas 4 a 9 descrevem a operação em andamento.

![Como o NAC funciona com o Intune](./media/ca-intune-common-ways-2.png)

1. Registre a solução de parceiro NAC com o AAD (Azure Active Directory) e conceda permissões delegadas para a API de NAC do Intune.
2. Configure a solução de parceiro NAC com as configurações adequadas, incluindo a URL de descoberta do Intune.
3. Configure a solução de parceiro NAC para autenticação de certificado.
4. O usuário se conecta ao ponto de acesso Wi-Fi corporativo ou faz uma solicitação de conexão VPN.
5. A solução de parceiro NAC encaminha as informações do dispositivo para o Intune e pergunta ao Intune quais são os estados de conformidade e de registro do dispositivo.
6. Se o dispositivo não estiver em conformidade ou não estiver registrado, a solução de parceiro NAC instrui o usuário a registrá-lo ou corrigir a conformidade do dispositivo.
7. O dispositivo tenta verificar novamente a conformidade e/ou o estado do registro.
8. Quando o dispositivo estiver registrado e em conformidade, a solução de parceiro NAC obtém o estado do Intune.
9. A conexão é estabelecida com êxito, permitindo que o dispositivo acesse os recursos corporativos.

## <a name="next-steps"></a>Próximas etapas

- [Integrar o Cisco ISE com o Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Integrar o Citrix NetScaler com o Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Integrar o HP Aruba Clear Pass com o Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
- [Integrar o secRMM (Gerenciador de Mídia Removível de segurança Squadra) ao Intune](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)