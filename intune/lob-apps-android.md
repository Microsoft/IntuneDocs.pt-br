---
title: "Como adicionar aplicativos de linha de negócios do Android ao Microsoft Intune"
titlesuffix: 
description: "Saiba como adicionar aplicativos de LOB (linha de negócios) do Android ao Microsoft Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3f336fb295dba396dad3a399aafc17435edb70b3
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Como adicionar aplicativos de linha de negócios (LOB) do Android no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Um aplicativo de LOB (linha de negócios) é um aplicativo que pode ser adicionado ao Intune de um arquivo de instalação de aplicativo. Normalmente, esses tipos de aplicativos são escritos internamente. O Intune instala o aplicativo de LOB no dispositivo do usuário. 

> [!Note]
> Para obter mais informações sobre aplicativos de LOB (linha de negócios) na Google Play for Work store, consulte [Trabalhando com um aplicativo de linha de negócios do Google Play for Work store](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store). 

## <a name="step-1---specify-the-software-setup-file"></a>Etapa 1 – Especificar os arquivos de instalação de software

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. No painel **Adicionar aplicativo**, escolha **Aplicativo de linha de negócios**.

## <a name="step-2---configure-the-app-package-file"></a>Etapa 2 - configurar o arquivo de pacote de aplicativos

1. No painel **Adicionar aplicativo**, escolha o **Arquivo do pacote do aplicativo**.
2. No painel **Arquivo do pacote do aplicativo**, escolha o botão Procurar e selecione um arquivo de instalação do Android com a extensão **.apk**.
3. Quando terminar, escolha **OK**.


## <a name="step-3---configure-app-information"></a>Etapa 3 - configurar informações do aplicativo

1. No painel **Adicionar aplicativo**, escolha o **Arquivo do pacote do aplicativo**.
2. No painel **Informações do aplicativo**, adicione os detalhes do seu aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome** – insira o nome do aplicativo que será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição** -insira uma descrição para o aplicativo que será exibida aos usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Ignorar versão do aplicativo** – Defina como **Sim** se o aplicativo for atualizado automaticamente pelo desenvolvedor do aplicativo.
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

1. No painel **Adicionar aplicativo**, verifique os detalhes do aplicativo.
2. Escolha **Adicionar** para carregar o aplicativo no Intune.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

## <a name="step-5---update-a-line-of-business-app"></a>Etapa 5 – Atualizar um aplicativo de linha de negócios

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> Para que o serviço do Intune implante com êxito um novo arquivo APK para o dispositivo, incremente a cadeia de caracteres android:versionCode no arquivo AndroidManifest.xml em seu pacote de APK.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou é exibido na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Para obter mais informações, consulte [Como monitorar atribuições e informações de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Para obter mais informações, consulte a [Visão geral do dispositivo e ciclos de vida do aplicativo](introduction-device-app-lifecycles.md)
