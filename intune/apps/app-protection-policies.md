---
title: Criar e implantar políticas de proteção do aplicativo
titleSuffix: Microsoft Intune
description: Este tópico descreve como criar e atribuir as políticas de proteção de aplicativo (APP) do Microsoft Intune.
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
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8657b6fa8110b4ea4bbf8ec0841d69197624dd9f
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563719"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Como criar e atribuir as políticas de proteção de aplicativo

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Saiba como criar e atribuir APP (políticas de proteção de aplicativo) do Microsoft Intune para usuários de sua organização. Este tópico também descreve como fazer alterações nas políticas existentes.

## <a name="before-you-begin"></a>Antes de começar

Políticas de proteção de aplicativo podem se aplicar a aplicativos em execução em dispositivos que podem ou não ser gerenciados pelo Intune. Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários compatíveis com as políticas de Proteção de Aplicativo do Intune, confira [O que são as políticas de Proteção de Aplicativo do Microsoft Intune?](app-protection-policy.md)

Se você estiver procurando uma lista de aplicativos com suporte no MAM, consulte [Lista de aplicativos do MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Para saber mais sobre como adicionar os aplicativos de linha de negócios (LOB) da sua organização ao Microsoft Intune para se preparar para as políticas de proteção de aplicativos, confira [ Adicionar aplicativos ao Microsoft Intune](apps-add.md).

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Políticas de proteção do aplicativo para aplicativos iOS/iPadOS e Android

Quando você cria uma política de proteção de aplicativo para aplicativos iOS/iPadOS e Android, você segue um fluxo de processo moderno do Intune que resulta em uma nova política de proteção.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Criar uma política de proteção de aplicativo iOS/iPadOS ou Android
1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. No portal do Intune, escolha **Aplicativos** > **Políticas de proteção de aplicativo**. Essa seleção abre os detalhes das **Políticas de proteção do aplicativo**, em que você cria novas políticas e edita políticas existentes.
3. Selecione **Criar política** e **iOS/iPadOS** ou **Android**. O painel **Criar política** é exibido.
4. Na página **Conceitos Básicos**, adicione os seguintes valores:

    | Valor | Descrição |
    |--------------|------------------------------------------------|
    | Nome | O nome desta política de proteção de aplicativo. |
    | Descrição | [Opcional] A descrição desta política de proteção de aplicativo. |


    O valor **Plataforma** é definido com base na sua escolha acima.

    ![Captura de tela da página Conceitos Básicos do painel Criar política](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Clique em **Avançar** para exibir a página **Aplicativos**.<br>
    A página **Aplicativos** permite que você escolha como deseja aplicar essa política a aplicativos em diferentes dispositivos. Você deve adicionar pelo menos um aplicativo.<p>
    
    | Valor/opção | Descrição |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Direcionar para aplicativos em todos os tipos de dispositivos | Use esta opção para direcionar sua política a aplicativos em dispositivos de qualquer estado de gerenciamento. Escolha **Não** para direcionar aplicativos em tipos de dispositivos específicos. Para obter mais informações, confira [Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo](#target-app-protection-policies-based-on-device-management-state) |
    |     Tipos de dispositivos | Use esta opção para especificar se esta política se aplica a dispositivos MDM gerenciados ou não gerenciados. Para as políticas de aplicativos iOS, selecione dentre dispositivos **Não gerenciados** e **Gerenciados**. Para as políticas de aplicativos Android, selecione dentre **Não gerenciado**, **Administrador de dispositivo Android** e **Android Enterprise**.  |
    | Aplicativos públicos | Clique em **Selecionar aplicativos públicos** para escolher os aplicativos a serem direcionados. |
    | Aplicativos personalizados | Clique em **Selecionar aplicativos personalizados** para selecionar aplicativos personalizados a serem direcionados com base em uma ID de Pacote. |
    
    Os aplicativos selecionados serão exibidos na lista de aplicativos públicos e personalizados. 
6. Clique em **Avançar** para exibir a página **Proteção de dados**.<br>
    Esta página fornece configurações para controles de DLP (prevenção contra perda de dados), incluindo restrições de cortar, copiar, colar e salvar como. Essas configurações determinar como os usuários interagem com os dados nos aplicativos que essa política de proteção de aplicativo aplica.

    **Configurações de proteção de dados**:<br>
    - **Proteção de dados do iOS/iPadOS** – Para obter informações, confira [Configurações da política de proteção de aplicativo iOS – Proteção de dados](~/apps/app-protection-policy-settings-ios.md#data-protection).
    - **Proteção de dados do Android** – Para obter informações, confira [Configurações da política de proteção de aplicativo Android – Proteção de dados](~/apps/app-protection-policy-settings-android.md#data-protection).

7. Clique em **Avançar** para exibir a página **Requisitos de acesso**.<br>
    Esta página fornece definições para permitir que você configure os requisitos de PIN e de credenciais aos quais os usuários devem atender para acessar aplicativos em um contexto de trabalho. 
 
    **Configurações de requisitos de acesso**:<br>
    - **Requisitos de acesso do iOS/iPadOS** – Para obter informações, confira [Configurações da política de proteção de aplicativo iOS – Requisitos de acesso](~/apps/app-protection-policy-settings-ios.md#access-requirements).
    - **Requisitos de acesso do Android** – Para obter informações, confira [Configurações da política de proteção de aplicativo Android – Requisitos de acesso](~/apps/app-protection-policy-settings-android.md#access-requirements).

8. Clique em **Avançar** para exibir a página **Inicialização condicional**.<br>
    Esta página fornece configurações para definir os requisitos de segurança de entrada de sua política de proteção de aplicativo. Selecione uma **Configuração** e insira o **Valor** que os usuários precisam cumprir para entrar no aplicativo da empresa. Selecione a **Ação** que você deseja executar se os usuários não atendem aos seus requisitos. Em alguns casos, várias ações podem ser definidas para uma única configuração.

    **Configurações de inicialização condicional**:<br>
    - **Inicialização condicional do iOS/iPadOS** – Para obter informações, confira [Configurações da política de proteção de aplicativo iOS – Inicialização condicional](~/apps/app-protection-policy-settings-ios.md#conditional-launch).
    - **Inicialização condicional do Android** – Para obter informações, confira [Configurações da política de proteção de aplicativo Android – Inicialização condicional](~/apps/app-protection-policy-settings-android.md#conditional-launch).

9. Clique em **Avançar** para exibir a página **Atribuições**.<br>
   A página **Atribuições** permite atribuir a política de proteção de aplicativos a grupos de usuários.
   
    >[!IMPORTANT]
    > Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos, a política só será aplicada aos usuários diretamente no grupo que você selecionou. Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.

10. Clique em **Avançar: Examinar + criar** para examinar os valores e configurações inseridos para esta política de proteção de aplicativo.

11. Quando terminar, clique em **Criar** para criar a política de proteção de aplicativo no Intune. 

    > [!TIP]
    > Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo. Quando os usuários finais usam o aplicativo para executar uma tarefa pessoal, eles não são afetados por essas políticas. Observe que, quando você cria um novo arquivo, ele é considerado um arquivo particular. 

Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play. Para obter mais informações, consulte:
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Alterar políticas existentes
Você pode editar uma política existente e aplicá-la aos usuários de destino. No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de oito horas.

Para ver o efeito das alterações imediatamente, o usuário final deve sair do aplicativo e entrar novamente.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Para alterar a lista de aplicativos associados à política

1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Propriedades**.

3. Ao lado da seção intitulada *Aplicativos*, selecione **Editar**.

4. A página **Aplicativos** permite que você escolha como deseja aplicar essa política a aplicativos em diferentes dispositivos. Você deve adicionar pelo menos um aplicativo.<p>
    
    | Valor/opção | Descrição |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Direcionar para aplicativos em todos os tipos de dispositivos | Use esta opção para direcionar sua política a aplicativos em dispositivos de qualquer estado de gerenciamento. Escolha **Não** para direcionar aplicativos em tipos de dispositivos específicos. Para obter mais informações, confira [Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo](#target-app-protection-policies-based-on-device-management-state) |
    |     Tipos de dispositivos | Use esta opção para especificar se esta política se aplica a dispositivos MDM gerenciados ou não gerenciados. Para as políticas de aplicativos iOS, selecione dentre dispositivos **Não gerenciados** e **Gerenciados**. Para as políticas de aplicativos Android, selecione dentre **Não gerenciado**, **Administrador de dispositivo Android** e **Android Enterprise**.  |
    | Aplicativos públicos | Clique em **Selecionar aplicativos públicos** para escolher os aplicativos a serem direcionados. |
    | Aplicativos personalizados | Clique em **Selecionar aplicativos personalizados** para selecionar aplicativos personalizados a serem direcionados com base em uma ID de Pacote. |

    Os aplicativos selecionados serão exibidos na lista de aplicativos públicos e personalizados. 

5. Clique em **Revisar + criar** para examinar os aplicativos selecionados para essa política.

6. Quando terminar, clique em **Salvar** para atualizar a política de proteção de aplicativo.
 
#### <a name="to-change-the-list-of-user-groups"></a>Para alterar a lista de grupos de usuários

1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Propriedades**.

3. Ao lado da seção intitulada *Atribuições*, selecione **Editar**.

4. Para adicionar um novo grupo de usuários à política, na guia *Incluir*, escolha **Selecionar grupos para incluir** e selecione o grupo de usuários. Escolha **Selecionar** para adicionar o grupo. 

5. Para excluir um grupo de usuários, na guia *Excluir* escolha **Selecionar grupos para excluir** e selecione o grupo de usuários. Escolha **Selecione** para remover o grupo de usuários.  

6. Para excluir os grupos que foram adicionados anteriormente, nas guias *Incluir* ou *Excluir*, selecione as reticências (...) e **Excluir**.

7. Clique em **Revisar + criar** para examinar os grupos de usuários selecionados para essa política.

8. Após terminar as alterações às atribuições, selecione **Salvar** para guardar a configuração e implantar a política para o novo conjunto de usuários. Se você selecionar **Cancelar** antes de salvar sua configuração, descartará todas as alterações feitas nas guias *Incluir* e *Excluir*.

### <a name="to-change-policy-settings"></a>Para alterar as configurações de política

1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Propriedades**.

3. Selecione **Editar** ao lado da seção correspondente às configurações que você deseja alterar. Em seguida, altere as configurações para novos valores.

7. Clique em **Revisar + criar** para examinar as configurações atualizadas para essa política.

4. Selecione **Salvar** para salvar suas alterações. Repita o processo para selecionar uma área de configurações e modificar e então salvar suas alterações até que todas as suas alterações tenham sido concluídas. Em seguida, você pode fechar o painel *Proteção de Aplicativo do Intune – Propriedades*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo
Em muitas organizações é comum permitir que os usuários finais usem dispositivos gerenciados MDM (gerenciamento de dispositivo móvel) do Intune, como dispositivos corporativos, bem como dispositivos não gerenciados protegidos apenas com políticas de Proteção de Aplicativo do Intune. Dispositivos não gerenciados são geralmente conhecidos como BYOD (traga seu próprio dispositivos).

Uma vez que as políticas de Proteção de Aplicativo do Intune são direcionadas para a identidade de um usuário, as configurações de proteção para um usuário podem se aplicar tanto a dispositivos registrados (gerenciados por MDM) quanto não registrados (sem MDM). Portanto, você pode ter como destino uma política de Proteção de Aplicativo do Intune para dispositivos Android e iOS registrados ou não registrados no Intune. Você pode ter uma política de proteção para dispositivos não gerenciados, na qual controles de DLP (prevenção contra perda de dados) estritos estejam em vigor, e uma política de proteção separada para dispositivos gerenciados MDM, em que os controles de DLP podem ser um pouco mais flexíveis. Para saber mais sobre como isso funciona em dispositivos Android Enterprise pessoais, confira o tópico [Políticas de proteção de aplicativo e perfis de trabalho](android-deployment-scenarios-app-protection-work-profiles.md).

Para criar essas políticas, navegue até **Aplicativos** > **Políticas de proteção de aplicativo** no console do Intune e selecione **Criar política**. Você também pode editar uma política de proteção do aplicativo existente. Para que a política de proteção de aplicativo seja aplicada a dispositivos gerenciados e não gerenciados, navegue até a página **Aplicativos** e confirme se **Direcionar para aplicativos em todos os tipos de dispositivo** está definido como **Sim**, o valor padrão. Se você desejar atribuir de maneira granular com base no estado de gerenciamento, defina **Direcionar para aplicativos em todos os tipos de dispositivo** como **Não**. 

### <a name="device-types"></a>Tipos de dispositivos

- **Não Gerenciado**: os dispositivos não gerenciados são aqueles em que o gerenciamento de MDM do Intune não foi detectado. Isso inclui dispositivos gerenciados por fornecedores de MDM de terceiros.
- **Dispositivos gerenciados do Intune**: os dispositivos são gerenciados pelo MDM do Intune.
- **Administrador do dispositivo Android**: Dispositivos gerenciados pelo Intune usando a API de Administração de Dispositivo Android.
- **Android Enterprise**: Dispositivos gerenciados pelo Intune usando Perfis de Trabalho do Android Enterprise ou Gerenciamento de Dispositivo Completo do Android Enterprise.

> [!NOTE]
> Os dispositivos Android solicitarão a instalação do aplicativo Portal da Empresa do Intune, independentemente do tipo de dispositivo escolhido. Por exemplo, se você escolher "Android Enterprise", os usuários com dispositivos Android não gerenciados ainda serão solicitados.

Para iOS, são necessárias mais definições de configuração de aplicativo a fim de direcionar as configurações da política de proteção do aplicativo para aplicativos, em dispositivos registrados no Microsoft Intune:

- **IntuneMAMUPN** deve ser configurado para todos os aplicativos gerenciados por MDM. Para obter mais informações, confira [Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **IntuneMAMDeviceID** deve ser configurado para todos os aplicativos de terceiros e gerenciados por MDM de linha de negócios. O **IntuneMAMDeviceID** deve ser configurado para o token de ID do dispositivo. Por exemplo, `key=IntuneMAMDeviceID, value={{deviceID}}`. Para obter mais informações, confira [Adicionar políticas de configuração de aplicativo para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md).
- Se apenas **IntuneMAMDeviceID** estiver configurado, o aplicativo do Intune considerará que o dispositivo como não gerenciado.

> [!NOTE]
> Para obter informações de suporte do iOS específicas sobre políticas de proteção do aplicativo com base no estado de gerenciamento de dispositivo, consulte [Políticas de proteção MAM direcionadas com base no estado de gerenciamento](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state).

## <a name="policy-settings"></a>Configurações de política
Para ver uma lista completa das configurações de política para iOS e Android, selecione um dos seguintes links:

- [Políticas do iOS](app-protection-policy-settings-ios.md)
- [Políticas do Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Próximas etapas
[Monitorar conformidade e status do usuário](app-protection-policies-monitor.md)

## <a name="see-also"></a>Consulte também
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-ios.md)
