---
title: Registrar com o gerenciador de registro do dispositivo | Microsoft Docs
description: "A conta do DEM (Gerenciador de Registro de Dispositivos) pode gerenciar grandes quantidades de dispositivos móveis corporativos compartilhados com uma única conta de usuário."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d1f63a9e65435e2cfc421c23de3ad87363bc446d
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---


# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Registrar dispositivos corporativos com o Gerenciador de registro de dispositivo no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A conta do *DEM* (gerenciador de registro de dispositivos) é uma conta especial do usuário que pode registrar até 1.000 dispositivos. Adicionar usuários existentes à conta do DEM para fornecer recursos de DEM especiais. Cada dispositivo registrado usa uma única licença. Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados (ou seja, sem afinidade do usuário) em vez de dispositivos pessoais ("BYOD").  

Os usuários devem existir no Portal do Azure para serem adicionados como gerenciadores de registro do dispositivo. Para uma melhor segurança, o usuário do DEM não deve ser um administrador do Intune também.

>[!NOTE]
>O método de registro DEM não pode ser usado com o [Apple Configurator Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) ou [registro direto](ios-direct-enrollment-in-microsoft-intune.md) ou com o [método de registro de DEP](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemplo de um cenário do gerenciador de registro de dispositivos

Um restaurante quer fornecer 50 tablets de ponto de venda para sua equipe e faz o pedido de monitores para sua equipe da cozinha. Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários. O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e adiciona um supervisor do restaurante à conta DEM, na verdade concedendo recursos de DEM a esse supervisor. O supervisor agora pode registrar os 50 dispositivos de tablets usando as credenciais do DEM.

Somente os usuários no console do Intune podem gerenciadores de registro de dispositivos. O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.

O usuário do DEM pode:

-   Registrar até 1000 dispositivos no Intune
-   Usar o aplicativo Portal de Empresa para obter os aplicativos corporativos
-   Configurar o acesso aos dados da empresa implantando aplicativos específicos da função nos tablets

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

1.  Certifique-se de que o usuário que você deseja adicionar à conta DEM já exista. Se você precisar adicionar o usuário, entre no [Portal do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) e siga as etapas em [Adicionar usuários individualmente ou em lote ao portal do Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

2.  Entre no [Console de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador.

3.  No painel de navegação, escolha **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**. A página **Gerenciadores de Registro de Dispositivos** abre.

4.  Escolha **Adicionar...**. A caixa de diálogo **Adicionar Gerenciador de Registro de Dispositivos** é aberta.

5.  Insira a **ID de usuário** da conta do Intune e escolha **OK**.

    O usuário do DEM pode registrar dispositivos móveis usando o mesmo procedimento que um usuário final utiliza para um cenário de BYOD no Portal da Empresa. O usuário final do gerenciador pode instalar o aplicativo do Portal da Empresa e registrar o dispositivo usando suas credenciais do DEM em até 1.000 dispositivos. Para as etapas de registro do usuário final para cada plataforma, consulte:

  - [Registrar seu dispositivo iOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [Registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [Registrar seu dispositivo Windows no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Excluir um gerenciador de registro de dispositivos do Intune

1.  Entre no [Portal de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador.

2.  No painel de navegação, escolha **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**. A página **Gerenciadores de Registro de Dispositivos** abre.

3.  Selecione o **Usuário** gerenciador de registro de dispositivos que você deseja excluir e escolha **Excluir**. Este usuário não será excluído do Intune e os dispositivos gerenciados por ele permanecerão registrados no Intune. Excluir um gerenciador de registro de dispositivos impede que tal usuário registre outros dispositivos no Intune.

4.  Escolha **Sim** para confirmar que deseja excluir o gerenciador de registro de dispositivos.

Excluir um gerenciador de registro de dispositivos não afeta os dispositivos registrados. Quando um gerenciador de registro de dispositivos é excluído:

-   Nenhum dispositivo registrado é afetado.

-   Os dispositivos registrados continuam sendo totalmente gerenciados.

-   As credenciais da conta do gerenciador de registro de dispositivos excluído continuam válidas para entrar no Portal da Empresa para acessar aplicativos.

-   As credenciais da conta do gerenciador de registro de dispositivos excluído não podem mais apagar ou desativar dispositivos.

-   A relação da conta do gerenciador de registro de dispositivos excluído com os dispositivos registrados permanece, mas nenhum dispositivo adicional pode ser registrado.

