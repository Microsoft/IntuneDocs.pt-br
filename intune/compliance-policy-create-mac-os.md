---
title: Configurações de conformidade para dispositivo macOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos macOS no Microsoft Intune. Exija proteção de integridade do sistema da Apple, defina restrições de senha, exija um firewall, permita o gatekeeper e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3224e7400ad56f971488aba53bb073a0d33bb9d
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423638"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do macOS para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos macOS no Intune. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use estas configurações para definir a versão mínima ou a máxima do SO, definir senhas para expirar e muito mais.

Esse recurso aplica-se a:

- macOS

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **Plataforma**, selecione **macOS**.

## <a name="device-health"></a>Integridade do Dispositivo

- **Exigir uma proteção de integridade do sistema**: **Exigir** que os dispositivos macOS tenham a [Proteção de Integridade do Sistema](https://support.apple.com/HT204899) (abre o site da Apple) habilitada. Quando definido como **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

## <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até que haja uma alteração de regra para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.
- **Versão de build mínima do SO**: quando a Apple publica atualizações de segurança, geralmente é atualizado o número de compilação, não a versão do sistema operacional. Use esse recurso para inserir um número de compilação mínima permitido no dispositivo.
- **Versão de build máxima do SO**: quando a Apple publica atualizações de segurança, geralmente é atualizado o número de compilação, não a versão do sistema operacional. Use esse recurso para inserir um número de compilação máxima permitido no dispositivo.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.
- **Tipo de senha**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).
- **Número de caracteres não alfanuméricos na senha**: insira o número mínimo de caracteres especiais, como `&`, `#`, `%`, `!` e assim por diante, que devem ser incluídos na senha.

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

- **Firewall**: selecione **Habilitar** para ajudar a proteger os dispositivos contra o acesso não autorizado. A habilitação desse recurso permite que você manipule as conexões de entrada com a Internet e use o modo furtivo. A opção **Não configurado** (padrão) deixa o firewall desativado e o tráfego de rede é permitido (não bloqueado).
- **Conexões de entrada**: **bloqueie** todas as conexões de rede de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Essa configuração também bloqueia todos os serviços de compartilhamento, incluindo compartilhamento de tela, acesso remoto, compartilhamento de música do iTunes e muito mais. A opção **Não configurado** (padrão) permite conexões de entrada e serviços de compartilhamento.
- **Modo Furtivo**: **habilite** o modo furtivo para impedir que dispositivos respondam a solicitações de investigação, que podem ser feitas por usuários mal-intencionados. Quando essa opção está habilitada, o dispositivo continua respondendo a solicitações de entrada de aplicativos autorizados. A opção **Não configurado** (padrão) deixa o modo furtivo desativado.

### <a name="gatekeeper"></a>Gatekeeper

Para obter mais informações, veja [Gatekeeper no macOS](https://support.apple.com/HT202491) (abre o site da Apple).

**Permitir aplicativos baixados destes locais**: permite que aplicativos com suporte sejam instalados em seus dispositivos de diferentes locais. Suas opções de localização:

- **Não configurado**: padrão. A opção gatekeeper não tem impacto sobre conformidade ou não conformidade. 
- **Mac App Store**: instale somente os aplicativos para a Mac App Store. Não é possível instalar aplicativos de terceiros nem de desenvolvedores identificados. Se um usuário selecionar o Gatekeeper para instalar aplicativos fora da Mac App Store, será considerado que o dispositivo não está em conformidade.
- **Mac App Store e desenvolvedores identificados**: instale aplicativos para a Mac App Store e desenvolvedores identificados. O macOS verifica a identidade dos desenvolvedores e faz algumas outras verificações para determinar a integridade do aplicativo. Se um usuário selecionar o Gatekeeper para instalar aplicativos fora dessas opções, será considerado que o dispositivo não está em conformidade.
- **Em qualquer lugar**: os aplicativos podem ser instalados em qualquer lugar e por qualquer desenvolvedor. Essa opção é a menos segura.

Selecione **OK** > **Criar** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja as [configurações da política de conformidade para dispositivos iOS](compliance-policy-create-ios.md).