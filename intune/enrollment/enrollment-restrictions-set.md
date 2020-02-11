---
title: Definir restrições de registro no Microsoft Intune
titleSuffix: ''
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0dac0607fcaa92ebe65a7ddacc3cd91c63bf246e
ms.sourcegitcommit: 5178aec0244e023e73546f3d10f1a76eaf1f4a3e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76971867"
---
# <a name="set-enrollment-restrictions"></a>Definir restrições de registro

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como Administrador do Intune, é possível criar e gerenciar as restrições de registro que definem quais dispositivos podem ser registrados no gerenciamento com o Intune, incluindo:
- Quantidade de dispositivos.
- Versões e sistemas operacionais.

É possível criar várias restrições e aplicá-las aos diferentes grupos de usuários. É possível definir a [ordem de prioridade](#change-enrollment-restriction-priority) para as diferentes restrições.

>[!NOTE]
>Restrições de registro não são um recurso de segurança. Dispositivos comprometidos podem falsificar a identidade. Tais restrições são uma barreira de melhor esforço para usuários que não são mal-intencionados.

As restrições de registro específicas que você pode criar incluem:

- Número máximo de dispositivos registrados.
- Plataformas de dispositivo que podem ser registradas:
  - Administrador do dispositivo Android
  - Perfil de trabalho do Android Enterprise
  - iOS
  - macOS
  - Windows
  - Windows Mobile
- Versão do sistema operacional da plataforma para iOS, administrador do dispositivo Android, perfil corporativo do Android Enterprise, Windows e Windows Mobile. (Somente versões do Windows 10 podem ser usadas. Deixe em branco se Windows 8.1 for permitido.)
  - Versão mínima.
  - Versão máxima.
- Restringir [dispositivos de propriedade pessoal](device-enrollment.md#bring-your-own-device) (somente iOS, administrador do dispositivo Android, perfil corporativo do Android Enterprise, macOS, Windows e Windows Mobile).

## <a name="default-restrictions"></a>Restrições padrão

As restrições padrão são fornecidas automaticamente para as restrições de registro de tipo de dispositivo e de limite de dispositivos. É possível voltar as opções para os padrões. As restrições padrão aplicam-se a todos os registros com usuário e sem usuário. É possível substituir esses padrões criando novas restrições com prioridades mais altas.

## <a name="create-a-device-type-restriction"></a>Criar uma restrição de tipo de dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **Restrições de Registro** > **Criar restrição** > **Restrição de tipo de dispositivo**.
2. Na página **Básico**, forneça à restrição um **Nome** e uma **Descrição** opcional.
3. Escolha **Avançar** para ir até a página **Configurações da plataforma**.
4. Em **Plataforma**, escolha **Permitir** para as plataformas que você deseja que essa restrição permita.
    ![Captura de tela da escolha das configurações de plataforma](./media/enrollment-restrictions-set/choose-platform-settings.png)
5. Em **Versões**, escolha as versões mínimas e máximas para as quais você deseja que as plataformas permitidas ofereçam suporte. As restrições de versão aplicam-se somente a dispositivos registrados no Portal da Empresa.
     Os formatos de versão com suporte incluem:
    - O administrador do dispositivo Android e o perfil de trabalho do Android Enterprise dão suporte a major.minor.rev.build.
    - O iOS é compatível com o major.minor.rev. As versões do sistema operacional não se aplicam a dispositivos Apple registrados por meio do Programa de Registro de Dispositivos, do Apple School Manager ou do aplicativo do Apple Configurator.
    - O Windows é compatível com major.minor.build.rev somente para Windows 10.
    
    > [!IMPORTANT]
    > As plataformas de administrador de dispositivo Android Enterprise (perfil de trabalho) e Android têm o seguinte comportamento:
    > - Se as duas plataformas tiverem permissão para o mesmo grupo, os usuários serão registrados em um perfil de trabalho se o dispositivo der suporte a isso; caso contrário, eles serão registrados como DA. 
    > - Se as duas plataformas tiverem permissão para o grupo e forem refinadas para versões específicas e sem sobreposição, os usuários receberão o fluxo de registro definido para sua versão do sistema operacional. 
    > - Se as duas plataformas tiverem permissão, mas forem bloqueadas para as mesmas versões, os usuários nos dispositivos com as versões bloqueadas serão retirados do fluxo de registro do administrador do dispositivo Android, serão bloqueados do registro e deverão sair. 
    >
    > Vale a pena observar que nem o perfil de trabalho nem o registro do administrador do dispositivo funcionarão, a menos que os pré-requisitos apropriados tenham sido concluídos no Registro do Android. 
    
   > [!Note]
   > O Windows 10 não fornece o número de rev durante o registro. Portanto, para a instância, se você inserir 10.0.17134.100 e o dispositivo for 10.0.17134.174, ele será bloqueado durante o registro.

6. Em **Propriedade pessoal**, escolha **Permitir** para as plataformas que você deseja permitir como dispositivos de propriedade pessoal.
7. Em **Fabricante do dispositivo**, insira uma lista separada por vírgulas dos fabricantes que você deseja bloquear.
8. Escolha **Avançar** para ir até a página **Atribuições**.
9. Escolha **Selecionar grupos para incluir** e, em seguida, use a caixa de pesquisa para localizar os grupos que você deseja incluir nessa restrição. A restrição aplica-se apenas a grupos aos quais ela foi atribuída. Se você não atribuir uma restrição a pelo menos um grupo, ela não terá nenhum efeito. Em seguida, escolha **Selecionar**. 
    ![Captura de tela da escolha das configurações de plataforma](./media/enrollment-restrictions-set/select-groups.png)
10. Selecione **Avançar** para acessar a página **Revisar + criar**.
11. Selecione **Criar** para criar a restrição.
12. A nova restrição é criada com uma prioridade acima do padrão. É possível [alterar a prioridade](#change-enrollment-restriction-priority).


## <a name="create-a-device-limit-restriction"></a>Criar uma restrição de limite de dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **Restrições de Registro** > **Criar restrição** > **Restrição de limite de dispositivo**.
2. Na página **Básico**, forneça à restrição um **Nome** e uma **Descrição** opcional.
3. Escolha **Avançar** para ir até a página **Limite do dispositivo**.
4. Em **Limite do dispositivo**, selecione o número máximo de dispositivos que um usuário pode registrar.
    ![Captura de tela da escolha do limite do dispositivo](./media/enrollment-restrictions-set/choose-device-limit.png)
5. Escolha **Avançar** para ir até a página **Atribuições**.
6. Escolha **Selecionar grupos para incluir** e, em seguida, use a caixa de pesquisa para localizar os grupos que você deseja incluir nessa restrição. A restrição aplica-se apenas a grupos aos quais ela foi atribuída. Se você não atribuir uma restrição a pelo menos um grupo, ela não terá nenhum efeito. Em seguida, escolha **Selecionar**. 
    ![Captura de tela da seleção de grupos](./media/enrollment-restrictions-set/select-groups-device-limit.png)
7. Selecione **Avançar** para acessar a página **Revisar + criar**.
8. Selecione **Criar** para criar a restrição.
9. A nova restrição é criada com uma prioridade acima do padrão. É possível [alterar a prioridade](#change-enrollment-restriction-priority).

Durante as inscrições de BYOD, os usuários veem uma notificação informando que eles atingiram o limite de dispositivos registrados. Por exemplo, no iOS:

![Notificação do limite de dispositivos iOS](./media/enrollment-restrictions-set/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> As restrições de limite de dispositivo não se aplicam aos seguintes tipos de registro do Windows:
> - Registros cogerenciados
> - Registros de GPO
> - Registros de ingresso no Azure Active Directory
> - Registros de ingresso em massa no Azure Active Directory
> - Registros do Autopilot
> - Registros do Gerenciador de Registro do Dispositivo
>
> As restrições de limite de dispositivo não são aplicadas a esses tipos de registro porque eles são considerados cenários de dispositivos compartilhados.
> Você pode definir limites rígidos para esses tipos de registro [no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/device-management-azure-portal#configure-device-settings).


## <a name="change-enrollment-restrictions"></a>Alterar restrições de registro

É possível alterar as configurações de uma restrição de registro seguindo as etapas abaixo. Essas restrições não afetam dispositivos já registrados. Os dispositivos registrados com o [agente Intune PC](../fundamentals/manage-windows-pcs-with-microsoft-intune.md) não podem ser bloqueados com esse recurso.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **Restrições de registro** > escolha a restrição que deseja alterar > **Propriedades**.
2. Escolha **Editar** ao lado das configurações que você deseja alterar.
3. Na página **Editar**, faça as alterações desejadas e prossiga para a página **Revisar + salvar** e escolha **Salvar**.


## <a name="blocking-personal-android-devices"></a>Bloqueio de dispositivos Android pessoais
- Se você impedir o registro de dispositivos de administrador Android de propriedade pessoal, os dispositivos de perfil corporativo do Android Enterprise de propriedade pessoal ainda poderão ser registrados.
- Por padrão, as configurações de dispositivos do perfil corporativo do Android Enterprise são as mesmas que as configurações de dispositivos de administrador Android. Após alterar o perfil corporativo do Android Enterprise ou as configurações de administrador do dispositivo Android, elas não serão mais as mesmas.
- Se você bloquear o registro de perfil corporativo do Android Enterprise pessoal, somente dispositivos Android corporativos poderão ser registrados com perfis corporativos do Android Enterprise.

## <a name="blocking-personal-windows-devices"></a>Bloqueio de dispositivos Windows pessoais
Se você bloquear o registro de dispositivos Windows de propriedade pessoal, o Intune verificará para ter certeza de que cada nova solicitação de registro do Windows foi autorizada como um registro corporativo. Os registros não autorizados serão bloqueados.

Os métodos a seguir se qualificam como autorizados como um registro corporativo do Windows:
- O usuário do registro está usando uma [conta de gerenciador de registros de dispositivos]( device-enrollment-manager-enroll.md).
- O dispositivo deve ser registrado por meio do [Windows Autopilot](enrollment-autopilot.md).
- O dispositivo está registrado com o Windows Autopilot, mas essa não é a única opção de registro do MDM nas configurações do Windows.
- O número IMEI do dispositivo está listado em **Registro de dispositivos** >  **[Identificadores de dispositivo corporativo](corporate-identifiers-add.md)** . (Não há suporte no Windows Phone 8.1.)
- O dispositivo está sendo registrado por meio de um [pacote de provisionamento em massa](windows-bulk-enroll.md).
- O dispositivo está sendo registrado pelo GPO ou por meio do [registro automático do Configuration Manager para cogerenciamento](https://docs.microsoft.com/configmgr/comanage/quickstart-paths#bkmk_path1).
 
Os seguintes registros são marcados como corporativos pelo Intune. No entanto, como eles não oferecem o controle por dispositivo ao administrador do Intune, eles são bloqueados:
- [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [ingresso no Azure Active Directory durante a instalação do Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Registro automático no MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [ingresso no Azure Active Directory na instalação do Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Os seguintes métodos de registro pessoais também serão bloqueados:
- [Registro automático do MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) com [Adicionar Conta Corporativa nas Configurações do Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- A opção [Somente registro do MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) nas Configurações do Windows.

\* Eles não serão bloqueados se registrados com o Autopilot.


## <a name="blocking-personal-ios-devices"></a>Bloqueio de dispositivos iOS pessoais
Por padrão, o Intune classifica os dispositivos iOS como de propriedade pessoal. Para ser classificado como de propriedade corporativa, um dispositivo iOS deve atender a uma das seguintes condições:
- Registrado com um número de série ou IMEI.
- Registrado usando o Registro de Dispositivo Automatizado (anteriormente conhecido como Programa de registro de dispositivos)


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
