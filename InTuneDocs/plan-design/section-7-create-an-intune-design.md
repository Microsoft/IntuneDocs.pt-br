---
title: Criar um design do Intune | Microsoft Docs
description: "Este artigo ajuda você a criar um design para um design e uma implementação somente na nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: ce51e92f9643ddc77e84e6b4c65825d397a37ddc
ms.lasthandoff: 04/14/2017


---

# <a name="create-an-intune-design"></a>Criar um design do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A seção do guia deve ser usada em paralelo com outros tópicos da Seção 2. Esse design se baseará nas informações que você coletará e nas decisões que serão tomadas, concluindo as seções anteriores deste guia. Nesta seção sobre design, teremos como foco o Intune independente, que é um serviço baseado em nuvem da Microsoft.

Embora haja requisitos mínimos de infraestrutura local, trabalhe em um plano de design para garantir que você terá a solução de gerenciamento de dispositivo móvel certa que atende a suas metas, seus objetivos e requisitos.

Além disso, é comum haver alterações de design durante as fases de implementação e teste. Portanto, lembre-se de documentar essas alterações e o motivo, conforme elas ocorrerem. Vamos abordar as seguintes áreas:

-   O ambiente atual

-   Opções de implantação do Intune

-   Requisitos de identidade para dependências externas

-   Considerações sobre plataformas de dispositivo

-   Requisitos para entrega  

Vamos examinar cada uma dessas áreas mais detalhadamente. 

## <a name="record-your-environment"></a>Registrar o ambiente

A primeira etapa antes de criar o design é registrar o ambiente atual. O ambiente atual podem influenciar as decisões de design e deve ser documentado e referenciado ao tomar outras decisões de design do Intune. Veja abaixo alguns exemplos de como registrar o ambiente atual:

-   **Identidade na nuvem**

    -   Você usa o DirSync ou AAD (Azure Active Directory) Connect?

    -   Seu ambiente é Federado?

    -   A Autenticação multifator está habilitada?

-   **Ambiente de email**

    -   O Exchange está sendo usado? A versão local ou na nuvem?

    -   Você está no meio de um projeto de migração do Exchange para a nuvem?

-   **Solução atual de MDM**

    -   Você está usando outras soluções de MDM?

    -   Quais soluções de MDM estão sendo usadas para os cenários de caso de uso corporativo e BYOD?

    -   Quais funcionalidades estão sendo usadas (por exemplo, configurações de dispositivo de aplicativo, configurações de Wi-Fi, etc.)?

    -   Há suporte para quais plataformas de dispositivo?

    -   Quais grupos e quantos usuários estão usando a solução de MDM?

-   **Solução de Certificado**

    -   Você implementou uma solução de Certificado?

    -   Quais tipo de certificados são usados?

-   **Gerenciamento de Sistemas**

    -   Como o ambiente de computador e servidor está sendo gerenciado?

    -   O System Center Configuration Manager está sendo usado? Você está usando uma plataforma de gerenciamento do sistema de terceiros?

-   **Solução de VPN**

    -   Qual é sua solução de VPN?

    -   Ela é usada para cenários de caso de uso corporativo e BYOD?

Lembre-se de observar os projetos ou outros planos em vigor para poder fazer alterações no ambiente ao registrar o ambiente atual de MDM. Veja abaixo um exemplo de uma maneira de registrar o ambiente atual para ajudar a criar o design do Intune:

| **Área de solução** | **Ambiente atual** | **Comentários** |
|:---:|:---:|:---:|
| **Identidade** | Azure AD, Azure AD Connect, não federado, sem MFA | Projeto em vigor para habilitar o MFA até o final do ano |                 
| **Ambiente de email** | Exchange no Local, Exchange Online | Atualmente migrando do Exchange no Local para o Exchange Online. 75% de caixas de correio migradas. Os últimos 25% serão migrados antes do início do Piloto do Intune. |                
| **SharePoint** | SharePoint local | Não há planos de migração para o SharePoint Online |  
| **MDM atual** | Exchange ActiveSync |  |
| **Solução de certificado** | Microsoft Server 2012 R2, Serviços de Certificados do AD | Usar somente o PKI para Servidores de Site |
| **Gerenciamento do Sistema** | System Center Configuration Manager CB 1606 | Gostaria de investigar a solução híbrida do Intune? |
| **Solução de VPN** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Escolher uma opção de implantação do Intune

O Intune oferece duas opções de implantação: independente e híbrida. Você precisará decidir qual delas atende aos seus requisitos de negócios. Independente refere-se ao serviço Intune em execução na nuvem, enquanto híbrido refere-se à integração do Intune com o System Center Configuration Manager.

- Saiba mais sobre como [escolher entre o gerenciamento de dispositivo móvel independente e híbrido do Microsoft Intune com o System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Local do locatário do Intune

Caso sua organização tenha uma presença global, lembre-se de planejar o local em que o locatário residirá ao assinar o serviço. O país é definido durante a inscrição para uma assinatura do Intune pela primeira vez e é mapeado para as regiões do mundo listadas abaixo:

-   América do Norte

-   Europa, Oriente Médio e África

-   Ásia e Pacífico

>[!IMPORTANT]
> Não é possível alterar o local do país/locatário posteriormente.

## <a name="external-dependencies"></a>Dependências externas

Dependências externas são serviços e produtos separados do Intune, mas que são um requisito do Intune ou que podem ser integradas com o Intune. É importante identificar os requisitos para dependências externas e como elas serão configuradas. Veja abaixo uma lista de alguns exemplos de dependências externas comuns.

-   Identidade

-   Grupos de usuários e de dispositivos

-   PKI

Vamos explorar mais detalhadamente essas dependências externas comuns abaixo

### <a name="identity"></a>Identidade

Identidade é como identificamos nossos usuários que estão abaixo de sua organização e que estão registrando um dispositivo. O Intune exige o Azure AD (Azure Active Directory) como o provedor de identidade do usuário. Se você já usa esse serviço, pode aproveitar sua identidade já existente na nuvem. Além disso, o Azure AD Connect é a ferramenta recomendada para sincronizar as identidades de usuários locais com os serviços em nuvem da Microsoft. Caso sua organização já esteja usando o Office 365, é importante que o Intune use o mesmo ambiente do Azure Active Directory.

Encontre mais informações sobre os requisitos de Identidade do Intune abaixo.

-   Saiba mais sobre os [requisitos de identidade](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Saiba mais sobre os [requisitos de sincronização de diretório](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Saiba mais sobre os [requisitos de autenticação multifator](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### <a name="user-and-device-groups"></a>Grupos de usuários e de dispositivos

Os grupos de usuários e de dispositivos determinam o destino de uma implantação. Isso pode incluir uma implantação que tem políticas, aplicativos e perfis como destino. O serviço de nuvem do Intune dá suporte apenas a grupos de usuários e de dispositivos. Você precisará determinar quais grupos de usuários e de dispositivos serão necessários. É recomendável criar todos os grupos no Active Directory local e sincronizá-los com o Azure Active Directory. Encontre mais informações sobre o planejamento e a criação de grupos de usuários e de dispositivos abaixo.

-   Saiba mais sobre como [planejar os grupos de usuários e de dispositivos](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Saiba [como criar grupos de usuários e de dispositivos](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### <a name="public-key-infrastructure-pki"></a>PKI (Infraestrutura de Chave Pública)

A Infraestrutura de Chave Pública fornece certificados para dispositivos ou usuários para uma autenticação segura em um serviço. O Intune dá suporte a uma infraestrutura de PKI da Microsoft. Certificados de usuários e de dispositivos podem ser emitidos para um dispositivo móvel, a fim de atender aos requisitos da autenticação baseada em certificado. Antes de implementar certificados, você precisa determinar se os certificados são necessários, se a infraestrutura de rede pode dar suporte à autenticação baseada em certificado e se os certificados são atualmente usados no ambiente existente.

Se você estiver planejando usar certificados com perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) com suporte, pronta para criar e implantar perfis de certificado.

Além disso, se certificados SCEP forem emitidos, você precisará determinar qual servidor hospedará o recurso NDES (Serviço de Registro de Dispositivo de Rede) e como ocorrerá a comunicação.

Mais informações sobre como configurar certificados no Intune:

-   [Configurar a infraestrutura de certificado para SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [Configurar a infraestrutura de certificado](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Configurar perfis de certificado do Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Como configurar políticas de acesso a recursos](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="device-platform-considerations"></a>Considerações sobre plataformas de dispositivo

É necessário examinar os dispositivos atentamente para entender como configurá-los corretamente.

-   Determinar as plataformas de dispositivo com suporte

-   Dispositivos

-   Propriedade do dispositivo

-   Registro em massa

Vamos examinar essas áreas mais detalhadamente.

### <a name="determine-supported-device-platforms"></a>Determinar as plataformas de dispositivo com suporte

Você precisa saber quais dispositivos estarão no ambiente e verificar se eles têm suporte ou não no Intune ao criar o projeto. O Intune dá suporte às plataformas iOS, Android e Windows.

-   Saiba mais sobre os [Dispositivos com suporte no Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

### <a name="devices"></a>Dispositivos

O Intune gerencia dispositivos móveis para proteger dados corporativos e permitir que os usuários finais trabalhem em mais locais. O Intune dá suporte a várias plataformas de dispositivo; portanto é recomendável documentar os dispositivos e as plataformas do sistema operacional que terão suporte no design de sua organização. Isso será expandido para os dispositivos e para as plataformas criadas na seção (requisitos de caso de uso).

Também recomendamos saber as versões para fazer referência à lista durante a verificação de funcionalidades do dispositivo por versão e plataforma do sistema operacional. Aqui está um exemplo:

| **Plataforma de dispositivo** | **Versões do sistema operacional** |
|:---:|:---:|
| iOS – iPhone | 9.0+ |                
| iOS – iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Tablet Windows 10 | 10+ |

### <a name="device-ownership"></a>Propriedade do dispositivo

O Intune dá suporte à propriedade corporativa e à propriedade BYOD. Um dispositivo será considerado de propriedade corporativa se for registrado por um gerenciador de registro do dispositivo ou pelo programa de registro de dispositivos. Como exemplo, um dispositivo pode ser registrado por meio do Apple DEP, marcado como corporativo e colocado em um grupo de dispositivos que recebe políticas e aplicativos corporativos de destino.

Consulte a [Seção 3: Determinar os requisitos de cenários de caso de uso](section-3-determine-use-case-requirements.md) para obter mais informações sobre casos de uso Corporativo e BYOD.

### <a name="bulk-enrollment"></a>Registro em massa

Há várias opções de registro disponíveis para registrar um dispositivo no Intune, a fim de complementar o registro por autoatendimento por meio do portal da empresa. O registro em massa pode ser realizado de diferentes maneiras conforme a plataforma. Se o registro em massa for necessário, primeiro determine o método de registro em massa e incorpore-o no design. Obtenha mais informações sobre os diferentes métodos de registro em massa abaixo.

-   Saiba mais sobre o [registro em massa](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Requisitos de recursos

Nesta seção, examinaremos os seguintes recursos e funcionalidades que estão alinhados aos requisitos de cenários de caso de uso:

-   Políticas de Termos e Condições

-   Políticas de configuração

-   Perfis de Recursos

-   Aplicativos

-   Política de Conformidade

-   Acesso condicional

Vamos examinar cada uma dessas áreas mais detalhadamente.

### <a name="terms-and-conditions-policies"></a>Políticas de Termos e Condições

Termos e Condições podem ser usados para explicar as políticas ou condições que um usuário final deverá aceitar antes do registro. O Intune dá suporte à capacidade de adicionar e implantar várias políticas de termos e condições em grupos de usuários. Você precisa determinar se as políticas de termos e condições são necessárias. Nesse caso, quem será responsável por fornecer essas informações na organização?

-   Saiba [como criar políticas de termos e condições](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) no Intune. Veja abaixo um exemplo de como documentar a política de termos e condições.

| **Nome de Termos e Condições** | **Caso de uso** | **Grupo de destino** |
|:---:|:---:|:---:|
| Termos e Condições corporativos | Corporativo | Usuários corporativos |                 
| Termos e Condições da política BYOD | BYOD | Usuários BYOD |                

### <a name="configuration-policies"></a>Políticas de configuração

As políticas de configuração são usadas para gerenciar as configurações e os recursos de segurança em um dispositivo. Ao criar as políticas de configuração, consulte a seção sobre requisitos de caso de uso para determinar as configurações necessárias para os dispositivos do Intune. Documente quais configurações e como elas devem ser definidas, bem como qual usuário ou quais grupos de dispositivos serão afetados.

É necessário criar, pelo menos, uma Política de Configuração por plataforma. Se necessário, é possível criar várias Políticas de Configuração por plataforma. Veja abaixo um exemplo de como criar quatro políticas de configuração diferentes para diferentes plataformas e cenários de caso de uso.

| **Nome da política** | **Plataforma de dispositivo** | **Configurações** | **Grupo de destino** |   
|:---:|:---:|:---:|:---:|
| Corporativo – iOS | iOS | PIN obrigatório; tamanho: 6; restringir o backup na nuvem | Dispositivos Corporativos |                                                           
| Corporativo – Android | Android | PIN obrigatório; tamanho: 6; restringir o backup na nuvem | Dispositivos Corporativos |                                                           
| BYOD – iOS  | iOS | PIN obrigatório; tamanho: 4 | Dispositivos BYOD |
| BYOD – Android  | Android | PIN obrigatório; tamanho: 4 | Dispositivos BYOD |

### <a name="profiles"></a>Perfis

Perfis são usados para ajudar o usuário final a se conectar aos dados da empresa. O Intune dá suporte a vários tipos de perfis. Consulte os casos de uso e os requisitos para determinar quando os [perfis](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) serão configurados. Todos os perfis de dispositivo são categorizados por tipo de plataforma e devem ser incluídos na documentação do design.

-   Perfis de certificado

-   Perfil de Wi-Fi

-   Perfil da VPN

-   Perfil de email

Vamos examinar cada tipo de perfil mais detalhadamente.

##### <a name="certificate-profiles"></a>Perfis de certificado

Os perfis de certificado permitem que o Intune emita um certificado para um usuário ou dispositivo. O Intune dá suporte ao seguinte:

-   Protocolo SCEP

-   Certificado Raiz Confiável

-   Certificado PFX.

É recomendável documentar qual grupo de usuários precisa de um certificado, quantos perfis de certificado serão necessários e em quais grupos de usuários eles serão implantados.

>[!NOTE]
> Lembre-se de que o certificado raiz confiável é necessário para o certificado SCEP; portanto, garanta que todos os usuários de destino para o certificado SCEP também recebem um certificado raiz confiável. Se forem necessários certificados SCEP, projete e documente quais modelos de certificado SCEP serão necessários.

Este é um exemplo de como é possível documentar os certificados durante o design:

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |   
|:---:|:---:|:---:|:---:|
| AC Raiz | AC Raiz Corporativa | Android, iOS, Windows Mobile | Corporativo, BYOD  |                                                           
| SCEP | Certificado de Usuário | Android, iOS, Windows Mobile | Corporativo, BYOD |                                                           

##### <a name="wi-fi-profile"></a>Perfil de Wi-Fi

Perfis de Wi-Fi são usados para conectar automaticamente um dispositivo móvel a uma rede sem fio. O Intune dá suporte à implantação de perfis de Wi-Fi em todas as plataformas com suporte.

-   Saiba mais sobre [como o Intune dá suporte a perfis de Wi-Fi.](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)

Veja abaixo um exemplo de um design para um perfil de Wi-Fi:

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Perfil de Wi-Fi da Ásia | Android | Corporativo, BYOD na região da Ásia|                                                           
| Wi-Fi | Perfil de Wi-Fi na América do Norte | Android, iOS, Windows 10 Mobile | Corporativo, BYOD na região da América do Norte |                                                           

##### <a name="vpn-profile"></a>Perfil da VPN

Perfis de VPN permitem que os usuários acessem a rede de locais remotos. O Intune dá suporte a perfis de VPN de conexões de VPN móveis nativas e de fornecedores de terceiros.

-   Saiba mais sobre os [perfis de VPN e os fornecedores com suporte no Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune).

Veja abaixo um exemplo de como documentar o design de um perfil VPN.

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |   
|:---:|:---:|:---:|:---:|
| VPN | Qualquer perfil de conexão VPN Cisco | Android, iOS, Windows 10 Mobile | Corporativo, BYOD na América do Norte e Alemanha|                                                           
| VPN | Pulse Secure | Android | Corporativo, BYOD na região da Ásia |                                                           

##### <a name="email-profile"></a>Perfil de email

Os perfis de email permitem que um cliente de email seja configurado automaticamente com informações de conexão e a configuração de email. O Intune dá suporte a perfis de email em alguns dispositivos.

-   Saiba mais sobre os [perfis de email](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) e quais plataformas têm suporte.

Veja abaixo um exemplo de como documentar o design de perfis de email:

| **Tipo** | **Nome do perfil** | **Plataforma de dispositivo** | **Casos de uso** |   
|:---:|:---:|:---:|:---:|
| Perfil de email | Perfil de email do iOS | iOS | Corporativo – BYOD para profissional da informação |                                                           
| Perfil de email | Perfil de email do Android Knox | Android Knox | BYOD |

### <a name="apps"></a>Aplicativos

O Intune dá suporte à entrega de aplicativos aos usuários ou dispositivos de várias maneiras. O tipo de aplicativo entregue pode ser aplicativos do instalador de software, aplicativos de uma loja pública de aplicativos, links externos ou aplicativos iOS gerenciados. Além das implantações de aplicativo individuais, os aplicativos adquiridos por volume podem ser gerenciados e implantados por meio de programas de compra por volume para iOS e Windows. Veja abaixo mais informações sobre como o Intune dá suporte a aplicativos e sobre os programas de compra por volume.

-   Saiba mais sobre os [tipos de aplicativos](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)

-   Saiba mais sobre o [iOS VPP (Volume Purchase Program) for Business](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).

-   Saiba mais sobre a [Windows Store para Empresas](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### <a name="app-type-requirements"></a>Requisitos de tipo de aplicativo

Como os aplicativos podem ser implantados em usuários e dispositivos, é recomendável decidir quais aplicativos serão gerenciados pelo Intune. Durante a coleta da lista, tente responder às seguintes perguntas:

-   Os aplicativos exigem integração com serviços de nuvem?

-   Todos os aplicativos estarão disponíveis para os usuários BYOD?

-   Quais são as opções de implantação disponíveis para esses aplicativos?

-   Sua empresa precisa fornecer acesso a dados de aplicativos SaaS (software como serviço) para seus parceiros?

-   Os aplicativos exigem acesso à Internet por meio dos dispositivos do usuário?

-   Os aplicativos estão disponíveis publicamente em uma loja de aplicativos ou são Aplicativos de Linha de Negócios personalizados?


>[!TIP]
> Confira os [diferentes tipos de aplicativos com suporte no Intune](https://docs.microsoft.com/intune/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

As políticas de proteção do aplicativo minimizam a perda de dados, definindo como o aplicativo gerencia os dados corporativos. O Intune dá suporte a políticas de proteção do aplicativo para qualquer aplicativo criado para funcionar com o gerenciamento de aplicativo móvel. Ao criar a política de proteção do aplicativo, é necessário determinar quais restrições você colocará aos dados corporativos em determinado aplicativo. É recomendável examinar o funcionamento das [políticas de proteção do aplicativo](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Veja abaixo um exemplo de como documentar os aplicativos existentes e qual proteção é necessária.

| **Aplicativo** | **Finalidade** | **Plataformas** | **Caso de uso** | **Política de proteção do aplicativo** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Disponível | iOS | Corporativo – Executivos | Sem risco de jailbreak, arquivos criptografados |                                                         
| Word | Disponível | iOS, Android – Samsung Knox, não Knox, Windows 10 Mobile | Corporativo, BYOD | Sem risco de jailbreak, arquivos criptografados |                                                         

#### <a name="compliance-policies"></a>Políticas de conformidade

As políticas de conformidade determinam se um dispositivo está em conformidade com requisitos específicos. O Intune usa políticas de conformidade para determinar se um dispositivo é considerado em conformidade ou não. Em seguida, o status de conformidade pode ser usado para restringir o acesso aos recursos da empresa. Se o acesso condicional é necessário, é recomendável criar uma [política de conformidade do dispositivo](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Consulte os requisitos e casos de uso para determinar quantas políticas de conformidade do dispositivo são necessárias e quais grupos de usuários são os grupos de usuários de destino. Além disso, é necessário determinar quanto tempo um dispositivo pode ficar offline sem fazer check-in antes de ser considerado fora de conformidade.

Veja abaixo um exemplo de como criar uma política de conformidade:

| **Nome da política** | **Plataforma de dispositivo** | **Configurações** | **Grupo de destino** |   
|:---:|:---:|:---:|:---:|
| Política de conformidade | iOS, Android – Samsung Knox, não Knox, Windows 10 Mobile | PIN – obrigatório, sem risco de jailbreak | Corporativo, BYOD |

#### <a name="conditional-access-policies"></a>Políticas de acesso condicional

O Acesso Condicional é usado para permitir que apenas os dispositivos em conformidade acessem os recursos da empresa. O Intune funciona com todo o EMS (Enterprise Mobility + Security) para controlar o acesso aos recursos da empresa. Você precisará determinar se o acesso condicional será necessário e o que deverá ser protegido.

-   Saiba mais sobre o [Acesso Condicional](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

Para o acesso online, determine quais plataformas e grupos de usuários serão o destino das políticas de acesso condicional.

Além disso, você precisa determinar se é necessário instalar/configurar o conector serviço a serviço do Intune para o Exchange Online ou Exchange no Local.

Saiba mais como instalar e configurar conectores serviço a serviço do Intune:

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Exchange Local](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Este é um exemplo de como documentar as políticas de acesso condicional:

| **Serviço** | **Plataformas para Autenticação Moderna** | **Autenticação básica** | **Casos de uso** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Bloquear dispositivos que não estão em conformidade em plataformas com suporte no Intune | Corporativo, BYOD |
| SharePoint Online | iOS, Android |  | Corporativo, BYOD |

## <a name="next-section"></a>Próxima seção

A próxima seção fornece diretrizes sobre o [processo de implementação do Intune](section-8-onboarding-process.md).

