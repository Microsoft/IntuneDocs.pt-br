---
title: Adicionar e atribuir aplicativos MTD ao Microsoft Intune
titleSuffix: 
description: "Use o Intune para adicionar aplicativos de MTD (Defesa contra Ameaças Móveis), o aplicativo Microsoft Authenticator e a política de configuração do iOS no Portal do Azure."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3fc71620fee1b1df907a4027c1c57cd91b53032e
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Adicionar e atribuir aplicativos MTD (Defesa contra Ameaças Móveis) com o Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

Você pode usar o Intune para adicionar e implantar aplicativos MTD para que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.

Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD. Além disso, você precisará da política de configuração de aplicativo iOS que indica qual aplicativo MTD iOS deve ser usado com o Intune.

> [!TIP]
> O Portal da Empresa do Intune funciona como o agente em dispositivos Android para as identidades dos usuários possam ser verificadas pelo Azure AD.

## <a name="before-you-begin"></a>Antes de começar

-   As etapas a seguir devem ser concluídas no [Portal do Azure](https://portal.azure.com/).

-   Verifique se que você está familiarizado com o processo de:

    -   [Adicionar um aplicativo no Intune](apps-add.md).

    -   [Adicionar uma política de configuração de aplicativo do iOS no Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Atribuindo um aplicativo com o Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [ Adicionando uma política de configuração de aplicativo iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Adicionar aplicativos

### <a name="all-mtd-partners"></a>Todos os parceiros de MTD

#### <a name="microsoft-authenticator-app-for-ios"></a>Aplicativo Microsoft Authenticator para iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos da Google do Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) na **etapa 7**.

#### <a name="ios"></a>iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Lookout for Work iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Aplicativo Lookout for Work fora da Apple store

Será necessário reassinar o aplicativo Lookout for Work iOS. O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store. Antes de distribuir o aplicativo, você deverá reassiná-lo com seu iOS Enterprise Developer Certificate.

Para obter instruções detalhadas sobre como reassinar o aplicativo Lookout for Work iOS, consulte [Processo para reassinar o aplicativo Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Habilitar a autenticação do Azure AD para o aplicativo Lookout for Work iOS

Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:

1. Acesse o [Portal do Azure](https://portal.azure.com), entre com suas credenciais e navegue para a página do aplicativo.
  
2. Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.

3. Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.

4.  Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.

5.  Adicione **Permissões delegadas** ao aplicativo.

    > [!NOTE] 
    > Consulte [Configurar um aplicativo cliente nativo com o Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) para ver mais detalhes.

##### <a name="add-the-lookout-for-work-ipa-file"></a>Adicionar o arquivo ipa do Lookout for Work

- Carregue o arquivo .ipa reassinado conforme descrito no tópico [Adicionar aplicativos iOS LOB com o Intune](lob-apps-ios.md). Também será necessário definir a versão mínima do sistema operacional para iOS 8.0 ou posterior.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos do Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) na **etapa 7**.

#### <a name="ios"></a>iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### <a name="check-point-sandblast-mobile"></a>SandBlast Mobile da Check Point

#### <a name="android"></a>Android

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da App Store para o SandBlast Mobile da Check Point](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) na **etapa 7**.

#### <a name="ios"></a>iOS

- Contate o [SandBlast Mobile da Check Point](https://www.checkpoint.com/products/sandblast-mobile/) a fim de obter o aplicativo iOS. Confira instruções sobre [como adicionar aplicativos da iOS Store ao Microsoft Intune](store-apps-ios.md) e use a URL da Apple Store na **etapa 5**, na seção **Informações de configuração do aplicativo**.

### <a name="zimperium"></a>Zimperium

#### <a name="android"></a>Android

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos para o Zimperium](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) na **etapa 7**.

#### <a name="ios"></a>iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Associar o aplicativo MTD a uma política de configuração de aplicativo iOS

### <a name="for-lookout"></a>Para Lookout

- Crie a política de configuração do aplicativo iOS conforme descrito no tópico [usando a política de configuração de aplicativo iOS](app-configuration-policies-use-ios.md).

### <a name="for-skycure"></a>Para Skycure

-   Use a conta do Azure AD configurada anteriormente no [Console de Gerenciamento do Skycure](https://aad.skycure.com), que deve ser a mesma conta usada para entrar no Portal Clássico do Intune.

-   É necessário **baixar** o arquivo da política de configuração de aplicativo do iOS: 
    -   Vá para o [Console de Gerenciamento do Skycure](https://aad.skycure.com) e entre com as Credenciais de Administrador.
    
    -   Acesse **Configurações** &gt; **Integrações de Gerenciamento de Dispositivo** &gt; **Seleção de Integração EMM**, escolha **Microsoft Intune** e salve sua seleção.
    
    -   Clique no link **Arquivos de configuração da integração** e salve o arquivo \*.zip gerado. O arquivo .zip contém o arquivo **skycure\_configuration.plist**, que será usado para criar a política de configuração de aplicativo do iOS no Microsoft Intune.
    
    -   Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do Skycure.
    
    - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo do arquivo **skycure_configuration.plist** e cole-o no corpo da política de configuração.

Você também pode copiar o conteúdo **skycure_configuration.plist** aqui:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-check-point-sandblast-mobile"></a>Para o SandBlast Mobile da Check Point

- Confira instruções sobre [como usar as políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) a fim de adicionar a política de configuração de aplicativo do iOS para o SandBlast Mobile da Check Point.
    - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo abaixo e cole-o no corpo da política de configuração.

```
<dict><key>MDM</key><string>INTUNE</string></dict>

```

### <a name="for-zimperium"></a>Para o Zimperium

- Consulte as instruções sobre como [usar as políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração do aplicativo iOS do Zimperium.
    - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo abaixo e cole-o no corpo da política de configuração.

```
<dict>
<key>provider</key><string>Intune</string>
<key>userprincipalname</key><string>{{userprincipalname}}</string>
<key>deviceid</key>
<string>{{deviceid}}</string>
<key>serialnumber</key>
<string>{{serialnumber}}</string>
<key>udidlast4digits</key>
<string>{{udidlast4digits}}</string>
</dict>

```

## <a name="to-assign-apps-all-mtd-partners"></a>Para atribuir aplicativos (todos os parceiros de MTD)

- Confira instruções sobre [como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

## <a name="next-steps"></a>Próximas etapas

- [Adicionar política de conformidade do dispositivo para MTD](mtd-device-compliance-policy-create.md)
