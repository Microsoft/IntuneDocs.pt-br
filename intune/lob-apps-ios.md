---
title: Adicionar um aplicativo de linha de negócios do iOS ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar um aplicativo de linha de negócios (LOB) do iOS ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e76e8940334e90f41fe5e5132f9210d69359f74a
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Adicionar um aplicativo de linha de negócios do iOS ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use as informações deste artigo para ajudar a adicionar aplicativos de uma linha de negócios (LOB) iOS ao Microsoft Intune.

>[!NOTE]
>Os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas. Você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários excluírem esses aplicativos, eles deverão acessar a loja de aplicativos e reinstalá-los manualmente.

## <a name="step-1-specify-the-software-setup-file"></a>Etapa 1: Especificar os arquivos de instalação de software

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, selecione **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione **Aplicativo de linha de negócios**.

## <a name="step-2-configure-the-app-package-file"></a>Etapa 2: Configurar o arquivo de pacote de aplicativos

1. No painel **Adicionar aplicativo**, selecione o **Arquivo do pacote do aplicativo**.
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do iOS com a extensão **.ipa**.
3. Quando tiver terminado, selecione **OK**.


## <a name="step-3-configure-app-information"></a>Etapa 3: Configurar informações do aplicativo

1. No painel **Adicionar aplicativo**, selecione **Informações do aplicativo**.
2. No painel **Informações do aplicativo**, adicione os detalhes do seu aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ser preenchidos automaticamente.
    - **Nome**: insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Sistema operacional mínimo**: na lista, escolha a versão mínima do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Ignorar versão do aplicativo**: defina como **Sim** se o aplicativo for atualizado automaticamente pelo desenvolvedor do aplicativo.
    - **Categoria**: selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: exiba o aplicativo em destaque na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL será exibida no portal da empresa.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: digite as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Quando tiver terminado, selecione **OK**.

## <a name="step-4-finish-up"></a>Etapa 4: Conclusão

1. No painel **Adicionar aplicativo**, confirme se os detalhes do seu aplicativo estão corretos.
2. Selecione **Adicionar** para carregar o aplicativo no Intune.

O aplicativo que você criou agora aparece na lista de aplicativos. Na lista, você pode atribuir o aplicativo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

## <a name="step-5-update-a-line-of-business-app"></a>Etapa 5: atualizar um aplicativo de linha de negócios

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Para que o serviço do Intune implante com êxito um novo arquivo IPA no dispositivo, é necessário incrementar a cadeia de caracteres `CFBundleVersion` no arquivo Info.plist em seu pacote de IPA.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou aparece na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Veja [Como monitorar informações e atribuições de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Veja [Visão geral dos ciclos de vida do dispositivo e do aplicativo](introduction-device-app-lifecycles.md).
