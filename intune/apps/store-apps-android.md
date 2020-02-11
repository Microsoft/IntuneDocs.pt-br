---
title: Adicionar aplicativos da Android Store ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos da loja do Android da Google Play Store ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6b9f6a9303e53652959639193633cdcc00dfb99
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755078"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da Android Store ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Antes de atribuir um aplicativo em um dispositivo ou um grupo de usuários, você deve primeiro adicionar o aplicativo ao Microsoft Intune. 

## <a name="add-an-app"></a>Adicionar um aplicativo

É possível adicionar um aplicativo da Android Store ao Intune do Portal do Azure ao fazer o seguinte:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de **Aplicativos da loja** disponíveis, selecione **Aplicativo da loja Android**.
4. Clique em **Selecionar**.<br>
   As etapas de **Adicionar aplicativo** são exibidas.
5. Para configurar as **Informações do aplicativo** para o aplicativo Android, navegue até a [Google Play Store](https://play.google.com/store) e pesquise o aplicativo que você deseja implantar. Exiba a página do aplicativo e anote os detalhes sobre ele. 
6. No painel **Informações do aplicativo**, adicione os detalhes do aplicativo:
    - **Nome**: Insira o nome do aplicativo como ele será exibido no Portal da Empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: Insira a URL da loja de aplicativos do aplicativo que você deseja criar. Use a URL da página do aplicativo quando os detalhes sobre ele forem exibidos na loja. 
    - **Sistema operacional mínimo**: Na lista, escolha a versão mais recente do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Categoria**: Como opção, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Mostrar como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos. Aplica-se a aplicativos implantados com a intenção de disponibilização.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*.
    - **Observações**: Opcionalmente, insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: Opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
7. Clique em **Avançar** para exibir a página **Marcas de escopo**.
8. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. Confira mais informações em [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).
9. Clique em **Avançar** para exibir a página **Atribuições**.
10. Selecione as atribuições de grupo para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md). 
11. Clique em **Avançar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
12. Ao terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

A folha **Visão geral** do aplicativo criado é exibida.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
