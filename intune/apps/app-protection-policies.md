---
title: Criar e implantar políticas de proteção do aplicativo
titleSuffix: Microsoft Intune
description: Este tópico descreve como criar e atribuir as políticas de proteção de aplicativo (APP) do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4958a35f3a83fecffacf26421e4c1d797f45ddaa
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940387"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Como criar e atribuir as políticas de proteção de aplicativo

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Saiba como criar e atribuir as políticas de proteção de aplicativo do Microsoft Intune aos usuários. Este tópico também descreve como fazer alterações nas políticas existentes.

## <a name="before-you-begin"></a>Antes de começar

Políticas de proteção de aplicativo podem se aplicar a aplicativos em execução em dispositivos que podem ou não ser gerenciados pelo Intune. Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários compatíveis com as políticas de Proteção de Aplicativo do Intune, confira [O que são as políticas de Proteção de Aplicativo do Microsoft Intune?](app-protection-policy.md)

Se você estiver procurando uma lista de aplicativos com suporte no MAM, consulte [Lista de aplicativos do MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Para saber mais sobre como adicionar os aplicativos de linha de negócios (LOB) da sua organização ao Microsoft Intune para se preparar para as políticas de proteção de aplicativos, confira [ Adicionar aplicativos ao Microsoft Intune](apps-add.md).

## <a name="create-an-app-protection-policy"></a>Criar uma política de proteção de aplicativo
1. No portal do Intune, acesse **Aplicativos de cliente** > **Políticas de proteção de aplicativo**. Essa seleção abre os detalhes das **Políticas de proteção do aplicativo**, em que você cria novas políticas e edita políticas existentes.
2. Selecione **Criar Política**.

   ![Captura de tela da folha "Adicionar uma política"](./media/app-protection-policies/app-protection-add-policy.png)

3. Especifique um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para a política. Você pode criar mais de uma política para cada plataforma.

4. Selecione **Aplicativos** para abrir a folha **Aplicativos**, em que uma lista de aplicativos disponíveis é exibida. Selecione um ou mais aplicativos da lista que deseja associar com a política que você está criando. Selecione pelo menos um aplicativo para criar uma política.  

5. Depois de selecionar os aplicativos, escolha **Selecionar** para salvar a seleção.

6. Na folha **Adicionar uma política**, selecione **Definir configurações necessárias** para abrir **Configurações**.

   Há três categorias de configurações de política:
   - **Proteção de dados**: esse grupo inclui os controles de DLP (prevenção de perda dados), como restrições de cortar, copiar, colar e salvar como. Essas configurações determinam como os usuários interagem com os dados nos aplicativos.
   - **Requisitos de acesso** – esse grupo contém as opções de PIN por aplicativo que determinam como o usuário final acessa os aplicativos em um contexto de trabalho.  
   - **Inicialização condicional** – esse grupo contém configurações como configurações de sistema operacional mínimo, jailbreak e detecção de dispositivos com raiz e períodos de cortesia offline.

   As configurações de política têm valores padrão para que você possa começar mais facilmente. Se os valores padrão atendem aos seus requisitos, não é necessário fazer alterações.

   > [!TIP]
   > Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo. Quando os usuários finais usam o aplicativo para executar uma tarefa pessoal, eles não são afetados por essas políticas. Observe que, quando você cria um novo arquivo, ele é considerado um arquivo particular. 

7. Selecione **OK** para salvar essa configuração. Agora você retornou à folha **Adicionar uma política**.
8. Selecione **Criar** para criar a política e salvar suas configurações.

Novas políticas criadas não são implantadas para todos os usuários até que você explicitamente faça isso. Para implantar uma política, consulte [Implantar uma política para usuários](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Implantar uma política para os usuários

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

## <a name="change-existing-policies"></a>Alterar políticas existentes
Você pode editar uma política existente e aplicá-la aos usuários de destino. No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de oito horas.

Para ver o efeito das alterações imediatamente, o usuário final deve sair do aplicativo e entrar novamente.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Para alterar a lista de aplicativos associados à política

1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Aplicativos de destino** para abrir a lista de aplicativos.

3. Remova ou adicione aplicativos da lista e selecione o ícone **Salvar** para salvar suas alterações.

### <a name="to-change-the-list-of-user-groups"></a>Para alterar a lista de grupos de usuários


1. No painel **Políticas de proteção de aplicativo**, selecione a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Atribuições** para abrir o painel **Proteção de Aplicativo do Intune – Atribuições**, que mostra a lista atual de grupos de usuários que têm essa política.

3. Para adicionar um novo grupo de usuários à política, na guia *Incluir*, escolha **Selecionar grupos para incluir** e selecione o grupo de usuários. Escolha **Selecionar** para adicionar o grupo. 

4. Para excluir um grupo de usuários, na guia *Excluir* escolha **Selecionar grupos para excluir** e selecione o grupo de usuários. Escolha **Selecione** para remover o grupo de usuários.  

5. Para excluir os grupos que foram adicionados anteriormente, nas guias *Incluir* ou *Excluir*, selecione as reticências (...) e **Excluir**. 

5. Após terminar as alterações às atribuições, selecione **Salvar** para guardar a configuração e implantar a política para o novo conjunto de usuários. Se você selecionar **Descartar** antes de salvar sua configuração, descartará todas as alterações feitas nas guias *Incluir* e *Excluir*.

### <a name="to-change-policy-settings"></a>Para alterar as configurações de política

1. No painel **Políticas de proteção de aplicativo**, escolha a política que você deseja alterar.

2. No painel *Proteção de Aplicativo do Intune*, selecione **Propriedades** para abrir a lista de áreas de configurações que você pode editar. 

3. Selecione a área de configurações com as configurações que você deseja alterar, como **Realocação de dados** ou **Requisitos de acesso**. Em seguida, altere as configurações para novos valores.

4. Selecione o ícone **Salvar** para salvar suas alterações. Repita o processo para selecionar uma área de configurações e modificar e então salvar suas alterações até que todas as suas alterações tenham sido concluídas. Em seguida, você pode fechar o painel *Proteção de Aplicativo do Intune – Propriedades*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo
Em muitas organizações é comum permitir que os usuários finais usem dispositivos gerenciados MDM (gerenciamento de dispositivo móvel) do Intune, como dispositivos corporativos, bem como dispositivos não gerenciados protegidos apenas com políticas de Proteção de Aplicativo do Intune. Dispositivos não gerenciados são geralmente conhecidos como BYOD (traga seu próprio dispositivos).

Uma vez que as políticas de Proteção de Aplicativo do Intune são direcionadas para a identidade de um usuário, as configurações de proteção para um usuário podem se aplicar tanto a dispositivos registrados (gerenciados por MDM) quanto não registrados (sem MDM). Portanto, você pode ter como destino uma política de Proteção de Aplicativo do Intune para dispositivos Android e iOS registrados ou não registrados no Intune. Você pode ter uma política de proteção para dispositivos não gerenciados, na qual controles de DLP (prevenção contra perda de dados) estritos estejam em vigor, e uma política de proteção separada para dispositivos gerenciados MDM, em que os controles de DLP podem ser um pouco mais flexíveis. Para saber mais sobre como isso funciona em dispositivos Android Enteprise pessoais, confira o tópico [Políticas de proteção de aplicativo e perfis de trabalho](android-deployment-scenarios-app-protection-work-profiles.md).

Para criar essas políticas, navegue até **Aplicativos clientes** > **Políticas de proteção de aplicativo** no console do Intune e, em seguida, selecione **Criar Política**. Você também pode editar uma política de proteção do aplicativo existente. Para a política de proteção do aplicativo se aplicar tanto a dispositivos gerenciados quanto não gerenciados, confirme que o **Destino para todos os tipos de aplicativo** está definido como **Sim**, o valor padrão. Se você quiser atribuir de maneira granular com base no estado de gerenciamento, defina **Destino para todos os tipos de aplicativo** como **Não**. 

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