---
title: Políticas de configuração de aplicativo do Microsoft Intune
titleSuffix: ''
description: Saiba como usar políticas de configuração de aplicativo em um dispositivo iOS ou Android no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 10dad24ee41f63dcc304d95e9b733f7de3f1b71a
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2019
ms.locfileid: "67649033"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Políticas de configuração de aplicativo do Microsoft Intune

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer definições de configuração para um aplicativo iOS ou Android. Essas configurações permitem que um aplicativo seja personalizado usando uma abordagem padrão do setor para gerenciamento e configuração de aplicativos. As definições da política de configuração são usadas quando o aplicativo verifica se elas existem, normalmente, na primeira vez em que ele é executado.

Você pode atribuir uma política de configuração de aplicativo a um grupo de usuários e dispositivos usando uma combinação de atribuições de inclusão e exclusão. Depois de adicionar uma política de configuração de aplicativo, você pode definir as atribuições para política de configuração de aplicativo. Ao definir as atribuições para a política, você pode optar por incluir ou excluir os grupos de usuários para os quais a política se aplica. Ao optar por incluir um ou mais grupos, você pode optar por selecionar grupos específicos para incluir ou selecionar grupos internos. Os grupos internos incluem **Todos os Usuários**, **Todos os Dispositivos** e **Todos os Usuários + Todos os Dispositivos**.

Por exemplo, uma configuração de aplicativos pode exigir que você especifique um dos seguintes detalhes:

- Um número de porta personalizado
- Configurações de idioma
- Configurações de segurança
- Configurações de identidade visual, como um logotipo da empresa

Se os usuários tivessem que inserir essas configurações, eles poderiam fazer isso incorretamente, o que poderia aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

As políticas de configuração de aplicativos podem ajudar a eliminar os problemas de instalação do aplicativo ao permitir que você atribua configurações a uma política atribuída aos usuários antes da execução do aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

As definições de configuração são usadas sempre que o aplicativo verifica a existência delas. Normalmente, um aplicativo verifica as definições de configuração na primeira vez em que é executado pelo usuário.

Você tem duas opções de como usar as configurações do aplicativo com o Intune:
 - **Dispositivos gerenciados** – o dispositivo é gerenciado pelo Intune como o provedor de MDM (gerenciamento de dispositivo móvel).
 - **Aplicativos gerenciados** – um aplicativo é gerenciado sem registro de dispositivos.

> [!NOTE]
> Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. Os aplicativos de suporte processam a configuração do aplicativo, removem e bloqueiam contas não aprovadas.

## <a name="apps-that-support-app-configuration"></a>Aplicativos que dão suporte à configuração de aplicativo

### <a name="managed-devices"></a>Dispositivos gerenciados
Você pode usar políticas de configuração de aplicativo para aplicativos que dão suporte a elas. Para dar suporte à configuração de aplicativos no Intune, os aplicativos precisam ter suporte ao uso de configurações de aplicativo como definido na [Comunidade Appconfig](https://www.appconfig.org/members). Consulte o fornecedor do aplicativo para obter mais detalhes.

### <a name="managed-apps"></a>Aplicativos gerenciados
É possível preparar seus aplicativos de linha de negócios incorporando o SDK de Aplicativo do Intune no aplicativo ou encapsulando o aplicativo ele ser desenvolvido. O SDK de Aplicativo do Intune, disponível para iOS e Android, habilita o aplicativo para as políticas de configuração de proteção de aplicativo do Intune. Ele se esforça para minimizar a quantidade de alterações de código necessárias do desenvolvedor do aplicativo. Para obter mais informações, consulte a [Visão geral do SDK de Aplicativo do Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Suporte de API do Graph para configuração de aplicativo

Além disso, você pode usar a API do Graph para realizar as tarefas de configuração de aplicativo. Para saber mais, confira [Configuração direcionada do MAM na referência da API do Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Próximas etapas

### <a name="managed-devices"></a>Dispositivos gerenciados

 - Saiba como usar a configuração de aplicativo com seus dispositivos iOS.  Confira [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md).
 - Saiba como usar a configuração de aplicativo com seus dispositivos Android.  Consulte [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplicativos gerenciados

 - Saiba como usar a configuração de aplicativo com aplicativos gerenciados. Consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).
