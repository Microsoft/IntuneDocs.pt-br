---
title: Criar e implantar políticas de proteção do aplicativo
titleSuffix: Microsoft Intune
description: Saiba como criar e atribuir as políticas de proteção de aplicativo do Microsoft Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 606c173c1723d526436b9ae75d9a4085883f071b
ms.sourcegitcommit: 29eaf27323763a5a200ec64b8679397c4b988f33
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305426"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Como criar e atribuir as políticas de proteção de aplicativo

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Saiba como criar e atribuir as políticas de proteção de aplicativo do Microsoft Intune aos usuários. Este tópico também descreve como fazer alterações nas políticas existentes.

## <a name="before-you-begin"></a>Antes de começar

Se você estiver procurando instruções no Portal Clássico do Intune, veja [Como criar políticas de proteção de aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

Políticas de proteção de aplicativo podem ser aplicadas a aplicativos em execução em dispositivos que podem ou não ser gerenciados pelo Intune. Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários com suporte nas políticas de proteção de aplicativo do Intune, consulte [O que são as políticas de proteção de aplicativo do Microsoft Intune](app-protection-policy.md).

Se você estiver procurando uma lista de aplicativos com suporte no MAM, consulte [Lista de aplicativos do MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  <a name="create-an-app-protection-policy"></a>Criar uma política de proteção de aplicativo
1. Na carga de trabalho **Aplicativos móveis**, selecione **Políticas de proteção do aplicativo** na seção **Gerenciar**. Essa seleção abre os detalhes das **Políticas de proteção do aplicativo**, em que você cria novas políticas e edita políticas existentes.
2. Escolha **Adicionar uma política**.

   ![Captura de tela da folha "Adicionar uma política"](./media/app-protection-add-policy.png)

3. Digite um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para a política. Se necessário, você pode criar mais de uma política para cada plataforma.

4. Escolha **Aplicativos** para abrir a folha **Aplicativos**, em que uma lista de aplicativos disponíveis é exibida. Selecione um ou mais aplicativos da lista que deseja associar com a política que você está criando.
5. Depois de selecionar os aplicativos, escolha **Selecionar** para salvar a seleção.

    > [!IMPORTANT]
    > Você deve selecionar pelo menos um aplicativo para criar uma política.

6. Escolha **Definir configurações necessárias** na folha **Adicionar uma política** para abrir **Configurações**.

   Há duas categorias de configurações de política, **Realocação dos dados** e **Acesso**.  As políticas de realocação de dados se aplicam à movimentação de dados dentro e fora dos aplicativos. As políticas de acesso determinam como o usuário final acessa os aplicativos em um contexto de trabalho.
   As configurações de política têm valores padrão para que você possa começar mais facilmente. Se os valores padrão atendem aos seus requisitos, não é necessário fazer alterações.

   > [!TIP]
   > Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo. Quando os usuários finais usam o aplicativo para executar uma tarefa pessoal, eles não são afetados por essas políticas.

7. Escolha **OK** para salvar esta configuração. Agora você retornou ao painel **Adicionar uma política**. Escolha **Criar** para criar a política e salvar suas configurações.
8. Escolha **OK** para salvar esta configuração. Agora você retornou à folha **Adicionar uma política**.
9. Escolha **Criar** para criar a política e salvar suas configurações.

Ao terminar de criar uma política conforme descrito no procedimento anterior, ela não é implantada para nenhum usuários. Para implantar uma política, consulte [Implantar uma política para usuários](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Implantar uma política para os usuários


1. No painel **Políticas de proteção do aplicativo**, selecione uma política.

1. No painel **Política**, escolha **Atribuições**, que abre o painel **Proteção de Aplicativo do Intune – Atribuições**. Escolha **Selecionar grupos para incluir** no painel **Atribuições** para abrir o painel **Selecionar grupos para incluir**.

   ![Captura de tela do painel Atribuições com a opção de menu Selecionar grupos para incluir realçada](./media/app-protection-policy-add-users.png)

2.  Uma lista de grupos de usuários é exibida no painel **Adicionar grupo de usuários**. Esta lista mostra todos os grupos de segurança no seu **Azure Active Directory**. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Selecionar**. A escolha de **Selecionar** implanta a política para os usuários.

    ![Captura de tela do painel Adicionar grupo de usuários mostrando a lista de usuários do Azure Active Directory](./media/azure-ad-user-group-list.png)

Agora você criou uma política e a implantou para os usuários.

Somente usuários atribuídos com licenças do Microsoft Intune serão afetados pela política. Os usuários do grupo de segurança selecionado, que não têm uma licença do Intune atribuída, não serão afetados.

>[!IMPORTANT]
> Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos, a política só será aplicada aos usuários diretamente no grupo que você selecionou. Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.

Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play. Para obter mais informações, consulte:
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Alterar políticas existentes
Você pode editar uma política existente e aplicá-la aos usuários de destino. No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de 8 horas.

Para ver o efeito das alterações imediatamente, o usuário final deve sair do aplicativo e entrar novamente.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Para alterar a lista de aplicativos associados à política

1.  No painel **Políticas de proteção do aplicativo**, escolha a política que você deseja alterar para abrir um painel específico da política selecionada.

2.  No painel da política, escolha **Aplicativos direcionados** para abrir a lista de aplicativos.

3.  Remova ou adicione aplicativos da lista e escolha o ícone **Salvar** para salvar suas alterações.

### <a name="to-change-the-list-of-user-groups"></a>Para alterar a lista de grupos de usuários


1.  No painel **Políticas de proteção do aplicativo**, escolha a política que você deseja alterar para abrir o painel específico da política selecionada.

2.  No painel da política, escolha **Atribuições** para abrir o painel **Proteção de Aplicativo do Intune – Atribuições**, que mostra a lista atual de grupos de usuários que têm essa política.

3.  Para adicionar um novo grupo de usuários à política, na guia **Incluir**, escolha **Selecionar grupos para incluir** e selecione o grupo de usuários. Escolha **Selecionar** para implantar a política no grupo selecionado.

4.  Para excluir um grupo de usuários, na guia **Excluir** escolha **Selecionar grupos para excluir** e selecione o grupo de usuários. Escolha **Selecione** para remover o grupo de usuários.

### <a name="to-change-policy-settings"></a>Para alterar as configurações de política

1.  No painel **Políticas de proteção do aplicativo**, escolha a política que você deseja alterar para abrir um painel específico da política selecionada.

2.  Escolha **Configurações de política** para abrir o painel **Configurações de política**.

3.  Altere as configurações e escolha o ícone **Salvar** para salvar suas alterações.

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo
Em muitas organizações é comum permitir que os usuários finais usem dispositivos gerenciados MDM (gerenciamento de dispositivo móvel) do Intune, como dispositivos corporativos, e dispositivos não gerenciados protegidos apenas com políticas de Proteção de Aplicativo do Intune, como os dispositivos BYO.

Uma vez que as políticas de Proteção de Aplicativo do Intune são direcionadas para a identidade de um usuário, as configurações de proteção para um usuário tradicionalmente se aplicam a dispositivos registrados (gerenciados por MDM) e não registrados (sem MDM). Portanto, você pode ter como destino uma política de Proteção de Aplicativo do Intune para dispositivos Android e iOS registrados ou não registrados no Intune. Você pode ter uma política de proteção para dispositivos não gerenciados na qual controles DLP (prevenção contra perda de dados) rígidos estejam em vigor e uma política de proteção separada para dispositivos gerenciados MDM, em que os controles DLP podem ser um pouco mais flexíveis. 

Para criar essas políticas, navegue até as políticas de **Aplicativos móveis** > **Proteção do aplicativo** no console do Intune e clique **Adicionar uma política**. Você também pode editar uma política de proteção do aplicativo existente. Se desejar que a política de proteção do aplicativo se aplique tanto a dispositivos gerenciados quanto não gerenciados, confirme que o **Destino para todos os tipos de aplicativo** esteja definido como **Sim**, o valor padrão. Se você quiser atribuir de maneira granular com base no estado de gerenciamento, defina a opção **Destino para todos os tipos de aplicativo** como **Não**. 

Para que os aplicativos iOS sejam considerados "Gerenciados", a configuração da política de configuração de **IntuneMAMUPN** precisa ser implantada em cada aplicativo. Para obter mais informações, confira [Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune](https://docs.microsoft.com/en-us/intune/data-transfer-between-apps-manage-ios#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).

> [!NOTE]
> Para obter informações de suporte do iOS específicas sobre políticas de proteção do aplicativo com base no estado de gerenciamento de dispositivo, consulte [Políticas de proteção MAM direcionadas com base no estado de gerenciamento](whats-new.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Configurações de política
Para ver uma lista completa das configurações de política para iOS e Android, selecione um dos seguintes links:

- [Políticas do iOS](app-protection-policy-settings-ios.md)
- [Políticas do Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Próximas etapas
[Monitorar conformidade e status do usuário](app-protection-policies-monitor.md)

### <a name="see-also"></a>Consulte também
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)
