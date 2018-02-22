---
title: "Como adicionar aplicativos de linha de negócios do Android ao Intune"
titlesuffix: Azure portal
description: "Saiba como adicionar aplicativos de linha de negócios do Android ao Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b63ab13dcedaa4787e9bae12ce713899b9c3e334
ms.sourcegitcommit: 0a5f424a8f683daa919b13b5c363173040d561c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/13/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Como adicionar aplicativos de linha de negócios (LOB) do Android no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Etapa 1 – Especificar os arquivos de instalação de software

1. Entre no Portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.

## <a name="step-2---configure-the-app-package-file"></a>Etapa 2 - configurar o arquivo de pacote de aplicativos

1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha do arquivo **Pacote de aplicativos**, escolha o botão Procurar e selecione um arquivo de instalação do Android com a extensão **.apk**.
3. Quando terminar, escolha **OK**.


## <a name="step-3---configure-app-information"></a>Etapa 3 - configurar informações do aplicativo

1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha **Informações do aplicativo**, adicione os detalhes para seu aplicativo. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
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

1. Na folha **Adicionar aplicativo**, verifique os detalhes do aplicativo.
2. Escolha **Adicionar** para carregar o aplicativo no Intune.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

## <a name="step-5---update-a-line-of-business-app"></a>Etapa 5 – Atualizar um aplicativo de linha de negócios

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note] 
> Para que o serviço do Intune implante com êxito um novo arquivo APK para o dispositivo, incremente a cadeia de caracteres android:versionCode no arquivo AndroidManifest.xml em seu pacote de APK.

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou é exibido na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Para obter mais informações, consulte [Como monitorar atribuições e informações de aplicativo](apps-monitor.md).

Saiba mais sobre o contexto do seu aplicativo no Intune. Para obter mais informações, consulte a [Visão geral do dispositivo e ciclos de vida do aplicativo](introduction-device-app-lifecycles.md)
