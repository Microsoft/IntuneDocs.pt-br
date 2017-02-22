---
title: "Registrar dispositivos – Gerenciador de registro de dispositivos | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: use a conta do gerenciador de registro do dispositivo para registrar dispositivos no Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 521a37044d6721fe905db7740329688ba2c24b35
ms.openlocfilehash: 1ab58388f3d126d5d831c65ad3342ec87fb77b91

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Registrar dispositivos usando o gerenciador de registro de dispositivo

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A conta do *DEM* (gerenciador de registro de dispositivos) é uma conta especial do usuário que pode registrar até 1.000 dispositivos. Adicionar usuários existentes à conta do DEM para fornecer recursos de DEM especiais. Cada dispositivo registrado usa uma única licença. Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados em vez de dispositivos pessoais ("BYOD").  

Os usuários devem existir no Portal do Azure para serem adicionados como gerenciadores de registro do dispositivo. Para uma melhor segurança, o usuário do DEM não deve ser um administrador do Intune também.

>[!NOTE]
>O método de registro DEM não pode ser usado com esses outros métodos de registro: [Apple Configurator com o Assistente de Configuração](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md), [Apple Configurator com registro direto](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md) ou [Programa de registro de dispositivos](enroll-ios-devices-using-device-enrollment-program.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemplo de um cenário do gerenciador de registro de dispositivos

Um restaurante quer fornecer 50 tablets de ponto de venda para sua equipe e faz o pedido de monitores para sua equipe da cozinha. Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários. O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e adiciona um supervisor do restaurante à conta DEM, na verdade concedendo recursos de DEM a esse supervisor. O supervisor agora pode registrar os 50 dispositivos de tablets usando as credenciais do DEM.

Somente os usuários no console do Intune podem gerenciadores de registro de dispositivos. O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.

O usuário do DEM pode:

-   Registrar até 1000 dispositivos no Intune.
-   Entre no Portal de Empresa para obter aplicativos corporativos.
-   Configurar o acesso aos dados da empresa implantando aplicativos específicos da função nos tablets.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitações de dispositivos registrados com uma conta do DEM

Dispositivos registrados com uma conta de gerenciador de registro de dispositivos têm as seguintes limitações:

  - Não há nenhum "usuário" de dispositivo específico. Portanto, não há nenhum acesso a dados da empresa ou email. No entanto, a VPN, por exemplo, ainda pode ser usada para fornecer aplicativos de dispositivo com acesso a dados.

  - Não há acesso condicional, pois esses são cenários por usuário.

  - O usuário do DEM não pode cancelar o registro de dispositivos registrados pelo DEM no próprio dispositivo usando o Portal da Empresa. O administrador do Intune tem essa funcionalidade, mas o usuário do DEM não.

  - Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.
 
  - Os usuários não podem usar aplicativos VPP (Apple Volume Purchase Program) devido aos requisitos de ID da Apple por usuário para o gerenciamento de aplicativo.
 
  - (somente iOS) Se você usar o DEM para registrar dispositivos iOS, não poderá usar o Apple Configurator ou o DEP(Programa de registro de dispositivo) da Apple para registrar dispositivos.


> [!NOTE]
> Para implantar aplicativos da empresa em dispositivos gerenciados pelo gerenciador de registro do dispositivo, implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** para a conta de usuário do gerenciador de registro do dispositivo.
> Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais. Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do administrador do Intune.


## <a name="add-a-device-enrollment-manager"></a>Adicionar um gerenciador de registro de dispositivo

1.  No Portal do Azure, escolha **Mais Serviços**, digite **Intune** na caixa de texto e escolha **Outros** > **Intune**.

2.  Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.

3.  Selecione **Adicionar**.

4.  Na folha **Adicionar Usuário**, insira um nome UPN para o usuário DEM e selecione **Adicionar**. O usuário DEM é adicionado à lista de usuários DEM.

## <a name="remove-a-device-enrollment-manager"></a>Remover um gerenciador de registro de dispositivo

Remover um gerenciador de registro de dispositivos não afeta os dispositivos registrados. Quando um gerenciador de registro de dispositivos é removido:

-   Remover um usuário da lista de usuários DEM não afeta os dispositivos registrados, que continuam sendo totalmente gerenciados.

-   As credenciais de conta do gerenciador de registro de dispositivo removido permanecem válidas.

-   O gerenciador de registro de dispositivos removido ainda não poderá apagar nem desativar dispositivos.

-   O gerenciador de registro de dispositivo removido não pode registrar dispositivos adicionais a menos que o limite por dispositivo, configurado pelo administrador do Intune, não tenha sido atingido.

**Para remover um gerenciador de registro de dispositivo**

1. Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.

2. Na folha **Gerenciadores de Registro de Dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Remover**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Exibir as propriedades de um gerenciador de registro de dispositivo

1. Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.

2. Na folha **Gerenciadores de Registro de Dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Propriedades**.



<!--HONumber=Feb17_HO1-->


