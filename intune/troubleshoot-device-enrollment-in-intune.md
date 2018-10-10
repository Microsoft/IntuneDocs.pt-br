---
title: Solucionar problemas de registro de dispositivo
description: Sugestões para solução de problemas de registro de dispositivo.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2a4b4a4b2b0df706504e76b418c5b87eb66b1111
ms.sourcegitcommit: 23997b701365bb514347d75edc2357eff1f1443f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47237656"
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Solução de problemas de registro de dispositivo no Intune

Este artigo fornece sugestões para solução de problemas de registro do dispositivo. Se essas informações não resolverem seu problema, consulte [Como obter suporte para o Microsoft Intune](get-support.md) para encontrar outras formas de obter ajuda.


## <a name="initial-troubleshooting-steps"></a>Etapas para solução de problemas iniciais

Antes de iniciar a solução de problemas, verifique se você configurou o Intune corretamente para habilitar o registro. Você pode ler sobre os requisitos de configuração em:

-   [Prepare-se registrar dispositivos no Microsoft Intune](setup-steps.md)
-   [Configurar gerenciamento de dispositivos iOS e Mac](ios-enroll.md)
-   [Configurar o gerenciamento de dispositivo Windows](windows-enroll.md)
-   [Configurar o gerenciamento de dispositivo do Android](android-enroll.md) - Não há etapas adicionais necessárias

Você também pode verificar se a data e hora no dispositivo do usuário estão definidas corretamente:

1. Reinicie o dispositivo.
2. Verifique se a data e a hora estão definidas próximas aos padrões GMT (+ ou - 12 horas) em relação ao fuso horário do usuário final.
3. Desinstale e reinstale o Portal da Empresa do Intune (se for aplicável).

Seus usuários de dispositivo gerenciado podem coletar logs de registro e diagnóstico para você examinar. As instruções para o usuário coletar logs são fornecidas em:

- [Enviar erros de registro do Android ao seu administrador de TI](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Enviar erros do iOS para o administrador de TI](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Problemas gerais de registro
Esses problemas podem ocorrer em todas as plataformas de dispositivo.

### <a name="device-cap-reached"></a>Limite do dispositivo associado
**Problema:** um usuário recebe um erro durante o registro (como **Portal da Empresa temporariamente indisponível**) e o DMPdownloader.log no Configuration Manager contém o erro **DeviceCapReached**.

**Resolução:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Verifique o número de dispositivos registrados e permitidos

Verifique se o usuário não está atribuído a mais dispositivos que o máximo permitido seguindo estas etapas:

1. No Intune, escolha **Registro do dispositivo** > **Restrições de registro** > **Restrições de limite de dispositivo**. Observe o valor da coluna **Limite de dispositivo**.

2. No Intune, escolha **Usuários** > **Todos os usuários** > selecione o usuário > **Dispositivos**. Observe o número total de dispositivos.

3. Se o número de dispositivos registrados do usuário já é igual à restrição de limite de dispositivo desse usuário, não é possível registrar mais nenhum até que:
    - [Os dispositivos existentes sejam removidos](devices-wipe.md), ou
    - Você aumente o limite de dispositivos [definindo restrições de dispositivo](enrollment-restrictions-set.md#set-device-limit-restrictions).

Para evitar atingir os limites de dispositivos, não deixe de remover os registros de dispositivo obsoletos.

> [!NOTE]
> 
> Você pode evitar o limite de registro de dispositivo usando a conta do Gerenciador de Registro do Dispositivo, conforme descrito em [Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivos no Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
> 
> Uma conta de usuário que é adicionada à conta de Gerenciadores de Registro de Dispositivos não conseguirá concluir o registro quando a política de acesso condicional for aplicada a esse logon de usuário específico.

### <a name="company-portal-temporarily-unavailable"></a>Portal da empresa temporariamente indisponível
**Problema:** os usuários recebem um erro de **Portal da Empresa temporariamente indisponível** no dispositivo.

**Resolução:**

1.  Remova o aplicativo de Portal da Empresa do Intune do dispositivo.

2.  No dispositivo, abra o navegador, navegue para [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) e tente fazer logon com o usuário.

3.  Se o usuário não conseguir entrar, ele deve tentar de outra rede.

4.  Se isso falhar, confirme que as credenciais do usuário foram sincronizadas corretamente com o Active Directory do Azure.

5.  Se o usuário fizer logon com êxito, um dispositivo iOS solicitará que você instale o aplicativo de Portal da Empresa do Intune e o registre. Em um dispositivo Android, será necessário instalar manualmente o aplicativo do Portal da Empresa do Intune, quando então será possível tentar registrar novamente.

### <a name="mdm-authority-not-defined"></a>Autoridade MDM não definida
**Problema:** um usuário recebe um erro de **Autoridade MDM não definida**.

**Resolução:**

1.  Verifique se a autoridade de MDM foi [definida adequadamente](mdm-authority-set.md).
    
2.  Confirme se as credenciais do usuário foram sincronizadas corretamente com o Azure Active Directory. Você pode confirmar se o UPN do usuário corresponde às informações do Active Directory no portal do Office 365.
    Se o UPN não corresponder às informações do Active Directory:

    1.  Desligue o DirSync no servidor local.

    2.  Exclua o usuário incompatível da lista de usuários do **Portal de Contas do Intune** .

    3.  Aguarde cerca de uma hora para permitir que o serviço do Azure remova os dados incorretos.

    4.  Ative o DirSync novamente e verifique se agora o usuário está sincronizado corretamente.

3.  Em um cenário em que você está usando o System Center Configuration Manager com o Intune, confirme se o usuário tem uma ID de usuário de nuvem válida:

    1.  Abra o SQL Management Studio.

    2.  Conecte-se ao banco de dados apropriado.

    3.  Abra a pasta de bancos de dados e localize e abra a pasta **CM_DBName**, em que DBName é o nome do banco de dados do cliente.

    4.  Na parte superior, escolha **Nova Consulta** e execute as seguintes consultas:

        -   Para ver todos os usuários: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Para ver Usuários Específicos, use a seguinte consulta, em que %testuser1% é um espaço reservado para username@domain.com para o usuário que você deseja pesquisar: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Depois de escrever a consulta, escolha **!Executar**.
        Após os resultados serem retornados, procure a ID do clouduser.  Se nenhuma ID for encontrada, o usuário não está licenciado para usar o Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Não é possível criar a política ou registrar os dispositivos se o nome da empresa contiver caracteres especiais
**Problema:** não é possível criar a política ou registrar os dispositivos.

**Resolução:** no [Centro de administração do Office 365](https://portal.office.com/), remova os caracteres especiais do nome da empresa e salve as informações da empresa.

### <a name="unable-to-sign-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Não é possível entrar ou registrar dispositivos quando você tem vários domínios verificados
**Problema:** esse problema pode ocorrer ao adicionar um segundo domínio verificado ao seu ADFS. Usuários com o sufixo de nome UPN do segundo domínio não poderão fazer logon nos portais ou registrar dispositivos.


<strong>Resolução:</strong> os clientes do Microsoft Office 365 precisarão implantar uma instância separada do Serviço de Federação AD FS 2.0 para cada sufixo se eles:
- usarem SSO (logon único) por meio do AD FS 2.0, e
- tiverem vários domínios de nível superior para sufixos UPN de usuários na sua organização (por exemplo, @contoso.com ou @fabrikam.com).


Um [rollup para o AD FS 2.0](http://support.microsoft.com/kb/2607496) funciona junto com o comutador <strong>SupportMultipleDomain</strong> para habilitar o servidor AD FS para ser compatível com esse cenário sem precisar exigir servidores AD FS 2.0 adicionais. Para obter mais informações, consulte [este blog](https://blogs.technet.microsoft.uucom/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/).


## <a name="android-issues"></a>Problemas de Android

### <a name="android-enrollment-errors"></a>Erros de registro do Android

A tabela a seguir lista os erros que os usuários finais podem encontrar durante o registro de dispositivos Android no Intune.

|Mensagem de erro|Problema|Resolução|
|---|---|---|
|**O administrador de TI precisa atribuir uma licença para o acesso**<br>Seu administrador de TI não concedeu a você o acesso para usar este aplicativo. Obtenha ajuda do seu administrador de TI ou tente novamente mais tarde.|Não é possível registrar o dispositivo porque a conta do usuário não tem a licença necessária.|Antes de registrarem os dispositivos, a licença necessária deverá ser atribuída aos usuários. Esta mensagem indica que eles têm o tipo de licença errado para a autoridade de gerenciamento de dispositivo móvel. Por exemplo, eles verão esse erro se ambos os pontos a seguir forem verdadeiros:<ol><li>O Intune foi definido como a autoridade de gerenciamento de dispositivo móvel</li><li>Eles estão usando uma licença do System Center 2012 R2 Configuration Manager.</li></ol>Para saber mais, veja [Atribuir licenças do Intune a suas contas de usuário](/intune/licenses-assign).|
|**O administrador de TI precisa configurar uma autoridade de MDM**<br>Parece que seu administrador de TI não configurou uma autoridade de MDM. Obtenha ajuda do seu administrador de TI ou tente novamente mais tarde.|A autoridade de gerenciamento de dispositivo móvel não foi definida.|A autoridade de gerenciamento de dispositivo móvel não foi definida no Intune. Veja informações sobre como [definir a autoridade de gerenciamento de dispositivo móvel](/intune/mdm-authority-set).|


### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Os dispositivos apresentaram falha no check-in com o serviço do Intune e são exibidos como "Não íntegro" no console de administração do Intune
**Problema:** alguns dispositivos Samsung que estão executando versões do Android 4.4 e 5.x podem interromper a verificação com o serviço do Intune. Se os dispositivos não fizerem o check-in:

- Eles não poderão receber políticas, aplicativos e comandos remotos do serviço do Intune.
- Eles mostram um Estado de Gerenciamento **não íntegro** no console do administrador.
- Os usuários que são protegidos por políticas de acesso condicional podem perder o acesso aos recursos corporativos.

O software Samsung Smart Manager, que é fornecido em certos dispositivos Samsung, pode desativar o Portal da Empresa do Intune e seus componentes. Quando o Portal da Empresa está em um estado desativado, ele não pode ser executado em segundo plano e, portanto, não pode contatar o serviço do Intune.

**Resolução nº1:**

Avise os usuários para iniciar o aplicativo do Portal da Empresa manualmente. Depois que o aplicativo for reiniciado, o dispositivo faz o check-in no serviço do Intune.

> [!IMPORTANT]
> Abrir o aplicativo do Portal da Empresa manualmente é uma solução temporária, pois o Gerenciador Inteligente Samsung pode desativar o aplicativo do Portal da Empresa novamente.

**Resolução nº2:**

Peça aos usuários que tentem atualizar para o Android 6.0. O problema de desativação não ocorre em dispositivos Android 6.0. Para verificar se uma atualização está disponível, acesse **Configurações** > **Sobre o dispositivo** > **Baixar atualizações manualmente** > siga as instruções nos prompts.

**Resolução nº3:**

Se a Resolução nº2 não funcionar, oriente os usuários a seguir estas etapas para fazer com que o Gerenciador Inteligente exclua o aplicativo do Portal da Empresa:

1. Inicie o aplicativo Gerenciador Inteligente no dispositivo.

   ![Selecione o ícone do Gerenciador Inteligente no dispositivo](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-icon.png)

2. Escolha o bloco **Bateria**.

   ![Selecione o bloco Bateria](./media/troubleshoot-device-enrollment-in-intune/smart-manager-battery-tile.png)

3. Em **Economia de energia do aplicativo** ou em **Otimização do aplicativo**, selecione **Detalhes**.

   ![Selecione Detalhes em Economia de energia do aplicativo ou em Otimização de aplicativo](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-power-saving-detail.png)

4. Escolha **Portal da Empresa** na lista de aplicativos.

   ![Selecione o Portal da Empresa na lista de aplicativos](./media/troubleshoot-device-enrollment-in-intune/smart-manager-company-portal.png)

5. Escolha **Desativado**.

   ![Selecione Desativado na caixa de diálogo Otimização de aplicativo](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-optimization-turned-off.png)

6. Em **Economia de energia do aplicativo** ou em **Otimização do aplicativo**, confirme se o Portal da Empresa está desativado.

   ![Verifique se o Portal da Empresa está desativado](./media/troubleshoot-device-enrollment-in-intune/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Falha na instalação do perfil
**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo Android.

**Resolução:**

1.  Confirme se o usuário recebeu a atribuição de uma licença apropriada para a versão do serviço do Intune que você está usando.

2.  Confirme se o dispositivo ainda não está registrado com outro provedor de MDM.

3. Confirme se o dispositivo ainda não tem um perfil de gerenciamento instalado.

4.  Confirme se o Chrome para Android é o navegador padrão e se os cookies estão habilitados.

### <a name="android-certificate-issues"></a>Problemas de certificado do Android

**Problema**: os usuários recebem a seguinte mensagem no dispositivo: *Não é possível se conectar porque o dispositivo não tem um certificado necessário.*

**Resolução 1**:

Talvez o usuário consiga recuperar o certificado ausente seguindo as instruções em [Seu dispositivo não tem um certificado necessário](/intune-user-help/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Se o erro persistir, tente a Resolução 2.

**Resolução 2**:

Depois de inserirem suas credenciais corporativas e serem redirecionado para o logon federado, os usuários ainda veem o erro de certificado ausente. Nesse caso, o erro pode significar que um certificado intermediário está ausente do seu servidor de AD FS (Serviços de Federação do Active Directory)

O erro de certificado ocorre porque os dispositivos com Android exigem a inclusão de certificados intermediários em uma [Saudação do Servidor SSL](https://technet.microsoft.com/library/cc783349.aspx). No momento, um servidor AD FS padrão ou instalação de servidor WAP – AD FS Proxy envia somente o certificado SSL do serviço AD FS na resposta de saudação de servidor SSL para uma saudação de cliente SSL.

Para corrigir o problema, importe os certificados para os Certificados Pessoais do Computador no servidor do AD FS ou proxies da seguinte maneira:

1.  Em servidores proxy e do ADFS, clique com o botão direito do mouse em **Iniciar** > **Executar** > **certlm.msc** para iniciar o Console de Gerenciamento de Certificado do Computador Local.
2.  Expanda **Pessoal** e escolha **Certificados**.
3.  Localize o certificado da comunicação de serviço do AD FS (certificado assinado publicamente) e clique duas vezes para exibir suas propriedades.
4.  Escolha a guia **Caminho de Certificação** para ver o(s) certificado(s) pai do certificado.
5.  Em cada certificado pai, escolha **Exibir Certificado**.
6.  Escolha **Detalhes** > **Copiar para arquivo...**
7.  Siga as solicitações do assistente para exportar ou salvar a chave pública do certificado pai para o local do arquivo de sua preferência.
8.  Clique com botão direito em **Certificados** > **Todas as Tarefas** > **Importar**.
9.  Siga as solicitações do assistente para importar os certificados pai para **Computador Local\Pessoal\Certificados**.
10. Reinicie os servidores AD FS.
11. Repita as etapas acima em todos os servidores AD FS e proxy.

Para verificar uma instalação de certificado apropriada, use a ferramenta de diagnóstico disponível em [https://www.digicert.com/help/](https://www.digicert.com/help/). Na caixa **Endereço do Servidor**, insira o FQDN de seu servidor do AD FS (ou seja: sts.contso.com) e clique em **Verificar Servidor**.

**Para validar a instalação correta do certificado**:

As etapas a seguir descrevem apenas um dos vários métodos e ferramentas que você pode usar para validar a instalação correta do certificado.

1. Vá para a [ferramenta gratuita do Digicert](ttps://www.digicert.com/help/).
2. Insira o nome de domínio totalmente qualificado do servidor AD FS (por exemplo, sts.contoso.com) e selecione **VERIFICAR SERVIDOR**.

Se o certificado do servidor estiver instalado corretamente, você verá todas as marcas de seleção nos resultados. Se o problema acima existir, você ver um “X” vermelho nas seções “Correspondências de Nome de Certificado” e “Certificado SSL instalado corretamente” do relatório.


## <a name="ios-issues"></a>Problemas de iOS

### <a name="ios-enrollment-errors"></a>Erros de registro do iOS
A tabela a seguir lista os erros que os usuários finais podem encontrar durante o registro de dispositivos de iOS no Intune.

|Mensagem de erro|Problema|Resolução|
|-------------|-----|----------|
|NoEnrollmentPolicy|Nenhuma política de registro localizada|Verifique se todos os pré-requisitos de registro, como o certificado APNs (Apple Push Notification Service), foram configurados e se "iOS como plataforma" está habilitado. Para obter instruções, veja [Configurar gerenciamento de dispositivos iOS e Mac](ios-enroll.md).|
|DeviceCapReached|Há muitos dispositivos móveis registrados.|Antes de registrar outro dispositivo móvel, o usuário deve remover um de seus dispositivos móveis registrados atualmente no Portal da Empresa. Consulte as instruções para o tipo de dispositivo que você está usando: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios), [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Há um problema com o certificado que permite que o dispositivo móvel se comunique com a rede da empresa.<br /><br />|O APNs (Apple Push Notification Service) fornece um canal para contatar os dispositivos iOS registrados. O registro falhará e essa mensagem será exibida se:<ul><li>As etapas para obter um certificado APNs não forem concluídas, ou</li><li>O certificado APNs expirou.</li></ul>Examine as informações sobre como configurar usuários em [Sincronizar o Active Directory e adicionar usuários ao Intune](users-add.md) e em [Organizando usuários e dispositivos](groups-add.md).|
|AccountNotOnboarded|Há um problema com o certificado que permite que o dispositivo móvel se comunique com a rede da empresa.<br /><br />|O APNs (Apple Push Notification Service) fornece um canal para contatar os dispositivos iOS registrados. O registro falhará e essa mensagem será exibida se:<ul><li>As etapas para obter um certificado APNs não forem concluídas, ou</li><li>O certificado APNs expirou.</li></ul>Para obter mais informações, examine [Set up iOS and Mac management with Microsoft Intune](ios-enroll.md) (Configurar gerenciamento de iOS e Mac com o Microsoft Intune).|
|DeviceTypeNotSupported|O usuário pode ter tentado se registrar usando um dispositivo não iOS. O tipo de dispositivo móvel que você está tentando registrar não é compatível.<br /><br />Confirme se o dispositivo está executando o iOS versão 8.0 ou posterior.<br /><br />|Verifique se o dispositivo do usuário está executando o iOS versão 8.0 ou posterior.|
|UserLicenseTypeInvalid|Não foi possível registrar o dispositivo porque a conta do usuário ainda não é membro de um grupo de usuários obrigatório.<br /><br />|Antes que possam registrar seus dispositivos, os usuários devem ser membros do grupo de usuários correto. Esta mensagem indica que eles têm o tipo de licença errado para a autoridade de gerenciamento de dispositivo móvel. Por exemplo, eles verão esse erro se ambos os pontos a seguir forem verdadeiros:<ol><li>O Intune foi definido como a autoridade de gerenciamento de dispositivo móvel</li><li>eles estão usando uma licença do System Center 2012 R2 Configuration Manager.</li></ol>Examine os artigos a seguir para obter mais informações:<br /><br />Examine [Configurar gerenciamento de iOS e Mac com o Microsoft Intune](ios-enroll.md) e as informações sobre como configurar usuários no [Sincronizar o Active Directory e adicionar usuários ao Intune](users-add.md) e em [Organizando usuários e dispositivos](groups-add.md).|
|MdmAuthorityNotDefined|A autoridade de gerenciamento de dispositivo móvel não foi definida.<br /><br />|A autoridade de gerenciamento de dispositivo móvel não foi definida no Intune.<br /><br />Examine o item nº 1 na seção "Etapa 6: registrar dispositivos móveis e instalar um aplicativo” em [Começar com uma avaliação de 30 dias do Microsoft Intune](free-trial-sign-up.md).|

### <a name="devices-are-inactive-or-the-admin-console-cant-communicate-with-them"></a>Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles
**Problema:** os dispositivos iOS não estão fazendo check-in no serviço do Intune. Os dispositivos devem fazer o check-in no serviço periodicamente para manter o acesso aos recursos corporativos protegidos. Se os dispositivos não fizerem o check-in:

- Eles não poderão receber políticas, aplicativos e comandos remotos do serviço do Intune.
- Eles mostram um Estado de Gerenciamento **não íntegro** no console do administrador.
- Os usuários que são protegidos por políticas de acesso condicional podem perder o acesso aos recursos corporativos.

**Resolução:** compartilhe as seguintes resoluções com seus usuários finais para ajudá-los a recuperar o acesso aos recursos corporativos.

Quando os usuários iniciarem o aplicativo do Portal da Empresa do iOS, ele poderá informar se o dispositivo perdeu contato com o Intune. Se detectar que não há nenhum contato, ele tentará realizar a sincronização automaticamente com o Intune para se reconectar (e os usuários verão a mensagem **Tentando sincronizar…**) .

  ![Notificação Tentando sincronizar](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_trying_to_sync_notification.png)

Se a sincronização for bem-sucedida, você verá uma notificação embutida **Sincronização bem-sucedida** no aplicativo do Portal da Empresa do iOS, indicando que o dispositivo está em um estado íntegro.

  ![Notificação Sincronização bem-sucedida](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_sync_successful_notification.png)

Se a sincronização não for bem-sucedida, os usuários verão uma notificação embutida **Não é possível sincronizar** no aplicativo do Portal da Empresa do iOS.

  ![Não é possível sincronizar a notificação](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_unable_to_sync_notification.png)

Para corrigir o problema, os usuários devem selecionar o botão **Configurar**, que está à direita da notificação **Não é possível sincronizar**. O botão Configurar leva os usuários para a tela de fluxo Configuração do Acesso da Empresa, em que eles podem seguir os prompts para registrar seu dispositivo.

  ![Tela de Configuração de Acesso da Empresa](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_company_access_setup.png)

Depois de registrado, os dispositivos retornam ao estado íntegro e recuperam o acesso aos recursos da empresa.

### <a name="verify-ws-trust-13-is-enabled"></a>Verifique se o WS-Trust 1.3 está habilitado
**Problema** Não é possível registrar dispositivos iOS do DEP (Programa de Registro de Dispositivos)

Registrar dispositivos DEP com afinidade de usuário requer que o ponto de extremidade nome do usuário/misto do WS-Trust 1.3 esteja habilitado para solicitar tokens de usuário. O Active Directory permite esse ponto de extremidade por padrão. Para obter uma lista de pontos de extremidade habilitados, use o cmdlet do PowerShell Get-AdfsEndpoint e procure o ponto de extremidade trust/13/UsernameMixed. Por exemplo:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

Para saber mais, veja a [documentação do Get-AdfsEndpoint](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

Para saber mais, veja as [Práticas recomendadas para proteção dos Serviços de Federação do Active Directory](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs). Para obter ajuda para determinar se o nome de usuário/misto do WS-Trust 1.3 está habilitado no seu provedor de federação de identidade:
- entre em contato com o Suporte da Microsoft se utilizar o ADFS
- entre em contato com seu fornecedor de identidade terceirizado.


### <a name="profile-installation-failed"></a>Falha na instalação do perfil
**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo iOS.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Etapas de solução de problemas para falhas na instalação de perfil

1.  Confirme se o usuário recebeu a atribuição de uma licença apropriada para a versão do serviço do Intune que você está usando.

2.  Confirme se o dispositivo ainda não está registrado com outro provedor de MDM.

3. Confirme se o dispositivo ainda não tem um perfil de gerenciamento instalado.

4.  Navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) e tente instalar o perfil quando solicitado.

5.  Confirme se o Safari para iOS é o navegador padrão e se os cookies estão habilitados.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Os dispositivos iOS registrados não aparecem no console ao usar o System Center Configuration Manager com o Intune
**Problema:** o usuário registra um dispositivo iOS, mas ele não aparece no console de administração do Configuration Manager. O dispositivo não indica que ele foi registrado. Possíveis causas:

- O Conector do Microsoft Intune, no site do Gerenciador de Configurações, não está se comunicando com o serviço do Intune.
- O componente do ddm (Data Discovery Manager) ou do statmgr (Gerenciamento de estado) não está processando mensagens no serviço do Intune.
- Você pode ter baixado o certificado MDM de uma conta e o usado em outra conta.


**Resolução:** examine os seguintes arquivos de log para identificar possíveis erros:

- dmpdownloader.log
- ddm.log
- statmgr.log

Em breve, adicionaremos exemplos sobre o que procurar nesses arquivos de log.


### <a name="users-ios-device-is-stuck-on-an-enrollment-screen-for-more-than-10-minutes"></a>O dispositivo iOS do usuário está parado em uma tela de registro por mais de 10 minutos

**Problema**: um registro de dispositivo pode ficar parado em uma dessas duas telas:
- Aguardando a configuração final da “Microsoft”
- Aplicativo de acesso guiado indisponível. Contate o administrador.

Este problema poderá acontecer se:
- houver uma interrupção temporária dos serviços da Apple ou
- o registro do iOS estiver configurado para usar tokens VPP, conforme mostrado na tabela, mas há algo errado com o token VPP.

| Configurações de registro | Valor |
| ---- | ---- |
| Plataforma | iOS |
| Afinidade de usuário | Registrar com afinidade de usuário |
|Autenticar com o Portal da Empresa em vez do Assistente de Configuração da Apple | Sim |
| Instalar o portal da empresa com VPP | Token de uso: endereço do token |
| Executar o Portal da Empresa no Modo de Aplicativo Único até a autenticação | Sim |

**Resolução**: para corrigir o problema, você precisa:
1. Determine se há algo errado com o token de VPP e corrija-o.
2. Identifique quais dispositivos estão bloqueados.
3. Apague os dispositivos afetados.
4. Instrua o usuário a reiniciar o processo de registro.

#### <a name="determine-if-theres-something-wrong-with-the-vpp-token"></a>Determinar se há algo errado com o token de VPP
1. Acesse **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > nome do token > **Perfis** > nome do perfil > **Gerenciar** > **Propriedades**.
2. Examine as propriedades para verificar se são exibidos erros semelhantes ao seguinte:
    - Este token expirou.
    - Este token está sem licenças do Portal da Empresa.
    - Este token está sendo usado por outro serviço.
    - Este token está sendo usado por outro locatário.
    - Este token foi excluído.
3. Corrija os problemas do token.

#### <a name="identify-which-devices-are-blocked-by-the-vpp-token"></a>Identifique quais dispositivos estão bloqueados pelo token de VPP
1. Acesse **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > nome do token > **Dispositivos**.
2. Filtre a coluna **Status do perfil** por **Bloqueado**.
3. Anote os números de série de todos os dispositivos que estão **Bloqueados**.

#### <a name="remotely-wipe-the-blocked-devices"></a>Apagar remotamente os dispositivos bloqueados
Depois de corrigir os problemas do token de VPP, será preciso apagar os dispositivos que estão bloqueados.
1. Acesse **Intune** > **Dispositivos** > **Todos os dispositivos** > **Colunas** > **Número de série** > **Aplicar**. 
2. Para cada dispositivo bloqueado, selecione-o na lista **Todos os dispositivos** e escolha **Apagar** > **Sim**.

#### <a name="tell-the-users-to-restart-the-enrollment-process"></a>Instrua os usuários a reiniciarem o processo de registro
Depois que você tiver apagado os dispositivos bloqueados, instrua os usuários a reiniciar o processo de registro.

## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemas ao usar o System Center Configuration Manager com o Intune
### <a name="mobile-devices-disappear"></a>Dispositivos móveis desaparecem
**Problema:** após registrar com êxito um dispositivo móvel no Configuration Manager, ele desaparece da coleção de dispositivos móveis. No entanto, o dispositivo ainda tem o Perfil de Gerenciamento e está listado no Gateway de CSS.

**Resolução:** esse problema pode ocorrer porque:
- Você tem um processo personalizado para remover dispositivos não ingressados no domínio, ou 
- o usuário desativou o dispositivo da assinatura.
Para validar e verificar qual conta de usuário ou processo removeu o dispositivo do console do Configuration Manager, execute as seguintes etapas.

#### <a name="check-how-device-was-removed"></a>Verifique como o dispositivo foi removido

1.  No console de administração do Configuration Manager, selecione **Monitoramento** &gt; **Status do Sistema** &gt; **Consultas de Mensagem de Status**.

2.  Clique com o botão direito do mouse em **Recursos Membros da Coleção Excluídos Manualmente** e selecione **Mostrar Mensagens**.

3.  Selecione uma data/hora apropriada ou as últimas 12 horas.

4.  Localize o dispositivo em questão e examine como o dispositivo foi removido. O exemplo a seguir mostra que a conta SCCMInstall excluiu o dispositivo por meio de um aplicativo desconhecido.

    ![Captura de tela para diagnóstico de exclusão do dispositivo](./media/troubleshoot-device-enrollment-in-intune/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Verifique se o Configuration Manager não tem uma tarefa agendada, script ou outro processo que poderia estar limpando automaticamente dispositivos móveis, fora do domínio ou relacionados.

### <a name="other-ios-enrollment-errors"></a>Outros erros de registro do iOS
Uma lista de erros de registro do iOS é fornecida em nossa documentação em [Solucionando problemas de registro de dispositivo iOS no Microsoft Intune](https://support.microsoft.com/help/4039809/troubleshooting-ios-device-enrollment-in-intune).

## <a name="pc-issues"></a>Problemas do computador

|Mensagem de erro|Problema|Resolução|
|---|---|---|
|**O administrador de TI precisa atribuir uma licença para o acesso**<br>Seu administrador de TI não concedeu a você o acesso para usar este aplicativo. Obtenha ajuda do seu administrador de TI ou tente novamente mais tarde.|Não é possível registrar o dispositivo porque a conta do usuário não tem a licença necessária.|Antes de registrarem os dispositivos, a licença necessária deverá ser atribuída aos usuários. Esta mensagem indica que eles têm o tipo de licença errado para a autoridade de gerenciamento de dispositivo móvel. Por exemplo, eles verão esse erro se ambos os pontos a seguir forem verdadeiros: <ol><li>O Intune foi definido como a autoridade de gerenciamento de dispositivo móvel</li><li>Eles estão usando uma licença do System Center 2012 R2 Configuration Manager.</li></ol>Veja informações sobre [como atribuir licenças do Intune às contas de usuário](https://docs.microsoft.com/intune/licenses-assign).|



### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>O computador já está registrado - erro hr 0x8007064c
**Problema:** o registro falha com o erro **O computador já está registrado**. O log de registro mostra o erro **hr 0x8007064c**.

Essa falha pode ocorrer porque o computador:
- estava registrado anteriormente, ou
- tem a imagem clonada de um computador que já estava registrado.
O certificado de conta da conta anterior ainda está presente no computador.

**Resolução:**

1. No menu **Iniciar**, digite **Executar** -> **MMC**.
1. Escolha **Arquivo** > **Adicionar/Remover Snap-ins**.
1. Clique duas vezes em **Certificados**, escolha a **Conta de computador** > **Avançar** e selecione **Computador Local**.
1. Clique duas vezes em **Certificados (computador local)** e escolha **Pessoal/Certificados**.
1. Procure pelo certificado Intune emitido por Sc_Online_Issuing e exclua-o, se estiver presente.
1. Se a chave do Registro a seguir existir, exclua-a: existir: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** e todas as subchaves.
1. Tente registrar novamente.
1. Se o computador ainda não conseguir se registrar, procure e exclua esta chave, se existir: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Tente registrar novamente.

    > [!IMPORTANT]
    > Nesta seção, o método ou tarefa contém etapas que descrevem como modificar o Registro. No entanto, problemas graves podem ocorrer se você modificar o Registro incorretamente. Portanto, certifique-se de seguir estas etapas com cuidado. Para maior proteção, faça backup do Registro antes de modificá-lo. Assim, será possível restaurá-lo se houver algum problema.
    > Para obter mais informações sobre como fazer backup e restaurar o Registro, leia [Como fazer backup e restaurar o registro no Windows](https://support.microsoft.com/kb/322756)

## <a name="general-enrollment-error-codes"></a>Códigos de erro geral de registro

|Código do erro|Possível problema|Resoluções sugeridas|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |O relógio no computador cliente não está definido com a hora correta.|Verifique se o relógio e o fuso horário do computador cliente estão definidos para a hora e o fuso horário corretos.|
|0x80240438, 0x80CF0438, 0x80CF402C|não é possível se conectar ao serviço do Intune. Verifique as configurações de proxy do cliente.|Verifique se o Intune é compatível com a configuração de proxy no computador cliente. Confirme se o computador cliente tem acesso à Internet.|
|0x80240438, 0x80CF0438|As configurações de proxy no Internet Explorer e no Sistema Local não estão definidas.|não é possível se conectar ao serviço do Intune. Verifique as configurações de proxy do cliente. Confirme se o Intune é compatível com a configuração de proxy no computador cliente. Confirme se o computador cliente tem acesso à Internet.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|O pacote de inscrição está desatualizado.|Baixe e instale o pacote do software cliente atual no espaço de trabalho Administração.|
|0x80043002, 0x80CF3002|A conta está no modo de manutenção.|Não é possível registrar novos computadores cliente quando a conta está no modo de manutenção. Para exibir suas configurações de conta, entre na sua conta.|
|0x80043003, 0x80CF3003|A conta está excluída.|Verifique se sua conta e assinatura do Intune continuam ativas. Para exibir suas configurações de conta, entre na sua conta.|
|0x80043005, 0x80CF3005|O computador cliente foi desativado.|Aguarde algumas horas, remova do computador as versões mais antigas do software cliente e tente instalar novamente o software cliente.|
|0x80043006, 0x80CF3006|O número máximo de estações permitidas para a conta foi atingido.|Sua organização precisa adquirir estações adicionais para poder registrar mais computadores cliente no serviço.|
|0x80043007, 0x80CF3007|Não foi possível localizar o arquivo de certificado na mesma pasta do programa de instalação.|Extrai todos os arquivos antes de iniciar a instalação. Não renomeie ou mova os arquivos extraídos: todos os arquivos precisam existir na mesma pasta ou a instalação falhará.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|O software não pode ser instalado porque uma reinicialização do computador cliente está pendente.|Reinicie o computador e tente instalar novamente o software cliente.|
|0x80070032|Um ou mais pré-requisitos de instalação do software cliente não foram encontrados no computador cliente.|Verifique se todas as atualizações necessárias estão instaladas no computador cliente e tente instalar novamente o software cliente.|
|0x80043008, 0x80CF3008|Falha ao iniciar o serviço de atualizações do Microsoft Online Management.|Entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](get-support.md) (Como obter suporte para o Microsoft Intune).|
|0x80043009, 0x80CF3009|O computador cliente já está inscrito no serviço.|Você deve retirar o computador cliente antes de ser possível registrá-lo novamente no serviço.|
|0x8004300B, 0x80CF300B|Não foi possível executar o pacote de instalação do software cliente porque a versão do Windows que está em execução no cliente não é compatível.|O Intune não é compatível com a versão do Windows em execução no computador cliente.|
|0xAB2|O Windows Installer não pode acessar o tempo de execução do VBScript para uma ação personalizada.|Este erro é causado por uma ação personalizada que se baseia em bibliotecas de vínculo dinâmico (DLLs). Ao solucionar problemas de DLL, pode ser necessário usar as ferramentas descritas em [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Suporte da Microsoft KB198038: Ferramentas úteis para problemas de implantação e pacote).|
|0x80cf0440|A conexão com o ponto de extremidade do serviço foi encerrada.|A conta de avaliação ou paga está suspensa. Criar uma nova conta de avaliação ou paga e registrar novamente.|




### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](get-support.md) (Como obter suporte para o Microsoft Intune).
