---
title: Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados
titlesuffix: Microsoft Intune
description: Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3e81b52f10bb94d90d5f66ca5aee13daaf4941e
ms.sourcegitcommit: cefa84efd3003fa5a0ef0c2dce6206a6a411a1ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "35232226"
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer definições de configuração personalizadas para um aplicativo iOS. Essas definições de configuração permitem que um aplicativo seja personalizado com base na orientação dos fornecedores. É necessário obter essas definições de configuração (chaves e valores) do fornecedor do aplicativo. Para configurar o aplicativo, especifique as configurações como chaves e valores ou como um XML que contém as chaves e os valores. Além disso, você não atribui essas políticas de configuração diretamente a usuários e dispositivos. Em vez disso, você associa uma política de configuração a um aplicativo e, em seguida, atribui o aplicativo. As definições da política de configuração são usadas quando o aplicativo verifica se elas existem, normalmente, na primeira vez em que ele é executado.

Depois de adicionar uma política de configuração de aplicativo, você pode definir as atribuições para política de configuração de aplicativo. Ao definir as atribuições para a política, você pode optar por incluir ou excluir os grupos de usuários para os quais a política se aplica. Ao optar por incluir um ou mais grupos, você pode optar por selecionar grupos específicos para incluir ou selecionar grupos internos. Os grupos internos incluem **Todos os Usuários**, **Todos os Dispositivos** e **Todos os Usuários + Todos os Dispositivos**. 

>[!NOTE]
>O Intune fornece os grupos **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console, com otimizações internas para sua conveniência. É altamente recomendável usar esses grupos para destinar a todos os usuários e todos os dispositivos em vez de usar outros grupos "Todos os usuários" e "Todos os dispositivos" que você mesmo tenha criado.

Depois de selecionar os grupos incluídos para sua política de configuração de aplicativo, você também pode escolher os grupos específicos a serem excluídos. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> -   **Aplicativo iOS gerenciado da loja de aplicativos**
> -   **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Criar uma política de configuração do aplicativo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione a carga de trabalho de **Aplicativos móveis**.
4. Escolha **Políticas de configuração do aplicativo** no grupo **Gerenciar** e escolha **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome** – o nome do perfil exibido no portal do Azure.
    - **Descrição** – a descrição do perfil que é exibida no portal do Azure.
    - **Tipo de registro de dispositivos** – escolha **Dispositivos gerenciados**.
6. Selecione **iOS** para **Plataforma**.
7.  Escolha **Aplicativo associado**. Em seguida, no painel **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração e selecione **OK**.
8.  No painel **Adicionar política de configuração**, escolha **Definições de configuração**.
9. Selecione **Formato de definições de configuração**. Selecione uma das seguintes opções para adicionar informações de XML:
    - **Usar o designer de configuração**
    - **Inserir dados XML**<br></br>
    Para obter detalhes sobre como usar o designer de configuração, confira [Usar o designer de configuração](#use-configuration-designer). Para obter detalhes sobre como inserir dados XML, confira [Inserir dados XML](#enter-xml-data). 
10. Depois de adicionar suas informações de XML, escolha **OK** e, em seguida, escolha **Adicionar** para adicionar a política de configuração. O painel de visão geral da política de configuração é exibido.
11. Selecione **Atribuições** para exibir as opções de inclusão e exclusão. 

    ![Captura de tela da guia Incluir de Atribuições de política](./media/app-config-policy01.png)
12. Selecione **Todos os Usuários** na guia **Inclusão**.

    ![Captura de tela de Atribuições de política – opção de lista suspensa Todos os usuários](./media/app-config-policy02.png)
13. Selecione a guia **Excluir**. 
14. Clique em **Selecionar grupos para excluir** para exibir o painel relacionado.

    ![Captura de tela Atribuições de política – folha Selecionar grupos para excluir](./media/app-config-policy03.png)
15. Escolha os grupos que você deseja excluir e, em seguida, clique em **Selecionar**.

    >[!NOTE]
    >Ao adicionar um grupo, se nenhum outro grupo ainda tiver sido incluído para um determinado tipo de atribuição, ele será pré-selecionado e ficará inalterável para outros tipos de atribuição de inclusão. Assim, esse grupo que foi usado, não poderá ser usado como um grupo excluído.
16. Clique em **Salvar**.

## <a name="use-configuration-designer"></a>Usar o designer de configuração

O Microsoft Intune fornece definições de configuração exclusivas a um aplicativo. Use o designer de configuração para aplicativos em dispositivos que estão registrados ou não no Microsoft Intune. O designer permite que você defina chaves de configuração e valores específicos que ajudam você a criar o XML subjacente. Você também deve especificar o tipo de dados para cada valor. Essas configurações são fornecidas para os aplicativos automaticamente quando os aplicativos são instalados.

### <a name="add-a-setting"></a>Adicionar uma configuração

1. Para cada chave e valor na configuração, defina:
   - **Chave de configuração** – a chave que identifica exclusivamente a configuração específica.
   - **Tipo de valor** – o tipo de dados do valor de configuração. Os tipos incluem Inteiro, Real, Cadeia de caracteres ou Booliano.
   - **Valor de configuração** – o valor da configuração.
2. Escolha **OK** para definir as configurações.

### <a name="delete-a-setting"></a>Excluir uma configuração

1. Escolha as reticências (**...**) ao lado da configuração.
2. Selecione **Excluir**.

Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

## <a name="enter-xml-data"></a>Inserir dados XML

É possível digitar ou colar uma lista de propriedades XML que contém as definições de configuração do aplicativo para dispositivos registrados no Intune. O formato da lista de propriedades XML varia dependendo do aplicativo que você está configurando. Para obter detalhes sobre o formato exato a ser usado, contate o fornecedor do aplicativo.

O Intune valida o formato XML. No entanto, o Intune não verifica se a PList (lista de propriedades) XML funciona com o aplicativo de destino.

Para saber mais sobre listas de propriedades XML:

  -  Leia [Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Consulte [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Compreender Listas de propriedades XML) na Biblioteca do Desenvolvedor iOS.

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
- \{\{userprincipalname\}\}—por exemplo, **John@contoso.com**
- \{\{mail\}\}—por exemplo, **John@contoso.com**
- \{\{partialupn\}\}—por exemplo, **João**
- \{\{accountid\}\}—por exemplo, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}—por exemplo, **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}—por exemplo, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—por exemplo, **João Silva**
- \{\{serialnumber\}\}—por exemplo, **F4KN99ZUG5V2** (para dispositivos iOS)
- \{\{serialnumberlast4digits\}\}— por exemplo, **G5V2** (para dispositivos iOS)

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo.
