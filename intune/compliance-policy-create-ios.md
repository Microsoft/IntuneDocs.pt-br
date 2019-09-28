---
title: Configurações de conformidade para dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos iOS no Microsoft Intune. Exigir um email, verificar dispositivos com jailbreak ou desbloqueados por rooting, definir o sistema de operacional mínimo e máximo permitido, definir quaisquer restrições de senha, incluindo extensão de senha e inatividade de dispositivo, restringir aplicativos e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bde1c296abb99e8c0c81b44908e78b204c62388e
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "71304122"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do iOS para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos iOS no Intune. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use estas configurações para exigir um email, marcar dispositivos com raiz (desbloqueados) como não estando em conformidade, definir um nível de ameaça permitido, definir a expiração de senhas e muito mais.

Esse recurso aplica-se a:

- iOS

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Selecione **Plataforma** para **iOS**.

## <a name="email"></a>Email

- **Exigir que os dispositivos móveis tenham um perfil de email gerenciado**: quando definido como **Obrigatório**, dispositivos que não têm um perfil de email gerenciado pelo Intune são considerados como não estando em conformidade. Um dispositivo pode não ter um perfil de email gerenciado quando não é direcionado corretamente ou se o usuário tiver configurado manualmente a conta de email no dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  O dispositivo é considerado como não estando em conformidade nas seguintes situações:

  - O perfil de email é atribuído a um grupo de usuários diferente que o grupo de usuários almejado pela política de conformidade.
  - O usuário configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo. O Intune não pode substituir o perfil de usuário configurado e o Intune não pode gerenciá-lo. Para estar em conformidade, o usuário final deve remover as configurações de email existentes. Depois, o Intune pode instalar o perfil de email gerenciado.

- **Selecione o perfil de email que deve ser gerenciado pelo Intune**: se a configuração **A conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para inserir o perfil de email do Intune. O perfil de email deve existir no dispositivo.

Para obter detalhes sobre perfis de email, veja [configurar o acesso ao email da organização usando perfis de email com o Intune](email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Dispositivos com jailbreak**: escolha **Bloquear** para marcar dispositivos desbloqueados por rooting (com jailbreak) como não estando em conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Exigir que o dispositivo esteja no ou sob o nível de ameaça de dispositivo** (iOS 8.0 e mais recente): use esta configuração para realizar uma avaliação de risco como condição para a conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Para usar essa configuração, escolha o nível de ameaça permitido:
  - **Protegido**: essa opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

## <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo exigido** (iOS 8.0 e mais recente): quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não estando em conformidade. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar o dispositivo. Depois disso, eles podem acessar recursos da organização.
- **Versão do sistema operacional máxima permitida** (iOS 8.0 e mais recente): quando um dispositivo usa uma versão de SO posterior àquela na regra, o acesso aos recursos da organização é bloqueado. O usuário final é solicitado a contatar seu administrador de TI. O dispositivo não pode acessar os recursos da organização até uma regra mudar para permitir a versão do SO.
- **Versão de build mínima do SO** (iOS 8.0 e mais recente): quando a Apple publica atualizações de segurança, geralmente é atualizado o número de build, não a versão do sistema operacional. Use esse recurso para inserir um número de compilação mínima permitido no dispositivo.
- **Versão de build máxima do SO** (iOS 8.0 e mais recente): quando a Apple publica atualizações de segurança, geralmente é atualizado o número de build, não a versão do sistema operacional. Use esse recurso para inserir um número de compilação máxima permitido no dispositivo.

## <a name="system-security"></a>Segurança do sistema

### <a name="password"></a>Senha

> [!NOTE]
> Depois que uma política de conformidade ou de configuração for aplicada a um dispositivo iOS, os usuários deverão definir uma senha a cada 15 minutos. Os usuários serão notificados continuamente até que uma senha seja definida.

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Dispositivos iOS que usam uma senha são criptografados.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.
- **Tipo de senha necessária**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).
- **Número de caracteres não alfanuméricos na senha**: insira o número mínimo de caracteres especiais, como `&`, `#`, `%`, `!` e assim por diante, que devem ser incluídos na senha.

    Definir um número mais alto exige que o usuário crie uma senha mais complexa.

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)** : selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.

### <a name="device-security"></a>Segurança de dispositivo

- **Aplicativos restritos**: é possível restringir aplicativos adicionando suas IDs de lote à política. Se um dispositivo tiver o aplicativo instalado, o dispositivo será marcado como não estando em conformidade.

  - **Nome do aplicativo**: insira um nome amigável para ajudá-lo a identificar a ID do lote.
  - **ID do lote de aplicativo**: insira o identificador do lote exclusivo atribuído pelo provedor do aplicativo. Para localizar a ID do pacote, veja [Como localizar a ID do pacote para um aplicativo iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (abre outro site da Microsoft).  

Selecione **OK** > **Criar** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja [configurações da política de conformidade para dispositivos macOS](compliance-policy-create-mac-os.md).
