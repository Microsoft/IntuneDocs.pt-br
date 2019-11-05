---
title: Defesa contra Ameaças Móveis com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Use a MTD (Defesa contra Ameaças Móveis) do Intune com seu parceiro de Defesa contra Ameaças Móveis para proteger o acesso aos recursos da empresa com base no risco do dispositivo.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b67e3b14fd94376fb6dacad88fa58ddc460a6bc5
ms.sourcegitcommit: 807ab3e35f4d9ffa18655410b7d61e5e772ab348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057577"
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integração da Defesa contra Ameaças Móveis com o Intune

O Intune pode integrar dados de um fornecedor de MTD (Defesa contra Ameaças Móveis) como uma fonte de informações para políticas de conformidade do dispositivo e regras de acesso condicional do dispositivo. É possível usar essas informações para ajudar a proteger recursos corporativos como Exchange e SharePoint bloqueando o acesso de dispositivos móveis comprometidos.

O Intune pode usar esses mesmos dados como uma fonte para dispositivos não registrados usando as políticas de proteção de aplicativo do Intune. Dessa forma, os administradores podem usar essas informações para ajudar a proteger dados corporativos em um [aplicativo protegido pelo Microsoft Intune](~/apps/apps-supported-intune-apps.md) e emitir um apagamento em bloco ou seletivo.

## <a name="protect-corporate-resources"></a>Proteger recursos corporativos

A integração das informações dos fornecedores de MTD pode ajudar você a proteger seus recursos corporativos contra ameaças que afetam as plataformas móveis.  

Normalmente, as empresas são proativas para proteger computadores contra vulnerabilidades e ataques, enquanto os dispositivos móveis geralmente ficam sem monitoramento e proteção. Quando as plataformas móveis tiverem proteção interna, como isolamento do aplicativo e lojas de aplicativos de consumidor verificadas, elas permanecerão vulneráveis a ataques sofisticados. À medida que mais funcionários usam dispositivos para trabalhar e para acessar informações confidenciais, as informações dos fornecedores de MTD poderão ajudar a proteger dispositivos e recursos contra ataques cada vez mais sofisticados.

## <a name="intune-mobile-threat-defense-connectors"></a>Conectores de Defesa Contra Ameaças Móveis do Intune

O Intune usa um conector da Defesa contra Ameaças Móveis para criar um canal de comunicação entre o Intune e o fornecedor de MTD escolhido. Os parceiros de MTD do Intune oferecem aplicativos intuitivos e fáceis de implantar para dispositivos móveis. Esses aplicativos executam e analisam ativamente informações sobre ameaças para serem compartilhadas com o Intune. O Intune pode usar os dados para fins de relatório ou de imposição.

Por exemplo: Um aplicativo de MTD conectado informa ao fornecedor de MTD que um celular em sua rede está atualmente conectado a uma rede vulnerável a ataques man-in-the-middle. Essas informações são categorizadas em um nível de risco apropriado de baixo, médio ou alto. Este nível de risco é comparado com as concessões de nível de risco definidas no Intune. Com base nessa comparação, o acesso a determinados recursos de sua escolha pode ser revogado enquanto o dispositivo está comprometido.

## <a name="data-that-intune-collects-for-mobile-threat-defense"></a>Dados que o Intune coleta para Defesa contra Ameaças Móveis

Se estiver habilitado, o Intune coletará informações de inventário de aplicativo de dispositivos pessoais e corporativos e as disponibilizará para que os provedores de MTD efetuem fetch, como o Lookout for Work. É possível coletar um inventário de aplicativo dos usuários de dispositivos iOS.

Esse serviço é uma aceitação; nenhuma informação de inventário de aplicativo é compartilhada por padrão. Um administrador do Intune precisa habilitar a **Sincronização de Aplicativos para dispositivos iOS** nas configurações do conector de Defesa contra Ameaças Móveis antes de as informações de inventário do aplicativo serem compartilhadas.

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

## <a name="sample-scenarios-for-enrolled-devices-using-device-compliance-policies"></a>Cenários de exemplo para dispositivos registrados usando políticas de conformidade do dispositivo

Quando um dispositivo é considerado infectado pela solução de Defesa Contra Ameaças Móveis:

![Imagem mostrando um dispositivo infectado da Defesa contra Ameaças Móveis](./media/mobile-threat-defense/MTD-image-1.png)

O acesso é concedido quando o dispositivo é corrigido:

![Imagem mostrando um acesso concedido da Defesa contra Ameaças Móveis](./media/mobile-threat-defense/MTD-image-2.png)

## <a name="sample-scenarios-for-unenrolled-devices-using-intune-app-protection-policies"></a>Cenários de exemplo para dispositivos não registrados usando políticas de proteção de aplicativo do Intune

Quando um dispositivo é considerado infectado pela solução de Defesa Contra Ameaças Móveis:<br>
![Imagem mostrando um dispositivo infectado da Defesa contra Ameaças Móveis](./media/mobile-threat-defense/MTD-image-3.png)

O acesso é concedido quando o dispositivo é corrigido:<br>
![Imagem mostrando um acesso concedido da Defesa contra Ameaças Móveis](./media/mobile-threat-defense/MTD-image-4.png)

> [!NOTE]
> Você pode usar vários fornecedores de Defesa Móvel com um único locatário do Intune. No entanto, quando dois ou mais fornecedores são configurados para uso na mesma plataforma, todos os dispositivos que executam essa plataforma devem instalar cada aplicativo de MTD e verificar se há ameaças. Falha ao enviar uma verificação de qualquer aplicativo configurado resulta no dispositivo marcado como fora de conformidade. 

## <a name="mobile-threat-defense-partners"></a>Parceiros de Defesa Contra Ameaças Móveis

Saiba como proteger o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo com:

- [Lookout for Work](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Defesa contra Ameaças Móveis Wandera](wandera-mtd-connector.md)
