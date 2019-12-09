---
title: Adicionar o Microsoft Edge a dispositivos macOS usando o Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar o Microsoft Edge a dispositivos macOS usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: c31dd652022ae0d394ab2229a0c25b362ad8574d
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563583"
---
# <a name="add-microsoft-edge-to-macos-devices-using-microsoft-intune"></a>Adicionar o Microsoft Edge a dispositivos macOS usando o Microsoft Intune

Antes que você possa implantar, configurar, monitorar ou proteger aplicativos, você deve adicioná-los ao Intune. Um dos [tipos de aplicativo](~/apps/apps-add.md#app-types-in-microsoft-intune) disponíveis é o Microsoft Edge *versão 77 e posteriores*. Selecionando esse tipo de aplicativo no Intune, você pode atribuir e instalar o Microsoft Edge *versão 77 e posteriores* a dispositivos que você gerencia que executam o macOS. Esse tipo de aplicativo torna fácil para você atribuir o Microsoft Edge a dispositivos macOS sem exigir que você use a ferramenta de encapsulamento de aplicativos macOS. Para ajudar a manter os aplicativos seguros e atualizados, o aplicativo é fornecido com o MAU (Microsoft AutoUpdate).

> [!IMPORTANT]
> Esse tipo de aplicativo está em **versão prévia pública** e oferece canais para desenvolvedores e beta para macOS. A implantação é apenas em inglês (EN); contudo, os usuários finais podem alterar o idioma de exibição no navegador em **Configurações** > **Idiomas**. 

> [!NOTE]
> O Microsoft Edge *versão 77 e posteriores* também está disponível para Windows 10.

## <a name="prerequisites"></a>Pré-requisitos
- O dispositivo macOS deve estar executando o macOS 10.12 ou posterior antes de instalar o Microsoft Edge.

## <a name="add-microsoft-edge-to-intune"></a>Adicionar o Microsoft Edge ao Intune
Você pode adicionar o Microsoft Edge versão 77 e posteriores ao Intune usando as seguintes etapas:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. Na lista **Tipo de aplicativo** no **Microsoft Edge, versão 77 e posteriores**, selecione **macOS**.

## <a name="configure-app-information"></a>Configurar informações do aplicativo
Nesta etapa, forneça informações sobre a implantação deste aplicativo. Essas informações ajudam a identificar o aplicativo no Intune e ajudar os usuários a encontrá-lo no aplicativo no Portal da Empresa.

1. Clique em **Informações do aplicativo** para exibir o painel **Informações do aplicativo**.
2. No painel **Informações do aplicativo**, forneça informações sobre a implantação desse aplicativo. Essas informações ajudam a identificar o aplicativo no Intune e ajudar os usuários a encontrá-lo no aplicativo no Portal da Empresa.
    - **Nome**: Insira o nome do aplicativo como ele será exibido no portal da empresa. Verifique se todos os nomes são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. Por exemplo, você pode listar os usuários direcionados na descrição.
    - **Editor**: a Microsoft aparece como o editor.
    - **Categoria**: Opcionalmente, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Essa configuração facilita para os usuários localizarem o aplicativo enquanto navegam pelo Portal da Empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o aplicativo na página principal do Portal da Empresa quando os usuários procurarem aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: a Microsoft aparece como o desenvolvedor.
    - **Proprietário**: a Microsoft aparece como o proprietário.
    - **Observações**: Opcionalmente, insira as observações que você deseja associar a esse aplicativo.
3. Selecione **OK**.

## <a name="configure-microsoft-edge-settings"></a>Definir as configurações do Microsoft Edge
Nesta etapa, configure as opções de instalação do aplicativo.

1. No painel **Adicionar Aplicativo**, selecione **Configurações do aplicativo**.
2. No painel **Configurações do aplicativo**, o Canal **Beta** é selecionado automaticamente e não pode ser alterado.
    - O Canal **Beta** é a experiência de versão prévia mais estável do Microsoft Edge e a melhor opção para um piloto completo em sua organização. Com atualizações importantes a cada seis semanas.

    > [!NOTE]
    > O logotipo do navegador Microsoft Edge é exibido com o aplicativo quando os usuários navegam no Portal da Empresa.
3.  Selecione **OK**.

## <a name="select-scope-tags-optional"></a>Selecione as marcas de escopo (opcional)
Você pode usar as marcas de escopo para determinar quem pode ver as informações do aplicativo cliente no Intune. Para obter todos os detalhes sobre marcas de escopo, confira Usar controle de acesso baseado em função e marcas de escopo para TI distribuída.
1.  Selecione **Escopo (Marcas)**  > **Adicionar**.
2.  Use a caixa **Selecionar** para procurar marcas de escopo.
3.  Marque a caixa de seleção ao lado das marcas de escopo que você deseja atribuir a esse aplicativo.
4.  Clique em **Selecionar** > **OK**.

## <a name="add-the-app"></a>Adicionar o aplicativo
Quando você terminar de configurar, selecione **Adicionar** no painel **Adicionar aplicativo**. 

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. 

> [!NOTE]
> No momento, a Apple não fornece uma maneira de o Intune desinstalar o Microsoft Edge em dispositivos macOS.

## <a name="next-steps"></a>Próximas etapas
- Para saber como configurar o Microsoft Edge em dispositivos macOS, confira [Configurar o Microsoft Edge em dispositivos macOS](https://docs.microsoft.com/deployedge/configure-microsoft-edge-on-mac).
- Para saber mais sobre como incluir e excluir atribuições de aplicativos de grupos de usuários, consulte [Incluir e excluir atribuições de aplicativos](~/apps/apps-inc-exl-assignments.md).
- [Atribuir aplicativos a grupos](~/apps/apps-deploy.md)

