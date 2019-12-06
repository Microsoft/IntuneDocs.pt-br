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
ms.openlocfilehash: 84f82cf2fde7d400e5531bac219b6cbb4877032f
ms.sourcegitcommit: 960ffb2214c35d75ad219fa2571a999529a0abd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "74478927"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Habilitar o conector de Defesa contra Ameaças Móveis no Intune para dispositivos não registrados

Durante a instalação do MTD (Defesa contra Ameaças Móveis), você configurou uma política para classificar ameaças em seu console do parceiro de Defesa contra Ameaças Móveis e criou a política de proteção de aplicativo no Intune. Se já tiver configurado o conector do Intune no console do parceiro MTD, agora você poderá habilitar a conexão do MTD para aplicativos de parceiro MTD.

> [!NOTE]
> Este artigo aplica-se a todos os parceiros de Defesa contra Ameaças Móveis que dão suporte a políticas de proteção de aplicativo: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>As políticas de acesso condicional clássicas para aplicativos MTD

Quando você integra um novo aplicativo à Defesa contra Ameaças Móveis do Intune e habilita a conexão a essa plataforma, o Intune cria uma política de acesso condicional clássica no Azure Active Directory. Cada aplicativo MTD integrado, como o [Defender ATP](advanced-threat-protection.md) ou um de nossos [parceiros de MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionais, cria uma nova política de acesso condicional clássica. Essas políticas podem ser ignoradas, mas não devem ser editadas, excluídas nem desabilitadas.

Se a política clássica for excluída, será necessário excluir a conexão com o Intune responsável por sua criação e configurá-la novamente. Esse processo recria a política clássica. Não há suporte para a migração de políticas clássicas para aplicativos MTD para o novo tipo de política de acesso condicional.

As políticas de acesso condicional clássicas para aplicativos MTD:

- São usadas pelo Intune MTD para exigir que os dispositivos sejam registrados no Azure AD, de modo que tenham uma ID de dispositivo, antes de se comunicarem com os parceiros de MTD. A ID é necessária para que os dispositivos possam relatar com êxito seu status ao Intune.

- Não afeta outros recursos ou aplicativos de nuvem.

- São diferentes das políticas de acesso condicional que você pode criar para ajudar a gerenciar o MTD.

- Por padrão, não interagem com outras políticas de acesso condicional usadas para avaliação.

Para exibir as políticas de acesso condicional clássicas, no [Azure](https://portal.azure.com/#home), acesse **Azure Active Directory** > **Acesso Condicional** > **Políticas clássicas**.

## <a name="to-enable-the-mtd-connector"></a>Para habilitar o conector MTD

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Administração de locatários** > **Conectores e tokens** > **Defesa contra Ameaças Móveis**.

3. No painel **Defesa contra Ameaças Móveis**, escolha **Adicionar**.

4. Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Habilite as opções de alternância de acordo com os requisitos de sua organização. A alternância da visibilidade das opções varia dependendo do parceiro de MTD.

## <a name="mobile-threat-defense-toggle-options"></a>Opções de alternância de Defesa contra Ameaças Móveis

Decida quais opções de alternância do MTD você precisa habilitar de acordo com os requisitos da sua organização. Veja mais detalhes abaixo:

**Configurações de política de proteção de aplicativo**

- **Conecte dispositivos Android versão 4.4 e posteriores ao *\<nome do parceiro de MTD>* para avaliar a política de proteção do aplicativo**: Ao habilitar essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.

- **Conecte dispositivos iOS versão 11 e posteriores ao *\<nome do parceiro de MTD>* para avaliar a política de proteção do aplicativo**: Ao habilitar essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.

**Configurações compartilhadas comuns**

- **Número de dias até que o parceiro seja considerado sem resposta**: Número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD no painel de Defesa contra Ameaças Móveis.

## <a name="next-steps"></a>Próximas etapas

- [Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Intune](~/protect/mtd-app-protection-policy.md).
