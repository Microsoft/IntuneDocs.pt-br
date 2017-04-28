---
title: "Configurações da política de termos e condições | Microsoft Docs"
description: "Você pode implantar os termos e condições do Intune em grupos de usuários para explicar como o registro, o acesso aos recursos de trabalho e o uso do aplicativo Portal da Empresa afetam usuários e dispositivos."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 177485a0b09a2b0213a293914799a34a3bfa1136
ms.lasthandoff: 04/24/2017


---

# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a>Configurações de política de termos e condições no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Você pode implantar os termos e condições do Intune em grupos de usuários para explicar como o registro, o acesso aos recursos de trabalho e o aplicativo de Portal da Empresa afetam usuários e dispositivos. Os usuários devem aceitar estes termos e condições antes de poderem usar o Portal da Empresa para registrar e acessar o trabalho.

Você pode criar e implantar várias políticas que contêm termos e condições diferentes. Você pode também gerar versões dos mesmos termos e condições em idiomas diferentes e, em seguida, implantá-las aos grupos apropriados.

## <a name="create-a-terms-and-conditions-policy"></a>Criar uma política de termos e condições

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.

    ![Captura de tela da política de termos e condições](./media/pol-sa-terms-conditions.png)

2.  Clique em **Adicionar** para criar uma nova política de termos e condições.

    Você também pode **Editar** ou **Excluir** uma política existente.

3.  Na página **Criar Termos e Condições**, especifique as seguintes informações:

    -   **Nome**&mdash;Um nome de política exclusivo exibido no console do Intune.

    -   **Descrição**&mdash;Detalhes que ajudarão a identificar a política no console do Intune.

    -   **Título**&mdash;O título que os usuários veem no Portal da Empresa.

    -   **Texto para explicar o que significa se o usuário aceitar**&mdash;O rótulo que os usuários veem quanto a sua aceitação. Por exemplo, "Eu concordo com os termos e condições".

4.  Ao terminar, clique em **Salvar**. A nova política é exibida no nó **Termos e Condições** do espaço de trabalho **Política**.

## <a name="deploy-a-terms-and-conditions-policy"></a>Implantar uma política de termos e condições

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.

2.  Na lista **Políticas de Termos e Condições**, selecione a política que você deseja implantar e clique em **Gerenciar Implantação**.

3.  Na caixa de diálogo **Gerenciar Implantação**, selecione os grupos de usuário nos quais você implantará a política e clique em **OK**.

    Quando os usuários de destino acessam o portal da empresa, o Intune exibe os termos e condições que você implantou. Os usuários devem aceitar esses termos antes de que possam obter acesso aos recursos da empresa.

## <a name="monitor-a-terms-and-conditions-policy"></a>Monitorar uma política de termos e condições

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.

2.  Na janela **Criar Novo Relatório**, clique em **Exibir Relatório**. O relatório será aberto, detalhando quais usuários que aceitaram os termos e condições que você implantou.

### <a name="updates-and-version-control-for-terms-and-conditions"></a>Atualizações e controle de versão dos termos e condições
Quando edita uma política de termos e condições existente, você pode escolher qual comportamento ocorre ao implantar a política. Use o procedimento a seguir para ajudá-lo a atualizar as políticas de termos e condições existentes.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Trabalhar com várias versões dos termos e condições

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.

2.  Selecione a política de termos e condições que deseja editar e, em seguida, clique em **Editar**.

3.  Na página **Editar Termos e Condições**, faça as edições necessárias e especifique se essa nova versão requer que todos os usuários aceitem os termos e condições ou se somente novos usuários verão a nova versão.

    É recomendável aumentar o número de versão e exigir a aceitação sempre que você fizer alterações significativas em sua política de termos e condições. Se você estiver corrigindo erros de digitação ou alterando a formatação, por exemplo, mantenha o número de versão atual.

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

