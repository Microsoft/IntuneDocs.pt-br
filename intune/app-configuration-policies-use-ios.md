---
title: "Como usar políticas de configuração de aplicativo do Intune para o iOS"
titleSuffix: Intune on Azure
description: "Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a9d56a2f570c0332b394b03f25deb6351b6ba67
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Como usar as políticas de configuração de aplicativo do Microsoft Intune para o iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações usadas quando os usuários executam um aplicativo iOS. Por exemplo, um aplicativo pode exigir que os usuários especifiquem:

-   Um número da porta personalizado.

-   Configurações de idioma.

-   Configurações de segurança.

-   Configurações de identidade visual, como um logotipo da empresa.

Quando os usuários inserem essas configurações incorretamente, isso pode aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação. Os aplicativos devem ter sido escritos para dar suporte ao uso de configurações de aplicativo. Consulte o fornecedor do aplicativo para obter mais informações.

Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política serão usadas sempre que o aplicativo verificá-las, normalmente na primeira vez em que é executado.

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> -   **Aplicativo iOS gerenciado da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Criar uma política de configuração do aplicativo
1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Aplicativos móveis**.
4.  Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Políticas de Configuração de Aplicativos**.
5.  Na folha da lista de políticas, escolha **Adicionar**.
6.  Na folha **Adicionar Política de Configuração**, forneça um **Nome** e uma **Descrição** opcional para a política de configuração de aplicativo.
7.  Para o **Tipo de Registro do Dispositivo**, escolha uma das seguintes opções:
    - **Registrado com o Intune** – para aplicativos que são gerenciados pelo Intune.
    - **Não registrado com o Intune** – para aplicativos que não são gerenciados pelo Intune ou são gerenciados por outra solução.
8.  Para **Plataforma**, escolha **iOS** (apenas para dispositivos registrados com o Microsoft Intune)
9.  Escolha **Aplicativo associado** e, na folha **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração.
10. Na folha **Adicionar Política de Configuração**, escolha **Definições de configuração**
11. Na folha **Definições de configuração**, escolha como deseja especificar os valores de XML que compõem o perfil de configuração em:
    - **Inserir dados XML** (apenas para dispositivos registrados com o Microsoft Intune) – Digite ou cole uma lista de propriedades XML que contém as definições de configuração do aplicativo desejadas. O formato da lista de propriedades XML varia dependendo do aplicativo que você está configurando. Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.
O Intune verifica se o XML que você inseriu está em um formato válido. Ele não verifica se a lista de propriedades XML funcionará com o aplicativo ao qual está associada.
Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.
    - **Usar o Designer de Configuração** (dispositivos registrados ou não com o Microsoft Intune) – Permite especificar os pares de chave e valor XML diretamente no portal.
11. Após terminar, volte para a folha **Adicionar Política de Configuração** e selecione **Criar**.

A política será criada e exibida na folha da lista de políticas.



>[!Note]
>Use o [SDK do aplicativo do Intune](https://docs.microsoft.com/intune/app-sdk-ios) a fim de preparar aplicativos LOB para gerenciamento pelas políticas de proteção do aplicativo e pelas políticas de configuração de aplicativo do Microsoft Intune, para dispositivos registrados ou não por meio desta plataforma. Por exemplo, você pode usar uma política de configuração de aplicativo para configurar URLs bloqueadas e permitidas para o [Intune Managed Browser](app-configuration-managed-browser.md). Quando um aplicativo é compatível com essas políticas, você pode configurá-lo usando uma política.


Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração de aplicativo.
Confira a documentação do aplicativo que você está configurando para saber mais sobre o que acontece quando uma ou mais políticas de configuração de aplicativo são conflitantes.

>[!Tip]
>Além disso, você pode usar a API do Graph para realizar essas tarefas. Para saber mais, confira [Configuração direcionada do MAM na referência da API do Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).


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

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.