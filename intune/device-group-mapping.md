---
title: Como usar categorias de dispositivo no Intune
titleSuffix: Azure portal
description: "Saiba como usar as categorias de dispositivos entre as quais os usuários podem escolher quando registram seus dispositivos no Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e34b9cd030244db4bdde78eedbb0f874f49fa1e1
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="map-device-groups"></a>Mapear grupos de dispositivos


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use as categorias de dispositivo do Microsoft Intune para adicionar dispositivos aos grupos automaticamente, com base nas categorias que você definir para facilitar o gerenciamento desses dispositivos.

Categorias de dispositivo usam o seguinte fluxo de trabalho:
1. Crie categorias para os usuários escolherem quando registrarem seus dispositivos
3. Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (consulte **Depois de configurar os grupos de dispositivos** neste tópico para obter mais detalhes).
4. Depois, é possível implantar políticas e aplicativos nesses grupos.

Você pode criar as categorias de dispositivo que desejar, por exemplo:
- Dispositivo de ponto de venda
- Dispositivo de demonstração
- Vendas
- Contabilização
- Manager

## <a name="how-to-configure-device-categories"></a>Como definir categorias de dispositivo

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Etapa 1 – Criar categorias de dispositivo na folha do Intune no Portal do Azure
1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Registro de Dispositivos**.
3. Na folha **Registro de Dispositivos**, escolha **Categorias de Dispositivo**.
4. Na página **Categorias de Dispositivo**, escolha **Criar** para adicionar uma nova categoria.
5. Na folha seguinte, insira um **Nome** para a nova categoria e uma **Descrição** opcional.
6. Quando terminar, clique em **Criar**. Você verá a categoria que você acabou de criar na lista de categorias.

Você usará o nome da categoria do dispositivo quando criar grupos de segurança do Azure Active Directory na etapa 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Etapa 2 – Criar grupos de segurança do Azure Active Directory
Nesta etapa, você criará grupos dinâmicos no portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.

Para continuar, consulte o tópico [Usar atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure Active Directory. 

Use as informações dessa seção para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**. Por exemplo (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Após configurar os grupos de dispositivos e quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou. Depois que escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Como exibir as categorias dos dispositivos que você gerencia

1.  No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune do Portal do Azure, escolha **Dispositivos e Grupos**.

3.  Em **Gerenciar**, clique em **Todos os dispositivos**.

4.  Na lista de dispositivos, examine a coluna **Categoria**.

Se a coluna **Categoria** não for exibida, clique em **Colunas**, escolha **Categoria** na lista e clique **Aplicar**.

### <a name="to-change-the-category-of-a-device"></a>Para alterar a categoria de um dispositivo

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos e Grupos**.
4. Na folha **Dispositivos e Grupos**, escolha **Gerenciar** > **Todos os dispositivos**.
5. Na lista de dispositivos, selecione o dispositivo desejado e, na folha de propriedades do dispositivo, escolha **Gerenciar** > **Propriedades**.
6. Na próxima folha, você pode alterar a **Categoria de dispositivo** do dispositivo selecionado para qualquer um dos nomes das categorias que você configurou anteriormente.

## <a name="after-you-configure-device-groups"></a>Depois de configurar os grupos de dispositivos

Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos do Intune ou ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (portal.manage.microsoft.com) após o registro do dispositivo. Em um dispositivo Windows, acesse o site e, em seguida, **Menu** > **Meus Dispositivos**. Escolha um dispositivo registrado listado na página e, depois, selecione uma categoria. 

Depois de escolher uma categoria, o dispositivo é adicionado automaticamente ao grupo correspondente que você criou. Se um dispositivo já estiver registrado antes da configuração de categorias, o usuário final verá uma notificação sobre o dispositivo no site do Portal da Empresa e deverá selecionar uma categoria na próxima vez que acessar o aplicativo do Portal da Empresa no iOS ou no Android.

## <a name="further-information"></a>Informações adicionais
- Você pode editar uma categoria de dispositivo no Portal do Azure, mas se fizer isso, deverá atualizar manualmente todos os grupos de segurança do Azure Active Directory que fazem referência a essa categoria.

- Se você excluir uma categoria, todos os dispositivos que foram atribuídos a ela posteriormente exibirão o nome da categoria **Não atribuído**.


