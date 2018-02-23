---
title: "Como criar uma política de conformidade para o macOS"
titleSuffix: Azure portal
description: "Saiba como criar uma política de conformidade para dispositivos macOS."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 2/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a5f1caeddbd3d171092ef59cfb092404b31154f2
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2018
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>Criar uma política de conformidade do dispositivo para dispositivos macOS com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Antes de começar

Antes de criar e atribuir uma política de conformidade do dispositivo, examine os conceitos da política de conformidade do dispositivo do Intune.

- Para saber mais sobre as políticas de conformidade do dispositivo, consulte a [introdução às políticas de conformidade do dispositivo](device-compliance.md).

> [!IMPORTANT]
> Você precisa criar políticas de conformidade do dispositivo para cada plataforma. As configurações da política de conformidade do dispositivo do Intune dependem das funcionalidades de plataforma, que são configurações expostas por meio do protocolo MDM.

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional:


| Configuração de política | macOS 10.11 e posterior |
| --- | --- |
| **Configuração de senha ou PIN** | Corrigida |   
| **Criptografia de dispositivo** | Corrigida (pela definição do PIN) |
| **Perfil de email** | Em Quarentena |
|**Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |  


**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando o dispositivo não é compatível, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="macos-compliance-policy-settings"></a>Configurações das políticas de conformidade do macOS

Você tem categorias diferentes com configurações diferentes para escolher ao criar uma nova conformidade do dispositivo com o Intune:

- Integridade do Dispositivo

- Propriedades do Dispositivo

- Segurança do Sistema

### <a name="device-health"></a>Integridade do Dispositivo

- **Exigir uma proteção de integridade do sistema** – defina como **Exigir** para verificar se os dispositivos macOS têm a proteção de integridade do sistema habilitada.

### <a name="device-properties"></a>Propriedades do dispositivo

- **Versão do sistema operacional mínima** – quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar o dispositivo. Depois disso, ele pode acessar recursos da empresa.

- **Versão do sistema operacional máxima** – quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e será solicitado que o usuário contate o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

### <a name="system-security-settings"></a>Configurações de segurança do sistema

#### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis** – defina como **Exigir** para que os usuários insiram uma senha antes de poder acessar o dispositivo.

- **Senhas simples** – defina como **Bloquear** para que o usuário não possa criar uma senha simples como **1234** ou **1111**.

- **Tamanho mínimo da senha** – especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.

- **Tipo de senha** – especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.

- **Número de caracteres não alfanuméricos na senha** – se você definir **Tipo de senha necessária** como **Alfanumérica**, use essa configuração para especificar o número mínimo de conjuntos de caracteres que a senha deve conter. 

    > [!NOTE]
    > Definir um número mais alto exige que o usuário crie uma senha mais complexa.

    > [!IMPORTANT]
    > Para dispositivos macOS, essa configuração refere-se ao número de caracteres especiais (por exemplo, **!** , **#**, **&amp;**) que devem ser incluídos na senha.

- **Máximo de minutos de inatividade antes que a senha seja exigida** – especifique o tempo ocioso antes que o usuário precise digitar novamente a senha.

- **Expiração da senha (dias)** – selecione o número de dias (entre 1 e 250) antes que a senha expire e seja preciso criar uma nova.

- **Número de senhas anteriores para evitar a reutilização** – especifique o número de senhas usadas anteriormente que não podem ser reutilizadas.

    > [!IMPORTANT]
    > Quando o requisito de senha é alterado em um dispositivo macOS, ele não tem efeito até a próxima vez que o usuário alterar sua senha. Por exemplo, se você definir a restrição de comprimento de senha para oito dígitos e o dispositivo macOS atualmente tiver uma senha de seis dígitos, o dispositivo permanecerá em conformidade até a próxima vez que o usuário atualizar a senha no dispositivo.

## <a name="to-create-a-device-compliance-policy"></a>Para criar uma política de conformidade do dispositivo

1. Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.

2. Quando entrar com êxito, você poderá ver o **Painel do Azure**.

3. Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

4. Escolha **Intune** e você poderá ver o **Painel do Intune**.

5. Escolha **Conformidade do dispositivo** e, em seguida, escolha **Políticas** em **Gerenciar**.

6. Escolha **Criar Política**.

7. Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.

8. A folha **política de conformidade do macOS** é aberta, escolha as categorias de configuração de conformidade do dispositivo **Segurança**, **Integridade do dispositivo** e **Propriedade do dispositivo** para especificar as configurações.

10. Ao acabar de escolher as configurações, escolha **OK** em cada categoria de configuração de conformidade do dispositivo.

11. Escolha **OK** e, em seguida, escolha **Criar**.

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

Para atribuir uma política de conformidade aos usuários, escolha uma política que você configurou. As políticas existentes podem ser encontradas na folha **Conformidade – Políticas**.

1. Escolha a política de conformidade do dispositivo que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.

2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.

3. Escolha **Selecionar** e, em seguida, **Salvar** para atribuir a política de conformidade do dispositivo aos grupos de segurança do Azure AD.

4. Ao terminar de atribuir a política de conformidade do dispositivo aos grupos, você poderá fechar a folha **Atribuições**.

    > [!TIP]
    > Por padrão, os dispositivos verificam a conformidade a cada oito horas, mas os usuários podem forçar esse processo por meio do aplicativo Portal da Empresa do Intune.

## <a name="next-steps"></a>Próximas etapas

[Saiba como monitorar políticas de conformidade do dispositivo](compliance-policy-monitor.md)
