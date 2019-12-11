---
title: Criar o design do Microsoft Intune
titleSuffix: Microsoft Intune
description: Este artigo ajuda você a criar um design para um design e uma implementação somente na nuvem do Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 24f15cb179dfc2b12b642f5f196d04dce58d4377
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505205"
---
# <a name="create-a-design"></a>Criar um design

O design do Intune se baseia nas informações coletadas e nas decisões tomadas ao concluir as outras [seções deste guia](../planning-guide.md). Ele ajuda você a reunir:

- O ambiente atual

- Opções de implantação do Intune

- Requisitos de identidade para dependências externas

- Considerações sobre plataformas de dispositivo

- Requisitos para entrega  

Embora haja requisitos mínimos de infraestrutura local, um plano de design ainda é útil para garantir que você tem a solução de gerenciamento de dispositivo móvel correta, que atende a suas metas, seus objetivos e requisitos.

Vamos examinar cada uma dessas áreas mais detalhadamente. 

## <a name="record-your-current-environment"></a>Registrar o ambiente atual
Além disso, é comum haver alterações de design durante as fases de teste e implementação. Use o plano de design para documentar essas alterações e o raciocínio por trás delas conforme elas ocorrem.

O ambiente atual pode influenciar as decisões de design e deve ser documentado e referenciado ao tomar outras decisões de design do Intune. Veja abaixo alguns exemplos de como registrar o ambiente atual:

- **Identidade na nuvem**

  - Você usa o DirSync ou o Azure AD (Azure Active Directory) Connect?

  - Seu ambiente é federado?

  - A MFA (autenticação multifator) está habilitada?

- **Ambiente de email**

  - Você usa o Exchange? Ele está local ou na nuvem?

  - Você está no meio de um projeto de migração do Exchange para a nuvem?

- **Solução de MDM (gerenciamento de dispositivo móvel) atual**

  - Você está usando outras soluções de MDM?

  - Quais soluções de MDM estão sendo usadas para os cenários de caso de uso corporativo e BYOD?

  - Quais funcionalidades estão sendo usadas (por exemplo, configurações do dispositivo do aplicativo, configurações de Wi-Fi etc.)?

  - Há suporte para quais plataformas de dispositivo?

  - Quais grupos e quantos usuários estão usando a solução de MDM?

- **Solução de certificado**

  - Você implementou uma solução de certificado?

  - Quais tipo de certificados são usados?

- **Gerenciamento de sistemas**

  - Como o ambiente de computador e servidor está sendo gerenciado?

  - O System Center Configuration Manager está sendo usado? Você está usando uma plataforma de gerenciamento do sistema de terceiros?

- **Solução de VPN**

  - Qual é sua solução de VPN?

  - Ela é usada para cenários de caso de uso corporativo e BYOD?

Lembre-se de observar os projetos ou outros planos em vigor que podem afetar o ambiente ao registrar o ambiente atual de MDM. Veja abaixo um exemplo de uma maneira de registrar o ambiente atual ao criar o design do Intune:

| **Área de solução** | **Ambiente atual** | **Comentários** |
|---|---|---|
| **Identidade** | Azure AD, Azure AD Connect, não federado, sem MFA | Projeto em vigor para habilitar o MFA até o final do ano |                 
| **Ambiente de email** | Exchange no Local, Exchange Online | Atualmente migrando do Exchange no Local para o Exchange Online. 75% de caixas de correio migradas. Os últimos 25% serão migrados antes do início do Piloto do Intune. |                
| **SharePoint** | SharePoint local | Não há planos de migração para o SharePoint Online |  
| **MDM atual** | Exchange ActiveSync |  |
| **Solução de certificado** | Microsoft Server 2012 R2, Serviços de Certificados do AD | Usar somente o PKI para Servidores de Site |
| **Gerenciamento do Sistema** | System Center Configuration Manager CB 1606 | Gostaria de investigar a solução híbrida do Intune? |
| **Solução de VPN** | Cisco AnyConnect |  |


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para desenvolver um plano de design do Intune.

## <a name="choose-an-intune-deployment-option"></a>Escolher uma opção de implantação do Intune

O Intune oferece duas opções de implantação: independente e híbrida. Autônomo refere-se ao serviço do Intune em execução na nuvem, enquanto híbrido refere-se à integração do Intune ao System Center Configuration Manager. O objetivo principal deste guia é o uso da opção autônoma. [Decida qual opção atende aos seus requisitos de negócios](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

> [!Important]
>A integração de novos clientes MDM híbridos foi preterida. Para obter mais informações, confira a postagem no blog [Migrar do Gerenciamento de dispositivo móvel híbrido para o Intune no Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150).


## <a name="intune-tenant-location"></a>Local do locatário do Intune

Caso sua organização tenha uma presença global, lembre-se de planejar o local em que o locatário reside ao assinar o serviço. O país/região é definido durante a inscrição para uma assinatura do Intune pela primeira vez e é mapeado para os países/regiões do mundo listadas abaixo:

- América do Norte

- Europa, Oriente Médio e África

- Ásia e Pacífico

>[!IMPORTANT]
> Não é possível alterar o local do país/região e do locatário posteriormente.

## <a name="external-dependencies"></a>Dependências externas

Dependências externas são serviços e produtos separados do Intune, mas que são um requisito do Intune ou que podem ser integradas com o Intune. É importante identificar os requisitos de dependências externas e como configurá-las. Alguns exemplos de dependências externas comuns são:

- Identidade

- Grupos de usuários e de dispositivos

- PKI (infraestrutura de chave pública)

A seguir, exploraremos mais detalhadamente essas dependências externas comuns.

### <a name="identity"></a>Identidade

Identidade é como identificamos nossos usuários que estão abaixo de sua organização e que estão registrando um dispositivo. O Intune exige o Azure AD (Azure Active Directory) como o provedor de identidade do usuário. Se você já usa esse serviço, pode aproveitar sua identidade existente na nuvem. Além disso, o Azure AD Connect é a ferramenta recomendada para sincronizar as identidades de usuários locais com os serviços em nuvem da Microsoft. Caso sua organização já esteja usando o Office 365, é importante que o Intune use o mesmo ambiente do Azure AD.

Saiba mais sobre os seguintes requisitos de identidade do Intune:

- [Requisitos de identidade](https://docs.microsoft.com/azure/active-directory/understand-azure-identity-solutions).

- [Requisitos de sincronização de diretório](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

- [Requisitos da autenticação multifator](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).

### <a name="user-and-device-groups"></a>Grupos de usuários e de dispositivos

Grupos de usuários e de dispositivos determinam o destino de uma implantação, incluindo políticas, aplicativos e perfis. É necessário determinar quais grupos de usuários e de dispositivos serão necessários.

Recomenda-se que todos os grupos sejam criados no Active Directory local e, em seguida, sincronizados com o Azure AD. Saiba mais sobre como planejar e criar os grupos de usuários e de dispositivos:

- [Planejar grupos de usuários e de dispositivos](users-add.md).

- [Criar grupos de usuários e de dispositivos](groups-add.md).

### <a name="public-key-infrastructure-pki"></a>PKI (infraestrutura de chave pública)
A infraestrutura de chave pública fornece certificados para dispositivos ou usuários a fim de autenticar um serviço de forma segura. O Intune dá suporte a uma infraestrutura de PKI da Microsoft. Certificados de usuários e de dispositivos podem ser emitidos para um dispositivo móvel, a fim de atender aos requisitos da autenticação baseada em certificado. Antes de usar certificados, é preciso determinar se eles são necessários, se a infraestrutura de rede pode dar suporte à autenticação baseada em certificado e se os certificados são usados atualmente no ambiente existente.

Caso esteja planejando usar certificados com perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](../protect/certificates-configure.md) com suporte, pronta para criar e implantar perfis de certificado.

Além disso, se perfis de certificado SCEP forem usados, você precisará determinar qual servidor hospedará o recurso do NDES (Serviço de Registro de Dispositivo de Rede) e como ocorrerá a comunicação.

Saiba mais sobre:

- [Como configurar perfis de certificado do Intune](../protect/certificates-configure.md)

- [Como configurar a infraestrutura de certificado para SCEP](../protect/certificates-scep-configure.md)

- [Como configurar a infraestrutura de certificado para PFX](../protect/certficates-pfx-configure.md)




## <a name="device-platform-considerations"></a>Considerações sobre plataformas de dispositivo

Analise os seguintes aspectos dos dispositivos para entender como gerenciá-los corretamente.

- Plataformas de dispositivos com suporte

- Dispositivos

- Propriedade do dispositivo

- Registro em massa

Vamos examinar essas áreas mais detalhadamente.

### <a name="determine-supported-device-platforms"></a>Determinar as plataformas de dispositivo com suporte

Você precisa saber quais dispositivos estarão no ambiente e verificar se eles têm suporte ou não no Intune ao criar o projeto. O Intune dá suporte às plataformas iOS, Android e Windows.

[Lista completa dos dispositivos com suporte do Intune](supported-devices-browsers.md).

### <a name="devices"></a>Dispositivos

O Intune gerencia dispositivos móveis para proteger dados corporativos e permitir que os usuários finais trabalhem em mais locais. O Intune oferece suporte a várias plataformas de dispositivo; portanto, é recomendável documentar os dispositivos, as plataformas do sistema operacional e as versões que terão suporte no design da sua organização. Por exemplo:

| **Plataforma de dispositivo** | **Versões do sistema operacional** |
|:---:|:---:|
| iOS – iPhone | 10.0+ |                
| iOS – iPad | 10.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Tablet Windows 10 | 10+ |


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para desenvolver uma lista de dispositivos.
### <a name="device-ownership"></a>Propriedade do dispositivo

O Intune oferece suporte a dispositivos corporativos e dispositivos pessoais. Um dispositivo será considerado corporativo se for registrado por um gerenciador de registros do dispositivo ou pelo programa de registro de dispositivos. Por exemplo, um dispositivo foi registrado por meio do DEP (Programa de Registro de Dispositivos) da Apple, marcado como corporativo e colocado em um grupo de dispositivos que recebe políticas e aplicativos corporativos direcionados.

Consulte a [Seção 3: Determinar os requisitos de cenários de caso de uso](planning-guide-requirements.md) para saber mais sobre casos de uso corporativo e BYOD.

### <a name="bulk-enrollment"></a>Registro em massa

 É possível realizar o registro em massa dos dispositivos de diferentes maneiras, de acordo com a plataforma. Se o registro em massa for necessário, primeiro [determine o método de registro em massa](../enrollment/device-enrollment.md) e incorpore-o ao design.

## <a name="feature-requirements"></a>Requisitos de recursos

Nestas seções, examinaremos os seguintes recursos e funcionalidades que estão alinhados aos requisitos de cenários de caso de uso:

- Políticas de Termos e condições

- Políticas de configuração

- Perfis de Recursos

- Aplicativos

- Política de conformidade

- Acesso condicional

Vamos examinar cada uma dessas áreas mais detalhadamente.

### <a name="terms-and-conditions-policies"></a>Políticas de Termos e condições

Os [Termos e condições](../enrollment/terms-and-conditions-create.md) podem ser usados para explicar as políticas ou condições que um usuário final deverá aceitar antes de registrar o dispositivo. O Intune dá suporte à capacidade de adicionar e implantar várias políticas de termos e condições em grupos de usuários.

Você precisa determinar se as políticas de termos e condições são necessárias. Nesse caso, quem será responsável por fornecer essas informações na organização? Veja abaixo um exemplo de como documentar a política de termos e condições.

| **Nome de Termos e Condições** | **Caso de uso** | **Grupo de destino** |
|:---:|:---:|:---:|
| Termos e Condições corporativos | Corporativo | Usuários corporativos |                 
| Termos e Condições da política BYOD | BYOD | Usuários BYOD |                


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para mapear os termos e condições dos seus grupos de usuários.

### <a name="configuration-policies"></a>Políticas de configuração

As políticas de configuração são usadas para gerenciar as configurações e os recursos de segurança de um dispositivo. Ao criar as políticas de configuração, consulte a seção sobre requisitos de caso de uso para determinar as configurações necessárias para os dispositivos do Intune. Documente as configurações e como elas devem ser configuradas. Documente também para quais grupos de usuários ou de dispositivos elas serão direcionadas.

É necessário criar pelo menos uma política de configuração por plataforma. Se necessário, é possível criar várias políticas de configuração por plataforma. Veja abaixo um exemplo de como criar quatro políticas de configuração distintas para diferentes plataformas e cenários de caso de uso.

| **Nome da política** | **Plataforma de dispositivo** | **Configurações** | **Grupo de destino** |   
|:---:|:---:|:---:|:---:|
| Corporativo – iOS | iOS | PIN obrigatório; tamanho: 6; restringir o backup na nuvem | Dispositivos Corporativos |                                                           
| Corporativo – Android | Android | PIN obrigatório; tamanho: 6; restringir o backup na nuvem | Dispositivos Corporativos |                                                           
| BYOD – iOS  | iOS | PIN obrigatório; tamanho: 4 | Dispositivos BYOD |
| BYOD – Android  | Android | PIN obrigatório; tamanho: 4 | Dispositivos BYOD |


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de política de configuração.

### <a name="profiles"></a>Perfis

Os perfis são usados para ajudar o usuário final a se conectar aos dados da empresa. O Intune dá suporte a vários tipos de perfis. Consulte os casos de uso e os requisitos para determinar quando os perfis serão configurados. Todos os perfis de dispositivo são categorizados por tipo de plataforma e devem ser incluídos na documentação do design.

- Perfis de certificado

- Perfil de Wi-Fi

- Perfil da VPN

- Perfil de email

Vamos examinar cada tipo de perfil mais detalhadamente.

#### <a name="certificate-profiles"></a>Perfis de certificado

Os perfis de certificado permitem que o Intune emita um certificado para um usuário ou dispositivo. O Intune dá suporte ao seguinte:

- Protocolo SCEP

- Certificado Raiz Confiável

- Certificado PFX.

É recomendável documentar qual grupo de usuários precisa de um certificado, quantos perfis de certificado serão necessários e em quais grupos de usuários eles serão implantados.

>[!NOTE]
> Lembre-se de que o certificado raiz confiável é necessário para o perfil de Certificado SCEP; portanto, garanta que todos os usuários de destino para o perfil de Certificado SCEP também recebam um certificado raiz confiável. Se forem necessários certificados SCEP, projete e documente quais modelos de certificado SCEP serão necessários.

Este é um exemplo de como é possível documentar os certificados durante o design:

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |   
|:---:|:---:|:---:|:---:|
| AC Raiz | AC Raiz Corporativa | Android, iOS, Windows Mobile | Corporativo, BYOD  |                                                           
| SCEP | Certificado de Usuário | Android, iOS, Windows Mobile | Corporativo, BYOD |                                                           


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de perfil de certificado.

#### <a name="wi-fi-profile"></a>Perfil de Wi-Fi

Os perfis de Wi-Fi são usados para conectar automaticamente um dispositivo móvel a uma rede sem fio. O Intune dá suporte à implantação de perfis de Wi-Fi em todas as plataformas com suporte. Saiba mais sobre [como o Intune dá suporte a perfis de Wi-Fi.](../configuration/wi-fi-settings-configure.md)

Veja abaixo um exemplo de um design para um perfil de Wi-Fi:

| **Tipo** | **Nome do perfil** | **Plataforma do dispositivo** | **Casos de uso** | | Wi-Fi | Perfil de Wi-Fi na Ásia | Android | BYOD corporativo na região da Ásia| | Wi-Fi | Perfil de Wi-Fi na América do Norte | Android, iOS, Windows 10 Mobile | BYOD corporativo na região da América do Norte |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de perfil de Wi-Fi.

#### <a name="vpn-profile"></a>Perfil da VPN

Perfis de VPN permitem que os usuários acessem a rede de locais remotos. O Intune dá suporte a perfis de VPN de conexões de VPN móveis nativas e de fornecedores terceirizados. Saiba mais sobre os [perfis de VPN e os fornecedores com suporte no Intune](../configuration/vpn-settings-configure.md).

Veja abaixo um exemplo de como documentar o design de um perfil VPN.

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |
|:---:|:---:|:---:|:---:|
| VPN | Qualquer perfil de conexão VPN Cisco | Android, iOS, Windows 10 Mobile | Corporativo, BYOD na América do Norte e Alemanha|
| VPN | Pulse Secure | Android | Corporativo, BYOD na região da Ásia |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de perfil de VPN.

#### <a name="email-profile"></a>Perfil de email

Os perfis de email permitem que um cliente de email seja configurado automaticamente com as informações de conexão e a configuração de email. O Intune dá suporte a perfis de email em alguns dispositivos. Saiba mais sobre os [perfis de email e quais plataformas têm suporte](../configuration/email-settings-configure.md).

Veja abaixo um exemplo de como documentar o design de perfis de email:

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |
|:---:|:---:|:---:|:---:|
| Perfil de email | Perfil de email do iOS | iOS | Corporativo – BYOD para profissional da informação |
| Perfil de email | Perfil de email do Android Knox | Android Knox | BYOD |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de perfil de email.
### <a name="apps"></a>Aplicativos

É possível usar o Intune para fornecer aplicativos aos usuários ou dispositivos de diversas maneiras. Os tipos de aplicativos incluem aplicativos do instalador do software, aplicativos de uma loja pública de aplicativos, links externos ou aplicativos iOS gerenciados. Além das implantações de aplicativo individuais, os aplicativos adquiridos por volume podem ser gerenciados e implantados por meio de programas de compra por volume para iOS e Windows. Saiba mais sobre:

- [Os tipos de aplicativos podem ser fornecidos](../apps/app-management.md)

- [iOS VPP (Volume Purchase Program) for Business](../apps/vpp-apps-ios.md)

- [Aplicativos da Microsoft Store para Empresas](../apps/windows-store-for-business.md)

#### <a name="app-type-requirements"></a>Requisitos de tipo de aplicativo

Como os aplicativos podem ser implantados em usuários e dispositivos, é recomendável decidir quais aplicativos serão gerenciados pelo Intune. Durante a coleta da lista, tente responder às seguintes perguntas:

- Os aplicativos exigem integração com serviços de nuvem?

- Todos os aplicativos estarão disponíveis para os usuários BYOD?

- Quais são as opções de implantação disponíveis para esses aplicativos?

- A empresa precisa fornecer acesso a dados de aplicativos SaaS (software como serviço) para seus parceiros?

- Os aplicativos exigem acesso à Internet por meio dos dispositivos do usuário?

- Os aplicativos estão disponíveis publicamente em uma loja de aplicativos ou são aplicativos LOB (de linha de negócios) personalizados?


#### <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

As políticas de proteção do aplicativo minimizam a perda de dados, definindo como o aplicativo gerencia os dados corporativos. O Intune dá suporte a políticas de proteção do aplicativo para qualquer aplicativo criado para funcionar com o gerenciamento de aplicativo móvel. Ao criar a política de proteção do aplicativo, é necessário decidir quais restrições serão colocadas nos dados corporativos de um determinado aplicativo. É recomendável examinar o funcionamento das [políticas de proteção do aplicativo](../apps/app-protection-policy.md). Veja abaixo um exemplo de como documentar os aplicativos existentes e qual proteção é necessária.

| **Aplicativo** | **Finalidade** | **Plataformas** | **Caso de uso** | **Política de proteção do aplicativo** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Disponível | iOS | Corporativo – Executivos | Sem risco de jailbreak, arquivos criptografados |                                                         
| Word | Disponível | iOS, Android – Samsung Knox, não Knox, Windows 10 Mobile | Corporativo, BYOD | Sem risco de jailbreak, arquivos criptografados |                                                         


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de política de proteção do aplicativo.
#### <a name="compliance-policies"></a>Políticas de conformidade

As políticas de conformidade determinam se um dispositivo está em conformidade com requisitos específicos. O Intune usa políticas de conformidade para determinar se um dispositivo é considerado compatível ou não compatível. Em seguida, o status de conformidade pode ser usado para restringir o acesso aos recursos da empresa. Se o acesso condicional for necessário, recomenda-se criar uma [política de conformidade do dispositivo](../protect/device-compliance-get-started.md).

Consulte os requisitos e casos de uso para determinar quantas políticas de conformidade do dispositivo são necessárias e quais grupos de usuários são os grupos de usuários de destino. Além disso, é necessário determinar por quanto tempo um dispositivo pode ficar offline sem fazer check-in antes de ser considerado não compatível.

Veja abaixo um exemplo de como criar uma política de conformidade:

| **Nome da política** | **Plataforma de dispositivo** | **Configurações** | **Grupo de destino** |
|:---:|:---:|:---:|:---:|
| Política de conformidade | iOS, Android – Samsung Knox, não Knox, Windows 10 Mobile | PIN – obrigatório, sem risco de jailbreak | Corporativo, BYOD |


[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de política de conformidade.
#### <a name="conditional-access-policies"></a>Políticas de acesso condicional

O acesso condicional é usado para permitir que apenas os dispositivos em conformidade acessem o email e outros recursos da empresa. O Intune funciona com o EMS (Enterprise Mobility + Security) para controlar o acesso aos recursos da empresa. Decida se você exigirá o acesso condicional e o que deverá ser protegido. Saiba mais sobre o [Acesso Condicional](../protect/conditional-access.md).

Para o acesso online, decida quais plataformas e grupos de usuários você direcionará por políticas de acesso condicional. Além disso, determine se é necessário instalar ou configurar o conector do Intune para o Exchange local: 

- [Exchange local](../protect/exchange-connector-install.md)

Este é um exemplo de como documentar as políticas de acesso condicional:

| **Serviço** | **Plataformas para Autenticação Moderna** | **Autenticação básica** | **Casos de uso** |
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Bloquear dispositivos não compatíveis em plataformas compatíveis com o Intune | Corporativo, BYOD |
| SharePoint Online | iOS, Android |  | Corporativo, BYOD |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para identificar suas necessidades de política de acesso condicional.

## <a name="next-steps"></a>Próximas etapas

A próxima seção fornece diretrizes sobre o [processo de implementação do Intune](planning-guide-onboarding.md).
