---
title: "Distribuição de política | Microsoft Intune"
description: "Recomendações específicas para uma distribuição em fases de política no Microsoft Intune."
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: bab43006d4f142f34ecbb69487acb8b63151ee61


---

# Distribuição de política
Este tópico fornece recomendações específicas para uma distribuição em fases de políticas no Microsoft Intune. Essa abordagem se aplica às primeiras políticas aplicadas em uma nova implantação do Intune ou às políticas adicionadas a uma implantação existente.

Para obter informações gerais sobre as fases de distribuição, consulte [Rollout phases for Microsoft Intune deployment](rollout-phases-for-microsoft-intune-deployment.md) (Fases da distribuição para a implantação do Microsoft Intune).

### Fases de distribuição de política
As fases de distribuição de política são:

-   Escopo do projeto

-   Prova de conceito

-   Piloto

-   Distribuição na empresa

-   Operações e manutenção

## Escopo do projeto
Defina o escopo da sua implantação de política do Intune:

-   Para uma nova implementação, será necessário definir todos os comportamentos de dispositivo desejados e quais requisitos de segurança você deseja criar com seu conjunto de política.

-   Decida quais usuários e dispositivos você deseja afetar com essas políticas.

-   Projete seus grupos de usuários e de dispositivos para que você possa aplicar as novas políticas adequadamente.

-   Determine se há restrições ou requisitos associados a cada sistema operacional que afetam as intenções da política.

-   Considere as especificações de design de política, tal como o tipo de política e o modelo a ser usado.

-   Se estiver iniciando o primeiro conjunto de políticas ou adicionando novas políticas a um conjunto de políticas existente, considere como as diferentes políticas interagem e qual será o provável comportamento do dispositivo. Problemas com interações de política e conflitos podem ser descobertos na fase Piloto, mas capturar conflitos de política no início do planejamento simplificará a execução do piloto.

## Prova de conceito
Na fase de Prova de conceito, teste a implantação da política em um ambiente de laboratório em dispositivos e usuários que você configurou estritamente para fins de teste.

-   Faça com que o suporte técnico participe desta fase para saber quais problemas podem surgir durante a implantação do piloto e da produção. As informações de solução de problemas estão disponíveis em [Solucionar problemas de políticas no Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).

-   Neste ponto do processo, você deve desenvolver planos de comunicação para usuários piloto e de produção. No mínimo, o plano deve incluir quais comportamentos do aplicativo mudarão e quando, a finalidade de negócio para a mudança e o que fazer se os usuários ou a equipe de TI encontrar problemas, tanto informações de autoatendimento quanto como entrar em contato com o suporte técnico.

## Piloto
Durante o piloto, você implantará a política para um pequeno grupo de usuários e dispositivos de teste. Há considerações específicas para a política de piloto no Intune:

-   O grupo de teste deve ser representativo em relação ao grupo ao qual a política será aplicada para a distribuição da produção.

-   Treine o suporte técnico sobre as mudanças na política e garanta que eles estejam preparados para ajudar os usuários no grupo de teste.

-   Ative seu plano de comunicação do usuário do piloto.

-   O piloto primeiro pode ser conduzido no modo isolado, no qual o dispositivo não está sujeito a outras políticas que podem causar conflitos e comportamento indesejado.

-   O teste final deve considerar a nova política e as políticas existentes que serão aplicadas ao mesmo dispositivo.

## Distribuição na empresa

-   Com base nos resultados do piloto, ajuste sua política planejada para corrigir conflitos de política e comportamento imprevisto.

-   Notifique o suporte técnico do cronograma de distribuição do aplicativo. Tenha mecanismos em vigor para responder às solicitações de ajuda e para ajustar a distribuição conforme necessário.

-   Esteja preparado para solucionar problemas da política caso surjam.

-   Ative seu plano de comunicação do usuário de produção.

-   Aplique as políticas de forma incremental aos grupos adicionais, monitorando o estado da política para os dispositivos afetados e acompanhando as solicitações do suporte técnico que podem estar relacionadas à nova política.

## Operações e manutenção
**Operações:** monitore o console do Intune para ver alertas e problemas do dispositivo ou do usuário, e verifique se as políticas estão funcionando de acordo com seu design.

**Suporte técnico:** verifique se o suporte técnico está ciente de quaisquer alterações nas políticas que afetam a experiência do usuário, pois elas podem resultar em solicitações de suporte.


### Consulte também
[Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Solução de problemas com políticas no Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)



<!--HONumber=Jul16_HO3-->


