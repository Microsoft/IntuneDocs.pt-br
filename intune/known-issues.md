---
title: Problemas conhecidos no Microsoft Intune no Azure
titleSuffix: Intune on Azure
description: Leia mais sobre os problemas conhecidos no Intune
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fda224613d8b69be82ef7f9681ba9165be33e52
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Problemas conhecidos no Microsoft Intune
<a id="known-issues-in-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use este tópico para saber mais sobre os problemas conhecidos no Microsoft Intune.

Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](get-support.md).

Caso você deseje solicitar um novo recurso para o Intune, considere enviar um relatório em nosso site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## Migração
<a id="migration" class="xliff"></a>

### Os grupos criados pelo Intune durante a migração podem afetar a funcionalidade de outros produtos da Microsoft
<a id="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products" class="xliff"></a>

Ao migrar do Intune clássico para o Azure, você poderá ver um novo grupo chamado **Todos os Usuários – b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Esse grupo contém todos os usuários em seu Azure Active Directory, não apenas os usuários licenciados do Intune. Esse uso pode causar problemas com outros produtos da Microsoft, caso você espere que alguns usuários novos ou existentes não sejam membros de nenhum grupo.

### Migração secundária necessária para funcionalidades selecionadas
<a id="secondary-migration-required-for-select-capabilities" class="xliff"></a>

As contas do Intune criadas antes de janeiro de 2017 devem ser migradas antes que essas funcionalidades possam ser usadas no portal do Azure:

- Perfis de Registro de Dispositivo Corporativo
- Programa de Registro do Dispositivo da Apple
- Dispositivos corporativos pré-registrados por grupo de número de série do iOS
- Gerenciadores de Registro de Dispositivos
- Apple Volume Purchase Program

Como essas funcionalidades não podem ser gerenciadas nos consoles clássicos do Silverlight e do Azure, a migração:
- Desabilita-as no console clássico
- Habilita-as no console do Azure.  

Se você gerenciar essas funcionalidades do Intune no Portal do Azure agora, lembre-se dos seguintes pontos:

#### Remove os perfis de Registro de Dispositivo Corporativo no Apple DEP
<a id="removes-default-corporate-device-enrollment-profiles-in-apple-dep" class="xliff"></a>
O Portal do Azure não dá suporte ao perfil de Registro de Dispositivo Corporativo padrão em dispositivos Apple DEP (Programa de Registro de dispositivos). Essa funcionalidade, disponível no console clássico do Intune no Silverlight, foi descontinuada para impedir a atribuição acidental de perfis. Quando os números de série DEP são sincronizados no Portal do Azure, nenhum perfil de Registro de Dispositivo Corporativo é atribuído. Um perfil de registro deve ser atribuído antes do uso do dispositivo.

#### Token de DEP da Apple restaurado com a migração
<a id="apple-dep-token-restored-with-migration" class="xliff"></a>

Se você excluir um token do Programa de registro de dispositivos da Apple no Portal Clássico do Intune (Silverlight) e não carregar um novo token para o Portal do Azure, o token original será restaurado no Portal do Azure durante a migração. Para remover esse token e impedir o registro DEP, exclua o token no Portal do Azure.

### As folhas de status das políticas migradas não funcionam
<a id="status-blades-for-migrated-policies-do-not-work" class="xliff"></a>

Não é possível exibir informações de status de políticas que foram migradas do portal clássico no portal do Azure. No entanto, você pode continuar exibindo relatórios dessas políticas no portal Clássico.
Para exibir informações de status das políticas de configuração migradas, recrie-as no portal do Azure.

## Aplicativos
<a id="apps" class="xliff"></a>

### Aplicativos iOS adquiridos por volume disponíveis somente no idioma padrão do locatário do Intune
<a id="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language" class="xliff"></a>
Aplicativos do iOS adquiridos por volume são exibidos e podem ser atribuídos apenas para o mesmo código de país que sua conta do Intune. O Intune somente sincroniza aplicativos da mesma localidade do iTunes do código de país de conta de locatário do Intune. Por exemplo, se você comprar um aplicativo que está disponível apenas na loja dos EUA, mas sua conta do Intune é da Alemanha, o Intune não mostrará o aplicativo.

### Várias cópias do mesmo programa iOS de compra por volume serão carregadas
<a id="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded" class="xliff"></a>
Não clique no botão **Carregar** várias vezes para o mesmo token VPP. Isso resultará no carregamento de tokens VPP duplicados e na sincronização do aplicativo diversas vezes para o mesmo token VPP. 

<!-- ## Groups -->

## Configuração do dispositivo
<a id="device-configuration" class="xliff"></a>

### Não é possível salvar uma política de Proteção de Informações do Windows em alguns dispositivos
<a id="you-cannot-save-a-windows-information-protection-policy-for-some-devices" class="xliff"></a>

Para dispositivos não registrados com o Intune, só é possível especificar um domínio primário no campo **Identificação Corporativa** nas configurações de uma política de Proteção de Informações do Windows.
Se você adicionar outros domínios (usando **Configurações avançadas** > **Perímetro da rede** > **Adicionar um domínio protegido**), não poderá salvar a política. A mensagem de erro exibida será alterada em breve para ser mais precisa.

### Suporte ao cliente VPN do Cisco AnyConnect
<a id="cisco-anyconnect-vpn-client-support" class="xliff"></a>
 
A versão mais recente do cliente VPN do Cisco AnyConnect (4.0.07072) não é compatível com o Intune no momento. Uma atualização futura do Intune incluirá a compatibilidade com esta versão do cliente VPN. Até lá, recomendamos não atualizar o cliente VPN do Cisco AnyConnect e continuar a usar a versão existente.

### Usando o tipo de senha numérica com dispositivos macOS Serra
<a id="using-the-numeric-password-type-with-macos-sierra-devices" class="xliff"></a>

Atualmente, se você selecionar o **Tipo de senha necessário** **Numérica** em um perfil de restrição de dispositivo em dispositivos macOS Sierra, ele será imposto como **Alfanumérica**. Se você desejar usar uma senha numérica com esses dispositivos, não defina essa configuração.
Esse problema poderá ser corrigido em uma versão futura do macOS.

Para obter mais informações sobre essas configurações, consulte [Configurações de restrição de dispositivo macOS no Microsoft Intune](device-restrictions-macos.md).

## Conformidade
<a id="compliance" class="xliff"></a>

### As políticas de conformidade do Intune não são mostradas no novo console
<a id="compliance-policies-from-intune-do-not-show-up-in-new-console" class="xliff"></a>

As políticas de conformidade criadas no portal clássico são migradas, mas não são exibidas no portal do Azure, devido às alterações de design no portal do Azure. As políticas de conformidade criadas no portal clássico do Intune ainda são impostas, mas devem ser exibidas e editadas no portal clássico do Intune.
Além disso, novas políticas de conformidade criadas no portal do Azure não estão visíveis no portal clássico do Intune.

Para saber mais, veja [O que é a conformidade do dispositivo](device-compliance.md).

<!-- ## Enrollment -->


<!-- ## Data protection -->


## Administração e contas
<a id="administration-and-accounts" class="xliff"></a>

Administradores Globais (também conhecidos como Administradores de Locatários) podem continuar realizando tarefas de administração diárias sem uma licença separada do Intune ou do EMS (Enterprise Mobility Suite). No entanto, para usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisam de uma licença do Intune ou do EMS.

<!-- ## Additional items -->












 
