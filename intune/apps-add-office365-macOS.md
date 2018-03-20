---
title: Instalar o Office 365 em dispositivos macOS usando o Microsoft Intune
titlesuffix: 
description: Saiba como usar o Microsoft Intune para instalar aplicativos do Office 365 em dispositivos macOS.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Como atribuir o Office 365 para dispositivos com macOS com o Microsoft Intune

O tipo de **Aplicativo da Store** facilita a atribuição de aplicativos do Office 365 para dispositivos macOS. Esse tipo de aplicativo permite que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Esses aplicativos também são fornecidos com o MAU (Microsoft AutoUpdate), para ajudar a manter os aplicativos seguros e atualizados. Os aplicativos que você desejar aparecerão como um aplicativo na lista de aplicativos no console do Intune.


## <a name="before-you-start"></a>Antes de começar

Antes de começar a adicionar o Office 365 ao dispositivos macOS, você precisa compreender os detalhes a seguir:

- Os dispositivos nos quais você implanta esses aplicativos deverão estar executando o macOS 10.10 ou posterior.
- O Intune só oferece suporte à adição de aplicativos do Office incluídos com o Office 2016 para Mac.
- Se algum aplicativo do Office estiver aberto quando o Intune instalar o pacote de aplicativos, os usuários finais poderão perder dados de arquivos não salvos.

## <a name="create-and-configure-the-app-suite"></a>Criar e configurar o pacote de aplicativos

Adicione o Office 365 usando a folha **Aplicativos**.
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Escolha **Aplicativos móveis** na folha **Intune**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** na seção **Gerenciar**. 
5. Escolha **Adicionar** para exibir a folha **Adicionar aplicativo**.
6. Na lista **Tipo de aplicativo**, selecione **macOS** no grupo **Office 365 Suite**.
7. Selecione **Informações de pacote de aplicativos** para fornecer informações sobre o pacote de aplicativos. Essas informações ajudam a identificar o pacote de aplicativos no Intune, além de ajudar os usuários a encontrá-lo no aplicativo Portal da Empresa.
8.  Especifique as seguintes informações:
    - **Nome do Pacote** – insira o nome do pacote de aplicativos como ele é exibido no Portal da Empresa. Verifique se todos os nomes de pacotes de aplicativos usados são exclusivos. Se o mesmo nome de pacote de aplicativos for usado duas vezes, apenas um dos aplicativos será exibido aos usuários no Portal da Empresa.
    - **Descrição do Pacote** – insira uma descrição para o pacote de aplicativos.
    - **Publicador** – a Microsoft aparece como o publicador.
    - **Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. Essa configuração facilita para os usuários localizarem o pacote de aplicativos enquanto navegam pelo Portal da Empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa** – Essa configuração exibirá pacote de aplicativos de forma proeminente na página principal do Portal da Empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** (opcional) – insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL privada** (opcional) – insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – a Microsoft aparece como o desenvolvedor.
    - **Proprietário** – a Microsoft aparece como o proprietário.
    - **Observações** (opcional) – insira as observações que você deseja associar a este aplicativo.
    - **Logotipo** – O logotipo do Office 365 é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
9.  Clique em **OK** na folha **Informações do aplicativo**.
10. Clique em **Adicionar** na folha **Adicionar aplicativo**.
    O pacote é exibido na lista de aplicativos como uma única entrada.

## <a name="configure-app-assignments"></a>Configurar as atribuições de aplicativo

Nesta etapa, configure as atribuições do pacote de aplicativos. 

1. Selecione o pacote de aplicativos **Office 365** na lista de aplicativos para exibir a folha de visão geral do **Office 365**.
2. Clique em **Atribuições** na folha **Office 365**.
3. Clique em **Adicionar grupo** para adicionar um grupo para usar o pacote de aplicativo. A folha **Adicionar grupo** é exibida.
3. Defina o **Tipo de atribuição** como **Necessário**.
4. Atribua o pacote aos grupos que você escolher. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Para os grupos que você exige o pacote de aplicativos do Office 365, não será possível desinstalá-lo por meio do Microsoft Intune.

5. Selecione **OK** na folha **Atribuir**.
6. Selecione **OK** na folha **Adicionar grupo**.
7. Selecione **Salvar** para confirmar suas atribuições.

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como adicionar aplicativos do Office 365 para dispositivos com Windows 10, consulte [Como atribuir aplicativos do Office 365 ProPlus 2016 para dispositivos com Windows 10 com o Microsoft Intune](apps-add-office365.md).
- Para saber mais sobre como incluir e excluir atribuições de aplicativos para grupos de usuários, consulte [Incluir e excluir atribuições de aplicativos](apps-inc-exl-assignments.md).
