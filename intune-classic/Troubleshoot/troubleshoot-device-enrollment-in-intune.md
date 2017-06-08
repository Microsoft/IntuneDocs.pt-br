---
title: Solucionar problemas de registro do dispositivo | Microsoft Docs
description: "Sugestões para solução de problemas de registro de dispositivo."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e72051f9318d24ed36fc39ea6645041f0a150a40
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="troubleshoot-device-enrollment-in-intune"></a>Solução de problemas de registro de dispositivo no Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico fornece sugestões para solução de problemas de registro do dispositivo. Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.


## <a name="initial-troubleshooting-steps"></a>Etapas para solução de problemas iniciais

Antes de iniciar a solução de problemas, verifique se você configurou o Intune corretamente para habilitar o registro. Você pode ler sobre os requisitos de configuração em:

-    [Prepare-se registrar dispositivos no Microsoft Intune](/intune-classic/deploy-use/prerequisites-for-enrollment)
-    [Configurar gerenciamento de dispositivos iOS e Mac](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
-    [Configurar o gerenciamento de dispositivo Windows](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-    [Configurar o gerenciamento de dispositivo do Android](/intune-classic/deploy-use/set-up-android-management-with-microsoft-intune) - Não há etapas adicionais necessárias
-    [Configurar o gerenciamento de dispositivo do Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

Seus usuários de dispositivo gerenciado podem coletar logs de registro e diagnóstico para você examinar. As instruções para o usuário coletar logs são fornecidas em:

- [Enviar erros de registro do Android ao seu administrador de TI](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Enviar erros do iOS para o administrador de TI](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Problemas gerais de registro
Esses problemas podem ocorrer em todas as plataformas de dispositivo.

### <a name="device-cap-reached"></a>Limite do dispositivo associado
**Problema:** um usuário recebe um erro no seu dispositivo durante o registro, como um erro **Portal da empresa temporariamente indisponível** em um dispositivo iOS, e o DMPdownloader.log no Configuration Manager contém o erro **DeviceCapReached**.

**Resolução:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Verifique o número de dispositivos registrados e permitidos

1.  Valide no portal de administração do Intune que o usuário tem não mais do que o máximo permitido de 15 dispositivos atribuídos.

2.  Em **Administrador** > **Gerenciamento de Dispositivo Móvel** > **Regras de Registro** no console do administrador do Intune, verifique se o Limite de registro do dispositivo está definido como 15.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Os administradores podem excluir dispositivos no portal do Azure Active Directory.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Para excluir dispositivos no portal do Active Directory do Azure

1.  Navegue até [http://aka.ms/accessaad](http://aka.ms/accessaad) ou clique em **Administrador** &gt; **Azure AD** de [https://portal.office.com](https://portal.office.com).

2.  Faça logon com sua ID da organização usando o link no lado esquerdo da página.

3.  Se você não tiver uma, crie uma assinatura do Azure escolhendo o link de assinatura **Registre a sua assinatura gratuita do Azure Active Directory**. Se você tiver uma conta paga, não precisará usar um cartão de crédito ou pagamento.

4.  Selecione **Active Directory** e selecione sua organização.

5.  Selecione a guia **Usuários** .

6.  Selecione o usuário cujos dispositivos que deseja excluir.

7.  Escolha **Dispositivos**.

8.  Remova os dispositivos conforme apropriado, como aqueles que não estão mais em uso, ou aqueles que têm definições imprecisas.

> [!NOTE]

> Você pode evitar o limite de registro de dispositivo usando a conta do Gerenciador de Registro do Dispositivo, conforme descrito em [Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivos no Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
>
> Uma conta de usuário que é adicionada à conta de Gerenciadores de Registro de Dispositivos não conseguirá concluir o registro quando a política de acesso condicional for aplicada a esse logon de usuário específico.

### <a name="company-portal-temporarily-unavailable"></a>Portal da empresa temporariamente indisponível
**Problema:** os usuários recebem um erro de **Portal da Empresa temporariamente indisponível** no dispositivo.

**Resolução:**

1.  Remova o aplicativo de Portal da Empresa do Intune do dispositivo.

2.  No dispositivo, abra o navegador, navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), e tente algum logon de usuário.

3.  Se o usuário não conseguir efetuar logon, faça-o tentar outra rede.

4.  Se isso falhar, confirme que as credenciais do usuário foram sincronizadas corretamente com o Active Directory do Azure.

5.  Se o usuário fizer logon com êxito, um dispositivo iOS solicitará que você instale o aplicativo de Portal da Empresa do Intune e o registre. Em um dispositivo Android, você precisará instalar manualmente o aplicativo de Portal da Empresa do Intune e depois disso você poderá tentar novamente o registro.

### <a name="mdm-authority-not-defined"></a>Autoridade MDM não definida
**Problema:** um usuário recebe um erro de **Autoridade MDM não definida**.

**Resolução:**

1.  Verifique se a Autoridade MDM foi definida corretamente para o tipo de serviço do Intune que está usando (isto é, Intune, Office 365 ou System Center Configuration Manager com Intune). Para o Intune, a Autoridade MDM é definida em **Administrador** &gt; **Gerenciamento de Dispositivo Móvel**. Para o Configuration Manager com o Intune, ela é definida quando você configura o conector do Intune e, no Office 365, ela é uma configuração de **Dispositivos Móveis**.

    > [!NOTE]
    > Após definir a Autoridade MDM, você pode alterá-la apenas entrando em contato com o Suporte, conforme descrito em [Como obter suporte para o Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

2.  Verifique se as credenciais do usuário foram sincronizadas corretamente com o Azure Active Directory, verificando se seu UPN corresponde às informações do Active Directory no Portal do Office 365.
    Se o UPN não coincidir com as informações do Active Directory:

    1.  Desligue o DirSync no servidor local.

    2.  Exclua o usuário incompatível da lista de usuários do **Portal de Contas do Intune** .

    3.  Aguarde cerca de uma hora para permitir que o serviço do Azure remova os dados incorretos.

    4.  Ative o DirSync novamente e verifique se agora o usuário está sincronizado corretamente.

3.  Em um cenário em que você estiver usando o System Center Configuration Manager com o Intune, verifique se o usuário tem uma ID de usuário de nuvem válida:

    1.  Abra o SQL Management Studio.

    2.  Conecte-se ao banco de dados apropriado.

    3.  Abra a pasta de bancos de dados e localize e abra a pasta **CM_DBName**, em que DBName é o nome do banco de dados do cliente.

    4.  Na parte superior, escolha **Nova Consulta** e execute as seguintes consultas:

        -   Para ver todos os usuários: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Para ver Usuários Específicos, use a seguinte consulta, em que %testuser1% representa username@domain.com para o usuário que você deseja pesquisar: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Depois de gravar a consulta, escolha **!Execute**.
        Após os resultados serem retornados, procure a ID do clouduser.  Se nenhuma ID for encontrada, o usuário não está licenciado para usar o Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Não é possível criar a política ou registrar os dispositivos se o nome da empresa contiver caracteres especiais
**Problema:** não é possível criar a política ou registrar os dispositivos.

**Resolução:** no [Centro de administração do Office 365](https://portal.office.com/), remova os caracteres especiais do nome da empresa e salve as informações da empresa.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Não é possível entrar ou registrar dispositivos quando você tiver vários domínios verificados
**Problema:** quando você adiciona um segundo domínio verificado ao seu ADFS, os usuários com o sufixo de nome UPN do segundo domínio não poderão fazer logon nos portais ou registrar dispositivos.


**Resolução:** os clientes do Microsoft Office 365 que usam o SSO (logon único) por meio do AD FS 2.0 e tiverem vários domínios de nível superior para sufixos UPN de usuários em sua organização (por exemplo, @contoso.com ou @fabrikam.com) deverão implantar uma instância separada do Serviço de Federação AD FS 2.0 em cada sufixo. Agora, há um [pacote cumulativo de atualizações para o AD FS 2.0](http://support.microsoft.com/kb/2607496) que funciona em conjunto com o comutador **SupportMultipleDomain** para habilitar o servidor AD FS, para dar suporte a esse cenário sem a necessidade de exigir servidores AD FS 2.0 adicionais. Confira [este blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) para obter mais informações.


## <a name="android-issues"></a>Problemas de Android
### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Os dispositivos apresentaram falha no check-in com o serviço do Intune e são exibidos como "Não íntegro" no console de administração do Intune
**Problema:** alguns dispositivos Samsung que estão executando versões do Android 4.4 e 5.x podem interromper a verificação com o serviço do Intune. Se os dispositivos não fizerem o check-in:

- Eles não poderão receber políticas, aplicativos e comandos remotos do serviço do Intune.
- Eles mostram um Estado de Gerenciamento **não íntegro** no console do administrador.
- Os usuários que são protegidos por políticas de acesso condicional podem perder o acesso aos recursos corporativos.

A Samsung confirmou que o software do Gerenciador Inteligente Samsung, que é fornecido em certos dispositivos Samsung, pode desativar o Portal da Empresa do Intune e seus componentes. Quando o Portal da Empresa está em um estado desativado, ele não pode ser executado em segundo plano e, portanto, não pode contatar o serviço do Intune.

**Resolução nº1:**

Avise os usuários para iniciar o aplicativo do Portal da Empresa manualmente. Depois que o aplicativo for reiniciado, o dispositivo faz o check-in no serviço do Intune.

> [!IMPORTANT]
> Abrir o aplicativo do Portal da Empresa manualmente é uma solução temporária, pois o Gerenciador Inteligente Samsung pode desativar o aplicativo do Portal da Empresa novamente.

**Resolução nº2:**

Peça aos usuários que tentem atualizar para o Android 6.0. O problema de desativação não ocorre em dispositivos Android 6.0. Para verificar se uma atualização está disponível, os usuários podem ir até **Configurações** > **Sobre dispositivo** > **Baixar atualizações manualmente** e siga as instruções no dispositivo.

**Resolução nº3:**

Se a Resolução nº2 não funcionar, oriente os usuários a seguir estas etapas para fazer com que o Gerenciador Inteligente exclua o aplicativo do Portal da Empresa:

1. Inicie o aplicativo Gerenciador Inteligente no dispositivo.

  ![Selecione o ícone do Gerenciador Inteligente no dispositivo](./media/smart-manager-app-icon.png)

2. Escolha o bloco **Bateria**.

  ![Selecione o bloco Bateria](./media/smart-manager-battery-tile.png)

3. Em **Economia de energia do aplicativo** ou em **Otimização do aplicativo**, selecione **Detalhes**.

  ![Selecione Detalhes em Economia de energia do aplicativo ou em Otimização de aplicativo](./media/smart-manager-app-power-saving-detail.png)

4. Escolha **Portal da Empresa** na lista de aplicativos.

  ![Selecione o Portal da Empresa na lista de aplicativos](./media/smart-manager-company-portal.png)

5. Escolha **Desativado**.

  ![Selecione Desativado na caixa de diálogo Otimização de aplicativo](./media/smart-manager-app-optimization-turned-off.png)

6. Em **Economia de energia do aplicativo** ou em **Otimização do aplicativo**, confirme se o Portal da Empresa está desativado.

  ![Verifique se o Portal da Empresa está desativado](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Falha na instalação do perfil
**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo Android.

**Resolução:**

1.  Confirme que foi atribuída ao usuário uma licença apropriada para a versão do serviço do Intune que você está usando.

2.  Confirme se o dispositivo já não está registrado com outro provedor MDM ou se ele ainda não tem um perfil de gerenciamento instalado.

3.  Confirme se o Chrome para Android é o navegador padrão e se os cookies estão habilitados.

### <a name="android-certificate-issues"></a>Problemas de certificado do Android

**Problema**: o usuário recebe a seguinte mensagem em seu dispositivo: *Não é possível se conectar porque o dispositivo não tem um certificado necessário.*

**Resolução 1**:

Solicite aos usuários que sigam as instruções em [Falta ao dispositivo um certificado necessário](/intune-user-help/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Se o erro persistir após os usuários seguirem essas instruções, tente a Resolução 2.

**Resolução 2**:

Se os usuários ainda virem o erro de ausência de certificado após inserir suas credenciais corporativas e serem redirecionados à experiência de logon federado, um certificado intermediário pode estar faltando no seu servidor de Serviços de Federação do Active Directory (AD FS).

O erro de certificado ocorre porque dispositivos Android exigem que certificados intermediários sejam incluídos em uma [saudação do servidor SSL](https://technet.microsoft.com/library/cc783349.aspx), mas, no momento, um servidor padrão do AD FS ou a instalação do servidor proxy do AD FS envia apenas o certificado SSL do serviço de AD FS na saudação de resposta do servidor SSL à uma saudação do cliente SSL.

Para corrigir o problema, importe os certificados para os Certificados Pessoais do Computador no servidor do AD FS ou proxies da seguinte maneira:

1.    Nos servidores AD FS e proxy, inicie o console de Gerenciamento de Certificados do computador local clicando com o botão direito do mouse em **Iniciar**, escolhendo **Executar** e digitando **certlm.msc**.
2.    Expanda **Pessoal** e selecione **Certificados**.
3.    Localize o certificado da comunicação de serviço do AD FS (certificado assinado publicamente) e clique duas vezes para exibir suas propriedades.
4.    Selecione a guia **Caminho de Certificação** para ver o(s) certificado(s) pai do certificado.
5.    Em cada certificado pai, selecione **Exibir Certificado**.
6.    Selecione a guia **Detalhes** e escolha **Copiar para arquivo...**.
7.    Siga as solicitações do assistente para exportar ou salvar a chave pública do certificado para o local de arquivo desejado.
8.    Importe os certificados pai que foram exportados na Etapa 3 para Computador Local\Pessoal\Certificados clicando com o botão direito do mouse em **Certificados**, selecionado **Todas Tarefas** > **Importar** e seguindo as solicitações do assistente para importar o(s) certificado(s).
9.    Reinicie os servidores AD FS.
10.    Repita as etapas acima em todos os servidores AD FS e proxy.
Agora, o usuário deve ser capaz de entrar no Portal da Empresa no dispositivo Android.

**Para validar a instalação correta do certificado**:

As etapas a seguir descrevem apenas um dos vários métodos e ferramentas que você pode usar para validar a instalação correta do certificado.

1. Vá para a [ferramenta gratuita do Digicert](ttps://www.digicert.com/help/).
2. Insira o nome de domínio totalmente qualificado do servidor AD FS (por exemplo, sts.contoso.com) e selecione **VERIFICAR SERVIDOR**.

Se o certificado do servidor estiver instalado corretamente, você verá todas as marcas de seleção nos resultados. Se o problema acima existir, você ver um “X” vermelho nas seções “Correspondências de Nome de Certificado” e “Certificado SSL instalado corretamente” do relatório.


## <a name="ios-issues"></a>Problemas de iOS

### <a name="ios-enrollment-errors"></a>Erros de registro do iOS
A tabela a seguir lista os erros que os usuários finais podem encontrar durante o registro de dispositivos de iOS no Intune.

|Mensagem de erro|Problema|Resolução|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Nenhuma política de registro localizada|Verifique se todos os pré-requisitos de registro, como o certificado APNs (Apple Push Notification Service), foram configurados e se "iOS como plataforma" está habilitado. Para obter instruções, veja [Configurar gerenciamento de dispositivos iOS e Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Há muitos dispositivos móveis registrados.|Antes de registrar outro dispositivo móvel, o usuário deve remover um de seus dispositivos móveis registrados atualmente no Portal da Empresa. Consulte as instruções para o tipo de dispositivo que você está usando: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios), [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Há um problema com o certificado que permite que o dispositivo móvel se comunique com a rede da empresa.<br /><br />|o APNs (Apple Push Notification Service) fornece um canal para chegar aos dispositivos iOS registrados. Se as etapas para obter um certificado APNS não tiverem sido executadas ou se o certificado APNS estiver vencido, as tentativas de registro falharão e essa mensagem será exibida.<br /><br />Examine as informações sobre como configurar usuários em [Sincronizar o Active Directory e adicionar usuários ao Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) e em [Organizando usuários e dispositivos](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Há um problema com o certificado que permite que o dispositivo móvel se comunique com a rede da empresa.<br /><br />|o APNs (Apple Push Notification Service) fornece um canal para chegar aos dispositivos iOS registrados. Se as etapas para obter um certificado APNS não tiverem sido executadas ou se o certificado APNS estiver vencido, as tentativas de registro falharão e essa mensagem será exibida.<br /><br />Para obter mais informações, examine [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) (Configurar gerenciamento de iOS e Mac com o Microsoft Intune).|
|DeviceTypeNotSupported|O usuário pode ter tentado se registrar usando um dispositivo não iOS. O tipo de dispositivo móvel que você está tentando registrar não tem suporte.<br /><br />Confirme se o dispositivo está executando o iOS versão 8.0 ou posterior.<br /><br />|Verifique se o dispositivo do usuário está executando o iOS versão 8.0 ou posterior.|
|UserLicenseTypeInvalid|O dispositivo não pode se registrado porque a conta de usuário ainda não é membro de um grupo de usuário necessário.<br /><br />|Antes que possam registrar seus dispositivos, os usuários devem ser membros do grupo de usuários correto. Esta mensagem indica que eles têm o tipo de licença errado para a autoridade de gerenciamento de dispositivo móvel designado. Por exemplo, se o Intune tiver sido designado como a autoridade de gerenciamento de dispositivo móvel e eles estiverem usando uma licença do System Center 2012 R2 Configuration Manager, eles receberão esse erro.<br /><br />Examine os itens a seguir para obter mais informações:<br /><br />Examine [Configurar gerenciamento de iOS e Mac com o Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) e as informações sobre como configurar usuários no [Sincronizar o Active Directory e adicionar usuários ao Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) e em [Organizando usuários e dispositivos](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|A autoridade de gerenciamento de dispositivo móvel não foi definida.<br /><br />|A autoridade de gerenciamento de dispositivo móvel não foi designada no Intune.<br /><br />Examine o item nº 1 na seção "Etapa 6: registrar dispositivos móveis e instalar um aplicativo” em [Começar com uma avaliação de 30 dias do Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles
**Problema:** os dispositivos iOS não estão fazendo check-in no serviço do Intune. Os dispositivos devem fazer o check-in no serviço periodicamente para manter o acesso aos recursos corporativos protegidos. Se os dispositivos não fizerem o check-in:

- Eles não poderão receber políticas, aplicativos e comandos remotos do serviço do Intune.
- Eles mostram um Estado de Gerenciamento **não íntegro** no console do administrador.
- Os usuários que são protegidos por políticas de acesso condicional podem perder o acesso aos recursos corporativos.

**Resolução:** compartilhe as seguintes resoluções com seus usuários finais para ajudá-los a recuperar o acesso aos recursos corporativos.

Quando os usuários iniciarem o aplicativo do Portal da Empresa do iOS, ele poderá informar se o dispositivo perdeu contato com o Intune. Se detectar que não há nenhum contato, ele tenta automaticamente a sincronização com o Intune para se reconectar e os usuários verão a notificação embutida **Tentando sincronizar...** .

  ![Notificação Tentando sincronizar](./media/ios_cp_app_trying_to_sync_notification.png)

Se a sincronização for bem-sucedida, você verá uma notificação embutida **Sincronização bem-sucedida** no aplicativo do Portal da Empresa do iOS, indicando que o dispositivo está em um estado íntegro.

  ![Notificação Sincronização bem-sucedida](./media/ios_cp_app_sync_successful_notification.png)

Se a sincronização não for bem-sucedida, os usuários verão uma notificação embutida **Não é possível sincronizar** no aplicativo do Portal da Empresa do iOS.

  ![Não é possível sincronizar a notificação](./media/ios_cp_app_unable_to_sync_notification.png)

Para corrigir o problema, os usuários devem selecionar o botão **Configurar**, que está à direita da notificação **Não é possível sincronizar**. O botão Configurar leva os usuários para a tela de fluxo Configuração do Acesso da Empresa, em que eles podem seguir os prompts para registrar seu dispositivo.

  ![Tela de Configuração de Acesso da Empresa](./media/ios_cp_app_company_access_setup.png)

Depois de registrado, os dispositivos retornam ao estado íntegro e recuperam o acesso aos recursos da empresa.

### <a name="verify-ws-trust-13-is-enabled"></a>Verifique se o WS-Trust 1.3 está habilitado
**Problema** Não é possível registrar dispositivos iOS do DEP (Programa de Registro de Dispositivo)

O registro de dispositivos do Programa de Registro de Dispositivo com afinidade do usuário requer que o ponto de extremidade misto/nome do usuário do WS-Trust 1.3 esteja habilitado para solicitar tokens do usuário. O Active Directory permite esse ponto de extremidade por padrão. Você pode obter uma lista de pontos de extremidade habilitados usando o cmdlet Get-AdfsEndpoint do PowerShell e procurando o ponto de extremidade trust/13/UsernameMixed. Por exemplo:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

Para saber mais, veja a [documentação do Get-AdfsEndpoint](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

Para saber mais, veja as [Práticas recomendadas para proteção dos Serviços de Federação do Active Directory](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs). Se você precisar de mais assistência para determinar se o Nome de Usuário/Misto do WS-Trust 1.3 está habilitado em seu provedor de federação de identidade, entre em contato com o Suporte da Microsoft se você usar o AD FS, ou com o fornecedor de identidade de terceiro.


### <a name="profile-installation-failed"></a>Falha na instalação do perfil
**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo iOS.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Etapas de solução de problemas para falhas na instalação de perfil

1.  Confirme que foi atribuída ao usuário uma licença apropriada para a versão do serviço do Intune que você está usando.

2.  Confirme se o dispositivo já não está registrado com outro provedor MDM ou se ele ainda não tem um perfil de gerenciamento instalado.

3.  Navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) e tente instalar o perfil quando solicitado.

4.  Confirme se o Safari para iOS é o navegador padrão e se os cookies estão habilitados.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Os dispositivos iOS registrados não aparecem no console ao usar o System Center Configuration Manager com o Intune
**Problema:** o usuário registra um dispositivo iOS, mas ele não aparece no console de administração do Configuration Manager. O dispositivo não indica que ele foi registrado. Possíveis causas:

- O Conector do Microsoft Intune, no site do Gerenciador de Configurações, não está se comunicando com o serviço do Intune.
- O componente do Data Discovery Manager ou do Gerenciamento de estado não está processando mensagens no serviço do Intune.
- Você pode ter baixado o certificado MDM de uma conta e o usado em outra conta.


**Resolução:** examine os seguintes arquivos de log para identificar possíveis erros:

- dmpdownloader.log
- ddm.log
- statmgr.log

Em breve, adicionaremos exemplos sobre o que procurar nesses arquivos de log.


## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemas ao usar o System Center Configuration Manager com o Intune
### <a name="mobile-devices-disappear"></a>Dispositivos móveis desaparecem
**Problema:** após registrar com êxito um dispositivo móvel no Configuration Manager, ele desaparece da coleção de dispositivos móveis, mas o dispositivo ainda tem o Perfil de gerenciamento e é listado no Gateway de CSS.

**Resolução:** isso pode ocorrer porque você tem um processo personalizado para remover dispositivos não ingressados no domínio ou porque o usuário desativou o dispositivo da assinatura. Para validar e verificar qual conta de usuário ou processo removeu o dispositivo do console do Configuration Manager, execute as seguintes etapas.

#### <a name="check-how-device-was-removed"></a>Verifique como o dispositivo foi removido

1.  No console de administração do Configuration Manager, selecione **Monitoramento** &gt; **Status do Sistema** &gt; **Consultas de Mensagem de Status**.

2.  Clique com o botão direito do mouse em **Recursos Membros da Coleção Excluídos Manualmente** e selecione **Mostrar Mensagens**.

3.  Selecione uma data/hora apropriada ou as últimas 12 horas.

4.  Localize o dispositivo em questão e examine como o dispositivo foi removido. O exemplo a seguir mostra que a conta SCCMInstall excluiu o dispositivo por meio de um aplicativo desconhecido.

    ![Captura de tela para diagnóstico de exclusão do dispositivo](./media/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Verifique se o Configuration Manager não tem uma tarefa agendada, script ou outro processo que poderia estar limpando automaticamente dispositivos móveis, fora do domínio ou relacionados.




### <a name="other-ios-enrollment-errors"></a>Outros erros de registro do iOS
Uma lista de erros de registro do iOS é fornecida em nossa documentação de usuário do dispositivo em [You see errors while trying to enroll your device in Intune](/intune-user-help/using-your-iOS-or-macOS-device-with-intune) (Erros ao tentar registrar seu dispositivo no Intune).

## <a name="pc--issues"></a>Problemas do computador

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>O computador já está registrado - erro hr 0x8007064c
**Problema:** o registro falha com o erro **O computador já está registrado**. O log de registro mostra o erro **hr 0x8007064c**.

Isso pode ocorrer porque o computador já foi registrado anteriormente ou tem a imagem clonada de um computador que tinha sido registrado. O certificado de conta da conta anterior ainda está presente no computador.



**Resolução:**

1. No menu **Iniciar**, digite **Executar** -> **MMC**.
1. Escolha **Arquivo** > **Adicionar/Remover Snap-ins**.
1. Clique duas vezes em **Certificados**, escolha a **Conta de computador** > **Avançar** e selecione **Computador Local**.
1. Clique duas vezes em **Certificados (computador local)** e escolha **Pessoal/Certificados**.
1. Procure pelo certificado Intune emitido por Sc_Online_Issuing e exclua-o, se estiver presente.
1. Se a chave do Registro a seguir existir, exclua-a: existir: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** e todas as subchaves.
1. Tente registrar novamente.
1. Se o computador ainda não conseguir realizar o registro, procure e exclua essa chave, se existir: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Tente registrar novamente.

    > [!IMPORTANT]
    > Nesta seção, o método ou tarefa contém etapas que descrevem como modificar o Registro. No entanto, problemas graves podem ocorrer se você modificar o Registro incorretamente. Portanto, certifique-se de seguir estas etapas com cuidado. Para maior proteção, faça backup do Registro antes de modificá-lo. Assim, será possível restaurá-lo se houver algum problema.
    > Para obter mais informações sobre como fazer backup e restaurar o Registro, leia [Como fazer backup e restaurar o registro no Windows](https://support.microsoft.com/kb/322756)

## <a name="general-enrollment-error-codes"></a>Códigos de erro geral de registro

|Código do erro|Possível problema|Resoluções sugeridas|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |O relógio no computador cliente não está definido com a hora correta.|Verifique se o relógio e o fuso horário do computador cliente estão definidos para a hora e o fuso horário corretos.|
|0x80240438, 0x80CF0438, 0x80CF402C|Não é possível se conectar ao serviço Intune. Verifique as configurações de proxy do cliente.|Verifique se a configuração de proxy no computador cliente tem suporte pelo Intune e se o computador tem acesso à Internet.|
|0x80240438, 0x80CF0438|As configurações de proxy no Internet Explorer e no Sistema Local não estão definidas.|Não é possível se conectar ao serviço Intune. Verifique as configurações de proxy do cliente, confirme se a configuração de proxy no computador cliente tem suporte no Intune e se o computador cliente tem acesso à Internet.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|O pacote de inscrição está desatualizado.|Baixe e instale o pacote do software cliente atual no espaço de trabalho Administração.|
|0x80043002, 0x80CF3002|A conta está no modo de manutenção.|Não é possível inscrever novos computadores clientes quando a conta está no modo de manutenção. Para exibir suas configurações de conta, entre na sua conta.|
|0x80043003, 0x80CF3003|A conta está excluída.|Verifique se sua conta e assinatura do Intune continuam ativas. Para exibir suas configurações de conta, entre na sua conta.|
|0x80043005, 0x80CF3005|O computador cliente foi desativado.|Aguarde algumas horas, remova do computador as versões mais antigas do software cliente e tente instalar novamente o software cliente.|
|0x80043006, 0x80CF3006|O número máximo de estações permitidas para a conta foi atingido.|Sua organização deve adquirir estações adicionais para poder inscrever mais computadores clientes no serviço.|
|0x80043007, 0x80CF3007|Não foi possível localizar o arquivo de certificado na mesma pasta do programa de instalação.|Extrai todos os arquivos antes de iniciar a instalação. Não renomeie ou relocalize os arquivos extraídos: todos os arquivos devem existir na mesma pasta ou a instalação falhará.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|O software não pode ser instalado porque uma reinicialização do computador cliente está pendente.|Reinicie o computador e tente instalar novamente o software cliente.|
|0x80070032|Um ou mais pré-requisitos de instalação do software cliente não foram encontrados no computador cliente.|Verifique se todas as atualizações necessárias estão instaladas no computador cliente e tente instalar novamente o software cliente.|
|0x80043008, 0x80CF3008|Falha ao iniciar o serviço de atualizações do Microsoft Online Management.|Entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).|
|0x80043009, 0x80CF3009|O computador cliente já está inscrito no serviço.|Você deve retirar o computador cliente antes de ser possível registrá-lo novamente no serviço.|
|0x8004300B, 0x80CF300B|O pacote de instalação do software cliente não pode ser executado porque a versão do Windows que está em execução no cliente não é suportada.|O Intune não dá suporte à versão do Windows em execução no computador cliente.|
|0xAB2|O Windows Installer não pode acessar o tempo de uma ação personalizada de execução do VBScript.|Este erro é causado por uma ação personalizada que se baseia em bibliotecas de vínculo dinâmico (DLLs). Ao solucionar problemas de DLL, pode ser necessário usar as ferramentas descritas em [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Suporte da Microsoft KB198038: Ferramentas úteis para problemas de implantação e pacote).|
|0x80cf0440|A conexão com o ponto de extremidade do serviço foi encerrada.|A conta de avaliação ou paga está suspensa. Criar uma nova conta de avaliação ou paga e registrar novamente.|




### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).
