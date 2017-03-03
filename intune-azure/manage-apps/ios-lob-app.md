---
title: "Como adicionar aplicativos de linha de negócios iOS ao Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda como adicionar aplicativos de linha de negócios iOS ao Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 6d41adabfab178daa7f6fce3d86bc8216bf4ab29
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a>Como adicionar aplicativos de linha de negócios (LOB) do iOS para o Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Etapa 1 – Especificar os arquivos de instalação de software

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha do Intune, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha Gerenciar > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Arquivo de Instalação de Software**.
7. Na folha **Selecionar arquivo de instalação**, clique no botão Procurar e navegue até o arquivo de configuração de aplicativo do iOS (com a extensão .ipa) e clique em **OK**.

## <a name="step-2---configure-app-information"></a>Etapa 2 – Configurar informações de aplicativo

1. Na folha **Editar Aplicativo**, configure as seguintes informações. Ao terminar, clique em **Adicionar**. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
    - **Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição do Aplicativo** – Insira uma descrição para o aplicativo. Isso será exibido para os usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Tipo de Dispositivo Aplicável** – Selecione se esse aplicativo puder ser instalado em iPads, iPhones ou iPods compatíveis.
    - **Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Categoria** (opcional) – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Carregar Ícone** – Carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
2. Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](/intune-azure/manage-apps/deploy-apps).
