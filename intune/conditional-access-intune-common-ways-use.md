---
title: Acesso condicional com o Intune
titleSuffix: Intune on Azure
description: Maneiras comuns de usar o acesso condicional com o Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ba1f12d762a6288fc2e7a3bfdae637f8ae13a94
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="common-ways-to-use-conditional-access-with-intune"></a>Maneiras comuns de usar o acesso condicional com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você precisa configurar a política de conformidade do dispositivo móvel do Intune e as funcionalidades de MAM (gerenciamento de aplicativo móvel) do Intune para impor a conformidade do acesso condicional em sua organização. Vamos falar sobre as maneiras comuns de usar o acesso condicional com o Intune.

## <a name="device-based-conditional-access"></a>Acesso condicional baseado no dispositivo

O Intune e o Azure Active Directory trabalham juntos para garantir que somente dispositivos gerenciados e em conformidade têm permissão para acessar o email, os serviços do Office 365, aplicativos SaaS (Software como serviço) e [aplicativos locais](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Além disso, você pode definir uma política no Azure Active Directory para permitir que somente os computadores que ingressaram no domínio ou os dispositivos móveis que foram registrados no Intune acessem os serviços do Office 365.

O Intune fornece funcionalidades de política de conformidade do dispositivo que avaliam o status de conformidade dos dispositivos. O status da conformidade é relatado ao Azure Active Directory, que usa isso para impor a política de acesso condicional criada no Azure Active Directory quando o usuário tenta acessar os recursos da empresa.

Começando no [novo portal do Azure](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), as políticas de acesso condicional baseado no dispositivo para o Exchange Online e outros produtos do Office 365 são configuradas por meio do portal do Azure.

-   Saiba mais sobre o [acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

-   Saiba mais sobre [o que é a conformidade do dispositivo do Intune](device-compliance.md).

-   Saiba mais sobre a [proteção de email, o Office 365 e outros serviços usando o acesso condicional com o Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="conditional-access-for-exchange-on-premises"></a>Acesso condicional para o Exchange Local

O acesso condicional pode ser usado para permitir ou bloquear o acesso ao **Exchange Local** com base no estado do registro e nas políticas de conformidade do dispositivo. Quando o acesso condicional é usado em combinação com uma política de conformidade do dispositivo, somente os dispositivos em conformidade podem acessar o Exchange Local.

Defina configurações avançadas no acesso condicional para um controle mais granular, como:

-   Permitir ou bloquear algumas plataformas.

-   Bloquear imediatamente dispositivos que não são gerenciados pelo Intune.

Qualquer dispositivo usado para acessar o Exchange Local é verificado quanto à conformidade quando as políticas de conformidade do dispositivo e de acesso condicional são aplicadas.

Quando os dispositivos não atendem às condições definidas, o usuário final é guiado pelo processo de registro do dispositivo para corrigir o problema que impede o dispositivo de estar em conformidade.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Como funciona o acesso condicional no Exchange Local

O Intune Exchange Connector mantém todos os registros do EAS (Exchange Active Sync) que existem no servidor Exchange, de forma que o Intune possa usar esses registros do EAS e mapeá-los para registros de dispositivo do Intune. Esses registros são dispositivos registrados e reconhecidos pelo Intune. Esse processo permite ou bloqueia o acesso a email.

Se o registro do EAS for novo e o Intune não o reconhecer, o Intune emitirá um comando let que bloqueia o acesso a email. Estes são mais detalhes sobre como esse processo funciona:

![Fluxograma do Exchange Local com AC](./media/ca-intune-common-ways-1.png)

1.  O usuário tenta acessar o email corporativo, que está hospedado no Exchange Local 2010 SP1 ou posterior.

2.  Se o dispositivo não for gerenciado pelo Intune, ele terá o acesso a email bloqueado. O Intune envia uma notificação de bloqueio para o cliente do EAS.

3.  O EAS recebe a notificação de bloqueio, move o dispositivo para a quarentena e envia o email de quarentena com etapas de correção que contêm links para que os usuários possam registrar seus dispositivos.

4.  Ocorre o processo de Ingresso no local de trabalho, que é a primeira etapa para que o dispositivo seja gerenciado pelo Intune.

5.  O dispositivo é registrado no Intune.

6.  O Intune mapeia o registro do EAS para um registro de dispositivo e salva o estado de conformidade do dispositivo.

7.  A ID do cliente do EAS é registrada pelo processo de Registro de Dispositivo do Azure AD, que cria uma relação entre o registro de dispositivo do Intune e a ID do cliente do EAS.

8.  O Registro de Dispositivo do Azure AD salva as informações de estado do dispositivo.

9.  Se o usuário atender às políticas de acesso condicional, o Intune emitirá um comando let por meio do Intune Exchange Connector que permite a sincronização da caixa de correio.

10. O servidor Exchange envia a notificação ao cliente do EAS, de forma que o usuário possa acessar o email.

#### <a name="whats-the-intune-role"></a>O que é a função do Intune?

O Intune avalia e gerencia o estado do dispositivo.

#### <a name="whats-the-exchange-server-role"></a>O que é a função de servidor Exchange?

O servidor Exchange fornece a API e a infraestrutura para mover os dispositivos para sua quarentena.

> [!IMPORTANT] 
> Lembre-se de que o usuário que está usando o dispositivo deve ter um perfil de conformidade atribuído a ele para que o dispositivo seja avaliado quanto à conformidade. Se nenhuma política de conformidade for implantada para o usuário, o dispositivo será tratado como em conformidade e nenhuma restrição de acesso será aplicada.

### <a name="conditional-access-based-on-network-access-control"></a>Acesso condicional baseado em controle de acesso à rede

O Intune integrado com parceiros, como Cisco ISE, Aruba Clear Pass e Citrix NetScaler, para fornecer controles de acesso baseados no registro do Intune e no estado de conformidade do dispositivo.

Os usuários podem ter o acesso permitido ou negado ao tentar acessar os recursos corporativos de Wi-Fi ou VPN, dependendo se o dispositivo é gerenciado e está em conformidade com as políticas de conformidade do dispositivo do Intune.

-   Saiba mais sobre a [integração de NAC com o Intune](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Acesso condicional baseado nos riscos do dispositivo

O Intune em parceria com fornecedores de Defesa contra Ameaças Móveis, que fornece uma solução de segurança para detectar malwares, cavalos de Troia e outras ameaças em dispositivos móveis.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Como funciona a integração entre o Intune e a defesa contra ameaças móveis

Quando os dispositivos móveis têm o agente de defesa contra ameaças móveis instalado, o agente pode enviar mensagens sobre o estado de conformidade novamente para o Intune, relatando se uma ameaça foi encontrada no próprio dispositivo móvel.

A integração entre o Intune e a defesa contra ameaças móveis desempenha um fator importante nas decisões sobre o acesso condicional baseadas nos riscos do dispositivo.

-   Saiba mais sobre a [defesa contra ameaças móveis do Intune](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).

### <a name="conditional-access-for-windows-pcs"></a>Acesso condicional para computadores Windows

O acesso condicional para computadores fornece funcionalidades semelhantes disponíveis para dispositivos móveis. Vamos falar sobre as maneiras pelas quais você pode usar o acesso condicional ao gerenciar computadores com o Intune.

#### <a name="corporate-owned"></a>De propriedade corporativa

-   **Ingressado no domínio do AD local:** essa tem sido a opção mais comum de implantação de acesso condicional para organizações, que estão razoavelmente confiantes com o fato de que já estão gerenciando seus computadores por meio de políticas de grupo do AD e/ou com o System Center Configuration Manager.

-   **Ingressado no domínio do Azure AD e gerenciamento do Intune:** esse cenário é normalmente voltado para cenários CYOD (Escolha seu próprio dispositivo) e cenários de laptops móveis em que esses dispositivos raramente são conectados à rede corporativa. O dispositivo é ingressado no Azure AD e registrado no Intune, o que remove qualquer dependência do AD local e dos controladores de domínio. Isso pode ser usado como um critério de acesso condicional ao acessar recursos corporativos.

-   **Ingressado no domínio do AD e o System Center Configuration Manager:** no branch atual, o System Center Configuration Manager fornece funcionalidades de acesso condicional que podem avaliar critérios específicos de conformidade, além de ser um computador ingressado no domínio:

    -   O computador está criptografado?

    -   Algum malware está instalado? Ele está atualizado?

    -   O dispositivo está desbloqueado ou com raiz?

#### <a name="bring-your-own-device-byod"></a>BYOD (Traga seu próprio dispositivo)

-   **Ingresso no local de trabalho e gerenciamento do Intune:** com essa opção, o usuário pode ingressar seus dispositivos pessoais para acessar recursos e serviços corporativos. Use o Ingresso no local de trabalho e registre dispositivos no Intune para receber políticas no dispositivo, que também é outra opção para avaliar os critérios de acesso condicional.

## <a name="app-based-conditional-access"></a>Acesso condicional baseado no aplicativo

O Intune e o Azure Active Directory funcionam em conjunto para garantir que somente aplicativos gerenciados podem acessar o email corporativo ou outros serviços do Office 365.

-   Saiba mais sobre o [acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md).

## <a name="next-steps"></a>Próximas etapas

[Como configurar o acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Como instalar o Exchange Connector local com o Intune](https://docs.microsoft.com/intune/exchange-connector-install).

[Como criar uma política de acesso condicional para o Exchange Local](conditional-access-exchange-create.md)