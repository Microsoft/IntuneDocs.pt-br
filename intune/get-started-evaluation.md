---
title: O que o Microsoft Intune pode fazer para minha empresa
titleSuffix: ''
description: Problemas de negócios comuns que o Microsoft Intune ajuda a resolver.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/26/2019
ms.topic: overview
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 313e4ccf0e96536b3e99edb968298e4cc3343aa1
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513980"
---
# <a name="what-can-intune-do-for-my-company"></a>O que o Intune pode fazer para minha empresa?
O Microsoft Intune é um serviço de EMM (gerenciamento de mobilidade empresarial) baseado em nuvem que ajuda a habilitar sua força de trabalho a ser produtiva enquanto mantém dados corporativos protegidos.

Com o Intune, você pode:

- gerenciar os dispositivos móveis que sua força de trabalho usa para acessar dados da empresa.
- gerenciar os aplicativos móveis que sua força de trabalho usa.
- proteger informações da empresa, ajudando a controlar a forma como sua força de trabalho as acessa e compartilha.
- garantir que dispositivos e aplicativos sejam compatíveis com os requisitos de segurança da empresa.

## <a name="common-business-problems-that-intune-helps-solve"></a>Problemas de negócios comuns que o Intune ajuda a resolver

* [Proteger seus dados e emails locais para que eles possam ser acessados por dispositivos móveis](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Proteger seus dados e emails do Office 365 para que eles possam ser acessados com segurança por dispositivos móveis](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Emitir telefones corporativos para sua força de trabalho](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Oferecer um programa de BYOD (traga seu próprio dispositivo) ou de dispositivos pessoais para todos os funcionários](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Habilitar os funcionários a acessarem o Office 365 de forma segura de um quiosque público não gerenciado](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Emitir tablets compartilhados de uso limitado para seus funcionários](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)

## <a name="quickstarts"></a>Guias de início rápido

Sabemos que começar a gerenciar dispositivos móveis pode ser difícil. Você precisará tomar muitas decisões diferentes em nome de sua empresa. As guias de início rápido a seguir ajudarão você a trabalhar com o Intune e concluir algumas tarefas comuns em um período de tempo mínimo.

Use o índice no lado esquerdo desta página para abrir as **Guias de Início Rápido** na ordem que quiser.

- [Experimente gratuitamente o Intune](free-trial-sign-up.md) – Crie uma assinatura gratuita para experimentar o Intune em um ambiente de teste.    
- [Criar um usuário](quickstart-create-user.md) – Adicione um usuário ao Intune para permitir que ele acesse os recursos da empresa em dispositivos móveis.
- [Crie um grupo](quickstart-create-group.md): organize os usuários em grupos para facilitar o gerenciamento das políticas e dos aplicativos que eles podem acessar.
- [Configure o registro automático](quickstart-setup-auto-enrollment.md): configure o Intune para registrar automaticamente os dispositivos quando usuários específicos entrarem nos dispositivos do Windows 10.
- [Registre seu dispositivo](quickstart-enroll-windows-device.md): assuma a função de um usuário e registre seu dispositivo no Intune. Em seguida, volte ao Intune para verificar se o dispositivo foi registrado.
- [Criar uma política de conformidade de dispositivo](quickstart-set-password-length-android.md) – Crie uma política de conformidade de dispositivo e atribua um grupo à política.
- [Envie notificações para dispositivos não compatíveis](quickstart-send-notification.md): envie uma notificação por email para os membros de sua força de trabalho que possuem dispositivos incompatíveis ao criar e atribuir uma política de conformidade.
- [Adicionar e atribuir um aplicativo](quickstart-add-assign-app.md) – Adicione e atribua um aplicativo cliente à força de trabalho da empresa.
- [Criar e atribuir uma política de proteção de aplicativo](quickstart-create-assign-app-policy.md) – Criar e atribuir uma política de proteção de aplicativo para um aplicativo cliente no dispositivo do usuário final.
- [Criar e atribuir uma função personalizada](quickstart-create-custom-role.md) – Crie e atribua uma função personalizada com permissões específicas a um departamento de operações de segurança. 
- [Criar um perfil de dispositivo de email para iOS](quickstart-email-profile.md) – Crie um perfil de dispositivo de email para dispositivos iOS.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, você deve ter uma conta de administrador e de locatário do Intune ativadas. Crie uma assinatura gratuita [para experimentar o Intune gratuitamente](free-trial-sign-up.md) em um ambiente de teste. Os assinantes atuais também podem executar essas atividades em seus locatários dinâmicos. Esses artigos de introdução assumem que você está trabalhando em dispositivos de teste.

Também é necessário verificar se você é o administrador global da sua organização para concluir todas as tarefas de Introdução.

## <a name="intune-architecture"></a>Arquitetura do Intune

O Intune é o componente do EMS (Enterprise Mobility + Security) que gerencia aplicativos e dispositivos móveis. Ele se integra intimamente a outros componentes do EMS como o Azure AD (Azure Active Directory) para controle de identidade e acesso e à Proteção de Informações do Azure para proteção de dados. Ao usá-lo com o Office 365, você pode permitir que sua força de trabalho se mantenha produtiva usando todos os dispositivos possíveis ao mesmo tempo que protege as informações da organização.

![Diagrama de arquitetura de alto nível para o Microsoft Intune](/intune/media/intunearchitecture.svg)

## <a name="next-steps"></a>Próximas etapas

[Introdução ao uso do Azure](get-started-azure.md) – entenda a anatomia do portal do Azure e saiba como fazer alterações na página exibida.

## <a name="learn-more"></a>Saiba mais

* [O que é o Intune?](introduction-intune.md)
* [O que é o portal do Azure?](what-is-intune.md)
* [Ciclos de vida do dispositivo e do aplicativo](introduction-device-app-lifecycles.md)
