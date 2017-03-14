---
title: Como usar categorias de dispositivo no Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como usar as categorias de dispositivos que os usuários podem escolher quando registram seus dispositivos no Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c635ced382074f7f45254fb219b58f54b56abb8e
ms.lasthandoff: 02/18/2017


---

# <a name="map-device-groups"></a>Mapear grupos de dispositivos


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use as categorias de dispositivo do Microsoft Intune para adicionar dispositivos aos grupos automaticamente, com base nas categorias que você definir para facilitar o gerenciamento desses dispositivos.

Categorias de dispositivo usam o seguinte fluxo de trabalho:
1.    Crie categorias para os usuários escolherem quando registrarem seus dispositivos
4.    Quando os usuários finais registram seus dispositivos, eles devem escolher uma categoria da lista de categorias configuradas por você. Se um dispositivo já estiver registrado, será solicitado ao usuário final que selecione uma categoria na próxima vez que acessar o aplicativo do Portal da Empresa.


Você pode criar as categorias de dispositivo que desejar, por exemplo:
- Dispositivo de ponto de venda
- Dispositivo de demonstração
- Vendas
- Contabilização
- Manager

## <a name="how-to-configure-device-categories"></a>Como definir categorias de dispositivo

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Etapa 1 – Criar categorias de dispositivo na folha do Intune no Portal do Azure
1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Registrar dispositivos**.
3. Na folha **Registro**, escolha **Categorias de Dispositivo**.
4. Na página **Categorias de Dispositivo**, escolha **Criar** para adicionar uma nova categoria.
5. Na folha seguinte, insira um **Nome** para a nova categoria e uma **Descrição** opcional.
6. Quando terminar, clique em **Criar**. Você verá a categoria que você acabou de criar na lista de categorias.

Você usará o nome da categoria do dispositivo quando criar grupos de segurança do Azure Active Directory na etapa 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Etapa 2 – Criar grupos de segurança do Azure Active Directory
Nesta etapa, você criará grupos dinâmicos no portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.

Para continuar, consulte o tópico [Usar atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure Active Directory. 

Use as informações dessa seção para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**. Por exemplo (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Após configurar os grupos de dispositivos e quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou. Depois que escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Como exibir as categorias dos dispositivos que você gerencia

1.    No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune do Portal do Azure, escolha **Dispositivos e Grupos**.

3.    Em **Gerenciar**, clique em **Todos os dispositivos**.

4.    Na lista de dispositivos, examine a coluna **Categoria**.

Se a coluna **Categoria** não for exibida, clique em **Colunas**, escolha **Categoria** na lista e clique **Aplicar**.

### <a name="to-change-the-category-of-a-device"></a>Para alterar a categoria de um dispositivo

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos e Grupos**.
4. Na folha **Dispositivos e Grupos**, escolha **Gerenciar** > **Todos os dispositivos**.
5. Na lista de dispositivos, selecione o dispositivo desejado e, na folha de propriedades do dispositivo, escolha **Gerenciar** > **Propriedades**.
6. Na próxima folha, você pode alterar a **Categoria de dispositivo** do dispositivo selecionado para qualquer um dos nomes das categorias que você configurou anteriormente.



## <a name="further-information"></a>Informações adicionais
- Você pode editar uma categoria de dispositivo no Portal do Azure, mas se fizer isso, deverá atualizar manualmente todos os grupos de segurança do Azure Active Directory que fazem referência a essa categoria.

- Se você excluir uma categoria, todos os dispositivos que foram atribuídos a ela posteriormente exibirão o nome da categoria **Não atribuído**.



