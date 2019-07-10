---
title: Adicionar e atribuir aplicativos MTD ao Microsoft Intune
titleSuffix: Microsoft Intune
description: Use o Intune para adicionar aplicativos de MTD (Defesa contra Ameaças Móveis), o aplicativo Microsoft Authenticator e a política de configuração do iOS no Portal do Azure.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fdc7434616db6c06f56438fb6d8774ae3f2deca9
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548427"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Adicionar e atribuir aplicativos MTD (Defesa contra Ameaças Móveis) com o Intune  

> [!NOTE] 
> Este artigo aplica-se a todos os parceiros de Defesa contra Ameaças Móveis.

Use o Intune para adicionar e implantar aplicativos MTD (Defesa contra Ameaças Móveis), de modo que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber diretrizes de correção das ameaças.

## <a name="before-you-begin"></a>Antes de começar    
As etapas a seguir devem ser concluídas no [Portal do Azure](https://portal.azure.com/). Verifique se que você está familiarizado com o processo de:

- [Adicionar um aplicativo no Intune](apps-add.md).
- [Adicionar uma política de configuração de aplicativo do iOS no Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
- [Atribuindo um aplicativo com o Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

> [!TIP]
> O Portal da Empresa do Intune funciona como o agente em dispositivos Android, de modo que os usuários possam ter suas identidades verificadas pelo Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>Configurar o Microsoft Authenticator para iOS  
Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD. Além disso, você precisará de uma política de configuração de aplicativo do iOS que define o aplicativo MTD do iOS usado com o Intune.

Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) na **etapa 12** na seção **Configurar informações de aplicativo**.

## <a name="configure-mtd-applications"></a>Configurar aplicativos MTD  
Escolha a seção que corresponde ao seu provedor MTD:

- [Lookout for Work](#configure-lookout-for-work-apps)
- [SEP (Symantec Endpoint Protection) Mobile](#configure-symantec-endpoint-protection-mobile-apps)
- [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
- [Zimperium](#configure-zimperium-apps)
- [Pradeo](#configure-pradeo-apps)
- [Better Mobile](#configure-better-mobile-apps)
- [Sophos Mobile](#configure-sophos-apps)
- [Wandera](#configure-wandera-apps)

### <a name="configure-lookout-for-work-apps"></a>Configurar aplicativos do Lookout for Work  
- **Android**  
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos da Google do Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) na **etapa 7**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o Lookout for Work iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) na **etapa 11** para a **URL da Appstore**.

- **Aplicativo Lookout for Work fora da Apple Store**  
  - Será necessário reassinar o aplicativo Lookout for Work iOS. O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store. Antes de distribuir o aplicativo, você deverá reassiná-lo com seu iOS Enterprise Developer Certificate.  
  - Para obter instruções detalhadas sobre como reassinar o aplicativo Lookout for Work iOS, consulte [Processo para reassinar o aplicativo Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.

  - **Habilitar a autenticação do Azure AD para usuários do aplicativo Lookout for Work para iOS.**

    1. Acesse o [Portal do Azure](https://portal.azure.com), entre com suas credenciais e navegue para a página do aplicativo.

    2. Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.

    3. Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.

    4. Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.

    5. Adicione **Permissões delegadas** ao aplicativo.

    > [!NOTE] 
    > Consulte [Configurar um aplicativo cliente nativo com o Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) para ver mais detalhes.

  - **Adicionar o arquivo ipa do Lookout for Work.**

    - Carregue o arquivo .ipa reassinado conforme descrito no artigo [Adicionar aplicativos iOS LOB com o Intune](lob-apps-ios.md). Também será necessário definir a versão mínima do sistema operacional para iOS 8.0 ou posterior.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Configurar aplicativos do Symantec Endpoint Protection Mobile  
- **Android**
   - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Na **etapa 7**, use esta [URL da loja de aplicativo SEP Mobile](https://play.google.com/store/apps/details?id=com.skycure.skycure).  Para **sistema de operacional mínimo**, selecione **Android 4.0 (Ice Cream Sandwich)** .

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o SEP Mobile](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) na **etapa 11** para a **URL da Appstore**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Configurar aplicativos do Check Point SandBlast Mobile  
- **Android**  
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da App Store para o SandBlast Mobile da Check Point](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) na **etapa 7**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da App Store para o SandBlast Mobile da Check Point](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) na **etapa 11** para a **URL da Appstore**.  

### <a name="configure-zimperium-apps"></a>Configurar aplicativos do Zimperium  
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos para o Zimperium](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) na **etapa 7**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) na **etapa 11** para a **URL da Appstore**.  
 
### <a name="configure-pradeo-apps"></a>Configurar aplicativos do Pradeo  
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos do Pradeo](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) na **etapa 7**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o Pradeo](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) na **etapa 11** para a **URL da Appstore**.

### <a name="configure-better-mobile-apps"></a>Configurar aplicativos Better Mobile  
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos do Active Shield](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) na **etapa 7**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o ActiveShield](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) na **etapa 11** para a **URL da Appstore**.

### <a name="configure-sophos-apps"></a>Configurar aplicativos Sophos  
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos do Sophos](https://play.google.com/store/apps/details?id=com.sophos.smsec) na **etapa 7**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos para o ActiveShield](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) na **etapa 11** para a **URL da Appstore**.

### <a name="configure-wandera-apps"></a>Configurar aplicativos Wandera  
 
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos móveis Wandera](https://play.google.com/store/apps/details?id=com.wandera.android) na **etapa 7**. Para o **Sistema operacional mínimo**, selecione **Android 5.0**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](https://docs.microsoft.com/intune/store-apps-ios). Use esta [URL da loja de aplicativos móveis Wandera](https://itunes.apple.com/app/wandera/id605469330) na **etapa 11** para a **URL da Appstore**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Configurar os aplicativos MTD com uma política de configuração de aplicativo do iOS  

### <a name="lookout-for-work-app-configuration-policy"></a>Política de configuração de aplicativo do Lookout for Work  
- Crie a política de configuração de aplicativo do iOS, conforme descrito no artigo [Usando a política de configuração de aplicativo do iOS](app-configuration-policies-use-ios.md).

### <a name="sep-mobile-app-configuration-policy"></a>Política de configuração de aplicativo do SEP Mobile  
- Use a mesma conta do Azure AD configurada anteriormente no [Console de Gerenciamento do Symantec Endpoint Protection](https://aad.skycure.com), que deverá ser a mesma conta usada para entrar no portal clássico do Intune.

- **Baixe** o arquivo da política de configuração de aplicativo do iOS: 
  - Vá para o [console do Symantec Endpoint Protection Management](https://aad.skycure.com) e entre com as suas credenciais de administrador.

  - Vá para **Configurações** e, em **Integrações**, escolha **Intune**. Escolha **Seleção de Integração EMM**. Escolha **Microsoft** e, em seguida, salve sua seleção.

  - Clique no link **Arquivos de configuração de integração** e salve o arquivo \*.zip gerado. O arquivo .zip contém o arquivo * **.plist** que será usado para criar a política de configuração de aplicativo iOS no Intune.

  - Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do SEP Mobile.

  - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo do arquivo ***.plist** e cole-o no corpo da política de configuração.

> [!NOTE]  
> Se não for possível recuperar os arquivos, entre em contato com o [Suporte ao Symantec Endpoint Protection Mobile Enterprise](https://support.symantec.com/en_US/contact-support.html).

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Política de configuração de aplicativo do Check Point SandBlast Mobile  
- Confira instruções sobre [como usar as políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) a fim de adicionar a política de configuração de aplicativo do iOS para o SandBlast Mobile da Check Point.
    - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo abaixo e cole-o no corpo da política de configuração.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="zimperium-app-configuration-policy"></a>Política de configuração de aplicativo do Zimperium  
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

### <a name="pradeo-app-configuration-policy"></a>Política de configuração de aplicativos do Pradeo  
O Pradeo não dá suporte à política de configuração de aplicativo no iOS.  Em vez disso, para obter um aplicativo configurado, trabalhe com o Pradeo para implementar arquivos personalizados de IPA ou APK que são pré-configurados com as configurações desejadas.

### <a name="better-mobile-app-configuration-policy"></a>Política de configuração de aplicativo do Better Mobile  
- Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do Better Mobile.
  - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo abaixo e cole-o no corpo da política de configuração. Substitua a URL `https://client.bmobi.net` pela URL do console apropriado.

```
<dict>
<key>better_server_url</key>
<string>https://client.bmobi.net</string>
<key>better_udid</key>
<string>{{aaddeviceid}}</string>
<key>better_user</key>
<string>{{userprincipalname}}</string>
</dict>
```

### <a name="sophos-mobile-app-configuration-policy"></a>Política de configuração de aplicativos do Sophos Mobile  
Crie a política de configuração de aplicativo do iOS, conforme descrito no artigo [Usando a política de configuração de aplicativo do iOS](app-configuration-policies-use-ios.md).

### <a name="wandera-app-configuration-policy"></a>Política de configuração de aplicativos Wandera  
Confira as instruções para [usar políticas de configuração de aplicativos do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativos iOS Wandera.
- Na **etapa 8**, use a opção **Inserir dados XML**. Entre no portal do RADAR Wandera e navegue até **Configurações** > **Integração de EMM** > **Push de Aplicativo**. Selecione **Intune** e, em seguida, copie o conteúdo abaixo e cole-o no corpo da política de configuração.  

  ```
  <dict><key>secretKey</key>
  <string>SeeRADAR</string>
  <key>apiKey</key>
  <string> SeeRADAR </string>
  <key>customerId</key>
  <string> SeeRADAR </string>
  <key>email</key>
  <string>{{mail}}</string>
  <key>firstName</key>
  <string>{{username}}</string>
  <key>lastName</key>
  <string></string>
  <key>activationType</key>
  <string>PROVISION_THEN_AWP</string></dict>  
  ```

## <a name="assign-apps-to-groups"></a>Atribuir aplicativos a grupos  
- Esta etapa se aplica a todos os parceiros MTD. Confira instruções sobre [como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

## <a name="next-steps"></a>Próximas etapas  
- [Configurar a política de conformidade do dispositivo para MTD](mtd-device-compliance-policy-create.md)
