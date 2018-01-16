---
title: Problemas conhecidos no Microsoft Intune no Portal do Azure
titlesuffix: Azure portal
description: Leia mais sobre os problemas conhecidos no Intune
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5cdda6a34311bb7b70234ab046975e6ff5417878
ms.sourcegitcommit: cfe3607ba0b76a37a3c54f465754482d49a816a0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2018
---
# <a name="known-issues-in-microsoft-intune"></a>Problemas conhecidos no Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use este tópico para saber mais sobre os problemas conhecidos no Microsoft Intune.

Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](get-support.md).

Caso você deseje solicitar um novo recurso para o Intune, considere enviar um relatório em nosso site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migração

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Os recursos herdados do PC cliente do Intune só estão disponíveis no console do Silverlight

A capacidade de gerenciar o Windows 10 no Intune no Portal do Azure está disponível por meio do registro de MDM do Windows. Para saber mais, confira [Intune on Azure console and legacy Intune PC Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure) (Intune no console do Azure e PC cliente herdado do Intune).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Os grupos criados pelo Intune durante a migração podem afetar a funcionalidade de outros produtos da Microsoft

Ao migrar do Intune para o Portal do Azure, você poderá ver um novo grupo chamado **Todos os Usuários –b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Esse grupo contém todos os usuários em seu Azure Active Directory, não apenas os usuários licenciados do Intune. Esse uso pode causar problemas com outros produtos da Microsoft, caso você espere que alguns usuários novos ou existentes não sejam membros de nenhum grupo.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>As folhas de status das políticas migradas não funcionam

Não é possível exibir informações de status de políticas que foram migradas do portal clássico no portal do Azure. No entanto, você pode continuar exibindo relatórios dessas políticas no Portal Clássico. Para exibir informações de status das políticas de configuração migradas, recrie-as no portal do Azure.

## <a name="apps"></a>Aplicativos

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Aplicativos iOS adquiridos por volume disponíveis somente no idioma padrão do locatário do Intune
Aplicativos do iOS adquiridos por volume são exibidos e podem ser atribuídos apenas para o mesmo código de país que sua conta do Intune. O Intune somente sincroniza aplicativos da mesma localidade do iTunes do código de país de conta de locatário do Intune. Por exemplo, se você comprar um aplicativo que está disponível apenas na loja dos EUA, mas sua conta do Intune for da Alemanha, o Intune não mostrará o aplicativo.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Várias cópias do mesmo programa iOS de compra por volume serão carregadas
Não clique no botão **Carregar** várias vezes para o mesmo token VPP. Isso resultará no carregamento de tokens VPP duplicados e na sincronização do aplicativo diversas vezes para o mesmo token VPP.

### <a name="assigning-office-365-to-macos-devices"></a>Atribuição do Office 365 a dispositivos com macOS
O recurso para atribuir o Office 365 para dispositivos com macOS com o Microsoft Intune estará disponível após a conclusão da nossa atualização de interface do usuário.

<!-- ## Groups -->

## <a name="device-configuration"></a>Configuração do dispositivo

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Não é possível salvar uma política de Proteção de Informações do Windows em alguns dispositivos

Para dispositivos não registrados com o Intune, só é possível especificar um domínio primário no campo **Identificação Corporativa** nas configurações de uma política de Proteção de Informações do Windows.
Se você adicionar outros domínios (usando **Configurações avançadas** > **Perímetro da rede** > **Adicionar um domínio protegido**), não poderá salvar a política. A mensagem de erro exibida será alterada em breve para ser mais precisa.

### <a name="cisco-anyconnect-vpn-client-support"></a>Suporte ao cliente VPN do Cisco AnyConnect

A versão mais recente do cliente VPN do Cisco AnyConnect (4.0.07072) não é compatível com o Intune no momento.
Uma atualização futura do Intune incluirá a compatibilidade com esta versão do cliente VPN. Até lá, recomendamos não atualizar o cliente VPN do Cisco AnyConnect e continuar a usar a versão existente.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Usando o tipo de senha numérica com dispositivos macOS Serra

Atualmente, se você selecionar o **Tipo de senha necessário** **Numérica** em um perfil de restrição de dispositivo em dispositivos macOS Sierra, ele será imposto como **Alfanumérica**. Se você desejar usar uma senha numérica com esses dispositivos, não defina essa configuração.
Esse problema poderá ser corrigido em uma versão futura do macOS.

Para obter mais informações sobre essas configurações, consulte [Configurações de restrição de dispositivo macOS no Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Conformidade

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>As políticas de conformidade do Intune não são mostradas no novo console

As políticas de conformidade criadas no portal clássico são migradas, mas não são exibidas no portal do Azure, devido às alterações de design no portal do Azure. As políticas de conformidade criadas no Portal Clássico do Intune ainda são impostas, mas você deve poder ler e editá-las no Portal Clássico.

Além disso, novas políticas de conformidade criadas no Portal do Azure não estão visíveis no Portal Clássico.

Para saber mais, confira [O que é a conformidade do dispositivo](device-compliance.md).

<!-- ## Enrollment -->


## <a name="data-protection"></a>Proteção de dados

### <a name="ios-app-protection-policies"></a>Políticas de proteção de aplicativo iOS

Você pode definir as [políticas de proteção de aplicativo para iOS](app-protection-policy-settings-ios.md) disponíveis para usuários em dispositivos gerenciados por meio do MAM (gerenciamento de aplicativo móvel) sem registro. Devido a um erro temporário, você só pode definir essas políticas para versões do iOS com uma versão de ponto decimal único em vez de vários pontos decimais. Em vez de configurar uma versão mínima do iOS 10.3.1, defina-a como iOS 10.3. Isso será resolvido em uma atualização a ser disponibilizada em breve para o SDK do iOS.


## <a name="administration-and-accounts"></a>Administração e contas

Administradores Globais (também conhecidos como Administradores de Locatários) podem continuar realizando tarefas de administração diárias sem uma licença separada do Intune ou do EMS (Enterprise Mobility Suite). No entanto, para usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisam de uma licença do Intune ou do EMS.

<!-- ## Additional items -->
