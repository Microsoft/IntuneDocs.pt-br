---
title: "Migrar políticas de acesso condicional no Portal Clássico do Intune para o novo Portal do Azure."
titleSuffix: Intune on Azure
description: "Migrar políticas de acesso condicional no Portal Clássico do Intune para o novo Portal do Azure."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2017
---
# Reatribuir políticas de acesso condicional no Portal Clássico do Intune para o novo Portal do Azure
<a id="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal" class="xliff"></a>

A partir do novo Portal do Azure, o acesso condicional dará suporte para várias políticas por aplicativo juntamente com maior capacidade de personalização.

## Antes de começar
<a id="before-you-begin" class="xliff"></a>

Se você estiver pronto para mover para o novo Portal do Azure, siga as etapas abaixo para reatribuir as políticas de acesso condicional criadas anteriormente no portal clássico do Intune:

- Colete as políticas de acesso condicional criadas anteriormente no portal clássico do Intune para saber quais configurações você precisará reatribuir mais tarde.

- Siga as etapas deste tópico para recriar essas políticas no novo Portal do Azure.

- Desabilite as políticas condicionais no console clássico do Intune depois de verificar se as novas políticas estão funcionando conforme o esperado no novo Portal do Azure.
<br /><br />
    - **Antes de desabilitar** as políticas de acesso condicional no portal clássico do Intune, planeje como você moverá os usuários para a nova política. Há duas abordagens:
<br /><br />
        - **Usar o mesmo grupo de inclusão para aplicar as políticas criadas no novo Portal do Azure e criar um novo grupo de isenção para ser usado com as políticas aplicadas pelo portal clássico do Intune**.
            - Mova gradualmente alguns usuários para o grupo de isolamento especificado no portal clássico.  Isso impede que as políticas direcionadas pelo portal clássico do Intune sejam aplicadas. As políticas criadas e direcionadas para o mesmo grupo de usuários no novo Portal do Azure são aplicadas além daquelas aplicadas no portal clássico do Intune. 
<br /><br />
        - **Crie um novo grupo para direcionar as políticas de acesso condicional no novo Portal do Azure**. Se você escolher essa abordagem, precisará fazer o seguinte:
            - Remova gradualmente os usuários dos grupos de segurança que têm políticas de acesso condicional direcionadas para o portal clássico do Intune.
            - Depois de confirmar que a nova política está funcionando para esses usuários, você poderá desabilitar a política no portal clássico do Intune. 
<br /><br />
- Se as configurações de política de acesso condicional forem configuradas para usar o EAS (Exchange Active Sync) no portal clássico do Intune, consulte as [instruções neste tópico](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) para **reatribuir as configurações de política de acesso condicional EAS no novo Portal do Azure**.

### Verificar as políticas de acesso condicional com base em dispositivo no portal clássico do Intune
<a id="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal" class="xliff"></a>

1.  Acesse o [Portal Clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.

2.  Escolha **Política** no menu à esquerda.

3.  Escolha **Acesso condicional** e selecione o serviço de nuvem da Microsoft (Exchange Online, SharePoint Online, etc.) para o qual você criou uma política de acesso condicional.

4.  Anote as configurações de acesso condicional e use essas notas como referência para criar as mesmas políticas de acesso condicional no novo Portal do Azure.

### Políticas de acesso condicional baseado em aplicativo e dispositivo funcionando juntas
<a id="app-and-device-based-conditional-access-policies-working-together" class="xliff"></a>

A folha **Proteção de Aplicativo do Intune** no novo Portal do Azure permite que os administradores definam as regras condicionais baseado em aplicativo para que somente os aplicativos que dão suporte às políticas de proteção de aplicativo do Intune tenham permissão de acesso aos recursos corporativos. Você pode optar por sobrepor essas políticas de acesso condicional baseado em aplicativo usando políticas de acesso condicional baseado em dispositivo. Dependendo se você deseja combinar as políticas condicionais baseadas em aplicativo e em dispositivo (AND lógico) ou fornecer uma opção (OR lógico). Se seus requisitos de política de acesso condicional são:

- Exigir dispositivo em conformidade **AND** usar o aplicativo aprovado.
    - Você deve definir sua política de acesso condicional usando a [folha de acesso condicional do Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e a [folha de Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Exigir dispositivo em conformidade **OR** usar o aplicativo aprovado.
    - Você deve definir sua política de acesso condicional usando as folhas de [Portal Clássico do Intune](https://manage.microsoft.com) e [Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Este tópico fornece capturas de tela que comparam a experiência do usuário no portal clássico do Intune com o novo Portal do Azure.

## Reatribuir as políticas de acesso condicional baseado em dispositivo do Intune
<a id="to-re-assign-intune-device-based-conditional-access-policies" class="xliff"></a>

1. Vá para [Acesso condicional no novo Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.

2. Escolha **Nova política**.

3. Forneça um nome para a política.

4. Escolha **Usuários e grupos** na seção **Atribuições** direcionada para a nova política de acesso condicional.
    
    ![Comparação da interface do usuário do grupo de usuários entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Se todos os usuários forem selecionados no Portal Clássico do Intune, inclua Todos os Usuários. O mesmo se aplica a grupos. Se você tiver grupos selecionados, será necessário escolher **selecionar usuários e grupos individuais** para incluir esses grupos. Além disso, se você tiver escolhido a opção **Isentar grupos** no Portal Clássico do Intune, será necessário excluir os grupos selecionados no novo Portal do Azure.

5. Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.

6. Escolha **Aplicativos de nuvem** na seção **Atribuições**.

7. Na folha **Aplicativos de nuvem**, escolha **Selecionar aplicativos**.

8. Escolha o aplicativo para o qual você deseja aplicar a nova política de acesso condicional e clique em **Selecionar**.

9. Clique em **Concluído**.

    ![Comparação da interface do usuário do aplicativo de nuvem entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-3.png)

    > [!TIP] 
    > Se você tiver vários aplicativos com a mesma política, considere consolidá-las em uma única política no novo Portal do Azure.

10. Escolha **Condições** na seção **Atribuições**.

11. Na folha **Condições**, escolha **Plataformas de Dispositivo** e escolha as plataformas de dispositivo aplicáveis.

12. Quando você terminar de escolher as plataformas de dispositivo, clique em **Concluído** duas vezes.

    ![Comparação da interface do usuário da plataforma de dispositivos entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-4.png)

    > [!TIP] 
    > Se você tiver escolhido plataformas individuais no portal clássico do Intune, escolha as plataformas individuais no novo Portal do Azure.

    > [!NOTE] 
    > Você pode especificar as opções de ingresso no domínio ou conformidade para o Windows posteriormente.

13. Escolha **Condições** na seção **Atribuições**.

14. Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável.

15. Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.

    ![Comparação da interface do usuário de aplicativos cliente entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-6.png)

16. Se você tiver escolhido as configurações do navegador no portal clássico do Intune, selecione ambos **Navegador** e **Aplicativos móveis e clientes de desktop** no novo Portal do Azure. Caso você não tenha escolhido as configurações do navegador no portal clássico do Intune, escolha apenas **Aplicativos móveis e clientes de área de trabalho**. 

17. Escolha **Conceder** na seção **Controles de acesso**.

18. Escolha **Exigir que o dispositivo esteja marcado como em conformidade** em **Conceder controles de acesso** e clique em **Selecionar**.

19. Se você tiver uma política para exigir que os dispositivos sejam ingressados no Windows e também permitir dispositivos registrado no Intune e em conformidade com o Windows, escolha **Exigir dispositivo ingressado no domínio** e **Exigir que o dispositivo esteja marcado como em conformidade** junto com **Exigir um dos controles selecionados**.

20. Se você não permitir que dispositivos registrados no Intune e em conformidade com o Windows, isente a política do Windows da política atual e crie um política separada com as **Plataformas de dispositivo** definido como **Windows**, inclua as outras condições conforme definido acima e escolha **Exigir dispositivo ingressado no domínio** em **Conceder controles de acesso**.

21. Ative o botão de alternância **Habilitar política** na folha da política de acesso condicional **Novo** e clique em **Criar**.

    ![Habilitar a comparação da interface do usuário da política de AC entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-11.png)

## Reatribuir as políticas de acesso condicional baseado em dispositivo do Intune para clientes EAS
<a id="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients" class="xliff"></a>

Se você tiver definido as configurações do EAS (Exchange Active Sync) como parte de uma política do Exchange Online no portal clássico do Intune, será necessário criar uma segunda política de acesso condicional no novo Portal do Azure.

1. Vá para [Acesso condicional no novo Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.

2. Escolha **Nova política**.

3. Forneça um nome para a política.

4. Escolha **Usuários e grupos** na seção **Atribuições** direcionada para a nova política de acesso condicional.

    ![Comparação da interface do usuário do grupo de usuários entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Se todos os usuários forem selecionados no Portal Clássico do Intune, inclua Todos os Usuários. O mesmo se aplica a grupos. Se você tiver grupos selecionados, será necessário escolher **selecionar usuários e grupos individuais** para incluir esses grupos. Além disso, se você tiver escolhido a opção **Isentar grupos** no Portal Clássico do Intune, será necessário excluir os grupos selecionados no novo Portal do Azure.

5. Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.

6. Escolha **Aplicativos de nuvem** na seção **Atribuições**.

7. Na folha **Aplicativos de nuvem**, clique em **Aplicativos selecionados**, escolha **Exchange Online**, clique em **Selecionar** e em **Concluído**.

    ![Comparação da interface do usuário de aplicativos de nuvem entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Políticas de acesso condicional para clientes EAS não podem incluir nenhum outro aplicativo de nuvem.

8. Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável. Se você tiver optado por bloquear os clientes sem suporte no Intune, use a opção **Aplicar política somente a plataformas com suporte**.

    ![Comparação da interface do usuário de aplicativos cliente entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-15.png)

9. Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.

10. Escolha **Conceder** na seção **Controles de acesso**.

11. Escolha **Exigir que o dispositivo esteja marcado como em conformidade** em **Conceder controles de acesso** e clique em **Selecionar**.

    ![Comparação da interface do usuário de Conceder acesso entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-16.png)

12. Ative o botão de alternância **Habilitar política** na folha da política de acesso condicional **Novo** e clique em **Criar**.

    ![Habilitar a comparação da interface do usuário da política de AC entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-17.png)

## Desabilitar as políticas de acesso condicional no Portal Clássico do Intune
<a id="disable-conditional-access-policies-in-the-intune-classic-portal" class="xliff"></a>
### Antes de começar
<a id="before-you-start" class="xliff"></a>

Depois que tiver reatribuído suas políticas de acesso condicional no novo Portal do Azure, é importante desabilitar gradualmente as políticas de acesso condicional criadas anteriormente no portal clássico do Intune. Além disso, pode ser necessário usar o mesmo grupo de segurança para aplicar as políticas de acesso condicional criadas no novo Portal do Azure

- Consulte a seção [antes de começar](#before-you-begin) no início deste tópico antes de desabilitar as políticas de acesso condicional no portal clássico do Intune.

### Desabilitar as políticas de acesso condicional
<a id="to-disable-the-conditional-access-policies" class="xliff"></a>

1.  Acesse o [Portal Clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.

2.  Escolha **Política** no menu à esquerda.

3.  Escolha **Acesso condicional** e selecione o serviço de nuvem da Microsoft (Exchange Online, SharePoint Online, etc.) para o qual você criou uma política de acesso condicional.

4.  Desmarque a opção **Habilitar política de acesso condicional** e clique em **Salvar**.

    ![Desabilitar as políticas de acesso condicional no Portal Clássico do Intune](./media/reassign-ca-18.png)

## Consulte também
<a id="see-also" class="xliff"></a>

- [Maneiras comuns de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md)
- [Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
- [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)