---
title: Criar política de conformidade para dispositivo macOS no Microsoft Intune – Azure | Microsoft Docs
description: Criar ou configurar uma política de conformidade de dispositivo do Microsoft Intune para dispositivos macOS para usar a Proteção de Integridade do Sistema, definir a versão mínima e máxima do sistema operacional, escolher seus requisitos de senha e criptografar o armazenamento de dados.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 14588563dd261063071c09c1bbd3b428fb375830
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184175"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Adicionar uma política de conformidade do dispositivo para dispositivos macOS com o Intune

Uma política de conformidade de dispositivos macOS do Intune determina as regras e configurações que os dispositivos macOS precisam cumprir para estarem em conformidade. Quando você usa as políticas de conformidade de dispositivo, é possível permitir ou bloquear o acesso aos recursos da empresa. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade. As políticas de conformidade de dispositivo de cada plataforma podem ser criadas no Portal do Azure no Intune. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional:

---------------------------

| Configuração de política | macOS 10.11 e posterior |
| --- | --- |
| **Configuração de senha ou PIN** | Corrigida |   
| **Criptografia de dispositivo** | Corrigida (pela definição do PIN) |
| **Perfil de email** | Em Quarentena |
|**Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |

---------------------------

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. Por exemplo, o usuário é forçado a definir um PIN.

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando o dispositivo não é compatível, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Para **Plataforma**, selecione **macOS**. Escolha **Definição de Configurações** para inserir as configurações de **Integridade do Dispositivo**, **Propriedades do Dispositivo** e **Segurança do Sistema**. Quando terminar, selecione **OK** e **Criar**.

## <a name="device-health"></a>Integridade do Dispositivo

- **Exigir uma proteção de integridade do sistema**: **Exigir** que os dispositivos macOS tenham a [Proteção de Integridade do Sistema](https://support.apple.com/HT204899) habilitada.

## <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até que haja uma alteração de regra para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.
- **Tipo de senha**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).
- **Número de caracteres não alfanuméricos na senha**: Insira o número mínimo de caracteres especiais (&, #, %, ! e assim por diante) que devem ser incluídos na senha.

    Definir um número mais alto exige que o usuário crie uma senha mais complexa.

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.

    > [!IMPORTANT]
    > Quando o requisito de senha é alterado em um dispositivo macOS, ele não tem efeito até a próxima vez que o usuário alterar sua senha. Por exemplo, se você definir a restrição de comprimento de senha para oito dígitos e o dispositivo macOS atualmente tiver uma senha de seis dígitos, o dispositivo permanecerá em conformidade até a próxima vez que o usuário atualizar a senha no dispositivo.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em um dispositivo**: escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos.

### <a name="device-security"></a>Segurança de dispositivo
O firewall protege os dispositivos contra o acesso não autorizado à rede. Você pode usar o Firewall para controlar as conexões por aplicativo. 

- **Firewall**: **habilite** para ajudar a proteger os dispositivos contra o acesso não autorizado. A habilitação desse recurso permite que você manipule as conexões de entrada com a Internet e use o modo furtivo. A opção **Não configurado** (padrão) deixa o firewall desativado e o tráfego de rede é permitido (não bloqueado).
- **Conexões de entrada**: **bloqueie** todas as conexões de rede de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Essa configuração também bloqueia todos os serviços de compartilhamento, incluindo compartilhamento de tela, acesso remoto, compartilhamento de música do iTunes e muito mais. A opção **Não configurado** (padrão) permite conexões de entrada e serviços de compartilhamento. 
- **Modo Furtivo**: **habilite** o modo furtivo para impedir que o dispositivo responda a solicitações de investigação, que podem ser feitas por usuários mal-intencionados. Quando essa opção está habilitada, o dispositivo continua respondendo a solicitações de entrada de aplicativos autorizados. A opção **Não configurado** (padrão) deixa o modo furtivo desativado.

### <a name="gatekeeper"></a>Gatekeeper

**Permitir aplicativos baixados destes locais**: permite que aplicativos com suporte sejam instalados em seus dispositivos de diferentes locais. Suas opções de localização:

- **Não configurado**: padrão. A opção gatekeepr não tem impacto sobre conformidade ou não conformidade. 
- **Mac App Store**: instale somente os aplicativos para a Mac App Store. Não é possível instalar aplicativos de terceiros nem de desenvolvedores identificados. Se um usuário selecionar o Gatekeeper para instalar aplicativos fora da Mac App Store, será considerado que o dispositivo não está em conformidade.
- **Mac App Store e desenvolvedores identificados**: instale aplicativos para a Mac App Store e desenvolvedores identificados. O macOS verifica a identidade dos desenvolvedores e faz algumas outras verificações para determinar a integridade do aplicativo. Se um usuário selecionar o Gatekeeper para instalar aplicativos fora dessas opções, será considerado que o dispositivo não está em conformidade.
- **Em qualquer lugar**: os aplicativos podem ser instalados em qualquer lugar e por qualquer desenvolvedor. Essa opção é a menos segura.

Para obter mais detalhes na documentação da Apple, confira [Gatekeeper no macOS](https://support.apple.com/HT202491).

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

1. Escolha uma política que você configurou. As políticas existentes estão em **Conformidade do dispositivo** > **Políticas**.
2. Escolha a política e as **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolher **Salvar** para implantar a política para os usuários.

> [!TIP]
> Por padrão, os dispositivos têm a conformidade verificada a cada oito horas. Mas os usuários podem forçar esse processo por meio do aplicativo de Portal da Empresa do Intune.

Você aplicou a política para os usuários. Os dispositivos usados pelos usuários que são direcionados pela política são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas
[Automatizar email e adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md)  
[Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)
