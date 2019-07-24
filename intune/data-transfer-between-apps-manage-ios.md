---
title: Gerenciar a transferência de dados entre aplicativos iOS
titleSuffix: Microsoft Intune
description: Entenda como usar políticas de gerenciamento de aplicativo móvel no Microsoft Intune para gerenciar transferências de dados entre aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9a1e370b65d8bfd7e61562347323bf1455dfe55b
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68354305"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune

Para ajudar a proteger os dados da empresa, restrinja as transferências de arquivos somente aos aplicativos que você gerencia. Você pode gerenciar aplicativos iOS das seguintes maneiras:

- Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política**. Consulte [todos os aplicativos gerenciados pelo Intune que você pode gerenciar com a política de proteção de aplicativo](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

- Implante e gerencie aplicativos por meio do **canal MDM**, que exige que os dispositivos se registrem em uma solução de MDM (Gerenciamento de Dispositivo Móvel). Os aplicativos que você implanta podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.

O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**. Defina as restrições de *Abrir no gerenciamento* nas configurações e implante-as usando sua solução de MDM.  Quando um usuário instala o aplicativo implantado, restrições definidas por você são aplicadas.

## <a name="use-app-protection-with-ios-apps"></a>Usar a proteção do aplicativo com aplicativos iOS
Use as políticas de proteção de aplicativo com o recurso **Abrir no gerenciamento** do iOS para proteger os dados da empresa das seguintes maneiras:

- **Dispositivos de funcionários não gerenciados por nenhuma solução de MDM:** Defina as configurações da política de proteção de aplicativo como **Permitir que o aplicativo transfira dados somente para aplicativos Gerenciados por Política**. O comportamento de *Abrir em* em um aplicativo Gerenciado por Política apresentará apenas outros aplicativos Gerenciados por Política como opção de compartilhamento. Se um usuário tentar enviar um arquivo protegido por política como um anexo no OneDrive no aplicativo de email nativo, esse arquivo ficará ilegível.

- **Dispositivos gerenciados por soluções MDM**: para dispositivos registrados no Intune ou em soluções MDM de terceiros, o compartilhamento de dados entre aplicativos com políticas de proteção de aplicativo e outros aplicativos gerenciados do iOS implantados por meio do MDM é controlado pelas políticas de aplicativo do Intune e pelo recurso **Gerenciamento de local de abertura** do iOS. Para verificar se os aplicativos implantados usando a solução de MDM também estão associados às políticas de proteção de aplicativo do Intune, defina a configuração de UPN do usuário conforme descrito na seção a seguir, [Definir configuração de UPN do usuário](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Para especificar como você deseja permitir a transferência de dados para outros aplicativos, habilite **Enviar dados da organização para outros aplicativos** e escolha o nível preferencial de compartilhamento. Para especificar como você deseja permitir que um aplicativo receba dados de outros aplicativos, habilite **Receber dados de outros aplicativos** e escolha o nível preferencial de recebimento de dados. Para obter mais informações sobre como receber e compartilhar de dados de aplicativo, confira [Configurações de realocação de dados](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Definir configuração de UPN do usuário para Microsoft Intune ou EMM de terceiros
Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados pelo Intune ou por uma solução EMM de terceiros. A configuração de UPN funciona com as políticas de proteção de aplicativo implantadas do Intune. O procedimento a seguir é um fluxo geral de como definir a configuração de UPN e a experiência do usuário resultante:

1. No [portal do Azure](https://portal.azure.com), [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) para iOS. Defina as configurações da política conforme os requisitos da sua empresa e selecione os aplicativos de iOS que devem ter essa política.

2. Implante os aplicativos e o perfil de email que você deseja gerenciar por meio do Intune ou da solução MDM de terceiros usando as seguintes etapas gerais. Essa experiência também é abordada no *Exemplo 1*.

3. Implante o aplicativo com as seguintes definições de configuração de aplicativos no dispositivo gerenciado:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Exemplo: [‘IntuneMAMUPN’, ‘janellecraig@contoso.com’]
      
     > [!NOTE]
     > No Intune, a política de Configuração de Aplicativos precisa ser configurada como **Dispositivos Gerenciados**.
     > Ou o aplicativo precisará ser instalado no Portal da Empresa do Intune (se for definido como disponível) ou enviado por push para o dispositivo, caso necessário. 

4. Implante a política **Abrir no gerenciamento** usando o Intune ou o provedor de MDM de terceiros para dispositivos registrados.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Exemplo 1: Experiência de administrador no Intune ou em um console de MDM de terceiros

1. Vá para o console de administração do Intune ou do seu provedor de MDM de terceiros. Vá para a seção do console em que você implanta as definições de configuração de aplicativo para dispositivos iOS registrados.

2. Na seção Configuração do Aplicativo, insira a seguinte configuração:

   **key** = IntuneMAMUPN, **value** = <username@company.com>

   A sintaxe exata do par chave/valor pode diferir com base no provedor de MDM de terceiros. A tabela a seguir mostra exemplos de provedores de MDM de terceiros e os valores exatos que você deve digitar para o par chave/valor.

   |Provedor de MDM de terceiros| Chave de Configuração | Tipo de valor | Valor da Configuração|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Cadeia de caracteres | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Cadeia de caracteres | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Cadeia de caracteres | ${userUPN} **ou** ${userEmailAddress} |
   |Gerenciamento de ponto de extremidade da Citrix | IntuneMAMUPN | Cadeia de caracteres | ${user.userprincipalname} |
   |ManageEngine Mobile Device Manager | IntuneMAMUPN | Cadeia de caracteres | %upn% |

> [!NOTE]  
> Para aplicativos do Outlook no iOS, se você implantar uma Política de Configuração de Aplicativos com a opção "Usando o designer de configuração", a chave de configuração IntuneMAMUPN será definida automaticamente em segundo plano para a política. Obtenha mais detalhes na seção de perguntas frequentes em [Experiência de política de configuração de aplicativos no novo Outlook para iOS e Android – configuração geral de aplicativos](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481). 


### <a name="example-2-end-user-experience"></a>Exemplo 2: Experiência do usuário final

1. O usuário instala o aplicativo Microsoft Word em um dispositivo.

2. O usuário inicia o aplicativo de email nativo gerenciado para acessar seus emails.

3. O usuário tenta abrir um documento do email nativo no Microsoft Word.

4. Quando o aplicativo Word é iniciado, é solicitado que o usuário final entre usando sua conta corporativa. A conta em que o usuário entra deve corresponder à conta especificada nas definições de configuração do aplicativo Microsoft Word.

    > [!NOTE]
    > O usuário pode adicionar e usar suas contas pessoais com o Word. As políticas de proteção de aplicativo não se aplicam quando o usuário utiliza o Word fora de um contexto de trabalho. 

5. Depois de entrar, as configurações de política de proteção de aplicativo se aplicam ao aplicativo Word.

6. A transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo.  Os dados são tratados em um contexto de trabalho e as configurações de política são aplicadas. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Validar configuração de UPN do usuário para EMM de terceiros

Depois de definir a configuração de UPN do usuário, valide a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.

Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar. Quando a configuração de política for **Sim**, o usuário deverá ver um prompt para definir ou inserir um PIN antes de poder acessar os dados da empresa.

Primeiro, [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) no aplicativo iOS. Para obter mais informações sobre como testar a política de proteção de aplicativo, consulte [Validar políticas de proteção do aplicativo](app-protection-policies-validate.md).


## <a name="see-also"></a>Consulte também
[O que é a política de proteção de aplicativo do Intune](app-protection-policy.md)
