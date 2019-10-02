---
title: Categorizar dispositivos em grupos no Intune
titleSuffix: Microsoft Intune
description: Saiba como categorizar os dispositivos em grupos para um gerenciamento mais fácil.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 114637478ffecd2cb88176d1d2304706665a3c22
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723197"
---
# <a name="categorize-devices-into-groups"></a>Categorizar os dispositivos em grupos

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Para facilitar o gerenciamento de dispositivos, você pode usar as categorias de dispositivo Microsoft Intune para adicionar automaticamente os dispositivos a grupos com base em categorias definidas por você.

Categorias de dispositivo usam o seguinte fluxo de trabalho:
1. Crie categorias para os usuários escolherem quando registrarem seus dispositivos.
2. Quando os usuários de dispositivos iOS e Android registram um dispositivo, eles devem escolher uma categoria na lista de categorias configuradas. Para atribuir uma categoria a um dispositivo Windows, os usuários devem usar o site Portal da Empresa.
3. Depois, é possível implantar políticas e aplicativos nesses grupos.

Você pode criar quaisquer categorias de dispositivo que desejar. Por exemplo:
- Dispositivo de ponto de venda
- Dispositivo de demonstração
- Vendas
- Contabilização
- Manager

## <a name="how-to-configure-device-categories"></a>Como definir categorias de dispositivo

### <a name="step-1-create-device-categories-on-the-intune-blade-of-the-azure-portal"></a>Etapa 1: criar categorias de dispositivo na folha do Intune no portal do Azure
1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo**.
2. Na folha **Registro de dispositivo**, escolha **Categorias de dispositivo**.
3. Na página **Categorias de dispositivo**, escolha **Criar** para adicionar uma nova categoria.
4. Na folha **Criar categoria de dispositivo**, insira um **Nome** para a nova categoria e uma **Descrição** opcional.
5. Quando terminar, selecione **Criar**. Você pode ver a nova categoria na lista de categorias.

Você usará o nome da categoria do dispositivo ao criar grupos de segurança do Azure AD (Azure Active Directory) na etapa 2.

### <a name="step-2-create-azure-active-directory-security-groups"></a>Etapa 2: criar grupos de segurança do Azure Active Directory
Nesta etapa, você criará grupos dinâmicos no Portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.

Para continuar, consulte [Usar atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure AD.

Use as informações dessa seção para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**. Por exemplo: **device.deviceCategory - eq** "*o nome de categoria de dispositivo que você obteve do Portal do Azure*".

Após configurar os grupos de dispositivos e quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou. Depois que escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

### <a name="view-the-categories-of-devices-that-you-manage"></a>Exibir as categorias dos dispositivos que você gerencia

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Dispositivos**.

2. Em **Gerenciar**, selecione **Todos os dispositivos**.

3. Na lista de dispositivos, examine a coluna **Categoria de dispositivo**.

Se a coluna **Categoria de dispositivo** não for mostrada, selecione **Colunas**. Escolha **Categoria de dispositivo** na lista e, em seguida, selecione **Aplicar**.

### <a name="change-the-category-of-a-device"></a>Alterar a categoria de um dispositivo

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Dispositivos**.
2. Na folha **Dispositivos**, na seção **Gerenciar**, escolha **Todos os dispositivos**.
3. Na lista de dispositivos, escolha o dispositivo que você deseja. Em seguida, na folha de propriedades do dispositivo, em **Gerenciar**, escolha **Propriedades**.
4. Na próxima folha, você pode alterar a **Categoria de dispositivo** do dispositivo selecionado para qualquer um dos nomes das categorias que você configurou anteriormente.

## <a name="after-you-configure-device-groups"></a>Depois de configurar os grupos de dispositivos

Quando os usuários de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos do Intune ou ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

Os usuários do Windows devem usar o site de Portal da Empresa para selecionar uma categoria.

Independentemente da plataforma, os usuários sempre podem ir para portal.manage.microsoft.com após o registro do dispositivo. Peça para o usuário acessar o site de Portal da Empresa e vá para **Meus Dispositivos**. O usuário pode escolher um dispositivo registrado listado na página e então selecionar uma categoria.

Depois de escolher uma categoria, o dispositivo é adicionado automaticamente ao grupo correspondente que você criou. Se um dispositivo já estiver registrado antes de você configurar as categorias, o usuário verá uma notificação sobre o dispositivo no site do Portal da Empresa. Isso permite que o usuário selecione uma categoria na próxima vez que ele acessar o aplicativo Portal da Empresa em iOS ou Android.

## <a name="further-information"></a>Informações adicionais
- Você pode editar uma categoria de dispositivo no Portal do Azure, mas deve atualizar manualmente todos os grupos de segurança do Azure AD que façam referência a essa categoria.

- Se você excluir uma categoria, os dispositivos atribuídos a ela exibirão o nome da categoria **Não atribuído**.