---
title: Instalar o Office 365 em dispositivos macOS usando o Microsoft Intune
titlesuffix: ''
description: Saiba como usar o Microsoft Intune para instalar aplicativos do Office 365 em dispositivos macOS.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9fd647add814d9cb188c90ef2d2b85ce89a0459b
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2018
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Atribuir o Office 365 para dispositivos macOS com o Microsoft Intune

O tipo de *Aplicativo da Store* facilita a atribuição de aplicativos do Office 365 para dispositivos macOS. Esse tipo de aplicativo permite que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Para ajudar a manter os aplicativos seguros e atualizados, esses aplicativos são fornecidos com o MAU (Microsoft AutoUpdate). Os aplicativos que você quiser serão exibidos como um aplicativo na lista de aplicativos no console do Intune.


## <a name="before-you-start"></a>Antes de começar

Antes de começar a adicionar o Office 365 a dispositivos macOS, compreenda estes detalhes:

- Os dispositivos nos quais você implanta esses aplicativos deverão estar executando o macOS 10.10 ou posterior.
- O Intune só oferece suporte à adição de aplicativos do Office incluídos com o pacote Office 2016 para Mac.
- Se algum aplicativo do Office estiver aberto quando o Intune instalar o pacote de aplicativos, os usuários poderão perder dados de arquivos não salvos.

## <a name="create-and-configure-the-app-suite"></a>Criar e configurar o pacote de aplicativos

Adicione o Office 365 desde o painel **Aplicativos**.
1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. No painel de carga de trabalho **Aplicativos móveis**, em **Gerenciar**, selecione **Aplicativos**. 
5. Selecione **Adicionar**.
6. Na lista **Tipo de aplicativo**, no grupo **Office 365 Suite**, selecione **macOS**.
7. Para saber mais sobre o pacote de aplicativos, selecione **Informações do Pacote de Aplicativos**.  
    Essas informações ajudam a identificar o pacote de aplicativos no Intune, e ajudam os usuários a encontrar o pacote de aplicativos no portal da empresa.
8. Digite as seguintes informações:
    - **Nome do Pacote**: insira o nome do pacote de aplicativos da forma como ele é exibido no portal da empresa. Verifique se todos os nomes de pacotes usados são exclusivos. Se o mesmo nome de pacote de aplicativos for usado duas vezes, apenas um dos aplicativos será exibido aos usuários no Portal da Empresa.
    - **Descrição do Pacote**: insira uma descrição para o pacote de aplicativos.
    - **Editor**: a Microsoft aparece como o editor.
    - **Categoria**: selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. Essa configuração facilita para os usuários localizarem o pacote de aplicativos enquanto navegam pelo Portal da Empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: selecione esta opção para exibir o pacote de aplicativos de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: a Microsoft aparece como o desenvolvedor.
    - **Proprietário**: a Microsoft aparece como o proprietário.
    - **Observações**: como opção, insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: o logotipo do Office 365 é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
9. Selecione **OK**.
10. No painel **Adicionar aplicativo**, selecione **Adicionar**.  
    O pacote é exibido na lista de aplicativos como uma única entrada.

## <a name="configure-app-assignments"></a>Configurar as atribuições de aplicativo

Nesta etapa, configure as atribuições do pacote de aplicativos. 

1. Na lista de aplicativos, selecione o pacote de aplicativos **Office 365** para exibir o painel de visão geral do **Office 365**.
2. No painel do **Office 365**, selecione **Atribuições**.
3. Para adicionar um grupo que usará o pacote de aplicativos, selecione **Adicionar grupo**.  
    O painel **Adicionar grupo** é exibido.
4. Defina o **Tipo de atribuição** como **Obrigatório**.
5. Atribua o pacote aos grupos que você selecionar. Para saber mais, confira [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Você não pode desinstalar o pacote de aplicativos do Office 365 por meio do Intune.

5. No painel **Atribuir**, selecione **OK**.
6. No painel **Adicionar grupo**, selecione **OK**.
7. Selecione **Salvar** para confirmar suas atribuições.

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como adicionar aplicativos do Office 365 para dispositivos com Windows 10, consulte [Atribuir aplicativos do Office 365 ProPlus 2016 para dispositivos com Windows 10 com o Microsoft Intune](apps-add-office365.md).
- Para saber mais sobre como incluir e excluir atribuições de aplicativos de grupos de usuários, consulte [Incluir e excluir atribuições de aplicativos](apps-inc-exl-assignments.md).
