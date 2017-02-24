---
title: "Solucionar problemas de registro de dispositivo | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como solucionar problemas de registro do dispositivo."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 8d56b6600ca86faabbb50d29405969385eb29940


---

# <a name="troubleshoot-device-enrollment-in-intune"></a>Solução de problemas de registro de dispositivo no Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Este tópico fornece sugestões para solução de problemas de registro do dispositivo. Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.


## <a name="initial-troubleshooting-steps"></a>Etapas para solução de problemas iniciais

Antes de iniciar a solução de problemas, verifique se você configurou o Intune corretamente para habilitar o registro. Consulte [Registrar dispositivos Android e Standard Knox](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices.md) para ver links para etapas de registro para cada plataforma.

Seus usuários de dispositivo gerenciado podem coletar logs de registro e diagnóstico para você examinar. As instruções para o usuário coletar logs são fornecidas em:

- [Enviar erros de registro do Android ao seu administrador de TI](https://docs.microsoft.com/intune/enduser/send-enrollment-errors-to-your-it-admin-android)
- [Enviar erros do iOS para o administrador de TI](https://docs.microsoft.com/intune/enduser/send-errors-to-your-it-admin-ios)

## <a name="general-enrollment-issues"></a>Problemas gerais de registro
Esses problemas podem ocorrer em todas as plataformas de dispositivo.

### <a name="device-cap-reached"></a>Limite do dispositivo associado
**Problema:** um usuário recebe um erro no seu dispositivo durante o registro, como um erro **Portal da empresa temporariamente indisponível** em um dispositivo iOS, e o DMPdownloader.log no Configuration Manager contém o erro **DeviceCapReached**.

**Resolução:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Verifique o número de dispositivos registrados e permitidos

No portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune do Portal do Azure, vá para **Registrar dispositivos** > **Restrições de Registro** e valide se o usuário não tem mais do que o máximo permitido de 15 dispositivos atribuídos.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Os administradores podem excluir dispositivos no portal do Azure Active Directory.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Para excluir dispositivos no portal do Active Directory do Azure

1.  Navegue até [http://aka.ms/accessaad](http://aka.ms/accessaad) ou clique em **Administrador** &gt; **Azure AD** de [https://portal.office.com](https://portal.office.com).

2.  Faça logon com sua ID da organização usando o link no lado esquerdo da página.

3.  Se não tiver uma, crie uma assinatura do Azure. Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (clique no link de assinatura **Register your free Azure Active Directory** [Registrar seu Azure Active Directory gratuito]).

4.  Selecione **Active Directory** e selecione sua organização.

5.  Selecione a guia **Usuários** .

6.  Selecione o usuário cujos dispositivos que deseja excluir.

7.  Escolha **Dispositivos**.

8.  Remova os dispositivos conforme apropriado, como aqueles que não estão mais em uso, ou aqueles que têm definições imprecisas.

> [!NOTE]

> Você pode evitar o limite de registro de dispositivo usando gerenciadores de registro do dispositivo, conforme descrito em [Registrar dispositivos usando o Gerenciador de registro de dispositivo](/intune-azure/enroll-devices/enroll-devices-using-device-enrollment-manager.md).
>
> Uma conta de usuário que é adicionada ao grupo de Gerenciadores de Registro de Dispositivos não conseguirá concluir o registro quando a política de acesso condicional for aplicada a esse logon de usuário específico.

### <a name="company-portal-temporarily-unavailable"></a>Portal da empresa temporariamente indisponível
**Problema:** um usuário recebe um erro de **Portal da empresa temporariamente indisponível** no dispositivo.

**Resolução:**

1.  Remova o aplicativo de Portal da Empresa do Intune do dispositivo.

2.  No dispositivo, abra o navegador, navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), e tente algum logon de usuário.

3.  Se o usuário não conseguir efetuar logon, faça-o tentar outra rede.

4.  Se isso falhar, confirme que as credenciais do usuário foram sincronizadas corretamente com o Active Directory do Azure.

5.  Se o usuário fizer logon com êxito, um dispositivo iOS solicitará que você instale o aplicativo de Portal da Empresa do Intune e o registre. Em um dispositivo Android, você precisará instalar manualmente o aplicativo de Portal da Empresa do Intune, e depois disso você poderá tentar novamente a inscrição.

### <a name="mdm-authority-not-defined"></a>Autoridade MDM não definida
**Problema:** um usuário recebe um erro de **Autoridade MDM não definida**.

**Resolução:**

1.  Verifique se a Autoridade MDM foi definida corretamente para o tipo de serviço do Intune que está usando (isto é, Intune, Office 365 ou System Center Configuration Manager com Intune). Consulte [Definir a autoridade de gerenciamento de dispositivo móvel](https://docs.microsoft.com/en-us/intune-azure/enroll-devices/set-mdm-authority) para ver instruções.

    > [!NOTE]
    > Após definir a Autoridade MDM, você pode alterá-la apenas entrando em contato com o Suporte, conforme descrito em [Como obter suporte para o Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

2.  Verifique se as credenciais do usuário foram sincronizadas corretamente com o Active Directory do Azure, verificando se seu UPN corresponde às informações do Active Directory no Portal da conta.
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


**Resolução:** os clientes do Microsoft Office 365 que utilizarem o logon único (SSO) por meio do AD FS 2.0 e tiverem vários domínios de nível superior para sufixos UPN de usuários em sua organização (por exemplo, @contoso.com ou @fabrikam.com)) deverão implantar uma instância separada do Serviço de Federação AD FS 2.0 em cada sufixo.  Agora, há um [pacote cumulativo de atualizações para o AD FS 2.0](http://support.microsoft.com/kb/2607496) que funciona em conjunto com o comutador **SupportMultipleDomain** para habilitar o servidor AD FS, para dar suporte a esse cenário sem a necessidade de exigir servidores AD FS 2.0 adicionais. Confira [este blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) para obter mais informações.


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

Solicite aos usuários que sigam as instruções em [Falta ao dispositivo um certificado necessário](https://docs.microsoft.com/intune/enduser/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Se o erro persistir após os usuários seguirem essas instruções, tente a Resolução 2.

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

### <a name="profile-installation-failed"></a>Falha na instalação do perfil
**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo iOS.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Etapas de solução de problemas para falhas na instalação de perfil

1.  Confirme que foi atribuída ao usuário uma licença apropriada para a versão do serviço do Intune que você está usando.

2.  Confirme se o dispositivo já não está registrado com outro provedor MDM ou se ele ainda não tem um perfil de gerenciamento instalado.

3.  Navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) e tente instalar o perfil quando solicitado.

4.  Confirme se o Safari para iOS é o navegador padrão e se os cookies estão habilitados.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Os dispositivos iOS registrados não aparecem no console ao usar o System Center Configuration Manager com o Intune
**Problema:** o usuário registra um dispositivo iOS, mas ele não aparece no console de administração do Configuration Manager. O dispositivo não indica que ele foi registrado. Possíveis causas:

- Você pode ter registrado seu conector Intune em uma conta e, então, ter registrado o dispositivo em outra conta.
- Você pode ter baixado o certificado MDM de uma conta e o usado em outra conta.


**Resolução:** execute as etapas a seguir:

1. Desabilite o iOS dentro do conector do Windows Intune.
    1. Clique com o botão direito do mouse na assinatura do Intune e selecione **Propriedades**.
    1. Na guia "iOS", desmarque a opção "Habilitar registro do iOS".



2. No SQL, execute as etapas a seguir no banco de dados do CAS

    1. atualizar o SC_ClientComponent_Property set Value2 = '', em que Nome é igual a '%APNS%'
    1. excluir do MDMPolicy, em que PolicyType = 7
    1. excluir do MDMPolicyAssignment, em que PolicyType = 7
    1. atualizar o SC_ClientComponent_Property set Value2 = '', em que Nome é igual a '%APNS%'
    1. excluir do MDMPolicy, em que PolicyType = 11
    1. excluir do MDMPolicyAssignment, em que PolicyType = 11
    1. EXCLUIR Drs_Signals
3. Reinicie o serviço SMS Executive ou o servidor CM.

4. Obtenha um novo certificado APN e carregue-o. Para fazer isso, clique com o botão direito do mouse na assinatura do Intune no painel esquerdo do Configuration Manager. Selecione a opção **Criar solicitação de certificado APNs** e siga as instruções.
5. 
## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemas ao usar o System Center Configuration Manager com o Intune

### <a name="mobile-devices-disappear"></a>Dispositivos móveis desaparecem

**Problema:** após registrar com êxito um dispositivo móvel no Configuration Manager, ele desaparece da coleção de dispositivos móveis, mas o dispositivo ainda tem o Perfil de gerenciamento e é listado no Gateway de CSS.

**Resolução:** isso pode ocorrer se você usa um processo personalizado para remover dispositivos não ingressados no domínio ou porque o usuário desativou o dispositivo da assinatura. Para validar e verificar qual conta de usuário ou processo removeu o dispositivo do console do Configuration Manager, execute as seguintes etapas para verificar como o dispositivo foi removido.

1.  No console de administração do Configuration Manager, selecione **Monitoramento** &gt; **Status do Sistema** &gt; **Consultas de Mensagem de Status**.

2.  Clique com o botão direito do mouse em **Recursos Membros da Coleção Excluídos Manualmente** e selecione **Mostrar Mensagens**.

3.  Escolha uma data/hora apropriada ou as últimas 12 horas.

4.  Localize o dispositivo em questão e examine como o dispositivo foi removido. O exemplo a seguir mostra que a conta SCCMInstall excluiu o dispositivo por meio de um aplicativo desconhecido.

    ![Captura de tela para diagnóstico de exclusão do dispositivo](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  Verifique se o Configuration Manager não tem uma tarefa agendada, script ou outro processo que poderia estar limpando automaticamente dispositivos móveis, fora do domínio ou relacionados.




### <a name="other-ios-enrollment-errors"></a>Outros erros de registro do iOS

Você pode exibir uma lista de [Erros de registro do iOS](https://docs.microsoft.com/intune/enduser/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios) que os usuários finais podem ver. A lista fornece informações sobre mensagens de erro que os usuários finais podem ver e as etapas que você seguir para resolver o problema.

## <a name="pc--issues"></a>Problemas do computador

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>O computador já está registrado - erro hr 0x8007064c
**Problema:** o registro falha com o erro **O computador já está registrado**. O log de registro mostra o erro **hr 0x8007064c**.

Esse erro pode ocorrer porque o computador já foi registrado anteriormente ou tem a imagem clonada de um computador que tinha sido registrado. O certificado de conta da conta anterior ainda está presente no computador.

**Resolução:**

1.. No menu **Iniciar**, digite **Executar** -> **MMC**.
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
    > Para obter mais informações sobre como fazer backup e restaurar o Registro, leia [Como fazer backup e restaurar o registro no Windows](https://support.microsoft.com/en-us/kb/322756).

## <a name="general-enrollment-error-codes"></a>Códigos de erro gerais de registro

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
|0x80043008, 0x80CF3008|Falha ao iniciar o serviço de atualizações do Microsoft Online Management.|Entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) (Como obter suporte para o Microsoft Intune).|
|0x80043009, 0x80CF3009|O computador cliente já está inscrito no serviço.|Você deve retirar o computador cliente antes de ser possível registrá-lo novamente no serviço.|
|0x8004300B, 0x80CF300B|O pacote de instalação do software cliente não pode ser executado porque a versão do Windows que está em execução no cliente não é suportada.|O Intune não dá suporte à versão do Windows em execução no computador cliente.|
|0xAB2|O Windows Installer não pode acessar o tempo de uma ação personalizada de execução do VBScript.|Este erro é causado por uma ação personalizada que se baseia em bibliotecas de vínculo dinâmico (DLLs). Ao solucionar problemas de DLL, pode ser necessário usar as ferramentas descritas em [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/en-us/kb/198038) (Suporte da Microsoft KB198038: Ferramentas úteis para problemas de implantação e pacote).|
|0x80cf0440|A conexão com o ponto de extremidade do serviço foi encerrada.|A conta de avaliação ou paga está suspensa. Criar uma nova conta de avaliação ou paga e registrar novamente.|




### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) (Como obter suporte para o Microsoft Intune).



<!--HONumber=Feb17_HO3-->


