---
title: Criar e implantar políticas de proteção do aplicativo
titleSuffix: Microsoft Intune
description: Este tópico descreve como criar e atribuir as políticas de proteção de aplicativo (APP) do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
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
ms.openlocfilehash: a8e105dae43c4e7139c8e44a8c6535baebe31cc4
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585443"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Como criar e atribuir as políticas de proteção de aplicativo

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Saiba como criar e atribuir APP (políticas de proteção de aplicativo) do Microsoft Intune para usuários de sua organização. Este tópico também descreve como fazer alterações nas políticas existentes.

## <a name="before-you-begin"></a>Antes de começar

Políticas de proteção de aplicativo podem se aplicar a aplicativos em execução em dispositivos que podem ou não ser gerenciados pelo Intune. Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários compatíveis com as políticas de Proteção de Aplicativo do Intune, confira [O que são as políticas de Proteção de Aplicativo do Microsoft Intune?](app-protection-policy.md)

Se você estiver procurando uma lista de aplicativos com suporte no MAM, consulte [Lista de aplicativos do MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Para saber mais sobre como adicionar os aplicativos de linha de negócios (LOB) da sua organização ao Microsoft Intune para se preparar para as políticas de proteção de aplicativos, confira [ Adicionar aplicativos ao Microsoft Intune](apps-add.md).

No momento, o fluxo de processo para criar uma política de proteção de aplicativo se diferencia com base na plataforma:
- Políticas de proteção do aplicativo para aplicativos iOS/iPadOS e Android
- Políticas de proteção do aplicativo para aplicativos Windows 10

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Políticas de proteção do aplicativo para aplicativos iOS/iPadOS e Android

Quando você cria uma política de proteção de aplicativo para aplicativos iOS/iPadOS e Android, você segue um fluxo de processo moderno do Intune que resulta em uma nova política de proteção.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Criar uma política de proteção de aplicativo iOS/iPadOS ou Android
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No portal do Intune, escolha **Aplicativos cliente** > **Políticas de proteção de aplicativo**. Essa seleção abre os detalhes das **Políticas de proteção do aplicativo**, em que você cria novas políticas e edita políticas existentes.
3. Selecione **Criar política** e **iOS/iPadOS** ou **Android**. A folha **Criar política** é exibida.
4. Na página **Conceitos Básicos**, adicione os seguintes valores:

    | Valor | Descrição |
    |--------------|------------------------------------------------|
    | Nome | O nome desta política de proteção de aplicativo. |
    | Descrição | [Opcional] A descrição desta política de proteção de aplicativo. |


    O valor **Plataforma** é definido com base na sua escolha acima.

    ![Captura de tela da página Conceitos Básicos da folha Criar política](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Clique em **Avançar** para exibir a página **Aplicativos**.<br>
    A página **Aplicativos** permite que você escolha como deseja aplicar essa política a aplicativos em diferentes dispositivos. Você deve adicionar pelo menos um aplicativo.<p>
    
    | Valor/opção | Descrição |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Direcionar para aplicativos em todos os tipos de dispositivos | Use esta opção para direcionar sua política a aplicativos em dispositivos de qualquer estado de gerenciamento. Escolha **Não** para direcionar aplicativos em tipos de dispositivos específicos. |
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

7. Clique em **Avançar** para exibir a página **Atribuições**.<br>
   A página **Atribuições** permite que você possa atribuir a política de proteção de aplicativo a grupos de usuários. 
8. Clique em **Avançar: Examinar + criar** para examinar os valores e configurações inseridos para esta política de proteção de aplicativo.
9. Quando terminar, clique em **Criar** para criar a política de proteção de aplicativo no Intune. 

## <a name="app-protection-policies-for-windows-10-apps"></a>Políticas de proteção do aplicativo para aplicativos Windows 10

Ao criar uma política de proteção de aplicativo para aplicativos Windows 10, você seguirá um fluxo de processo clássico do Intune.

### <a name="create-a-windows-10-app-protection-policy"></a>Criar uma política de proteção de aplicativo Windows 10
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No portal do Intune, escolha **Aplicativos cliente** > **Políticas de proteção de aplicativo**. Essa seleção abre os detalhes das **Políticas de proteção do aplicativo**, em que você cria novas políticas e edita políticas existentes.
3. Selecione **Criar política**.

    <img alt="Screenshot of the 'Create policy' blade for Windows 10" src="~/apps/media/app-protection-policies/app-protection-add-policy.png" width="350">

4. Especifique um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para a política. Você pode criar mais de uma política para cada plataforma.

4. Você pode optar por **Direcionar a todos os tipos de aplicativo**. Esta opção permite que você direcione sua política a aplicativos em dispositivos de qualquer estado de gerenciamento. Durante a resolução de conflitos de política, essa configuração será substituída se um usuário tiver uma política direcionada para um estado de gerenciamento específico. Para obter mais informações, consulte [Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo](~/apps/app-protection-policies.md#target-app-protection-policies-based-on-device-management-state).

5. Selecione **Aplicativos** para abrir a folha **Aplicativos**, em que uma lista de aplicativos disponíveis é exibida. Selecione um ou mais aplicativos da lista que deseja associar com a política que você está criando. Selecione pelo menos um aplicativo para criar uma política.  

6. Depois de selecionar os aplicativos, escolha **Selecionar** para salvar a seleção.

7. Na folha **Adicionar uma política**, selecione **Definir configurações necessárias** para abrir **Configurações**.

   Há três categorias de configurações de política:
   - **Proteção de dados**: esse grupo inclui os controles de DLP (prevenção de perda dados), como restrições de cortar, copiar, colar e salvar como. Essas configurações determinam como os usuários interagem com os dados nos aplicativos.
   - **Requisitos de acesso** – esse grupo contém as opções de PIN por aplicativo que determinam como o usuário final acessa os aplicativos em um contexto de trabalho.  
   - **Inicialização condicional** – esse grupo contém configurações como configurações de sistema operacional mínimo, jailbreak e detecção de dispositivos com raiz e períodos de cortesia offline.

   As configurações de política têm valores padrão para que você possa começar mais facilmente. Se os valores padrão atendem aos seus requisitos, não é necessário fazer alterações.

   > [!TIP]
   > Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo. Quando os usuários finais usam o aplicativo para executar uma tarefa pessoal, eles não são afetados por essas políticas. Observe que, quando você cria um novo arquivo, ele é considerado um arquivo particular. 

8. Selecione **OK** para salvar essa configuração. Agora você retornou à folha **Adicionar uma política**.
9. Selecione **Criar** para criar a política e salvar suas configurações.

Novas políticas do Windows 10 que você criar não serão atribuídas a nenhum usuário até que você explicitamente faça isso. Para atribuir uma política do Windows 10, confira [Atribuir uma política do Windows 10 aos usuários](~/apps/app-protection-policies.md#assign-a-windows-10-policy-to-users)

### <a name="assign-a-windows-10-policy-to-users"></a>Atribuir uma política do Windows 10 a usuários 

1. No painel **Políticas de proteção do aplicativo**, selecione uma política.

2. No painel ***Proteção de Aplicativo do Intune**, selecione **Atribuições** para abrir o painel **Proteção de Aplicativo do Intune – Atribuições**. Na guia *Incluir*, selecione **Selecionar grupos a incluir**. 

   ![Captura de tela do painel Atribuições com o menu Selecionar grupos a serem incluídos](./media/app-protection-policies/app-protection-policy-add-users.png)

3. Uma lista de todos os grupos de segurança no seu **Azure Active Directory** é exibida. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Selecionar**. 

    ![Captura de tela do painel Adicionar grupo de usuários com a lista de usuários do Azure AD](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Depois de incluir e excluir grupos, selecione **Salvar** para guardar a configuração e implantar a política aos usuários. Se você selecionar **Descartar** antes de salvar sua configuração, descartará todas as alterações feitas nas guias *Incluir* e *Excluir*.   
 
     ![Captura de tela mostrando as opções para salvar e descartar](./media/app-protection-policies/save-assignment.png)
  
Agora você criou uma política e a implantou para os usuários.

Somente usuários atribuídos com licenças do Microsoft Intune serão afetados pela política. Os usuários do grupo de segurança selecionado, que não têm uma licença do Intune atribuída, não serão afetados.

>[!IMPORTANT]
> Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos, a política só será aplicada aos usuários diretamente no grupo que você selecionou. Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.

Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play. Para obter mais informações, consulte:
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-ios.md)

### <a name="change-existing-windows-10-policies"></a>Alterar políticas do Windows 10 existentes
Você pode editar uma política existente e aplicá-la aos usuários de destino. No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de oito horas.

Para ver o efeito das alterações imediatamente, o usuário final deve sair do aplicativo e entrar novamente.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Para alterar a lista de aplicativos associados à política

1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Aplicativos de destino** para abrir a lista de aplicativos.

3. Remova ou adicione aplicativos da lista e selecione o ícone **Salvar** para salvar suas alterações.

#### <a name="to-change-the-list-of-user-groups"></a>Para alterar a lista de grupos de usuários

1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Atribuições** para abrir o painel **Proteção de Aplicativo do Intune – Atribuições**, que mostra a lista atual de grupos de usuários que têm essa política.

3. Para adicionar um novo grupo de usuários à política, na guia *Incluir*, escolha **Selecionar grupos para incluir** e selecione o grupo de usuários. Escolha **Selecionar** para adicionar o grupo. 

4. Para excluir um grupo de usuários, na guia *Excluir* escolha **Selecionar grupos para excluir** e selecione o grupo de usuários. Escolha **Selecione** para remover o grupo de usuários.  

5. Para excluir os grupos que foram adicionados anteriormente, nas guias *Incluir* ou *Excluir*, selecione as reticências (...) e **Excluir**. 

5. Após terminar as alterações às atribuições, selecione **Salvar** para guardar a configuração e implantar a política para o novo conjunto de usuários. Se você selecionar **Descartar** antes de salvar sua configuração, descartará todas as alterações feitas nas guias *Incluir* e *Excluir*.

### <a name="to-change-windows-10-policy-settings"></a>Para alterar as configurações de política do Windows 10

1. No painel **Políticas de proteção de aplicativo**, escolha a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Propriedades** para abrir a lista de áreas de configurações que você pode editar. 

3. Selecione a área de configurações com as configurações que você deseja alterar, como **Realocação de dados** ou **Requisitos de acesso**. Em seguida, altere as configurações para novos valores.

4. Selecione o ícone **Salvar** para salvar suas alterações. Repita o processo para selecionar uma área de configurações e modificar e então salvar suas alterações até que todas as suas alterações tenham sido concluídas. Em seguida, você pode fechar o painel *Proteção de Aplicativo do Intune – Propriedades*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo
Em muitas organizações é comum permitir que os usuários finais usem dispositivos gerenciados MDM (gerenciamento de dispositivo móvel) do Intune, como dispositivos corporativos, bem como dispositivos não gerenciados protegidos apenas com políticas de Proteção de Aplicativo do Intune. Dispositivos não gerenciados são geralmente conhecidos como BYOD (traga seu próprio dispositivos).

Uma vez que as políticas de Proteção de Aplicativo do Intune são direcionadas para a identidade de um usuário, as configurações de proteção para um usuário podem se aplicar tanto a dispositivos registrados (gerenciados por MDM) quanto não registrados (sem MDM). Portanto, você pode ter como destino uma política de Proteção de Aplicativo do Intune para dispositivos Android e iOS registrados ou não registrados no Intune. Você pode ter uma política de proteção para dispositivos não gerenciados, na qual controles de DLP (prevenção contra perda de dados) estritos estejam em vigor, e uma política de proteção separada para dispositivos gerenciados MDM, em que os controles de DLP podem ser um pouco mais flexíveis. Para saber mais sobre como isso funciona em dispositivos Android Enterprise pessoais, confira o tópico [Políticas de proteção de aplicativo e perfis de trabalho](android-deployment-scenarios-app-protection-work-profiles.md).

Para criar essas políticas, navegue até **Aplicativos clientes** > **Políticas de proteção de aplicativo** no console do Intune e, em seguida, selecione **Criar Política**. Você também pode editar uma política de proteção do aplicativo existente. Para que a política de proteção de aplicativo seja aplicada a dispositivos gerenciados e não gerenciados, navegue até a página **Aplicativos** e confirme se **Direcionar para aplicativos em todos os tipos de dispositivo** está definido como **Sim**, o valor padrão. Se você desejar atribuir de maneira granular com base no estado de gerenciamento, defina **Direcionar para aplicativos em todos os tipos de dispositivo** como **Não**. 

![Captura de tela da folha Adicionar uma política com Direcionar a todos os tipos de aplicativo](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Tipos de aplicativo

- **Aplicativos em dispositivos não gerenciados**: os dispositivos não gerenciados são aqueles em que o gerenciamento de MDM do Intune não foi detectado. Isso inclui fornecedores de MDM de terceiros.
- **Aplicativos em dispositivos gerenciados do Intune**: os dispositivos são gerenciados pelo MDM do Intune.
- **Aplicativos do Perfil de trabalho Android**: Dispositivos gerenciados que foram registrados como dispositivos de perfil de trabalho do Android Enterprise.

> Os dispositivos Android solicitarão a instalação do aplicativo Portal da Empresa do Intune, independentemente do tipo de aplicativo escolhido. Por exemplo, se você escolher "Aplicativos em dispositivos gerenciados do Intune", os usuários com dispositivos Android não gerenciados ainda serão solicitados.

Para iOS, são necessárias mais definições de configuração de aplicativo a fim de direcionar as configurações da política de proteção do aplicativo para aplicativos, em dispositivos registrados no Microsoft Intune:

- **IntuneMAMUPN** deve ser configurado para todos os aplicativos gerenciados por MDM. Para obter mais informações, confira [Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **IntuneMAMDeviceID** deve ser configurado para todos os aplicativos de terceiros e gerenciados por MDM LOB. O **IntuneMAMDeviceID** deve ser configurado para o token de ID do dispositivo. Por exemplo, `key=IntuneMAMDeviceID, value={{deviceID}}`. Para obter mais informações, confira [Adicionar políticas de configuração de aplicativo para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md).
- Se apenas **IntuneMAMDeviceID** estiver configurado, o aplicativo do Intune considerará que o dispositivo como não gerenciado.

> [!NOTE]
> Para obter informações de suporte do iOS específicas sobre políticas de proteção do aplicativo com base no estado de gerenciamento de dispositivo, consulte [Políticas de proteção MAM direcionadas com base no estado de gerenciamento](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Configurações de política
Para ver uma lista completa das configurações de política para iOS e Android, selecione um dos seguintes links:

- [Políticas do iOS](app-protection-policy-settings-ios.md)
- [Políticas do Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Próximas etapas
[Monitorar conformidade e status do usuário](app-protection-policies-monitor.md)

## <a name="see-also"></a>Consulte também
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-ios.md)
