---
title: "RBAC (controle de acesso baseado em função) para o Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como o RBAC permite controlar quem pode executar ações e fazer alterações."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f4a80949dafbd3acc0413c75bbb0b8b5f5ae5664
ms.openlocfilehash: 2507626d23beece9723134191e8747f731478ddb
ms.lasthandoff: 02/23/2017


---

# <a name="role-based-access-control-rbac-for-microsoft-intune"></a>RBAC (controle de acesso baseado em função) para o Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Em termos simples, **funções** (ou RBAC) do Intune ajudam a controlar quem pode executar várias ações do Intune e a quem essas ações se aplicam. Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções.

Uma função é definida por:

- **Definição** – O nome de uma função e as permissões que ela configura.
- **Membros** – O usuário ou grupo de usuários que receberão essas permissões.
- **Escopo** – Os usuários ou dispositivos que uma pessoa especificada (o membro) pode gerenciar.
- **Atribuição** – Após a definição, os membros e o escopo serem configurados, a função será atribuída.

## <a name="built-in-roles"></a>Funções internas

As seguintes são funções internas do Intune e você pode personalizá-las ou atribuí-las a grupos sem qualquer configuração adicional.

- **Administrador do Intune** – Tem permissões completas para executar todas as operações do Intune.
- **Gerenciador de Aplicativos** – Gerenciar e implantar aplicativos e perfis.
- **Gerenciador de Políticas de Configuração** – Gerenciar e implantar definições de configurações e perfis.
- **Operador de assistência técnica** – realizar tarefas remotas e exibir informações do usuário e do dispositivo.
- **Operador somente leitura** – Exibir informações no Portal do Intune sem a capacidade de fazer alterações.


## <a name="custom-roles"></a>Funções personalizadas

Se nenhuma das funções internas atende às suas necessidades, você pode criar sua própria função escolhendo configurações que se estendem por vários dos recursos do Intune. Você poderá ver uma lista das configurações disponíveis posteriormente neste tópico.

### <a name="example"></a>Exemplo

Você contrata um novo administrador de TI que será responsável pela implantação e gerenciamento de aplicativos para usuários em seu escritório de Londres. Os usuários estão em um grupo do Azure AD chamado **Londres**. Você deseja garantir que o administrador de TI não pode implantar aplicativos para usuários de nenhum outro escritório. Você realiza as seguintes ações:

- Atribua a função **Gerenciador de Aplicativos** interna com as seguintes propriedades:
    - **Membros** – Selecione um grupo que contém o administrador de TI que implantará aplicativos
    - **Escopo** – Selecione o grupo **Londres** do Azure AD.

    >[!IMPORTANT]
    >Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
    >- **Administrador Global de AAD**
    >- **Administrador de Serviço do Intune**

### <a name="how-to-create-a-custom-role"></a>Como criar uma função personalizada

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha do **Intune**, escolha **Controle de acesso**.
![Carga de trabalho de controle de acesso](./media/axxess-control.png)
1. Na folha **Funções** da carga de trabalho **Controle de acesso**, escolha **Adicionar personalizado**.
2. Na folha **Adicionar Função Personalizada**, insira um nome e uma descrição para a nova função e clique em **Permissões**.
3. Na folha **Permissões**, escolha as permissões que você deseja usar com essa função. Use a lista de referência de configurações de função personalizada posteriormente neste tópico para ajudá-lo.
4. Quando terminar, clique em **OK**.
5. Na folha **Adicionar Função Personalizada**, clique em **Criar**.

A nova função é exibida na lista na folha **Funções**.

## <a name="how-to-assign-a-role"></a>Como atribuir uma função

1. Na folha **Funções** da carga de trabalho **Controle de acesso**, escolha a função interna ou personalizada que você deseja atribuir.
2. Na folha <*nome da função*> – **Propriedades**, escolha **Gerenciar** > **Atribuições**.
    >[!TIP]
    >Nessa folha, também é possível editar ou excluir funções existentes.
3. Na próxima folha, escolha **Atribuir**.
4. Na folha **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e, em seguida, escolha o seguinte:
    - **Membros** – Selecione um grupo que contém o usuário para o qual você deseja conceder permissões.
    - **Escopo** – Selecione um grupo que contém os usuários que o membro acima terá permissão para gerenciar.
5. Quando terminar, clique em **OK**.

A nova atribuição é exibida na lista de atribuições.

## <a name="custom-role-settings-reference"></a>Referência de configurações de função personalizada

Ao criar uma função personalizada, é possível definir uma ou mais das seguintes configurações:

### <a name="device-configurations"></a>Configurações do dispositivo

|||
|-|-|
|**Atribuir**|Atribuir perfis de dispositivo aos grupos.|
|**Criar**|Criar perfis de dispositivo.|
|**Excluir**|Excluir perfis de dispositivo.|
|**Ler**|Ler perfis de dispositivo e suas propriedades.|
|**Atualizar**|Atualizar os perfis de dispositivo existentes.|

### <a name="managed-apps"></a>Aplicativos gerenciados

|||
|-|-|
|**Atribuir**|Atribuir aplicativos gerenciados a grupos.|
|**Criar**|Adicionar novos aplicativos gerenciados ao Intune.|
|**Excluir**|Excluir aplicativos gerenciados.|
|**Ler**|Ler os aplicativos gerenciados e suas propriedades.|
|**Atualizar**|Atualizar os aplicativos gerenciados existentes.|
|**Apagamento**|Apagar aplicativos gerenciados dos dispositivos.|

### <a name="managed-devices"></a>Dispositivos gerenciados

|||
|-|-|
|**Excluir**|Excluir dispositivos gerenciados do Intune.|
|**Ler**|Exibir informações sobre dispositivos gerenciados no Portal do Intune.|
|**Atualizar**|Atualizar informações sobre dispositivos gerenciados.|

### <a name="mobile-apps"></a>Aplicativos móveis

|||
|-|-|
|**Atribuir**|Atribuir aplicativos móveis a grupos.|
|**Criar**|Adicionar novos aplicativos móveis ao Intune.|
|**Excluir**|Excluir aplicativos móveis.|
|**Ler**|Ler os aplicativos móveis e suas propriedades.|
|**Atualizar**|Atualizar os aplicativos móveis existentes.|

### <a name="organization"></a>Organização

|||
|-|-|
|**Ler**|Ler as configurações de locatário.|
|**Atualizar**|Atualizar as configurações de locatário.|

### <a name="remote-tasks"></a>Tarefas remotas

|||
|-|-|
|**Bypass de Bloqueio de Ativação**|Remover o bloqueio de ativação de um dispositivo iOS sem a ID Apple e a senha do usuário. |
|**Desabilitar Modo de Perda**|Desabilitar o Modo de Perda. O modo de perda permite especificar uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo.|
|**Habilitar Modo de Perda**|Habilitar o Modo de Perda. O modo de perda permite especificar uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo.|
|**Localizar Dispositivo**|-|
|**Reinicializar Agora**|Faz com que o dispositivo seja reiniciado.|
|**Bloqueio Remoto**|Bloqueia um dispositivo. O proprietário do dispositivo deve usar a senha para desbloqueá-lo.|
|**Redefinir Senha**|Gera uma nova senha para o dispositivo que será exibido na folha Visão Geral de <device name>.|
|**Desativar**|Remove somente os dados da empresa gerenciados pelo Intune. Não remove dados pessoais do dispositivo.|
|**Apagamento**|Retorna o dispositivo para suas configurações padrão.|



### <a name="telecom-expenses"></a>Despesas de telecomunicações

|||
|-|-|
|**Ler**|Ler as configurações de TEM (Gerenciamento das Despesas de Telecomunicações).|
|**Atualizar**|Atualizar as configurações de TEM (Gerenciamento das Despesas de Telecomunicações).|

### <a name="terms-and-conditions"></a>Termos e condições

|||
|-|-|
|**Atribuir**|Atribuir os termos e condições aos grupos.|
|**Criar**|Criar as configurações de termos e condições.|
|**Excluir**|Excluir as configurações de termos e condições.|
|**Ler**|Ler as configurações de termos e condições no Portal do Intune.|
|**Atualizar**|Atualizar configurações de termos e condições existentes.|
