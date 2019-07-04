---
title: Integração de controle de acesso de rede com o Microsoft Intune – Azure | Microsoft Docs
description: Soluções de NAC (controle de acesso) à rede verificam o registro e a conformidade para dispositivos com o Intune. NAC inclui determinados comportamentos e funciona com Acesso Condicional. Veja as etapas para integração e obtenha uma lista de soluções de parceiros.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 400de55e26076a8d612ac31388d5c5daec68d4a0
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67044544"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integração de NAC (controle de acesso de rede) com o Intune

O Intune se integra com os parceiros de controle de acesso de rede para ajudar as organizações a proteger dados corporativos quando os dispositivos tentam acessar os recursos locais.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Como soluções do Intune e de NAC ajudam a proteger os recursos de sua organização?

Soluções NAC verificam o registro do dispositivo e o estado de conformidade com o Intune para tomar decisões de controle de acesso. Se o dispositivo não estiver registrado ou se estiver registrado e não estiver em conformidade com as políticas de conformidade do dispositivo do Intune, ele deverá ser redirecionado para o Intune para registro ou verificação de conformidade do dispositivo.

### <a name="example"></a>Exemplo

Se o dispositivo for registrado e estiver em conformidade com o Intune, a solução NAC deverá permitir que o dispositivo acesse os recursos corporativos. Por exemplo, o acesso dos usuários pode ser permitido ou negado ao tentar acessar os recursos de VPN ou Wi-Fi corporativo.

## <a name="feature-behaviors"></a>Comportamentos do recurso

Dispositivos que estão realizando sincronizações ativamente com o Intune não podem mudar de **Em conformidade** / **Não em conformidade** para **Não Sincronizado** (ou **Desconhecido**). O estado **Desconhecido** é reservado para dispositivos recém-registrados que ainda não foram avaliados quanto à conformidade.

Para dispositivos com acesso bloqueado aos recursos, o serviço responsável pelo bloqueio deve redirecionar todos os usuários para o [portal de gerenciamento](https://portal.manage.microsoft.com) a fim de determinar por que o dispositivo está bloqueado.  Se os usuários visitarem essa página, seus dispositivos serão reavaliados sincronicamente para fins de conformidade.

## <a name="nac-and-conditional-access"></a>NAC e Acesso Condicional

O NAC trabalha junto com o Acesso Condicional para fornecer decisões de controle de acesso. Para obter mais detalhes, confira [Maneiras comuns de usar o Acesso Condicional com o Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Como funciona a integração de NAC

A lista a seguir é uma visão geral sobre como funciona a integração de NAC quando integrada ao Intune. As três primeiras etapas, 1 a 3, explicam o processo de integração. Depois que a solução de NAC estiver integrada ao Intune, as etapas 4 a 9 descrevem a operação em andamento.

![Imagem conceitual de como o NAC funciona com o Intune](./media/ca-intune-common-ways-2.png)

1. Registre a solução de parceiro NAC com o AAD (Azure Active Directory) e conceda permissões delegadas para a API de NAC do Intune.
2. Configure a solução de parceiro NAC com as configurações adequadas, incluindo a URL de descoberta do Intune.
3. Configure a solução de parceiro NAC para autenticação de certificado.
4. O usuário se conecta ao ponto de acesso Wi-Fi corporativo ou faz uma solicitação de conexão VPN.
5. A solução de parceiro NAC encaminha as informações do dispositivo para o Intune e pergunta ao Intune quais são os estados de conformidade e de registro do dispositivo.
6. Se o dispositivo não estiver em conformidade ou não estiver registrado, a solução de parceiro NAC instruirá o usuário a registrá-lo ou consertar a conformidade do dispositivo.
7. O dispositivo tenta verificar novamente sua conformidade e o estado de registro, quando aplicável.
8. Quando o dispositivo estiver registrado e em conformidade, a solução de parceiro NAC obtém o estado do Intune.
9. A conexão é estabelecida com êxito, permitindo que o dispositivo acesse os recursos corporativos.

## <a name="use-nac-for-vpn-on-your-ios-devices"></a>Usar o NAC para VPN em dispositivos iOS  

- O NAC está disponível nas VPNs a seguir, sem habilitar o NAC no perfil de VPN:

  - NAC para Cisco Legacy AnyConnect
  - F5 Access herdado
  - VPN Citrix

- O NAC também está disponível para F5 Access e Citrix SSO. Para habilitar o NAC no SSO da Citrix:

  - Use o Citrix Gateway 12.0.59 ou superior.  
  - Os usuários devem ter o SSO da Citrix 1.1.6 ou superior instalado.
  - [Integrar o NetScaler com o Intune para NAC](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html) como descrito na documentação de produto da Citrix.
  - No perfil de VPN, selecione **Configurações de base** > **Habilitar NAC (Controle de Acesso de Rede)** > selecione **Concordo**.

  A conexão VPN é desconectada por motivos de segurança a cada 24 horas. A VPN pode ser reconectada imediatamente.

- Para habilitar o NAC para F5 Access:

  - Use o F5 BIG-IP 13.1.1.5. O BIG-IP 14 não é compatível.
  - Integre o BIG-IP com o Intune para NAC. O guia da F5 ([Visão geral: como configurar o APM para verificações de situação do dispositivo com sistemas de gerenciamento de ponto de extremidade](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89)) lista as etapas.
  - No perfil de VPN, selecione **Configurações de base** > **Habilitar NAC (Controle de Acesso de Rede)** > selecione **Concordo**.

  A conexão VPN é desconectada por motivos de segurança a cada 24 horas. A VPN pode ser reconectada imediatamente.

- O controle de acesso de rede não é compatível com o seguinte cliente VPN no iOS:
  - Cisco AnyConnect

Estamos trabalhando com nossos parceiros para lançar uma solução NAC para esses clientes mais novos. Quando soluções estiverem prontas, este artigo será atualizado com informações adicionais.

## <a name="next-steps"></a>Próximas etapas

- [Integrar o Cisco ISE com o Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Integrar o Citrix NetScaler com o Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Integrar o Gerenciador de Política de Acesso de BIG-IP da F5 com o Intune](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-13-0-0/6.html)
- [Integrar o HP Aruba ClearPass ao Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=31271)
- [Integrar o secRMM (Gerenciador de Mídia Removível de segurança Squadra) ao Intune](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)
