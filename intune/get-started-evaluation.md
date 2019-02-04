---
title: O que o Microsoft Intune pode fazer para minha empresa
titleSuffix: ''
description: Problemas de negócios comuns que o Microsoft Intune ajuda a resolver.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: c8e15675beb97b396c9340e2ab3bfa86a3a43f76
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831421"
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

## <a name="quickstarts"></a>Inícios rápidos

Sabemos que pode ser difícil iniciar o gerenciamento de dispositivos móveis, porque há muitas decisões diferentes que você precisa tomar em nome da sua empresa. Os inícios rápidos a seguir ajudam você a se familiarizar com o Intune e realizar algumas tarefas comuns em um curto espaço de tempo.

Você pode seguir a ordem planejada dos **Inícios Rápidos** usando o sumário à esquerda da página.

- [Experimente gratuitamente o Intune](free-trial-sign-up.md) – Crie uma assinatura gratuita para experimentar o Intune em um ambiente de teste.    
- [Criar um usuário](quickstart-create-user.md) – Adicione um usuário ao Intune para permitir que ele acesse os recursos da empresa em dispositivos móveis.
- [Criar um grupo](quickstart-create-group.md) – Organize usuários em grupos para facilitar o gerenciamento das políticas e dos aplicativos que eles podem acessar.
- [Configurar o registro automático](quickstart-setup-auto-enrollment.md) – Configure o Microsoft Intune para registrar automaticamente os dispositivos quando usuários específicos entrarem com dispositivos Windows 10.
- [Registrar seu dispositivo](quickstart-enroll-windows-device.md) – Assuma a função de um usuário do Intune e registre seu dispositivo no Microsoft Intune. Em seguida, retorne para o Intune e confirme o dispositivo registrado.
- [Criar uma política de conformidade de dispositivo](quickstart-set-password-length-android.md) – Crie uma política de conformidade de dispositivo e atribua um grupo à política.
- [Enviar notificações para dispositivos não compatíveis](quickstart-send-notification.md) – Envie uma notificação por email para os membros de sua força de trabalho que têm dispositivos não compatíveis ao criar e atribuir uma política de conformidade.
- [Adicionar e atribuir um aplicativo](quickstart-add-assign-app.md) – Adicione e atribua um aplicativo cliente à força de trabalho da empresa.
- [Criar e atribuir uma política de proteção de aplicativo](quickstart-create-assign-app-policy.md) – Criar e atribuir uma política de proteção de aplicativo para um aplicativo cliente no dispositivo do usuário final.
- [Criar e atribuir uma função personalizada](quickstart-create-custom-role.md) – Crie e atribua uma função personalizada com permissões específicas a um departamento de operações de segurança. 
- [Criar um perfil de dispositivo de email para iOS](quickstart-email-profile.md) – Crie um perfil de dispositivo de email para dispositivos iOS.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, você deve ter uma conta de administrador e de locatário do Intune ativadas. Crie uma assinatura gratuita [para experimentar o Intune gratuitamente](free-trial-sign-up.md) em um ambiente de teste. Os assinantes atuais também podem executar essas atividades em seu locatário dinâmico. Esses artigos de introdução assumem que você está trabalhando em dispositivos de teste.

Também é necessário verificar se você é o administrador global da sua organização para concluir todas as tarefas de Introdução.

## <a name="intune-architecture"></a>Arquitetura do Intune

O Intune é o componente do EMS (Enterprise Mobility + Security) que gerencia aplicativos e dispositivos móveis. Ele se integra intimamente a outros componentes do EMS como o Azure AD (Azure Active Directory) para controle de identidade e acesso e à Proteção de Informações do Azure para proteção de dados. Ao usá-lo com o Office 365, você pode permitir que sua força de trabalho fique produtiva usando todos os dispositivos possíveis e ainda manter as informações da organização protegidas.

![Diagrama de arquitetura de alto nível para o Microsoft Intune](/intune/media/intunearchitecture.svg)

## <a name="next-steps"></a>Próximas etapas

[Introdução ao uso do Azure](get-started-azure.md) – entenda a anatomia do portal do Azure e saiba como fazer alterações na página exibida.

## <a name="learn-more"></a>Saiba mais

* [O que é o Intune?](introduction-intune.md)
* [O que é o portal do Azure?](what-is-intune.md)
* [Ciclos de vida do dispositivo e do aplicativo](introduction-device-app-lifecycles.md)