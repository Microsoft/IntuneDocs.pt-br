---
title: Registrar com o gerenciador de registro do dispositivo | Microsoft Docs
description: "A conta do DEM (Gerenciador de Registro de Dispositivos) pode gerenciar grandes quantidades de dispositivos móveis corporativos compartilhados com uma única conta de usuário."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 751c6bee73175b8e6ac5ad192f12540520c676c0


---


# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Registrar dispositivos corporativos com o Gerenciador de registro de dispositivo no Microsoft Intune
As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. A conta do *gerenciador de registro de dispositivos* (DEM) é uma conta especial do Intune que pode registrar até 1.000 dispositivos. Cada dispositivo registrado usa uma única licença. Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados em vez de dispositivos pessoais ("BYOD"). Os usuários não poderão usar aplicativos de email "nativo", por exemplo. O licenciamento do DEM é por dispositivo, não por usuário.

Por exemplo, você pode atribuir uma conta de usuário do gerenciador de registro de dispositivos a um gerente ou supervisor de loja para permitir que ela faça o seguinte:

-   Registre dispositivos no Intune.

-   Entre no Portal de Empresa para obter aplicativos corporativos.

-   Instale e desinstale software.

-   Configure o acesso aos dados da empresa.


**Cenário de um gerenciador de registro do dispositivo:** um restaurante quer oferecer tablets de ponto de venda para sua equipe de garçons e monitores de pedidos para sua equipe da cozinha. Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários. O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e registra os dispositivos da empresa usando essa conta. Como alternativa, o administrador pode conceder credenciais do gerenciador de registro de dispositivos a um gerente do restaurante, permitindo que ele registre e gerencie os dispositivos.

O administrador ou o gerente podem implantar aplicativos específicos da função para os dispositivos do restaurante. Um administrador também pode selecionar o dispositivo no console do Intune e retirá-lo de gerenciamento de dispositivos móveis com o console de administração.

Dispositivos registrados com uma conta de gerenciador de registro de dispositivos têm as seguintes limitações:
  - Não há qualquer "usuário" de dispositivo específico, portanto, não há nenhum acesso a dados da empresa ou email. No entanto, a VPN, por exemplo, ainda pode fornecer ao dispositivo aplicativos com acesso aos dados.
  - Não há acesso condicional, pois esses são cenários por usuário.
  - Não é possível redefinir esses dispositivos no Portal da Empresa.
  - Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.
  - Não é possível usar aplicativos VPP (Programa de compra por volume da Apple) devido a requisitos de ID da Apple por usuário para o gerenciamento de aplicativo.
  - (iOS) Também não podem ser registrados com o Apple Configurator ou o DEO (programa de registro de dispositivos) da Apple, mas o DEP ou dispositivos gerenciados pelo Apple Configurator podem ser registrados sem afinidade de usuário.

> [!NOTE]
> Para implantar aplicativos da empresa em dispositivos gerenciados pelo gerenciador de registro do dispositivo, implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** para a conta de usuário do gerenciador de registro do dispositivo.
> Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais. Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do administrador do Intune.

## <a name="create-device-enrollment-manager-accounts"></a>Criar contas de gerenciador de registro de dispositivo
Contas de gerenciador de registro de dispositivos são contas de usuário com permissão para registrar um grande número de dispositivos corporativos. Somente os usuários no console do Intune podem gerenciadores de registro de dispositivos.

#### <a name="add-a-device-enrollment-manager-to-intune"></a>Adicionar um gerenciador de registro de dispositivos ao Intune

1.  Acesse o [portal de conta do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) e entre em sua conta de administrador.

2.  Escolha **Adicionar usuário**.

3.  Confirme se a conta de usuário que será o gerenciador de registro de dispositivos está listada. Se não estiver, adicione o usuário escolhendo **Novo** e concluindo o processo de **Adicionar usuário**. Uma licença de assinatura é necessária para cada usuário que acessa o serviço. O gerenciador de registro de dispositivos não pode ser um administrador do Intune. Verifique se você precisa adicionar mais licenças antes de usar esse recurso.

4.  Entre no [Console de administração do Microsoft Intune](http://manage.microsoft.com) com suas credenciais de administrador.

5.  No painel de navegação, escolha **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**. A página **Gerenciadores de Registro de Dispositivos** abre.

6.  Escolha **Adicionar...**. A caixa de diálogo **Adicionar Gerenciador de Registro de Dispositivos** é aberta.

7.  Insira a **ID de usuário** da conta do Intune e escolha **OK**. O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.

8.  O gerenciador de registro de dispositivos pode registrar dispositivos móveis usando o mesmo procedimento que um usuário final utiliza para um cenário de BYOD no Portal da Empresa. O usuário final do gerenciador pode instalar o aplicativo do Portal da Empresa e registrar o dispositivo usando suas credenciais do DEM em até 1.000 dispositivos.

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Excluir um gerenciador de registro de dispositivos do Intune

1.  Entre no [Portal de administração do Microsoft Intune](http://manage.microsoft.com) com suas credenciais de administrador.

2.  No painel de navegação, escolha **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**. A página **Gerenciadores de Registro de Dispositivos** abre.

3.  Selecione o **Usuário** gerenciador de registro de dispositivos que você deseja excluir e escolha **Excluir**. Este usuário não será excluído do Intune e os dispositivos gerenciados por ele permanecerão registrados no Intune. Excluir um gerenciador de registro de dispositivos impede que tal usuário registre outros dispositivos no Intune.

4.  Escolha **Sim** para confirmar que deseja excluir o gerenciador de registro de dispositivos.

Excluir um gerenciador de registro de dispositivos não afeta os dispositivos registrados. Quando um gerenciador de registro de dispositivos é excluído:

-   Nenhum dispositivo registrado é afetado.

-   Os dispositivos registrados continuam sendo totalmente gerenciados.

-   As credenciais da conta do gerenciador de registro de dispositivos excluído continuam válidas para entrar no Portal da Empresa para acessar aplicativos.

-   As credenciais da conta do gerenciador de registro de dispositivos excluído não podem mais apagar ou desativar dispositivos.

-   A relação da conta do gerenciador de registro de dispositivos excluído com os dispositivos registrados permanece, mas nenhum dispositivo adicional pode ser registrado.



<!--HONumber=Dec16_HO2-->


