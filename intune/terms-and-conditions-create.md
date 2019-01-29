---
title: Definir termos e condições no Microsoft Intune
titlesuffix: ''
description: Definir termos e condições que os usuários veem no Portal da Empresa do Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 7283b728e519eb2ca5a9a0b7516774c8cfc26f9b
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831506"
---
# <a name="terms-and-conditions-for-user-access"></a>Termos e condições para acesso do usuário

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como um administrador do Intune, você pode exigir que os usuários aceitem os termos e condições da sua empresa antes de usarem o Portal da Empresa para:
- registrar dispositivos
- acessar recursos como email e aplicativos da empresa.    
A configuração dos termos e condições é opcional.

Você pode criar vários conjuntos de termos e atribuí-los a grupos diferentes, por exemplo, para oferecer suporte a idiomas diferentes.

Há duas maneiras de criar os termos e condições da sua empresa:
- usando o Intune conforme descrito neste artigo.
- usando o [recurso de termos de uso do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou) Para saber qual método é melhor para você, confira a [postagem no blog Escolher a solução de Termos certa para a sua organização](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Criar termos e condições
Conclua estas etapas para criar termos e condições. O nome de exibição e a descrição são para uso administrativo enquanto as propriedades dos termos são exibidas para os usuários no Portal da Empresa.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Registro do dispositivo** > **Termos e condições**.
2. Escolha **Criar**.
![Captura de tela do Portal do Azure mostrando o botão Criar para termos e condições](media/terms-create-terms.png)
3. No painel expandido, especifique as seguintes informações:

   - **Nome de exibição**: o nome dos termos no Portal do Azure. Os usuários não veem esse nome.

   - **Descrição**: detalhes opcionais que ajudam a identificar esse conjunto de termos no Portal do Azure.

4. Escolha a seta ao lado de **Definir termos de uso** para abrir o painel de Termos e Condições e, em seguida, insira as seguintes informações:

   ![Captura da tela de aceitação de termos e condições do usuário final com o resumo dos termos](./media/terms-summary-create.png)

   - **Título**: o nome dos termos que os usuários veem no Portal da Empresa acima de **Resumo**.
   - **Resumo dos termos**: texto que explica a implicação de os usuários aceitarem os termos. Por exemplo, "Ao registrar seu dispositivo, você concorda com os termos de uso definidos pela Contoso". Leia os termos com atenção antes de continuar".
   - **Termos e condições**: os termos e condições que os usuários veem e devem aceitar ou rejeitar.

5. Escolha **OK** > **Criar**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Ver como os termos são exibidos para os usuários
O exemplo a seguir mostra o **Título** e o **Resumo de Termos** no console de administrador e no Portal da Empresa.

![Captura de tela do Título e do Resumo de Termos no console de administrador e no Portal da Empresa.](./media/terms-summary-terms.png)

O exemplo a seguir mostra os termos e condições no console de administrador e no Portal da Empresa.

![Captura de tela dos termos e condições no console de administrador e no Portal da Empresa.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Atribuir termos e condições

Você pode atribuir termos e condições a grupos de usuários que devem aceitá-los antes de usar o Portal da Empresa.

1. No Portal do Azure, escolha **Registro de dispositivo** e, depois, **Termos e Condições**.
2. Na lista de termos e condições, escolha os termos que você deseja atribuir > **Gerenciar** > **Atribuições**.
![Captura de tela do painel Atribuir Grupo do Portal do Azure mostrando o botão Selecionar Grupo e o botão Selecionar para a atribuição de termos e condições](media/terms-assign-groups.png)
3. Escolha **Selecionar grupos a incluir** > escolha os grupos aos quais você deseja atribuir os termos > **Selecionar**. Não é possível atribuir Termos e Condições a grupos dinâmicos.
4. No painel **Grupos Atribuídos**, escolha **Salvar**.  Os termos e condições agora estão atribuídos aos usuários nos grupos selecionados. Os usuários serão solicitados a aceitar os termos na próxima vez que acessarem o portal da empresa. Os termos e condições precisam ser aceitos apenas uma vez. Usuários com vários dispositivos não precisam aceitá-los em todos os dispositivos.


## <a name="monitor-terms-and-conditions"></a>Monitorar os termos e condições

1. No Portal do Azure, selecione **Todos os Serviços** > **Monitoramento + Gerenciamento** > **Intune**. 
1. No painel Intune, escolha **Registro do dispositivo** > **Termos e condições**.
2. Na lista de termos e condições, escolha os termos para os quais você deseja exibir a aceitação > **Relatório de Aceitação**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Trabalhar com várias versões dos termos e condições
Você pode editar seus termos e condições e gerenciar suas versões. Cada vez que fizer uma alteração significativa a seus termos e condições, você deverá:
- aumentar o número de versão
- exigir que os usuários aceitem que os novos termos e condições. Mantenha o número de versão atual se, por exemplo, você estiver corrigindo erros de digitação ou alterando a formatação.

1. No Portal do Azure, selecione **Todos os Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. No painel do Intune, escolha **Registro de dispositivo** > **Termos e condições** > escolha os termos e condições que você deseja modificar > **Propriedades**.

4. No painel **Propriedades**, escolha **Termos e Condições** e, em seguida, modifique o **Título**, o **Resumo de Termos** e os **Termos e Condições** conforme necessário. Se as alterações tornarem necessário que os usuários aceitem outra vez os novos termos, escolha **Exigir que os usuários aceitem novamente e aumentar o número de versão para**

4.  Escolha **OK** > **Salvar**.

Os usuários precisam aceitar os termos e condições atualizados apenas uma vez. Usuários com vários dispositivos não precisam aceitar os termos e condições em todos os dispositivos.
