---
title: "Definir termos e condições no Microsoft Intune"
titlesuffix: Azure portal
description: "Definir termos e condições que os usuários veem no Portal da Empresa do Intune. "
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fa35cb7b08f0bbf677dd7d8b5122b8b286c49b72
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2018
---
# <a name="ensure-users-accept-company-terms-for-access"></a>Conferir se os usuários aceitaram os termos da empresa para acesso

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, você pode exigir que os usuários aceitem os termos e condições de sua empresa antes de poderem usar o Portal da Empresa para registrar seus dispositivos e acessar recursos como aplicativos e email da empresa. A configuração dos termos e condições é opcional.

Você pode criar vários conjuntos de termos e atribuí-los a grupos diferentes, por exemplo, para oferecer suporte a idiomas diferentes.

## <a name="create-terms-and-conditions"></a>Criar termos e condições
Conclua estas etapas para criar termos e condições. O nome de exibição e a descrição são para uso administrativo enquanto as propriedades dos termos são exibidas para os usuários no Portal da Empresa.

1. No Portal do Azure, escolha **Registro de dispositivo** e, depois, **Termos e Condições**.
2. Selecione **Criar**.
![Captura de tela do Portal do Azure mostrando o botão Criar para termos e condições](media/terms-create-terms.png)
3. Na folha expandida, especifique as seguintes informações:

   - **Nome de exibição**: o nome dos termos no Portal do Azure. Os usuários não veem esse nome.

   - **Descrição**: detalhes opcionais que ajudam a identificar esse conjunto de termos no Portal do Azure.

4. Selecione a seta ao lado de Definir termos de uso para abrir a folha de Termos e Condições e, em seguida, insira as seguintes informações:

   ![Captura da tela de aceitação de termos e condições do usuário final com o resumo dos termos](./media/terms-summary-create.png)

   - **Título**: o nome dos termos que os usuários veem no Portal da Empresa acima de **Resumo**.
   - **Resumo dos Termos**: texto que explica a implicação de os usuários aceitarem os termos. Por exemplo, “Ao registrar seu dispositivo, você concorda com os termos de uso definidos pela Contoso”. Leia os termos com atenção antes de continuar".
   - **Termos e Condições**: os termos e condições que os usuários veem e devem aceitar ou rejeitar.

5. Selecione **OK** e **Criar**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Ver como os termos são exibidos para os usuários
O exemplo a seguir mostra o **Título** e o **Resumo de Termos** no console de administrador e no Portal da Empresa.

![Captura de tela do Título e do Resumo de Termos no console de administrador e no Portal da Empresa.](./media/terms-summary-terms.png)

O exemplo a seguir mostra os termos e condições no console de administrador e no Portal da Empresa.

![Captura de tela dos termos e condições no console de administrador e no Portal da Empresa.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Atribuir termos e condições

Você pode atribuir termos e condições a grupos de usuários que devem aceitá-los antes de usar o Portal da Empresa.

1. No Portal do Azure, escolha **Registro de dispositivo** e, depois, **Termos e Condições**.
2. Na lista de termos e condições, selecione as condições que você deseja atribuir e, em seguida, selecione **Grupos Atribuídos**.
![Captura de tela da folha de atribuição de grupo do Portal do Azure mostrando o botão Selecionar Grupo e o botão Selecionar para a atribuição de termos e condições](media/terms-assign-groups.png)
3. Clique no botão **Selecionar Grupo** e, na folha **Selecionar Grupos**, selecione os grupos a que você deseja atribuir os termos e clique em **Selecionar**. Não é possível atribui Termos e Condições a grupos dinâmicos.
4. Na folha **Grupos Atribuídos**, clique em **Salvar**.  Os termos e condições agora estão atribuídos aos usuários nos grupos selecionados. Os usuários serão solicitados a aceitar os termos na próxima vez que acessarem o portal da empresa. Os termos e condições precisam ser aceitos apenas uma vez. Usuários com vários dispositivos não precisam aceitá-los em todos os dispositivos.


## <a name="monitor-terms-and-conditions"></a>Monitorar os termos e condições

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha Intune, escolha **Registro de dispositivo** e escolha **Termos e Condições**.
2. Na lista de termos e condições, selecione os termos para os quais deseja exibir a aceitação e, em seguida, selecione **Status de Aceitação**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Trabalhar com várias versões dos termos e condições
Você pode editar seus termos e condições e gerenciar suas versões. É recomendável aumentar o número de versão e exigir a aceitação sempre que você fizer alterações significativas em seus termos e condições. Se você estiver corrigindo erros de digitação ou alterando a formatação, por exemplo, mantenha o número de versão atual.

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune, escolha **Registro de dispositivo**, escolha **Termos e Condições**, selecione os termos e condições você deseja modificar e, em seguida, selecione **Propriedades**.

4. Na folha **Propriedades**, selecione **Termos e Condições** e, em seguida, modifique o **Título**, o **Resumo de Termos** e os **Termos e Condições** conforme o necessário. Se as alterações feitas obrigarem os usuários a aceitar novamente os novos termos, clique em **Exigir que os usuários aceitem novamente e aumentar o número de versão para**

4.  Selecione **OK** e **Salvar**.

Os usuários precisam aceitar os termos e condições atualizados apenas uma vez. Usuários com vários dispositivos não precisam aceitar os termos e condições em todos os dispositivos.
