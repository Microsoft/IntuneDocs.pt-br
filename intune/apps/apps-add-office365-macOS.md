---
title: Instalar o Office 365 em dispositivos macOS usando o Microsoft Intune
titleSuffix: ''
description: Saiba como usar o Microsoft Intune para instalar aplicativos do Office 365 em dispositivos macOS.
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
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cf4c2abb5506f297af8a4e77145abea5360381b
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755350"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Atribuir o Office 365 para dispositivos macOS com o Microsoft Intune

Esse tipo de aplicativo facilita a atribuição de aplicativos do Office 365 2016 para dispositivos macOS. Esse tipo de aplicativo permite que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Para ajudar a manter os aplicativos seguros e atualizados, esses aplicativos são fornecidos com o MAU (Microsoft AutoUpdate). Os aplicativos que você quiser serão exibidos como um aplicativo na lista de aplicativos no console do Intune.


## <a name="before-you-start"></a>Antes de começar

Antes de começar a adicionar o Office 365 a dispositivos macOS, compreenda estes detalhes:

- Os dispositivos nos quais você implanta esses aplicativos deverão estar executando o macOS 10.10 ou posterior.
- O Intune só oferece suporte à adição de aplicativos do Office incluídos com o pacote Office 2016 para Mac.
- Se algum aplicativo do Office estiver aberto quando o Intune instalar o pacote de aplicativos, os usuários poderão perder dados de arquivos não salvos.

## <a name="select-the-office-365-suite-app-type"></a>Selecionar o tipo de aplicativo do Office 365 Suite

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. Selecione **macOS**, na seção **Office 365 Suite** do painel **Selecionar tipo de aplicativo**.
4. Clique em **Selecionar**. As etapas **Adicionar o Office 365 Suite** são exibidas.

## <a name="step-1---app-suite-information"></a>Etapa 1 – Informações do pacote de aplicativos

Nesta etapa, você fornece informações sobre o pacote de aplicativos. Essas informações ajudam a identificar o pacote de aplicativos no Intune, e ajudam os usuários a encontrar o pacote de aplicativos no portal da empresa.

1. Na página **Informações do pacote de aplicativos**, você pode confirmar ou modificar os valores padrão:
    - **Nome do Pacote**: Insira o nome do pacote de aplicativos da forma como ele é exibido no portal da empresa. Verifique se todos os nomes de pacotes usados são exclusivos. Se o mesmo nome de pacote de aplicativos for usado duas vezes, apenas um dos aplicativos será exibido aos usuários no Portal da Empresa.
    - **Descrição do Pacote**: Insira uma descrição para o pacote de aplicativos. Por exemplo, você pode listar os aplicativos que você selecionou para serem incluídos.
    - **Editor**: a Microsoft aparece como o editor.
    - **Categoria**: Opcionalmente, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Essa configuração facilita para os usuários localizarem o pacote de aplicativos enquanto navegam pelo Portal da Empresa.
    - **Mostrar como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: a Microsoft aparece como o desenvolvedor.
    - **Proprietário**: a Microsoft aparece como o proprietário.
    - **Observações**: Insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: O logotipo do Office 365 é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
2. Clique em **Avançar** para exibir a página **Marcas de escopo**.

## <a name="step-2---select-scope-tags-optional"></a>Etapa 2 – Selecionar as marcas de escopo (opcional)
Você pode usar as marcas de escopo para determinar quem pode ver as informações do aplicativo cliente no Intune. Para obter todos os detalhes sobre marcas de escopo, confira [Usar controle de acesso baseado em função e marcas de escopo para TI distribuída](../fundamentals/scope-tags.md).

1. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. 
2. Clique em **Avançar** para exibir a página **Atribuições**.

## <a name="step-3---assignments"></a>Etapa 3 – Atribuições

1. Selecione as atribuições de grupo **Necessário** ou **Disponível para dispositivos registrados** para o pacote de aplicativos. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md) e [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Você não pode desinstalar o pacote de aplicativos do Office 365 para macOS por meio do Intune.

2. Clique em **Avançar** para exibir a página **Revisar + criar**. 

## <a name="step-4---review--create"></a>Etapa 4 – Examinar + criar

1. Examine os valores e as configurações que você inseriu para o pacote do aplicativo.
2. Quando terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

    A folha **Visão geral** do pacote de aplicativo Office 365 para Window 10 que você criou é exibida. O pacote é exibido na lista de aplicativos como uma única entrada.

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como adicionar aplicativos do Office 365 para dispositivos com Windows 10, consulte [Atribuir aplicativos do Office 365 ProPlus 2016 para dispositivos com Windows 10 com o Microsoft Intune](apps-add-office365.md).
- Para saber mais sobre como incluir e excluir atribuições de aplicativos de grupos de usuários, consulte [Incluir e excluir atribuições de aplicativos](apps-inc-exl-assignments.md).
