---
title: Adicionar um aplicativo de linha de negócios do Windows Phone ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos de linha de negócios (LOB) do Windows Phone usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 328bafc2a55191c203263911ceaac9b520eb07f5
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755146"
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Adicionar um aplicativo de linha de negócios do Windows Phone ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use as informações deste artigo para adicionar um aplicativo de linha de negócios (LOB) do Windows Phone ao Microsoft Intune. Um aplicativo de LOB é um aplicativo que pode ser adicionado ao Intune a partir de um arquivo de instalação de aplicativo. Esse tipo de aplicativo normalmente é escrito internamente. O Intune instala o aplicativo de LOB no dispositivo do usuário. 

## <a name="select-the-app-type"></a>Selecione o tipo de aplicativo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de aplicativo **Outros**, selecione **Aplicativo de linha de negócios**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.

## <a name="step-1---app-information"></a>Etapa 1 – Informações do aplicativo

### <a name="select-the-app-package-file"></a>Selecionar um arquivo de pacote do aplicativo

1. No painel **Adicionar aplicativo**, clique em **Selecionar o arquivo do pacote do aplicativo**. 
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do Windows Phone com a extensão **.xap**.
   Os detalhes do aplicativo serão exibidos.
3. Ao terminar, selecione **OK** no painel **Arquivo do pacote do aplicativo** para adicionar o aplicativo.

### <a name="set-app-information"></a>Configurar as informações do aplicativo

1. Na página **Informações do aplicativo**, adicione os detalhes do seu aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ser preenchidos automaticamente.
    - **Nome**: Insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido no portal da empresa.
    - **Descrição**: Insira uma descrição do aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **Sistema operacional mínimo**: Na lista, escolha a versão mínima do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Categoria**: Selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Mostrar como um aplicativo em destaque no Portal da Empresa**: Exiba o aplicativo de maneira proeminente em na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL será exibida no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: Opcionalmente, Insira o nome do proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: Insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: Carregue um ícone associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
2. Clique em **Avançar** para exibir a página **Marcas de escopo**.

## <a name="step-2---select-scope-tags-optional"></a>Etapa 2 – Selecionar as marcas de escopo (opcional)
Você pode usar as marcas de escopo para determinar quem pode ver as informações do aplicativo cliente no Intune. Para obter todos os detalhes sobre marcas de escopo, confira [Usar controle de acesso baseado em função e marcas de escopo para TI distribuída](../fundamentals/scope-tags.md).

1. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. 
2. Clique em **Avançar** para exibir a página **Atribuições**.

## <a name="step-3---assignments"></a>Etapa 3 – Atribuições

1. Selecione as atribuições de grupo **Necessário**, **Disponível para dispositivos registrados** ou **Desinstalar** para o aplicativo. Confira mais informações em [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md) e [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).
2. Clique em **Avançar** para exibir a página **Revisar + criar**. 

## <a name="step-4---review--create"></a>Etapa 4 – Examinar + criar

1. Examine os valores e as configurações que você inseriu para o aplicativo.
2. Ao terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

    A folha **Visão geral** do aplicativo de linha de negócios é exibida.

O aplicativo que você criou agora aparece na lista de aplicativos. Na lista, você pode atribuir o aplicativo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou aparece na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Veja [Como monitorar informações e atribuições de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Veja [Visão geral dos ciclos de vida do dispositivo e do aplicativo](../fundamentals/device-lifecycle.md).
