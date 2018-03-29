---
title: Remover dados da empresa em dispositivos que usam o Microsoft Intune – Azure | Microsoft Docs
description: Remova dados da empresa em um dispositivo ou realize uma redefinição de fábrica em um dispositivo Android, Android for Work, iOS, macOS ou Windows usando o Microsoft Intune. Além disso, exclua um dispositivo do Azure Active Directory.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4581b59de68c2877b122887fa1ffe86eaa2b92c
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Remova dispositivos por meio da redefinição de fábrica ou remova os dados da empresa

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

É possível remover dispositivos do Intune que não sejam mais necessários, que estejam sendo realocados ou que estejam ausentes. Faça isso usando as ações **Remover dados da empresa** ou **Restaurar configurações de fábrica**. Os usuários também podem emitir um comando remoto do Portal da Empresa do Intune para dispositivos de propriedade pessoal registrados no Intune.

> [!NOTE]
> Antes de remover um usuário do Azure AD (Active Directory), use as ações **Restaurar configurações de fábrica** ou **Remover os dados da empresa** para todos os dispositivos associados a esse usuário. Se você remover os usuários que gerenciaram dispositivos do Azure AD, o Intune não poderá mais emitir uma redefinição de fábrica nem remover dados da empresa para esses dispositivos.

## <a name="factory-reset"></a>Redefinição de fábrica

A ação **Restaurar configurações de fábrica** restaura um dispositivo para as configurações padrão de fábrica. Uma redefinição de fábrica restaura todos os dados e configurações da empresa e do usuário. O dispositivo é removido do gerenciamento do Intune. Uma redefinição de fábrica será útil para redefinir um dispositivo antes de dar a ele um novo usuário ou quando o dispositivo tiver sido perdido ou roubado. Tome cuidado ao selecionar **Restaurar configurações de fábrica**. Os dados no dispositivo não podem ser recuperados.

### <a name="factory-reset-a-device"></a>Restaurar configurações de fábrica de um dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** > **Todos os dispositivos**.
4. Selecione o nome do dispositivo cujas configurações você deseja restaurar.
5. No painel que mostra o nome do dispositivo, selecione **Restaurar configurações de fábrica**.
6. Para o Windows 10 versão 1709 ou posterior, você também tem a opção **Reter estado de registro e conta do usuário**. 
    
    |Retidos durante uma redefinição de fábrica|Não mantido|
    | -------------|------------|
    |Contas do usuário associadas ao dispositivo|Arquivos do usuário|
    |Estado do computador \(ingresso no domínio, ingresso no Azure AD)| Aplicativos instalados pelo usuário \(aplicativos do Win32 e da loja)|
    |Registro de MDM (gerenciamento de dispositivo móvel)|Configurações do dispositivo não padrão|
    |Aplicativos instalados pelo OEM \(aplicativos do Win32 e da loja)||
    |Perfil de usuário||
    |Dados do usuário fora do perfil do usuário||
    |Logon automático do usuário|| 
    
         
7. Para confirmar a redefinição de fábrica, selecione **Sim**.

Se o dispositivo estiver ligado e conectado, a ação **Restaurar configurações de fábrica** se propagará entre todos os tipos de dispositivo em menos de 15 minutos.

## <a name="remove-company-data"></a>Remover os dados da empresa

A ação **Remover dados da empresa** remove dados do aplicativo gerenciado (quando for o caso), configurações e perfis de email que foram atribuídos usando o Intune. **Remover dados da empresa** deixa os dados pessoais do usuário no dispositivo. O dispositivo é removido do gerenciamento do Intune. 

As tabelas a seguir descrevem quais dados são removidos e o efeito da ação **Remover dados da empresa** nos dados que permanecem no dispositivo depois da remoção dos dados da empresa.

### <a name="ios"></a>iOS

|Tipo de dados|iOS|
|-------------|-------|
|Aplicativos da empresa e dados associados instalados pelo Intune|Aplicativos são desinstalados. Dados de aplicativo da empresa são removidos.<br /><br />Os dados dos aplicativos da Microsoft que usam o gerenciamento de aplicativos móveis são removidos. O aplicativo não é removido.|
|Configurações|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Certificados são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Email|Os perfis de email provisionados por meio do Intune são removidos. O email armazenado em cache no dispositivo é excluído.|
|Outlook|Mensagens de email recebidas pelo aplicativo Microsoft Outlook para iOS são removidas.|
|Cancelamento de ingresso no Azure AD|O registro do Azure AD é removido.|
|Contacts |Os contatos sincronizados diretamente do aplicativo com o catálogo de endereços nativos são removidos. Quaisquer contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser removidos. <br /> <br />No momento, apenas o aplicativo do Outlook é compatível.

### <a name="android"></a>Android

|Tipo de dados|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Links da Web|Removidos.|Removidos.|
|Aplicativos Google Play não gerenciados|Aplicativos e dados permanecem instalados.|Aplicativos e dados permanecem instalados.|
|Aplicativos de linha de negócios não gerenciados|Aplicativos e dados permanecem instalados.|Os aplicativos são desinstalados e os dados locais do aplicativo são removidos. Nenhum dado fora do aplicativo (por exemplo, em um cartão SD) é removido.|
|Aplicativos Google Play gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Os dados protegidos pela criptografia do MAM (Gerenciamento de aplicativo móvel) de fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados, mas não são removidos.|
|Aplicativos de linha de negócios gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|
|Configurações|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|
|Configurações do perfil de certificado|Os certificados são revogados, mas não removidos.|Certificados são removidos e revogados.|
|Agente de gerenciamento|O privilégio de administrador do dispositivo é revogado.|O privilégio de administrador do dispositivo é revogado.|
|Email|N/D (perfis de email não são compatíveis com dispositivos Android)|Os perfis de email provisionados por meio do Intune são removidos. O email armazenado em cache no dispositivo é excluído.|
|Outlook|Emails recebidos pelo aplicativo do Outlook para Android serão removidos, mas somente se o Outlook estiver protegido pelas políticas de MAM. Caso contrário, o Outlook não será apagado quando o registro do dispositivo for cancelado.|Emails recebidos pelo aplicativo do Outlook para Android serão removidos, mas somente se o Outlook estiver protegido pelas políticas de MAM. Caso contrário, o Outlook não será apagado quando o registro do dispositivo for cancelado.|
|Cancelamento de ingresso no Azure AD|O registro do Azure AD é removido.|O registro do Azure AD é removido.|
|Contacts |Os contatos sincronizados diretamente do aplicativo com o catálogo de endereços nativos são removidos. Quaisquer contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser removidos. <br /> <br />No momento, apenas o aplicativo do Outlook é compatível.|Os contatos sincronizados diretamente do aplicativo com o catálogo de endereços nativos são removidos. Quaisquer contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser removidos. <br /> <br />No momento, apenas o aplicativo do Outlook é compatível.

### <a name="android-for-work"></a>Android for Work

Executar a remoção dos dados da empresa em um dispositivo Android for Work remove todos os dados, aplicativos e as configurações no perfil de trabalho nesse dispositivo. O dispositivo é desativado do gerenciamento com o Intune. Não há suporte para a redefinição de fábrica no Android for Work.


### <a name="macos"></a>macOS

|Tipo de dados|macOS|
|-------------|-------|
|Configurações|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Os certificados que foram implantados por meio do MDM são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Outlook|Se o acesso condicional for habilitado, o dispositivo não receberá um novo email.|
|Cancelamento de ingresso no Azure AD|O registro do Azure AD é removido.|

### <a name="windows"></a>Windows

|Tipo de dados|Windows 8.1 (MDM) e Windows RT 8.1|Windows RT|Windows Phone 8.1 e Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplicativos da empresa e dados associados instalados pelo Intune|As chaves são revogadas para arquivos protegidos pelo EFS. O usuário não pode abrir os arquivos.|Aplicativos da empresa não são removidos.|Os aplicativos instalados originalmente por meio do Portal da empresa são desinstalados. Dados de aplicativo da empresa são removidos.|Aplicativos são desinstalados. Chaves de sideload são removidas.<br>Na versão 1703 do Windows 10 (Atualização para Criadores) e em versões posteriores, os aplicativos do Office 365 ProPlus não são removidos.|
|Configurações|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|As configurações definidas pela política do Intune não serão mais impostas. Os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|Não há suporte.|Removidos.|
|Configurações do perfil de certificado|Certificados são removidos e revogados.|Certificados são removidos e revogados.|Não há suporte.|Certificados são removidos e revogados.|
|Email|Remove o email habilitado para EFS. Isso inclui emails e anexos no aplicativo Mail para Windows.|Não há suporte.|Os perfis de email provisionados por meio do Intune são removidos. O email armazenado em cache no dispositivo é excluído.|Remove o email habilitado para EFS. Isso inclui emails e anexos no aplicativo Mail para Windows. Remove contas de email que foram provisionadas pelo Intune.|
|Cancelamento de ingresso no Azure AD|Não.|Não.|O registro do Azure AD é removido.|Não aplicável. No Windows 10, não é possível remover dados da empresa para dispositivos ingressados no Azure AD.|

### <a name="remove-company-data"></a>Remover os dados da empresa

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Dispositivos**, selecione **Todos os dispositivos**.
4. Selecione o nome do dispositivo do qual você deseja remover os dados da empresa.
5. No painel que mostra o nome do dispositivo, selecione **Remover dados da empresa**. Para confirmar, selecione **Sim**.

Se o dispositivo estiver ligado e conectado, a ação **Remover dados da empresa** se propagará entre todos os tipos de dispositivo em menos de 15 minutos.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Excluir dispositivos do portal do Azure Active Directory

Talvez seja necessário excluir dispositivos do Azure AD devido a problemas de comunicação ou a dispositivos ausentes. É possível usar a ação **Excluir** para remover registros de dispositivo do Portal do Azure para dispositivos que você sabe que estão inacessíveis e provavelmente não se comunicarão com o Azure novamente. A ação **Excluir** não remove um dispositivo do gerenciamento.

1.  Entre no [Azure Active Directory no Portal do Azure](http://aka.ms/accessaad) usando suas credenciais de administrador. Também é possível entrar no [Portal do Office 365](https://portal.office.com). No menu, selecione **Centros de administração** > **Azure AD**.
2.  Se não tiver uma, crie uma assinatura do Azure. Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (selecione link de assinatura **Registrar seu Azure Active Directory gratuito** ).
3.  Selecione **Azure Active Directory** e, em seguida, selecione sua organização.
4.  Selecione a guia **Usuários** .
5. Selecione o usuário associado ao dispositivo que você deseja excluir.
6.  Selecione **Dispositivos**.
7.  Remova os dispositivos conforme apropriado. Por exemplo, você pode remover dispositivos que não estão mais em uso ou dispositivos que têm definições imprecisas.
