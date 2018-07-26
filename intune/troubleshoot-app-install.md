---
title: Solucionar problemas de instalação do aplicativo
titlesuffix: Microsoft Intune
description: Use o painel de solução de problemas do Microsoft Intune para resolver problemas com a instalação do aplicativo.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: c1c2a37103f8fedc09a70b4387aae3f472dfb636
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138672"
---
# <a name="troubleshoot-app-installation-issues"></a>Solucionar problemas de instalação do aplicativo

Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. O Microsoft Intune fornece detalhes sobre falha na instalação do aplicativo, com os quais os operadores de suporte técnico e os administradores dessa plataforma podem exibir informações do aplicativo para atender às solicitações de ajuda dos usuários. O painel de solução de problemas do Intune fornece os detalhes da falha, inclusive sobre aplicativos gerenciados no dispositivo do usuário. Fornecemos detalhes sobre o ciclo de vida de ponta a ponta de um aplicativo em cada dispositivo individual, no painel **Aplicativos Gerenciados**. Você pode exibir problemas de instalação, por exemplo, quando o aplicativo for criado, modificado, direcionado e baixado em um dispositivo. 

## <a name="to-review-app-troubleshooting-details"></a>Para examinar os detalhes da solução de problemas do aplicativo

O Intune fornece detalhes da solução de problemas do aplicativo, de acordo com os aplicativos instalados no dispositivo de um usuário específico.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Solucionar problemas**.
4. Clique em **Selecionar usuário** para selecionar um usuário cujos problemas serão solucionados. O painel **Selecionar usuário** será exibido.
5. Selecione um usuário digitando o nome ou o endereço de email. Clique em **Selecionar**, na parte inferior do painel. As informações da solução de problemas do usuário são exibidas no painel **Solucionar problemas**. 
6. Selecione na lista **Dispositivos** o dispositivo para o qual você deseja solucionar problemas.
    ![Painel Solução de problemas do Microsoft Intune](media/troubleshoot-app-install-01.png)
7. Selecione **Aplicativos Gerenciados**, no painel do dispositivo selecionado. O programa exibirá os aplicativos gerenciados.
    ![Detalhes de um dispositivo específico gerenciado pelo Intune.](media/troubleshoot-app-install-02.png)
8. Selecione um aplicativo na lista, cujo **Status de Instalação** indica uma falha.
    ![Aplicativo selecionado que mostra os detalhes da falha de instalação.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > O mesmo aplicativo pode ser atribuído a vários grupos, mas com diferentes ações previstas (finalidades) para o aplicativo. Por exemplo, uma tentativa resolvida de um aplicativo mostrará **excluído**, se o aplicativo for excluído por um usuário, durante a respectiva atribuição. Para saber mais, confira [Como são resolvidos os conflitos entre as finalidades do aplicativo](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > No momento, o Intune não filtra aplicativos com base na plataforma do SO.

Os detalhes do erro de instalação do aplicativo indicarão o problema. Use esses detalhes para determinar a ação adequada à resolução do problema. Para saber mais sobre como solucionar problemas de instalação do aplicativo, confira [Códigos de erro da solução de problemas de instalação de aplicativos](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> Você também pode acessar o painel **solução de problemas** apontando o navegador para: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre a solução de problemas do Intune, confira [Usar o portal de solução de problemas para ajudar os usuários na empresa](help-desk-operators.md). 
- Saiba mais sobre os problemas conhecidos do Microsoft Intune. Para obter mais informações, consulte [Problemas conhecidos no Microsoft Intune](known-issues.md).
- Precisa de mais ajuda? Veja [Como obter suporte para o Microsoft Intune](get-support.md).
