---
title: "Preparar o Intune para o gerenciamento de dispositivo móvel | Microsoft Docs"
description: "A finalidade deste artigo é ajudar os leitores a avaliar seus requisitos comerciais e técnicos antes de migrar para o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 2e7bcedebdf777db64a9ec90aa758822634ed435
ms.lasthandoff: 03/28/2017


---

# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>Fase 1: Preparar o Intune para o MDM (gerenciamento de dispositivo móvel)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Antes de entrar nos detalhes da configuração do Intune, vamos analisar os requisitos de gerenciamento de dispositivos móveis de sua organização. Talvez seja útil executar relatórios de usuários ativos em seu provedor de MDM atual, a fim de identificar os grupos de usuário críticos. Depois, você pode começar a responder as perguntas na [seção Avaliar requisitos de MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>Avaliar os requisitos de MDM

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Quais os tipos de dispositivos que você precisa gerenciar?

-   A quais [plataformas](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers) você precisa oferecer suporte?

-   Os dispositivos para os quais você precisa oferecer suporte são corporativos ou BYOD?

-   Qual é o tipo de conectividade usado? Wi-Fi, celular, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>O que seus usuários precisam fazer nos dispositivos gerenciados?

-   Você precisa provisionar aplicativos para seus usuários finais?

-   Você usa aplicativos de linha de negócios personalizados? Ou, você só precisa de aplicativos de armazenamento público?

-   Você precisa provisionar contas de email?

### <a name="what-kinds-of-users"></a>Quais tipos de usuários?

-   Quantos usuários usarão um único dispositivo?

-   De quais Termos de Uso você precisa?

    -   Envolva o departamento jurídico o quanto antes nesta questão.

    -   Qual localização é necessária?

-   Os usuários estão familiarizados com tecnologia e TI em geral?

### <a name="what-is-your-device-security-policy"></a>Qual é sua política de segurança de dispositivo? 

-   Você precisa de criptografia no nível do dispositivo?

-   Comprimentos do código pin/senha do dispositivo?

-   Você precisa desativar recursos do dispositivo, ou restringir determinados comportamentos do dispositivo?

    -   Você pode controlar várias configurações específicas à plataforma com perfis de configuração do dispositivo, por exemplo: desabilitar a câmera, bloqueio no modo de aplicativo único.
<br></br>
-   Para quais tipos de autenticação você precisa dar suportar?

    -   Se você precisar da autenticação baseada em certificado, quais são os tipos de certificados que devem ser provisionados?

        -   O Intune pode provisionar certificados com os perfis de acesso aos recursos dos dispositivos registrados.
<br></br>
    -   Para qual tipo de infraestrutura de PKI (Infraestrutura de chave pública) você precisa oferecer suporte?
<br></br>
-   Você precisa oferecer suporte à VPN (Rede virtual privada) no nível do aplicativo ou dispositivo?

    -   O Intune pode provisionar as configurações de VPN para provedores de VPN de terceiros.
<br></br>
-   É possível fazer exceções temporárias para certos requisitos a fim de evitar o tempo de inatividade? Ou os dispositivos com acesso sempre devem atender a todos os requisitos de segurança?

## <a name="additional-information"></a>Informações adicionais

-   Para obter mais exemplos, veja os [estudos de caso](https://customers.microsoft.com/en-US/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) de setores diferentes da indústria para ver como as organizações avaliaram seus requisitos de gerenciamento de dispositivos móveis.

## <a name="next-steps"></a>Próximas etapas

[Fase 1: Configuração básica](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

