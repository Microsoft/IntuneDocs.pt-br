---
title: Guia de teste do SDK do Aplicativo do Microsoft Intune para Android
description: O guia de teste do SDK do Aplicativo do Microsoft Intune para Android ajuda a testar seu aplicativo Android gerenciado pelo Intune.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9eada01f2b1e876d6d3b47140c671e3ff7eeab02
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503499"
---
# <a name="microsoft-intune-app-sdk-for-android-testing-guide"></a>Guia de teste do SDK do Aplicativo do Microsoft Intune para Android

Este guia ajuda os desenvolvedores a testar seus aplicativos Android gerenciados pelo Intune.  

## <a name="prerequisite-test-accounts"></a>Contas de teste de pré-requisito
Você pode criar novas contas com ou sem dados gerados previamente. Para criar uma nova conta:
1. Vá ao site de [Demos da Microsoft](https://demos.microsoft.com/environments/create/tenant). 
2. [Configure o Intune](../fundamentals/setup-steps.md) para habilitar o MDM (gerenciamento de dispositivo móvel).
3. [Criar usuários](../fundamentals/users-add.md).
4. [Criar grupos](../fundamentals/groups-add.md).
5. [Atribua licenças](../fundamentals/licenses-assign.md) conforme apropriado para seu teste.


## <a name="azure-portal-policy-configuration"></a>Configuração de política do portal do Azure
[Crie e atribua políticas de proteção de aplicativo](../apps/app-protection-policies.md) na [folha do Intune do portal do Azure](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Você também pode criar e atribuir sua [política de configuração de aplicativo](../apps/app-configuration-policies-overview.md) na folha do Intune.

> [!NOTE]
> Se seu aplicativo não estiver listado no portal do Azure, você poderá defini-lo como destino com uma política selecionando a opção **mais aplicativos** e dando um nome ao pacote na caixa de texto.

## <a name="test-cases"></a>Casos de teste

Os casos de teste a seguir fornecem as etapas de configuração e confirmação. Use estas diretrizes para ajudar a solucionar problemas de aplicativo Android gerenciado pelo Intune.

### <a name="required-pin-and-corporate-credentials"></a>Credenciais corporativas e PIN obrigatórios

Você pode solicitar um PIN para acessar recursos corporativos. Além disso, você pode impor autenticação corporativa antes que os usuários poderem usar aplicativos gerenciados. Aqui está como:

1. Configure **Solicitar PIN para acesso** e **Solicitar credenciais corporativas para acesso** como **Sim**. Para mais informações, confira [Configurações de política de proteção do aplicativo Android no Microsoft Intune](../apps/app-protection-policy-settings-android.md#access-requirements).
2. Confirme as seguintes condições:
    - A inicialização do aplicativo deve apresentar um prompt para entrada de PIN ou do usuário de produção usado durante o registro no Portal da Empresa.
    - A falha em apresentar uma solicitação de entrada válida pode ser devido a um manifesto do Android configurado incorretamente, especificamente os valores para a integração da ADAL (O skipbroker Authentication Library) (Azure Active Directory a autenticação, a ClientID e a autoridade).
    - A falha em apresentar qualquer prompt pode ocorrer devido a um valor `MAMActivity` integrado incorretamente. Para obter mais informações sobre `MAMActivity`, veja [Guia do desenvolvedor do SDK de Aplicativo do Microsoft Intune para Android](app-sdk-android.md).

> [!NOTE] 
> Se o teste anterior não estiver funcionando, os testes a seguir provavelmente também falharão. Examine a integração de [SDK](app-sdk-android.md##sdk-integration) e [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Restringir a transferência e receber dados com outros aplicativos
É possível controlar a transferência de dados entre aplicativos gerenciados corporativos da seguinte maneira:

1. Defina **Permitir ao aplicativo transferir dados para outros aplicativos** como **Aplicativos gerenciados por política**.
2. Defina **Permitir que o aplicativo receba dados de outros aplicativos** para **Todos os aplicativos**. O uso de provedores de conteúdo e intenções é afetado por essas políticas.
3. Confirme as seguintes condições:
    - Abrir de um aplicativo não gerenciado em seu aplicativo funciona corretamente.
    - Compartilhar conteúdo entre aplicativos gerenciados é permitido.
    - Compartilhar de aplicativos gerenciados para aplicativos não gerenciados (por exemplo, Chrome) é bloqueado.

### <a name="restrict-cut-copy-and-paste"></a>Restringir recortar, copiar e colar
Você pode restringir a área de transferência do sistema a aplicativos gerenciados da seguinte maneira:

1. Defina **Restringir recortar, copiar e colar com outros aplicativos** como **Gerenciados por política com colar em**.
2. Confirme as seguintes condições:
    - A cópia de texto de seu aplicativo em um aplicativo não gerenciado (por exemplo, mensagens) está bloqueada.

### <a name="prevent-save"></a>Impedir o salvamento
É possível controlar a funcionalidade **Salvar como** da seguinte maneira:

1. Se seu aplicativo exigir [controles integrados ao 'Salvar como' ](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), defina **Impedir 'Salvar como'** como **Sim**.
2. Confirme as seguintes condições:
    - Salvar está restrito a apenas os locais gerenciados apropriados.

### <a name="file-encryption"></a>Criptografia de arquivo
Você pode criptografar dados no dispositivo da seguinte maneira:

1. Defina **Criptografar dados do aplicativo** como **Sim**.
2. Confirme as seguintes condições:
    - O comportamento normal do aplicativo não é afetado.

### <a name="prevent-android-backups"></a>Impedir backups do Android
É possível controlar o backup do aplicativo da seguinte maneira:

1. Se você tiver definido as [restrições de backup integrado](app-sdk-android.md#protecting-backup-data), configure **Impedir backups do Android** como **Sim**.
2. Confirme as seguintes condições:
    - Os backups são restritos.

### <a name="unenrollment"></a>Cancelamento de registro
Você pode apagar remotamente aplicativos gerenciados que contêm email e documentos corporativos, e os dados pessoais serão descriptografados quando não forem mais administrados. Aqui está como:

1. No portal do Azure, [emita um apagamento](../apps/apps-selective-wipe.md).
2. Caso seu aplicativo não esteja registrado para nenhum manipulador de apagamento, confirme as seguintes condições:
    - Ocorre um apagamento completo do aplicativo.
3. Se seu aplicativo tiver se registrado para `WIPE_USER_DATA` ou `WIPE_USER_AUXILARY_DATA`, confirme as seguintes condições:
    - O conteúdo gerenciado é removido do aplicativo. Para obter mais informações, veja o [Guia do desenvolvedor do SDK do Aplicativo do Intune para Android – Apagamento seletivo](app-sdk-android.md#selective-wipe).

### <a name="multi-identity-support"></a>Suporte a várias identidades
Integrar [suporte a várias identidades](app-sdk-android.md#multi-identity-optional) é uma alteração de alto risco que precisa ser totalmente testada. Os problemas mais comuns ocorrem devido à configuração inadequada da identidade (contexto versus nível de ameaça) e aos arquivos de rastreamento (`MAMFileProtectionManager`).

No mínimo, confirme que:

- A política **Salvar Como** está funcionando corretamente para identidades gerenciadas.
- As restrições de copiar e colar são impostas corretamente, passando de gerenciadas para pessoais.
- Somente os dados pertencentes à identidade gerenciada são criptografados e arquivos pessoais não são modificados.
- Apagamento seletivo durante o cancelamento de registro só remove os dados de identidade gerenciada.
- O usuário é solicitado a realizar uma inicialização condicional ao mudar de conta não gerenciada para gerenciada (apenas na primeira vez).

### <a name="app-configuration-optional"></a>Configuração de aplicativos (opcional)
Você pode configurar o comportamento de aplicativos gerenciados. Se seu aplicativo consumir as definições de configuração de aplicativos, você deverá testar para ver se seu aplicativo lida corretamente com todos os valores que você, como administrador, pode definir. Você pode criar e atribuir [políticas de configuração de aplicativo](../apps/app-configuration-policies-overview.md) no Intune.

## <a name="next-steps"></a>Próximas etapas

- [Adicionar um aplicativo de linha de negócios do Android ao Microsoft Intune](../apps/lob-apps-android.md)
