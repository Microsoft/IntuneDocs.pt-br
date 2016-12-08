---
title: Categorizar os dispositivos com o mapeamento do grupo de dispositivos | Microsoft Intune
description: "Use o mapeamento do grupo de dispositivos do Microsoft Intune para agrupar dispositivos em categorias que você define para facilitar o gerenciamento desses dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: bdfa96a4268733bf6fa3a7999d85a881a7c4e513

---

# Categorize os dispositivos com o mapeamento do grupo de dispositivos no Microsoft Intune
Use o **mapeamento do grupo de dispositivos** do Microsoft Intune para adicionar dispositivos aos grupos automaticamente, com base nas categorias que você definir para facilitar o gerenciamento desses dispositivos. 

O mapeamento do grupo de dispositivos usa o seguinte fluxo de trabalho:
1. Crie categorias para os usuários escolherem quando registrarem seus dispositivos
2. Crie grupos ou use grupos existentes para cada categoria que você deseja usar. De acordo com a versão do Intune que você está usando, tais grupos serão do Intune ou grupos de segurança do Azure Active Directory.
2. Você configura as regras que mapeiam a categoria escolhida para o grupo de dispositivos que você criou.
3. Quando os usuários finais registram seus dispositivos, eles devem escolher uma categoria da lista de categorias configuradas por você. Depois que escolherem, o dispositivo será adicionado automaticamente ao grupo correspondente que você criou. Se um dispositivo já estiver registrado, será solicitado ao usuário final que selecione uma categoria na próxima vez que acessar o aplicativo do Portal da Empresa.
4. Depois, é possível implantar políticas e aplicativos nesses grupos.

Você pode criar as categorias de dispositivo que desejar, por exemplo:
* Dispositivo de ponto de venda
* Dispositivo de demonstração
* Vendas
* Contabilização
* Manager

## Informações importantes sobre uma alteração no gerenciamento de grupos para o Intune

Com base nos seus comentários, estamos unificando a experiência de agrupamento e direcionamento no Enterprise Mobility + Security. Por esse motivo, em breve converteremos os grupos do Intune em grupos de segurança baseados no Azure Active Directory. Após essa alteração, você não criará grupos usando o Intune novamente. Em vez disso, você poderá criá-los no portal do Azure. Essa alteração ocorrerá de forma gradual e você pode ler os detalhes completos e a linha do tempo [neste tópico](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### Qual procedimento deste tópico você deve usar para configurar o mapeamento de grupo de dispositivos?

Em virtude da implementação faseada dos grupos de segurança do Azure Active Directory, você deve abrir o espaço de trabalho **Grupos** no [console de administração do Intune](https://manage.microsoft.com) para identificar o procedimento a se usar:

-  Se um link para o portal do Azure for exibido, você não está mais usando os grupos do Intune. Siga o procedimento [Como configurar o mapeamento do grupo de dispositivos para grupos do Azure Active Directory](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) abaixo.
-  Se um link para o portal do Azure não for exibido, você ainda está usando os grupos do Intune. Siga o procedimento [Como configurar o mapeamento do grupo de dispositivos para grupos do Intune](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) abaixo.

## Como configurar o mapeamento do grupo de dispositivos para grupos do Intune
1. Para cada categoria de dispositivos que você deseja usar, crie um grupo de dispositivos do Intune ou identifique um grupo existente. Para obter informações sobre como criar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).
2. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
3. No espaço de trabalho **Administração**, expanda o **Gerenciamento de Dispositivo Móvel** e escolha **Mapeamento do Grupo de Dispositivos**.
4. Na página **Mapeamento do Grupo de Dispositivos**, habilite o mapeamento do grupo de dispositivos.
5. Escolha **Adicionar** para criar uma nova regra de mapeamento.
6. Na caixa de diálogo **Add device group mapping rule** (Adicionar regra de mapeamento do grupo de dispositivos), digite o nome da categoria que você deseja criar e, na lista suspensa, escolha a coleção de dispositivos para a qual você deseja mapear essa categoria. Escolha **Adicionar** depois de concluir.
7. Quando terminar de adicionar categorias e grupos, escolha **Salvar**.



## Como configurar o mapeamento do grupo de dispositivos para grupos do Azure Active Directory

### Etapa 1 – Criar categorias de dispositivo no console de administração do Intune
1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
3. No espaço de trabalho **Administração**, expanda o **Gerenciamento de Dispositivo Móvel** e escolha **Categorias de Dispositivo**.
4. Na página **Categorias de Dispositivo**, será exibida uma lista na qual você poderá configurar categorias de dispositivo: 
- Você pode digitar um nome e clicar em **Adicionar**, para adicioná-la como uma nova categoria de dispositivo.
- Além disso, você pode selecionar uma categoria e a **Excluir** em seguida.

Você usará o nome da categoria do dispositivo quando criar grupos de segurança do Azure Active Directory na etapa 2.

### Etapa 2 – Criar grupos de segurança do Azure Active Directory

Nesta etapa, você criará grupos dinâmicos no portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.

Para continuar, consulte o tópico [Usar atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure Active Directory.
Use as informações desse tópico para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**.
Por exemplo, (**dispositivo.Categoriadodispositivo -eq** ”<*nome da categoria do dispositivo obtido no console de administração do Intune*>”)


## Depois de configurar os grupos de dispositivos

Quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou. Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos do Intune ou ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

### Consulte também
[Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


