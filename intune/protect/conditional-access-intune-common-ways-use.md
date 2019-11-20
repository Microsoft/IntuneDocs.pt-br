---
title: Cenários de Acesso Condicional
titleSuffix: Microsoft Intune
description: Saiba como o Acesso Condicional do Intune geralmente é usado para Acesso Condicional baseado em aplicativo e em dispositivo.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b9795ca8a585fd926cc269d493760b37aa7666eb
ms.sourcegitcommit: f46df983b66845bea24a90aaa2ac6cace16b9b0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051973"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Quais são as maneiras comuns de usar o Acesso Condicional com o Intune?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]


Há dois tipos de acesso condicional com o Intune: acesso condicional baseado em dispositivo e acesso condicional baseado em aplicativo. Você precisa configurar as políticas de conformidade relacionadas para orientar a conformidade de acesso condicional em sua organização. Geralmente usamos o acesso condicional para realizar ações como permitir ou bloquear o acesso ao Exchange, controlar o acesso à rede ou integrar a uma solução de Defesa contra Ameaças Móveis.
 
As informações deste artigo podem ajudá-lo a entender como usar os recursos de conformidade de *dispositivo* móvel do Intune e os recursos de MAM (gerenciamento de *aplicativo* móvel) do Intune. 

> [!NOTE]
> O Acesso Condicional é um recurso do Azure Active Directory incluído com uma licença do Azure Active Directory Premium. O Intune aprimora esse recurso, adicionando a conformidade de dispositivo móvel e o gerenciamento de aplicativo móvel à solução. O nó Acesso Condicional acessado no *Intune* é o mesmo nó que o acessado no *Azure AD*.  

## <a name="device-based-conditional-access"></a>Acesso Condicional baseado no dispositivo

O Intune e o Azure Active Directory trabalham juntos para garantir que somente dispositivos gerenciados e em conformidade possam acessar o email, os serviços do Office 365, aplicativos SaaS (Software como serviço) e [aplicativos locais](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Além disso, você pode definir uma política no Azure Active Directory para permitir que somente os computadores que ingressaram no domínio ou os dispositivos móveis que foram registrados no Intune acessem os serviços do Office 365.

O Intune fornece funcionalidades de política de conformidade do dispositivo que avaliam o status de conformidade dos dispositivos. O status da conformidade é relatado ao Azure Active Directory que usa isso para impor a política de Acesso Condicional criada no Azure Active Directory quando o usuário tenta acessar os recursos da empresa.

As políticas de Acesso condicional baseado no dispositivo para o Exchange Online e outros produtos do Office 365 são configuradas por meio do [portal do Azure](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).  

- Saiba mais sobre como [Exigir dispositivos gerenciados com Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/require-managed-devices).

- Saiba mais sobre [Conformidade de dispositivo do Intune](device-compliance-get-started.md).

- Saiba mais sobre [Navegadores compatíveis com o Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#supported-browsers).

> [!NOTE]
> Em dispositivos Android, ao habilitar o Acesso Baseado em dispositivo para o SharePoint Online ou o acesso baseado em navegador para o Exchange Online, os usuários precisam habilitar a opção **Habilitar o Acesso do Navegador** no dispositivo registrado, da seguinte maneira:
> 1. Inicie o **aplicativo do Portal da Empresa**.
> 2. Vá para a página **Configurações** por meio dos três pontos (...) ou do botão de menu do hardware.
> 3. Pressione o botão **Habilitar o Acesso do Navegador** . 
> 4. No navegador Chrome, saia do Office 365 e reinicie o Chrome.

### <a name="conditional-access-based-on-network-access-control"></a>Acesso condicional baseado em controle de acesso à rede

O Intune integra-se a parceiros, como Cisco ISE, Aruba Clear Pass e Citrix NetScaler, para fornecer controles de acesso baseados no registro do Intune e no estado de conformidade do dispositivo.

Os usuários podem ter o acesso permitido ou negado ao tentar acessar os recursos corporativos de Wi-Fi ou VPN, dependendo se o dispositivo é gerenciado e está em conformidade com as políticas de conformidade do dispositivo do Intune.

- Saiba mais sobre a [integração de NAC com o Intune](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Acesso condicional baseado nos riscos do dispositivo

O Intune firma uma parceria com fornecedores de Defesa contra Ameaças Móveis, que fornecem uma solução de segurança para detectar malware, cavalos de Troia e outras ameaças em dispositivos móveis.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Como funciona a integração entre o Intune e a Defesa contra Ameaças Móveis

Quando os dispositivos móveis têm o agente de Defesa contra Ameaças Móveis instalado, o agente envia mensagens sobre o estado de conformidade novamente para o Intune, relatando se há uma ameaça no próprio dispositivo móvel.

A integração entre o Intune e a defesa contra ameaças móveis desempenha um papel importante nas decisões sobre o acesso condicional baseadas nos riscos do dispositivo.

- Saiba mais sobre a [defesa contra ameaças móveis do Intune](mobile-threat-defense.md).

### <a name="conditional-access-for-windows-pcs"></a>Acesso condicional para computadores Windows

O acesso condicional para computadores fornece recursos semelhantes aos disponíveis para dispositivos móveis. Vamos falar sobre as maneiras pelas quais você pode usar o acesso condicional ao gerenciar computadores com o Intune.

#### <a name="corporate-owned"></a>De propriedade corporativa

- **Ingressado no domínio do AD local:** Essa tem sido a opção mais comum para organizações que estão razoavelmente confiantes com o fato de que já estão gerenciando seus computadores por meio de políticas de grupo do AD ou com o System Center Configuration Manager.

- **Ingressado no domínio do Azure AD e gerenciamento do Intune:** Esse cenário destina-se a organizações que desejam estar na nuvem primeiro (ou seja, usam principalmente serviços de nuvem, com o objetivo de reduzir o uso de uma infraestrutura local) ou somente na nuvem (sem infraestrutura local). O ingresso no Azure AD funciona bem em um ambiente híbrido, permitindo o acesso a aplicativos e recursos locais e na nuvem. O dispositivo se une ao Azure AD e é registrado no Intune, que pode ser usado como critério de acesso condicional ao acessar recursos corporativos.

- **Ingressado no domínio do AD e o System Center Configuration Manager:** No branch atual, o System Center Configuration Manager oferece recursos de acesso condicional que podem avaliar critérios específicos de conformidade, além de ser um computador ingressado no domínio:

  - O computador está criptografado?

  - O antimalware está instalado? Ele está atualizado?

  - O dispositivo está desbloqueado ou com raiz?

#### <a name="bring-your-own-device-byod"></a>BYOD (Traga seu próprio dispositivo)

- **Ingresso no local de trabalho e gerenciamento do Intune:** o usuário pode ingressar seus dispositivos pessoais para acessar recursos e serviços corporativos. Você pode usar o recurso Workplace Join e registrar dispositivos no MDM do Intune para receber políticas no nível de dispositivo, que são outras opções para avaliar os critérios de acesso condicional.

Saiba mais sobre [Gerenciamento de dispositivos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/overview).

## <a name="app-based-conditional-access"></a>Acesso condicional baseado no aplicativo

O Intune e o Azure Active Directory funcionam em conjunto para garantir que somente aplicativos gerenciados podem acessar o email corporativo ou outros serviços do Office 365.

- Saiba mais sobre o [acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md).

### <a name="intune-conditional-access-for-exchange-on-premises"></a>Acesso condicional do Intune para o Exchange local

O acesso condicional pode ser usado para permitir ou bloquear o acesso ao **Exchange Local** com base no estado do registro e nas políticas de conformidade do dispositivo. Quando o acesso condicional é usado em combinação com uma política de conformidade do dispositivo, somente os dispositivos em conformidade podem acessar o Exchange Local.

Defina configurações avançadas no acesso condicional para um controle mais granular, como:

- Permitir ou bloquear algumas plataformas.

- Bloquear imediatamente dispositivos que não são gerenciados pelo Intune.

Qualquer dispositivo usado para acessar o Exchange Local é verificado quanto à conformidade quando as políticas de conformidade do dispositivo e de acesso condicional são aplicadas.

Quando os dispositivos não atendem às condições definidas, o usuário final é guiado pelo processo de registro do dispositivo para corrigir o problema que está tornando o dispositivo incompatível.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Como funciona o acesso condicional no Exchange Local

O acesso condicional para o Exchange local funciona de maneira diferente das políticas baseadas no Acesso Condicional do Azure. Você instala o Intune Exchange Connector local para interagir diretamente com o servidor Exchange. O Intune Exchange Connector mantém todos os registros do EAS (Exchange Active Sync) que existem no servidor Exchange, de forma que o Intune possa usar esses registros do EAS e mapeá-los para registros de dispositivo do Intune. Esses registros são dispositivos registrados e reconhecidos pelo Intune. Esse processo permite ou bloqueia o acesso a email.

Se o registro do EAS é novo e o Intune não o reconhece, o Intune emite um cmdlet (pronuncia-se "comand-let") que direciona o servidor Exchange para bloquear o acesso ao email. Saiba mais a seguir sobre como esse processo funciona:

![Fluxograma do Exchange Local com AC](./media/conditional-access-intune-common-ways-use/ca-intune-common-ways-1.png)

1. O usuário tenta acessar o email corporativo, que está hospedado no Exchange Local 2010 SP1 ou posterior.

2. Se o dispositivo não é gerenciado pelo Intune, ele tem o acesso ao email bloqueado. O Intune envia uma notificação de bloqueio para o cliente do EAS.

3. O EAS recebe a notificação de bloqueio, move o dispositivo para a quarentena e envia o email de quarentena com etapas de correção que contêm links para que os usuários possam registrar seus dispositivos.

4. Ocorre o processo de Ingresso no local de trabalho, que é a primeira etapa para que o dispositivo seja gerenciado pelo Intune.

5. O dispositivo é registrado no Intune.

6. O Intune mapeia o registro do EAS para um registro de dispositivo e salva o estado de conformidade do dispositivo.

7. A ID do cliente do EAS é registrada pelo processo de Registro de Dispositivo do Azure AD, que cria uma relação entre o registro de dispositivo do Intune e a ID do cliente do EAS.

8. O Registro de Dispositivo do Azure AD salva as informações de estado do dispositivo.

9. Se o usuário atender às políticas de acesso condicional, o Intune emitirá um cmdlet por meio do Intune Exchange Connector que permite a sincronização da caixa de correio.

10. O servidor Exchange envia a notificação ao cliente do EAS, de forma que o usuário possa acessar o email.


#### <a name="whats-the-intune-role"></a>O que é a função do Intune?

O Intune avalia e gerencia o estado do dispositivo.

#### <a name="whats-the-exchange-server-role"></a>O que é a função de servidor Exchange?

O servidor Exchange fornece a API e a infraestrutura para mover os dispositivos para a quarentena.

> [!IMPORTANT]
> Lembre-se de que o usuário que está usando o dispositivo deve ter um perfil de conformidade e uma licença do Intune atribuídos a ele para que o dispositivo possa ser avaliado quanto à conformidade. Se nenhuma política de conformidade for implantada para o usuário, o dispositivo será tratado como em conformidade e nenhuma restrição de acesso será aplicada.

## <a name="next-steps"></a>Próximas etapas

[Como configurar o Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Configurar políticas de acesso condicional baseado em aplicativo](app-based-conditional-access-intune-create.md)

[Como instalar o Exchange Connector local com o Intune](exchange-connector-install.md).

[Como criar uma política de Acesso Condicional para o Exchange Local](conditional-access-exchange-create.md)
