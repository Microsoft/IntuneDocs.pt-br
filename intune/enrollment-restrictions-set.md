---
title: "Definir restrições de registro no Microsoft Intune"
titlesuffix: 
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6466d62cf8af4e6b8a14980db5e9a244deb45c4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="set-enrollment-restrictions"></a>Definir restrições de registro

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, você pode criar e gerenciar restrições de registro. Essas restrições definem o número e os tipos de dispositivos que podem registrar-se no gerenciamento com o Intune. É possível criar várias restrições e aplicá-las aos diferentes grupos de usuários. É possível definir a [ordem de prioridade](#change-enrollment-restriction-priority) para as diferentes restrições.

>[!NOTE]
>Restrições de registro não são um recurso de segurança. Dispositivos comprometidos podem falsificar a identidade. Tais restrições são uma barreira de melhor esforço para usuários que não são mal-intencionados.

>[!NOTE]
>A funcionalidade de restrição e a prioridade do registro de grupo atribuído mencionada a seguir está no processo de ser distribuída em toda a base de clientes do Intune. Até essa implantação estar concluída, talvez você não tenha acesso aos recursos do grupo e prioridade.

As restrições de registro específicas que você pode criar incluem:

- Número máximo de dispositivos registrados
- Plataformas de dispositivo que podem ser registradas:
  - Android
  - Android for Work
  - iOS
  - macOS
  - Windows
- Versão do sistema operacional da plataforma para iOS, Android for Work e Windows (somente as versões do Windows 10 poderão ser usadas, deixe isso em branco se Windows 8.1 for permitido)
  - Versão mínima
  - Versão máxima
- Restringir dispositivos pessoais (apenas iOS, Android, Android for Work e macOS)

## <a name="default-restrictions"></a>Restrições padrão

As restrições padrão são fornecidas automaticamente para as restrições de registro de tipo de dispositivo e de limite de dispositivos. É possível voltar as opções para os padrões. As restrições padrão aplicam-se a todos os registros com usuário e sem usuário. É possível substituir esses padrões criando novas restrições com prioridades mais altas.

## <a name="create-a-restriction"></a>Criar uma restrição

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Escolha **Registro de dispositivos** > **Restrições de registro**.
4. Escolha **Criar restrição**.
5. Dê à restrição um nome e uma descrição.
6. Escolha um **Tipo de restrição** e, em seguida, clique em **Criar**.
7. Para restrições de limite de dispositivos, clique em **Limite de dispositivos** para definir o número máximo de dispositivos que um usuário pode registrar.
8. Para restrições de tipo de dispositivo, clique em **Plataformas** e **Configurações de plataforma** para permitir ou bloquear várias plataformas e versões.
9. Clique em **Atribuições** > **+ Selecionar grupos**.
10. Em **Selecionar grupos**, selecione um ou mais grupos e clique em **Selecionar**. A restrição aplica-se apenas a grupos aos quais ela foi atribuída. Se você não atribuir uma restrição a pelo menos um grupo, ela não terá nenhum efeito.
11. Clique em **Salvar**.
12. A nova restrição é criada com uma prioridade acima do padrão. É possível [alterar a prioridade](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Definir restrições de tipo de dispositivo

É possível alterar as configurações para uma restrição de tipo de dispositivo seguindo estas etapas:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Escolha **Registro de dispositivos** > **Restrições de registro**.
4. Em **Restrições de tipo de dispositivo**, escolha a restrição que você deseja definir.
5. No nome da restrição (**Todos os usuários** para a restrição padrão), selecione **Plataformas**. Escolha **Permitir** ou **Bloquear** para cada plataforma listada.
6. Clique em **Salvar**.
7. No nome da restrição (**Todos os usuários** para a restrição padrão), selecione **Configurações de plataforma** e selecione as **Versões** mínimas e máximas para as plataformas listadas. As versões compatíveis incluem:
  - O Android e o Android for Work são compatíveis com major.minor.rev.build.
  - O iOS é compatível com o major.minor.rev.
  - O Windows é compatível com minor.rev.build somente para Windows 10.
  As versões do sistema operacional não se aplicam a dispositivos Apple registrados por meio do Programa de Registro de Dispositivos, do Apple School Manager ou do aplicativo do Apple Configurator.
6. Especifique se deseja **Permitir** ou **Bloquear** dispositivos **de propriedade pessoal** para cada plataforma listada.

    ![Captura de tela do espaço de trabalho de restrições de dispositivo com a plataforma de dispositivo padrão configurada para dispositivos de propriedade pessoal](media/device-restrictions-platform-configurations.png)
7. Clique em **Salvar**.

>[!NOTE]
>- Se você impedir o registro de dispositivos pessoais Android, os dispositivos pessoais Android for Work ainda poderão ser registrados.
>- Por padrão, as configurações de dispositivos Android for Work serão as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.
>- Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

## <a name="set-device-limit-restrictions"></a>Definir restrições de limite de dispositivos

É possível alterar as configurações para uma restrição de limite de dispositivos seguindo estas etapas:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Escolha **Registro de dispositivos** > **Restrições de registro**.
4. Em **Restrições de limite de dispositivos**, escolha a restrição que você deseja definir.
5. Escolha **Limite de dispositivos** e, em seguida, na lista suspensa, selecione o número máximo de dispositivos que um usuário pode registrar.
    ![Captura de tela da folha de restrições de limite do dispositivo](./media/device-restrictions-limit.png)
4. Clique em **Salvar**.

O usuário final verá uma notificação informando quando ele atingiu o limite de dispositivos registrados. Por exemplo, no iOS, ela teria esta aparência:

![Captura de tela da notificação do limite de dispositivos do iOS](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>Alterar a prioridade de restrição de registro

A prioridade será usada quando um usuário existir em vários grupos que recebem restrições. Os usuários estão sujeitos apenas à restrição de prioridade mais alta atribuída a um grupo em que eles estão. Por exemplo, Joe está em um grupo A atribuído a restrições de prioridade 5 e um grupo B atribuído a restrições de prioridade 2. Joe está sujeito apenas às restrições de prioridade 2.

Quando você cria uma restrição, ela é adicionada à lista acima da padrão.

O registro de dispositivo inclui restrições padrão para restrições de limite de dispositivos e de tipo de dispositivo. Essas duas restrições aplicam-se a todos os usuários, a menos que sejam substituídas por restrições de prioridade mais alta.

É possível alterar a prioridade de qualquer restrição não padrão.

**Para alterar a prioridade de restrição**

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Escolha **Registro de dispositivos** > **Restrições de registro**.
4. Passe o mouse sobre a restrição na lista de prioridades.
5. Usando os três pontos verticais à esquerda, arraste a prioridade para a posição desejada na lista.
