---
title: Como adicionar aplicativos de linha de negócios do macOS ao Microsoft Intune
titleSuffix: ''
description: Como adicionar aplicativos de LOB (linha de negócios) do macOS ao Microsoft Intune.
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
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7aa6af751e5ab3e1e3cdff6b1d2e3d6693f65df
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755163"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>Como adicionar aplicativos de LOB (linha de negócios) do macOS ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use as informações deste artigo para ajudar a adicionar aplicativos de linha de negócios do macOS ao Microsoft Intune. Você deve baixar uma ferramenta externa para pré-processar seus arquivos *.pkg* antes de carregar o arquivo de linha de negócios para o Microsoft Intune. O pré-processamento dos seus arquivos *.pkg* deve ser realizado em um dispositivo macOS.

> [!NOTE]
> A partir do lançamento do macOS Catalina 10.15, antes de adicionar seus aplicativos ao Intune, verifique se os aplicativos de LOB do macOS estão autenticados. Se os desenvolvedores dos aplicativos de LOB não autenticarem seus aplicativos, os aplicativos não serão executados nos dispositivos macOS dos usuários. Para obter mais informações sobre como verificar se um aplicativo está autenticado, visite [Autenticar seus aplicativos macOS para se preparar para o macOS Catalina](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Notarizing-your-macOS-apps-to-prepare-for-macOS/ba-p/808579).

> [!NOTE]
> Embora os usuários de dispositivos macOS possam remover alguns dos aplicativos macOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários finais excluírem esses aplicativos, eles deverão ir para a loja de aplicativos e reinstalá-los manualmente.

## <a name="before-your-start"></a>Antes de começar

Baixe uma ferramenta externa, marque a ferramenta baixada como um executável e processe previamente os arquivos *.pkg* com a ferramenta, antes de carregar o arquivo de linha de negócios no Microsoft Intune. O pré-processamento dos seus arquivos *.pkg* deve ser realizado em um dispositivo macOS. Use a Ferramenta de Encapsulamento de Aplicativo Intune para Mac para permitir que aplicativos Mac sejam gerenciados pelo Microsoft Intune.

> [!IMPORTANT]
> O arquivo *.pkg* deve ser assinado com o certificado "Instalador de ID de Desenvolvedor", obtido de uma conta de Desenvolvedor da Apple. Somente arquivos *.pkg* podem ser usados para carregar os aplicativos de LOB macOS para o Microsoft Intune. Não há suporte para a conversão de outros formatos, como *.dmg* para *.pkg*.
>

1. Baixe a [Ferramenta de Encapsulamento de Aplicativo do Intune para Mac](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac).

    > [!NOTE]
    > A **Ferramenta de Encapsulamento de Aplicativo Intune para Mac** deve ser executada em um computador macOS. 

2. Marque a ferramenta baixada como um executável:
   - Inicie o aplicativo terminal.
   - Altere o diretório para o local em que `IntuneAppUtil` está localizado.
   - Execute o seguinte comando para tornar a ferramenta executável:<br> 
       `chmod +x IntuneAppUtil`

3. Use o comando `IntuneAppUtil` dentro da **Ferramenta de Encapsulamento de Aplicativo do Intune para Mac** para encapsular o arquivo de aplicativo de LOB *.pkg* de um arquivo *.intunemac*.<br>

    Comandos de exemplo a usar para a Ferramenta de Encapsulamento de Aplicativo do Microsoft Intune para macOS:
    > [!IMPORTANT]
    > Certifique-se de que o argumento `<source_file>` não contenha espaços antes de executar os comandos `IntuneAppUtil`.

    - `IntuneAppUtil -h`<br>
    Esse comando exibirá informações de uso da ferramenta.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Este comando encapsulará o arquivo de aplicativo de LOB *.pkg* para um aplicativo *.intunemac*.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Este comando extrairá os parâmetros detectados e a versão para o arquivo *.intunemac* criado.

## <a name="select-the-app-type"></a>Selecionar o tipo de aplicativo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de aplicativo **Outros**, selecione **Aplicativo de linha de negócios**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.

## <a name="step-1---app-information"></a>Etapa 1 – Informações do aplicativo

### <a name="select-the-app-package-file"></a>Selecionar um arquivo de pacote do aplicativo

1. No painel **Adicionar aplicativo**, clique em **Selecionar o arquivo do pacote do aplicativo**. 
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do macOS com a extensão *.intunemac*.
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
2. Quando terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

    A folha **Visão geral** do aplicativo de linha de negócios é exibida.

O aplicativo que você criou aparece na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

> [!NOTE]
> Se o arquivo *.pkg* contiver vários aplicativos ou instaladores de aplicativos, o Microsoft Intune somente informará que o *aplicativo* foi instalado com êxito quando todos os aplicativos instalados forem detectados no dispositivo.

## <a name="update-a-line-of-business-app"></a>Atualizar um aplicativo de linha de negócios

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Para o serviço Intune para implantar com êxito um novo arquivo *.pkg* para o dispositivo, você deve incrementar o pacote `version` e a cadeia de caracteres `CFBundleVersion` no arquivo *packageinfo* no seu pacote *.pkg*.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou é exibido na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Para obter mais informações, consulte [Como monitorar atribuições e informações de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Para obter mais informações, consulte a [Visão geral do dispositivo e ciclos de vida do aplicativo](../fundamentals/device-lifecycle.md)
