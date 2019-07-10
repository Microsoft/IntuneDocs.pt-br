---
title: Configurar conformidade do dispositivo e do aplicativo durante uma migração do Intune
titleSuffix: Microsoft Intune
description: Este artigo fornece as etapas necessárias para configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativo durante uma migração do Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 86aefbfc37db7929f9748d4783db319cf97d4545
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548458"
---
# <a name="configure-device-compliance-and-app-management-policies-when-migrating-to-microsoft-intune"></a>Configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativo durante uma migração para o Microsoft Intune

A principal meta ao migrar para o Intune é registrar todos os dispositivos no Intune e torná-los em conformidade com suas políticas. As políticas de dispositivo não só ajudam você a gerenciar dispositivos de usuário corporativos, mas também dispositivos pessoais (BYOD) e compartilhados, como quiosques, máquinas de ponto de venda, tablets compartilhados por vários alunos em uma sala de aula ou dispositivos sem usuários (somente iOS).

Cada plataforma de dispositivo pode oferecer configurações diferentes, mas as políticas de dispositivo do Intune trabalham com cada uma delas para fornecer os seguintes recursos de gerenciamento de dispositivo móvel:

- Controle do número de dispositivos que cada usuário registra.

- Gerenciar configurações de dispositivos (por exemplo, criptografia no nível do dispositivo, tamanho da senha e uso de câmera).

- Entregar aplicativos, perfis de email, perfis de VPN e assim por diante.

- Avaliação de critérios no nível do dispositivo para as políticas de conformidade de segurança.

> [!IMPORTANT]
> As políticas de gerenciamento de dispositivo não são atribuídas diretamente aos dispositivos ou usuários individuais, em vez disso, são atribuídas a grupos de usuários. As políticas podem ser aplicadas diretamente a um grupo de usuários e, portanto, para o dispositivo de usuário ou podem ser aplicadas a um grupo de dispositivos e, portanto, aos membros do grupo.

## <a name="task-list-for-device-compliance-policies"></a>Lista de tarefas para políticas de conformidade do dispositivo

### <a name="task-1-add-device-groups-optional"></a>Tarefa 1: Adicionar grupos de dispositivos (opcional)

Você poderá criar grupos de dispositivos quando precisar realizar tarefas administrativas com base na identidade do dispositivo, em vez de na identidade do usuário.

Os grupos de dispositivos são úteis para o gerenciamento de dispositivos que não têm usuários dedicados, como dispositivos de quiosque, dispositivos compartilhados por colegas de turno ou dispositivos atribuídos a um local específico.

Ao configurar grupos de dispositivos antes do registro do dispositivo, você pode usar categorias de dispositivo para ingressar automaticamente os dispositivos nos grupos após o registro. Em seguida, eles receberão as políticas de dispositivo do seu grupo automaticamente. [Introdução aos grupos](groups-get-started.md).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Tarefa 2: Usar perfis de acesso aos recursos (Wi-Fi, VPN e certificados de email)

Os perfis de acesso aos recursos fornecem certificados e configurações de acesso a dispositivos registrados. Se você estiver usando autenticação baseada em certificado, [configure os certificados](certificates-configure.md).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Tarefa 3: Criar e implantar perfis de configuração de dispositivo

Você precisa criar um perfil de configuração de dispositivo para impor as configurações no nível do dispositivo, por exemplo: desabilitar a câmera, loja de aplicativos, configurar o modo de aplicativo único, tela inicial e assim por diante. Saiba mais sobre [perfis de dispositivo](device-profiles.md).

#### <a name="directly-import-ios-configuration-profiles-optional"></a>Importar diretamente perfis de configuração do iOS (opcional)

- **Perfis do Apple Configurator iOS (iOS 7.1 e posterior):** se a solução de MDM existente usar perfis do Apple Configurator (arquivos .mobileconfig), o Intune poderá importá-las diretamente como políticas de configuração personalizadas.

- **Políticas de configuração de aplicativos móveis do iOS:** se a solução de MDM existente usar políticas de configuração de aplicativos móveis do iOS, o Intune poderá importá-las diretamente desde que atendam ao formato XML especificado pela Apple para listas de propriedades.

- Saiba como adicionar uma política personalizada para [iOS](custom-settings-ios.md).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Tarefa 4: Criar e implantar uma política de conformidade do dispositivo (opcional)

As políticas de conformidade do dispositivo avaliam as configurações orientadas a segurança e fornecem relatórios que mostram se os dispositivos são compatíveis com os padrões corporativos ou não. Essas configurações incluem:

- Tamanho do PIN

- Status desbloqueado

- Versão do SO

Confira os recursos adicionais para configurações de conformidade do dispositivo:

- Saiba mais sobre [políticas de conformidade do dispositivo](device-compliance.md).

- Saiba [como criar uma política de conformidade do dispositivo](device-compliance-get-started.md).

### <a name="task-5-publish-and-deploy-apps"></a>Tarefa 5: Publicar e implantar aplicativos

Com o Intune MDM, você pode fornecer aplicativos exigindo a instalação automática deles ou disponibilizá-los no Portal da Empresa.

- [Como adicionar aplicativos](apps-add.md).

- [Como implantar aplicativos](apps-deploy.md).

### <a name="task-6-enable-device-enrollment"></a>Tarefa 6: Habilitar registro de dispositivo

O registro de dispositivo é necessário para gerenciar o dispositivo. Saiba [como se preparar para registrar dispositivos corporativos e pessoais](device-enrollment.md).

## <a name="next-steps"></a>Próximas etapas

[Configurar políticas de proteção de aplicativo (opcional)](migration-guide-app-protection-policies.md).
