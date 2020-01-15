---
title: Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Intune
titleSuffix: Microsoft Intune
description: Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: 7cc873079d9a139edfa2217d97806afe0c5bbf28
ms.sourcegitcommit: 06dce5c8111592ad774247e86e539dd3128117e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2019
ms.locfileid: "75545949"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Criar uma política de proteção de aplicativo com a Defesa contra Ameaças Móveis com o Intune

O Intune com MTD (Defesa contra Ameaças Móveis) ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis. Você pode criar uma política de proteção do aplicativo do Intune que avalia o risco para determinar se o dispositivo tem permissão para acessar dados corporativos ou não.


> [!NOTE]
> Este artigo aplica-se a todos os parceiros de Defesa contra Ameaças Móveis que dão suporte a políticas de proteção de aplicativo:
>
> - Better Mobile (Android)
> - Zimperium (Android, iOS)
> - Lookout for Work (Android, iOS).

## <a name="before-you-begin"></a>Antes de começar

Como parte da configuração de MTD, você criou no console do parceiro de MTD uma política que classifica diversas ameaças como os níveis alto, médio e baixo. Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de proteção de aplicativo do Intune.

Pré-requisitos para a política de proteção de aplicativo com MTD:

- Configurar a integração da MTD com o Intune. Sem essa integração, a política de proteção do aplicativo de MTD não terá nenhum efeito.

## <a name="to-create-an-mtd-app-protection-policy"></a>Para criar uma política de proteção de aplicativo MTD

Use o procedimento para [criar uma Política de proteção de aplicativo para o iOS/iPadOS ou Android](../apps/app-protection-policies.md#app-protection-policies-for-iosipados-and-android-apps) e use as seguintes informações das páginas *Aplicativos*, *Inicialização condicional* e *Atribuições*:

- **Aplicativos**: selecione o aplicativo do parceiro de Defesa contra Ameaças Móveis que você usa.
- **Inicialização condicional**:  abaixo de *Condições do dispositivo*, use a caixa suspensa para selecionar **Nível máximo permitido de ameaça ao dispositivo**.

  Opções para o **valor** do nível de ameaça:

  - **Protegido**: este é o nível mais seguro. O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como não compatível.
  - **Baixa**: O dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Média**: O dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.
  - **Alta**: Esse nível é o menos seguro. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis apenas para fins de relatório. É necessário ativar a MTD do aplicativo com esta configuração nos dispositivos.

  Opções de **Ação**:

  - **Bloquear o acesso**
  - **Apagar os dados**

- **Atribuições**: Atribua a política aos grupos de usuários.  Os dispositivos usados pelos membros do grupo são avaliados quanto ao acesso a dados corporativos nos aplicativos de destino por meio da proteção de aplicativo do Intune.


## <a name="next-steps"></a>Próximas etapas  

- Siava mais sobre a [Defesa contra Ameaças Móveis](~/protect/mobile-threat-defense.md) no Microsoft Intune.
