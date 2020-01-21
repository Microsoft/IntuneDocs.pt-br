---
title: Adicionar Microsoft Edge para Windows 10 ao Microsoft Intune
titleSuffix: ''
description: Saiba mais sobre como adicionar o Microsoft Edge para Windows ao Microsoft Intune.
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
ms.openlocfilehash: b4839340ba1f3bad6f28a1120d882d0f600b1d44
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563575"
---
# <a name="add-microsoft-edge-for-windows-10-to-microsoft-intune"></a>Adicionar Microsoft Edge para Windows 10 ao Microsoft Intune

Antes que você possa implantar, configurar, monitorar ou proteger aplicativos, você deve adicioná-los ao Intune. Um dos [tipos de aplicativo](~/apps/apps-add.md#app-types-in-microsoft-intune) disponíveis é o Microsoft Edge *versão 77 e posteriores*. Selecionando esse tipo de aplicativo no Intune, você pode atribuir e instalar o Microsoft Edge *versão 77 e posteriores* a dispositivos que você gerencia que executam o Windows 10.

> [!IMPORTANT]
> Esse tipo de aplicativo está em **versão prévia pública** e oferece canais para desenvolvedores e beta para Windows 10. A implantação é apenas em inglês (EN); contudo, os usuários finais podem alterar o idioma de exibição no navegador em **Configurações** > **Idiomas**. O Microsoft Edge é um aplicativo Win32 instalado no contexto do sistema e em arquiteturas semelhantes (aplicativo x86 em sistema operacional x86 e aplicativo x64 em sistema operacional x64). O Intune detectará se há instalações preexistentes do Microsoft Edge. Se estiverem instaladas no contexto do usuário, a instalação do sistema irá substituí-las. Se estiverem instaladas no contexto do sistema, o sucesso da instalação será informado. Além disso, as atualizações automáticas do Microsoft Edge são **Ativadas** por padrão e o Microsoft Edge não pode ser desinstalado.

> [!NOTE]
> O Microsoft Edge *versão 77 e posteriores* está disponível para macOS também.
> 
> Você não pode usar a implantação de aplicativos interna do Microsoft Edge para computadores de ingresso no local de trabalho. A implantação de aplicativos internos requer a extensão de gerenciamento do Intune, que só existe para dispositivos ingressados no AAD. Você ainda pode implantar o Microsoft Edge *versão 77 e posteriores* usando um *.msi* carregado em **Aplicativos**, confira [Adicionar um aplicativo de linha de negócios para Windows ao Microsoft Intune](~/apps/lob-apps-windows.md).

## <a name="prerequisites"></a>Pré-requisitos
- O Windows 10 RS2 e superiores são necessários.
- Versões pré-instaladas do Microsoft Edge *versão 77 e posteriores* para os canais para **desenvolvedores** e **beta** no contexto do usuário serão substituídas pelo Edge instalado no contexto do sistema.

## <a name="configure-the-app-in-intune"></a>Configurar o aplicativo no Intune
Você pode adicionar um Microsoft Edge versão 77 e posteriores ao Intune usando as seguintes etapas:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. Na lista **Tipo de aplicativo** no **Microsoft Edge, versão 77 e posteriores**, selecione **Windows 10**.

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

## <a name="configure-app-settings"></a>Definir configurações do aplicativo
Nesta etapa, configure as opções de instalação do aplicativo.

1. No painel **Adicionar Aplicativo**, selecione **Configurações do aplicativo**.
2. No painel **Configurações do aplicativo**, selecione **Beta** ou **Dev** na lista **Canal** para determinar de qual Canal do Microsoft Edge você implantará o aplicativo.
    - O Canal **Beta** é a experiência de versão prévia mais estável do Microsoft Edge e a melhor opção para um piloto completo em sua organização. Com as principais atualizações a cada seis semanas, cada versão incorpora os aprendizados e melhorias do Canal de Desenvolvimento.
    - O Canal de **Desenvolvimento** está pronto para comentários empresariais sobre o Windows, Windows Server e macOS. Ele é atualizado a cada semana e contém as melhorias e correções mais recentes.

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
Quando você terminar de configurar o aplicativo, selecione **Adicionar** no painel **Adicionar aplicativo**. 

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. 

> [!NOTE]
> No momento, se você cancelar a atribuição da implantação do Microsoft Edge, ela permanecerá no dispositivo.

## <a name="troubleshooting"></a>Solução de problemas
**Microsoft Edge versão 77 e posteriores para Windows 10:**<br>
O Intune usa a extensão de gerenciamento do Intune para baixar e implantar o instalador do Microsoft Edge em dispositivos Windows 10 atribuídos e comunica as configurações de implantação ao instalador do Microsoft Edge, que baixa e instala o navegador Microsoft Edge diretamente da CDN. Confira os [pré-requisitos da extensão de gerenciamento do Intune](~/apps/intune-management-extension.md#prerequisites) e as melhores práticas descritas ao acessar o Serviço de Atualização do Azure e a CDN para garantir que sua configuração de rede permita que dispositivos Windows 10 acessem esses locais. Além disso, para permitir o acesso aos arquivos de instalação de uma CDN para instalar o navegador, você precisa permitir o acesso aos pontos de extremidade do Windows Update. Para obter mais informações, confira [Gerenciar pontos de extremidade de conexão do Windows 10, versão 1809 – Windows Update](https://docs.microsoft.com/windows/privacy/manage-windows-1809-endpoints#windows-update) e [Pontos de extremidade de rede para Microsoft Intune](~/fundamentals/intune-endpoints.md).

## <a name="next-steps"></a>Próximas etapas
- [Atribuir aplicativos a grupos](~/apps/apps-deploy.md)
