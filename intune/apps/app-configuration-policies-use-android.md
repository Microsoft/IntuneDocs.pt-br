---
title: Adicionar políticas de configuração de aplicativo para dispositivos Android Enterprise gerenciados
titleSuffix: Microsoft Intune
description: Use as políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações quando os usuários executam um aplicativo do Google Play Gerenciado.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ec80922cf2539fdbacb572fd96c5a5e45549b5c3
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75204997"
---
# <a name="add-app-configuration-policies-for-managed-android-enterprise-devices"></a>Adicionar políticas de configuração de aplicativo para dispositivos Android Enterprise gerenciados

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

As políticas de configuração de aplicativo no Microsoft Intune fornecem configurações para aplicativos do Google Play Gerenciado em dispositivos Android Enterprise gerenciados. O desenvolvedor do aplicativo expõe as definições de configuração do aplicativo gerenciado pelo Android. O Intune usa essas configurações expostas para permitir que o administrador configure recursos para o aplicativo. A política de configuração de aplicativo é atribuída aos seus grupos de usuários. As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.

> [!NOTE]  
> Nem todo aplicativo dá suporte à configuração de aplicativo. Verifique com o desenvolvedor do aplicativo se este é compatível com as políticas de configuração de aplicativo.

1. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Aplicativos** > **Políticas de configuração de aplicativo** >  **Adicionar** > **Dispositivos gerenciados**.
2. Adicione as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política é **Política de aplicativo Android Enterprise Nine Work para toda a empresa**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Tipo de registro do dispositivo**: Essa configuração é definida como **Dispositivos gerenciados**.
    - **Plataforma**: Selecione **Android**.

3. Escolha **Aplicativo Associado**. Escolha o aplicativo Android ao qual essa política de configuração de aplicativos será associada. Escolha na lista de [aplicativos do Google Play Gerenciado que foram aprovados e sincronizados com o Intune](~/apps/apps-add-android-for-work.md).
4. Selecione **Permissões**. É possível definir configurações usando:

    - [Designer de configuração](#use-the-configuration-designer)
    - [Editor de JSON](#enter-the-json-editor)

5. Selecione **OK** > **Adicionar**.

## <a name="use-the-configuration-designer"></a>Usar o designer de configuração

Você pode usar o designer de configuração para aplicativos do Google Play Gerenciado quando o aplicativo for criado para aceitar as definições de configuração. A configuração aplica-se a dispositivos registrados no Intune. O designer permite definir valores de configuração específicos para as configurações que um aplicativo expõe.

1. Selecione **Adicionar**. Escolha a lista de definições de configuração que você deseja inserir para o aplicativo.

    Se você está usando o GMail ou o Nine Work como seu aplicativo de email, confira [Configurações de dispositivo Android Enterprise para configurar o email](../email-settings-android-enterprise.md) para saber mais sobre essas configurações.

2. Para cada chave e valor na configuração, defina:

    - **Tipo de valor**: O tipo de dados do valor de configuração. Para tipos de valor de cadeia de caracteres, opcionalmente, você pode escolher um perfil de certificado ou variável como o tipo de valor.
    - **Valor da configuração**: O valor para a configuração. Se você escolher a variável ou o certificado para o **Tipo de valor**, escolha em uma lista de variáveis ou perfis de certificado. Se você escolher um certificado, o alias do certificado implantado no dispositivo será preenchido no runtime.

### <a name="supported-variables-for-configuration-values"></a>Variáveis compatíveis para valores de configuração

Você poderá escolher as seguintes opções se escolher variável como o tipo de valor:

| Opção | Exemplo |
|----|----|
| ID do Dispositivo AAD | dc0dc142-11d8-4b12-bfea-cae2a8514c82 |
| ID da Conta | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| ID de Dispositivo do Intune | b9841cd9-9843-405f-be28-b2265c59ef97 |
| Domain | contoso.com |
| Email | john@contoso.com |
| Nome UPN parcial | John |
| ID do Usuário | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Nome de usuário | John Doe |
| Nome UPN | john@contoso.com |


### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Permitir somente contas da organização configuradas em aplicativos de várias identidades 

Para dispositivos Android, use os seguintes pares de chave/valor:

| **Key** | com.microsoft.intune.mam.AllowedAccountUPNs |
|---|---|
| **Valores** | <ul><li>Um ou mais UPNs delimitados por <code>;</code>.</li><li>Somente contas permitidas são as contas de usuário gerenciado definidas por essa chave.</li><li> Para dispositivos registrados no Intune, o token <code>{{userprincipalname}}</code> pode ser usado para representar a conta de usuário registrado.</li></ul> |

   > [!NOTE]
   > Você deve usar o Outlook para Android 2.2.222 e posterior, Word, Excel, PowerPoint para Android 16.0.9327.1000 e posterior ou OneDrive para Android 5.28 e posterior ao permitir apenas contas da organização configuradas com várias identidades.<p></p>
   > Como Administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. Os aplicativos de suporte processam a configuração do aplicativo, removem e bloqueiam contas não aprovadas.<p></p>

## <a name="enter-the-json-editor"></a>Inserir o editor de JSON

Algumas definições de configuração em aplicativos (como aplicativos com tipos Pacote) não podem ser configuradas com o designer de configuração. Use o editor de JSON para esses valores. As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.

1. Em **Formato de definições de configuração**, selecione **Inserir editor de JSON**.
2. No editor, é possível definir os valores JSON para as definições de configuração. Escolha **Baixar modelo de JSON** para baixar um arquivo de exemplo que, em seguida, pode ser configurado.
3. Escolha **OK** e, em seguida, **Adicionar**.

A política é criada e mostrada na lista.

Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração de aplicativo.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Pré-configurar o estado de concessão de permissões para aplicativos

Você também pode pré-configurar as permissões de aplicativo para acessar os recursos do dispositivo Android. Por padrão, os aplicativos Android que exigem permissões de dispositivo, como o acesso à localização ou à câmera do dispositivo, solicitam que os usuários aceitem ou neguem as permissões.

Por exemplo, um aplicativo usa o microfone do dispositivo. O usuário é solicitado a conceder ao aplicativo permissão para usar o microfone.

1. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Aplicativos** > **Políticas de configuração de aplicativo** >  **Adicionar** > **Dispositivos gerenciados**.
2. Adicione as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política é **Política de aplicativo de permissões de prompt Android Enterprise para toda a empresa**.
    - **Descrição**. Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Tipo de registro do dispositivo**: Essa configuração é definida como **Dispositivos gerenciados**.
    - **Plataforma**: Selecione **Android**.

3. Escolha **Aplicativo Associado**. Escolha o aplicativo para o qual deseja definir uma política de configuração. Escolha na lista de aplicativos de perfil de trabalho Android que você aprovou e sincronizou com o Intune.
4. Escolha **Permissões** > **Adicionar**. Na lista, escolha as permissões de aplicativo disponíveis e, depois, **OK**.
5. Selecione uma opção para cada permissão a ser concedida com esta política:
    - **Aviso**. Avise o usuário para aceitar ou recusar.
    - **Concessão automática**. Aprovar automaticamente sem notificar o usuário.
    - **Negação automática**. Negar automaticamente sem notificar o usuário.
6. Para atribuir a política de configuração de aplicativo, escolha a política de configuração de aplicativo > **Atribuição** > **Selecionar grupos**. Escolha os grupos de usuários a atribuir > **Selecionar**.
7. Escolha **Salvar** para atribuir a política.

## <a name="additional-information"></a>Informações adicionais

- [Atribuir aplicativos do Google Play Gerenciado a dispositivos Android Enterprise](apps-add-android-for-work.md#assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices)
- [Implantar definições de configuração de aplicativos no Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune)

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo.
