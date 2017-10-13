---
title: "Defesa contra Ameaças Móveis com o Intune"
titleSuffix: Azure portal
description: Proteger o acesso a recursos da empresa com base nos riscos do dispositivo
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f928b214642c5954561f2c56b30b71b36ecd57eb
ms.sourcegitcommit: 012f262660fa9fb321ac3470f5dba165b8e5256a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integração da Defesa contra Ameaças Móveis com o Intune


Os conectores de Defesa Contra Ameaças Móveis do Intune permitem que você utilize o fornecedor de Defesa Contra Ameaças Móveis escolhido como uma fonte de informações para suas políticas de conformidade e regras de acesso condicional. Isso permite que os administradores de TI adicionem uma camada de proteção aos seus recursos corporativos como Exchange e Sharepoint, especificamente de dispositivos móveis comprometidos.

## <a name="what-problem-does-this-solve"></a>Que problema isso resolve?

As empresas precisam proteger dados confidenciais contra ameaças emergentes, incluindo ameaças físicas, baseadas em aplicativo e em rede, bem como vulnerabilidades do sistema operacional.

Historicamente, as empresas têm sido proativas ao proteger computadores contra ataques, enquanto os dispositivos móveis ficam sem monitoramento e sem proteção. Plataformas móveis têm proteção interna, como isolamento de aplicativo e lojas de aplicativos de consumidor verificadas, mas permanecerão vulneráveis a ataques sofisticados. Hoje, um número maior de funcionários usa dispositivos para o trabalho e precisam ter acesso a informações confidenciais. Os dispositivos precisam ser protegidos contra ataques cada vez mais sofisticados.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Como os conectores de Defesa Contra Ameaças Móveis do Intune funciona?

O conector protege os recursos da empresa criando um canal de comunicação entre o Intune e seu fornecedor de Defesa Contra Ameaças Móveis escolhido. Os parceiros de Defesa Contra Ameaças Móveis do Intune oferecem aplicativos intuitivos e fáceis de implantar para dispositivos móveis que ativamente examinam e analisam as informações sobre ameaças para compartilhar com o Intune, para fins de relatório ou imposição. 

Por exemplo, se um aplicativo de Defesa Contra Ameaças Móveis relata para o fornecedor de Defesa Contra Ameaças Móveis que um telefone em sua rede atualmente está conectado a uma rede vulnerável a ataques Man in the Middle, essas informações são compartilhadas e categorizadas em um nível de risco adequado (baixo/médio/alto), que pode então ser comparado às tolerâncias de nível de risco configuradas no Intune para determinar se o acesso a determinados recursos de sua escolha deve ser revogado enquanto o dispositivo está comprometido.

## <a name="sample-scenarios"></a>Cenários de exemplo

Quando um dispositivo é considerado infectado pela solução de Defesa Contra Ameaças Móveis:

![Dispositivo infectado na Defesa contra Ameaças Móveis](./media/MTD-image-1.png)

O acesso é concedido quando o dispositivo é corrigido:

![Acesso concedido na Defesa contra Ameaças Móveis](./media/MTD-image-2.png)

> [!NOTE] 
> O uso de vários fornecedores de Defesa contra ameaças de móveis com o Intune não tem suporte. Ter diversas ferramentas de MTD habilitadas fará com que todos os aplicativos MTD sejam instalados e verifiquem os dispositivos em busca de ameaças.

## <a name="mobile-threat-defense-partners"></a>Parceiros de Defesa Contra Ameaças Móveis

Saiba como proteger o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo com:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
