---
title: "Gerenciar a transferência de dados entre aplicativos do iOS"
description: "Use este tópico para entender como você pode usar o recurso Open in do iOS e as políticas de gerenciamento de aplicativo móvel para gerenciar transferências de dados entre aplicativos."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 05975303bd45764d56f00986aea5aa30399893f9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Gerenciar transferência de dados entre aplicativos iOS com Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>Gerenciar aplicativos iOS
Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.  Você pode gerenciar aplicativos iOS das seguintes maneiras:

-   Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política** aplicativos.

-   Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.  Isso requer que os dispositivos sejam registrados na solução MDM. Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.

O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**. As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.  Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.

##  <a name="manage-data-transfer-between-ios-apps"></a>Gerenciar a transferência de dados entre aplicativos do iOS
Políticas de proteção de aplicativo podem ser usadas com o recurso iOS **Abrir no gerenciamento** para proteger os dados da empresa das seguintes maneiras:

-   **Dispositivos de propriedade do funcionário não gerenciados por nenhuma solução de MDM:** você pode definir as [configurações de política de proteção de aplicativo](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Quando o usuário final abrir um arquivo protegido em um aplicativo não gerenciado por política, o arquivo ficará ilegível.

-   **Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de proteção de aplicativo e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente. Para permitir a transferência de dados entre aplicativos com as políticas de proteção de aplicativo, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.   

-   **Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.
Para verificar se os aplicativos implantados usando a solução de MDM de terceiros também estão associados às políticas de proteção de aplicativo configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting-for-third-party-emm).  Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas de proteção de aplicativo serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta corporativa.

> [!IMPORTANT]
> A configuração de UPN do usuário só será necessária para aplicativos implantados para dispositivos gerenciados por um MDM de terceiro.  Para dispositivos gerenciados pelo Intune, essa configuração não é necessária.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>Definir configuração de UPN do usuário para EMM de terceiros
Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados por uma solução EMM de terceiros. O procedimento descrito abaixo é um fluxo geral de como definir a configuração de UPN e experiência do usuário final resultante:


1.  No portal do Azure, [configure uma política de proteção de aplicativo](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para a plataforma iOS. Defina as configurações de política conforme os requisitos da sua empresa e selecione os aplicativos que devem ter essa política.

2.  Implante os aplicativos e o perfil de email que você deseja gerenciar **por meio da solução MDM de terceiros** usando as etapas gerais abaixo. Essa experiência também é abordada no Exemplo 1.

  1.  Implante o aplicativo com as seguintes configurações do aplicativo:

      **key** = IntuneMAMUPN,  **value** = <username@company.com>

      Exemplo: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Implante Abrir na política de gerenciamento usando o provedor de MDM de terceiros para dispositivos registrados.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Exemplo 1: experiência de Admin no console do MDM de terceiros

1. Vá para o console de administração do seu provedor MDM de terceiros. Vá para a seção do console em que você implanta as definições de configuração de aplicativo para dispositivos iOS registrados.

2. Na seção Configuração do Aplicativo, insira a seguinte configuração:

  **key** = IntuneMAMUPN,  **value** = <username@company.com>

  A sintaxe exata do par chave/valor pode diferir com base no provedor de MDM de terceiros. A tabela a seguir mostra exemplos de provedores de MDM de terceiros e os valores exatos que você deve digitar para o par chave/valor.

|Provedor de MDM de terceiros| Chave de Configuração | Tipo de valor | Valor da Configuração|
| ------- | ---- | ---- | ---- |
| VMware AirWatch | IntuneMAMUPN | Cadeia de caracteres | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | Cadeia de caracteres | $EMAIL$ **ou** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | Cadeia de caracteres | ${userUPN} **ou** ${userEmailAddress} |

### <a name="example-2-end-user-experience"></a>Exemplo 2: experiência do usuário final

1.  O usuário final instala um aplicativo Microsoft Word no dispositivo.

2.  O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.

3.  O usuário final tenta abrir o documento do email nativo no Microsoft Word.

4.  Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.  Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.

    > [!NOTE]
    > O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas de proteção de aplicativo ao usar o aplicativo do Word em um contexto pessoal.

5.  Quando o logon for bem-sucedido, as configurações da política de proteção de aplicativo são aplicadas ao aplicativo Word.

6.  Agora, a transferência de arquivos deu certo e o documento foi marcado como identidade corporativa no aplicativo. Além disso, o arquivo é tratado em um contexto de trabalho, e as configurações da política são aplicadas adequadamente.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Validar configuração de UPN do usuário para EMM de terceiros

Depois de definir a configuração de UPN do usuário, você deve validar a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.

Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar visualmente em um dispositivo. Se a configuração de política estiver definida como **Sim**, o usuário final receberá um prompt para definir ou inserir um PIN durante a tentativa de acessar dados da empresa.

Primeiro, [crie e implante uma política de proteção de aplicativo](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) no aplicativo iOS. Consulte [Validar as políticas de proteção do aplicativo](validate-mobile-application-management.md) para obter mais informações sobre como testar a política de proteção de aplicativo.



### <a name="see-also"></a>Consulte também
[Proteger dados de aplicativo usando políticas de proteção de aplicativo com o Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
