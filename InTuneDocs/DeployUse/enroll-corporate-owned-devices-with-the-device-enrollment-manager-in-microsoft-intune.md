---
# required metadata

title: Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivo no Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivo no Microsoft Intune
As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário. O *Gerenciador de registro de dispositivos* é uma conta especial do Intune com permissão para registrar mais de cinco dispositivos. Você pode atribui-la a um gerente da loja ou supervisor, por exemplo, como um conta de usuário de gerenciador de registro de dispositivos, para permitir que ela faça o seguinte:

-   Registrar dispositivos no Intune

-   Fazer logon no portal de empresa para obter aplicativos da empresa

-   Instalar e desinstalar software

-   Configurar o acesso aos dados da empresa


**Exemplos de cenários do gerenciador de registro do dispositivo:** um restaurante quer oferecer tablets de ponto de venda para sua equipe de garçons e monitores de pedidos para sua equipe da cozinha. Os funcionários nunca precisam ter acesso aos dados da empresa ou fazer logon como um usuário. O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e registra os dispositivos da empresa usando essa conta. Como alternativa, o administrador pode conceder credenciais de gerenciador de registro de dispositivos a um gerente do restaurante, permitindo que ele registre e gerencie os dispositivos.

O administrador ou o gerente podem implantar aplicativos específicos da função para os dispositivos do restaurante. Um administrador também pode selecionar o dispositivo no console do Intune e retirá-lo de gerenciamento de dispositivos móveis com o console de administração.

Dispositivos registrados com uma conta DEM (gerenciador de registro do dispositivo) têm as seguintes restrições:
  - Nenhum usuário específico, então todos os dispositivos são livres de usuários; portanto, não há acesso de dados da empresa ou do email, embora a VPN, por exemplo, ainda possa fornecer aplicativos de dispositivos com acesso a dados
  - Sem acesso condicional pois esses são cenários por usuário
  - Não podem ser dispositivos de redefinição do portal da empresa
  - Nenhum aplicativo de Apple Volume Purchase Program (VPP) devido a requisitos de ID da Apple por usuário para o gerenciamento de aplicativo
  - Também não podem ser registrados com o Apple Configurator ou o programa de registro de dispositivo da Apple (dispositivos iOS)

> [!NOTE]
> Contas de usuário do gerenciador de registro de dispositivos com mais de 20 dispositivos registrados podem ter problemas ao usar o aplicativo Portal da Empresa. Para implantar aplicativos da empresa em dispositivos gerenciados com o gerenciador de registro do dispositivo, implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** para a conta de usuário do gerenciador de registro do dispositivo.
> Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais e apenas se eles foram registrados usando o aplicativo do Portal da Empresa. Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do Intune.

## Criar contas de gerenciador de registro de dispositivo
Contas de gerenciador de registro de dispositivos são contas de usuário com permissão para registrar um grande número de dispositivos corporativos. Somente os usuários no console do Intune podem gerenciadores de registro de dispositivos.

#### Adicionar um gerenciador de registro de dispositivos ao Intune

1.  Acesse o [Portal de conta do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) e entre na sua conta de administrador.

2.  Clique em **Adicionar usuário**.

3.  Confirme se a conta de usuário que será o gerenciador de registro de dispositivos está listada. Caso contrário, adicione o usuário clicando em **Novo** e concluindo o processo de Adicionar usuário. Uma licença de assinatura é necessária para cada usuário que acessa o serviço e o *gerenciador de registro do dispositivos* não pode ser um administrador do Intune. Determine se você precisa adicionar mais licenças antes de usar esse recurso.

4.  Faça logon no [Console de administração do Microsoft Intune](http://manage.microsoft.com) com sua inscrição de administrador.

5.  No painel de navegação, clique em **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**. Abra a página de Gerenciadores de Registro de Dispositivos.

6.  Clique em **Adicionar...**. A caixa de diálogo **Adicionar Gerenciador de Registro de Dispositivos** é aberta.

7.  Insira a **ID de usuário** da conta do Intune e clique em **OK**. O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.

8.  O gerenciador de registro de dispositivos pode registrar dispositivos móveis usando o mesmo procedimento que um usuário final usa para um cenário de BYOD no portal da empresa.

## Excluir um gerenciador de registro de dispositivos do Intune

1.  Faça logon no [Portal de administração do Microsoft Intune](http://manage.microsoft.com) com sua entrada de administrador.

2.  No painel de navegação, clique em **Admin** , vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**. Abra a página de Gerenciadores de Registro de Dispositivos.

3.  Selecione o **Usuário** gerenciador de registro de dispositivos que você deseja excluir e clique em **Excluir**. Este usuário não será excluído do Intune e os dispositivos gerenciados por ele permanecerão registrados no Intune. Excluir um gerenciador de registro de dispositivos impede que tal usuário registre outros dispositivos no Intune.

4.  Clique em **Sim** para confirmar que deseja excluir o gerenciador de registro de dispositivos.

Excluir um gerenciador de registro de dispositivos não afeta os dispositivos registrados. Quando um gerenciador de registro de dispositivos é excluído:

-   Nenhum dispositivo registrado é afetado

-   Os dispositivos registrados continuam sendo totalmente gerenciados

-   As credenciais da conta do gerenciador de registro de dispositivos excluído continuam válidas para fazer logon no portal da empresa para acessar aplicativos

-   As credenciais da conta do gerenciador de registro de dispositivos excluído não podem mais apagar ou desativar dispositivos

-   A relação da conta do gerenciador de registro de dispositivos excluído com os dispositivos registrados permanece, mas nenhum dispositivo adicional pode ser registrado


<!--HONumber=May16_HO3-->


