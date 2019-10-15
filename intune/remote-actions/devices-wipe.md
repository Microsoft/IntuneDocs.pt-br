---
title: Desativar ou apagar dispositivos usando o Microsoft Intune – Azure | Microsoft Docs
description: Desative ou apague um dispositivo Android, de perfil de trabalho Android, iOS, macOS ou Windows usando o Microsoft Intune. Além disso, exclua um dispositivo do Azure Active Directory.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f81dcf6a3553b4ff08ec6c2dbffda24bc7946b73
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728397"
---
# <a name="remove-devices-by-using-wipe-retire-or-manually-unenrolling-the-device"></a>Remova dispositivos por meio de apagamento, desativação ou cancelando o registro do dispositivo manualmente

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usando as ações **Desativar** ou **Apagar**, você pode remover dispositivos do Intune que não são mais necessários, que estão sendo realocados ou que estão ausentes. Os usuários também podem emitir um comando remoto do Portal da Empresa do Intune para dispositivos que estão registrados no Intune.

> [!NOTE]
> Antes de remover um usuário do Azure AD (Azure Active Directory), use as ações **Apagar** ou **Desativar** para todos os dispositivos associados a esse usuário. Se você remover usuários que tenham dispositivos gerenciados do Azure AD, o Intune não poderá apagar nem desativar esses dispositivos.

## <a name="wipe"></a>Apagamento

A ação **Apagar** restaura um dispositivo para as configurações padrão de fábrica. Os dados do usuário serão mantidos se você marcar a caixa de seleção **Manter estado de registro e conta do usuário**. Caso contrário, todos os dados, aplicativos e configurações serão removidos.

|Ação de apagamento|**Manter o estado do registro e a conta de usuário**|Removido do gerenciamento do Intune|Descrição|
|:-------------:|:------------:|:------------:|------------|
|**Apagamento**| Não verificado | Sim | Apaga todas as contas de usuário, dados, políticas de MDM e configurações. Redefine o sistema operacional para seu estado e configurações padrão.|
|**Apagamento**| Verificado | Não | Apaga todas as políticas de MDM. Mantém as contas de usuário e dados. Redefine as configurações de usuário de volta ao padrão. Redefine o sistema operacional para seu estado e configurações padrão.|


> [!NOTE]
> A ação Limpar não está disponível para dispositivos iOS registrados por meio do Registro de Usuário.

A opção **Reter estado de registro e conta do usuário** está disponível apenas para o Windows 10 versão 1709 ou posterior.

As políticas de MDM serão reaplicadas na próxima vez que o dispositivo se conectar ao Intune.

Um apagamento é útil para redefinir um dispositivo antes de fornecê-lo a um novo usuário ou quando o dispositivo é perdido ou roubado. Tenha cuidado ao selecionar o **apagamento**. Os dados no dispositivo não podem ser recuperados.

### <a name="wiping-a-device"></a>Apagando um dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecione **Dispositivos** > **Todos os dispositivos**.
4. Selecione o nome do dispositivo que você deseja apagar.
5. No painel que mostra o nome do dispositivo, selecione **Apagar**.
6. Para o Windows 10 versão 1709 ou posterior, você também tem a opção **Reter estado de registro e conta do usuário**. 
    
    |Retido durante um apagamento |Não mantido|
    | -------------|------------|
    |Contas do usuário associadas ao dispositivo|Arquivos do usuário|
    |Estado do computador \(ingresso no domínio, ingresso no Azure AD)| Aplicativos instalados pelo usuário \(aplicativos do Win32 e da loja)|
    |Registro de MDM (gerenciamento de dispositivo móvel)|Configurações do dispositivo não padrão|
    |Aplicativos instalados pelo OEM \(aplicativos do Win32 e da loja)||
    |Perfil de usuário||
    |Dados do usuário fora do perfil do usuário||
    |Logon automático do usuário|| 
    
         
7. Para confirmar o apagamento, selecione **Sim**.

Se o dispositivo estiver ligado e conectado, a ação **Apagar** será propagada para todos os tipos de dispositivos em menos de 15 minutos.

## <a name="retire"></a>Desativar

A ação **Desativar** remove os dados do aplicativo gerenciado (quando é o caso), as configurações e os perfis de email que foram atribuídos usando o Intune. O dispositivo é removido do gerenciamento do Intune. Isso ocorrerá na próxima vez que o dispositivo fizer check-in e receber a ação remota **Desativar**. O dispositivo ainda é exibido no Microsoft Intune até o check-in. Se você deseja remover imediatamente os dispositivos obsoletos, use [Excluir ação](devices-wipe.md#delete-devices-from-the-intune-portal).

**Desativar** deixa os dados pessoais do usuário no dispositivo.  

As tabelas a seguir descrevem quais dados são removidos e o efeito da ação **Desativar** nos dados que permanecem no dispositivo após a remoção de dados da empresa.

### <a name="ios"></a>iOS

|Tipo de dado|iOS|
|-------------|-------|
|Aplicativos da empresa e dados associados instalados pelo Intune|**Aplicativos instalados usando o Portal da Empresa:** Para aplicativos que são fixados ao perfil de gerenciamento, todos os dados de aplicativo e os aplicativos propriamente ditos são removidos. Esses aplicativos incluem os aplicativos instalados originalmente da App Store e posteriormente gerenciados como aplicativos da empresa. <br /><br /> **Aplicativos da Microsoft que usam o gerenciamento de aplicativos móveis e foram instalados da App Store:** Para aplicativos que não são gerenciados pelo Portal da Empresa, os dados de aplicativo da empresa que são protegidos pela criptografia de MAM (gerenciamento de aplicativo móvel) dentro do armazenamento local do aplicativo são removidos. Dados protegidos pela criptografia de MAM fora do aplicativo permanecem criptografados e não utilizáveis, mas não são removidos. Os dados pessoais de aplicativos e os aplicativos não são removidos.|
|Settings|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Certificados são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Email|Os perfis de email provisionados por meio do Intune são removidos. O email armazenado em cache no dispositivo é excluído.|
|Cancelamento de ingresso no Azure AD|O registro do Azure AD é removido.|

### <a name="android"></a>Android

|Tipo de dado|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Links da Web|Removidos.|Removidos.|
|Aplicativos Google Play não gerenciados|Os aplicativos e dados permanecem instalados. <br /> <br />Os dados de aplicativo da empresa que são protegidos pela criptografia de MAM (gerenciamento de aplicativo móvel) dentro do armazenamento local do aplicativo são removidos. Dados protegidos pela criptografia de MAM fora do aplicativo permanecem criptografados e não utilizáveis, mas não são removidos. |Os aplicativos e dados permanecem instalados. <br /> <br />Os dados de aplicativo da empresa que são protegidos pela criptografia de MAM (gerenciamento de aplicativo móvel) dentro do armazenamento local do aplicativo são removidos. Dados protegidos pela criptografia de MAM fora do aplicativo permanecem criptografados e não utilizáveis, mas não são removidos.|
|Aplicativos de linha de negócios não gerenciados|Os aplicativos e dados permanecem instalados.|Os aplicativos são desinstalados e os dados locais do aplicativo são removidos. Nenhum dado fora do aplicativo (por exemplo, em um cartão SD) é removido.|
|Aplicativos Google Play gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Os dados protegidos pela criptografia do MAM (Gerenciamento de aplicativo móvel) de fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados, mas não são removidos.|
|Aplicativos de linha de negócios gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|
|Settings|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|
|Configurações do perfil de certificado|Os certificados são revogados, mas não removidos.|Certificados são removidos e revogados.|
|Agente de gerenciamento|O privilégio de administrador do dispositivo é revogado.|O privilégio de administrador do dispositivo é revogado.|
|Email|N/D (perfis de email não são compatíveis com dispositivos Android)|Os perfis de email provisionados por meio do Intune são removidos. O email armazenado em cache no dispositivo é excluído.|
|Cancelamento de ingresso no Azure AD|O registro do Azure AD é removido.|O registro do Azure AD é removido.|

### <a name="android-work-profile"></a>Perfil de trabalho Android

A remoção dos dados da empresa de um dispositivo de perfil de trabalho Android remove todos os dados, os aplicativos e as configurações do perfil de trabalho desse dispositivo. O dispositivo é desativado do gerenciamento com o Intune. Não há suporte para apagamento nos perfis de trabalho do Android.

### <a name="android-enterprise-kiosk-devices"></a>Dispositivos de quiosque Android Enterprise

Você só pode apagar os dispositivos de quiosque. Você não pode desativar dispositivos de quiosque do Android.


### <a name="macos"></a>macOS

|Tipo de dado|macOS|
|-------------|-------|
|Settings|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Os certificados que foram implantados por meio do MDM são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Outlook|Se o Acesso Condicional for habilitado, o dispositivo não receberá um novo email.|
|Cancelamento de ingresso no Azure AD|O registro do Azure AD é removido.|

### <a name="windows"></a>Windows

|Tipo de dado|Windows 8.1 (MDM) e Windows RT 8.1|Windows RT|Windows Phone 8.1 e Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplicativos da empresa e dados associados instalados pelo Intune|As chaves são revogadas para arquivos protegidos pelo EFS. O usuário não pode abrir os arquivos.|Aplicativos da empresa não são removidos.|Os aplicativos instalados originalmente por meio do Portal da empresa são desinstalados. Os dados de aplicativo da empresa são removidos.|Os aplicativos são desinstalados. Chaves de sideload são removidas.<br>Na versão 1703 do Windows 10 (Atualização para Criadores) e em versões posteriores, os aplicativos do Office 365 ProPlus não são removidos. Os aplicativos Win32 instalados pela extensão de gerenciamento do Intune não serão desinstalados em dispositivos não registrados. Os administradores podem aproveitar a exclusão de atribuição para não oferecer aplicativos Win32 em dispositivos BYOD.|
|Settings|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|Sem suporte.|Removidos.|
|Configurações do perfil de certificado|Certificados são removidos e revogados.|Certificados são removidos e revogados.|Sem suporte.|Certificados são removidos e revogados.|
|Email|Remove o email habilitado para EFS. Isso inclui emails e anexos no aplicativo Mail para Windows.|Sem suporte.|Os perfis de email provisionados por meio do Intune são removidos. O email armazenado em cache no dispositivo é excluído.|Remove o email habilitado para EFS. Isso inclui emails e anexos no aplicativo Mail para Windows. Remove contas de email que foram provisionadas pelo Intune.|
|Cancelamento de ingresso no Azure AD|Não.|Não.|O registro do Azure AD é removido.|O registro do Azure AD é removido.|

> [!NOTE]
> Para dispositivos Windows 10 que ingressam no Microsoft Azure AD durante a OOBE (tela de apresentação), o comando "desativar" removerá do dispositivo todas as contas do Microsoft Azure AD. Faça os procedimentos descritos em [Iniciar o computador no modo de segurança](https://support.microsoft.com/en-us/help/12376/windows-10-start-your-pc-in-safe-mode) para entrar como administrador local e recuperar o acesso aos dados locais do usuário. 

### <a name="retire"></a>Desativar

1. Entre no [Intune no portal do Azure](https://aka.ms/intuneportal).
2. No painel **Dispositivos**, selecione **Todos os dispositivos**.
3. Selecione o nome do dispositivo que você deseja desativar.
4. No painel que mostra o nome do dispositivo, selecione **Desativar**. Para confirmar, selecione **Sim**.

Se o dispositivo estiver ligado e conectado, a ação **Desativar** será propagada para todos os tipos de dispositivos em menos de 15 minutos.

## <a name="delete-devices-from-the-intune-portal"></a>Excluir dispositivos do portal do Intune

Se você quiser remover dispositivos do portal do Intune, poderá excluí-los do painel específico do dispositivo. Na próxima vez que o dispositivo fizer check-in, quaisquer dados da empresa contidos nele serão removidos.

1. Entre no [Intune no portal do Azure](https://aka.ms/intuneportal).
2. Escolha **Dispositivos** > **Todos os dispositivos** > escolher dispositivos que você deseja excluir > **Excluir**.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Excluir dispositivos automaticamente com regras de limpeza
Você pode configurar o Intune para excluir automaticamente os dispositivos que parecem estar inativos, obsoletos ou sem resposta. Essas regras de limpeza monitoram continuamente seu inventário de dispositivos para que os registros de dispositivos permaneçam atualizados. Os dispositivos excluídos dessa maneira são removidos do gerenciamento do Intune.
1. Entre no [Intune no portal do Azure](https://aka.ms/intuneportal).
2. Escolha **Dispositivos** > **Regras de limpeza de dispositivo** > **Sim**.
3. Na caixa **Excluir dispositivos que ainda não fizeram check-in para este número de dias**, digite um número entre 30 e 270.
4. Escolha **Salvar**.



## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Excluir dispositivos do portal do Azure Active Directory

Talvez seja necessário excluir dispositivos do Azure AD devido a problemas de comunicação ou a dispositivos ausentes. É possível usar a ação **Excluir** para remover registros de dispositivo do Portal do Azure para dispositivos que você sabe que estão inacessíveis e provavelmente não se comunicarão com o Azure novamente. A ação **Excluir** não remove um dispositivo do gerenciamento.

1. Entre no [Azure Active Directory no Portal do Azure](https://aka.ms/accessaad) usando suas credenciais de administrador. Você também pode entrar no [Centro de administração do Microsoft 365](https://admin.microsoft.com). No menu, selecione **Centros de administração** > **Azure AD**.
2. Se não tiver uma, crie uma assinatura do Azure. Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (selecione link de assinatura **Registrar seu Azure Active Directory gratuito** ).
3. Selecione **Azure Active Directory** e, em seguida, selecione sua organização.
4. Selecione a guia **Usuários** .
5. Selecione o usuário associado ao dispositivo que você deseja excluir.
6. Selecione **Dispositivos**.
7. Remova os dispositivos conforme apropriado. Por exemplo, você pode remover dispositivos que não estão mais em uso ou dispositivos que têm definições imprecisas.

## <a name="retire-an-apple-dep-device-from-intune"></a>Desativar um dispositivo DEP da Apple do Intune

Se você quiser remover completamente um dispositivo DEP da Apple do gerenciamento pelo Intune, siga estas etapas:

1. Entre no [Intune no portal do Azure](https://aka.ms/intuneportal).
2. Escolha **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo > **Desativar**.
![Captura de tela da desativação](./media/devices-wipe/retire.png)
3. Visite [deploy.apple.com](http://deploy.apple.com) e pesquise pelo dispositivo usando o respectivo número de série.
4. No menu **Atribuído a**, escolha **Não atribuído**.

5. Escolha **Reatribuir**.

    ![Captura de tela para reatribuição da Apple](./media/devices-wipe/apple-reassign.png)

## <a name="fresh-start"></a>Novo Início

Aplicável a dispositivos Windows 10. Leia mais sobre o [Novo Início](device-fresh-start.md).

## <a name="next-steps"></a>Próximas etapas

Se você quiser registrar novamente um dispositivo excluído, consulte [Opções de registro](../enrollment/enrollment-options.md).
