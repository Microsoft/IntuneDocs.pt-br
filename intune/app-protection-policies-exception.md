---
title: Exceções da política de transferência de dados para aplicativos
titleSuffix: Microsoft Intune
description: Crie exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 812f73cb0857298f01967cebbb36f0b8220fb9c6
ms.sourcegitcommit: 179bea63fe52a8cce236b6ca8d82a6bd51bf17a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Como criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como um administrador, você pode criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune. Uma exceção permite que você escolha especificamente quais aplicativos não gerenciados podem transferir dados entre aplicativos gerenciados. Os aplicativos não gerenciados que são incluídos na lista de exceções devem ser considerados confiáveis pelo departamento de TI. 

>[!WARNING] 
> Você é responsável por fazer alterações na política de exceção de transferência de dados. As adições a essa política permitem que aplicativos não gerenciados (aplicativos que não são gerenciados pelo Intune) acessem dados protegidos por aplicativos gerenciados. Esse acesso aos dados protegidos pode resultar em vazamentos de segurança de dados. Adicione exceções de transferência de dados somente a aplicativos que sua organização deve usar, mas que não sejam compatíveis com as APPs (políticas de proteção do aplicativo) do Intune. Além disso, adicione exceções somente para aplicativos que não representam riscos de vazamento de dados.

Dentro de uma Política de Proteção de Aplicativos do Intune, a configuração de **Permitir que o aplicativo transfira dados para outros aplicativos** como **Aplicativos gerenciados por política** significa que o aplicativo pode transferir dados somente para aplicativos que são gerenciados pelo Intune. Se você precisar permitir a transferência de dados para aplicativos específicos que não dão suporte ao aplicativo do Intune, você pode criar exceções a essa política usando **Selecionar aplicativos para isenção**. As isenções permitem que os aplicativos gerenciados pelo Intune invoquem aplicativos não gerenciados com base no protocolo de URL (iOS) ou o nome do pacote (Android). Por padrão, o Intune adiciona aplicativos vitais nativos à lista de exceções. 

## <a name="ios-data-transfer-exceptions"></a>Exceções de transferência de dados do iOS
Para uma política destinada ao iOS, você pode configurar as exceções de transferência de dados por protocolo de URL. Para adicionar uma exceção, consulte a documentação fornecida pelo desenvolvedor do aplicativo para encontrar informações sobre os protocolos de URL compatíveis. Para obter mais informações sobre exceções de transferência de dados do iOS, consulte [Configurações de política de proteção de aplicativo iOS – Isenções de transferência de dados](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Exceções de transferência de dados de Android
Para uma política destinada ao Android, você pode configurar as exceções de transferência de dados por nome de pacote do aplicativo. Verifique a página **Google Play** Store do aplicativo ao qual você deseja adicionar uma exceção, a fim de localizar o nome do pacote do aplicativo. Para obter informações adicionais sobre exceções de transferência de dados do Android, consulte [Configurações de política de proteção de aplicativo Android – Isenções de transferência de dados](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play. A ID do pacote está contida na URL da página do aplicativo. Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.

### <a name="example"></a>Exemplo
Ao adicionar o pacote **Webex** como uma exceção à política de transferência de dados de MAM, os links do Webex, em uma mensagem de email do Outlook gerenciada, terão permissão para abrir diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados.

- Exemplo do **Webex** do iOS: para isentar o aplicativo **Webex** e permitir que ele seja invocado por aplicativos gerenciados do Intune, você deve adicionar uma exceção de transferência de dados à cadeia de caracteres a seguir: <code>wbx</code>
    
 - Exemplo do **Maps** do iOS: para isentar o aplicativo nativo do **Maps** e permitir que ele seja invocado por aplicativos gerenciados do Intune, você deve adicionar uma exceção de transferência de dados à cadeia de caracteres a seguir: <code>maps</code>

- Exemplo do **Webex** do Android: para isentar o aplicativo **Webex** e permitir que ele seja invocado por aplicativos gerenciados do Intune, você deve adicionar uma exceção de transferência de dados à cadeia de caracteres a seguir: <code>com.cisco.webex.meetings</code>
    
- Exemplo de **SMS** do Android: para isentar o aplicativo nativo de **SMS** de modo que ele possa ser chamado por aplicativos gerenciados pelo Intune em dispositivos Android e aplicativos de mensagens diferentes, você deve adicionar exceções de transferência de dados para as seguintes cadeias de caracteres: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Próximas etapas

- [Criar e implantar as políticas de proteção do aplicativo](app-protection-policies.md)
- [Configurações de política de proteção de aplicativo iOS – Isenções de transferência de dados](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Configurações de política de proteção de aplicativo Android – Isenções de transferência de dados](app-protection-policy-settings-android.md#data-transfer-exemptions)
