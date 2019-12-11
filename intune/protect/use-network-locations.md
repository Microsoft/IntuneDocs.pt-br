---
title: Associar dispositivos Android por local de rede no Microsoft Intune – Azure | Microsoft Docs
description: Criar ou configurar locais de rede no Microsoft Intune para dispositivos Android. Você pode marcar dispositivos como não compatíveis com base no local de rede do dispositivo. Se o dispositivo ficar fora do local de rede, você poderá bloquear o acesso aos recursos da empresa.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ayesham
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 847ab759b697d402acb07d9c8d83d3a3ef9aaef2
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74058144"
---
# <a name="use-locations-network-fence-in-intune"></a>Usar Locais (limite de rede) no Intune

Você talvez queira bloquear o acesso a uma rede corporativa se um dispositivo sair de um local. O recurso **Locais** no Intune oferece essa funcionalidade. 

Você pode criar uma política de conformidade baseada no local de rede, também conhecida como isolamento de rede. A política garante que dispositivos devam ser conectados a uma rede de trabalho para estarem em conformidade. Essa política pode ser usada com políticas de Acesso Condicional para que os dispositivos tenham acesso a recursos de trabalho *somente* quando o dispositivo estiver conectado à rede de trabalho. Quando o dispositivo não está conectado à rede de trabalho, o dispositivo deixa de estar em conformidade e perde o acesso aos recursos de trabalho.

Considere o seguinte cenário:

Em suas instalações de fabricação, alguns funcionários usam dispositivos Android. Um funcionário leva o dispositivo Android fora da instalação ou fábrica. Para ajudar a evitar acesso não autorizado, você pode:

1. Criar um local com um intervalo IPv4 chamado **Andar de fabricação**.
2. Crie uma política de conformidade que exija que esses dispositivos sejam conectados à sua rede corporativa e atribua essa política.
3. Se o dispositivo sair da fábrica, ele será considerado como não estando em conformidade e não terá acesso a recursos corporativos.

Além disso, você pode adicionar [ações de não conformidade](#configure-the-actions-for-noncompliance). Quando o dispositivo estiver de volta ao local e no local de rede, ele recuperará o acesso aos recursos corporativos.

## <a name="prerequisites"></a>Pré-requisitos

Para criar uma política de conformidade baseada em local:

- Crie um local de rede como intervalos de rede IPV4 para o Servidor de Gateway, o Servidor DHCP e/ou o servidor DNS aos quais os dispositivos se conectam
- Crie a política de conformidade que usa esses locais e defina a ação executada quando o dispositivo não está mais conectado ao local de rede
- Dispositivos Android 6.0 e superiores, com o aplicativo Portal da Empresa atualizado

## <a name="create-a-location"></a>Criar um local

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Políticas de conformidade** > **Locais** > **Criar**.

2. Insira as seguintes propriedades:  

   - Obrigatório. Insira um **Nome** para o local, como **Andar do fabricante** ou **Prédio 44-seguro**.
   - Opcional. Insira um **Intervalo IPv4** com a notação CIDR (Roteamento Interdomínio Sem Classe), como `aaa.bbb.ccc.ddd/n`.
   - Opcional. Insira o endereço **Gateway IPv4**, como `aaa.bbb.ccc.ddd`.
   - Opcional. Insira o endereço do **Servidor DHCP IPv4**, como `aaa.bbb.ccc.ddd`.
   - Opcional. Insira uma lista de endereços de **Servidores DNS IPv4**. Essa configuração usa **correspondência de subconjunto**. Se os Servidores DNS IPv4 no dispositivo forem subconjuntos dos valores definidos, o dispositivo será considerado como estando DENTRO do isolamento. Insira um endereço por linha, como:  
     `aaa.bbb.ccc.ddd`  
     `aaa.bbb.ccc.ddd`
   - Opcional. Insira uma lista de **Sufixos DNS**. Essa configuração usa **correspondência de subconjunto**. Se os Sufixos DNS no dispositivo forem subconjuntos dos valores definidos, o dispositivo será considerado como estando DENTRO do isolamento. Insira um nome de domínio em cada linha, como:  
     `contoso.com`  
     `contoso.org`

3. **Salve** suas alterações.

## <a name="create-the-location-compliance-policy"></a>Crie a política de conformidade do local

Ao [criar a política de conformidade](create-compliance-policy.md), selecione **Android** como a **Plataforma**. Em **Locais**, você pode escolher um ou mais dos locais de rede que você adicionou. Esses locais fazem parte do isolamento de rede que você está criando para seus dispositivos.

## <a name="configure-the-actions-for-noncompliance"></a>Configurar as ações para não conformidade

Depois que a política de conformidade for criada, a ação padrão de não conformidade se aplicará ao dispositivo. Você pode adicionar mais ações. Por exemplo, adicione uma ação que envie um email para o usuário quando o dispositivo não estiver mais em conformidade com os locais.

[Adicionar ações para não conformidade](actions-for-noncompliance.md) fornece algumas diretrizes.

## <a name="company-portal-app"></a>Aplicativo do Portal da Empresa

Quando o dispositivo está conectado aos seus locais, o dispositivo é mostrado como em conformidade no aplicativo do Portal da Empresa. Quando o dispositivo não está conectado a um de seus locais, ele é mostrado como não em conformidade.

## <a name="next-steps"></a>Próximas etapas

[Monitorar políticas de conformidade do dispositivo](compliance-policy-monitor.md)  
[Introdução às políticas de conformidade](device-compliance-get-started.md)
