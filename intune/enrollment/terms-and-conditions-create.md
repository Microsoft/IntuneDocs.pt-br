---
title: Definir termos e condições no Microsoft Intune
titleSuffix: ''
description: Definir termos e condições que os usuários veem no Portal da Empresa do Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ef002b508e484d6967bbdd0908729332d866046
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726356"
---
# <a name="terms-and-conditions-for-user-access"></a>Termos e condições para acesso do usuário

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como um administrador do Intune, você pode exigir que os usuários aceitem os termos e condições da sua empresa antes de usarem o Portal da Empresa para:
- registrar dispositivos
- acessar recursos como email e aplicativos da empresa.

A configuração dos termos e condições é opcional.

Você pode criar vários conjuntos de termos e atribuí-los a grupos diferentes, por exemplo, para oferecer suporte a idiomas diferentes.

Há duas maneiras de criar os termos e condições da sua empresa:
- usando o Intune conforme descrito neste artigo.
- usando o [recurso de termos de uso do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)

Para saber qual método é melhor para você, confira a [postagem no blog Escolher a solução de Termos certa para a sua organização](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Criar termos e condições
Conclua estas etapas para criar termos e condições. O nome de exibição e a descrição são para uso administrativo enquanto as propriedades dos termos são exibidas para os usuários no Portal da Empresa.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No painel **Intune**, escolha **Registro do dispositivo** > **Termos e condições**.
3. Escolha **Criar**.
4. Na página **Básico**, especifique as seguintes informações:

   - **Nome**: o nome dos termos no Portal do Azure. Os usuários não veem esse nome.
   - **Descrição**: detalhes opcionais que ajudam a identificar esse conjunto de termos no Portal do Azure.

    ![Captura de tela do portal do Azure mostrando a página Básico para termos e condições](./media/terms-and-conditions-create/terms-basics-page.png)

5. Escolha **Avançar** para ir para a página **Termos** e forneça as seguintes informações:

   - **Título**: o nome dos termos que os usuários veem no Portal da Empresa acima de **Resumo**.
   - **Termos e condições**: os termos e condições que os usuários veem e devem aceitar ou rejeitar.
   - **Resumo dos termos**: texto que explica a implicação de os usuários aceitarem os termos. Por exemplo, "Ao registrar seu dispositivo, você concorda com os termos de uso definidos pela Contoso". Leia os termos com atenção antes de continuar".

6. Escolha **Avançar** para ir para a página **Marcas de escopo**.

7. Escolha **Selecionar marcas de escopo**, selecione as marcas de escopo que você deseja atribuir a esses termos e condições e, em seguida, escolha **Selecionar**. 

8. Escolha **Avançar** para ir para a página **Atribuições** e escolha uma das seguintes opções para **Atribuir a**:
    - **Todos os usuários**: escolha esta opção para atribuir esses termos e condições a todos os usuários.
    - **Selecionar grupos**: escolha esta opção para atribuir esses termos e condições a todos os grupos que você identificar por meio da opção **Selecionar grupos para incluir**.

9. Escolha **Avançar** > **Criar**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Ver como os termos são exibidos para os usuários
O exemplo a seguir mostra o **Título** e o **Resumo de Termos** no console de administrador e no Portal da Empresa.

![Captura de tela do Título e do Resumo de Termos no console de administrador e no Portal da Empresa.](./media/terms-and-conditions-create/terms-summary-terms.png)

O exemplo a seguir mostra os termos e condições no console de administrador e no Portal da Empresa.

![Captura de tela dos termos e condições no console de administrador e no Portal da Empresa.](./media/terms-and-conditions-create/terms-properties-terms.png)


## <a name="monitor-terms-and-conditions"></a>Monitorar os termos e condições

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). 
1. No painel Intune, escolha **Registro do dispositivo** > **Termos e condições**.
2. Na lista de termos e condições, escolha os termos para os quais você deseja exibir a aceitação > **Relatório de Aceitação**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Trabalhar com várias versões dos termos e condições
Você pode editar seus termos e condições e gerenciar suas versões. Cada vez que fizer uma alteração significativa a seus termos e condições, você deverá:
- aumentar o número de versão
- exigir que os usuários aceitem os novos termos e condições

Se você estiver corrigindo erros de digitação ou alterando a formatação, por exemplo, mantenha o número de versão atual.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. No painel do Intune, escolha **Registro de dispositivo** > **Termos e condições** > escolha os termos e condições que você deseja modificar > **Propriedades**.

4. No painel **Propriedades**, escolha **Termos e Condições** e, em seguida, modifique o **Título**, o **Resumo de Termos** e os **Termos e Condições** conforme necessário. Se as alterações tornarem necessário que os usuários aceitem outra vez os novos termos, escolha **Exigir que os usuários aceitem novamente e aumentar o número de versão para**

4. Escolha **OK** > **Salvar**.

Os usuários precisam aceitar os termos e condições atualizados apenas uma vez. Usuários com vários dispositivos não precisam aceitar os termos e condições em todos os dispositivos.
