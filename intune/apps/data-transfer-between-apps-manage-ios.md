---
title: Gerenciar a transferência de dados entre aplicativos iOS
titleSuffix: Microsoft Intune
description: Entenda como usar políticas de gerenciamento de aplicativo móvel no Microsoft Intune para gerenciar transferências de dados entre aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
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
ms.openlocfilehash: b9b93ec96eb6480c04514f1505a787332dd13625
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940021"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune

Para ajudar a proteger os dados da empresa, restrinja as transferências de arquivos somente aos aplicativos que você gerencia. Você pode gerenciar aplicativos iOS das seguintes maneiras:

- Proteger dados da organização para contas corporativas ou escolares, configurando uma política de proteção de aplicativo para os aplicativos, que podemos chamar de *aplicativos gerenciados por políticas*.  Consulte [todos os aplicativos gerenciados pelo Intune que você pode gerenciar com a política de proteção de aplicativo](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

- Implante e gerencie os aplicativos por meio do gerenciamento de dispositivos iOS, que exige que os dispositivos se registrem em uma solução de Gerenciamento de Dispositivos Móveis (MDM). Os aplicativos que você implanta podem ser aplicativos *gerenciados por política* ou outros aplicativos gerenciados do iOS.

O recurso **Abrir em gerenciamento** para dispositivos iOS registrados pode limitar as transferências de arquivo entre os aplicativos do iOS. Defina as restrições de *Abrir no gerenciamento* nas configurações e implante-as usando sua solução de MDM.  Quando um usuário instala o aplicativo implantado, restrições definidas por você são aplicadas.

## <a name="use-app-protection-with-ios-apps"></a>Usar a proteção do aplicativo com aplicativos iOS
Use as políticas de proteção de aplicativo com o recurso **Abrir no gerenciamento** do iOS para proteger os dados da empresa das seguintes maneiras:

- **Dispositivos não gerenciados por nenhuma solução de MDM:** Você pode definir as configurações da política de proteção de aplicativos para controlar o compartilhamento de dados com outros aplicativos por meio do *Abrir em* ou *Compartilhar extensões*.  Para fazer isso, defina a configuração **Enviar dados da organização para outro aplicativo** como **Aplicativos gerenciados por política com o valor de filtragem de Abrir em/Compartilhar**.  O comportamento de *Abrir em/Compartilhar* no *aplicativo gerenciado por política* apresentará apenas outros *aplicativos gerenciados por política* como opção de compartilhamento. 

- **Dispositivos gerenciados por soluções MDM**: para dispositivos registrados no Intune ou em soluções MDM de terceiros, o compartilhamento de dados entre aplicativos com políticas de proteção de aplicativo e outros aplicativos gerenciados do iOS implantados por meio do MDM é controlado pelas políticas de aplicativo do Intune e pelo recurso **Gerenciamento de local de abertura** do iOS. Para verificar se os aplicativos implantados usando a solução de MDM também estão associados às políticas de proteção de aplicativo do Intune, defina a configuração de UPN do usuário conforme descrito na seção a seguir, [Definir configuração de UPN do usuário](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Para especificar como você deseja permitir a transferência de dados para outros aplicativos, habilite **Enviar dados da organização para outros aplicativos** e escolha o nível preferencial de compartilhamento. Para especificar como você deseja permitir que um aplicativo receba dados de outros aplicativos, habilite **Receber dados de outros aplicativos** e escolha o nível preferencial de recebimento de dados. Para obter mais informações sobre como receber e compartilhar de dados de aplicativo, confira [Configurações de realocação de dados](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Definir configuração de UPN do usuário para Microsoft Intune ou EMM de terceiros
Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados pelo Intune ou por uma solução EMM de terceiros para identificar a conta de usuário registrada. A configuração de UPN funciona com as políticas de proteção de aplicativo implantadas do Intune. O procedimento a seguir é um fluxo geral de como definir a configuração de UPN e a experiência do usuário resultante:

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

*Como compartilhar de um* aplicativo gerenciado por políticas *para outros aplicativos com compartilhamento de SO*

1. Um usuário abre o aplicativo Microsoft OneDrive em um dispositivo iOS registrado e entra na conta corporativa.  A conta em que o usuário entra deve corresponder à conta UPN especificada nas definições de configuração do aplicativo Microsoft OneDrive.

2. Depois de entrar, suas configurações de aplicativo configuradas pelo administrador se aplicam à conta de usuário no Microsoft OneDrive.  Isso inclui definir a configuração **Enviar dados da organização para outros aplicativos** com o valor **Aplicativos gerenciados por política com compartilhamento de SO**.

3. O usuário visualiza um arquivo de trabalho e tenta compartilhar via Abrir em para o aplicativo gerenciado do iOS.  

4. A transferência de dados é bem-sucedida e os dados agora estão protegidos pelo **Abrir no Portal de Gerenciamento** no aplicativo gerenciado pelo iOS.  O aplicativo do Intune não se aplica a aplicativos que não são *aplicativos gerenciados por políticas*.

*Como compartilhar de um* aplicativo gerenciado do iOS *para um* aplicativo gerenciado por política *com dados da organização recebidos*

1. Um usuário abre o email nativo em um dispositivo iOS registrado com um perfil de email gerenciado.  

1. O usuário abre um anexo de documento de trabalho do email nativo para o Microsoft Word.

1. Quando o aplicativo Word é iniciado, uma das duas experiências ocorre:
   1. Os dados são protegidos pelo aplicativo do Intune quando:
      - O usuário é conectado à sua conta corporativa que corresponde ao UPN da conta que você especificou nas definições de configuração do aplicativo Microsoft Word. 
      - As configurações do aplicativo configurado pelo administrador se aplicam à conta de usuário no Microsoft Word.  Isso inclui definir a configuração **Receber dados de outros aplicativos** com o valor **Todos os aplicativos com dados da organização recebidos**.
      - A transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo.  O aplicativo do Intune protege as ações do usuário para o documento.
   1. Os dados **não** são protegidos pelo aplicativo do Intune quando:
      - O usuário **não** está conectado à sua conta corporativa.
      - As configurações definidas pelo administrador não são aplicadas ao Microsoft Word porque o usuário **não** está conectado.
      - A transferência de dados é bem-sucedida e o documento **não** é marcado como identidade corporativa no aplicativo.  O aplicativo do Intune **não** protege as ações do usuário para o documento porque ele não está ativo.

    > [!NOTE]
    > O usuário pode adicionar e usar suas contas pessoais com o Word. As políticas de proteção de aplicativo não se aplicam quando o usuário utiliza o Word fora de um contexto de trabalho. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Validar configuração de UPN do usuário para EMM de terceiros

Depois de definir a configuração de UPN do usuário, valide a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.

Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar. Quando a configuração de política for **Exigir**, o usuário deverá ver um prompt para definir ou inserir um PIN antes de poder acessar os dados da empresa.

Primeiro, [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) no aplicativo iOS. Para obter mais informações sobre como testar a política de proteção de aplicativo, consulte [Validar políticas de proteção do aplicativo](app-protection-policies-validate.md).


## <a name="see-also"></a>Consulte também
[O que é a política de proteção de aplicativo do Intune](app-protection-policy.md)
