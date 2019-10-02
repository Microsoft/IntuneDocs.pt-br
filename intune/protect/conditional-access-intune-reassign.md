---
title: Migrar o Acesso Condicional para o portal do Azure
titleSuffix: Microsoft Intune
description: Reatribua as políticas de Acesso Condicional criadas anteriormente no Portal Clássico do Intune para o portal do Azure.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a369abd2f3873d970e9efc1ebf3ea814a9295fec
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722677"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Reatribuir políticas de Acesso Condicional no portal clássico do Intune para o portal do Azure

A partir do novo portal do Azure, o Acesso Condicional dará suporte para várias políticas por aplicativo juntamente com maior capacidade de personalização. Se já tiver criado anteriormente as políticas de Acesso Condicional no Portal Clássico do Intune, você poderá migrá-las para o portal do Azure. 

## <a name="before-you-begin"></a>Antes de começar

Se você estiver pronto para mudar para o portal do Azure, siga as etapas neste tópico para reatribuir as políticas de Acesso Condicional criadas anteriormente no portal clássico do Intune:

- Colete as políticas de Acesso Condicional criadas anteriormente para saber quais configurações você precisará reatribuir mais tarde.

- Siga as etapas deste tópico para recriar essas políticas no Portal do Azure.

- Desabilite as políticas condicionais no Portal Clássico do Intune depois de verificar se as novas políticas estão funcionando conforme o esperado no novo Portal do Azure.
<br /><br />
  - **Antes de desabilitar** as políticas de Acesso Condicional no portal clássico do Intune, planeje como você moverá os usuários para a nova política. Há duas abordagens:
<br /><br />
    - **Usar o mesmo grupo de inclusão para aplicar as políticas criadas no Portal do Azure e criar um novo grupo de isenção para ser usado com as políticas aplicadas pelo portal clássico do Intune**.
      - Mova gradualmente alguns usuários para o grupo de isolamento especificado no portal clássico. Isso impede que as políticas direcionadas pelo portal clássico do Intune sejam aplicadas. As políticas criadas e direcionadas para o mesmo grupo de usuários no Portal do Azure são aplicadas além daquelas aplicadas no portal clássico do Intune. 
<br /><br />
    - **Criar um novo grupo para direcionar as políticas de Acesso Condicional no portal do Azure**. Se você escolher essa abordagem, precisará fazer o seguinte:
      - Remova gradualmente os usuários dos grupos de segurança que têm políticas de Acesso Condicional direcionadas a eles no portal clássico do Intune.
      - Depois de confirmar que a nova política está funcionando para esses usuários, você poderá desabilitar a política no portal clássico do Intune. 
<br /><br />
- Se as configurações de política de Acesso Condicional forem configuradas para usar o EAS (Exchange ActiveSync) no portal clássico do Intune, confira as [instruções neste tópico](#reassign-intune-device-based-conditional-access-policies-for-eas-clients) para **reatribuir as configurações de política de Acesso Condicional EAS no portal do Azure**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Verificar as políticas de Acesso Condicional com base em dispositivo no portal clássico do Intune

1. Acesse o [Portal clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.

2. Escolha **Política** no menu à esquerda.

3. Escolha **Acesso Condicional** e selecione o serviço de nuvem da Microsoft (por exemplo, Exchange Online ou SharePoint Online) para o qual você criou uma política de Acesso Condicional.

4. Anote as configurações de Acesso Condicional e confira-as ao criar as mesmas políticas de Acesso Condicional no portal do Azure.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Políticas de Acesso Condicional baseado em aplicativo e dispositivo funcionando juntas

A folha **Proteção de Aplicativo do Intune** no Portal do Azure permite que os administradores definam as regras condicionais baseadas em aplicativo para que somente os aplicativos que dão suporte às políticas de proteção de aplicativo do Intune tenham permissão de acesso aos recursos corporativos. Você pode optar por sobrepor essas políticas de Acesso Condicional baseado em aplicativo usando políticas de Acesso Condicional baseado em dispositivo. Você pode combinar as políticas condicionais baseadas em aplicativo e em dispositivo (AND lógico) ou fornecer uma opção (OR lógico). Se seus requisitos de política de Acesso Condicional devem:

- Exigir um dispositivo em conformidade **AND** usar o aplicativo aprovado.
  - Você deve definir sua política de Acesso Condicional usando a [folha de Acesso Condicional do Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e a [folha de Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Exigir um dispositivo em conformidade **OR** usar o aplicativo aprovado.
  - Você deve definir sua política de Acesso Condicional usando as folhas de [Portal clássico do Intune](https://manage.microsoft.com) e [Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Este tópico fornece capturas de tela que comparam a experiência do usuário no portal clássico do Intune com o Portal do Azure.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Reatribuir as políticas de Acesso Condicional baseado em dispositivo do Intune

1. Vá para [Acesso Condicional no portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.

2. Escolha **Nova política**.

3. Forneça um nome para a política.

4. Na seção **Atribuições**, escolha **Usuários e grupos** para direcionar a nova política de Acesso Condicional.

    ![Imagem que compara a interface do usuário do grupo de usuários entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-1.png)

    > [!IMPORTANT] 
    > A seleção feita para o Portal do Azure deve corresponder à seleção feita para o Portal Clássico. Por exemplo, se todos os usuários forem selecionados no portal clássico do Intune, selecione **Todos os usuários** no Portal do Azure. Além disso, se você tiver escolhido a opção **Isentar grupos** no portal clássico do Intune, exclua também os grupos selecionados no Portal do Azure.

5. Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.

6. Na seção **Atribuições**, escolha **Aplicativos de nuvem**.

7. Na folha **Aplicativos de nuvem**, escolha **Selecionar aplicativos**.

8. Escolha o aplicativo para o qual você deseja aplicar a nova política de Acesso Condicional e clique em **Selecionar**.

9. Clique em **Concluído**.

    ![Imagem de uma comparação da interface do usuário do aplicativo na nuvem entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-3.png)

    > [!TIP] 
    > Se você tiver vários aplicativos com a mesma política, considere consolidá-las em uma única política no Portal do Azure.

10. Na seção **Atribuições**, escolha **Condições**.

11. Na folha **Condições**, escolha **Plataformas de dispositivo** e escolha as plataformas de dispositivo aplicáveis.

12. Quando você terminar de escolher as plataformas de dispositivo, clique em **Concluído** duas vezes.

    ![Imagem que compara a interface do usuário da Plataforma de dispositivo dos portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-4.png)

    > [!TIP] 
    > Se você tiver escolhido plataformas individuais no portal clássico do Intune, escolha as plataformas individuais no Portal do Azure.

    > [!NOTE] 
    > Você pode especificar as opções de ingresso no domínio ou conformidade para o Windows posteriormente.

13. Na seção **Atribuições**, escolha **Condições**.

14. Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável.

15. Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.

    ![Imagem que compara a interface do usuário dos aplicativos cliente entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-6.png)

16. Se você tiver escolhido as configurações do navegador no portal clássico do Intune, selecione ambos **Navegador** e **Aplicativos móveis e cliente de área de trabalho** no Portal do Azure. Caso você não tenha escolhido as configurações do navegador no portal clássico do Intune, escolha apenas **Aplicativos móveis e cliente de área de trabalho**. 

17. Na seção **Controles de acesso**, escolha **Conceder**.

18. Em **Conceder Controles de Acesso**, escolha **Exigir que o dispositivo seja marcado como em conformidade** e clique em **Selecionar**.

19. Se você tiver uma política para exigir que os dispositivos sejam ingressados no Windows e também permitir dispositivos registrado no Intune e em conformidade com o Windows, escolha **Exigir dispositivo ingressado no domínio** e **Exigir que o dispositivo esteja marcado como em conformidade** junto com **Exigir um dos controles selecionados**.

20. Se você não permitir que dispositivos Windows em conformidade e registrados no Intune, isente a política do Windows da política atual. E crie uma política separada com a opção **Plataformas de dispositivo** definida como **Windows**, inclua as outras condições conforme definido acima e escolha **Exigir dispositivo ingressado no domínio** em **Conceder Controles de Acesso**.

21. Na folha de política de Acesso Condicional **Novo**, ative o botão de alternância **Habilitar política** e clique em **Criar**.

    ![Comparar a interface do usuário da opção Habilitar política de Acesso Condicional entre o Intune e o Azure](./media/conditional-access-intune-reassign/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Reatribuir as políticas de Acesso Condicional baseado em dispositivo do Intune para clientes EAS

Se você tiver definido as configurações do Exchange ActiveSync como parte de uma política do Exchange Online no portal clássico do Intune, será necessário criar uma segunda política de Acesso Condicional no portal do Azure.

1. Vá para [Acesso Condicional no portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.

2. Escolha **Nova política**.

3. Forneça um nome para a política.

4. Na seção **Atribuições**, escolha **Usuários e grupos** para direcionar a nova política de Acesso Condicional.

    ![Imagem mostrando uma comparação da interface do usuário do grupo de usuários entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-12.png)

    > [!IMPORTANT] 
    > A seleção feita para o Portal do Azure deve corresponder à seleção feita para o Portal do Azure. Por exemplo, se todos os usuários forem selecionados no portal clássico do Intune, selecione **Todos os usuários** no Portal do Azure. Além disso, se você tiver escolhido a opção **Isentar grupos** no portal clássico do Intune, exclua também os grupos selecionados no Portal do Azure.

5. Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.

6. Na seção **Atribuições**, escolha **Aplicativos de nuvem**.

7. Na folha **Aplicativos de nuvem**, clique em **Selecionar aplicativos** e escolha **Exchange Online**. Em seguida, clique em **Selecione** e **Concluído**.

    ![Imagem de uma comparação da interface do usuário dos Aplicativos na nuvem entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Políticas de acesso condicional para clientes EAS não podem incluir nenhum outro aplicativo de nuvem.

8. Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável. Se você tiver optado por bloquear os clientes sem suporte no Intune, use a opção **Aplicar política somente a plataformas com suporte**.

    ![Imagem mostrando uma comparação da interface do usuário dos aplicativos cliente entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-15.png)

9. Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.

10. Na seção **Controles de acesso**, escolha **Conceder**.

11. Em **Conceder Controles de Acesso**, escolha **Exigir que o dispositivo seja marcado como em conformidade** e clique em **Selecionar**.

    ![Imagem que compara a interface do usuário da opção Conceder acesso entre os portais do Intune e do Azure](./media/conditional-access-intune-reassign/reassign-ca-16.png)

12. Na folha de política de Acesso Condicional **Novo**, ative o botão de alternância **Habilitar política** e clique em **Criar**.

    ![Comparação da interface do usuário da opção Habilitar política de Acesso Condicional entre o Intune e o Azure](./media/conditional-access-intune-reassign/reassign-ca-17.png)

> [!NOTE]
> Se você definir **Plataformas de dispositivo**, ocorrerá uma falha ao salvar a política com o erro “Configuração de política incompatível”. O Exchange ActiveSync não poderá identificar a plataforma que está sendo usada pelo dispositivo que está se conectando. Portanto, não há suporte para a configuração de plataformas de dispositivo específicas ao criar uma política para dispositivos do Exchange ActiveSync.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Desabilitar as políticas de Acesso Condicional no Portal Clássico do Intune

Depois que tiver reatribuído suas políticas de Acesso Condicional no portal do Azure, é importante desabilitar gradualmente as políticas de Acesso Condicional criadas anteriormente no portal clássico do Intune. Além disso, pode ser necessário usar o mesmo grupo de segurança para aplicar as políticas de Acesso Condicional criadas no portal do Azure.

> [!NOTE]
> Antes de desabilitar as políticas de Acesso Condicional no portal clássico do Intune, confira a seção [Antes de começar](#before-you-begin) no início desse tópico.

### <a name="to-disable-the-conditional-access-policies"></a>Desabilitar as políticas de Acesso Condicional

Como o MDM foi removido do portal clássico do Intune, o seguinte link foi fornecido para exibir/desabilitar essas políticas clássicas:

[https://portal.azure.com/?microsoft_aad_iam_classicPolicyDontHide=true#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/ClassicPolicies](https://portal.azure.com/?microsoft_aad_iam_classicPolicyDontHide=true#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/ClassicPolicies)

## <a name="see-also"></a>Consulte também

- [Maneiras comuns de usar o Acesso Condicional com o Intune](conditional-access-intune-common-ways-use.md)
- [Acesso Condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
- [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
