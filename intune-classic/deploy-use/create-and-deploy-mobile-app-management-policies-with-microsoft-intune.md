---
title: Criar e implantar políticas de MAM
description: Use as instruções passo a passo neste tópico para criar e implantar políticas de gerenciamento de aplicativos móveis.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cc133071f4d6c0d1a3bbb3acc7c0bd5cb45b6cef
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a>Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Esse tópico descreve o processo de criação de uma política de proteção de aplicativo no **Portal do Azure**. O portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo e é recomendável que você use este portal para criá-las. O portal do Azure dá suporte aos seguintes cenários MAM:

- Dispositivos registrados no Intune.
- Dispositivos gerenciados por uma solução de MDM terceirizada.
- Dispositivos que não são gerenciados por uma solução MDM (BYOD).

> [!IMPORTANT]
> Aqui estão algumas considerações caso você esteja usando o **console de administração do Intune** para gerenciar seus dispositivos:
> 
> * você pode criar uma política de proteção de aplicativo que dá suporte a aplicativos para dispositivos registrados no Intune usando o [console de administração do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
> * As políticas de proteção de aplicativo criadas no console de administração do Intune não podem ser importadas no portal do Azure.  As políticas de proteção de aplicativo devem ser recriadas no Portal do Azure.
> 
> * Você não poderá ver todas as configurações de política de proteção de aplicativo no console de administração do Intune. O portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo.
> 
> * Para implantar aplicativos gerenciados, você precisa criar uma política de proteção de aplicativo no console de administração do Intune. Nesse caso, talvez você queira criar política de proteção de aplicativo no console de administração do Intune e no portal do Azure: no console de administração do Intune para poder implantar aplicativos gerenciados e no portal do Azure porque ele é o novo console de administração que tem todas as configurações de política de proteção de aplicativo.
> 
> * Se você criar políticas de proteção de aplicativo no console de administração do Intune e no portal do Azure, a política criada no portal do Azure será aplicada aos aplicativos.

Para ver uma lista de configurações de política com suporte para as plataformas Android e iOS, selecione um dos seguintes:

> [!div class="op_single_selector"]
> - [Políticas do iOS](ios-mam-policy-settings.md)
> - [Políticas do Android](android-mam-policy-settings.md)

- Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários com suporte nas políticas de proteção de aplicativo do Intune, consulte [proteger dados de aplicativo usando as políticas de proteção de aplicativo](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

##  <a name="create-an-app-protection-policy"></a>Criar uma política de proteção de aplicativo
As políticas de proteção de aplicativo são criadas no Portal do Azure. Se esta é a primeira vez que você está usando o Portal do Azure, leia [Portal do Azure para políticas de proteção de aplicativo do Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) para se familiarizar com o Portal do Azure. Antes de criar uma política de proteção de aplicativo, examine as informações de [pré-requisitos e suporte](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

Siga as etapas abaixo para criar as políticas de proteção de aplicativo:

1. Acesse o [Portal do Azure](https://portal.azure.com) e insira suas credenciais.

2. Escolha **Mais Serviços** e digite "Intune".

3. Escolha **Proteção de Aplicativo do Intune**.

4. Escolha **Gerenciamento de aplicativos móveis do Intune &gt; Configurações** para abrir a folha **Todas as Configurações**.

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  Na folha **Todas as configurações**, escolha **Política de aplicativos**. Isso abre a folha **Política de aplicativo**, em que você criará novas políticas e editará as políticas existentes. Escolha **Adicionar uma política**.

    ![Captura de tela da folha Política de aplicativos com a opção de menu Adicionar uma política realçada ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  Digite um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para criar uma política para iOS ou Android. Você pode criar mais de uma política para cada plataforma.

    ![Captura de tela da folha Adicionar uma política](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Escolha **Aplicativos** para abrir a **folha Aplicativos**, em que uma lista de aplicativos disponíveis é exibida. Selecione um ou mais aplicativos da lista que deseja associar à política que está sendo criada. Depois de selecionar os aplicativos, escolha **Selecionar** na parte inferior da folha **Aplicativos** para salvar sua seleção.

    > [!IMPORTANT]
    > Você deve selecionar pelo menos um aplicativo para criar uma política.

5.  Na folha **Adicionar uma política**, escolha **Definir as configurações necessárias** para abrir a folha de configurações da política.

    Há duas categorias de configurações de política, **Realocação dos dados** e **Acesso**.  Políticas de realocação de dados aplicam-se à movimentação de dados dentro e fora dos aplicativos, enquanto as políticas de acesso determinam como o usuário final acessa os aplicativos em um contexto de trabalho.
    As configurações de política têm valores padrão para que você possa começar mais facilmente. Não é necessário fazer alterações se os valores padrão atendem às suas necessidades.

    > [!TIP]
    > Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo.  Quando o usuário final usa o aplicativo para executar uma tarefa pessoal, ele não é afetado por essas políticas.

    ![Captura de tela da folha de configurações, juntamente com a folha Adicionar uma política](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  Escolha **OK** para salvar esta configuração. Agora você retornou à folha **Adicionar uma política** . Escolha **Criar** para criar a política e salvar suas configurações.

    ![Captura de tela da folha Adicionar uma política mostrando que aplicativos e configurações foram definidos](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

Ao terminar de criar uma política conforme descrito no procedimento anterior, ela não é implantada para nenhum usuários. Para implantar uma política, consulte a seção a seguir, "Implantar uma política para usuários".

> [!IMPORTANT]
> Se você criar uma política de proteção de aplicativo para um aplicativo usando o console de administração do Intune e uma política de proteção de aplicativo usando o portal do Azure, a política criada usando o portal do Azure terá precedência. No entanto, o relatório no console do Intune ou do Configuration Manager relatará as configurações de política criadas no console de administração do Intune. Por exemplo:
>
> -   Você criou uma política de proteção de aplicativo no console de administração do Intune que bloqueia a cópia de um aplicativo.
> -   Você criou uma política de proteção de aplicativo no console do Azure que permite a cópia em um aplicativo.
> -   Você associa essas duas políticas ao mesmo aplicativo.
> -   A política criada no console do Azure tem precedência e a cópia é permitida.
> -   No entanto, status e relatórios no console do Intune indicarão incorretamente que a cópia está bloqueada.

## <a name="line-of-business-lob-apps-optional"></a>Aplicativos de linha de negócios (LOB) (opcionais)

Começando com a versão do Intune 1703, você tem a opção de adicionar de modo geral aplicativos LOB no Intune ao criar uma nova política de proteção de aplicativos. Isso lhe dá a opção de definir políticas de proteção de aplicativos para aplicativos LOB usando o SDK do MAM sem a necessidade de permissões totais de implantação do aplicativo.
/intune/app-sdk-get-started
> [!TIP]
> Você também pode adicionar aplicativos LOB no Intune percorrendo o fluxo de trabalho do [Intune App SDK](/intune/app-sdk-get-started).

> [!IMPORTANT]
> Se os usuários tiverem apenas permissões específicas para implantar aplicativos MAM e não permissões totais de implantação de aplicativos, o que lhes permitiria implantar qualquer aplicativo no Intune, eles não conseguirão percorrer o fluxo de trabalho Intune SDK, mas ainda poderão adicionar seus aplicativos LOB por meio do fluxo de trabalho de criação de política de proteção de aplicativos MAM.

### <a name="to-add-lob-apps-ios-and-android"></a>Para adicionar aplicativos LOB (iOS e Android)

1.  Na caixa Adicionar uma folha de política, selecione Configurar **aplicativos** para abrir a folha de aplicativos.

    ![MAM Adicionar uma folha de política](../media/AppManagement/mam-lob-apps-1.png)

2.  Clique em **Mais aplicativos**, em seguida, digite a **ID do pacote** (para iOS), **ID do pacote** (para Android), clique em Selecionar para adicionar seus aplicativos LOB.

    ![MAM Folha de mais aplicativos](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a>Para adicionar aplicativos LOB (Windows)

> [!IMPORTANT]
> Você precisa selecionar o Windows 10 na lista suspensa da plataforma ao criar uma nova política de proteção de aplicativos.

1. Na caixa Adicionar uma folha de política, selecione **Aplicativos permitidos** ou **Aplicativos isentos** para abrir a folha de aplicativos permitidos ou isentos.

   > [!NOTE]
   > 
   > - **Aplicativos permitidos**: Estes são os aplicativos que precisam atender a esta política.
   > - **Aplicativos isentos**: Estes aplicativos são isentos desta política e podem acessar dados corporativos sem restrições.
   > <br></br>
2. Na folha de aplicativos permitidos ou isentos, clique em **Adicionar aplicativos**. Você pode adicionar aplicativos recomendados pela Microsoft, adicionar aplicativos da área de trabalho ou da loja.

    a.  **Aplicativos recomendados:** uma lista pré-populada de aplicativos (principalmente do Office) que deixamos os administradores importar facilmente para a política.

    b.  **Aplicativos da loja:** O administrador pode adicionar qualquer aplicativo da Windows Store à política.

    c.  **Aplicativos da área de trabalho do Windows:** O administrador pode adicionar qualquer aplicativo tradicional de área de trabalho do Windows à política (por exemplo, exe, dll, etc.)

## <a name="deploy-a-policy-to-users"></a>Implantar uma política para os usuários

1.  Na folha **Política**, escolha **Grupos de usuários**, o que abre a folha **Grupos de usuários**. Escolha **Adicionar grupo de usuários** na folha **Grupos de usuários** para abrir a folha **Adicionar grupo de usuários**.

    ![Captura de tela da folha Grupos de usuários com a opção de menu Adicionar grupo de usuários realçada](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  Uma lista de grupos de usuários é exibida na folha **Adicionar grupo de usuários** . Esta é uma lista de todos os grupos de segurança no seu **Active Directory do Azure**. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Selecionar**. A escolha de **Selecionar** implanta a política para os usuários.

    ![Captura de tela da folha Adicionar grupo de usuários adicionar mostrando a lista de usuários do Azure Active Directory](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    Agora você criou uma política e a implantou para os usuários.

Somente usuários com licenças do Intune atribuídas serão afetados pela política. Os usuários que estão no grupo de segurança que você selecionou e que não têm uma licença do Intune atribuída não serão afetados.

>[!IMPORTANT]
> Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos Android e iOS, a política só será aplicada aos usuários diretamente no grupo que você selecionou. Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.

Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play. Para obter mais informações, consulte:
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](/intune/end-user-mam-apps-android)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a>Alterar políticas existentes
Você pode editar uma política existente e aplicá-la aos usuários de destino. No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de 8 horas.

Para ver o efeito das alterações imediatamente, o usuário final precisará sair do aplicativo e entrar novamente.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Para alterar a lista de aplicativos associados à política

1.  Na folha **Política de aplicativos**, escolha a política que quer alterar. Isso abrirá uma folha específica para a política que você selecionou.

    ![Captura de tela de uma política existente aberta em uma folha separada](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Na folha de política, escolha **Aplicativos de destino** para abrir a lista de aplicativos.

3.  Remova ou adicione aplicativos da lista e escolha o ícone **Salvar** para salvar suas alterações.

### <a name="to-change-the-list-of-user-groups"></a>Para alterar a lista de grupos de usuários

1.  Na folha **Política de aplicativos**, escolha a política que quer alterar. Isso abrirá a folha específica para a política selecionada.

2.  Na folha da política, escolha **Grupos de usuários** para abrir a folha **Grupo de usuários** que mostra a lista atual de grupos de usuários que têm essa política.

3.  Para adicionar um novo grupo de usuários à política, escolha **Adicionar grupo de usuários** e selecione o grupo de usuários. Escolha **Selecionar** para implantar a política no grupo selecionado.

    ![Captura de tela da folha Adicionar grupo de usuários, com dois grupos de usuários selecionados](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Para excluir um grupo de usuários, realce o grupo de usuários que deseja remover. Em seguida, selecione as reticências (...) e escolha **Excluir** para remover o grupo de usuários.

    ![Captura de tela mostrando a opção Excluir ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>Para alterar as configurações de política

1.  Na folha **Política de aplicativos**, escolha a política que quer alterar. Isso abrirá uma folha específica para a política que você selecionou.

    ![Captura de tela de uma política existente aberta em uma folha separada ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Escolha **Configurações de política** para abrir a folha **Configurações de política**.

3.  Altere as configurações e escolha o ícone **Salvar** para salvar suas alterações.

    ![Captura de tela da folha Configurações de política mostrando a opção de menu Salvar na parte superior](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>Configurações de política
Para ver uma lista completa de configurações de política para iOS e Android, selecione um dos seguintes:

> [!div class="op_single_selector"]
> - [Políticas do iOS](ios-mam-policy-settings.md)
> - [Políticas do Android](android-mam-policy-settings.md)

## <a name="next-steps"></a>Próximas etapas
[Monitorar conformidade e status do usuário](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Consulte também
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](/intune/end-user-mam-apps-android)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](/intune/end-user-mam-apps-ios)
