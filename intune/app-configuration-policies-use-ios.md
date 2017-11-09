---
title: "Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados | Microsoft Docs"
titlesuffix: Azure portal
description: "Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d293ff6001ef937c7da0055e6642aa5a1226bd2e
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações quando os usuários executam um aplicativo iOS. Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> -   **Aplicativo iOS gerenciado da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Criar uma política de configuração do aplicativo

1. Entre no Portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
3. Selecione a carga de trabalho de **Aplicativos móveis**.
4. Clique em **Políticas de configuração de aplicativo**, no grupo **Gerenciar** e, em seguida, clique em **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome**  
      O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**  
      A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro de dispositivo**  
      Selecione **Dispositivos gerenciados**.
6. Selecione **iOS** para a **Plataforma**.
7.  Escolha **Aplicativo associado** e, na folha **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração.
8.  Na folha **Adicionar Política de Configuração**, escolha **Definições de configuração**
9. Selecione **Formato de definições de configuração**. Selecione um:
    - **[Usar o designer de configuração](#Use-the-configuration-designer)**
    - **[Inserir dados XML](#enter-xml-data)**
10. Clique em **OK** e em **Adicionar**.

## <a name="use-configuration-designer"></a>Usar o designer de configuração

Você pode usar o designer de configuração para aplicativos em dispositivos que são registrados ou não registrados no Intune. O designer permite que você configure valores e chaves de configuração específicos. Você também deve especificar o tipo de dados para cada valor. As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.

### <a name="add-a-setting"></a>Adicionar uma configuração

1. Para cada chave e valor na configuração, defina: <ul><li>**Chave de configuração**<br>Isso é usado para identificar exclusivamente a configuração específica.</li><li>**Tipo de Valor**<br>O tipo de dados do valor de configuração. Os tipos incluem Inteiro, Real, Cadeia de caracteres ou Booliano.</li><li>**Valor da configuração**<br>O valor para a configuração.</li></ul>
2. Clique em **OK** para definir as configurações.

### <a name="delete-a-setting"></a>Excluir uma configuração

1. Clique nas reticências (...) ao lado da configuração.
2. Selecione **Excluir**.

Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

## <a name="enter-xml-data"></a>Inserir dados XML

Você pode digitar ou colar uma lista de propriedades XML que contém as definições de configuração do aplicativo para dispositivos registrados no Intune. O formato da lista de propriedades XML varia dependendo do aplicativo que você está configurando. Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.

O Intune valida o formato XML. No entanto, o Intune não verifica se a lista de propriedades XML funcionará com o aplicativo de destino.
Para obter mais informações sobre listas de propriedades XML, consulte o artigo [Compreensão de listas de propriedades XML]

Para saber mais sobre listas de propriedades XML:

  -  Leia [Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Consulte [Compreender XML Plist](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na Biblioteca do Desenvolvedor iOS.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Exemplo de formato de arquivo XML de configuração de aplicativo

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
### <a name="supported-xml-plist-data-types"></a>Tipos de dados XML PList com suporte

O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:

- &lt;inteiro&gt;
- &lt;real&gt;
- &lt;cadeia de caracteres&gt;
- &lt;matriz&gt;
- &lt;dict&gt;
- &lt;true /&gt; ou &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Tokens usados na lista de propriedades

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

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.