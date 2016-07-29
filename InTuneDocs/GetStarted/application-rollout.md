---
title: "Distribuição de aplicativos | Microsoft Intune"
description: "Recomendações específicas para uma distribuição em fases de aplicativos no Microsoft Intune."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 83306c0847eaf98d499e649308669a33306aa97e


---

# Distribuição de aplicativos
Este tópico fornece recomendações específicas para uma distribuição em fases de aplicativos no Microsoft Intune. Para obter informações gerais sobre as fases de distribuição, consulte [Rollout phases for Microsoft Intune deployment](rollout-phases-for-microsoft-intune-deployment.md) (Fases da distribuição para a implantação do Microsoft Intune).

### Fases de distribuição do aplicativo
As fases de distribuição do aplicativo são:

-   Escopo do projeto

-   Prova de conceito

-   Piloto

-   Distribuição na empresa

-   Operações e manutenção

## Escopo do projeto
Considere o seguinte:

-   A tarefa de usuário que o aplicativo se destina a habilitar.

-   A adequação do aplicativo para os usuários e seus dispositivos (todos os sistemas operacionais que podem ser usados).

-   Verifique se o instalador do aplicativo escolhido tem suporte pela distribuição de aplicativos do Intune, conforme descrito em [Adicionar aplicativos com o Microsoft Intune](/intune/deploy-use/add-apps).

-   Garanta que os pré-requisitos da distribuição de aplicativo estejam instalados. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Determine se o Intune dá suporte ao tipo de aplicativo.

-   Verifique se você tem espaço de armazenamento de nuvem suficiente disponível para carregar o aplicativo. São fornecidas instruções para adquirir armazenamento adicional em [Adicionar aplicativos com o Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> Você pode baixar este [modelo de planejamento para aplicativos móveis](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59) para auxiliar no processo de distribuição.

## Prova de conceito
Na fase de Prova de conceito, teste a implantação do aplicativo em um ambiente de laboratório em dispositivos e usuários que você configurou estritamente para fins de teste.

-   Faça com que o suporte técnico participe desta fase para saber quais problemas podem surgir durante a implantação do piloto e da produção. As informações de solução de problemas estão disponíveis em [Troubleshoot app deployment problems in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune) (Solucionar problemas de implantação de aplicativos no Microsoft Intune).

-   Neste ponto do processo, você deve desenvolver planos de comunicação para usuários piloto e de produção. No mínimo, o plano deve incluir qual aplicativo está sendo implantado, como e quando os usuários o obterão, a finalidade comercial da implantação e o que fazer se encontrem problemas, tanto informações de autoajuda e quanto como entrar em contato com o suporte técnico.

## Piloto
Durante o piloto, você implantará o aplicativo para um pequeno grupo de usuários e dispositivos de teste. Considere o seguinte:

-   Certifique-se de que o grupo de teste seja representativo dos usuários e dispositivos que usarão o aplicativo após a distribuição da produção.

-   Treine o suporte técnico sobre a implantação do aplicativo e garanta que estejam preparados para ajudar os usuários no grupo de teste.

-   Escolha os usuários de teste que submeterão o aplicativo ao uso típico e relatarão problemas de forma confiável para os administradores do piloto.

-   Ative seu plano de comunicação do usuário do piloto.

## Distribuição na empresa

-   Use os resultados do piloto para ajustar sua distribuição na empresa.

-   Notifique o suporte técnico do cronograma de distribuição do aplicativo. Tenha mecanismos em vigor para responder às solicitações de ajuda e ajustar a distribuição conforme necessário.

-   Esteja preparado para solucionar problemas da implantação se surgirem problemas.

-   Ative seu plano de comunicação do usuário de produção.

-   Use uma abordagem em fases para implantar o aplicativo, adicionando grupos de forma incremental para garantir que a distribuição esteja progredindo sem problemas.

## Operações e manutenção
**Operações:** monitore seu console do Intune para alertas, problemas de dispositivo ou usuário e para garantir que a distribuição de aplicativos está funcionando de acordo com seu design.

**Suporte técnico:** garanta que o suporte técnico esteja ciente das alterações na disponibilidade do aplicativo que podem resultar em solicitações de suporte.

### Consulte também
[Implantar aplicativos](/intune/deploy-use/deploy-apps)

[Solucionar problemas de implantação de aplicativo no Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Jul16_HO4-->


