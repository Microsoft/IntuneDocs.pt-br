---
title: Habilitar o conector de Defesa contra Ameaças Móveis para dispositivos não registrados
titleSuffix: Microsoft Intune
description: Habilitar o conector de Defesa contra Ameaças Móveis no Microsoft Intune para dispositivos não registrados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63079757ee3610d825601921da1d33aa94f851b6
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72794401"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Habilitar o conector de Defesa contra Ameaças Móveis no Intune para dispositivos não registrados

Durante a instalação do MTD (Defesa contra Ameaças Móveis), você configurou uma política para classificar ameaças em seu console do parceiro de Defesa contra Ameaças Móveis e criou a política de proteção de aplicativo no Intune. Se já tiver configurado o conector do Intune no console do parceiro MTD, agora você poderá habilitar a conexão do MTD para aplicativos de parceiro MTD.

> [!NOTE] 
> Este artigo aplica-se a todos os parceiros de Defesa contra Ameaças Móveis que dão suporte a políticas de proteção de aplicativo: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

## <a name="to-enable-the-mtd-connector"></a>Para habilitar o conector MTD

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. No **Painel do Intune**, escolha **Conformidade do dispositivo** e, depois, **Defesa contra Ameaças Móveis** na seção **Configuração**.

3. No painel **Defesa contra Ameaças Móveis**, escolha **Adicionar**.

4. Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Habilite as opções de alternância de acordo com os requisitos de sua organização. A alternância da visibilidade das opções varia dependendo do parceiro de MTD.

## <a name="mtd-toggle-options"></a>Opções de alternância de MTD

Você pode decidir quais opções de alternância de MTD você precisa habilitar de acordo com os requisitos da sua organização. Veja mais detalhes abaixo:

**Configurações de Política de Proteção de Aplicativo**
- **Conecte dispositivos Android versão 4.1 e superior a *\<nome do parceiro de MTD>* para avaliar a política de proteção do aplicativo**: Quando você habilita essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.
- **Conecte dispositivos iOS versão 8.0 e superior a *\<nome do parceiro de MTD>* para avaliar a política de proteção do aplicativo**: Quando você habilita essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.

**Configurações compartilhadas comuns**
- **Número de dias até que o parceiro seja considerado sem resposta**: Número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD no painel de Defesa contra Ameaças Móveis.

> [!NOTE] 
> Quando você habilita a conexão da Defesa contra Ameaças Móveis com o Intune, o Intune cria uma política de acesso condicional clássica no Azure Active Directory. Cada aplicativo MTD integrado, como o [Defender ATP](advanced-threat-protection.md) ou um de nossos [parceiros de MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionais, cria uma nova política de acesso condicional clássica. **Essas políticas podem ser ignoradas, mas não devem ser editadas, excluídas nem desabilitadas.**
> 
> As políticas de acesso condicional clássicas para aplicativos MTD: 
> - São usadas pelo Intune MTD para exigir que os dispositivos sejam registrados no Azure AD, de modo que tenham uma ID de dispositivo, antes de se comunicarem com os parceiros de MTD. A ID é necessária para que os dispositivos possam relatar com êxito seu status ao Intune.  
> - Não afeta outros recursos ou aplicativos de nuvem.  
> - São diferentes das políticas de acesso condicional que você pode criar para ajudar a gerenciar o MTD ou para Exigir AC de Proteção do Aplicativo
> - Por padrão, não interagem com outras políticas de acesso condicional usadas para avaliação.  
>
> Para exibir as políticas de acesso condicional clássicas, no [Azure](https://portal.azure.com/#home), acesse **Azure Active Directory** > **Acesso Condicional** > **Políticas clássicas**.

## <a name="next-steps"></a>Próximas etapas

- [Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Intune](~/protect/mtd-app-protection-policy.md).