---
title: Decisões de tecnologia para BYOD com EMS
description: Principais decisões de tecnologia para habilitar BYOD e proteger dados corporativos com o Microsoft Enterprise Mobility + Security.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/8/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.openlocfilehash: 0a080660fcc1b285e0ed00b76a94c2f0cc1ba40a
ms.sourcegitcommit: c78923b0d5b320322c828b1bbea2deb9062e30d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37844956"
---
# <a name="technology-decisions-for-enabling-byod-with-microsoft-enterprise-mobility--security-ems"></a>Decisões de tecnologia para habilitar BYOD com Microsoft Enterprise Mobility + Security (EMS)

À medida que você desenvolve sua estratégia para permitir que os funcionários trabalhem remotamente em seus próprios dispositivos (BYOD), você precisa tomar decisões importantes nos cenários para habilitar BYOD e proteger seus dados corporativos. Felizmente, o EMS oferece todos os recursos de que você precisa em um abrangente conjunto de soluções.  

Neste tópico, podemos examinar o caso de uso simples de habilitar o acesso BYOD ao email corporativo. Vamos nos concentrar em se você precisa ou não gerenciar todo o dispositivo ou apenas os aplicativos, sendo ambas opções completamente válidas.

## <a name="assumptions"></a>Suposições
* Você tem um conhecimento básico de Azure Active Directory e do Microsoft Intune
* Suas contas de email são hospedadas no Exchange Online

## <a name="common-reasons-to-manage-the-device-mdm"></a>Motivos comuns para gerenciar o dispositivo (MDM)
Você pode facilmente orientar os usuários a registrar seus dispositivos no gerenciamento de dispositivo implantando uma política de [acesso condicional](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) no Exchange Online. Aqui estão as razões pelas quais talvez você queira gerenciar dispositivos pessoais:

**Wi-Fi/VPN** – se os usuários precisarem ter um perfil de conectividade corporativa para serem produtivos, isso poderá ser facilmente configurado.

**Aplicativos** – se os usuários precisarem que um conjunto de aplicativos seja enviado ao dispositivo, eles poderão ser entregues facilmente. Isso inclui aplicativos que você pode precisar para fins de segurança, como um aplicativo de Proteção contra Ameaças Móveis.

**Conformidade** – algumas organizações precisam estar em conformidade políticas regulatórias ou outras que chamem controles MDM específicos. Por exemplo, você precisa do MDM para criptografar todo o dispositivo ou para produzir um relatório de todos os aplicativos no dispositivo.

## <a name="common-reasons-to-only-manage-the-apps-mam"></a>Motivos comuns para gerenciar apenas os aplicativos (MAM)
MAM sem MDM é muito popular para organizações que dão suporte a BYOD. Você pode orientar os usuários a acessar o email do Outlook Mobile (que dá suporte para proteções MAM) ao implantar uma política de acesso condicional no Exchange Online. Aqui estão as razões pelas quais você talvez queira apenas gerenciar aplicativos em dispositivos pessoais:

**Experiência do usuário** – o registro de MDM inclui muitos avisos (impostos pela plataforma) que geralmente resultam em o usuário decidir que afinal preferiria não acessar seus emails no seu dispositivo pessoal. MAM é muito menos alarmante aos usuários, uma vez que eles simplesmente recebem um pop-up uma vez para serem informados de que as proteções MAM estão em vigor.

**Conformidade** – algumas organizações precisam estar em conformidade com as políticas que exigem menos recursos de gerenciamento de dispositivos pessoais. Por exemplo, MAM só é capaz de remover dados corporativos dos aplicativos, diferente do MDM, que é capaz de remover todos os dados do dispositivo.

![Dispositivo de comparação de imagem e gerenciamento de aplicativo em dispositivos móveis](./media/byod-app-device-mgmt.png)

Saiba mais sobre [ciclos de vida de gerenciamento de aplicativo e gerenciamento dispositivo](introduction-device-app-lifecycles.md).

## <a name="mdm-vs-mam-capability-comparison"></a>Comparação de funcionalidades do MDM vs. MAM
Como já mencionado, o acesso condicional pode conduzir um usuário na inscrição do seu dispositivo ou no uso de aplicativo gerenciado, como Outlook Mobile. Muitas outras condições podem ser aplicadas a ambos os casos, incluindo:

* Qual o usuário está tentando o acesso
* Se o local é confiável ou não confiável
*   Nível de risco de conexão
* Plataforma do dispositivo

Ainda assim, muitas organizações costumam ter riscos específicos com os quais estão preocupadas.  A tabela a seguir lista as preocupações comuns e a resposta do MAM vs. do MDM para elas.

| Preocupação   |   MDM  |   MAM  |
|------------|--------|--------|
|Acesso a dados não autorizado | Requer associação de grupo | Requer associação de grupo |
|Acesso a dados não autorizado | Requer registro do dispositivo | Requer aplicativo protegido |
|Acesso a dados não autorizado | Requer local específico | Requer local específico |
| | | |
|Conta de usuário comprometida| Exigir MFA | Exigir MFA|
|Conta de usuário comprometida | Bloquear usuários de alto risco | Bloquear usuários de alto risco |
|Conta de usuário comprometida | PIN do dispositivo | PIN do aplicativo |
| | | |
| Aplicativo ou dispositivo comprometido | Requer um dispositivo em conformidade | Verificação de jailbreak na inicialização do aplicativo |
| Aplicativo ou dispositivo comprometido | Criptografar dados do dispositivo | Criptografar dados do aplicativo |
| | | |
|Dispositivo perdido ou roubado | Remover todos os dados do dispositivo | Remover todos os dados do aplicativo|
| | | |
| Compartilhamento ou salvamento acidental de dados em locais não protegidos | Restringir os backups de dados do dispositivo | Restringir recortar/copiar/colar|
| Compartilhamento ou salvamento acidental de dados em locais não protegidos | Restringir salvar-como | Restringir salvar-como |
|Compartilhamento ou salvamento acidental de dados em locais não protegidos | Desabilitar a impressão | N/D|

## <a name="next-steps"></a>Próximas etapas
Agora é hora de decidir se você pretende habilitar BYOD em sua organização focando em gerenciamento de dispositivos, gerenciamento de aplicativo ou uma combinação dos dois. A opção de implementação é sua e você pode ter certeza de que os recursos de identidade e de segurança disponíveis com o Azure AD ficarão disponíveis não importa qual você escolher.  

Use o [Guia de Planejamento](planning-guide.md) do Intune para mapear ao próximo nível de planejamento.
