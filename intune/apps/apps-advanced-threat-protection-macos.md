---
title: Adicionar o Microsoft Defender ATP a dispositivos macOS usando o Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar o Microsoft Defender ATP a dispositivos macOS usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
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
ms.openlocfilehash: 6ae6e8a621b10ec969fa3fcfb2dfeabb8d5a7bdd
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569554"
---
# <a name="add-microsoft-defender-atp-to-macos-devices-using-microsoft-intune"></a>Adicionar o Microsoft Defender ATP a dispositivos macOS usando o Microsoft Intune

Antes que você possa implantar, configurar, monitorar ou proteger aplicativos, você deve adicioná-los ao Intune. Um dos [tipos de aplicativo](~/apps/apps-add.md#app-types-in-microsoft-intune) disponíveis é o Microsoft Defender ATP (Proteção Avançada contra Ameaças). Selecionando esse tipo de aplicativo no Intune, você pode atribuir e instalar o Microsoft Defender ATP em dispositivos que você gerencia que executam o macOS. Esse tipo de aplicativo torna fácil para você atribuir o Microsoft Defender ATP a dispositivos macOS sem exigir que você use a ferramenta de encapsulamento de aplicativos macOS. Para ajudar a manter os aplicativos seguros e atualizados, o aplicativo é fornecido com o MAU (Microsoft AutoUpdate).

## <a name="prerequisites"></a>Pré-requisitos
- O dispositivo macOS deve estar executando o macOS 10.13 ou posterior.
- O dispositivo macOS deve ter pelo menos 650 MB de espaço em disco.
- Implante a extensão do kernel no Intune. Para obter mais informações, confira [Adicionar extensões de kernel do macOS no Intune](~/configuration/kernel-extensions-overview-macos.md).

> [!IMPORTANT]
> A extensão de kernel só poderá ser aprovada automaticamente se estiver presente no dispositivo antes de o aplicativo Microsoft Defender ATP ser instalado. Caso contrário, os usuários verão a mensagem "Extensão do sistema bloqueada" em Macs e deverão aprovar a extensão acessando **Preferências de Segurança** ou **Preferências do Sistema** > **Segurança e Privacidade** e, em seguida, selecionando **Permitir**. Para obter mais informações, confira [Solucionar problemas de extensão de kernel no Microsoft Defender ATP para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-support-kext).

## <a name="add-microsoft-defender-atp-to-intune"></a>Adicionar o Microsoft Defender ATP ao Intune
Você pode adicionar o Microsoft Defender ATP ao Intune usando as seguintes etapas:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. Na lista **Tipo de aplicativo**, no **Microsoft Defender ATP**, selecione **macOS**.

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
> No momento, a Apple não fornece uma maneira de o Intune desinstalar o Microsoft Defender ATP em dispositivos macOS.

## <a name="next-steps"></a>Próximas etapas
- Para saber como configurar o Microsoft Defender ATP em dispositivos macOS, confira [Configurar o Microsoft Defender ATP em dispositivos macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-preferences).
- Para saber mais sobre como incluir e excluir atribuições de aplicativos de grupos de usuários, consulte [Incluir e excluir atribuições de aplicativos](~/apps/apps-inc-exl-assignments.md).
- [Atribuir aplicativos a grupos](~/apps/apps-deploy.md)

