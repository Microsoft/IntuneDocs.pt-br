---
title: Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados
titlesuffix: Microsoft Intune
description: Use as políticas de configuração de aplicativo no Microsoft Intune para fornecer configurações quando os usuários executarem um aplicativo de perfil de trabalho Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 4b76625276a34c027ae8c74f1c6a3977c4a7e8bd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179942"
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use as políticas de configuração de aplicativo no Microsoft Intune para fornecer configurações para aplicativos de perfil de trabalho Android. O desenvolvedor do aplicativo deve expor as definições de configuração de aplicativo gerenciado Android para especificar as definições de configuração para o aplicativo. Atribua a política de configuração do aplicativo ao grupo de usuários ao qual você deseja que as configurações sejam aplicadas.  As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.

> [!Note]  
> Nem todo aplicativo dá suporte à configuração de aplicativo. Verifique com o desenvolvedor do aplicativo se ele criou o aplicativo para dar suporte a políticas de configuração de aplicativo.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione a carga de trabalho **Aplicativos clientes**.
4. Escolha **Políticas de configuração do aplicativo** no grupo **Gerenciar** e escolha **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome** – o nome do perfil que será exibido no portal do Azure.
    - **Descrição** – a descrição do perfil que será exibida no portal do Azure.
    - **Tipo de registro de dispositivos** – escolha **Dispositivos gerenciados**.
6. Selecione **Android** para **Plataforma**.
7. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual deseja definir uma política de configuração de aplicativo. Selecione na lista de aplicativos de perfil de trabalho Android que você aprovou e sincronizou com o Intune.
8. Selecione **Permissões**. É possível definir configurações usando:
    - [Designer de configuração](#Use-the-configuration-designer)
    - [Editor de JSON](#Enter-the-JSON-editor)
9. Escolha **OK** e, em seguida, **Adicionar**.

## <a name="use-the-configuration-designer"></a>Usar o designer de configuração

Você pode usar o designer de configuração para aplicativos Android que dão suporte à configuração. A configuração será aplicada a dispositivos registrados no Intune. O designer permite definir valores de configuração específicos para as configurações que um aplicativo expõe.

Selecione **Adicionar** para selecionar a lista de definições de configuração que você deseja especificar para o aplicativo.  
Para cada chave e valor na configuração, defina:

  - **Tipo de valor**  
    O tipo de dados do valor de configuração. Para tipos de valor de cadeia de caracteres, opcionalmente, você pode escolher um perfil de certificado ou variável como o tipo de valor.
  - **Valor da configuração**  
    O valor para a configuração. Se você selecionar a variável ou o certificado para o tipo de valor, poderá escolher em uma lista de variáveis ou perfis de certificado na lista suspensa de valor de configuração.  Se você escolher um certificado, o alias de certificado do certificado implantado no dispositivo será preenchido no tempo de execução.
    
### <a name="supported-variables-for-configuration-values"></a>Variáveis compatíveis para valores de configuração

Você poderá escolher as seguintes opções se escolher variável como o tipo de valor:
- Nome UPN – por exemplo, **John@contoso.com**
- Email – por exemplo, **John@contoso.com**
- UPN parcial – por exemplo, **Julio**
- ID da Conta – por exemplo, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- ID do dispositivo – por exemplo, **b9841cd9-9843-405f-be28-b2265c59ef97**
- ID de usuário – por exemplo, **3ec2c00f-b125-4519-acf0-302ac3761822**
- Nome de usuário – por exemplo, **John Doe**

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Permitir somente contas da organização configuradas em aplicativos de várias identidades 

Para dispositivos Android, use os seguintes pares de chave/valor:

| **Key** | com.microsoft.intune.mam.AllowedAccountUPNs |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Valores** | <ul><li>Um ou mais UPNs delimitados por <code>;</code>.</li><li>Somente contas permitidas são as contas de usuário gerenciado definidas por essa chave.</li><li> Para dispositivos registrados no Intune, o token <code>{{userprincipalname}}</code> pode ser usado para representar a conta de usuário registrado.</li></ul> |

   > [!NOTE]
   > Você deve usar o Outlook para Android 2.2.222 ou posterior ao permitir apenas contas da organização configuradas com várias identidades.<p></p>
   > Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. Os aplicativos de suporte processam a configuração do aplicativo, removem e bloqueiam contas não aprovadas.<p></p>
   > Para o Microsoft Word, Microsoft Excel e Microsoft PowerPoint, você deve usar a versão do aplicativo 16.0.9327.1000 e posteriores. 

## <a name="enter-the-json-editor"></a>Inserir o editor de JSON

Algumas definições de configuração em aplicativos (como aquelas com os tipos Pacote) não podem ser configuradas com o designer de configuração. É necessário usar o editor de JSON para esses valores. As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.

1. Em **Formato de definições de configuração**, selecione **Inserir editor de JSON**.
2. No editor, é possível definir os valores JSON para as definições de configuração. Escolha **Baixar modelo de JSON** para baixar um arquivo de exemplo que, em seguida, pode ser configurado.
3. Escolha **OK** e, em seguida, **Adicionar**.

A política será criada e exibida na folha da lista de políticas.

Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração de aplicativo.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Pré-configurar o estado de concessão de permissões para aplicativos

Você também pode pré-configurar a permissão para que os aplicativos acessem os recursos do dispositivo Android. Por padrão, os aplicativos Android que exigem permissões de dispositivo – como o acesso à localização ou à câmera do dispositivo – solicitam que os usuários aceitem ou neguem as permissões. Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final deverá conceder ao aplicativo permissão para usar o microfone.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Escolha **Aplicativos clientes**.
3. Em **Gerenciar**, escolha **Políticas de configuração do aplicativo** e, em seguida, clique em **Adicionar**.
4. Defina os seguintes detalhes:
    - **Nome**. O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**. A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro de dispositivo**. Selecione **Dispositivos gerenciados**.
    - **Plataforma**. Selecione **Android**.
5. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração. Selecione na lista de aplicativos de perfil de trabalho Android que você aprovou e sincronizou com o Intune.
6. Selecione **Permissões** e, em seguida, escolha **Adicionar**.
7. Selecione na lista de permissões de aplicativo disponíveis e, em seguida, escolha **OK**.
8. Selecione uma opção para cada permissão a ser concedida com esta política:
    - **Aviso**. Avise o usuário para aceitar ou recusar.
    - **Concessão automática**. Aprovar automaticamente sem notificar o usuário.
    - **Negação automática**. Negar automaticamente sem notificar o usuário.
9. Para atribuir a política de configuração de aplicativo, selecione a política de configuração de aplicativo, selecione **Atribuição** e, em seguida, selecione **Selecionar grupos**.
10. Selecione os grupos de usuários a serem atribuídos e, em seguida, escolha **Selecionar**.
11. Escolha **Salvar** para atribuir a política.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo.

