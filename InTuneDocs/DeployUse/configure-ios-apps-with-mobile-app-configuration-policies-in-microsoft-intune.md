---
# required metadata

title: Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune
Use políticas de configuração de aplicativo móvel no Microsoft Intune para fornecer as configurações que possam ser necessárias quando o usuário executar um aplicativo. Por exemplo, um aplicativo pode exigir que o usuário especifique:

-   Um número da porta personalizada quando ele é executado

-   Configurações de idioma

-   Configurações de segurança

-   Configurações de identidade visual, como um logotipo da empresa

Se essas configurações forem inseridas incorretamente pelo usuário, isso pode aumentar a carga do suporte técnico e também reduzir a adoção de novos aplicativos.

Políticas de configuração de aplicativo móvel podem ajudar a eliminar esses problemas, permitindo que você implante essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e o usuário não precisa executar nenhuma ação.

Você não implanta essas políticas diretamente para usuários e dispositivos. Em vez disso, você associar a política um aplicativo e implanta o aplicativo. As configurações de política serão usadas sempre que o aplicativo verificá-las (normalmente, na primeira vez que é executado).

> [!TIP]
> Esse tipo de política está atualmente disponível somente a dispositivos que executam iOS 7.1 e mais recente e tem suporte para os seguintes tipos de instalação do aplicativo:
> 
> -   **Aplicativo iOS gerenciados da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
> 
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Deploy apps with Microsoft Intune](deploy-apps.md) (Implantar aplicativos com o Microsoft Intune).

## Configurar uma política de configuração do aplicativo móvel

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Visão Geral** &gt; **Adicionar Política**.

2.  Na lista de políticas, expanda **iOS**, clique em **Configuração do Aplicativo Móvel** e, em seguida, clique em **Criar Política**.

    > [!TIP]
    > Você só pode definir configurações personalizadas para esse tipo de política. Configurações recomendadas não estão disponíveis.

3.  Na seção **Geral** da página **Criar Política** , forneça um nome e uma descrição opcional para a política de configuração de aplicativo móvel.

4.  Na seção **Política de Configuração de Aplicativo Móvel** da página, digite ou cole uma lista de propriedades XML que contenham as definições de configuração do aplicativo que você quer na caixa.

    > [!TIP]
    > Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.
    > 
    > O formato da lista de propriedades XML vai variar dependendo do aplicativo que você está configurando. Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.
    > 
    > O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:
    > 
    > &lt;integer&gt;
    > &lt;real&gt;
    > &lt;cadeia de caracteres&gt;
    > &lt;array&gt;
    > &lt;dict&gt;
    > &lt;true /&gt; ou &lt;false /&gt;
    > 
    > Para obter mais informações sobre tipos de dados, consulte o artigo [sobre listas de propriedades](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) na biblioteca do desenvolvedor do iOS.
    >
        > Além disso, o Intune dá suporte aos seguintes tipos de token na lista de propriedades:
    >    
    > \{\{userprincipalname\}\} - (Exemplo: **John@contoso.com**)
    > \{\{mail\}\} - (Exemplo: **John@contoso.com**)
    > \{\{partialupn\}\} - (Exemplo: **John**)
    > \{\{accountid\}\} - (Exemplo: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
    > \{\{deviceid\}\} - (Exemplo: **b9841cd9-9843-405f-be28-b2265c59ef97**)
    > \{\{userid\}\} - (Exemplo: **3ec2c00f-b125-4519-acf0-302ac3761822**)
    > \{\{username\}\} - (Exemplo: **John Doe**)
    > \{\{serialnumber\}\} - (Exemplo: **F4KN99ZUG5V2**) para dispositivos iOS
    > \{\{serialnumberlast4digits\}\} - (Exemplo: **G5V2**) para dispositivos iOS
>
> Os caracteres \{\{ e \}\} são usados por tipos de token apenas e não devem ser usados para outras finalidades.




5.  Clique em **Validar** para garantir que o XML que você inseriu está em um formato de lista de propriedade válido.

    > [!IMPORTANT]
    > Quando você clica em **Validar**, o Intune verifica se o XML que você inseriu está em um formato válido. Ele não verifica se a lista de propriedades XML funcionará com o aplicativo associado.

6.  Quando terminar, clique em **Salvar Política**.

A nova política é exibida no nó **Políticas de Configuração** .

## Associar uma política de configuração de aplicativo móvel a um aplicativo
Depois de criar uma política de configuração do aplicativo móvel, você deve associá-la ao aplicativo iOS ao qual você deseja aplicar as definições da política de configuração.

Para fazer isso, siga as etapas para criar uma implantação de aplicativo em [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Adicionar aplicativos para dispositivos móveis no Microsoft Intune) e [Deploy apps with Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos com o Microsoft Intune). Quando você chegar à página **Configuração do Aplicativo Móvel** do assistente, selecione a política que deseja associar ao aplicativo na lista suspensa **Política de Configuração do Aplicativo**.

Em seguida, continue a implantar e monitorar a implantação de aplicativo como de costume.

Quando o aplicativo implantado é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo móvel.

> [!TIP]
> Se uma ou mais políticas de configuração de aplicativo móvel estiverem em conflito, nenhuma política será aplicada e o conflito será relatado no **Painel** do console de administração do Intune.

## Exemplo de formato de arquivo XML de configuração de aplicativo móvel

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




<!--HONumber=May16_HO1-->


