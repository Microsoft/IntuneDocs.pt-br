---
title: Glossário do Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba os significados da terminologia usada no Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 07/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd7b5613-ee9f-4dc3-990c-ab4c1d40720d
ms.custom: intune-azure
ms.openlocfilehash: 2b59ed38329462ad8d8db604979c8eb725f7973a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-glossary"></a>Glossário do Microsoft Intune
Entenda as definições dos termos comuns usados no Microsoft Intune.

## <a name="a"></a>A

|||
|-|-|
|Atribuição de aplicativo|Permite aos usuários [encontrar, baixar e instalar](/intune/app-management) os aplicativos de que precisam. Isso era conhecido como *implantação de aplicativo*.|
|Perfil de configuração do aplicativo <br/><br/>Política de configuração de aplicativo|Disponível para aplicativos móveis com configurações específicas de fornecedor. Define um aplicativo [iOS](/intune/app-configuration-policies-use-ios) ou [Android](/intune/app-configuration-policies-use-android) com configurações específicas antes que ele seja executado.|
|Monitoramento de aplicativo|Permite [examinar o status e as atividades recentes](/intune/apps-monitor) relacionados à atribuição de aplicativo.|
|Tarefa de remoção de dados da proteção de aplicativo|[Remove os dados do aplicativo](/intune/app-protection-policies) do dispositivo do usuário.|
|Política de proteção de aplicativo|Disponível para aplicativos móveis que se integram às tecnologias EMS (Enterprise Mobility + Security). Garante que os aplicativos do usuário estão em conformidade com as [políticas de proteção de dados da empresa](/intune/app-protection-policies).|
|SDK do Aplicativo|O [SDK do Aplicativo do Microsoft Intune](/intune/app-sdk) possibilita que você adicione funcionalidade a seus aplicativos internamente escritos, o que permite que sejam gerenciados pelas políticas de Proteção de Aplicativo do Intune.|
|Ação de desinstalação de aplicativo|Permite [desinstalar aplicativos](/intune/apps-deploy) dos dispositivos do usuário.|
|Ferramenta de Encapsulamento de Aplicativo|Um [aplicativo de linha de comando](/intune/apps-prepare-mobile-application-management) que cria um wrapper em torno de um aplicativo de linha de negócios, permitindo que ele seja gerenciado por uma política de Proteção de Aplicativo do Intune.|
|Ação de atribuição|Uma opção escolhida quando você [atribui um aplicativo](/intune/apps-deploy). É possível optar por tornar a instalação do aplicativo obrigatória (obrigatória), opcional (Disponível) ou desinstalar o aplicativo.|
|Instalação disponível|Ao atribuir um aplicativo com essa ação, ele é exibido no portal da empresa e os usuários podem [instalá-lo sob demanda](/intune/apps-deploy).|
|Portal do Azure|O novo console do Intune [Leia mais](/intune/what-is-intune).|

## <a name="b"></a>B

|||
|-|-|
|BYOD|[Traga seu próprio dispositivo](/intune/device-enrollment). Os usuários podem instalar o aplicativo do Portal da Empresa do Intune em seu dispositivo e registrá-lo, obtendo acesso a recursos da empresa como email, aplicativos da empresa, dados da empresa e suporte.|

## <a name="c"></a>C

|||
|-|-|
|Perfil de certificado|Use esse tipo de política para [proteger o acesso a recursos corporativos](/intune/certificates-configure) com certificados ao usar perfis de Wi-Fi, email ou VPN.|
|COD|Os [dispositivos da empresa](/intune/device-enrollment) podem ser registrados de diversas maneiras, dependendo das necessidades da organização e dos tipos de dispositivos gerenciados.|
|Portal da Empresa|Um aplicativo ou um site que fornece aos usuários [acesso a aplicativos e dados da empresa](/intune/company-portal-customize).|
|Política de conformidade|Verifique se os dispositivos [estão em conformidade com determinadas regras ](/intune/device-compliance), como usar um PIN para acessar o dispositivo e a criptografia de dados armazenados no dispositivo.|
|Aplicativos compatíveis e incompatíveis|Sendo parte de uma [política de restrição de dispositivo](/intune/device-restrictions-configure), essas configurações permitem que você defina uma lista de aplicativos que os usuários podem ou não executar. Em seguida, o Intune o informa por relatórios que um aplicativo incompatível foi instalado ou executado. Para algumas plataformas, o Intune também pode bloquear a instalação de um aplicativo não compatível.|
|Acesso condicional|[Permite o acesso ao email corporativo, Office 365 e outros serviços](/intune/conditional-access) somente de dispositivos compatíveis com as regras definidas por você.|
|Política personalizada|Você [utiliza essas políticas](/intune/custom-settings-configure) quando uma política de configuração geral não tiver uma configuração interna que atenda às suas necessidades. É possível usar uma política personalizada para criar uma configuração por outros meios, como o Apple Configurator ou OMA-URI.|

## <a name="d"></a>D

|||
|-|-|
|Implantação|O ato de enviar um aplicativo ou uma política para um dispositivo ou usuário que você gerencia. Essa ação agora é conhecida como *atribuir*.|
|Gerenciador de registro de dispositivos|As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A [conta do DEM (gerenciador de registros de dispositivo)](/intune/device-enrollment-program-enroll-ios) é uma conta especial do Intune que pode registrar até 1.000 dispositivos.|
|Perfis de dispositivo|[Esses perfis](/intune/device-profile-create) permitem que você configure uma ampla variedade de configurações de segurança, recursos e acesso nos dispositivos gerenciados.|

## <a name="e"></a>E

|||
|-|-|
|Perfil de email|Essa política pode ser usada para definir [configurações de acesso a email](/intune/email-settings-configure) em dispositivos móveis, minimizando a quantidade de configuração que o usuário final deve fazer.|
|EMS|O Microsoft Enterprise Mobility + Security (anteriormente conhecido como Enterprise Mobility Suite) mantém os dados da empresa protegidos ao mesmo tempo em que permite que os usuários [acessem os aplicativos e o conteúdo que precisam](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|Usuário final|[Usuários de dispositivos como telefones e computadores](/intune/end-user-educate) gerenciados com o Intune.|
|Registrar|O Microsoft Intune usa o [registro](/intune/device-enrollment) para trazer dispositivos para o gerenciamento e permitir acesso aos recursos.|

## <a name="f"></a>F

|||
|-|-|
|FastTrack|Um [serviço Microsoft](https://technet.microsoft.com/library/mt228265.aspx) para usuários do Intune com mais de 150 licenças em um plano qualificado. Ao usar esse serviço, os especialistas da Microsoft podem trabalhar com você para colocar o Intune em funcionamento.|

## <a name="g"></a>G

|||
|-|-|
|Grupos|Os grupos permitem [logicamente juntar os usuários ou dispositivos](/intune/groups-get-started). Por exemplo, você pode criar um grupo de todos os computadores Windows. Em seguida, você pode atribuir aplicativos e perfis a esses grupos.|

## <a name="h"></a>H

|||
|-|-|
|Híbrida|Uma configuração na qual é possível gerenciar dispositivos registrados com o Intune por meio do console do System Center Configuration Manager.|

## <a name="i"></a>I

|||
|-|-|
|Portal do Azure|O portal do Azure usado para a maioria das operações de gerenciamento do Intune.|
|Cliente de software do Intune|Uma maneira alternativa de [gerenciar alguns computadores Windows](/intune-classic/get-started/choose-how-to-manage-devices) para obter ajuda ao decidir qual método usar.|
|Intune Software Publisher|Uma ferramenta usada para [definir aplicativos que deseja implantar e carregá-los para seu espaço de armazenamento em nuvem](/intune-classic/deploy-use/add-apps).|
|Inventário|Use para exibir o [hardware e o software instalado](/intune/device-inventory) em dispositivos gerenciados.|

## <a name="k"></a>K

|||
|-|-|
|Modo de quiosque|Configurado como parte de um [perfil de restrição de dispositivo](/intune/device-restrictions-configure), esse modo permite o bloqueio de dispositivos. Por exemplo, você poderá configurar um dispositivo de varejo para permitir a execução de apenas alguns aplicativos.|

## <a name="m"></a>M

|||
|-|-|
|Managed Browser|Um [aplicativo de navegação na Web](/intune/app-configuration-managed-browser) que você pode atribuir em sua organização usando o Intune. Uma política de navegador gerenciado configura uma lista de permitidos ou uma lista de contatos bloqueados que restringe os sites que podem ser visitados pelos usuários do navegador gerenciado.|
|Autoridade MDM|A [autoridade de MDM](/intune/mdm-authority-set) define o serviço de gerenciamento que tem permissão para gerenciar um conjunto de dispositivos. As opções para a autoridade de MDM incluem o Intune e o Configuration Manager com Intune.|
|Políticas de configuração de aplicativo móvel|Disponível para aplicativos móveis com configurações específicas de fornecedor. Por exemplo, uma política do [iOS](/intune/app-configuration-policies-use-ios) ou do [Android](/intune/app-configuration-policies-use-android) usada para fornecer configurações para aplicativos em conformidade quando executados, por exemplo, um nome de empresa ou endereço do servidor.|
|Política de provisionamento de aplicativo móvel|Uma política do iOS que ajuda você a garantir que os [perfis de provisionamento](/intune/app-provisioning-profile-ios) para os aplicativos iOS atribuídos não expiram.|
|Gerenciamento de aplicativos móveis|[Gerenciamento de aplicativo móvel (MAM)](/intune/app-lifecycle) permite publicar, enviar por push, configurar, proteger, monitorar e atualizar aplicativos móveis para usuários.
|Gerenciamento de dispositivos móveis|O [MDM (Gerenciamento de Dispositivo Móvel)](/intune/device-lifecycle) permite registrar dispositivos no Intune, de forma que você possa provisionar, configurar, monitorar e gerenciar esses dispositivos.



## <a name="o"></a>O

|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. Um protocolo de gerenciamento de dispositivo padrão do setor usado por muitos fabricantes de hardware para permitir o controle dos recursos de PCs e dispositivos móveis.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. Esses itens identificam as configurações de dispositivo individuais que estão em conformidade com o padrão OMA-DM. As configurações podem ser usadas em [perfis personalizados do Intune](/intune/custom-settings-configure) quando não há nenhuma configuração interna para atender às suas necessidades.|

## <a name="p"></a>P

|||
|-|-|
|Redefinição de senha|Um recurso do Intune que permite forçar o usuário final a [redefinir a senha](/intune/device-passcode-reset) em dispositivos com suporte.|

## <a name="r"></a>R

|||
|-|-|
|Bloqueio remoto|Um recurso do Intune que permite o [bloqueio de dispositivos com suporte](/intune/device-remote-lock), mesmo se você não estiver em posse do dispositivo.|
|Instalação requerida|Quando você atribui um aplicativo com essa ação, a [intervenção do usuário](/intune/apps-deploy) não é necessária para concluir a instalação. Em algumas plataformas, o usuário final poderá precisar aceitar a instalação.|


## <a name="s"></a>S

|||
|-|-|
|Apagamento seletivo|O [apagamento seletivo](/intune/device-company-data-remove) remove somente os dados da empresa protegidos pela política de proteção de aplicativo, incluindo perfis de email e configurações de um dispositivo. O apagamento seletivo deixa os dados pessoais do usuário no dispositivo.|
|Sideload|A ação de instalação de um aplicativo de linha de negócios sem acessá-los em uma loja de aplicativos.|
|Assinatura|O contrato em que você toma parte e que lhe fornece acesso como locatário do Intune.|

## <a name="t"></a>T

|||
|-|-|
|TeamViewer|Um aplicativo de terceiros que funciona com o Intune para fornecer [funcionalidades de assistência remota](/intune/device-profile-android-teamviewer) para um dispositivo Android gerenciado com o Intune.|
|Locatário|Uma única instância do serviço do Intune que você pode acessar com uma assinatura.|
|Termos e condições|Um tipo de política atribuída para usuários que contém informações que devem ser [lidas e aceitas](/intune/terms-and-conditions-create) antes de usar o Portal da Empresa para registrar e acessar seu trabalho.|

## <a name="v"></a>V

|||
|-|-|
|Aplicativos e livros comprados por volume|Algumas lojas de aplicativos oferecem a possibilidade de comprar várias licenças para um aplicativo ou livro que você deseja usar na empresa. O Intune ajuda você a gerenciar aplicativos e livros [comprados por meio de um programa como esse](/intune/vpp-apps). Importe as informações de licença da loja de aplicativos, acompanhe quantas licenças você utilizou e evite a instalação de mais cópias do aplicativo do que você possui.|
|Perfil da VPN|Uma política que atribui [configurações de VPN](/intune/vpn-settings-configure) a dispositivos gerenciados, minimizando a configuração necessária para os usuários finais.|

## <a name="w"></a>W

|               |                                                                                                                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Perfil de Wi-Fi | Uma política que atribui [configurações de rede sem fio](/intune/wi-fi-settings-configure) a dispositivos para permitir que os usuários se conectem à rede da empresa sem precisar saber ou definir as configurações. |

