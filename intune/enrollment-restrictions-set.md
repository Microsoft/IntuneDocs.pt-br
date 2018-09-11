---
title: Definir restrições de registro no Microsoft Intune
titlesuffix: ''
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 76c0b96a1759caad4a1052a7233c7dcc8cecfa3b
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313710"
---
# <a name="set-enrollment-restrictions"></a>Definir restrições de registro

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, é possível criar e gerenciar as restrições de registro que definem o número e os tipos de dispositivos que podem se registrar no gerenciamento com o Intune. É possível criar várias restrições e aplicá-las aos diferentes grupos de usuários. É possível definir a [ordem de prioridade](#change-enrollment-restriction-priority) para as diferentes restrições.

>[!NOTE]
>Restrições de registro não são um recurso de segurança. Dispositivos comprometidos podem falsificar a identidade. Tais restrições são uma barreira de melhor esforço para usuários que não são mal-intencionados.

As restrições de registro específicas que você pode criar incluem:

- Número máximo de dispositivos registrados.
- Plataformas de dispositivo que podem ser registradas:
  - Android
  - Perfil de trabalho Android
  - iOS
  - macOS
  - Windows
- Versão do sistema operacional da plataforma para iOS, Android, perfil de trabalho Android e Windows. (Somente versões do Windows 10 podem ser usadas. Deixe em branco se Windows 8.1 for permitido.)
  - Versão mínima.
  - Versão máxima.
- Restringir dispositivos de propriedade pessoal (somente iOS, Android, perfil de trabalho do Android, macOS e Windows).

## <a name="default-restrictions"></a>Restrições padrão

As restrições padrão são fornecidas automaticamente para as restrições de registro de tipo de dispositivo e de limite de dispositivos. É possível voltar as opções para os padrões. As restrições padrão aplicam-se a todos os registros com usuário e sem usuário. É possível substituir esses padrões criando novas restrições com prioridades mais altas.

## <a name="create-a-restriction"></a>Criar uma restrição

1. Entre no Portal do Azure.
2. Selecione **Mais serviços**, pesquise **Intune** e, em seguida, escolha **Intune**.
3. Selecione **Registro de dispositivos** > **Restrições de registro**.
4. Selecione **Criar restrição**.
5. Dê à restrição um nome e uma descrição.
6. Escolha um **Tipo de restrição** e, em seguida, selecione **Criar**.
7. Para restrições de limite de dispositivos, selecione **Limite de dispositivos** para definir o número máximo de dispositivos que um usuário pode registrar.
8. Para restrições de tipo de dispositivo, selecione **Plataformas** e **Configurações de plataforma** para permitir ou bloquear várias plataformas e versões.
9. Selecione **Atribuições** > **+ Selecionar grupos**.
10. Em **Selecionar grupos**, selecione um ou mais grupos e escolha **Selecionar**. A restrição aplica-se apenas a grupos aos quais ela foi atribuída. Se você não atribuir uma restrição a pelo menos um grupo, ela não terá nenhum efeito.
11. Selecione **Salvar**.
12. A nova restrição é criada com uma prioridade acima do padrão. É possível [alterar a prioridade](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Definir restrições de tipo de dispositivo

É possível alterar as configurações de uma restrição de tipo de dispositivo seguindo estas etapas. Essas restrições não afetam dispositivos que já foram registrados. Os dispositivos registrados com o [agente Intune PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune.md) não podem ser bloqueados com esse recurso.

1. Entre no Portal do Azure.
2. Selecione **Mais serviços**, pesquise **Intune** e, em seguida, escolha **Intune**.
3. Selecione **Registro de dispositivos** > **Restrições de registro**.
4. Em **Restrições de Tipo de Dispositivo** > escolha a restrição que você deseja definir > **Propriedades** > **Selecionar plataformas**. Escolha **Permitir** ou **Bloquear** para cada plataforma listada.
    ![Captura de tela para permitir ou bloquear uma plataforma](media/enrollment-restrictions-set/platform-allow-block.png)
5. Selecione **OK**.
6. Escolha **Configurar plataformas**.
    ![Captura de tela para configurar plataformas](media/enrollment-restrictions-set/configure-platforms.png)
7. Selecione as **Versões** mínimas e máximas para as plataformas listadas. Os formatos de versão com suporte incluem:
    - O perfil de trabalho Android dá suporte para major.minor.rev.build.
    - O iOS é compatível com o major.minor.rev. As versões do sistema operacional não se aplicam a dispositivos Apple registrados por meio do Programa de Registro de Dispositivos, do Apple School Manager ou do aplicativo do Apple Configurator.
    - O Windows é compatível com minor.rev.build somente para Windows 10.
8. Escolha se deseja **Permitir** ou **Bloquear** dispositivos de **Propriedade pessoal** para cada plataforma listada.
9. Selecione **OK**.

### <a name="android-device-type-restrictions"></a>Restrições de tipo de dispositivo Android
- Se você impedir o registro de dispositivos Android de propriedade pessoal, os dispositivos de perfil de trabalho Android de propriedade pessoal ainda poderão ser registrados.
- Por padrão, as configurações de dispositivos do perfil de trabalho Android são as mesmas que as configurações de dispositivos Android. Depois que você alterar as configurações do perfil de trabalho Android, elas não serão mais as mesmas.
- Se você bloquear o registro do perfil de trabalho Android pessoal, somente os dispositivos Android corporativos poderão ser registrados como um perfil de trabalho Android.

### <a name="windows-device-type-restrictions"></a>Restrições de tipo de dispositivo Windows
Depois que a restrição de tipo de dispositivo da plataforma Windows for definida como **Bloquear**, o Intune verificará se cada nova solicitação de registro do Windows foi autorizada como um registro corporativo. Os registros não autorizados serão bloqueados.

Os métodos a seguir se qualificam como autorizados como um registro corporativo do Windows:
 - O usuário do registro está usando uma [conta de gerenciador de registros de dispositivos]( device-enrollment-manager-enroll.md).
- O dispositivo está sendo registrado por meio do [Windows Autopilot](enrollment-autopilot.md).
- O número IMEI do dispositivo está listado em **Registro de dispositivos** > **[Identificadores de dispositivo corporativo](corporate-identifiers-add.md)**. (Não há suporte no Windows Phone 8.1.)
- O dispositivo está sendo registrado por meio de um [pacote de provisionamento em massa](windows-bulk-enroll.md).
- O dispositivo está sendo registrado por meio do [registro automático do SCCM para o cogerenciamento](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management.md).
 
Os seguintes registros são marcados como corporativos pelo Intune, mas como eles não oferecem o controle por dispositivo do administrador do Intune, eles serão bloqueados:
 - [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [ingresso no Azure Active Directory durante a instalação do Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Registro automático no MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [ingresso no Azure Active Directory na instalação do Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-setup.md).
 
Os seguintes métodos de registro pessoais também serão bloqueados:
- [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [Adicionar Conta Corporativa nas Configurações do Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-registered-devices-windows10-setup.md).
- A opção [Somente registro do MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) nas Configurações do Windows.


## <a name="set-device-limit-restrictions"></a>Definir restrições de limite de dispositivos

É possível alterar as configurações para uma restrição de limite de dispositivos seguindo estas etapas:

1. Entre no Portal do Azure.
2. Selecione **Mais serviços**, pesquise **Intune** e, em seguida, escolha **Intune**.
3. Selecione **Registro de dispositivos** > **Restrições de registro**.
4. Em **Restrições de limite de dispositivos**, escolha a restrição que você deseja definir.
5. Selecione **Limite de dispositivos** e, em seguida, na lista suspensa, selecione o número máximo de dispositivos que um usuário pode registrar.
    ![Folha de restrições de limite de dispositivo com as restrições de limite de dispositivo](./media/device-restrictions-limit.png)
6. Selecione **Salvar**.


Os usuários veem uma notificação informando que eles atingiram o limite de dispositivos registrados. Por exemplo, no iOS, ela teria esta aparência:

![Notificação do limite de dispositivos iOS](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>Alterar a prioridade de restrição de registro

A prioridade será usada quando um usuário existir em vários grupos que recebem restrições. Os usuários estão sujeitos apenas à restrição de prioridade mais alta atribuída a um grupo em que eles estão. Por exemplo, Joe está no grupo A e recebeu restrições de prioridade 5 e também está no grupo B e recebeu restrições de prioridade 2. Joe está sujeito apenas às restrições de prioridade 2.

Quando você cria uma restrição, ela é adicionada à lista acima da padrão.

O registro de dispositivo inclui restrições padrão para restrições de limite de dispositivos e de tipo de dispositivo. Essas duas restrições aplicam-se a todos os usuários, a menos que sejam substituídas por restrições de prioridade mais alta.

É possível alterar a prioridade de qualquer restrição não padrão.

1. Entre no Portal do Azure.
2. Selecione **Mais serviços**, pesquise **Intune** e, em seguida, escolha **Intune**.
3. Selecione **Registro de dispositivos** > **Restrições de registro**.
4. Passe o mouse sobre a restrição na lista de prioridades.
5. Usando os três pontos verticais, arraste a prioridade para a posição desejada na lista.
