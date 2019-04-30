---
title: Noções básicas sobre entrega e tempo da política de proteção de aplicativos
titleSuffix: Microsoft Intune
description: Conheça as diferentes janelas de implantação para que as políticas de proteção de aplicativo entendam quando as alterações devem aparecer em seus dispositivos de usuário final.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ec111319-7e02-434f-946b-88647726bf1a
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 879ccc890a727ddbd911a2b42266d205a1a293c5
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501265"
---
# <a name="understand-app-protection-policy-delivery-timing"></a>Noções básicas sobre entrega e tempo da política de proteção de aplicativos

Conheça as diferentes janelas de implantação para que as políticas de proteção de aplicativo entendam quando as alterações devem aparecer em seus dispositivos de usuário final.

## <a name="delivery-timing-summary"></a>Resumo do tempo de entrega

A entrega da política de proteção de aplicativos depende do estado da licença e do registro do serviço do Intune para seus usuários.  

|    Estado do Usuário    |    Comportamento da Proteção de Aplicativo     |    Intervalo de Repetição (confira a observação)    |    Por que isso acontece?    |
|-----------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|    Locatário não integrado    |    Aguarde o próximo intervalo de repetição.  A Proteção do Aplicativo não está ativa para o usuário.    |    24 horas    |    Ocorrerá quando você não tiver configurado seu locatário do Intune.    |
|    Usuário não licenciado     |    Aguarde o próximo intervalo de repetição.  A Proteção de Aplicativo não está ativa para o usuário.     |    12 horas – No entanto, em dispositivos Android, esse intervalo requer o SDK da APP do Intune versão 5.6.0 ou posterior. Caso contrário, para dispositivos Android, o intervalo é de 24 horas.   |    Ocorre quando você não licenciou o usuário para o Intune.    |
|    O usuário não atribuiu Políticas de Proteção de Aplicativo    |    Aguarde o próximo intervalo de repetição.  A Proteção do Aplicativo não está ativa para o usuário.    |    12 horas        |    Ocorre quando você não atribuiu configurações de APP ao usuário.    |
|    O usuário registrou-se no Intune MAM com êxito    |    A Proteção de Aplicativo é aplicada por configurações de política.    As atualizações ocorrem com base no intervalo de repetição    |    Serviço do Intune definido com base na carga do usuário.    Normalmente 30 min.     |    Ocorre quando o usuário registrou com êxito o serviço Intune para a configuração de MAM.    |

> [!NOTE]
> Os intervalos de repetição podem exigir que ocorra o uso de aplicativo ativo, o que significa que o aplicativo foi iniciado e está em uso.  Se o intervalo de repetição for de 24 horas e o usuário aguardar 48 horas para iniciar o aplicativo, o cliente da Proteção de Aplicativos tentará novamente em 48 horas.

## <a name="handling-network-connectivity-issues"></a>Como tratar problemas de conectividade de rede

Quando o registro do usuário falha devido a problemas de conectividade de rede, um intervalo de repetição acelerado é usado.  O cliente da Proteção de Aplicativos tentará novamente em intervalos cada vez maiores até que ele atinja 60 minutos ou até que uma conexão bem-sucedida seja realizada.  O cliente continuará tentando novamente em intervalos de 60 minutos até que uma conexão bem-sucedida seja realizada. Em seguida, o cliente retornará para o intervalo de repetição padrão com base no estado do usuário.

## <a name="next-steps"></a>Próximas etapas

[Atribuir licenças aos usuários para que possam registrar dispositivos no Intune](licenses-assign.md)

