---
title: "Usar redefinição de fábrica ou remoção dos dados da empresa em dispositivos que usam o Microsoft Intune"
titlesuffix: 
description: "Saiba como remover os dados da empresa de um dispositivo ou redefini-lo para as configurações de fábrica."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 62404f6ffede7a7f3f7150da1fde289f2ba9e64f
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Remova dispositivos por meio da redefinição de fábrica ou remova os dados da empresa

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

É possível remover dispositivos do Intune que não são mais necessários, que estão sendo realocados ou estão ausentes. Para isso, emita um comando **remover os dados da empresa** ou **redefinição de fábrica**. Os usuários também podem emitir um comando remoto do Portal da Empresa do Intune para dispositivos de propriedade pessoal registrados no Intune.

> [!NOTE]
> Antes de remover um usuário do Azure Active Directory, emita um comando de **Redefinição de fábrica** ou **Remover os dados da empresa** para todos os dispositivos associados a esse usuário. Caso os usuários com dispositivos gerenciados sejam removidos do Azure Active Directory, o Intune não poderá emitir os comandos de redefinição de fábrica ou remoção dos dados da empresa para esses dispositivos.

## <a name="factory-reset"></a>Redefinição de fábrica

A **Redefinição de fábrica** restaura um dispositivo para suas configurações padrão de fábrica, removendo todas as configurações e os dados da empresa e do usuário. O dispositivo é removido do gerenciamento do Intune. A redefinição de fábrica é útil para redefinir um dispositivo antes de cedê-lo a um novo usuário ou quando o dispositivo é roubado ou perdido. Tenha cuidado ao selecionar a redefinição de fábrica. Os dados no dispositivo não podem ser recuperados.

### <a name="to-factory-reset-a-device"></a>Restaurar configurações de fábrica do dispositivo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
4. Escolha o nome do dispositivo que você deseja redefinir para as configurações de fábrica.
5. Na folha que mostra o nome do dispositivo, escolha **Redefinição de fábrica**.
6. Para o Windows 10 versão 1709 ou superior, há uma opção adicional para "Manter o estado do registro e a conta de usuário". 
    
    |Mantido por meio de uma redefinição de fábrica|Não mantido|
    | -------------|------------|
    |Contas do usuário associadas ao dispositivo|Arquivos do usuário|
    |Estado do computador \(ingresso no domínio, ingressado no Azure Active Directory)| Aplicativos instalados pelo usuário \(aplicativos do Win32 e da loja)|
    |Registro do MDM|Configurações do dispositivo não padrão|
    |Aplicativos instalados pelo OEM \(aplicativos do Win32 e da loja)||
    |Perfil de usuário||
    |Dados do usuário de fora do perfil do usuário||
    |Logon automático do usuário|| 
    
         
7. Escolha **Sim** para confirmar a redefinição de fábrica.

Se o dispositivo estiver ligado e conectado, um comando de redefinição de fábrica levará menos de 15 minutos para ser propagado para todos os tipos de dispositivo.

## <a name="remove-company-data"></a>Remover os dados da empresa

O comando **remover os dados da empresa** remove os dados de aplicativos gerenciados (quando for o caso), configurações e perfis de email atribuídos pelo Intune. O comando remover os dados da empresa deixa os dados pessoais do usuário no dispositivo. O dispositivo é removido do gerenciamento do Intune. As tabelas a seguir descrevem quais dados são removidos e o efeito nos dados que permaneceram no dispositivo após a remoção dos dados da empresa.

### <a name="ios"></a>iOS

|Tipo de dados|iOS|
|-------------|-------|
|Aplicativos da empresa e dados associados instalados pelo Intune|Aplicativos são desinstalados. Dados de aplicativo da empresa são removidos.<br /><br />Os dados dos aplicativos da Microsoft que usam o gerenciamento de aplicativos móveis são removidos. O aplicativo não é removido.|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Certificados são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Email|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|
|Outlook|Mensagens de email recebidas pelo aplicativo Microsoft Outlook para iOS são removidas.|
|Sair do Azure Active Directory (AAD)|O registro no Azure AD é removido.|
|Contacts | Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.  Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser removidos. <br /> <br />Atualmente, há suporte somente para aplicativo do Outlook.

### <a name="android"></a>Android

|Tipo de dados|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Links da Web|Removidos.|Removidos.|
|Aplicativos Google Play não gerenciados|Aplicativos e dados permanecem instalados.|Aplicativos e dados permanecem instalados.|
|Aplicativos de linha de negócios não gerenciados|Aplicativos e dados permanecem instalados.|Os aplicativos são desinstalados e dados locais do aplicativo são removidos como resultado. Nenhum dado fora do aplicativo (por exemplo, em um cartão SD) é removido.|
|Aplicativos Google Play gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados, mas não são removidos.|
|Aplicativos de linha de negócios gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|
|Configurações do perfil de certificado|Certificados revogados, mas não removidos.|Certificados removidos e revogados.|
|Agente de gerenciamento|O privilégio de administrador do dispositivo é revogado.|O privilégio de administrador do dispositivo é revogado.|
|Email|N/D (não há suporte para perfis de email em dispositivos Android)|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|
|Outlook|Emails recebidos pelo aplicativo do Microsoft Outlook para Android serão removidos, mas somente se o Outlook estiver protegido pelas políticas MAM. Caso contrário, o Outlook não será apagado ao cancelar o registro.|Emails recebidos pelo aplicativo do Microsoft Outlook para Android serão removidos, mas somente se o Outlook estiver protegido pelas políticas MAM. Caso contrário, o Outlook não será apagado ao cancelar o registro.|
|Sair do Azure Active Directory (AAD)|Registro do Azure AD removido.|Registro do Azure AD removido.|
|Contacts | Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.  Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser removidos. <br /> <br />Atualmente, há suporte somente para aplicativo do Outlook.|Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.  Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser removidos. <br /> <br />Atualmente, há suporte somente para aplicativo do Outlook.

### <a name="android-for-work"></a>Android for Work

Executar a remoção dos dados da empresa em um dispositivo Android for Work remove todos os dados, aplicativos e as configurações no perfil de trabalho nesse dispositivo. Isso desativa o dispositivo de gerenciamento com o Intune. Não há suporte para a redefinição de fábrica no Android for Work.


### <a name="macos"></a>macOS

|Tipo de dados|macOS|
|-------------|-------|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Os certificados que foram implantados por meio do MDM são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Outlook|Se o acesso condicional estiver habilitado, nenhum novo email será recebido pelo dispositivo.|
|Sair do Azure Active Directory (AAD)|O registro no Azure AD é removido.|

### <a name="windows"></a>Windows

|Tipo de dados|Windows 8.1 (MDM) e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplicativos da empresa e dados associados instalados pelo Intune|Arquivos protegidos por EFS terão sua chave revogada e o usuário não conseguirá abrir os arquivos.|Não removerão aplicativos da empresa.|Aplicativos instalados originalmente por meio do portal da empresa são desinstalados. Dados de aplicativo da empresa são removidos.|Os aplicativos são desinstalados e a chaves de sideload são removidas.<br>Na versão 1703 do Windows 10 (Atualização para Criadores) e em versões posteriores, os aplicativos do Office 365 ProPlus não serão removidos.|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|Não há suporte.|Removidos.|
|Configurações do perfil de certificado|Certificados removidos e revogados.|Certificados removidos e revogados.|Não há suporte.|Certificados removidos e revogados.|
|Email|Remove o email habilitado para EFS, que inclui o aplicativo Mail para emails e anexos do Windows.|Não há suporte.|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|Remove o email habilitado para EFS, que inclui o aplicativo Mail para emails e anexos do Windows. Remove contas de email que foram provisionadas pelo Intune.|
|Sair do Azure Active Directory (AAD)|Não.|Não.|Registro do Azure AD removido.|Não aplicável. O Windows 10 não oferece suporte à remoção de dados da empresa em dispositivos associados ao Azure Active Directory.|

### <a name="to-remove-company-data"></a>Remover os dados da empresa

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
4. Escolha o nome do dispositivo do qual você deseja remover os dados da empresa.
5. Na folha que mostra o nome do dispositivo, escolha **Remover os dados da empresa** e, em seguida, escolha **Sim** para confirmar a remoção.

Se o dispositivo estiver ligado e conectado, um comando de remoção de dados levará menos de 15 minutos para ser propagado para todos os tipos de dispositivo.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Excluir dispositivos do portal do Azure Active Directory

Por conta de problemas de comunicação ou dispositivos ausentes, pode ser necessário excluir dispositivos do Azure Active Directory (AAD). O comando de exclusão não remove um dispositivo do gerenciamento, mas é possível usar **Excluir** para remover registros de dispositivo do Portal do Azure que você sabe que estão inacessíveis e provavelmente não se comunicarão com o Azure novamente.

1.  Entre no [Azure Active Directory no portal do Azure](http://aka.ms/accessaad) com suas credenciais de administrador. Também é possível entrar no [Portal do Office 365](https://portal.office.com) e, em seguida, escolher **Centros de administração** &gt; **Azure AD** usando o link no lado esquerdo da página.
3.  Se não tiver uma, crie uma assinatura do Azure. Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (clique no link de assinatura **Register your free Azure Active Directory** [Registrar seu Azure Active Directory gratuito]).
4.  Selecione **Azure Active Directory** e, em seguida, selecione sua organização.
5.  Selecione a guia **Usuários** .
6.  Selecione o usuário cujos dispositivos que deseja excluir.
7.  Escolha **Dispositivos**.
8.  Remova os dispositivos conforme apropriado, como aqueles que não estão mais em uso, ou aqueles que têm definições imprecisas.
