---
title: Problemas conhecidos no Microsoft Intune – Azure | Microsoft Docs
description: Leia sobre os problemas conhecidos no Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e523e4fb6505b2faaa0aa776b89454524130ba8
ms.sourcegitcommit: 503d76e0b066d0db77bcc48e5116c861f6a6fb57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187845"
---
# <a name="known-issues-in-microsoft-intune"></a>Problemas conhecidos no Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use este artigo para saber mais sobre os problemas conhecidos no Microsoft Intune.

Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](get-support.md).

Caso você queira solicitar um novo recurso para o Intune, considere registrar um relatório em nosso site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migração

### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal"></a>Exportar políticas de conformidade do Portal Clássico do Azure para recriar essas políticas no portal do Azure do Intune

As políticas de conformidade criadas no Portal Clássico do Azure serão preteridas. Você pode examinar e excluir as políticas de conformidade existentes, no entanto, você não pode atualizá-las. Se você precisar migrar políticas de conformidade para o portal do Azure do Intune atual, exporte as políticas como um arquivo separado por vírgula (arquivo .csv). Em seguida, use os detalhes no arquivo para recriar essas políticas no portal do Azure do Intune.

> [!IMPORTANT]
> Quando o Portal Clássico do Azure for desativado, você não poderá mais acessar ou exibir suas políticas de conformidade. Portanto, exporte as políticas e recrie-as no portal do Azure antes que o Portal Clássico do Azure seja desativado.

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Os recursos herdados do PC cliente do Intune só estão disponíveis no console do Silverlight

A capacidade de gerenciar o Windows 10 no Intune no Portal do Azure está disponível por meio do registro de MDM do Windows. Para obter mais informações, consulte [Intune on Azure console and legacy Intune PC Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure) (Intune no console do Azure e PC cliente herdado do Intune).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Os grupos criados pelo Intune durante a migração podem afetar a funcionalidade de outros produtos da Microsoft

Ao migrar do Intune para o Portal do Azure, você poderá ver um novo grupo chamado **Todos os Usuários –b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Esse grupo contém todos os usuários em seu Azure Active Directory, não apenas os usuários licenciados do Intune. Esse uso pode causar problemas com outros produtos da Microsoft, caso você espere que alguns usuários novos ou existentes não sejam membros de nenhum grupo.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>As folhas de status das políticas migradas não funcionam

Não é possível exibir informações de status de políticas que foram migradas do Portal Clássico do Azure no Portal do Azure. No entanto, você pode continuar exibindo relatórios dessas políticas no Portal Clássico. Para exibir informações de status das políticas de configuração migradas, recrie-as no portal do Azure.

## <a name="apps"></a>Aplicativos


### <a name="multiple-app-install-prompts-for-certain-vpp-apps"></a>Vários prompts de instalação de aplicativo para determinados aplicativos VPP
Talvez você veja vários prompts de instalação de aplicativo para determinados aplicativos VPP já instalados nos dispositivos de usuário final. Esse problema ocorrerá se a opção **Atualizações automáticas do aplicativo** estiver definida como **Ativada** para o token de VPP que você carregou para o Portal do Azure do Intune.    

Para solucionar esse problema, é possível desabilitar a opção **Atualizações automáticas do aplicativo** para o token de VPP. Para fazer isso, abra o Microsoft Intune no Portal do Azure. No Intune, selecione **Aplicativos clientes** > **Tokens VPP do iOS**. Em seguida, selecione o Token de VPP que implantou o aplicativo afetado e selecione **Editar** > **Atualizações automáticas do aplicativo** > **Desativar** > **Salvar**. Como alternativa, é possível interromper a implantação do aplicativo afetado como um aplicativo VPP, que interromperá os prompts.    

Esse é um problema conhecido na versão atual. Há uma correção futura que resolverá esse problema. Quando a correção for implementada, os usuários não verão mais vários prompts de instalação de aplicativos.

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Aplicativos iOS adquiridos por volume disponíveis somente no idioma padrão do locatário do Intune
Aplicativos do iOS adquiridos por volume são exibidos e podem ser atribuídos apenas para o mesmo código de país que sua conta do Intune. O Intune somente sincroniza aplicativos da mesma localidade do iTunes que o código de país da conta de locatário do Intune. Por exemplo, se você comprar um aplicativo disponível apenas em uma loja dos EUA, mas sua conta do Intune for da Alemanha, o Intune não mostrará o aplicativo.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Várias cópias do mesmo programa iOS de compra por volume serão carregadas
Não clique no botão **Carregar** várias vezes para o mesmo token VPP. Isso resultará no carregamento de tokens VPP duplicados e na sincronização do aplicativo diversas vezes para o mesmo token VPP.

### <a name="some-managed-browser-traffic-not-routed-through-azure-app-proxy----2463492---"></a>Parte do tráfego do Managed Browser não roteada por meio do Proxy de Aplicativo do Azure <!-- 2463492 -->
Há um problema conhecido com a integração do Proxy de Aplicativo e do Managed Browser onde determinado tráfego terciário (como chamadas JavaScript ou AJAX) não são roteadas por meio do Proxy de Aplicativo do Azure. Esse é um problema conhecido na versão atual.  

<!-- ## Groups -->

## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Não é possível salvar uma política de Proteção de Informações do Windows em alguns dispositivos

Para dispositivos não registrados com o Intune, só é possível especificar um domínio primário no campo **Identificação Corporativa** nas configurações de uma política de Proteção de Informações do Windows.
Se você adicionar outros domínios (usando **Configurações avançadas** > **Perímetro da rede** > **Adicionar um domínio protegido**), não poderá salvar a política. A mensagem de erro exibida será alterada em breve para ser mais precisa.

### <a name="cisco-anyconnect-and-cisco-legacy-anyconnect-vpn-client-support---ios"></a>Suporte ao cliente do Cisco AnyConnect e do Cisco Legacy AnyConnect VPN - iOS

Em dispositivos iOS, a integração de Controle de Acesso à Rede (NAC) não funciona com o novo cliente do Cisco AnyConnect. Estamos trabalhando com a Cisco para fornecer integração a NAC.

[Criar perfis VPN no Intune](vpn-settings-ios.md) fornece mais detalhes sobre os clientes do Cisco AnyConnect e do Cisco Legacy AnyConnect.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Usando o tipo de senha numérica com dispositivos macOS Serra

Atualmente, se você selecionar o **Tipo de senha necessário** **Numérica** em um perfil de restrição de dispositivo em dispositivos macOS Sierra, ele será imposto como **Alfanumérica**. Se você desejar usar uma senha numérica com esses dispositivos, não defina essa configuração.
Esse problema poderá ser corrigido em uma versão futura do macOS.

Para obter mais informações sobre essas configurações, consulte [Configurações de restrição de dispositivo macOS no Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Conformidade

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>As políticas de conformidade do Intune não são mostradas no novo console

As políticas de conformidade criadas no portal clássico são migradas, mas não são exibidas no portal do Azure, devido às alterações de design no portal do Azure. As políticas de conformidade criadas no Portal Clássico do Intune ainda são impostas, mas você deve poder ler e editá-las no Portal Clássico.

Além disso, novas políticas de conformidade criadas no Portal do Azure não estão visíveis no Portal Clássico.

Para saber mais, veja [O que é a conformidade do dispositivo](device-compliance.md).

<!-- ## Enrollment -->

## <a name="conditional-access"></a>Acesso condicional

### <a name="conditional-access-settings-from-intune-do-not-show-up-in-new-console"></a>As configurações de acesso condicional do Intune não são mostradas no novo console

Depois que seu locatário tiver sido migrado para o portal do Azure, as configurações de acesso condicional continuarão a ser aplicadas, no entanto, elas não aparecerão no portal do Azure Intune. 

Se você desejar ver e gerenciar essas configurações no portal do Azure, será preciso remover as configurações antigas do portal clássico e recriá-las no portal do Azure. 

Para obter mais informações, consulte [Melhores práticas para acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

## <a name="data-protection"></a>Proteção de dados

### <a name="ios-app-protection-policies"></a>Políticas de proteção de aplicativo iOS

Você pode definir as [políticas de proteção de aplicativo para iOS](app-protection-policy-settings-ios.md) disponíveis para usuários em dispositivos gerenciados por meio do MAM (gerenciamento de aplicativo móvel) sem registro. Devido a um erro temporário, você só pode definir essas políticas para versões do iOS com uma versão de ponto decimal único em vez de vários pontos decimais. Em vez de configurar uma versão mínima do iOS 10.3.1, defina-a como iOS 10.3. Isso será resolvido em uma atualização a ser disponibilizada em breve para o SDK do iOS.


## <a name="administration-and-accounts"></a>Administração e contas

Administradores Globais (também conhecidos como Administradores de Locatários) podem continuar realizando tarefas de administração diárias sem uma licença separada do Intune ou do EMS (Enterprise Mobility Suite). No entanto, para usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisam de uma licença do Intune ou do EMS.

<!-- ## Additional items -->
