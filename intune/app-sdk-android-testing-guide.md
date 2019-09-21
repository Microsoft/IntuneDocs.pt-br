---
title: Guia de teste para desenvolvedores do SDK de Aplicativo do Microsoft Intune para Android
description: O guia de teste do SDK do Aplicativo do Microsoft Intune para Android ajuda a testar seu aplicativo Android gerenciado pelo Intune.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91b7fc7414c3a6d6517cd4b704cb5e99ddcf96d0
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167175"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Guia de teste para desenvolvedores do SDK de Aplicativo do Microsoft Intune para Android

O guia de teste do SDK do Aplicativo do Microsoft Intune para Android é desenvolvido para ajudar a testar seu aplicativo Android gerenciado pelo Intune.  

## <a name="prerequisite-test-accounts"></a>Contas de teste de pré-requisito
Novas contas podem ser criadas com e sem dados gerados previamente. Para criar uma nova conta:
1. Navegue até o site [Demos da Microsoft](https://demos.microsoft.com/environments/create/tenant). 
2. [Configure o Intune](setup-steps.md) para habilitar o MDM (gerenciamento de dispositivo móvel).
3. [Criar usuários](users-add.md).
4. [Criar grupos](groups-add.md).
5. [Atribua licenças](licenses-assign.md) conforme apropriado para seu teste.


## <a name="azure-portal-policy-configuration"></a>Configuração de política do portal do Azure
[Crie e atribua políticas de proteção de aplicativo](app-protection-policies.md) na [folha do Intune do portal do Azure](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Sua [política de configuração de aplicativos](app-configuration-policies-overview.md) também pode ser criada e atribuída na folha do Intune.

> [!NOTE]
> Se seu aplicativo não estiver listado no portal do Azure, você poderá defini-lo como destino com uma política selecionando a opção **mais aplicativos** e dando um nome ao pacote na caixa de texto.

> [!IMPORTANT]
> Para uma política de configuração de aplicativos ser aplicada, o usuário que está se registrando deve ser definido como destino por uma [política de proteção de aplicativo do Intune](app-protection-policy.md).

## <a name="test-cases"></a>Casos de teste

Os casos de teste a seguir fornecem as etapas de configuração e confirmação. Use estas diretrizes para ajudar a solucionar problemas de aplicativo Android gerenciado pelo Intune.

### <a name="required-pin-and-corporate-credentials"></a>Credenciais corporativas e PIN obrigatórios

Você pode exigir um PIN para acessar recursos corporativos. Além disso, você pode impor autenticação corporativa antes que os usuários poderem usar aplicativos gerenciados. Use as etapas a seguir para definir estes requisitos:

1. Configure **Exigir PIN para acesso** e **Exigir credenciais corporativas para acesso** como **Sim**. Para mais informações, confira [Configurações de política de proteção do aplicativo Android no Microsoft Intune](app-protection-policy-settings-android.md#access-requirements).
2. Confirme as seguintes condições:
    - A inicialização do aplicativo deve apresentar um prompt para entrada de PIN/instalação e/ou o usuário de produção que foi usado durante o registro com o Portal da Empresa.
    - Falha na apresentação de uma solicitação de conexão válida pode ser devido a um manifesto do Android configurado incorretamente, especificamente os valores para a integração de ADAL (SkipBroker, ClientID e Autoridade).
    - A falha na apresentação de qualquer prompt pode ser devido a um valor `MAMActivity` integrado incorretamente. Para obter mais informações sobre `MAMActivity`, veja [Guia do desenvolvedor do SDK de Aplicativo do Microsoft Intune para Android](app-sdk-android.md).

> [!NOTE] 
> Se o teste acima não estiver funcionando, os testes abaixo provavelmente também falharão. Examine a integração de [SDK](app-sdk-android.md##sdk-integration) e [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Restringir a transferência e receber dados com outros aplicativos
Você pode controlar a transferência de dados entre aplicativos gerenciados corporativos da seguinte maneira:

1. Defina **Permitir ao aplicativo transferir dados para outros aplicativos** como **Aplicativos gerenciados por política**.
2. Defina **Permitir que o aplicativo receba dados de outros aplicativos** para **Todos os aplicativos**. O uso de provedores de conteúdo e intenções será afetado por essas políticas.
3. Confirme as seguintes condições:
    - Abrir de um aplicativo não gerenciado em seu aplicativo funciona corretamente.
    - Compartilhar conteúdo entre aplicativos gerenciados é permitido.
    - Compartilhar de aplicativos gerenciados para aplicativos não gerenciados (por exemplo, Chrome) é bloqueado.

### <a name="restrict-cut-copy-and-paste"></a>Restringir recortar, copiar e colar
Você pode restringir a área de transferência do sistema a aplicativos gerenciados da seguinte maneira:

1. Defina **Restringir recortar, copiar e colar com outros aplicativos** como **Gerenciados por política com colar em**.
2. Confirme as seguintes condições:
    - Copiar o texto de seu aplicativo para um aplicativo gerenciado e não gerenciado (por exemplo, mensagens) está bloqueado.

### <a name="prevent-save-as"></a>Impedir **Salvar Como**
Você pode controlar a funcionalidade **Salvar como** da seguinte maneira:

1. Se seu aplicativo exigir [controles 'salvar como' integrados](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), defina **Prevenir 'Salvar como'** como **Sim**.
2. Confirme as seguintes condições:
    - Salvar está restrito a apenas os locais gerenciados apropriados.

### <a name="file-encryption"></a>Criptografia de Arquivo
Você pode criptografar dados no dispositivo da seguinte maneira:

1. Defina **Criptografar dados do aplicativo** como **Sim**.
2. Confirme as seguintes condições:
    - O comportamento normal do aplicativo não é afetado.

### <a name="prevent-android-backups"></a>Impedir backups do Android
Você pode controlar o backup do aplicativo da seguinte maneira:

1. Se você tiver definido [restrições de backup integrado](app-sdk-android.md#protecting-backup-data), configure **Prevenir backups do Android** como **Sim**.
2. Confirme as seguintes condições:
    - Os backups são restritos.

### <a name="unenrollment"></a>Cancelamento de registro
Você pode apagar remotamente aplicativos gerenciados que contêm email e documentos corporativos, e os dados pessoais são descriptografados quando não são mais administrados da seguinte maneira:

1. No portal do Azure, [emita um apagamento](apps-selective-wipe.md).
2. Caso seu aplicativo não esteja registrado para nenhum manipulador de apagamento, confirme as seguintes condições:
    - Ocorre um apagamento completo do aplicativo.
3. Se seu aplicativo tiver se registrado para `WIPE_USER_DATA` ou `WIPE_USER_AUXILARY_DATA`, confirme as seguintes condições:
    - O conteúdo gerenciado é removido do aplicativo. Para obter mais informações, veja o [guia do desenvolvedor do SDK do Aplicativo do Intune para Android – Apagamento Seletivo](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Várias identidades
Integrar [suporte a várias identidades](app-sdk-android.md#multi-identity-optional) é uma alteração de alto risco que precisa ser totalmente testada. Os problemas mais comuns serão devidos à configuração incorreta da identidade (nível de contexto vs. de ameaça) e também arquivos de acompanhamento (`MAMFileProtectionManager`).

No mínimo, os seguintes cenários para várias identidades devem ser revalidados:

- A política **Salvar Como** está funcionando corretamente para identidades gerenciadas.
- As restrições de copiar e colar são impostas corretamente de gerenciadas para pessoais.
- Somente os dados pertencentes à identidade gerenciada são criptografados e arquivos pessoais não são modificados.
- Apagamento seletivo durante o cancelamento de registro só remove os dados de identidade gerenciada.
- O usuário final é solicitado a realizar uma inicialização condicional ao mudar de conta não gerenciada para gerenciada (apenas na primeira vez).

### <a name="app-configuration-optional"></a>Configuração de aplicativos (opcional)
Você pode configurar o comportamento de aplicativos gerenciados da seguinte maneira:

1. Se seu aplicativo consumir as definições de configuração de aplicativos, você deverá testar para ver se seu aplicativo lida corretamente com todos os valores que você, como administrador, pode definir. As [políticas de configuração de aplicativos](app-configuration-policies-overview.md) podem ser criadas e atribuídas usando o Intune.

## <a name="next-steps"></a>Próximas etapas

- [Adicionar um aplicativo de linha de negócios do Android ao Microsoft Intune](lob-apps-android.md).
