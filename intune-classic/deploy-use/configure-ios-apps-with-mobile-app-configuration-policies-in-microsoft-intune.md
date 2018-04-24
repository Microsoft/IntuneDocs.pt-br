---
title: Usar políticas de configuração de aplicativo móvel do iOS
description: Use políticas de configuração de aplicativo móvel no Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo iOS.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 02e821f24c378c15a474adda901699664a9af68a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Use políticas de configuração de aplicativo móvel no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo. Por exemplo, um aplicativo pode exigir que os usuários especifiquem:

-   Um número da porta personalizado.

-   Configurações de idioma.

-   Configurações de segurança.

-   Configurações de identidade visual, como um logotipo da empresa.

Se os usuários inserirem essas configurações incorretamente, isso poderá aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

Políticas de configuração de aplicativo móvel podem ajudar a eliminar esses problemas, permitindo que você implante essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

Você não implanta essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e implanta o aplicativo. As configurações de política serão usadas sempre que o aplicativo verificá-las (normalmente, na primeira vez que é executado).

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> -   **Aplicativo iOS gerenciado da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Deploy apps with Microsoft Intune](deploy-apps.md) (Implantar aplicativos com o Microsoft Intune).

## <a name="configure-a-mobile-app-configuration-policy"></a>Configurar uma política de configuração do aplicativo móvel

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.

2.  Na lista de políticas, expanda **iOS**, escolha **Configuração do Aplicativo Móvel** e, em seguida, escolha **Criar Política**.

    > [!TIP]
    > Você só pode definir configurações personalizadas para esse tipo de política. Configurações recomendadas não estão disponíveis.

3.  Na seção **Geral** da página **Criar Política**, forneça um nome e uma descrição opcional para a política de configuração de aplicativo móvel.

4.  Na seção **Política de Configuração de Aplicativo Móvel** da página, na caixa, digite ou cole uma lista de propriedades XML que contenha as definições de configuração do aplicativo que você quer. O formato da lista de propriedades XML vai variar dependendo do aplicativo que você está configurando. Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.

    > [!TIP]
    > Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.

5.  Clique em **Validar** para garantir que o XML que você inseriu está em um formato de lista de propriedades válido.

    > [!IMPORTANT]
    > Quando você clica em **Validar**, o Intune verifica se o XML que você inseriu está em um formato válido. Ele não verifica se a lista de propriedades XML funcionará com o aplicativo a que está associada.

6.  Quando terminar, clique em **Salvar Política**.

A nova política é exibida no nó **Políticas de Configuração** .

## <a name="information-about-the-xml-file-format"></a>Informações sobre o formato de arquivo XML

O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:

- &lt;inteiro&gt;
- &lt;real&gt;
- &lt;cadeia de caracteres&gt;
- &lt;matriz&gt;
- &lt;dict&gt;
- &lt;true /&gt; ou &lt;false /&gt;

Para obter mais informações sobre tipos de dados, consulte o artigo [sobre listas de propriedades](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) na biblioteca do desenvolvedor do iOS.

Além disso, o Intune dá suporte aos seguintes tipos de token na lista de propriedades:
- \{\{userprincipalname\}\} – (Exemplo: **John@contoso.com**)
- \{\{mail\}\} – (Exemplo: **John@contoso.com**)
- \{\{partialupn\}\} – (Exemplo: **Samuel**)
- \{\{accountid\}\} – (Exemplo: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Exemplo: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Exemplo: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Exemplo: **Samuel Ferreira**)
- \{\{serialnumber\}\} – (Exemplo: **F4KN99ZUG5V2**) para dispositivos iOS
- \{\{serialnumberlast4digits\}\} – (Exemplo: **G5V2**) para dispositivos iOS

Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

## <a name="associate-a-mobile-app-configuration-policy-with-an-app"></a>Associar uma política de configuração de aplicativo móvel a um aplicativo
Depois de criar uma política de configuração do aplicativo móvel, você deve associá-la ao aplicativo iOS ao qual você deseja aplicar as definições da política de configuração.

Para fazer isso, siga as etapas para criar uma implantação de aplicativo em [Adicionar aplicativos para dispositivos registrados ao Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) e [Implantar aplicativos com o Microsoft Intune](deploy-apps-in-microsoft-intune.md). Quando você chegar à página **Configuração do Aplicativo Móvel** do assistente, selecione a política que deseja associar ao aplicativo na lista suspensa **Política de Configuração do Aplicativo**.

Em seguida, continue a implantar e monitorar a implantação de aplicativo como de costume.

Quando o aplicativo implantado é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo móvel.

> [!TIP]
> Se uma ou mais políticas de configuração de aplicativo móvel entrarem em conflito, nenhuma delas será aplicada. O conflito será relatado no **Painel** do console de administração do Intune.

## <a name="example-format-for-a-mobile-app-configuration-xml-file"></a>Exemplo de formato de um arquivo XML de configuração de aplicativo móvel

Quando você cria um arquivo de configuração de aplicativo móvel, você pode especificar um ou mais dos seguintes valores usando este formato:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>
```
