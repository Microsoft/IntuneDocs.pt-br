---
title: Portal de solução de problemas de suporte técnico
titleSuffix: Microsoft Intune
description: A equipe de suporte técnico usa o portal de solução de problemas para resolver problemas técnicos dos usuários.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/11/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0094cdd12b2594cb60260d768daec8c5bed04c9c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510259"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Usar o portal de solução de problemas para ajudar os usuários na sua empresa

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O portal de solução de problemas permite que os operadores de suporte técnico e os administradores do Intune exibam informações do usuário para atender às solicitações de ajuda do usuário. As organizações que incluem um suporte técnico podem atribuir o **Operador de suporte técnico** a um grupo de usuários. A função de operador de suporte técnico pode usar o painel **Solucionar problemas**.

O painel **Solução de problemas** também mostra problemas de registro de usuário. Os detalhes sobre o problema e as etapas de correção sugeridas podem ajudar os administradores e os operadores de suporte técnico a solucionar problemas. Determinados problemas de registro não são capturados e alguns erros podem não ter as sugestões de correção.

Para obter etapas de como adicionar uma função de operador de suporte técnico, consulte [RBAC (controle de administração baseado em funções) com o Intune](/intune/role-based-access-control)

Quando um usuário contata o suporte com um problema técnico com o Intune, o operador de suporte técnico insere o nome do usuário. O Intune mostra dados úteis que podem ajudar a solucionar vários problemas da camada 1 incluindo:

- Status do usuário
- Atribuições
- Problemas de conformidade
- O dispositivo não está respondendo
- O dispositivo não consegue obter configurações de VPN ou Wi-Fi
- Falha na instalação do aplicativo

## <a name="to-review-troubleshooting-details"></a>Para examinar os detalhes de solução de problemas

No painel de solução de problemas, escolha **Selecionar usuário** para exibir informações do usuário. As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos.  

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, escolha **Solucionar problemas**.
4. Clique em **Selecionar** para selecionar um usuário cujos problemas serão solucionados.
5. Selecione um usuário digitando o nome ou o endereço de email. Clique em **Selecionar**. As informações de solução de problemas do usuário são mostradas no painel Solução de problemas. A tabela a seguir explica as informações.

> [!Note]  
> Você também pode acessar o painel **solução de problemas** apontando o navegador para: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Áreas do painel de solução de problemas

Você pode usar o painel **Solucionar problemas** para examinar as informações do usuário.

![Painel de solução de problemas, com áreas numeradas descritas na tabela a seguir](./media/help-desk-operators/troubleshooting-dash.png)

| Área | Nome | Descrição |
| ---  | ---  | ---         |
| 1.   | Status da conta  | Mostra o status do locatário do Intune atual como **Ativo** ou **Inativo**.       |
| 2.   | Seleção de usuários  | O nome do usuário selecionado no momento. Clique em **Alterar usuário** para escolher um novo usuário.       |
| 3.   | Status do usuário  | Exibe o status da licença do Intune do usuário, o número de dispositivos, a conformidade de cada dispositivo, o número de aplicativos e a conformidade dos aplicativos.       |
| 4.   | Informações do usuário  | Use a lista para selecionar os detalhes a serem examinados no painel. <br>Você pode selecionar: <ul><li>Aplicativos cliente<li>Políticas de conformidade<li> Políticas de configuração<li>Políticas de proteção do aplicativo <li>Restrições de registro</ul>      |
| 5.   | Associação de grupo  | Mostra os grupos atuais dos quais o usuário selecionado é membro.       |

<!-- this section needs to be updated

## Client apps reference

The apps that are running devices
- managed by Intune and Azure Active Directory (AD) 
- owned by users managed by Intune and Azure Active Directory (AD).

### Properties

The properties of client apps.

| Property      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name          | The name of the application.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| OS            | The operating system installed on the device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Type          | You can choose an assignment type for each app.  <br> **Available** - Users install the app from the Company Portal app or website.  <br> **Not Applicable** - The app is not installed or shown in the Company Portal. <br> **Uninstall** - The app is uninstalled from devices in the selected groups.  <br> **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. |
| Last Modified | The name of the type of device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| App install | Denotes whether an app install failure or success has occurred on the individual device. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection status

An app protection policy is available to mobile apps that integrate with Enterprise Mobility Solution (EMS) technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## App protection policies reference

An app protection policy is available to mobile apps that integrate with EMS technologies.These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

### Properties

The table summarizes app protection policies status for devices managed by Intune.

| Property    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Name        | The name of the application.                                                                                                        |
| Deployed    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Platform    | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Enrollment  | The name of the type of device.                                                                                                     |
| Last Update | The timestamp the policy was modified.                                                                                              |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device Name        | The name of the type of device.                                                                                                     |
| Managed By         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last Check in      | The name of the type of device.                                                                                                     |

## Compliance policies reference

Makes sure that the devices used to access company apps and data, comply with certain rules like using a PIN to access the device, and encryption of data stored on the device.

### Properties

The properties of the compliance policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## Configuration policies reference

An app configuration policy is available to mobile apps with vendor-specific configuration. 

### Properties

The properties of the configuration policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |


### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

-->

## <a name="enrollment-failure-reference"></a>Referência de falha de registro

A tabela Falhas de Registro lista as tentativas de registro que falharam. Um dispositivo listado na tabela a seguir pode ter sido registrado com êxito posteriormente durante outra tentativa. Algumas tentativas com falha não podem ser listadas. As informações de mitigação não estão disponíveis para todas as falhas.

| Coluna da tabela | Descrição |
|-------------|----------|
| Início do registro | A hora de início quando o usuário iniciou o registro. |
| SO | O sistema operacional do dispositivo. |
| Versão do SO | A versão do sistema operacional do dispositivo. |
| Falha | O motivo da falha. |

### <a name="failure-details"></a>Detalhes da falha

Quando você escolhe uma linha de falha, mais detalhes são fornecidos.

| Seção | Descrição |
|-------------|----------|
| Detalhes da falha | Uma explicação mais detalhada da falha. |
| Possíveis correções | As etapas sugeridas para resolver o erro. Algumas falhas podem não ter correção. |
| Recursos (opcional) | Links para leitura adicional ou áreas no portal para agir. |

### <a name="enrollment-errors"></a>Erros de registro

| Erro do | Detalhes |
|-------------|----------|
| Tempo limite excedido ou falha de iOS | O tempo limite foi excedido entre o dispositivo e o Intune porque o usuário demorou muito para concluir o registro. |
| O usuário não foi encontrado nem licenciado | O usuário não tem uma licença ou foi removido do serviço. |
| Dispositivo já registrado | Alguém tentou registrar um dispositivo usando o Portal da empresa em um dispositivo que ainda está registrado por outro usuário. |
| Não integrado ao Intune | Ocorreu uma tentativa de registro quando a autoridade de MDM (gerenciamento de dispositivo móvel) do Intune não estava configurada. |
| Falha de autorização de registro | Ocorreu uma tentativa de registro usando uma versão antiga do portal da empresa. |
| Dispositivo incompatível | O dispositivo não cumpre os requisitos mínimos para registro no Intune. |
| Restrições de registro não cumpridas | Esse registro foi bloqueado devido a uma restrição de registro configurada pelo administrador. |
| Versão de dispositivo muito anterior | O administrador configurou uma restrição de registro que exige uma versão posterior do dispositivo. |
| Versão de dispositivo muito posterior | O administrador configurou uma restrição de registro que exige uma versão anterior do dispositivo. |
| O dispositivo não pode ser registrado como pessoal | O administrador configurou uma restrição de registro para bloquear registros pessoais e o dispositivo com falha não foi predefinido como corporativo. |
| Plataforma de dispositivo bloqueada | O administrador configurou uma restrição de registro que bloqueia a plataforma do dispositivo. |
| Token em massa expirado | O token em massa no pacote de provisionamento expirou. |
| Dispositivo Autopilot ou detalhes não encontrados | O dispositivo Autopilot não foi encontrado ao tentar se registrar. |
| Perfil do Autopilot não encontrado ou não atribuído | O dispositivo não tem um perfil ativo do Autopilot. |
| Método de registro inesperado do Autopilot | O dispositivo tentou se registrar usando um método não permitido. |
| Dispositivo Autopilot removido | O dispositivo que está tentando se registrar foi removido do Autopilot para esta conta. |
| Limite do dispositivo associado | Esse registro foi bloqueado devido a uma restrição de limite de registro configurada pelo administrador. |
| Integração de Apple | Todos os dispositivos iOS foram impedidos de se registrar no momento devido à ausência ou expiração de um Apple MDM Push Certificate no Intune. |
| Dispositivo não pré-registrado | O dispositivo não foi previamente registrado como corporativo e todos os registros pessoais foram bloqueados por um administrador. |
| Recurso incompatível | O usuário provavelmente tentou fazer o registro por um método incompatível com a configuração do Intune. |

## <a name="collect-available-data-from-mobile-device"></a>Coletar dados disponíveis do dispositivo móvel

Use os seguintes recursos para ajudar a coletar dados de dispositivo ao solucionar problemas de dispositivo do usuário:
- [Enviar erros de registro do iOS para o administrador de TI](/intune-user-help/send-errors-to-your-it-admin-ios)
- [Ajudar o suporte de sua empresa a corrigir problemas do dispositivo com o log detalhado](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
- [Enviar logs do Android para o suporte de sua empresa usando um cabo USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
- [Enviar logs de dados de diagnóstico do Android para o administrador de TI usando o email](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
- [Enviar erros de registro do Android para o administrador de TI](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Próximas etapas

Você pode aprender mais sobre o RBAC (controle de administração baseado em função) para definir funções no dispositivo organizacional, no gerenciamento de aplicativos móveis e nas tarefas de proteção de dados. Para obter mais informações, consulte [RBAC (controle de administração baseado em funções) com o Intune](/intune/role-based-access-control).

Saiba mais sobre os problemas conhecidos do Microsoft Intune. Para obter mais informações, consulte [Problemas conhecidos no Microsoft Intune](/intune/known-issues).

Saiba como criar um tíquete de suporte e obter ajuda sempre que precisar. [Obter suporte](/intune/get-support).
