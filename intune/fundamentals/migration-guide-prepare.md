---
title: Preparar o Intune para o gerenciamento de dispositivo móvel
titleSuffix: Microsoft Intune
description: Avalie seus requisitos comerciais e técnicos antes de migrar para o Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 29ae889e99a843a8569782bad2b1303c7bb4304c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727474"
---
# <a name="phase-1-prepare-microsoft-intune-for-mobile-device-management-mdm"></a>Fase 1: Preparar o Microsoft Intune para o MDM (gerenciamento de dispositivo móvel)

Antes de entrar nos detalhes da configuração do Intune, vamos analisar os requisitos de gerenciamento de dispositivos móveis de sua organização. Pode ser útil executar relatórios de usuários ativos no seu provedor de MDM atual para identificar os grupos de usuários críticos. Em seguida, você pode começar a abordar as perguntas na seção [Avaliar os requisitos de MDM](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>Avaliar os requisitos de MDM

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Quais os tipos de dispositivos que você precisa gerenciar?

- A quais [plataformas](supported-devices-browsers.md) você precisa oferecer suporte?

- Os dispositivos para os quais você precisa dar suporte são propriedade corporativa ou pessoais?

- Qual é o tipo de conectividade usado? Wi-Fi, celular, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>O que seus usuários precisam fazer nos dispositivos gerenciados?

- Você precisa provisionar aplicativos para seus usuários finais?

- Você usa aplicativos de linha de negócios personalizados? Ou, você só precisa de aplicativos de armazenamento público?

- Você precisa provisionar contas de email?

### <a name="what-kinds-of-users"></a>Quais tipos de usuários?

- Quantos usuários usarão um único dispositivo?

- De quais termos de uso você precisa?

  - Envolva o departamento jurídico o quanto antes nesta questão.
  - Qual localização é necessária?

- Os usuários estão familiarizados com tecnologia e TI em geral?

### <a name="what-is-your-device-security-policy"></a>Qual é sua política de segurança de dispositivo?

- Você precisa de criptografia no nível do dispositivo?

- Quais são seus comprimentos de código PIN/senha do dispositivo atuais?

- Você precisa desativar recursos do dispositivo, ou restringir determinados comportamentos do dispositivo? Você pode controlar várias configurações específicas à plataforma com perfis de configuração do dispositivo, por exemplo:
  - Desabilitar a câmera
  - Bloqueio para o modo de aplicativo único<br/>

- Para quais tipos de autenticação você precisa dar suportar? Se você precisar da autenticação baseada em certificado, quais são os tipos de certificados que devem ser provisionados?
  - O Intune pode provisionar certificados com os perfis de acesso aos recursos dos dispositivos registrados.
  - Para qual tipo de infraestrutura de PKI (Infraestrutura de chave pública) você precisa oferecer suporte?
  <br></br>
- Você precisa oferecer suporte à VPN (Rede virtual privada) no nível do aplicativo ou dispositivo?

  - O Intune pode provisionar as configurações de VPN para provedores de VPN de terceiros.
  <br/><br/>
- É possível fazer exceções temporárias para certos requisitos a fim de evitar o tempo de inatividade? Ou os dispositivos com acesso sempre devem atender a todos os requisitos de segurança?

## <a name="next-steps"></a>Próximas etapas
Leia estes [estudos de caso](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) de setores diferentes da indústria para ver como as organizações avaliaram seus requisitos de gerenciamento de dispositivo móvel.

Examine a [configuração básica do Intune](migration-guide-setup.md).
