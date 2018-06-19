---
title: Registrar dispositivos usando uma conta do gerenciador de registros de dispositivo
titlesuffix: Microsoft Intune
description: Use a conta do gerenciador de registros de dispositivo para registrar dispositivos no Intune. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a32eb1d65710bf09d61c0846a8d949d5cd99ed2
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2018
ms.locfileid: "34216319"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Registrar dispositivos por meio do uso de uma conta do gerenciador de registros de dispositivo

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A conta do *DEM* (gerenciador de registro de dispositivos) é uma conta especial do usuário que pode registrar até 1.000 dispositivos. Adicionar usuários existentes à conta do DEM para fornecer recursos de DEM especiais. Cada dispositivo registrado usa uma única licença. Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados em vez de dispositivos pessoais ("BYOD").  

Os usuários devem existir no [Portal do Azure](https://portal.azure.com) para serem adicionados como gerenciadores de registro do dispositivo. Para uma melhor segurança, o usuário do DEM não deve ser um administrador do Intune também.

>[!NOTE]
>O método de registro DEM não pode ser usado com estes outros métodos de registro: [Apple Configurator com o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator com registro direto](apple-configurator-direct-enroll-ios.md), [ASM (Apple School Manager)](apple-school-manager-set-up-ios.md) ou [DEP (Programa de registro de dispositivos)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemplo de um cenário do gerenciador de registro de dispositivos

Um restaurante quer fornecer 50 tablets de ponto de venda para sua equipe e faz o pedido de monitores para sua equipe da cozinha. Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários. O administrador do Intune cria uma conta de gerente de registros de dispositivos e adiciona um supervisor do restaurante à conta do DEM. O supervisor agora tem recursos do DEM. O supervisor agora pode registrar os 50 dispositivos de tablets usando as credenciais do DEM.

Somente os usuários do [Portal do Azure](https://portal.azure.com) podem gerenciadores de registro de dispositivos. O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.

O usuário do DEM pode:

-   Registrar até 1000 dispositivos no Intune
-   Entre no Portal da Empresa para obter aplicativos da empresa
-   Configurar o acesso aos dados da empresa implantando aplicativos específicos da função nos tablets

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitações de dispositivos registrados com uma conta do DEM

Dispositivos registrados com uma conta de gerenciador de registro de dispositivos têm as seguintes limitações:

  - Sem acesso por usuário. Como os dispositivos não têm um usuário atribuído, o dispositivo não tem nenhum acesso a email ou a dados da empresa. As configurações de VPN, por exemplo, ainda poderão ser usadas para fornecer aos aplicativos de dispositivo o acesso a dados.
  - O usuário do DEM não pode cancelar o registro de dispositivos registrados pelo DEM no próprio dispositivo usando o Portal da Empresa. O administrador do Intune pode cancelar o registro.
  - Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.
  - Os usuários não podem usar aplicativos VPP (Apple Volume Purchase Program) com licenças de usuário devido aos requisitos de ID da Apple para gerenciamento de aplicativo.
  - (Somente iOS) Se você usar o DEM para registrar dispositivos iOS, não poderá usar o Apple Configurator, o Apple DEP (Programa de registro de dispositivos) nem o ASM (Apple School Manager) para registrar dispositivos.
  - (Somente Android) Há um limite para o número de dispositivos Android for Work que podem ser registrados com uma única conta do DEM. No máximo 10 dispositivos de perfil de trabalho do Android podem ser registrados por conta do DEM. Essa limitação não se aplica ao registro do Android herdado.
  - Os dispositivos poderão instalar aplicativos se tiverem licenças de dispositivo.
  - Cada dispositivo exige uma licença de dispositivo. Saiba mais sobre [licenças de usuário e dispositivo](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Você pode implantar aplicativos da empresa para dispositivos gerenciados pelo gerente de registros de dispositivo. Implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** na conta de usuário do gerente de registros de dispositivo.
> Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais. Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do administrador do Intune.


## <a name="add-a-device-enrollment-manager"></a>Adicionar um gerenciador de registro de dispositivo

1.  No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Gerenciadores de registro de dispositivo**.

2.  Selecione **Adicionar**.

3.  Na folha **Adicionar Usuário**, insira um nome UPN para o usuário DEM e selecione **Adicionar**. O usuário DEM é adicionado à lista de usuários DEM.

## <a name="permissions-for-dem"></a>Permissões para o DEM

Funções do Azure AD global de Administrador de Serviços do Intune são necessárias para executar tarefas relacionadas ao registro de DEM no Portal de Administração. Essas funções também são necessárias para ver todos os usuários DEM, apesar de as permissões RBAC serem listadas e estarem disponíveis na função de Usuário personalizada. Um usuário sem a função Administrador Global ou Administrador de Serviços do Intune atribuída, mas que tem permissões de leitura para a função Gerentes de Registro de Dispositivo, pode ver somente os usuários do DEM que ele criou. O suporte à função RBAC para esses recursos será anunciada no futuro.

Se um usuário não tiver a função Administrador Global ou Administrador de Serviços do Intune atribuída, mas tiver permissões de leitura habilitadas para a função Gerentes de Registro de Dispositivo atribuída a ele, o usuário poderá ver apenas os usuários do DEM que ele criou.

## <a name="remove-a-device-enrollment-manager"></a>Remover um gerenciador de registro de dispositivo

Remover um gerenciador de registro de dispositivos não afeta os dispositivos registrados. Quando um gerenciador de registro de dispositivos é removido:

-   Os dispositivos registrados não são afetados e continuam sendo totalmente gerenciados.
-   As credenciais de conta do gerenciador de registro de dispositivo removido permanecem válidas.
-   O gerenciador de registro de dispositivos removido ainda não poderá apagar nem desativar dispositivos.
-   O gerenciador de registros de dispositivo removido pode registrar somente um número de dispositivos até o limite por usuário configurado pelo administrador do Intune.

**Para remover um gerenciador de registro de dispositivo**

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** e, em seguida, selecione **Gerentes de registro de dispositivo**.
2. Na folha **Gerenciadores de registro de dispositivo**, selecione o usuário DEM e selecione **Excluir**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Exibir as propriedades de um gerenciador de registro de dispositivo

1. No [Portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** e, depois, **Gerenciadores de registro de dispositivo**.
2. Na folha **Gerenciadores de registro de dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Propriedades**.
