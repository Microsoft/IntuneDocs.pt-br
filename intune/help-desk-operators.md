---
title: Portal de solução de problemas de suporte técnico
titlesuffix: Microsoft Intune
description: A equipe de suporte técnico usa o portal de solução de problemas para resolver problemas técnicos dos usuários.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/23/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba74c93e2ef7dc469ebd7f5086659181b72a0981
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230016"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Usar o portal de solução de problemas para ajudar os usuários na sua empresa

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Solucionar problemas**.
4. Clique em **Selecionar** para selecionar um usuário cujos problemas serão solucionados.
5. Selecione um usuário digitando o nome ou o endereço de email. Clique em **Selecionar**. As informações de solução de problemas do usuário são mostradas no painel Solução de problemas. A tabela a seguir explica as informações.

> [!Note]  
> Você também pode acessar o painel **solução de problemas** apontando o navegador para: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Áreas do painel de solução de problemas

Você pode usar o painel **Solucionar problemas** para examinar as informações do usuário.

![](/intune/media/troubleshooting-dash.png)

| Área | Nome | Descrição |
| ---  | ---  | ---         |
| 1.   | Status da conta  | Mostra o status do locatário do Intune atual como **Ativo** ou **Inativo**.       |
| 2.   | Seleção de usuários  | O nome do usuário selecionado no momento. Clique em **Alterar usuário** para escolher um novo usuário.       |
| 3.   | Status do usuário  | Exibe o status da licença do Intune do usuário, o número de dispositivos, a conformidade de cada dispositivo, o número de aplicativos e a conformidade dos aplicativos.       |
| 4.   | Informações do usuário  | Use a lista para selecionar os detalhes a serem examinados no painel. <br>Você pode selecionar: <ul><li>Aplicativos cliente<li>Políticas de conformidade<li> Políticas de configuração<li>Políticas de proteção do aplicativo <li>Restrições de registro</ul>      |
| 5.   | Associação de grupo  | Mostra os grupos atuais dos quais o usuário selecionado é membro.       |

## <a name="client-apps-reference"></a>Referência de aplicativos cliente

Os aplicativos que são executados nos dispositivos
- gerenciados pelo Intune e o AD (Azure Active Directory) 
- pertencente aos usuários gerenciados pelo Intune e o AD (Azure Active Directory).

### <a name="properties"></a>Propriedades

As propriedades dos aplicativos cliente.

| Propriedade      | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nome          | O nome do aplicativo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| SO            | O sistema operacional instalado no dispositivo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Tipo          | Você pode escolher um tipo de atribuição para cada aplicativo.  <br> **Disponível** – Os usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa.  <br> **Não Aplicável** – O aplicativo não é instalado nem é mostrado no Portal da Empresa. <br> **Desinstalar** – O aplicativo é desinstalado dos dispositivos nos grupos selecionados.  <br> **Disponível com ou sem registro** – Atribua este aplicativo a grupos de usuários cujos dispositivos não são registrados com o Intune. |
| Última modificação | O nome do tipo de dispositivo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Dispositivos

Dispositivos gerenciados pelo Intune ou por usuários gerenciados pelo Intune ou pelo Azure AD.

| Propriedade           | Descrição                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nome do dispositivo        | O nome do tipo de dispositivo.                                                                                                     |
| Gerenciado por         | O carimbo de data/hora em que a política foi modificada.                                                                                              |
| Tipo de ingresso no Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Propriedade          | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**).                                               |
| Em conformidade com o Intune   | O nome do tipo de dispositivo.                                                                                                     |
| Em conformidade com o Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Instalação do aplicativo | Indica se ocorreu êxito ou falha na instalação de um aplicativo no dispositivo individual. |
| SO                 | O sistema operacional instalado no dispositivo.                                                                                       |
| Versão do SO         | O número de versão do sistema operacional do dispositivo.                                                                                  |
| Último check-in      | O nome do tipo de dispositivo.                                                                                                     |

### <a name="app-protection-status"></a>Status de proteção do aplicativo

Uma política de proteção do aplicativo está disponível para aplicativos móveis que se integram a tecnologias EMS (Enterprise Mobility Solution). Essas políticas fornecem uma linha de base de proteção para os dados corporativos quando eles são baixados em aplicativos móveis, incluindo os aplicativos móveis do Office. 

| Propriedade    | Descrição                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**). |
| Nome do aplicativo    | O nome do aplicativo                                                           |
| Nome do dispositivo | O nome do tipo de dispositivo.                                                       |
| Tipo de dispositivo | O nome do tipo de dispositivo.                                                       |
| Políticas    | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**). |
| Última sincronização   | O carimbo de data/hora da última vez em que o dispositivo foi sincronizado com o Intune.                   |

## <a name="app-protection-policies-reference"></a>Referência de políticas de proteção do aplicativo

Uma política de proteção de aplicativo está disponível para aplicativos móveis que se integram a tecnologias EMS. Essas políticas oferecem uma linha de base de proteção para seus dados corporativos quando ele é baixado em aplicativos móveis, incluindo aplicativos móveis do Office. 

### <a name="properties"></a>Propriedades

A tabela resume o status das políticas de proteção do aplicativo para dispositivos gerenciados pelo Intune.

| Propriedade    | Descrição                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nome        | O nome do aplicativo.                                                                                                        |
| Implantado    | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Plataforma    | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**).                                               |
| Registro  | O nome do tipo de dispositivo.                                                                                                     |
| Última atualização | O carimbo de data/hora em que a política foi modificada.                                                                                              |

### <a name="devices"></a>Dispositivos

Dispositivos gerenciados pelo Intune ou por usuários gerenciados pelo Intune ou pelo Azure AD.

| Propriedade           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nome do Dispositivo        | O nome do tipo de dispositivo.                                                                                                     |
| Gerenciados por         | O carimbo de data/hora em que a política foi modificada.                                                                                              |
| Tipo de ingresso no Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Propriedade          | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**).                                               |
| Em conformidade com o Intune   | O nome do tipo de dispositivo.                                                                                                     |
| Em conformidade com o Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Em conformidade com o Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| SO                 | O sistema operacional instalado no dispositivo.                                                                                       |
| Versão do SO         | O número de versão do sistema operacional do dispositivo.                                                                                  |
| Último Check-in      | O nome do tipo de dispositivo.                                                                                                     |

## <a name="compliance-policies-reference"></a>Referência de políticas de conformidade

Verifique se os dispositivos usados para acessar os aplicativos e os dados da empresa estão em conformidade com determinadas regras, como usar um PIN para acessar o dispositivo e a criptografia de dados armazenados no dispositivo.

### <a name="properties"></a>Propriedades

As propriedades das políticas de conformidade.

| Propriedade      | Descrição                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Atribuição    | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Nome          | O nome do aplicativo.                                                                                                        |
| SO            | O sistema operacional instalado no dispositivo.                                                                                       |
| Tipo de política   | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** e **Desconhecido**).                                               |
| Última modificação | O nome do tipo de dispositivo.                                                                                                     |

### <a name="devices"></a>Dispositivos

Dispositivos gerenciados pelo Intune ou por usuários gerenciados pelo Intune ou pelo Azure AD.

| Propriedade           | Descrição                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nome do dispositivo        | O nome do tipo de dispositivo.                                                                                                     |
| Gerenciado por         | O carimbo de data/hora em que a política foi modificada.                                                                                              |
| Tipo de ingresso no Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Propriedade          | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** e **Desconhecido**).                                               |
| Em conformidade com o Intune   | O nome do tipo de dispositivo.                                                                                                     |
| Em conformidade com o Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| SO                 | O sistema operacional instalado no dispositivo.                                                                                       |
| Versão do SO         | O número de versão do sistema operacional do dispositivo.                                                                                  |
| Último check-in      | O nome do tipo de dispositivo.                                                                                                     |

### <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

Uma política de proteção do aplicativo está disponível para aplicativos móveis que se integram a tecnologias EMS. Essas políticas fornecem uma linha de base de proteção para os dados corporativos quando eles são baixados em aplicativos móveis, incluindo os aplicativos móveis do Office. 

| Propriedade    | Descrição                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**). |
| Nome do aplicativo    | O nome do aplicativo                                                           |
| Nome do dispositivo | O nome do tipo de dispositivo.                                                       |
| Tipo de dispositivo | O nome do tipo de dispositivo.                                                       |
| Políticas    | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**). |
| Última sincronização   | O carimbo de data/hora da última vez em que o dispositivo foi sincronizado com o Intune.                   |

## <a name="configuration-policies-reference"></a>Referência de políticas de configuração

Uma política de configuração de aplicativo está disponível para aplicativos móveis com configurações específicas do fornecedor. 

### <a name="properties"></a>Propriedades

As propriedades das políticas de configuração.

| Propriedade      | Descrição                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Atribuição    | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Nome          | O nome do aplicativo.                                                                                                        |
| SO            | O sistema operacional instalado no dispositivo.                                                                                       |
| Tipo de política   | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**).                                               |
| Última modificação | O nome do tipo de dispositivo.                                                                                                     |

### <a name="devices"></a>Dispositivos

Dispositivos gerenciados pelo Intune ou por usuários gerenciados pelo Intune ou pelo Azure AD.

| Propriedade           | Descrição                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nome do dispositivo        | O nome do tipo de dispositivo.                                                                                                     |
| Gerenciado por         | O carimbo de data/hora em que a política foi modificada.                                                                                              |
| Tipo de ingresso no Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| Propriedade          | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**).                                               |
| Em conformidade com o Intune   | O nome do tipo de dispositivo.                                                                                                     |
| Em conformidade com o Azure AD | O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**. |
| SO                 | O sistema operacional instalado no dispositivo.                                                                                       |
| Versão do SO         | O número de versão do sistema operacional do dispositivo.                                                                                  |
| Último check-in      | O nome do tipo de dispositivo.                                                                                                     |


### <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

Uma política de proteção do aplicativo está disponível para aplicativos móveis que se integram a tecnologias EMS. Essas políticas fornecem uma linha de base de proteção para os dados corporativos quando eles são baixados em aplicativos móveis, incluindo os aplicativos móveis do Office. 

| Propriedade    | Descrição                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**). |
| Nome do aplicativo    | O nome do aplicativo                                                           |
| Nome do dispositivo | O nome do tipo de dispositivo.                                                       |
| Tipo de dispositivo | O nome do tipo de dispositivo.                                                       |
| Políticas    | O tipo de propriedade do dispositivo (**Empresa**, **Pessoal** ou **Desconhecido**). |
| Última sincronização   | O carimbo de data/hora da última vez em que o dispositivo foi sincronizado com o Intune.                   |

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
