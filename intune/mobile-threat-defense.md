---
title: Defesa contra Ameaças Móveis com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Use a MTD (Defesa contra Ameaças Móveis) do Intune com seu parceiro de Defesa contra Ameaças Móveis para proteger o acesso aos recursos da empresa com base no risco do dispositivo.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0452229d6c1ea2d9e87a302675167d200bd348eb
ms.sourcegitcommit: 6bba9f2ef4d1ec699f5713a4da4f960e7317f1cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67407164"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>O que é a integração da Defesa contra Ameaças Móveis com o Intune?
O Intune pode integrar dados de um fornecedor de Defesa contra Ameaças Móveis como uma fonte de informações para políticas de conformidade e regras de acesso condicional. É possível usar essas informações para ajudar a proteger recursos corporativos como Exchange e SharePoint bloqueando o acesso de dispositivos móveis comprometidos.  

## <a name="what-problem-does-this-solve"></a>Que problema isso resolve?
A integração de informações de um fornecedor de Defesa Contra Ameaças Móveis pode ajudar a proteger seus recursos corporativos contra ameaças que afetam as plataformas móveis.  

Normalmente, as empresas são proativas para proteger computadores contra vulnerabilidades e ataques, enquanto os dispositivos móveis geralmente ficam sem monitoramento e proteção. Quando as plataformas móveis tiverem proteção interna, como isolamento do aplicativo e lojas de aplicativos de consumidor verificadas, elas permanecerão vulneráveis a ataques sofisticados. À medida que mais funcionários usam dispositivos para trabalhar e para acessar informações confidenciais, as informações do fornecedor de Defesa contra Ameaças Móveis poderão ajudar a proteger dispositivos e recursos contra ataques cada vez mais sofisticados.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Como funcionam os conectores da Defesa contra Ameaças Móveis do Intune?

O Intune usa um conector da Defesa contra Ameaças Móveis para criar um canal de comunicação entre o Intune e o fornecedor da Defesa contra Ameaças Móveis escolhido. Os parceiros da Defesa contra Ameaças Móveis do Intune oferecem aplicativos intuitivos e fáceis de implantar para dispositivos móveis. Esses aplicativos executam e analisam ativamente informações sobre ameaças para serem compartilhadas com o Intune. O Intune pode usar os dados para fins de relatório ou de imposição.  

Por exemplo: Um aplicativo de Defesa contra Ameaças Móveis conectado informa ao fornecedor da Defesa contra Ameaças Móveis que um celular em sua rede está atualmente conectado a uma rede vulnerável a ataques man-in-the-middle. Essas informações são categorizadas em um nível de risco apropriado de baixo, médio ou alto. Este nível de risco é comparado com as concessões de nível de risco definidas no Intune. Com base nessa comparação, o acesso a determinados recursos de sua escolha pode ser revogado enquanto o dispositivo está comprometido.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Quais dados o Intune coleta para Defesa contra Ameaças Móveis?

Se estiver habilitado, o Intune coletará informações de inventário de aplicativo de dispositivos pessoais e corporativos e as disponibilizará para que os provedores MTD (Defesa contra Ameaças Móveis) efetuem fetch, como o Lookout for Work. É possível coletar um inventário de aplicativo dos usuários de dispositivos iOS.

Esse serviço é uma aceitação; nenhuma informação de inventário de aplicativo é compartilhada por padrão. Um administrador do Intune precisa habilitar a Sincronização de Aplicativos para dispositivos iOS nas configurações do serviço antes de as informações de inventário de aplicativo serem compartilhadas.

**Inventário de aplicativos**  
Se você habilitar a Sincronização do Aplicativo para dispositivos iOS, os inventários de dispositivos iOS pessoais e corporativos serão enviados para o provedor de serviços MTD. Os dados de inventário de aplicativos incluem:

 - ID do aplicativo
 - Versão de Aplicativo
 - Versão Curta do Aplicativo
 - Nome do Aplicativo
 - Tamanho do Pacote do Aplicativo
 - Tamanho Dinâmico do Aplicativo
 - Indica se o aplicativo é validado ou não
 - Indica se o aplicativo é gerenciado ou não

## <a name="sample-scenarios"></a>Cenários de exemplo

Quando um dispositivo é considerado infectado pela solução de Defesa Contra Ameaças Móveis:

![Imagem mostrando um dispositivo infectado da Defesa contra Ameaças Móveis](./media/MTD-image-1.png)

O acesso é concedido quando o dispositivo é corrigido:

![Imagem mostrando um acesso concedido da Defesa contra Ameaças Móveis](./media/MTD-image-2.png)

> [!NOTE] 
> O uso de vários fornecedores de Defesa contra ameaças de móveis com o Intune não tem suporte. Ter diversas ferramentas de MTD habilitadas fará com que todos os aplicativos MTD sejam instalados e verifiquem os dispositivos em busca de ameaças.

## <a name="mobile-threat-defense-partners"></a>Parceiros de Defesa Contra Ameaças Móveis

Saiba como proteger o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo com:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Defesa contra Ameaças Móveis Wandera](wandera-mtd-connector.md)
