---
title: Gerenciar a transferência de dados entre aplicativos iOS
titlesuffix: Microsoft Intune
description: Entenda como usar políticas de gerenciamento de aplicativo móvel no Microsoft Intune para gerenciar transferências de dados entre aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4c2872e70697b15326f89abd5721048643c5421a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune
## <a name="manage-ios-apps"></a>Gerenciar aplicativos iOS
Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.  Você pode gerenciar aplicativos iOS das seguintes maneiras:

-   Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política** aplicativos. Consulte [todos os aplicativos gerenciados pelo Intune que você pode gerenciar com a política de proteção de aplicativo](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.  Isso requer que os dispositivos sejam registrados na solução MDM. Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.

O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**. As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.  Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.

##  <a name="using-app-protection-with-ios-apps"></a>Usando a proteção do aplicativo com aplicativos iOS
Políticas de proteção de aplicativo podem ser usadas com o recurso iOS **Abrir no gerenciamento** para proteger os dados da empresa das seguintes maneiras:

-   **Dispositivos do funcionário não gerenciados por nenhuma solução de MDM:** defina as configurações de política de proteção de aplicativo como **Permitir que o aplicativo transfira dados somente para aplicativos Gerenciados por Política**. O comportamento do “Open-in” em um aplicativo Gerenciado por Política somente apresentará outros aplicativos Gerenciados por Política como uma opção de compartilhamento. Se um usuário tentar enviar um arquivo protegido por política como um anexo no OneDrive no email nativo, esse arquivo ficará ilegível.

-   **Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de proteção de aplicativo e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente. Para permitir a transferência de dados entre aplicativos com as políticas de proteção de aplicativo, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.   

-   **Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.
Para verificar se os aplicativos implantados usando a solução de MDM de terceiros também estão associados às políticas de proteção de aplicativo configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting-for-third-party-emm).  Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas de proteção de aplicativo serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta corporativa.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Definir configuração de UPN do usuário para Microsoft Intune ou EMM de terceiros
Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados pelo Intune ou por uma solução EMM de terceiros. O procedimento descrito abaixo é um fluxo geral de como definir a configuração de UPN e experiência do usuário final resultante:

1.  No [portal do Azure](https://portal.azure.com), [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) para iOS. Defina as configurações da política conforme os requisitos da sua empresa e selecione os aplicativos de iOS que devem ter essa política.

2.  Implante os aplicativos e o perfil de email que você deseja gerenciar por meio do Intune ou da solução MDM de terceiros usando as etapas gerais abaixo. Essa experiência também é abordada no Exemplo 1.

3.  Implante o aplicativo com as seguintes configurações do aplicativo:

      **key** = IntuneMAMUPN,  **value** = <username@company.com>

      Exemplo: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Implante a política **Abrir no gerenciamento** usando o Intune ou o provedor de MDM de terceiros para dispositivos registrados.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Exemplo 1: experiência de Administrador no Intune ou no console do MDM de terceiros

1. Vá para o console de administração do Intune ou do seu provedor de MDM de terceiros. Vá para a seção do console em que você implanta as definições de configuração de aplicativo para dispositivos iOS registrados.

2. Na seção Configuração do Aplicativo, insira a seguinte configuração:

   **key** = IntuneMAMUPN,  **value** = <username@company.com>

   A sintaxe exata do par chave/valor pode diferir com base no provedor de MDM de terceiros. A tabela a seguir mostra exemplos de provedores de MDM de terceiros e os valores exatos que você deve digitar para o par chave/valor.

|Provedor de MDM de terceiros| Chave de Configuração | Tipo de valor | Valor da Configuração|
| ------- | ---- | ---- | ---- |
|Microsoft Intune| IntuneMAMUPN | Cadeia de caracteres | {UserPrincipalName}|
|VMware AirWatch| IntuneMAMUPN | Cadeia de caracteres | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | Cadeia de caracteres | ${userUPN} **ou** ${userEmailAddress} |


### <a name="example-2-end-user-experience"></a>Exemplo 2: experiência do usuário final

1.  O usuário final instala um aplicativo Microsoft Word no dispositivo.

2.  O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.

3.  O usuário final tenta abrir o documento do email nativo no Microsoft Word.

4.  Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.  Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.

    > [!NOTE]
    > O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas de proteção de aplicativo ao usar o aplicativo do Word em um contexto pessoal.

5.  Quando o logon for bem-sucedido, as configurações da política de proteção de aplicativo são aplicadas ao aplicativo Word.

6.  A transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo. Além disso, os dados são tratados em um contexto de trabalho e as configurações da política são aplicadas de acordo.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Validar configuração de UPN do usuário para EMM de terceiros

Depois de definir a configuração de UPN do usuário, você deve validar a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.

Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar visualmente em um dispositivo. Se a configuração de política estiver definida como **Sim**, o usuário final receberá um prompt para definir ou inserir um PIN durante a tentativa de acessar dados da empresa.

Primeiro, [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) no aplicativo iOS. Consulte [Validar as políticas de proteção do aplicativo](app-protection-policies-validate.md) para obter mais informações sobre como testar a política de proteção de aplicativo.


### <a name="see-also"></a>Consulte também
[O que é a política de proteção de aplicativo do Intune](app-protection-policy.md)
