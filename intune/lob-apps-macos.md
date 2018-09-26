---
title: Como adicionar aplicativos de linha de negócios do macOS ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar aplicativos de LOB (linha de negócios) do macOS ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b735478e22558c138476faec081351e3974cf95c
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602190"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>Como adicionar aplicativos de LOB (linha de negócios) do macOS ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use as informações deste artigo para ajudar a adicionar aplicativos de linha de negócios do macOS ao Microsoft Intune. Você deve baixar uma ferramenta externa para pré-processar seus arquivos *.pkg* antes de carregar o arquivo de linha de negócios para o Microsoft Intune. O pré-processamento dos seus arquivos *.pkg* deve ser realizado em um dispositivo macOS.

> [!NOTE]
> Embora os usuários de dispositivos macOS possam remover alguns dos aplicativos macOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários finais excluírem esses aplicativos, eles deverão ir para a loja de aplicativos e reinstalá-los manualmente.

## <a name="before-your-start"></a>Antes de começar

Você deve baixar uma ferramenta externa para pré-processar seus arquivos *.pkg* antes de carregar o arquivo de linha de negócios para o Microsoft Intune. O pré-processamento dos seus arquivos *.pkg* deve ser realizado em um dispositivo macOS. Use a Ferramenta de Encapsulamento de Aplicativo Intune para Mac para permitir que aplicativos Mac sejam gerenciados pelo Microsoft Intune.

> [!IMPORTANT]
> Somente arquivos *.pkg* podem ser usados para carregar os aplicativos de LOB macOS para o Microsoft Intune. Não há suporte para a conversão de outros formatos, como *.dmg* para *.pkg*.

1. Baixe e execute a [Ferramenta de Encapsulamento de Aplicativo Intune para Mac](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac).

    > [!NOTE]
    > A **Ferramenta de Encapsulamento de Aplicativo Intune para Mac** deve ser executada em um computador macOS.

2. Use o comando `IntuneAppUtil` dentro da **Ferramenta de Encapsulamento de Aplicativo do Intune para Mac** para encapsular o arquivo de aplicativo de LOB *.pkg* de um arquivo *.intunemac*.<br>

    Comandos de exemplo a usar para a Ferramenta de Encapsulamento de Aplicativo do Microsoft Intune para macOS:
    
    - `IntuneAppUtil -h`<br>
    Esse comando exibirá informações de uso da ferramenta.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Este comando encapsulará o arquivo de aplicativo de LOB *.pkg* para um aplicativo *.intunemac*.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Este comando extrairá os parâmetros detectados e a versão para o arquivo *.intunemac* criado.

## <a name="step-1---specify-the-software-setup-file"></a>Etapa 1 – Especificar os arquivos de instalação de software

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos clientes**.
4. Na carga de trabalho **Aplicativos clientes**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. No painel **Adicionar aplicativo**, escolha **Aplicativo de linha de negócios**.

## <a name="step-2---configure-the-app-package-file"></a>Etapa 2 - configurar o arquivo de pacote de aplicativos

1. No painel **Adicionar aplicativo**, escolha o **Arquivo do pacote do aplicativo**.
2. No painel **Arquivo do pacote do aplicativo**, escolha o botão procurar e selecione um arquivo de instalação do macOS com a extensão *.intunemac*.
3. Quando terminar, escolha **OK**.


## <a name="step-3---configure-app-information"></a>Etapa 3 - configurar informações do aplicativo

1. No painel **Adicionar aplicativo**, escolha **Informações do aplicativo**.
2. No painel **Informações do aplicativo**, adicione os detalhes do seu aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome** – insira o nome do aplicativo que será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição** -insira uma descrição para o aplicativo que será exibida aos usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Logotipo** – carregue um ícone que será associado ao aplicativo. Esse é o ícone que é exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
3. Quando terminar, escolha **OK**.

## <a name="step-4---finish-up"></a>Etapa 4 - conclusão

1. No painel **Adicionar aplicativo**, confirme se os detalhes do seu aplicativo estão corretos.
2. Escolha **Adicionar** para carregar o aplicativo no Intune.

O aplicativo que você criou aparece na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

> [!NOTE]
> Se o arquivo *.pkg* contiver vários aplicativos ou instaladores de aplicativos, o Microsoft Intune somente informará que o *aplicativo* foi instalado com êxito quando todos os aplicativos instalados forem detectados no dispositivo.

## <a name="step-5---update-a-line-of-business-app"></a>Etapa 5 – Atualizar um aplicativo de linha de negócios

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Para o serviço Intune para implantar com êxito um novo arquivo *.pkg* para o dispositivo, você deve incrementar o pacote `version` e a cadeia de caracteres `CFBundleVersion` no arquivo *packageinfo* no seu pacote *.pkg*.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou é exibido na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Para obter mais informações, consulte [Como monitorar atribuições e informações de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Para obter mais informações, consulte a [Visão geral do dispositivo e ciclos de vida do aplicativo](introduction-device-app-lifecycles.md)
