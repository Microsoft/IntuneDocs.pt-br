---
title: Como categorizar dispositivos em grupos no Intune
titleSuffix: Microsoft Intune
description: "Saiba como categorizar os dispositivos em grupos para um gerenciamento mais fácil."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d07b025881ea78299d617205ce5ba39bb92a1231
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="categorize-devices-into-groups-for-easier-management"></a>Categorizar os dispositivos em grupos para um gerenciamento mais fácil

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use as categorias de dispositivo do Microsoft Intune para adicionar dispositivos aos grupos automaticamente, com base nas categorias que você definir para facilitar o gerenciamento desses dispositivos.

Categorias de dispositivo usam o seguinte fluxo de trabalho:
1. Crie categorias para os usuários escolherem quando registrarem seus dispositivos
2. Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (para saber mais, confira **Depois de configurar os grupos de dispositivos** neste artigo).
3. Depois, é possível implantar políticas e aplicativos nesses grupos.

Você pode criar as categorias de dispositivo que desejar, por exemplo:
- Dispositivo de ponto de venda
- Dispositivo de demonstração
- Vendas
- Contabilização
- Manager

## <a name="how-to-configure-device-categories"></a>Como definir categorias de dispositivo

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Etapa 1 – Criar categorias de dispositivo na folha do Intune no Portal do Azure
1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo**.
2. Na folha **Registro de dispositivo**, escolha **Categorias de dispositivo**.
3. Na página **Categorias de dispositivo**, escolha **Criar** para adicionar uma nova categoria.
4. Na folha **Criar categoria de dispositivo**, insira um **Nome** para a nova categoria e uma **Descrição** opcional.
5. Quando terminar, clique em **Criar**. Você pode ver a nova categoria na lista de categorias.

Você usará o nome da categoria do dispositivo quando criar grupos de segurança do Azure Active Directory na etapa 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Etapa 2 – Criar grupos de segurança do Azure Active Directory
Nesta etapa, você criará grupos dinâmicos no portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.

Para continuar, consulte o artigo [Usar atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure Active Directory.

Use as informações dessa seção para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**. Por exemplo (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Após configurar os grupos de dispositivos e quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou. Depois que escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Como exibir as categorias dos dispositivos que você gerencia

1.  No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Dispositivos**.

2.  Em **Gerenciar**, clique em **Todos os dispositivos**.

3.  Na lista de dispositivos, examine a coluna **Categoria de dispositivo**.

Se a coluna **Categoria de dispositivo** não for exibida, clique em **Colunas**, escolha **Categoria de dispositivo** na lista e, em seguida, clique em **Aplicar**.

### <a name="to-change-the-category-of-a-device"></a>Para alterar a categoria de um dispositivo

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Dispositivos**.
2. Na folha **Dispositivos**, na seção **Gerenciar**, escolha **Todos os dispositivos**.
3. Na lista de dispositivos, selecione o dispositivo desejado e, em seguida, na folha de propriedades do dispositivo, na seção **Gerenciar**, escolha **Propriedades**.
4. Na próxima folha, você pode alterar a **Categoria de dispositivo** do dispositivo selecionado para qualquer um dos nomes das categorias que você configurou anteriormente.

## <a name="after-you-configure-device-groups"></a>Depois de configurar os grupos de dispositivos

Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos do Intune ou ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

Os usuários finais do Windows deve usar o site de Portal da Empresa para selecionar uma categoria.

Independentemente de plataforma, os usuários finais sempre podem ir para portal.manage.microsoft.com após o registro do dispositivo. Peça para o usuário acessar o site de Portal da Empresa e vá para **Meus Dispositivos**. Eles podem escolher um dispositivo registrado listado na página e, depois, selecione uma categoria.

Depois de escolher uma categoria, o dispositivo é adicionado automaticamente ao grupo correspondente que você criou. Se um dispositivo já estiver registrado antes da configuração de categorias, o usuário final verá uma notificação sobre o dispositivo no site do Portal da Empresa e deverá selecionar uma categoria na próxima vez que acessar o aplicativo do Portal da Empresa no iOS ou no Android.

## <a name="further-information"></a>Informações adicionais
- Você pode editar uma categoria de dispositivo no Portal do Azure, mas deverá atualizar manualmente todos os grupos de segurança do Azure Active Directory que fazem referência a essa categoria.

- Se você excluir uma categoria, os dispositivos atribuídos a ela exibirão o nome da categoria **Não atribuído**.
