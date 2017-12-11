---
title: "Defesa contra Ameaças Móveis com o Intune"
titleSuffix: Azure portal
description: Proteger o acesso a recursos da empresa com base nos riscos do dispositivo
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16402b30895e61d9a4ff8393fd4d4c6efa061e9e
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integração da Defesa contra Ameaças Móveis com o Intune


Os conectores da Defesa contra Ameaças Móveis do Intune permitem que você aproveite seu fornecedor de Defesa contra Ameaças Móveis escolhido como uma fonte de informações para suas políticas de conformidade e regras de acesso condicional. Isso permite que os administradores de TI adicionem uma camada de proteção aos seus recursos corporativos como Exchange e Sharepoint, especificamente de dispositivos móveis comprometidos.

## <a name="what-problem-does-this-solve"></a>Qual problema isso resolve?

As empresas precisam proteger dados confidenciais contra ameaças emergentes, incluindo ameaças físicas, baseadas em aplicativo e em rede, bem como vulnerabilidades do sistema operacional.

Historicamente, as empresas têm sido proativas ao proteger computadores contra ataques, enquanto os dispositivos móveis ficam sem monitoramento e proteção. Plataformas móveis têm proteção interna, como isolamento de aplicativo e lojas de aplicativos de consumidor verificadas, mas permanecerão vulneráveis a ataques sofisticados. Hoje, um número maior de funcionários usa dispositivos para o trabalho e precisam ter acesso a informações confidenciais. Os dispositivos precisam ser protegidos contra ataques cada vez mais sofisticados.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Como funcionam os conectores da Defesa contra Ameaças Móveis do Intune?

O conector protege recursos da empresa criando um canal de comunicação entre o Intune e o fornecedor de Defesa contra Ameaças Móveis escolhido. Parceiros de Defesa contra Ameaças Móveis do Intune oferecem aplicativos intuitivos e fáceis de implantar para dispositivos móveis que examinam e analisam ativamente informações sobre ameaças para compartilhar com o Intune, para fins de relatórios ou imposição. 

Por exemplo, se um aplicativo de Defesa contra Ameaças Móveis conectado informar ao fornecedor de Defesa contra Ameaças Móveis que um telefone em sua rede está conectado a uma rede vulnerável aos ataques de intermediários, essas informações serão compartilhadas e categorizadas em um nível apropriado de risco (baixo/médio/grande) – que, em seguida, pode ser comparado com suas concessões de nível de risco configuradas no Intune, a fim de determinar se o acesso a determinados recursos de sua escolha deve ser revogado enquanto o dispositivo estiver comprometido.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Quais dados o Intune coleta para Defesa contra Ameaças Móveis?

O Intune coleta informações de inventário de aplicativos em dispositivos pessoais e corporativos e as disponibiliza para que provedores MTD (Defesa contra Ameaças Móveis) efetuem fetch, como o Lookout for Work. É possível coletar um inventário de aplicativos dos usuários de dispositivos iOS 11+.

**Inventário de aplicativos**  
Inventários de dispositivos pessoais e corporativos iOS 11+ são enviados para o provedor de serviços de MTD. Os dados de inventário de aplicativos incluem:

 - ID do aplicativo
 - Versão de Aplicativo
 - Versão Curta do Aplicativo
 - Nome do Aplicativo
 - Tamanho do Pacote do Aplicativo
 - Tamanho Dinâmico do Aplicativo
 - O Aplicativo é validado ou não
 - O Aplicativo é gerenciado ou não

## <a name="sample-scenarios"></a>Exemplo de cenários

Quando um dispositivo é considerado infectado pela solução de Defesa contra Ameaças Móveis:

![Dispositivo infectado da Defesa contra Ameaças Móveis](./media/MTD-image-1.png)

O acesso é concedido quando o dispositivo é corrigido:

![Acesso concedido à Defesa contra Ameaças Móveis](./media/MTD-image-2.png)

> [!NOTE] 
> O uso de vários fornecedores de Defesa contra ameaças de móveis com o Intune não tem suporte. Ter diversas ferramentas de MTD habilitadas fará com que todos os aplicativos MTD sejam instalados e verifiquem os dispositivos em busca de ameaças.

## <a name="mobile-threat-defense-partners"></a>Parceiros de Defesa contra Ameaças Móveis

Saiba como proteger o acesso aso recursos da empresa com base nos riscos ao dispositivo, rede e aplicativo com:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
