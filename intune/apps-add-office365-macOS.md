---
title: Instalar o Office 365 para dispositivos com macOS usando o Intune
titlesuffix: Azure portal
description: "Saiba como usar o Intune para facilitar a instalação de aplicativos do Office 365 em dispositivos com macOS."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1573a6a2ca78489df46c9e08ebbfe9a16b0731c7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Como atribuir o Office 365 para dispositivos com macOS com o Microsoft Intune

Esse tipo de aplicativo facilita a atribuição de aplicativos do Office 365 para dispositivos com macOS. Esse novo tipo de aplicativo permite que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Esses aplicativos também são fornecidos com o MAU (Microsoft AutoUpdate), para ajudar a manter os aplicativos seguros e atualizados. Os aplicativos que você desejar aparecerão como um aplicativo na lista de aplicativos no console do Intune.


## <a name="before-you-start"></a>Antes de começar

- Os dispositivos nos quais você implanta esses aplicativos deverão estar executando o macOS 10.10 ou posterior.
- O Intune só oferece suporte à adição de aplicativos do Office incluídos com o Office 2016 para Mac.
- Se algum aplicativo do Office estiver aberto quando o Intune instalar o pacote de aplicativos, os usuários finais poderão perder dados de arquivos não salvos.


## <a name="get-started"></a>Introdução
Adicione o Office 365 usando a folha **Aplicativos**.
1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Aplicativos móveis**.
4.  Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** no grupo **Gerenciar**. Escolha **Adicionar**.
5.  Na folha **Adicionar Aplicativo**, escolha **Office 365** > **macOS**.
6.  Selecione **Adicionar**.

## <a name="configure-the-app-suite"></a>Configurar o pacote de aplicativos

Forneça informações sobre o pacote de aplicativos. Essas informações ajudam a identificá-lo no Intune, além de ajudar os usuários a encontrá-lo no aplicativo Portal da Empresa.

1.  Na folha **Adicionar Aplicativo**, escolha **Informações do Pacote de Aplicativos**.
2.  Especifique as seguintes informações:
    - **Nome do Pacote** – insira o nome do pacote de aplicativos como ele é exibido no Portal da Empresa. Verifique se todos os nomes de pacotes de aplicativos usados são exclusivos. Se o mesmo nome de pacote de aplicativos for usado duas vezes, apenas um dos aplicativos será exibido aos usuários no Portal da Empresa.
    - **Descrição do Pacote** – insira uma descrição para o pacote de aplicativos.
    - **Publicador** – a Microsoft aparece como o publicador.
    - **Categoria** – como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do pacote de aplicativos pelos usuários quando navegam pelo Portal da Empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa** – isso exibirá o pacote de aplicativos de forma proeminente na página principal do Portal da Empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – a Microsoft aparece como o desenvolvedor.
    - **Proprietário** – a Microsoft aparece como o proprietário.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Carregar Ícone** – carregue um ícone que será exibido com o aplicativo quando os usuários navegarem pelo Portal da Empresa.
3.  Selecione **OK**. O pacote é exibido na lista de aplicativos como uma única entrada.

## <a name="configure-app-assignments"></a>Configurar as atribuições de aplicativo

Nesta etapa, configure as atribuições do pacote de aplicativos. Observe que o tipo de aplicativo disponível chegará em breve.

1.  Selecione o pacote de aplicativos na lista de aplicativos e selecione **Atribuições**.
2.  Escolha **Selecionar grupos**.
3.  Atribua o pacote aos grupos que você escolher. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](/intune/apps-deploy).
4.  Para cada grupo, selecione **Exigir Instalação**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Selecione **Salvar** para confirmar suas atribuições.

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como adicionar aplicativos do Office 365 para dispositivos com Windows 10, consulte [Como atribuir aplicativos do Office 365 ProPlus 2016 para dispositivos com Windows 10 com o Microsoft Intune](/intune/apps-add-office365).
