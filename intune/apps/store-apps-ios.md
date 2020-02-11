---
title: Adicionar aplicativos da loja do iOS ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos da iOS Store ao Microsoft Intune. Você poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2daa7428cf8677f9e1a2b11db2b3ce65e2df8bc4
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754993"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da loja do iOS ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use as informações deste artigo para ajudá-lo a adicionar aplicativos da iOS Store ao Microsoft Intune. Aplicativos da loja do iOS são aplicativos instalados pelo Intune no dispositivo de um usuário. Um usuário faz parte da força de trabalho da sua empresa. Os aplicativos da iOS Store são atualizados automaticamente.

>[!NOTE]
>Embora os usuários de dispositivos iOS possam remover alguns aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários excluírem esses aplicativos, eles deverão acessar a App Store e reinstalá-los manualmente.

## <a name="before-you-start"></a>Antes de começar

Você poderá atribuir aplicativos usando esse método apenas se eles forem gratuitos na App Store. Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).

>[!NOTE]
>Ao trabalhar com o Microsoft Intune, recomendamos que você use o Microsoft Edge ou o Google Chrome.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de **Aplicativo da loja** disponíveis, selecione **Aplicativo da iOS Store**.
4. Clique em **Selecionar**.<br>
   As etapas de **Adicionar aplicativo** são exibidas.
5. Selecione **Pesquisar na App Store**.
6. No painel **Pesquisar na App Store**, escolha a localidade do país/região da App Store.
7. Na caixa **Pesquisar**, digite o nome (ou parte do nome) do aplicativo.  
    O Intune pesquisará na loja e retornará uma lista com resultados relevantes.
8. Na lista de resultados, selecione o aplicativo desejado e, em seguida, selecione **Selecionar**.<br>

   A página **Informações do aplicativo** será exibida no painel **Adicionar aplicativo**. Quando possível, as informações do aplicativo serão adicionadas com base no aplicativo selecionado na loja.

9. Na página **Informações do aplicativo**, adicione os detalhes do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome**: Insira o nome do aplicativo como ele será exibido no Portal da Empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: Digite a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Sistema operacional mínimo**: Na lista, escolha a versão mais recente do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Tipo de dispositivo aplicável**: Na lista, selecione os dispositivos que são usados pelo aplicativo.
    - **Categoria**: Como opção, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Mostrar como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, insira o nome do desenvolvedor do aplicativo. Este campo estará visível somente para administradores, e não para os usuários.
    - **Proprietários**: Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*. Este campo estará visível somente para administradores, e não para os usuários.
    - **Observações**: Opcionalmente, insira as observações que você deseja associar a esse aplicativo. Esse campo só é visível para administradores, e não para usuários finais.
    - **Logotipo**: Opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
10. Clique em **Avançar** para exibir a página **Marcas de escopo**.
11. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. Confira mais informações em [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).
12. Clique em **Avançar** para exibir a página **Atribuições**.
13. Selecione as atribuições de grupo para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md). 
14. Clique em **Avançar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
15. Ao terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

A folha **Visão geral** do aplicativo criado é exibida.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
