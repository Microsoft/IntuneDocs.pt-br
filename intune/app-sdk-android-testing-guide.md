---
title: Guia de teste para desenvolvedores do SDK de Aplicativo do Microsoft Intune para Android
description: SDK do Microsoft Intune App para Android guia teste ajuda a testar seu aplicativo Android gerenciado pelo Intune.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4203f424c395399cb0ed1e7472b006602aa0b210
ms.sourcegitcommit: db7a6b8fc9e82dae4f2111ca0b2d3c14e33658f9
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58072465"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Guia de teste para desenvolvedores do SDK de Aplicativo do Microsoft Intune para Android

SDK do Microsoft Intune App para Android guia teste foi projetado para ajudá-lo a testar seu aplicativo Android gerenciado pelo Intune.  

## <a name="prerequisite-test-accounts"></a>Contas de teste de pré-requisito
Novas contas podem ser criadas com e sem dados gerados previamente. Para criar uma nova conta:
1. Navegue até a [Demos Microsoft](https://demos.microsoft.com/environments/create/tenant) site. 
2. [Configurar o Intune](https://docs.microsoft.com/intune/setup-steps) para habilitar o gerenciamento de dispositivo móvel (MDM).
3. [Criar usuários](https://docs.microsoft.com/intune/users-add).
4. [Criar grupos](https://docs.microsoft.com/intune/groups-add).
5. [Atribuir licenças](https://docs.microsoft.com/intune/licenses-assign) conforme apropriado para seu teste.


## <a name="azure-portal-policy-configuration"></a>Configuração de política do portal do Azure
[Criar e atribuir as políticas de proteção de aplicativo](https://docs.microsoft.com/intune/app-protection-policies) no [folha do Intune do portal do Azure](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Sua [política de configuração de aplicativo](https://docs.microsoft.com/intune/app-configuration-policies-overview) também podem ser criados e atribuídos na folha do Intune.

> [!NOTE]
> Se seu aplicativo não estiver listado no portal do Azure, você pode direcioná-lo com uma política, selecionando o **mais aplicativos** opção e fornecendo o nome do pacote na caixa de texto.

> [!IMPORTANT]
> Para uma política de configuração de aplicativo a ser aplicado, o usuário de registro deve ser alvo de uma [política de proteção de aplicativo do Intune](https://docs.microsoft.com/intune/app-protection-policy).

## <a name="test-cases"></a>Casos de teste

Os casos de teste a seguir fornecem as etapas de configuração e a confirmação. Use essas diretrizes para ajudar a solucionar problemas de aplicativo Android gerenciado pelo Intune.

### <a name="required-pin-and-corporate-credentials"></a>Credenciais corporativas e PIN necessária

Você pode exigir um pin para acessar recursos corporativos. Além disso, você pode impor autenticação corporativa antes que os usuários podem usar aplicativos gerenciados. Use as etapas a seguir para definir esses requisitos:

1. Configure **exigir PIN para acesso** e **exigir credenciais corporativas para acesso** para **Sim**. Para mais informações, confira [Configurações de política de proteção do aplicativo Android no Microsoft Intune](app-protection-policy-settings-android.md#access-requirements).
2. Confirme as seguintes condições:
    - Inicialização do aplicativo deve apresentar um prompt para entrada PIN/instalação e/ou o usuário de produção que foi usado durante o registro com o Portal da empresa.
    - Falha na apresentação de uma solicitação de conexão válida pode ser devido a um manifesto do android configurado incorretamente, especificamente os valores para a integração ADAL (SkipBroker, ClientID e autoridade).
    - Falha na apresentação de qualquer prompt pode ser devido a um incorretamente integrado `MAMActivity` valor. Para obter mais informações sobre `MAMActivity`, consulte [Microsoft Intune App SDK para o guia do desenvolvedor Android](app-sdk-android.md).

> [!NOTE] 
> Se o teste acima não estiver funcionando, os testes abaixo provavelmente também falhará. Revisão [SDK](app-sdk-android.md##sdk-integration) e [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) integração.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Restringir a transferência e receber dados com outros aplicativos
Você pode controlar a transferência de dados entre aplicativos gerenciados corporativos da seguinte maneira:

1. Definir **permitir que o aplicativo transfira dados para outros aplicativos** à **aplicativos gerenciados por política**.
2. Defina **Permitir que o aplicativo receba dados de outros aplicativos** para **Todos os aplicativos**. Uso de provedores de conteúdo e tentativas será afetado por essas políticas.
3. Confirme as seguintes condições:
    - Abertura de um aplicativo não gerenciado em funções do aplicativo corretamente.
    - Compartilhamento de conteúdo entre aplicativos gerenciados é permitido.
    - Compartilhamento de aplicativos gerenciados para aplicativos não gerenciados (por exemplo, o Chrome) é bloqueado.

### <a name="restrict-cut-copy-and-paste"></a>Restringir recortar, copiar e colar
Você pode restringir a área de transferência do sistema para aplicativos gerenciados da seguinte maneira:

1. Definir **restringir recortar, copiar e colar com outros aplicativos** à **gerenciados por política com Colar em**.
2. Confirme as seguintes condições:
    - Copiar o texto de seu aplicativo em um gerenciado um aplicativo não gerenciado (por exemplo, mensagens) está bloqueado.

### <a name="prevent-save-as"></a>Impedir **Salvar Como**
Você pode controlar **Salvar como** funcionalidade da seguinte maneira:

1. Se seu aplicativo requer [integrado 'Salvar como' controles](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), defina **impedir "Salvar como"** para **Sim**.
2. Confirme as seguintes condições:
    - Salvar é restrito a apenas locais gerenciados apropriados.

### <a name="file-encryption"></a>Criptografia de Arquivo
Você pode criptografar dados no dispositivo, da seguinte maneira:

1. Definir **criptografar dados do aplicativo** à **Sim**.
2. Confirme as seguintes condições:
    - Comportamento normal do aplicativo não é afetado.

### <a name="prevent-android-backups"></a>Impedir backups do Android
Você pode controlar o backup do aplicativo da seguinte maneira:

1. Se você tiver definido [integrado a restrições de backup](app-sdk-android.md#protecting-backup-data), configure **evitar backups do Android** para **Sim**.
2. Confirme as seguintes condições:
    - Os backups são restritos.

### <a name="unenrollment"></a>Cancelamento de registro
Você pode apagar remotamente os aplicativos gerenciados do que contêm documentos e emails corporativos e dados pessoais são descriptografados quando não for administrado da seguinte maneira:

1. No portal do Azure, [emita um apagamento](https://docs.microsoft.com/intune/apps-selective-wipe).
2. Se seu aplicativo não se registrar para todos os manipuladores apagamento confirme as seguintes condições:
    - Ocorre um apagamento completo do aplicativo.
3. Se seu aplicativo registrou `WIPE_USER_DATA` ou `WIPE_USER_AUXILARY_DATA`, confirme as seguintes condições:
    - O conteúdo gerenciado é removido do aplicativo. Para obter mais informações, consulte [SDK do Intune App para o guia do desenvolvedor do Android – apagamento seletivo do](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Várias identidades
Integrando [suporte a várias identidades](app-sdk-android.md#multi-identity-optional) é uma alteração de alto risco que precisa ser totalmente testados. Os problemas mais comuns serão devidos à configuração incorreta da identidade (contexto vs. o nível de ameaça) e também arquivos de controle (`MAMFileProtectionManager`).

No mínimo devem ser revalidados os seguintes cenários de várias identidades:

- **Salvar como** política está funcionando corretamente para identidades gerenciadas.
- Copie e colar as restrições são impostas corretamente do código gerenciado para pessoal.
- Somente os dados pertencentes à identidade gerenciada são criptografados e arquivos pessoais não são modificados.
- Apagamento seletivo durante o cancelamento de registro só remove os dados de identidade gerenciada.
- O usuário final é solicitado para a inicialização condicional ao alterar de não gerenciado para a conta gerenciada (apenas na primeira vez).

### <a name="app-configuration-optional"></a>Configuração do aplicativo (opcional)
Você pode configurar o comportamento de aplicativos gerenciados da seguinte maneira:

1. Se seu aplicativo consome as definições de configuração de aplicativo, você deve testar que seu aplicativo lida corretamente com todos os valores (como administrador) podem ser definidas. [As políticas de configuração de aplicativo](https://docs.microsoft.com/intune/app-configuration-policies-overview) podem ser criados e atribuídos usando o Intune.

## <a name="next-steps"></a>Próximas etapas

- [Adicionar um aplicativo de linha de negócios do Android ao Microsoft Intune](lob-apps-android.md).
