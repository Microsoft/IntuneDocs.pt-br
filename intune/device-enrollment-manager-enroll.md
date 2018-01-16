---
title: "Registrar dispositivos – gerenciador de registro de dispositivos"
titlesuffix: Azure portal
description: Use a conta do gerenciador de registros de dispositivo para registrar dispositivos no Intune. "
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 03facdde2ff5652799cc3d2113a48ea5ae772ea9
ms.sourcegitcommit: 5fd17a57989c6da3d325ed2e0018ce16fe20bb79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2018
---
# <a name="enroll-devices-using-device-enrollment-manager"></a>Registrar dispositivos usando o gerenciador de registro de dispositivo

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A conta do *DEM* (gerenciador de registro de dispositivos) é uma conta especial do usuário que pode registrar até 1.000 dispositivos. Adicionar usuários existentes à conta do DEM para fornecer recursos de DEM especiais. Cada dispositivo registrado usa uma única licença. Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados em vez de dispositivos pessoais ("BYOD").  

Os usuários devem existir no Portal do Azure para serem adicionados como gerenciadores de registro do dispositivo. Para uma melhor segurança, o usuário do DEM não deve ser um administrador do Intune também.

>[!NOTE]
>O método de registro DEM não pode ser usado com estes outros métodos de registro: [Apple Configurator com o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator com registro direto](apple-configurator-direct-enroll-ios.md), [ASM (Apple School Manager)](apple-school-manager-set-up-ios.md) ou [DEP (Programa de registro de dispositivos)](device-enrollment-program-enroll-ios.md). Também não pode ser usado para registrar dispositivos com macOS. 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemplo de um cenário do gerenciador de registro de dispositivos

Um restaurante quer fornecer 50 tablets de ponto de venda para sua equipe e faz o pedido de monitores para sua equipe da cozinha. Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários. O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e adiciona um supervisor do restaurante à conta DEM, na verdade concedendo recursos de DEM a esse supervisor. O supervisor agora pode registrar os 50 dispositivos de tablets usando as credenciais do DEM.

Somente os usuários no Portal do Azure podem gerenciadores de registro de dispositivos. O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.

O usuário do DEM pode:

-   Registrar até 1000 dispositivos no Intune
-   Entre no Portal da Empresa para obter aplicativos da empresa
-   Configurar o acesso aos dados da empresa implantando aplicativos específicos da função nos tablets

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitações de dispositivos registrados com uma conta do DEM

Dispositivos registrados com uma conta de gerenciador de registro de dispositivos têm as seguintes limitações:

  - Sem acesso por usuário. Como os dispositivos não têm um usuário atribuído, o dispositivo não tem nenhum acesso a email ou a dados da empresa. As configurações de VPN, por exemplo, ainda poderão ser usadas para fornecer aos aplicativos de dispositivo o acesso a dados.
  - Sem acesso condicional, pois esses cenários são por usuário.
  - O usuário do DEM não pode cancelar o registro de dispositivos registrados pelo DEM no próprio dispositivo usando o Portal da Empresa. A administração do Intune pode fazer isso, ao contrário do usuário DEM.
  - Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.
  - Os usuários não podem usar aplicativos VPP (Apple Volume Purchase Program) devido aos requisitos de ID da Apple por usuário para o gerenciamento de aplicativo.
  - (Somente iOS) Se você usar o DEM para registrar dispositivos iOS, não poderá usar o Apple Configurator, o Apple DEP (Programa de registro de dispositivos) nem o ASM (Apple School Manager) para registrar dispositivos.
  - (Somente Android) Há um limite para a quantidade de dispositivos Android for Work que podem ser registrados com uma conta DEM única. Podem ser registrados, no máximo, dez dispositivos de perfil de trabalho do Android por conta do DEM. Essa limitação não se aplica ao registro do Android herdado.
  - Cada dispositivo exige uma licença de dispositivo. Saiba mais sobre [licenças de usuário e dispositivo](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Para implantar aplicativos da empresa em dispositivos gerenciados pelo gerenciador de registro do dispositivo, implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** para a conta de usuário do gerenciador de registro do dispositivo.
> Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais. Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do administrador do Intune.


## <a name="add-a-device-enrollment-manager"></a>Adicionar um gerenciador de registro de dispositivo

1.  No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2.  Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.

3.  Selecione **Adicionar**.

4.  Na folha **Adicionar Usuário**, insira um nome UPN para o usuário DEM e selecione **Adicionar**. O usuário DEM é adicionado à lista de usuários DEM.

## <a name="permissions-for-dem"></a>Permissões para o DEM

As funções do Azure AD Administrador Global ou de Serviços do Intune são necessárias para realizar tarefas de registro do DEM. Essas funções também são necessárias para ver todos os usuários DEM, apesar de as permissões RBAC serem listadas e estarem disponíveis na função de Usuário personalizada. Um usuário sem uma função Administrador global ou Administrador de serviços do Intune atribuída, mas que tem permissões de leitura para a função Gerentes de Registro de Dispositivo, pode ver somente os usuários do DEM criados por ele. O suporte à função RBAC para esses recursos será anunciada no futuro.

Se um usuário não tiver a função Administrador global ou Administrador de serviços do Intune atribuída a ele, mas tiver permissões de leitura habilitadas para a função Gerentes de Registro do Dispositivo atribuída a ele, poderá ver apenas os usuários do DEM criados por ele.

## <a name="remove-a-device-enrollment-manager"></a>Remover um gerenciador de registro de dispositivo

Remover um gerenciador de registro de dispositivos não afeta os dispositivos registrados. Quando um gerenciador de registro de dispositivos é removido:

-   Os dispositivos registrados não são afetados e continuam sendo totalmente gerenciados.
-   As credenciais de conta do gerenciador de registro de dispositivo removido permanecem válidas.
-   O gerenciador de registro de dispositivos removido ainda não poderá apagar nem desativar dispositivos.
-   O gerenciador de registros de dispositivo removido pode registrar somente um número de dispositivos até o limite por usuário configurado pelo administrador do Intune.

**Para remover um gerenciador de registro de dispositivo**

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.
3. Na folha **Gerenciadores de Registro de Dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Remover**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Exibir as propriedades de um gerenciador de registro de dispositivo

1. No Portal do Azure, escolha **Registro de dispositivo** e, depois, **Gerentes de Registro de Dispositivo**.
2. Na folha **Gerenciadores de Registro de Dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Propriedades**.
