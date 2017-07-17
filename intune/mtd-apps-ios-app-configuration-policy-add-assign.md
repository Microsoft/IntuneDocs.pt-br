---
title: Adicionar e atribuir aplicativos MTD ao Intune
titleSuffix: Intune on Azure
description: "Adicionar aplicativos MTD, o aplicativo Microsoft Authenticator e a política de configuração do iOS ao Intune no Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Adicionar e atribuir aplicativos MTD (Defesa contra Ameaças Móveis) com o Intune
<a id="add-and-assign-mobile-threat-defense-mtd-apps-with-intune" class="xliff"></a>

Você pode usar o Intune para adicionar e implantar aplicativos MTD para que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.

Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD. Além disso, você precisará da política de configuração de aplicativo iOS que indica qual aplicativo MTD iOS deve ser usado com o Intune.

> [!TIP]
> O Portal da Empresa do Intune funciona como o agente em dispositivos Android para as identidades dos usuários possam ser verificadas pelo Azure AD.

## Antes de começar
<a id="before-you-begin" class="xliff"></a>

-   As etapas a seguir devem ser concluídas no [Portal do Azure](https://portal.azure.com/).

-   Verifique se que você está familiarizado com o processo de:

    -   [Adicionar um aplicativo no Intune](apps-add.md).

    -   [Adicionar uma política de configuração de aplicativo do iOS no Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Atribuindo um aplicativo com o Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [ Adicionando uma política de configuração de aplicativo iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## Adicionar aplicativos
<a id="to-add-apps" class="xliff"></a>

### Aplicativo Skycure para Android
<a id="skycure-app-for-android" class="xliff"></a>

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos do Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) na **etapa 7**.

### Aplicativo Skycure para iOS
<a id="skycure-app-for-ios" class="xliff"></a>

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### Aplicativo Microsoft Authenticator para iOS
<a id="microsoft-authenticator-app-for-ios" class="xliff"></a>

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### Aplicativo Lookout for Work Android
<a id="lookout-for-work-android-app" class="xliff"></a>

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos da Google do Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) na **etapa 7**.

### Aplicativo Lookout for Work iOS
<a id="lookout-for-work-ios-app" class="xliff"></a>

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Lookout for Work iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### Aplicativo Lookout for Work fora da Apple store
<a id="lookout-for-work-app-outside-the-apple-store" class="xliff"></a>

Será necessário reassinar o aplicativo Lookout for Work iOS. O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store. Antes de distribuir o aplicativo, você deverá reassiná-lo com seu iOS Enterprise Developer Certificate.

Para obter instruções detalhadas sobre como reassinar o aplicativo Lookout for Work iOS, consulte [Processo para reassinar o aplicativo Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.

#### Habilitar a autenticação do Azure AD para o aplicativo Lookout for Work iOS
<a id="enable-azure-ad-authentication-for-lookout-for-work-ios-app" class="xliff"></a>

Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:

1. Acesse o [Portal do Azure](https://portal.sazure.com), entre com suas credenciais e navegue para a página do aplicativo.
  
2. Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.

3. Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.

4.  Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.

5.  Adicione **Permissões delegadas** ao aplicativo.

    > [!NOTE] 
    > Consulte [Configurar um aplicativo cliente nativo com o Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) para ver mais detalhes.

#### Adicionar o arquivo ipa do Lookout for Work
<a id="add-the-lookout-for-work-ipa-file" class="xliff"></a>

- Carregue o arquivo .ipa reassinado conforme descrito no tópico [Adicionar aplicativos iOS LOB com o Intune](lob-apps-ios.md). Também será necessário definir a versão mínima do sistema operacional para iOS 8.0 ou posterior.

## Associar o aplicativo MTD a uma política de configuração de aplicativo iOS
<a id="to-associate-the-mtd-app-with-an-ios-app-configuration-policy" class="xliff"></a>

### Para Skycure
<a id="for-skycure" class="xliff"></a>

-   Use a mesma conta do Azure AD previamente configurada no Console de gerenciamento do Skycure, que deve ser a mesma conta usada para fazer logon no console clássico do Intune.

-   O arquivo de integração do Skycure precisa estar pronto para uso. Este é o arquivo .zip baixado anteriormente do console de Gerenciamento do Skycure, que contém o arquivo **skycure\_configuration.plist** com os parâmetros da política de configuração de aplicativo do iOS.

- Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do Skycure.
    - Na etapa 8, use a opção **Inserir dados XML**, copie o conteúdo do arquivo **skycure_configuration.plist** e cole seu conteúdo no corpo da política de configuração.

Você também pode copiar o conteúdo **skycure_configuration.plist** aqui:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### Para Lookout
<a id="for-lookout" class="xliff"></a>

- Crie a política de configuração do aplicativo iOS conforme descrito no tópico [usando a política de configuração de aplicativo iOS](app-configuration-policies-use-ios.md).

## Atribuir aplicativos MTD
<a id="to-assign-mtd-apps" class="xliff"></a>

- Consulte as instruções para [atribuir aplicativos a grupos com o Intune](apps-deploy.md).

## Próximas etapas
<a id="next-steps" class="xliff"></a>

[Configurar a integração de Skycure com o Intune](skycure-mtd-connector-integration.md)
[Configurar a integração do Lookout com o Intune](lookout-mtd-connector-integration.md)
