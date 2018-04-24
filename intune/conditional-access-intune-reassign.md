---
title: Migrar o acesso condicional para o Portal do Azure
titlesuffix: Microsoft Intune
description: Reatribua as políticas de acesso condicional criadas anteriormente no Portal Clássico do Intune para o Portal do Azure.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d295ade29522a5593993b5541311eadd9e4c9528
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Reatribuir políticas de acesso condicional no portal clássico do Intune para o Portal do Azure

A partir do novo Portal do Azure, o acesso condicional dará suporte para várias políticas por aplicativo juntamente com maior capacidade de personalização. Se já tiver criado anteriormente as políticas de acesso condicional no Portal Clássico do Intune, você poderá migrá-las para o Portal do Azure. 

## <a name="before-you-begin"></a>Antes de começar

Se você estiver pronto para mudar para o Portal do Azure, siga as etapas neste tópico para reatribuir as políticas de acesso condicional criadas anteriormente no portal clássico do Intune:

- Colete as políticas de acesso condicional criadas anteriormente para saber quais configurações você precisará reatribuir mais tarde.

- Siga as etapas deste tópico para recriar essas políticas no Portal do Azure.

- Desabilite as políticas condicionais no Portal Clássico do Intune depois de verificar se as novas políticas estão funcionando conforme o esperado no novo Portal do Azure.
<br /><br />
    - **Antes de desabilitar** as políticas de acesso condicional no portal clássico do Intune, planeje como você moverá os usuários para a nova política. Há duas abordagens:
<br /><br />
        - **Usar o mesmo grupo de inclusão para aplicar as políticas criadas no Portal do Azure e criar um novo grupo de isenção para ser usado com as políticas aplicadas pelo portal clássico do Intune**.
            - Mova gradualmente alguns usuários para o grupo de isolamento especificado no portal clássico. Isso impede que as políticas direcionadas pelo portal clássico do Intune sejam aplicadas. As políticas criadas e direcionadas para o mesmo grupo de usuários no Portal do Azure são aplicadas além daquelas aplicadas no portal clássico do Intune. 
<br /><br />
        - **Criar um novo grupo para direcionar as políticas de acesso condicional no Portal do Azure**. Se você escolher essa abordagem, precisará fazer o seguinte:
            - Remova gradualmente os usuários dos grupos de segurança que têm políticas de acesso condicional direcionadas a eles no portal clássico do Intune.
            - Depois de confirmar que a nova política está funcionando para esses usuários, você poderá desabilitar a política no portal clássico do Intune. 
<br /><br />
- Se as configurações de política de acesso condicional forem configuradas para usar o EAS (Exchange Active Sync) no portal clássico do Intune, consulte as [instruções neste tópico](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) para **reatribuir as configurações de política de acesso condicional EAS no Portal do Azure**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Verificar as políticas de acesso condicional com base em dispositivo no portal clássico do Intune

1.  Acesse o [Portal clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.

2.  Escolha **Política** no menu à esquerda.

3.  Escolha **Acesso condicional** e selecione o serviço de nuvem da Microsoft (por exemplo, Exchange Online ou SharePoint Online) para o qual você criou uma política de acesso condicional.

4.  Anote as configurações de acesso condicional e consulte-as ao criar as mesmas políticas de acesso condicional no Portal do Azure.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Políticas de acesso condicional baseado em aplicativo e dispositivo funcionando juntas

A folha **Proteção de Aplicativo do Intune** no Portal do Azure permite que os administradores definam as regras condicionais baseadas em aplicativo para que somente os aplicativos que dão suporte às políticas de proteção de aplicativo do Intune tenham permissão de acesso aos recursos corporativos. Você pode optar por sobrepor essas políticas de acesso condicional baseado em aplicativo usando políticas de acesso condicional baseado em dispositivo. Você pode combinar as políticas condicionais baseadas em aplicativo e em dispositivo (AND lógico) ou fornecer uma opção (OR lógico). Se seus requisitos de política de acesso condicional devem:

- Exigir um dispositivo em conformidade **AND** usar o aplicativo aprovado.
    - Você deve definir sua política de acesso condicional usando a [folha de acesso condicional do Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e a [folha de Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Exigir um dispositivo em conformidade **OR** usar o aplicativo aprovado.
    - Você deve definir sua política de acesso condicional usando as folhas de [Portal clássico do Intune](https://manage.microsoft.com) e [Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Este tópico fornece capturas de tela que comparam a experiência do usuário no portal clássico do Intune com o Portal do Azure.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Reatribuir as políticas de acesso condicional baseado em dispositivo do Intune

1. Vá para [Acesso condicional no Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.

2. Escolha **Nova política**.

3. Forneça um nome para a política.

4. Na seção **Atribuições**, escolha **Usuários e grupos** para direcionara a nova política de acesso condicional.
    
    ![Imagem mostrando uma comparação da interface do usuário do grupo de usuários entre os Portais do Intune e do Azure](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > A seleção feita para o Portal do Azure deve corresponder à seleção feita para o Portal Clássico. Por exemplo, se todos os usuários forem selecionados no portal clássico do Intune, selecione **Todos os usuários** no Portal do Azure. Além disso, se você tiver escolhido a opção **Isentar grupos** no portal clássico do Intune, exclua também os grupos selecionados no Portal do Azure.

5. Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.

6. Na seção **Atribuições**, escolha **Aplicativos de nuvem**.

7. Na folha **Aplicativos de nuvem**, escolha **Selecionar aplicativos**.

8. Escolha o aplicativo para o qual você deseja aplicar a nova política de acesso condicional e clique em **Selecionar**.

9. Clique em **Concluído**.

    ![Imagem mostrando uma comparação da interface do usuário do aplicativo de nuvem entre os Portais do Intune e do Azure](./media/reassign-ca-3.png)

    > [!TIP] 
    > Se você tiver vários aplicativos com a mesma política, considere consolidá-las em uma única política no Portal do Azure.

10. Na seção **Atribuições**, escolha **Condições**.

11. Na folha **Condições**, escolha **Plataformas de dispositivo** e escolha as plataformas de dispositivo aplicáveis.

12. Quando você terminar de escolher as plataformas de dispositivo, clique em **Concluído** duas vezes.

    ![Imagem mostrando uma comparação da interface do usuário da plataforma do dispositivo entre os Portais do Intune e do Azure](./media/reassign-ca-4.png)

    > [!TIP] 
    > Se você tiver escolhido plataformas individuais no portal clássico do Intune, escolha as plataformas individuais no Portal do Azure.

    > [!NOTE] 
    > Você pode especificar as opções de ingresso no domínio ou conformidade para o Windows posteriormente.

13. Na seção **Atribuições**, escolha **Condições**.

14. Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável.

15. Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.

    ![Imagem mostrando uma comparação da interface do usuário do aplicativo cliente entre os Portais do Intune e do Azure](./media/reassign-ca-6.png)

16. Se você tiver escolhido as configurações do navegador no portal clássico do Intune, selecione ambos **Navegador** e **Aplicativos móveis e cliente de área de trabalho** no Portal do Azure. Caso você não tenha escolhido as configurações do navegador no portal clássico do Intune, escolha apenas **Aplicativos móveis e cliente de área de trabalho**. 

17. Na seção **Controles de acesso**, escolha **Conceder**.

18. Em **Conceder Controles de Acesso**, escolha **Exigir que o dispositivo seja marcado como em conformidade** e clique em **Selecionar**.

19. Se você tiver uma política para exigir que os dispositivos sejam ingressados no Windows e também permitir dispositivos registrado no Intune e em conformidade com o Windows, escolha **Exigir dispositivo ingressado no domínio** e **Exigir que o dispositivo esteja marcado como em conformidade** junto com **Exigir um dos controles selecionados**.

20. Se você não permitir que dispositivos Windows em conformidade e registrados no Intune, isente a política do Windows da política atual. E crie uma política separada com a opção **Plataformas de dispositivo** definida como **Windows**, inclua as outras condições conforme definido acima e escolha **Exigir dispositivo ingressado no domínio** em **Conceder Controles de Acesso**.

21. Na folha de política de acesso condicional **Novo**, ative o botão de alternância **Habilitar política** e clique em **Criar**.

    ![Imagem mostrando como habilitar a comparação de interface do usuário da política de acesso condicional entre os Portais do Intune e do Azure](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Reatribuir as políticas de acesso condicional baseado em dispositivo do Intune para clientes EAS

Se você tiver definido as configurações do Exchange Active Sync como parte de uma política do Exchange Online no portal clássico do Intune, será necessário criar uma segunda política de acesso condicional no Portal do Azure.

1. Vá para [Acesso condicional no Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.

2. Escolha **Nova política**.

3. Forneça um nome para a política.

4. Na seção **Atribuições**, escolha **Usuários e grupos** para direcionara a nova política de acesso condicional.

    ![Imagem mostrando uma comparação da interface do usuário do grupo de usuários entre os Portais do Intune e do Azure](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > A seleção feita para o Portal do Azure deve corresponder à seleção feita para o Portal do Azure. Por exemplo, se todos os usuários forem selecionados no portal clássico do Intune, selecione **Todos os usuários** no Portal do Azure. Além disso, se você tiver escolhido a opção **Isentar grupos** no portal clássico do Intune, exclua também os grupos selecionados no Portal do Azure.

5. Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.

6. Na seção **Atribuições**, escolha **Aplicativos de nuvem**.

7. Na folha **Aplicativos de nuvem**, clique em **Selecionar aplicativos** e escolha **Exchange Online**. Em seguida, clique em **Selecione** e **Concluído**.

    ![Imagem mostrando uma comparação da interface do usuário do aplicativo de nuvem entre os Portais do Intune e do Azure](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > As políticas de acesso condicional para clientes EAS não podem incluir nenhum outro aplicativo de nuvem.

8. Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável. Se você tiver optado por bloquear os clientes sem suporte no Intune, use a opção **Aplicar política somente a plataformas com suporte**.

    ![Imagem mostrando uma comparação da interface do usuário do aplicativo cliente entre os Portais do Intune e do Azure](./media/reassign-ca-15.png)

9. Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.

10. Na seção **Controles de acesso**, escolha **Conceder**.

11. Em **Conceder Controles de Acesso**, escolha **Exigir que o dispositivo seja marcado como em conformidade** e clique em **Selecionar**.

    ![Imagem mostrando uma comparação da interface do usuário de concessão de acesso entre os Portais do Intune e do Azure](./media/reassign-ca-16.png)

12. Na folha de política de acesso condicional **Novo**, ative o botão de alternância **Habilitar política** e clique em **Criar**.

    ![Imagem mostrando Habilitar a comparação de interface do usuário da política de acesso condicional entre os Portais do Intune e do Azure](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Desabilitar as políticas de acesso condicional no Portal Clássico do Intune

Depois que tiver reatribuído suas políticas de acesso condicional no Portal do Azure, é importante desabilitar gradualmente as políticas de acesso condicional criadas anteriormente no portal clássico do Intune. Além disso, pode ser necessário usar o mesmo grupo de segurança para aplicar as políticas de acesso condicional criadas no Portal do Azure.

> [!NOTE]
> Antes de desabilitar as políticas de acesso condicional no portal clássico do Intune, consulte a seção [Antes de começar](#before-you-begin) no início desse tópico.

### <a name="to-disable-the-conditional-access-policies"></a>Desabilitar as políticas de acesso condicional

1.  Acesse o [Portal clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.

2.  Escolha **Política** no menu à esquerda.

3.  Escolha **Acesso condicional** e selecione o serviço de nuvem da Microsoft (por exemplo, Exchange Online ou SharePoint Online) para o qual você criou uma política de acesso condicional.

4.  Desmarque a opção **Habilitar política de acesso condicional** e clique em **Salvar**.

    ![Imagem mostrando Desabilitar políticas de acesso condicional no Portal Clássico do Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Consulte também

- [Maneiras comuns de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md)
- [Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
- [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
