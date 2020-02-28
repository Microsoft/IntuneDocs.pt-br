---
title: Solucionando problemas de registro de dispositivo Windows no Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestões para solucionar alguns dos problemas mais comuns ao registrar dispositivos Windows no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dae8e92209a8640ab3254e073d3043d390c3791b
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514244"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Solucionar problemas de registro de dispositivo Windows no Microsoft Intune

Este artigo ajuda os Administradores do Intune a entender e solucionar problemas ao registrar dispositivos Windows no Intune.

## <a name="prerequisites"></a>Pré-requisitos
Antes de dar início à solução de problemas, é importante reunir algumas informações básicas. Essas informações podem ajudar você a entender melhor o problema e reduzir o tempo necessário para encontrar uma resolução.

Colete as seguintes informações sobre o problema:
- Uma licença válida do Intune foi atribuída ao usuário? Antes de registrarem os dispositivos, os usuários deverão ter a licença necessária atribuída.
- A atualização mais recente está instalada no dispositivo Windows? Alguns recursos do Intune funcionam apenas com a versão mais recente do Windows. Muitas correções de problemas conhecidos são disponibilizadas pelo Windows Update. Aplicar todas as atualizações mais recentes costuma corrigir problemas com o registro de dispositivos Windows. 
- Qual é a mensagem de erro exata?
- Onde você vê a mensagem de erro?
- Quando o problema começou? O registro funcionou em algum momento? 
- Qual plataforma (Android, iOS/iPadOS, Windows) apresenta o problema?
- Quantos usuários são afetados? Todos os usuários foram afetados ou apenas alguns deles?
- Quantos dispositivos foram afetados? Todos os dispositivos foram afetados ou apenas alguns deles?
- Qual é a autoridade de MDM?
- Como o registro está sendo realizado? Você está usando BYOD ("Traga seu próprio dispositivo") ou o DEP (Programa de registro de dispositivos) da Apple com perfis de registro?

## <a name="error-messages"></a>Mensagens de erro

### <a name="this-user-is-not-authorized-to-enroll"></a>Este usuário não está autorizado a se registrar.

Erro 0x801c003: "Este usuário não está autorizado a se registrar. Tente novamente ou entre em contato com o administrador do sistema com o código de erro (0x801c0003)."
Erro 80180003: "Ocorreu um problema. Este usuário não está autorizado a se registrar. Tente novamente ou entre em contato com o administrador do sistema com o código de erro 80180003."

**Causa:** uma das seguintes condições: 

- o usuário já registrou o número máximo de dispositivos permitidos no Intune.    
- o dispositivo está bloqueado pelas restrições do tipo de dispositivo.    
- o computador está executando o Windows 10 Home. No entanto, o registro no Intune e o ingresso no Azure AD só têm suporte no Windows 10 Pro e em edições superiores.

#### <a name="resolution"></a>Resolução
Há várias soluções possíveis para esse problema:

##### <a name="remove-devices-that-were-enrolled"></a>Remover dispositivos registrados
1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).    
2. Vá para **Usuários** > **Todos os Usuários**.    
3. Selecione a conta de usuário afetada e clique em **Dispositivos**.    
4. Selecione os dispositivos não utilizados ou indesejados e clique em **Excluir**. 

##### <a name="increase-the-device-enrollment-limit"></a>Aumentar o limite de registro de dispositivos

> [!NOTE]
> Esse método aumenta o limite de registro de dispositivo para todos os usuários, e não apenas para o usuário afetado.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vá para **Dispositivos** > **Restrições de registro** > **Padrão** (em **Restrições de limite de dispositivo**) > **Propriedades** > **Editar** (ao lado de **Limite de dispositivos**) > aumente o **Limite de dispositivos** (máximo de 15) > **Examinar + Salvar**.    
 

##### <a name="check-device-type-restrictions"></a>Verificar as restrições do tipo de dispositivo
1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) com uma conta de administrador global.
2. Vá para **Dispositivos** > **Restrições de registro** e, em seguida, selecione a restrição **Padrão** em **Restrições do Tipo de Dispositivo**.    
3. Selecione **Plataformas** e, em seguida, selecione **Permitir** para **Windows (MDM)** .

    > [!IMPORTANT]
    > Se a configuração já for **Permitir**, altere-a para **Bloquear**, salve e, em seguida, altere-a novamente para **Permitir** e salve novamente. Isso redefine a configuração de registro.

4. Aguarde cerca de 15 minutos e, em seguida, registre o dispositivo afetado novamente.    

##### <a name="upgrade-windows-10-home"></a>Atualizar para o Windows 10 Home
[Atualize o Windows 10 Home para o Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) ou para uma edição superior. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Este usuário não tem permissão para se registrar.

Erro 0x801c0003: "Este usuário não tem permissão para se registrar. Tente novamente ou entre em contato com o administrador do sistema com o código de erro 801c0003."

**Causa:** a configuração **Os usuários podem ingressar dispositivos no Azure AD** está definida como **Nenhum**. Isso impede que novos usuários ingressem dispositivos no Azure AD. Por isso, o registro do Intune falha.

#### <a name="resolution"></a>Resolução
1. Entre no [Portal do Azure](https://portal.azure.com/) como administrador.    
2. Vá para **Azure Active Directory** > **Dispositivos** > **Configurações do Dispositivo**.    
3. Defina **Os usuários podem ingressar no Azure AD com seus dispositivos** como **Todos**.    
4. Registrar novamente o dispositivo.   

### <a name="the-device-is-already-enrolled"></a>O dispositivo já está registrado.

Erro 8018000a: "Algo deu errado. O dispositivo já está registrado.  Entre em contato com o administrador do sistema com o código de erro 8018000a. "

**Causa:** uma destas condições é verdadeira:
- outro usuário já registrou o dispositivo no Intune ou o ingressou no Azure AD. Para determinar se esse é o caso, acesse **Configurações** > **Contas** > **Acesso Corporativo**. Procure uma mensagem semelhante à seguinte: "Outro usuário no sistema já está conectado com uma conta corporativa ou de estudante. Remova essa conexão corporativa ou de estudante e tente novamente. "    

#### <a name="resolution"></a>Resolução

Use um dos métodos a seguir para solucionar o problema:

##### <a name="remove-the-other-work-or-school-account"></a>Remover a outra conta corporativa ou de estudante
1. Saia do Windows e entre usando a outra conta que registrou ou ingressou o dispositivo.    
2. Vá para **Configurações** > **Contas** > **Acesso Corporativo** e, em seguida, remova a conta corporativa ou de estudante.
3. Saia do Windows e entre usando sua conta.    
4. Registre o dispositivo no Intune ou ingresse-o no Azure AD. 



### <a name="this-account-is-not-allowed-on-this-phone"></a>Esta conta não tem permissão neste telefone.

Erro: "Esta conta não tem permissão neste telefone. Verifique se as informações fornecidas estão corretas e tente novamente ou solicite suporte de sua empresa. "

**Causa:** o usuário que tentou registrar o dispositivo não tem uma licença válida do Intune.

#### <a name="resolution"></a>Resolução
Atribua uma licença válida do Intune ao usuário e, em seguida, registre o dispositivo.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>Parece que o ponto de extremidade de Termos de Uso do MDM não está configurado corretamente.

**Causa:** uma destas condições é verdadeira: 
 - você usa o MDM (gerenciamento de dispositivo móvel) para o Office 365 e o Intune no locatário, e o usuário que tentou registrar o dispositivo não tem uma licença válida do Intune nem uma licença do Office 365.     
- Os termos e condições do MDM no Azure AD estão em branco ou não contêm a URL correta.    

#### <a name="resolution"></a>Resolução

Para solucionar esse problema, use um dos seguintes métodos: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Atribuir uma licença válida ao usuário
Vá para o [Centro de Administração do Microsoft 365](https://portal.office.com/adminportal/home) e atribua uma licença do Intune ou do Office 365 ao usuário.

##### <a name="correct-the-mdm-terms-of-use-url"></a>Corrigir a URL dos termos de uso do MDM
  1. Entre no [portal do Azure](https://portal.azure.com/) e selecione **Azure Active Directory**.    
  2. Selecione **Mobilidade (MDM e MAM)** e, em seguida, clique em **Microsoft Intune**.    
  3. Selecione **Restaurar as URLs padrão do MDM** e verifique se a **URL dos termos de uso do MDM** está definida como **https://portal.manage.microsoft.com/TermsofUse.aspx** .    
  4. Selecione **Salvar**.    


### <a name="something-went-wrong"></a>Algo deu errado.

Erro 80180026: "Ocorreu um problema. Confirme se você está usando as informações de entrada corretas e se sua organização usa esse recurso. Tente novamente ou entre em contato com o administrador do sistema com o código de erro 80180026."

**Causa:** esse erro pode ocorrer quando você tenta ingressar um computador com Windows 10 no Azure AD e as duas condições a seguir são verdadeiras: 
- O registro automático do MDM está habilitado no Azure.    
- O cliente de PC do Intune (agente de PC do Intune) está instalado no computador com Windows 10.

#### <a name="resolution"></a>Resolução
Use um dos métodos a seguir para resolver o problema:

##### <a name="disable-mdm-automatic-enrollment-in-azure"></a>Desabilitar o registro automático do MDM no Azure.
1. Entre no [portal do Azure](https://portal.azure.com/).    
2. Vá para **Azure Active Directory** > **Mobilidade (MDM e MAM)**  > **Microsoft Intune**.    
3. Defina o **Escopo do usuário do MDM** como **Nenhum** e, em seguida, clique em **Salvar**.    
     
##### <a name="uninstall"></a>Desinstalar
Desinstale o agente cliente de PC do Intune do computador.    

### <a name="the-software-cannot-be-installed"></a>Não é possível instalar o software.

Erro: "Não é possível instalar o software, 0x80cf4017."

**Causa:** o software cliente está desatualizado.

#### <a name="resolution"></a>Resolução
1. Entre em [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Vá para **Administrador** > **Download de Software Cliente** e, em seguida, clique em **Download de Software Cliente**.    
3. Salve o pacote de instalação e, em seguida, instale o software cliente. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>O certificado de conta não é válido e pode ter expirado.

Erro: "O certificado de conta não é válido e pode ter expirado, 0x80cf4017."

**Causa:** o software cliente está desatualizado.

#### <a name="resolution"></a>Resolução
1. Entre em [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Vá para **Administrador** > **Download de Software Cliente** e, em seguida, clique em **Download de Software Cliente**.    
3. Salve o pacote de instalação e, em seguida, instale o software cliente.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Sua organização não dá suporte a esta versão do Windows. 

Erro: "Houve um problema. Sua organização não dá suporte a esta versão do Windows.  (0x80180014)"

**Causa:** o registro de MDM do Windows está desabilitado em seu locatário do Intune.

#### <a name="resolution"></a>Resolução
Para corrigir esse problema em um ambiente autônomo do Intune, siga estas etapas: 
 
1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Restrições de registro** > escolha uma restrição de tipo de dispositivo.    
2. Escolha **Propriedades** > **Editar** (ao lado de **Configurações da plataforma**) > **Permitir** para **Windows (MDM)** .    
3. Clique em **Avaliar + salvar**.    

### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Ocorreu uma falha na instalação durante o registro em massa.

**Causa:** as contas de usuário do Azure AD no pacote de conta (Package_GUID) do respectivo pacote de provisionamento não têm permissão para ingressar dispositivos no Azure AD. Essas contas do Azure AD são criadas automaticamente quando você configura um pacote de provisionamento com o WCD (Windows Configuration Designer) ou com o aplicativo Configurar computadores escolares, e são usadas para ingressar os dispositivos no Azure AD.

#### <a name="resolution"></a>Resolução
1. Entre no [Portal do Azure](https://portal.azure.com/) como administrador.    
2. Vá para **Azure Active Directory > Dispositivos > Configurações do Dispositivo**.    
3. Defina **Os usuários podem ingressar no Azure AD com seus dispositivos** como **Todos** ou **Selecionados**.

   Se escolher **Selecionados**, clique em **Selecionados** e, em seguida, clique em **Adicionar Membros** para adicionar todos os usuários que podem ingressar dispositivos no Azure AD. Verifique se todas as contas do Azure AD para o pacote de provisionamento foram adicionadas.
 
Para obter mais informações sobre como criar um pacote de provisionamento para o Windows Configuration Designer, confira [Criar um pacote de provisionamento para o Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package).

Para obter mais informações sobre o aplicativo Configurar computadores escolares, confira [Usar o aplicativo Configurar computadores escolares](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app).


### <a name="auto-mdm-enroll-failed"></a>Registro de MDM automático: falha 

Ao tentar registrar um dispositivo Windows 10 automaticamente usando a Política de Grupo, você enfrenta os seguintes problemas: 
- No Agendador de Tarefas, em **Microsoft** > **Windows** > **EnterpriseMgmt**, o resultado da execução mais recente da tarefa **Agendamento criado pelo cliente de registro para registrar-se automaticamente no MDM no AAD** é o seguinte: **Evento 76 de Registro de MDM Automático: falha (código de erro Win32 desconhecido: 0x8018002b)**       
- No Visualizador de Eventos, o evento a seguir é registrado em **Logs de Aplicativos e Serviços/Microsoft/Windows/DeviceManagement-Enterprise-Diagnostics-Provider/Admin**:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Causa:** uma destas condições é verdadeira: 
- o UPN contém um domínio não verificado ou não roteável, como .local (por exemplo, joe@contoso.local).    
- o **Escopo do usuário do MDM** está definido como **Nenhum**. 

#### <a name="resolution"></a>Resolução
Se o UPN contiver um domínio não verificado ou não roteável, siga estas etapas: 

1. No servidor em que o AD DS (Active Directory Domain Services) é executado, abra **Usuários e Computadores do Active Directory** digitando **dsa.msc** na caixa de diálogo **Executar** e, em seguida, clique em **OK**.    
2. Clique em **Usuários** em seu domínio e, em seguida, faça o seguinte:  
    - Se houver apenas um usuário afetado, clique nele com o botão direito do mouse e clique em **Propriedades**. Na guia **Conta**, na lista suspensa de sufixos de UPN em **Nome de logon do usuário**, selecione um sufixo de UPN válido, como contoso.com, e clique em **OK**.    
    - Se houver vários usuários afetados, selecione os usuários e, no menu **Ação**, clique em **Propriedades**. Na guia **Conta**, marque a caixa de seleção **Sufixo do UPN**, selecione um sufixo de UPN válido, como contoso.com, na lista suspensa e clique em **OK**.
3. Aguarde a próxima sincronização ou force uma Sincronização Delta no Servidor de Sincronização executando os seguintes comandos em um prompt do PowerShell com privilégios elevados:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

Se o **Escopo do usuário do MDM** estiver definido como **Nenhum**, siga estas etapas: 
 
1. Entre no [portal do Azure](https://portal.azure.com/) e selecione **Azure Active Directory**.
2. Selecione **Mobilidade (MDM e MAM)** e, em seguida, selecione **Microsoft Intune**.    
3. Defina o **Escopo do usuário do MDM** como **Todos**. Ou defina o **Escopo do usuário do MDM** como **Alguns** e selecione os Grupos que podem registrar automaticamente seus dispositivos Windows 10.    
4. Defina o **Escopo do usuário do MAM** como **Nenhum**.


### <a name="an-error-occurred-while-creating-autopilot-profile"></a>Ocorreu um erro ao criar o perfil do Autopilot.

**Causa:** o formato de nomenclatura especificado para o modelo do nome do dispositivo não atende aos requisitos. Por exemplo, você usou letras minúsculas para a macro serial, como %serial% em vez de %SERIAL%.

#### <a name="resolution"></a>Resolução

O formato de nomenclatura deve atender aos seguintes requisitos:

- Crie um nome exclusivo para seus dispositivos. Os nomes precisam ter 15 caracteres ou menos e podem conter letras (a-z, A-Z), números (0-9) e hifens (‐).
- Os nomes não podem conter apenas números.
- Os nomes não podem conter espaços em branco.
- Use a macro %SERIAL% para adicionar um número de série específico do hardware. Ou use a macro %RAND:<# de dígitos>% para adicionar uma cadeia de caracteres numéricos aleatória, que conterá <# de dígitos> dígitos. Por exemplo, MYPC-%RAND:6% gera um nome como MYPC-123456.

### <a name="something-went-wrong-oobeidps"></a>Algo deu errado. OOBEIDPS.

**Causa:** esse problema ocorre quando um proxy, firewall ou outro dispositivo de rede está bloqueando o acesso ao IdP (provedor de identidade).

#### <a name="resolution"></a>Resolução
Verifique se o acesso necessário do Autopilot a serviços baseados na Internet não está bloqueado. Para obter mais informações, confira [Requisitos de rede do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements-network).


### <a name="registering-your-device-for-mobile-management-failed3-0x801c03ea"></a>Registrando seu dispositivo para o gerenciamento móvel (Falha:3, 0x801C03EA).

**Causa:** o dispositivo tem um chip do TPM com suporte para a versão 2.0, mas ainda não foi atualizado para essa versão.

#### <a name="resolution"></a>Resolução
Atualize o chip do TPM para a versão 2.0.

Se o problema persistir, verifique se o mesmo dispositivo faz parte de dois grupos atribuídos, com cada grupo atribuído a um perfil do Autopilot diferente. Se o dispositivo estiver em dois grupos, determine qual perfil do Autopilot deve ser aplicado a ele e, em seguida, remova a atribuição do outro perfil.

Para obter mais informações sobre como implantar um dispositivo Windows no modo de quiosque com o Autopilot, confira [Implantando um quiosque usando o Windows Autopilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/).


### <a name="securing-your-hardware-failed-0x800705b4"></a>Protegendo seu hardware (Falha: 0x800705b4).

Erro 800705b4: 
```
Securing your hardware (Failed: 0x800705b4)
Joining your organization's network (Previous step failed)
Registering your device for mobile management (Previous step failed)
```

**Causa:** o dispositivo Windows de destino não atende a um dos seguintes requisitos:

- o dispositivo precisa ter um chip do TPM 2.0 físico. Dispositivos com TPMs virtuais (por exemplo, VMs do Hyper-V) ou chips do TPM 1.2 não funcionam com o modo de autoimplantação.
- o dispositivo precisa estar executando uma das seguintes versões do Windows:
    - Windows 10 build 1703 ou uma versão posterior.
    - Se o Hybrid Azure AD Join for usado, o Windows 10 build 1809 ou uma versão posterior.


#### <a name="resolution"></a>Resolução
Verifique se o dispositivo de destino atende aos dois requisitos descritos na seção **Causa**.

Para obter mais informações sobre como implantar um dispositivo Windows no modo de quiosque com o Autopilot, confira [Implantando um quiosque usando o Windows Autopilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/).


### <a name="something-went-wrong-error-code-80070774"></a>Algo deu errado. Código de erro 80070774.

Erro 0x80070774: Algo deu errado. Confirme se você está usando as informações de entrada corretas e se sua organização usa esse recurso. Tente novamente ou entre em contato com o administrador do sistema com o código de erro 80070774.

Normalmente, esse problema ocorre antes que o dispositivo seja reiniciado em um cenário com o Hybrid Azure AD Autopilot, quando o dispositivo atinge o tempo limite na tela de Entrada inicial. Isso significa que o controlador de domínio não pode ser encontrado ou alcançado com êxito por problemas de conectividade. Ou que o dispositivo entrou em um estado que não pode ingressar no domínio.

**Causa:** a causa mais comum é que o Hybrid Azure AD Join esteja sendo usado e o recurso Atribuir usuário esteja configurado no perfil do Autopilot. O uso do recurso Atribuir usuário executa um ingresso do Azure AD no dispositivo durante a tela de entrada inicial, o que coloca o dispositivo em um estado no qual não pode ingressar em seu domínio local. Portanto, o recurso Atribuir usuário deve ser usado somente em cenários padrão do Azure AD Join Autopilot.  O recurso não deve ser usado em cenários do Hybrid Azure AD Join.

#### <a name="resolution"></a>Resolução

1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Windows** > **Dispositivos Windows**.
2. Selecione o dispositivo que está apresentando o problema e clique nas reticências (…) na extremidade direita.
3. Selecione **Cancelar atribuição do usuário** e aguarde a conclusão do processo.
4. Verifique se o perfil do Hybrid Azure AD Autopilot foi atribuído antes de tentar o OOBE novamente.

#### <a name="second-resolution"></a>Segunda resolução
Se o problema persistir, no servidor que hospeda o Conector do Intune de Ingresso no Domínio Offline, verifique se a ID do Evento 30312 está registrada no log do Serviço de Conector do ODJ. O Evento 30312 é semelhante ao seguinte:

```
Log Name:      ODJ Connector Service
Source:        ODJ Connector Service Source
Event ID:      30132
Level:         Error
Description:
{
          "Metric":{
                   "Dimensions":{
                             "RequestId":"<RequestId>",
                             "DeviceId":"<DeviceId>",
                             "DomainName":"contoso.com",
                             "ErrorCode":"5",
                             "RetryCount":"1",
                              "ErrorDescription":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation",
                              "InstanceId":"<InstanceId>",
                              "DiagnosticCode":"0x00000800",
                              "DiagnosticText":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation [Exception Message: \"DiagnosticException: 0x00000800. Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation\"] [Exception Message: \"Failed to call NetProvisionComputerAccount machineName=<ComputerName>\"]"
                   },
                   "Name":"RequestOfflineDomainJoinBlob_Failure",
                   "Value":0
          }
}
```

Normalmente, esse problema é causado pela delegação incorreta de permissões à unidade organizacional em que os dispositivos do Windows Autopilot são criados. Para obter mais informações, confira [Aumentar o limite de conta de computador na Unidade Organizacional](windows-autopilot-hybrid.md#increase-the-computer-account-limit-in-the-organizational-unit).

1. Abra **Usuários e Computadores do Active Directory** (DSA.msc).
2. Clique com o botão direito do mouse na unidade organizacional que você usará para criar computadores ingressados no Azure AD híbrido > **Delegar Controle**.
3. No assistente **Delegação de Controle**, escolha **Avançar** > **Adicionar** > **Tipos de Objeto**.
4. No painel **Tipos de Objeto**, marque a caixa de seleção **Computadores** > **OK**.
5. No painel **Selecionar Usuários**, **Computadores** ou **Grupos**, na caixa **Inserir nomes de objeto para selecionar**, insira o nome do computador em que o conector está instalado.
6. Selecione **Verificar Nomes** para validar sua entrada > **OK** > **Avançar**.
7. Selecione **Criar uma tarefa personalizada para delegar** > **Avançar**.
8. Selecione a caixa de seleção **Somente os seguintes objetos na pasta** e, em seguida, selecione as caixas de seleção **Objetos de computador**, **Criar objetos selecionados nesta pasta** e **Excluir objetos selecionados nesta pasta**.
9. Selecione **Avançar**.
10. Sob **Permissões**, selecione a caixa de seleção **Controle total**. Essa ação selecionará todas as outras opções.
11. Selecione **Avançar** > **Concluir**.

### <a name="the-enrollment-status-page-times-out-before-the-sign-in-screen"></a>A Página de Status do Registro atinge o tempo limite antes da tela de entrada

**Causa:** esse problema pode ocorrer quando todas as condições a seguir são verdadeiras:
- você está usando a Página de Status do Registro para acompanhar aplicativos da Microsoft Store para Empresas.
- você tem uma política de Acesso Condicional do Azure AD que usa o controle "exigir que um dispositivo seja marcado como compatível".
- A política se aplica a todos os aplicativos de nuvem e ao Windows.

#### <a name="resolution"></a>Solução:
Tente um destes procedimentos:
- direcione suas políticas de conformidade do Intune aos dispositivos. Certifique-se de que a conformidade seja determinada antes que o usuário faça logon.
- use o licenciamento offline para aplicativos da loja. Dessa forma, o cliente do Windows não precisa verificar na Microsoft Store antes de determinar a conformidade do dispositivo.



## <a name="next-steps"></a>Próximas etapas

- [Solucionar problemas de registro de dispositivo no Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Faça uma pergunta no fórum do Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Confira o blog da equipe de suporte do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Confira o blog de segurança e mobilidade corporativa da Microsoft](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Obter suporte para o Microsoft Intune](../fundamentals/get-support.md)
- [Localizar erros de registro de cogerenciamento](https://docs.microsoft.com/configmgr/comanage/how-to-monitor#enrollment-errors)
