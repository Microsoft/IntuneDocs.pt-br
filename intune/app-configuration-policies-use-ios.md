---
title: "Como usar políticas de configuração de aplicativo do Intune para o iOS"
titleSuffix: Intune on Azure
description: "Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Como usar as políticas de configuração de aplicativo do Microsoft Intune para o iOS
<a id="how-to-use-microsoft-intune-app-configuration-policies-for-ios" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo iOS. Por exemplo, um aplicativo pode exigir que os usuários especifiquem:

-   Um número da porta personalizado.

-   Configurações de idioma.

-   Configurações de segurança.

-   Configurações de identidade visual, como um logotipo da empresa.

Se os usuários inserirem essas configurações incorretamente, isso poderá aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política serão usadas sempre que o aplicativo verificá-las (normalmente, na primeira vez que é executado).

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> -   **Aplicativo iOS gerenciado da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).

## Criar uma política de configuração do aplicativo
<a id="create-an-app-configuration-policy" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1.  Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Políticas de Configuração de Aplicativos**.

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

Em seguida, continue a [Atribuir](apps-deploy.md) e a [Monitor](apps-monitor.md) o aplicativo como de costume.

Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo.

> [!TIP]
> Se uma ou mais políticas de configuração de aplicativo entrarem em conflito, nenhuma delas será aplicada.

## Criar uma política de configuração direcionada para o MAM
<a id="create-a-mam-targeted-configuration-policy" class="xliff"></a>
A configuração voltada para MAM permite que um aplicativo receba dados de configuração por meio do SDK do aplicativo do Intune. O formato e as variantes desses dados devem ser definidos e comunicados aos clientes do Intune pelo proprietário/desenvolvedor do aplicativo. Os administradores do Intune podem direcionar e implantar dados de configuração por meio do console do Intune Azure. Os dados de configuração direcionada para o MAM podem ser fornecidos por meio do Serviço MAM para aplicativos habilitados para MAM-WE. Por exemplo, o [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser) permitiu/bloqueou a lista de URLs. Os dados de configuração de aplicativo são enviados por push por meio de nosso Serviço MAM diretamente para o aplicativo em vez de pelo canal MDM. As [políticas de configuração de aplicativo do MDM](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) são a solução nativa por meio de MDM. A principal diferença com a configuração direcionada para o MAM é que o dispositivo em que o aplicativo é executado não precisa ser registrado pelo MDM. A configuração direcionada para o MAM está disponível no iOS e no Android. Para iOS, o aplicativo deve incorporam o SDK do Intune APP para iOS (v 7.0.1) e estar participando de definições de configuração do aplicativo. As etapas para criar uma política de configuração direcionada para o MAM são as seguintes: 

1. Entre no **portal do Azure**.

2. Escolha **Intune > Aplicativos móveis – Políticas de configuração de aplicativo**.

3. Na folha **Políticas de configuração de aplicativo**, escolha **Adicionar**.

4. Insira um **Nome** e uma **Descrição** opcional para as definições de configuração de aplicativo e escolha **Não registrado no Intune**.

5. Escolha **Selecionar aplicativos necessários** e, em seguida, na folha de aplicativos **Direcionados**, escolha aplicativos para as plataformas desejadas. <br>
**Observação:** para aplicativos LOB, selecione **Mais aplicativos**. Insira a ID de pacote do aplicativo.

6. Escolha **OK** para retornar à folha **Adicionar configuração de aplicativo**.

7. Escolha **Definir configuração**. Na folha **Configuração**, defina os pares de chave e valor para fornecer as configurações.

8. Quando terminar, escolha **OK**.

9. Na **folha Adicionar configuração de aplicativo**, escolha **Criar**.

A nova configuração é criada e exibida na folha Configuração de aplicativo.

Em seguida, continue a [Atribuir](apps-deploy.md) e a [Monitor](apps-monitor.md) o aplicativo como de costume.

Quando o aplicativo atribuído (integrado ao SDK do Aplicativo do Intune) for executado em um dispositivo, ele será executado com as configurações definidas na política de configuração direcionada para o MAM. O aplicativo atribuído precisa ter integrado a versão com suporte do SDK do Aplicativo do Intune. Para obter mais informações sobre os requisitos de desenvolvimento de aplicativo para usar políticas de Configuração Direcionada para o MAM, consulte [Guia de integração do SDK do Aplicativo do Intune para iOS](https://docs.microsoft.com/intune/app-sdk-ios).

Para obter mais informações sobre as funcionalidades de nossa API do Graph em relação aos valores de configuração direcionada para o MAM, consulte [Referência da API do Graph para a Configuração Direcionada para o MAM](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## Informações sobre o formato de arquivo XML
<a id="information-about-the-xml-file-format" class="xliff"></a>

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

## Exemplo de formato de arquivo XML de configuração de aplicativo
<a id="example-format-for-an-app-configuration-xml-file" class="xliff"></a>

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
