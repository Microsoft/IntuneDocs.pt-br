---
title: "Criar e implantar políticas de proteção do aplicativo"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como políticas de proteção de aplicativo do Intune podem ajudar a proteger os dados corporativos usados por aplicativos gerenciados."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 607598812a414843f1f33a00670a6a85b6687878
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-create-and-assign-app-protection-policies"></a>Como criar e atribuir as políticas de proteção de aplicativo

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Se você não estiver no serviço do Intune no programa de versão prévia do Portal do Azure**, este tópico explicará [como criar políticas de proteção de aplicativo](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) no console do Intune clássico.

Políticas de proteção de aplicativo podem ser aplicadas a aplicativos em execução em dispositivos que podem ou não ser gerenciados pelo Intune. Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários com suporte nas políticas de proteção de aplicativo do Intune, consulte [O que são as políticas de proteção de aplicativo do Microsoft Intune](what-is-app-protection-policy.md).

##  <a name="create-an-app-protection-policy"></a>Criar uma política de proteção de aplicativo
1.  Na carga de trabalho **Gerenciar aplicativos**, escolha **Gerenciar** > **Políticas de proteção de aplicativos**.

2.  Isso abre a folha **Políticas de proteção de aplicativo**, em que você criará novas políticas e editará as políticas existentes. Escolha **Adicionar uma política**.

  ![Captura de tela da folha Adicionar uma política](../media/app-protection-add-policy.png)

3.  Digite um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para criar uma política para iOS ou Android. Você pode criar mais de uma política para cada plataforma.

4.  Escolha **Aplicativos** para abrir a **folha Aplicativos**, em que uma lista de aplicativos disponíveis é exibida. Selecione um ou mais aplicativos da lista que deseja associar à política que está sendo criada. Depois de selecionar os aplicativos, escolha **Selecionar** na parte inferior da folha **Aplicativos** para salvar sua seleção.

    > [!IMPORTANT]
    > Você deve selecionar pelo menos um aplicativo para criar uma política.

5.  Na folha **Adicionar uma política**, escolha **Definir as configurações necessárias** para abrir a folha de configurações da política.

    Há duas categorias de configurações de política, **Realocação dos dados** e **Acesso**.  Políticas de realocação de dados aplicam-se à movimentação de dados dentro e fora dos aplicativos, enquanto as políticas de acesso determinam como o usuário final acessa os aplicativos em um contexto de trabalho.
    As configurações de política têm valores padrão para que você possa começar mais facilmente. Não é necessário fazer alterações se os valores padrão atendem às suas necessidades.

    > [!TIP]
    > Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo.  Quando o usuário final usa o aplicativo para executar uma tarefa pessoal, ele não é afetado por essas políticas.



6.  Escolha **OK** para salvar esta configuração. Agora você retornou à folha **Adicionar uma política** . Escolha **Criar** para criar a política e salvar suas configurações.


Ao terminar de criar uma política conforme descrito no procedimento anterior, ela não é implantada para nenhum usuários. Para implantar uma política, consulte a seção a seguir, "Implantar uma política para usuários".

## <a name="deploy-a-policy-to-users"></a>Implantar uma política para os usuários

1.  Na folha **Política**, escolha **Grupos de usuários**, o que abre a folha **Grupos de usuários**. Escolha **Adicionar grupo de usuários** na folha **Grupos de usuários** para abrir a folha **Adicionar grupo de usuários**.

  ![Captura de tela da folha Grupos de usuários com a opção de menu Adicionar grupo de usuários realçada](../media/app-protection-policy-add-users.png)

2.  Uma lista de grupos de usuários é exibida na folha **Adicionar grupo de usuários** . Esta é uma lista de todos os grupos de segurança no seu **Active Directory do Azure**. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Selecionar**. A escolha de **Selecionar** implanta a política para os usuários.
  ![Captura de tela da folha Adicionar grupo de usuários adicionar mostrando a lista de usuários do Azure Active Directory](../media/azure-ad-user-group-list.png)

Agora você criou uma política e a implantou para os usuários.

Somente usuários com licenças do Microsoft Intune atribuídas a eles serão afetados pela política. Os usuários que estão no grupo de segurança que você selecionou e que não têm uma licença do Microsoft Intune atribuída a eles não serão afetados.

>[!IMPORTANT]
> Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos Android e iOS, a política só será aplicada aos usuários diretamente no grupo que você selecionou. Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.

Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play. Para obter mais informações, consulte:
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-android-apps.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-ios-apps.md)

##  <a name="change-existing-policies"></a>Alterar políticas existentes
Você pode editar uma política existente e aplicá-la aos usuários de destino. No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de 8 horas.

Para ver o efeito das alterações imediatamente, o usuário final precisará sair do aplicativo e entrar novamente.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Para alterar a lista de aplicativos associados à política

1.  Na folha **Política de aplicativos**, escolha a política que quer alterar. Isso abrirá uma folha específica para a política que você selecionou.

2.  Na folha de política, escolha **Aplicativos de destino** para abrir a lista de aplicativos.

3.  Remova ou adicione aplicativos da lista e escolha o ícone **Salvar** para salvar suas alterações.

### <a name="to-change-the-list-of-user-groups"></a>Para alterar a lista de grupos de usuários

1.  Na folha **Política de aplicativos**, escolha a política que quer alterar. Isso abrirá a folha específica para a política selecionada.

2.  Na folha da política, escolha **Grupos de usuários** para abrir a folha **Grupo de usuários** que mostra a lista atual de grupos de usuários que têm essa política.

3.  Para adicionar um novo grupo de usuários à política, escolha **Adicionar grupo de usuários** e selecione o grupo de usuários. Escolha **Selecionar** para implantar a política no grupo selecionado.

4.  Para excluir um grupo de usuários, realce o grupo de usuários que deseja remover. Em seguida, selecione as reticências (...) e escolha **Excluir** para remover o grupo de usuários.
  ![Captura de tela mostrando a opção Excluir ](../media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>Para alterar as configurações de política

1.  Na folha **Política de aplicativos**, escolha a política que quer alterar. Isso abrirá uma folha específica para a política que você selecionou.


2.  Escolha **Configurações de política** para abrir a folha **Configurações de política**.

3.  Altere as configurações e escolha o ícone **Salvar** para salvar suas alterações.

## <a name="policy-settings"></a>Configurações de política
Para ver uma lista completa de configurações de política para iOS e Android, selecione um dos seguintes:

> [!div class="op_single_selector"]
- [Políticas do iOS](ios-app-protection-policy-settings.md)
- [Políticas do Android](android-app-protection-policy-settings.md)

## <a name="next-steps"></a>Próximas etapas
[Monitorar conformidade e status do usuário](monitor-app-protection-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Consulte também
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-android-apps.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-ios-apps.md)

