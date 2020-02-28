---
title: Configurações de conformidade para dispositivos iOS/iPadOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos iOS/iPadOS no Microsoft Intune. Exigir um email, verificar dispositivos com jailbreak ou desbloqueados por rooting, definir o sistema de operacional mínimo e máximo permitido, definir quaisquer restrições de senha, incluindo extensão de senha e inatividade de dispositivo, restringir aplicativos e muito mais.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/07/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 437673878335b04b76c53b13f18acac32213720a
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514023"
---
# <a name="iosipados-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do iOS/iPadOS para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos iOS/iPadOS no Intune. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use estas configurações para exigir um email, marcar dispositivos com raiz (desbloqueados) como não estando em conformidade, definir um nível de ameaça permitido, definir a expiração de senhas e muito mais.

Esse recurso aplica-se a:

- iOS
- iPadOS

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Em **Plataforma**, selecione **iOS/iPadOS**.

## <a name="email"></a>Email

- **Exigir que os dispositivos móveis tenham um perfil de email gerenciado**:  
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Os dispositivos que não tenham um email de perfil gerenciado pelo Intune são considerados não compatíveis. Um dispositivo pode não ter um perfil de email gerenciado quando não é direcionado corretamente ou se o usuário tiver configurado manualmente a conta de email no dispositivo.

  O dispositivo é considerado como não estando em conformidade nas seguintes situações:  
  - O perfil de email é atribuído a um grupo de usuários diferente que o grupo de usuários almejado pela política de conformidade.
  - O usuário configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo. O Intune não pode substituir o perfil de usuário configurado e o Intune não pode gerenciá-lo. Para estar em conformidade, o usuário final deve remover as configurações de email existentes. Depois, o Intune pode instalar o perfil de email gerenciado.  

Para obter detalhes sobre perfis de email, veja [configurar o acesso ao email da organização usando perfis de email com o Intune](../configuration/email-settings-configure.md).

## <a name="device-health"></a>Integridade do dispositivo

- **Dispositivos com jailbreak**:  
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Bloquear** – Marque dispositivos desbloqueados por rooting (com jailbreak) como fora de conformidade.  

- **Requer que o dispositivo esteja em nível igual ou inferior ao Nível de Ameaças do Dispositivo** *(iOS 8.0 e mais recente)* :  
  Use essa configuração para fazer a avaliação de risco como uma condição de conformidade. Escolha o nível de ameaça permitido:  
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Protegido** – Esta opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixa** – O dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer ameaça superior coloca o dispositivo em um status de não compatível.
  - **Médio** – O dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alto** – Esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

## <a name="device-properties"></a>Propriedades do Dispositivo

### <a name="operating-system-version"></a>Versão do Sistema Operacional  

- **Versão mínima do SO** *(iOS 8.0 e mais recentes)* :  
  Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não estando em conformidade. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar o dispositivo. Depois disso, eles podem acessar recursos da organização.

- **Versão máxima do SO** *(iOS 8.0 e mais recentes)* :  
  Quando um dispositivo usa uma versão de SO posterior à versão inserida na regra, o acesso aos recursos da organização é bloqueado. O usuário final é solicitado a contatar seu administrador de TI. O dispositivo não pode acessar os recursos da organização até uma regra mudar para permitir a versão do SO.

- **Versão mínima do build do SO** *(iOS 8.0 e mais recentes)* :  
  Quando a Apple publica atualizações de segurança, geralmente é atualizado o número de compilação, não a versão do sistema operacional. Use esse recurso para inserir um número de compilação mínima permitido no dispositivo.

- **Versão máxima do build do SO** *(iOS 8.0 e mais recentes)* :  
  Quando a Apple publica atualizações de segurança, geralmente é atualizado o número de compilação, não a versão do sistema operacional. Use esse recurso para inserir um número de compilação máxima permitido no dispositivo.

## <a name="system-security"></a>Segurança do Sistema

### <a name="password"></a>Senha

> [!NOTE]
> Depois que uma política de conformidade ou de configuração for aplicada a um dispositivo iOS/iPadOS, os usuários deverão definir uma senha a cada 15 minutos. Os usuários serão notificados continuamente até que uma senha seja definida. Quando uma senha é definida para o dispositivo iOS/iPadOS, o processo de criptografia é iniciado automaticamente. O dispositivo permanece criptografado até que a senha seja desabilitada.

- **Exigir uma senha para desbloquear os dispositivos móveis**:  
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.  
  - **Exigir** – Os usuários precisam inserir uma senha para acessar o dispositivo. Dispositivos iOS/iPadOS que usam uma senha são criptografados.

- **Senhas simples**:  
  - **Não configurado** (*padrão*) – os usuários podem criar senhas simples, como **1234** ou **1111**.
  - **Bloquear** — Os usuários não podem criar senhas simples, como **1234** ou **1111**. 

- **Comprimento mínimo da senha**:  
  Insira o número mínimo de dígitos ou caracteres que a senha deve ter.  

- **Tipo de senha necessária**:  
  Escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).

- **Número de caracteres não alfanuméricos na senha**:  
  Insira o número mínimo de caracteres especiais, como `&`, `#`, `%`, `!` e assim por diante, que devem ser incluídos na senha. 

  Definir um número mais alto exige que o usuário crie uma senha mais complexa.

- **Máximo de minutos após o bloqueio de tela antes que a senha seja exigida** *(iOS 8.0 e mais recente)* :  
  Especifique quanto tempo após o bloqueio da tela o usuário precisará digitar uma senha para acessar o dispositivo. As opções incluem o padrão de *Não configurado*, *Imediatamente* e de *1 minuto* a *4 oras*.

- **Máximo de minutos de inatividade até a tela ser bloqueada**:  
  Insira o tempo ocioso antes que o dispositivo bloqueie a tela. As opções incluem o padrão de *Não configurado*, *Imediatamente* e de *1 minuto* a *15 minutos*.

- **Expiração da senha (dias)** :  
  Selecione o número de dias antes que a senha expire e seja preciso criar uma nova. 

- **Número de senhas anteriores para evitar a reutilização** *(iOS 8.0 e mais recente)* :   
  Insira o número de senhas usadas anteriormente e que não podem ser usadas.

### <a name="device-security"></a>Segurança de dispositivo

- **Aplicativos restritos**:  
  Você pode restringir os aplicativos adicionando suas IDs do lote à política. Se um dispositivo tiver o aplicativo instalado, o dispositivo será marcado como não estando em conformidade.

  - **Nome do aplicativo** – Insira um nome amigável para ajudar a identificar a ID do lote.
  - **ID do lote de aplicativo** – Insira o identificador do lote exclusivo atribuído pelo provedor do aplicativo. Para localizar a ID do pacote, confira [Como localizar a ID do pacote para um aplicativo iOS/iPadOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (abre outro site da Microsoft).  

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja [configurações da política de conformidade para dispositivos macOS](compliance-policy-create-mac-os.md).
