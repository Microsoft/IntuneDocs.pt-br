---
title: "Glossário do Intune | Microsoft Docs"
description: Saiba mais sobre a terminologia do Microsoft Intune
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 9e084cce8e34b0de2dce7c6b8503d5b5089c930e
ms.lasthandoff: 04/14/2017


---

# <a name="microsoft-intune-glossary"></a>Glossário do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="a"></a>A

|||
|-|-|
|SDK do Aplicativo|O [SDK de Aplicativos do Microsoft Intune](/intune/develop/intune-app-sdk) possibilita que você adicione funcionalidade a seus aplicativos internamente escritos, que permite que sejam administrados pelas políticas de gerenciamento de aplicativos móveis do Intune.|
|Ferramenta de Encapsulamento de Aplicativo|Um [aplicativo de linha de comando](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) que cria um wrapper no aplicativo da linha de negócios, que permite que o aplicativo seja administrado por uma política de gerenciamento de aplicativos móveis do Intune.|
|Instalação disponível|Ao implantar um aplicativo com essa ação, ele é exibido no portal da empresa e os usuários podem [instalá-lo sob demanda](/intune/deploy-use/deploy-apps).|
|Portal do Azure|Um novo console do Intune que será lançado em breve. Neste momento, você pode usar o portal do Azure para criar [políticas do Intune MAM](/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies) para dispositivos.|

## <a name="b"></a>B
|||
|-|-|
|BYOD|[Traga seu próprio dispositivo](/intune/get-started/choose-how-to-enroll-devices1). Os usuários podem instalar o aplicativo do Portal da Empresa do Intune em seu dispositivo e registrá-lo, obtendo acesso a recursos da empresa como email, aplicativos da empresa, dados da empresa e suporte.|

## <a name="c"></a>C
|||
|-|-|
|Perfil de certificado|Use esse tipo de política para [proteger o acesso a recursos corporativos](/intune/deploy-use/secure-resource-access-with-certificate-profiles) com certificados ao usar perfis de Wi-Fi, email ou VPN.|
|Espaço de armazenamento em nuvem|Um lugar no qual os aplicativos ou os dados sobre aplicativos criados, [são armazenados](/intune/deploy-use/add-apps#cloud-storage-space).|
|COD|Os [dispositivos da empresa](/intune/get-started/choose-how-to-enroll-devices1) podem ser registrados de diversas maneiras, dependendo das necessidades da organização e dos tipos de dispositivos gerenciados.|
|Portal da Empresa|Um aplicativo ou um site que fornece aos usuários [acesso a aplicativos e dados da empresa](/intune/get-started/microsoft-intune-company-portal).|
|Política de conformidade|Certifique-se de que os dispositivos usados para acessar os aplicativos e os dados da empresa [estejam em conformidade com determinadas regras](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune), como usar um PIN para acessar o dispositivo e a criptografia de dados armazenados no dispositivo.|
|Aplicativos compatíveis e incompatíveis|Partes de uma [política de configuração geral](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), essas configurações permitem que você defina uma lista de aplicativos que os usuários podem, ou não podem, executar. Então, o Intune o informará por meio de relatórios que um aplicativo incompatível foi instalado ou executado. Para algumas plataformas, o Intune também pode bloquear a instalação de um aplicativo não compatível.|
|Acesso condicional|[Permite o acesso ao email corporativo, Office 365 e outros serviços](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) somente de dispositivos compatíveis com as regras definidas por você.|
|Política personalizada|Você [utiliza essas políticas](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) quando uma política de configuração geral não tiver uma configuração interna que atenda às suas necessidades. É possível usar uma política personalizada para criar uma configuração por outros meios, como o Apple Configurator ou OMA-URI.|

## <a name="d"></a>D
|||
|-|-|
|Implantação|O ato de enviar um aplicativo ou uma política para um dispositivo ou usuário que você gerencia.|
|Ação de implantação|Uma opção escolhida quando você [implanta um aplicativo](/intune/deploy-use/deploy-apps-in-microsoft-intune). É possível optar por fazer a instalação obrigatória, opcional ou desinstalar o aplicativo.|
|Gerenciador de registro de dispositivos|As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A conta do [gerenciador de registro de dispositivos (DEM)](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) é uma conta especial do Intune que pode registrar até 1.000 dispositivos.|
|Mapeamento de grupo de dispositivos|Ajuda a [adicionar automaticamente os dispositivos a grupos](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) com base em uma categoria de dispositivo (como "Pessoal" ou "Vendas") que você, ou o usuário final, pode atribuir ao dispositivo.|

## <a name="e"></a>E
|||
|-|-|
|Perfil de email|Essa política pode ser usada para definir [configurações de acesso de email](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) para clientes de email específicos em dispositivos móveis, minimizando a quantidade de configuração que o usuário final precisa fazer.|
|EMS|O Microsoft Enterprise Mobility + Security (anteriormente conhecido como Enterprise Mobility Suite) mantém os dados da empresa protegidos ao mesmo tempo em que permite que os usuários [acessem os aplicativos e o conteúdo que precisam](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|Usuário final|[Usuários de dispositivos como telefones e computadores](/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) gerenciados com o Intune.|
|Registrar|O Microsoft Intune usa o [registro](/intune/deploy-use/enroll-devices-in-microsoft-intune) para trazer dispositivos para o gerenciamento e permitir acesso aos recursos.|

## <a name="f"></a>F
|||
|-|-|
|FastTrack|Um [serviço Microsoft](https://technet.microsoft.com/library/mt228265.aspx) para usuários do Intune com mais de 150 licenças em um plano qualificado. Ao usar esse serviço, os especialistas da Microsoft trabalharão com você para colocar o Itune em funcionamento.|

## <a name="g"></a>G
|||
|-|-|
|Grupos|Os grupos permitem [logicamente juntar os usuários ou dispositivos](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). Por exemplo, você pode criar um grupo de todos os computadores Windows. É possível implantar aplicativos e política para esses grupos.|

## <a name="h"></a>H
|||
|-|-|
|Híbrida|Uma configuração na qual é possível gerenciar dispositivos registrados com o Intune [através do console do System Center Configuration Manager](/intune/get-started/integration-with-cloud-services).|

## <a name="i"></a>I
|||
|-|-|
|console administrativo do Intune|O console atual usado para a maioria das operações de gerenciamento do Intune.|
|Cliente de software do Intune|Uma maneira alternativa de [gerenciar alguns computadores Windows](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune). Consulte [Escolher como gerenciar dispositivos](/intune/get-started/choose-how-to-manage-devices) para obter ajuda ao decidir qual método usar.|
|Intune Software Publisher|Uma ferramenta usada para [definir aplicativos que deseja implantar e carregá-los para seu espaço de armazenamento em nuvem](/intune/deploy-use/add-apps).|
|Inventário|Use para exibir o [hardware e o software instalado](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune) em dispositivos gerenciados.|

## <a name="k"></a>K
|||
|-|-|
|Modo de quiosque|Configurado como parte de uma [política de configuração geral](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), esse modo permite bloquear dispositivos. Por exemplo, é possível configurar um dispositivo de varejo para permitir que apenas um aplicativo seja executado.|

## <a name="m"></a>M
|||
|-|-|
|Managed Browser|Um [aplicativo de navegação na web](/intune/deploy-use/manage-internet-access-using-managed-browser-policies) que você pode implantar em sua organização usando o Microsoft Intune. Uma política de navegador gerenciado configura uma lista de permitidos ou uma lista de contatos bloqueados que restringe os sites que podem ser visitados pelos usuários do navegador gerenciado.|
|Gerenciamento de aplicativos móveis|[Gerenciamento de aplicativo móvel (MAM)](/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune) permite publicar, enviar por push, configurar, proteger, monitorar e atualizar aplicativos móveis para usuários.
|Gerenciamento de dispositivos móveis|[Gerenciamento de dispositivo móvel (MDM)](/intune/deploy-use/overview-of-device-lifecycle-in-microsoft-intune) permite registrar dispositivos no Intune, de modo que você possa provisionar, configurar, monitorar e executar ações nesses dispositivos.
|Autoridade MDM|A [autoridade de MDM](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) define o serviço de gerenciamento que tem permissão para gerenciar um conjunto de dispositivos. As opções para a autoridade de MDM incluem o Intune e o Configuration Manager com Intune.|
|Política de provisionamento de aplicativo móvel|Uma política do iOS que ajuda a garantir que [perfis de provisionamento](/intune/deploy-use/ios-mobile-app-provisioning-profiles) para que os aplicativos iOS implantados não expirem.|
|Políticas de configuração de aplicativo móvel|Uma política do iOS usada para [fornecer configurações para aplicativos compatíveis com iOS](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) quando executados, por exemplo, um nome de empresa ou endereço do servidor.|

## <a name="o"></a>O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. Um protocolo de gerenciamento de dispositivo padrão do setor usado por muitos fabricantes de hardware para permitir o controle dos recursos de PCs e dispositivos móveis.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. Identifica as configurações de dispositivos individuais que estão em conformidade com o padrão OMA-DM. Um número dele pode ser usado em [políticas personalizadas do Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) quando não houver qualquer configuração interna para atender às suas necessidades.|

## <a name="p"></a>P
|||
|-|-|
|Política|Um [pacote de informações](/intune/deploy-use/microsoft-intune-policy-reference) enviado do Intune a um dispositivo. Por exemplo, você pode implantar as configurações de segurança ou informações de conformidade do dispositivo para o dispositivo.|
|Redefinição de senha|Um recurso do Intune que permite forçar o usuário final a [redefinir a senha](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) em dispositivos com suporte.|

## <a name="r"></a>R
|||
|-|-|
|Bloqueio remoto|Um recurso do Intune que permitirá que você [bloqueie dispositivos com suporte](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune), mesmo se você não estiver em posse do dispositivo.|
|Relatórios|O Intune fornece uma variedade de [relatórios internos](/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports) que disponibilizam informações sobre os dispositivos que você gerencia.|
|Instalação requerida|Quando você implanta um aplicativo com esta ação, ele é instalado no dispositivo [sem intervenção do usuário](/intune/deploy-use/deploy-apps) (embora em algumas plataformas, o usuário final possa ter que aceitar a instalação).|
|Requisitos|Uma [operação de implantação de aplicativo](/intune/deploy-use/add-apps) que permite que você selecione os requisitos que devem ser atendidos em um dispositivo antes que o aplicativo seja instalado. Por exemplo, é possível especificar a versão do sistema operacional do iOS que deve ser instalada antes do aplicativo.|

## <a name="s"></a>S
|||
|-|-|
|Apagamento seletivo|O [apagamento seletivo](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) remove somente os dados da empresa, incluindo dados de gerenciamento de aplicativo móvel (MAM), quando aplicável, configurações e perfis de email do dispositivo. O apagamento seletivo deixa os dados pessoais do usuário no dispositivo.|
|Assinatura|O contrato em que você toma parte e que lhe fornece acesso como locatário do Intune.|

## <a name="t"></a>T
|||
|-|-|
|TeamViewer|Um aplicativo de terceiros que funciona com o Intune para fornecer [recursos de assistência remota](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) para PCs com Windows gerenciados com o cliente de software do Intune.|
|Locatário|Uma única instância do serviço do Intune que você pode acessar com uma assinatura.|
|Termos e condições|Um tipo de política implantada para usuários com informações que devem ser [lidas e aceitas](/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) antes de usar o Portal da Empresa para registrar e acessar seu trabalho.|

## <a name="v"></a>V
|||
|-|-|
|Aplicativos adquiridos por volume|Algumas lojas de aplicativos oferecem a possibilidade de comprar várias licenças para um aplicativo que você deseja executar na empresa. O Intune ajuda a gerenciar aplicativos [adquiridos por meio de um programa desse tipo](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune), importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.|
|Perfil da VPN|Uma política que implanta [configurações VPN](/intune/deploy-use/vpn-connections-in-microsoft-intune) em dispositivos gerenciados, minimizando qualquer configuração necessária para os usuários finais.|

## <a name="w"></a>W
|||
|-|-|
|Perfil de Wi-Fi|Uma política que implanta [configurações de rede sem fio](/intune/deploy-use/wi-fi-connections-in-microsoft-intune) em dispositivos para permitir que os usuários se conectem à rede da empresa sem precisar saber ou definir as configurações.

