---
title: "Como usar políticas de configuração de aplicativo do Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 1e1f03a81d28d73476b64cef7af3b93e4d003697
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-use-microsoft-intune-app-configuration-policies"></a>Como usar as políticas de configuração de aplicativo do Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo. Por exemplo, um aplicativo pode exigir que os usuários especifiquem:

-   Um número da porta personalizado.

-   Configurações de idioma.

-   Configurações de segurança.

-   Configurações de identidade visual, como um logotipo da empresa.

Se os usuários inserirem essas configurações incorretamente, isso poderá aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e implanta o aplicativo. As configurações de política serão usadas sempre que o aplicativo verificá-las (normalmente, na primeira vez que é executado).

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> -   **Aplicativo iOS gerenciado da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](/intune-azure/manage-apps/add-apps).

## <a name="create-an-app-configuration-policy"></a>Criar uma política de configuração do aplicativo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
1.  Na carga de trabalho **Gerenciar aplicativos**, escolha **Gerenciar** > **Políticas de Configuração de Aplicativos**.

2.  Na folha da lista de políticas, escolha **Adicionar**.

3.  Na folha **Adicionar política de configuração**, forneça um nome e uma descrição opcional para a política de configuração do aplicativo.
4.  Escolha **Aplicativo associado** e, na folha **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração.
5.  Na folha **Adicionar política de configuração**, escolha **Definições de configurações** e, na folha Definições de configurações, escolha como você deseja especificar os valores de XML que compõem o perfil de configuração de:
    - **Inserir dados XML** – Digite ou cole uma lista de propriedades XML que contém as definições de configuração do aplicativo que você deseja. O formato da lista de propriedades XML vai variar dependendo do aplicativo que você está configurando. Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.
    O Intune verifica se o XML que você inseriu está em um formato válido. Ele não verifica se a lista de propriedades XML funcionará com o aplicativo a que está associada.
    Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.
    - **Usar o designer de configuração** – Permite que você especifique os pares de chave e valor XML diretamente no portal.
8. Após terminar, volte para a folha **Adicionar Política de Configuração** e selecione **Criar**.

A política será criada e aparecerá na folha da lista de políticas.

Em seguida, continue a [Atribuir](deploy-apps.md) e a [Monitor](monitor-apps.md) o aplicativo como de costume.

Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo.

> [!TIP]
> Se uma ou mais políticas de configuração de aplicativo entrarem em conflito, nenhuma delas será aplicada.

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





## <a name="example-format-for-an-app-configuration-xml-file"></a>Exemplo de formato de arquivo XML de configuração de aplicativo

Quando você cria um arquivo de configuração de aplicativo, você pode especificar um ou mais dos seguintes valores usando este formato:

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

