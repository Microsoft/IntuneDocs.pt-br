---
title: "Configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativo durante uma migração do Intune"
description: "A finalidade deste artigo é mostrar as etapas necessárias para configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativo durante uma migração do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5e848dda6643a28141a8f5f1d0bdc01f2bd9d390
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-device-compliance-and-app-management-policies"></a>Configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativos

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

O principal objetivo ao migrar para o Intune é registrar todos os dispositivos e torná-l-os compatíveis com suas políticas. As políticas de dispositivo não só ajudam você a gerenciar dispositivos de usuário corporativos, mas também dispositivos pessoais (BYOD) e compartilhados, como quiosques, máquinas de ponto de venda, tablets compartilhados por vários alunos em uma sala de aula ou dispositivos sem usuários (somente iOS).

Cada plataforma de dispositivo pode oferecer configurações diferentes, mas as políticas de dispositivo do Intune trabalham com cada uma delas para fornecer os seguintes recursos de gerenciamento de dispositivo móvel:

-   Controle do número de dispositivos que cada usuário registra.

-   Gerenciamento das configurações de dispositivos (por exemplo, criptografia no nível de dispositivo, comprimento da senha, uso de câmera).

-   Entrega de aplicativos, perfis de email, perfis de VPN etc.

-   Avaliação de critérios no nível do dispositivo para as políticas de conformidade de segurança.

> [!IMPORTANT]
> As políticas de gerenciamento de dispositivo não são atribuídas diretamente aos dispositivos ou usuários individuais, em vez disso, são atribuídas a grupos de usuários. As políticas podem ser aplicadas diretamente a um grupo de usuários e, portanto, para o dispositivo de usuário, ou podem ser aplicadas a um grupo de dispositivos e, portanto, aos membros do grupo.

## <a name="task-list-for-device-compliance-policies"></a>Lista de tarefas para políticas de conformidade do dispositivo

### <a name="task-1-add-device-groups-optional"></a>Tarefa 1: Adicionar grupos de dispositivos (opcional)

Você poderá criar grupos de dispositivos quando precisar realizar várias tarefas administrativas com base na identidade do dispositivo, em vez de na identidade do usuário.

Os grupos de dispositivos são úteis para o gerenciamento de dispositivos sem usuários dedicados, como dispositivos de quiosque ou dispositivos compartilhados por colegas de turno ou atribuídos a um local específico.

Ao configurar grupos de dispositivos antes do registro do dispositivo, você pode aproveitar as categorias dos dispositivos para agrupar automaticamente os dispositivos no registro a fim de receber automaticamente as políticas de dispositivo do grupo. [Introdução aos grupos](/intune/groups-get-started).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Tarefa 2: Usar perfis de acesso aos recursos (Wi-Fi, VPN e certificados de email)

Os perfis de acesso aos recursos provisionam certificados e configurações de acesso a dispositivos registrados.

Conforme abordado anteriormente na seção Avaliar os requisitos de MDM, se você estiver usando a autenticação baseada em certificado, [configure certificados](/intune/certificates-configure).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Tarefa 3: Criar e implantar perfis de configuração de dispositivo

Você precisa criar um perfil de configuração de dispositivo para impor as configurações no nível do dispositivo, por exemplo: desabilitar a câmera, loja de aplicativos, configurar o modo de aplicativo único, tela inicial etc.

- Saiba mais sobre [perfis de dispositivo](/intune/device-profiles).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Importação direta de perfis de configuração do iOS (opcional)

-   **Perfis do Apple Configurator iOS (iOS 7.1 e posterior):** se a solução de MDM existente usar perfis do Apple Configurator (arquivos .mobileconfig), o Intune poderá importá-las diretamente como políticas de configuração do cliente.

-   **Políticas de configuração de aplicativos móveis do iOS:** se a solução de MDM existente usar políticas de configuração de aplicativos móveis do iOS, o Intune poderá importá-las diretamente desde que atendam ao formato XML especificado pela Apple para listas de propriedades.

- Saiba como adicionar uma política personalizada para [iOS](/intune/custom-settings-ios)

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Tarefa 4: Criar e implantar uma política de conformidade do dispositivo (opcional)

As políticas de conformidade do dispositivo avaliam as configurações orientadas a segurança e fornecem relatórios que mostram se os dispositivos são compatíveis com os padrões corporativos ou não. As políticas de conformidade do dispositivo avaliam fatores de segurança orientados a segurança, como:

-   Tamanho do PIN

-   Status desbloqueado

-   Versão do SO

Confira os recursos adicionais para configurações de conformidade do dispositivo:

-   Saiba mais sobre [políticas de conformidade do dispositivo](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Saiba [como criar uma política de conformidade do dispositivo](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Tarefa 5: Publicar e implantar aplicativos

Com o Intune MDM, você pode provisionar aplicativos exigindo a instalação automática deles, ou disponibilizá-los no Portal da Empresa.

-   Saiba [como adicionar aplicativos](/intune-classic/deploy-use/add-apps).

-   Saiba [como implantar aplicativos](/intune-classic/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Tarefa 6: Habilitar o registro de dispositivo

O registro estabelece o gerenciamento pelo provisionamento de controle no dispositivo. Saiba [como se preparar para registrar dispositivos corporativos e pessoais](/intune/device-enrollment).

## <a name="next-steps"></a>Próximas etapas 

[Configurar Políticas de Proteção de Aplicativo (opcional)](migration-guide-app-protection-policies.md)
