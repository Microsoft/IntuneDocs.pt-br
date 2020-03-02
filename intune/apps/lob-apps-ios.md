---
title: Adicionar um aplicativo de linha de negócios do iOS ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar um aplicativo de linha de negócios (LOB) iOS ao Microsoft Intune.
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
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 507c7ecff9715ebf9f24567c735592f3f255ccc9
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609167"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Adicionar um aplicativo de linha de negócios do iOS ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use as informações deste artigo para ajudar a adicionar aplicativos de uma linha de negócios (LOB) iOS ao Microsoft Intune. Um aplicativo de linha de negócios é um aplicativo que pode ser adicionado ao Intune de um arquivo de instalação de aplicativo IPA. Esse tipo de aplicativo normalmente é escrito internamente. Primeiro, ingresse no iOS Developer Enterprise Program (programa para desenvolvedores corporativos para iOS). Para saber mais sobre como fazer isso, confira o [site da Apple](https://developer.apple.com/programs/ios/enterprise/).

> [!NOTE]
> Os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas. Você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários excluírem esses aplicativos, eles deverão acessar a loja de aplicativos e reinstalá-los manualmente.
>
> Aplicativos LOB para iOS têm um limite de tamanho máximo de 4 GB por aplicativo.

> [!NOTE]
> Os identificadores de pacote (por exemplo, *com.contoso.app*) devem ser identificadores exclusivos de um aplicativo. Por exemplo, para instalar uma versão beta de um aplicativo de linha de negócios ao lado da versão de produção para fins de teste, a versão beta deve ter um identificador exclusivo diferente (por exemplo, *com.contoso.app-beta*). Caso contrário, a versão beta se sobreporá à de produção e será tratada como uma atualização. Renomear o arquivo .ipa não tem nenhum efeito sobre esse comportamento.

## <a name="select-the-app-type"></a>Selecione o tipo de aplicativo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de aplicativo **Outros**, selecione **Aplicativo de linha de negócios**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.

## <a name="step-1---app-information"></a>Etapa 1 – Informações do aplicativo

### <a name="select-the-app-package-file"></a>Selecionar um arquivo de pacote do aplicativo

1. No painel **Adicionar aplicativo**, clique em **Selecionar o arquivo do pacote do aplicativo**. 
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do iOS com a extensão **.ipa**.
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

1. Selecione as atribuições de grupo **Necessário**, **Disponível para dispositivos registrados** ou **Desinstalar** para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md) e [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).
2. Clique em **Avançar** para exibir a página **Revisar + criar**. 

## <a name="step-4---review--create"></a>Etapa 4 – Examinar + criar

1. Examine os valores e as configurações que você inseriu para o aplicativo.
2. Ao terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

    A folha **Visão geral** do aplicativo de linha de negócios é exibida.

O aplicativo que você criou agora aparece na lista de aplicativos. Na lista, você pode atribuir o aplicativo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

> [!NOTE]
> Os perfis de provisionamento para aplicativos LOB do iOS têm um aviso de 30 dias antes de expirarem.

## <a name="step-5-update-a-line-of-business-app"></a>Etapa 5: Atualizar um aplicativo de linha de negócios

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

A atualização do aplicativo de linha de negócios será instalada automaticamente.

> [!NOTE]
> Para que o serviço do Intune implante com êxito um novo arquivo IPA no dispositivo, é necessário incrementar a cadeia de caracteres `CFBundleVersion` no arquivo Info.plist em seu pacote de IPA.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou aparece na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Veja [Como monitorar informações e atribuições de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Veja [Visão geral dos ciclos de vida do dispositivo e do aplicativo](../fundamentals/device-lifecycle.md).
