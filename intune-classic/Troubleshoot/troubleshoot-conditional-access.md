---
title: Solucionar problemas de acesso condicional
description: "O que fazer quando os usuários não obtêm acesso aos recursos por meio de acesso condicional do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 21053cd7ce930bd11625807f7fdda3ebbdd953f3
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="troubleshoot-conditional-access"></a>Solucionar problemas de acesso condicional

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Normalmente, um usuário está tentando acessar o email ou o SharePoint e recebe uma solicitação para registrar. Essa solicitação levará o usuário para o portal da empresa.

Este tópico descreve o que fazer quando os usuários não obtêm acesso aos recursos por meio de acesso condicional do Intune.


## <a name="the-basics-for-success-in-conditional-access"></a>Os conceitos básicos para o sucesso no acesso condicional

Para que o acesso condicional funcione, são necessárias as seguintes condições:

-   O dispositivo deve ser gerenciado pelo Intune.
-   O dispositivo deve estar registrado no AAD (Azure Active Directory). Em circunstâncias normais, esse registro ocorre automaticamente durante o registro do Intune.
-   O dispositivo deve ser compatível com suas políticas de conformidade do Intune, tanto para o dispositivo quanto para o usuário do dispositivo.  Se não houver nenhuma política de conformidade, o registro do Intune será suficiente.
-   O Exchange ActiveSync deverá ser ativado no dispositivo se o usuário estiver recuperando mensagens por meio do cliente de email nativo do dispositivo em vez de por meio do Outlook.     Isso ocorre automaticamente para dispositivos iOS, Windows Phone e Android/KNOX Standard.
-   O Intune Exchange Connector deve estar configurado corretamente. Consulte [Troubleshooting the Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) (Solução de problemas do Exchange Connector no Microsoft Intune) para obter mais informações.

Essas condições podem ser exibidas para cada dispositivo no Portal de gerenciamento do Azure e no relatório de inventário de dispositivo.

## <a name="enrollment-issues"></a>Problemas de registro

 -  O dispositivo não está registrado, portanto o registro resolverá o problema.
 -  O usuário registrou o dispositivo, mas houve falha no ingresso no local de trabalho. O usuário deve atualizar o registro por meio do portal da empresa.

## <a name="compliance-issues"></a>Problemas de conformidade

 -  O dispositivo não é compatível com a política do Intune. Problemas comuns são requisitos de senha e criptografia. O usuário será redirecionado para o portal da empresa, em que ele pode configurar seu dispositivo para que seja compatível.
 -  Pode levar algum tempo para que as informações de conformidade sejam registradas para um dispositivo. Aguarde alguns minutos e tente novamente.
 -  Para dispositivos iOS:
     -   Um perfil de email existente criado pelo usuário bloqueia a implantação de um perfil criado pelo administrador do Intune. Isso é um problema comum, pois usuários do iOS normalmente vão criar um perfil de email e, depois, se registrar. O portal da empresa informará ao usuário que ele não é compatível devido ao seu perfil de email configurado manualmente e solicitará que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser implantado. Para evitar o problema, instrua os usuários a registrar sem instalar um perfil de email e permitir que o Intune implante o perfil.
     -   Um dispositivo iOS pode ficar parado em um estado de verificação de conformidade, impedindo que o usuário inicie outro check-in. Reiniciar o portal da empresa pode corrigir isso, e o estado da conformidade refletirá o estado do dispositivo no Intune. Depois que todos os dados forem coletados de uma sincronização de dispositivo, a verificação de conformidade será rápida, levando em média menos da metade de uma segundo.

        Normalmente, o motivo para os dispositivos permanecerem nesse estado é porque eles estão com problemas de conexão com o serviço ou a sincronização está levando muito tempo.  Se o problema persistir em diferentes configurações de rede (celular, Wi-Fi, VPN), após várias reinicializações do dispositivo e após a verificação de que o SSP está atualizado no dispositivo, entre em contato com o Suporte da Microsoft conforme descrito em [Como obter suporte para o Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

 - Para dispositivos Android:
    - Certos dispositivos Android parecem ser criptografados, mas o aplicativo de Portal da Empresa reconhece esses dispositivos como não criptografados. 
    
        -   Os dispositivos nesse estado exigem que o usuário defina uma senha de inicialização segura. O usuário verá uma notificação do dispositivo no aplicativo Portal da Empresa solicitando uma senha de inicialização para o dispositivo. Depois de tocar na notificação do dispositivo e confirmar o PIN existente ou a senha, escolha a opção **Exigir PIN para iniciar o dispositivo** na tela **Proteger inicialização**. Em seguida, toque no botão **Verificar Conformidade** do dispositivo no aplicativo Portal da Empresa. Agora o dispositivo deve ser detectado como criptografado.
    
        -   Alguns fabricantes de dispositivos criptografam seus dispositivos usando um PIN padrão em vez do PIN secreto definido pelo usuário. O Intune reconhece a criptografia usando o PIN padrão como inseguro, pois esse método de criptografia pode colocar os dados no dispositivo em risco, podendo ser acessados por usuários mal-intencionados com acesso físico ao dispositivo. Se esse for o problema, considere o uso de [políticas de proteção do aplicativo](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).

## <a name="policy-issues"></a>Problemas de política

Quando você cria uma política de conformidade e a vincula a uma política de email, ambas as políticas precisam ser implantadas para o mesmo usuário. Portanto, tenha cuidado ao planejar quais políticas são implantadas em quais grupos. Os usuários que têm apenas uma política aplicada têm uma probabilidade de descobrir que seus dispositivos não são compatíveis.


## <a name="exchange-activesync-issues"></a>Problemas com o Exchange ActiveSync

### <a name="compliant-android-device-gets-quarantine-notice"></a>Um dispositivo Android compatível recebe aviso de quarentena
- Um dispositivo Android registrado e compatível ainda pode receber um aviso de quarentena ao tentar acessar recursos corporativos. Antes de escolher o link que diz **Começar**, o usuário deve verificar se o portal da empresa não estava aberto quando ele tentou acessar os recursos. Os usuários devem fechar o portal da empresa, tente novamente para acessar os recursos e, em seguida, escolher o link **Começar**.

### <a name="retired-device-continues-to-have-access"></a>Um dispositivo desativado continua tendo acesso.
- Durante a utilização do Exchange Online, um dispositivo desativado pode continuar tendo acesso por várias horas após a desativação. Isso ocorre porque o Exchange armazena em cache os direitos de acesso por 6 horas. Considere outros meios de proteção de dados em dispositivos desativados neste cenário.

### <a name="device-is-compliant-and-registered-with-aad-but-still-blocked"></a>O dispositivo é compatível e registrado com o AAD, mas ainda é bloqueado
- Às vezes, o provisionamento da EASID (ID do Exchange ActiveSync) para o AAD é atrasado. Uma causa comum desse problema é a limitação, então, aguarde alguns minutos e tente novamente.

### <a name="device-blocked"></a>Dispositivo bloqueado

Um dispositivo pode ser bloqueado do Acesso condicional sem receber um email de ativação.

- Há uma regra padrão do Exchange que coloca os dispositivos em quarentena ou os bloqueia? Se uma regra padrão bloquear ou colocar os dispositivos em quarentena, os dispositivos não poderão receber o email de ativação do Exchange Connector. Isso ocorre por design.
- A conta de notificação está configurada corretamente conforme descrito na configuração básica?
- O dispositivo está presente no console de administração do Intune como um dispositivo do Exchange ActiveSync? Se não, é provável que a descoberta do dispositivo esteja falhando, provavelmente devido a um problema de sincronização do Exchange Connector. Consulte O dispositivo do Exchange ActiveSync não é descoberto no Exchange.
- Verifique os logs do Exchange Connector quanto à atividade EnviarEmail e verifique se há erros. Um exemplo de comando a ser procurado é EnviarEmail da conta de notificação para EmailUsuário.
- Antes de bloquear o dispositivo, o Exchange Connector envia o email de ativação. Se o dispositivo estiver offline, ele poderá não receber o email de ativação. Verifique se o cliente de email do dispositivo tem recuperação de email usando Push em vez de Pull, pois isso também pode fazer com que o usuário perca o email. Mude para Pull e veja se o dispositivo recebe o email.

## <a name="non-compliant-device-not-blocked"></a>Um dispositivo incompatível não é bloqueado

Se você encontrar um dispositivo que não é compatível, mas continua tendo acesso, execute as etapas a seguir.

- Analise os grupos de Destino e Exclusão. Se um usuário não estiver no grupo de destino correto ou estiver no grupo de exclusão, ele não será bloqueado. Somente os dispositivos de usuários em um grupo de Destino são verificados quanto à conformidade.
- Certifique-se de que o dispositivo esteja sendo descoberto. O Exchange Connector está apontando para uma CAS do Exchange 2010 enquanto o usuário está em um servidor Exchange 2013? Nesse caso, se a regra padrão do Exchange for Permitir, mesmo se o usuário estiver no grupo de Destino, o Intune não poderá estar ciente da conexão do dispositivo com o Exchange.
- Verifique a existência/estado de acesso do dispositivo no Exchange:
    - Use este cmdlet do PowerShell para obter uma lista de todos os dispositivos móveis para uma caixa de correio: "Get-ActiveSyncDeviceStatistics -mailbox mbx". Caso o dispositivo não esteja listado, ele não está acessando o Exchange.
    - Se o dispositivo estiver listado, use cmdlet Get-CASmailbox -identity:’upn’ | fl para obter informações detalhadas sobre seu estado de acesso e fornecer essas informações ao Suporte da Microsoft.

## <a name="before-you-open-a-support-ticket"></a>Antes de abrir um tíquete de suporte
Caso esses procedimentos de solução de problemas não resolvam o problema, há informações que o Suporte da Microsoft pode solicitar, como logs de caixa de correio do OWA ou logs do Exchange Connector.

### <a name="collecting-owa-mailbox-logs"></a>Coletando logs de caixa de correio do OWA

1. Faça logon por meio do OWA e escolha o símbolo de configurações (engrenagem) ao lado de seu nome no canto superior direito.
2. Escolha **Opções**
3. Escolha **Telefone** (talvez seja **Dispositivos Móveis**) na coluna à esquerda.
4. No menu superior, escolha **Dispositivos Móveis**.
5. Escolha seu dispositivo na lista e, em seguida, escolha **Iniciar Registro**.
6. Quando solicitado, escolha **Sim** na caixa de diálogo pop-up.
7. Execute a ação que causou o problema, para que você possa reproduzi-lo.
8. Aguarde por 1 a 2 minutos e volte para a lista telefônica no OWA. Verifique se o seu telefone está selecionado na lista e, no menu superior, escolha **Recuperar Log**.
9. Você deve ter recebido um email de si mesmo com um anexo. Quando você abrir um tíquete de suporte, forneça o conteúdo do email ao Suporte da Microsoft.

### <a name="exchange-connector-logs"></a>Logs do Exchange Connector

#### <a name="general-log-information"></a>Informações gerais sobre logs
Para exibir logs do Exchange Connector, use a [Ferramenta do Visualizador de Rastreamento do Servidor] (ferramenta do visualizador de rastreamento do servidor (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx'). Essa ferramenta requer que você baixe o SDK do Windows Server.

>[!NOTE]
>Os logs estão localizados em C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs. Os logs estão contidos em uma série de 30 arquivos de log que começa com *Connector0.log* e para em *Connector29.log*. Os logs se sobrepõem uns aos outros após 10 MB de dados serem acumulados em um log. Depois de chegarem a Connector29, os logs recomeçam em Connector0, substituindo os arquivos de log anteriores.

#### <a name="locating-sync-logs"></a>Localização de logs de sincronização

-    Localize uma sincronização completa nos logs pesquisando **full sync**. O início de uma sincronização completa será marcado por este texto:

    “Handling command: Getting the mobile device list without a time filter (full sync) for <number> users”

    O final do log de uma sincronização completa será semelhante a:

    Getting the mobile device list without a time filter (full sync) for 4 users completed successfully. Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','

-   Localize uma sincronização rápida (delta) nos logs pesquisando **quick sync**.

##### <a name="exceptions-in-get-next-command"></a>Exceções no comando Get next
Verifique os logs do Exchange Connector quanto a exceções no comando **Get next** e forneça-as ao Suporte da Microsoft.

#### <a name="verbose-logging"></a>Log detalhado

Para habilitar o log detalhado:

1.  Abra o arquivo de configuração de rastreamento do Exchange Connector. O arquivo está localizado em: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.  Localize TraceSourceLine com a seguinte chave: OnPremisesExchangeConnectorService
3.  Alterar o valor do nó **SourceLevel** de **Warning ActivityTracing** (o padrão) para **Verbose ActivityTracing**, conforme mostrado abaixo.

    <TraceSourceLine> <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key> <Value xsi:type="TraceSource"> <SourceLevel>All</SourceLevel> <Listeners> <Listener> <ListenerType>CircularTraceListener</ListenerType> <SourceLevel>Verbose ActivityTracing</SourceLevel> <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes> <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName> <FileQuota>30</FileQuota> </Listener> </Listeners> </Value>
    </TraceSourceLine>



### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).
