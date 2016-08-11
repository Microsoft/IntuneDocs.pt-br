---
title: "Configurações de política do Windows 10 | Microsoft Intune"
description: "Use as configurações de política listadas neste tópico para ajudá-lo a definir as configurações internas e personalizadas para dispositivos Windows 10 Mobile e Windows 10 Desktop."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7ef205aece89667ea84b9b73e42e71fc540fa257
ms.openlocfilehash: cbfd2da544814dc93a818a1ca5bd0496a268634b


---

# Configurações de política do Windows 10 no Microsoft Intune

Use as configurações de política listadas neste tópico para ajudá-lo a definir as configurações internas e personalizadas para dispositivos Windows 10 Mobile e Windows 10 Desktop.

> [!IMPORTANT]
> Você pode gerenciar computadores Windows 10 de duas maneiras: registrando-os ou instalando o software cliente de computador do Intune. Cada método oferece funcionalidades diferentes (consulte [Escolha como gerenciar dispositivos](/intune/get-started/choose-how-to-manage-devices) para obter mais informações).
> Ao gerenciar seus computadores Windows 10 com o software cliente de computador do Intune, você não pode usar as políticas e configurações detalhadas neste tópico. Para aplicar essas configurações, os dispositivos Windows 10 devem ser registrados com o Intune.

## Definições de política de configuração geral

Use a **política de configuração geral** do Microsoft Intune para Windows 10 para definir configurações gerais para Windows 10 Desktop e dispositivos Windows 10 Mobile registrados. 


### Senha

|Nome da configuração|Detalhes|
|----------------|----------------------|
|**Exigir uma senha para desbloquear dispositivos**|Requer uma senha nos dispositivos com suporte.|
|**Tipo de senha necessária**|Especifica o tipo de senha que será necessário, apenas com caracteres numéricos ou alfanuméricos|
|**Tipo de senha necessária** - **Número mínimo de conjuntos de caracteres**|Há quatro conjuntos de caracteres: minúsculas, maiúsculas, símbolos e números. Essa configuração especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha.|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres que na senha do dispositivo deve conter.<br>(Somente Windows 10 Mobile)|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Apaga o dispositivo se houver falha neste número de tentativas de logon.|
|**Minutos de inatividade antes que a tela se apague**|Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.|
|**Expiração da senha (dias)**|Especifica o período após o qual a senha do dispositivo deve ser alterada.|
|**Lembrar de histórico de senha**|Especifica se você deseja impedir que o usuário final crie senhas usadas anteriormente.|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|
|**Exigir senha quando o dispositivo retorna de um estado ocioso**|Se habilitado, o usuário deverá inserir uma senha para desbloquear o dispositivo de um estado ocioso.<br>(Somente Windows 10 Mobile)|

### Criptografia

|Nome da configuração|Detalhes|
|----------------|----------------------|
|**Exigir criptografia no dispositivo móvel**|Habilita a criptografia em dispositivos de destino.<br>(Somente Windows 10 Mobile)|

### System (sistema)

|Nome da configuração|Detalhes|
|----------------|----------------------|
|**Permitir captura de tela**|Permite que o usuário capture a tela do dispositivo como uma imagem.<br>(Somente Windows 10 Mobile)|
|**Permitir cancelamento de registro manual**|Permite que o usuário exclua manualmente a conta da empresa do dispositivo.|
|**Permitir instalação de certificado raiz manual**|Especifica se o usuário pode instalar manualmente os certificados raiz.<br>(Somente Windows 10 Mobile)|
|**Permitir que o diagnóstico e os dados de uso sejam enviados à Microsoft**|Determina a quantidade de dados de diagnóstico e de uso que são enviadas dos dispositivos para a Microsoft.<br><br>**Não** - Nenhum dado é enviado para a Microsoft<br>**Básico** - O dispositivo envia apenas informações limitadas para a Microsoft<br>**Avançado** - Envia dados de diagnóstico avançados para a Microsoft<br>**Completo (recomendado)** - Envia os mesmos dados que **Avançado**, além de dados adicionais sobre o estado do dispositivo|


### Conta e sincronização

|Nome da configuração|Detalhes|
|----------------|----------------------|---------------------|
|**Permitir conta da Microsoft**|Permite que o usuário associe uma conta da Microsoft ao dispositivo.|
|**Permitir a adição de contas não Microsoft manualmente**|Permite que o usuário adicione contas de email a dispositivos que não estão associados uma conta da Microsoft.|
|**Permitir a sincronização de configurações de contas da Microsoft**|Permitir usar configurações de dispositivo e aplicativo associadas a uma conta da Microsoft para sincronização entre dispositivos.|

### Microsoft Edge

|Nome da configuração|Detalhes|
|----------------|----------------------|
|**Permitir navegador da web**|Permitir o uso do navegador da Web Microsoft Edge no dispositivo.<br>(Somente Windows 10 Mobile)|
|**Permitir sugestões de pesquisa na barra de endereços**|Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.|
|**Permitir envio de tráfego de intranet no Internet Explorer**|Permite que os usuários abram sites da intranet no Internet Explorer.<br>(Somente Windows 10 Desktop)|
|**Permitir Não Rastrear**|Configura o navegador Microsoft Edge para enviar cabeçalhos Não Rastrear para sites visitados pelos usuários.|
|**Habilitar SmartScreen**|Habilita a configuração do navegador SmartScreen nos dispositivos.|
|**Permitir script ativo**|Permite que scripts, como JavaScript, sejam executados no navegador Microsoft Edge.|
|**Permitir pop-ups**|Habilita ou desabilita o bloqueador de pop-ups do navegador.<br>(Somente Windows 10 Desktop)|
|**Permitir cookies**|Habilita ou desabilita cookies.|
|**Permitir Preenchimento Automático**|Permite que os usuários possam alterar as configurações de preenchimento automático no navegador.<br>(Somente Windows 10 Desktop)|
|**Permitir Gerenciador de Senhas**|Habilitar ou desabilitar o recurso de Gerenciamento de Senha do Microsoft Edge.|
|**Local do Enterprise Mode Site List**|Especifica onde encontrar a lista de sites que será aberta no modo Empresarial. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop)|

### Aplicativos

|Nome da configuração|Detalhes|
|----------------|----------------------|---------------------|
|**Permitir loja de aplicativo**|Permite ao usuário acessar a loja de aplicativos no dispositivo.<br>(Somente Windows 10 Mobile)|



### Celular

|Nome da configuração|Detalhes|
|----------------|----------------------|---------------------|
|**Permitir roaming de Dados**|Permita o roaming entre redes durante o acesso de dados.|
|**Permitir VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.|
|**Permitir roaming de VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando estiver em roaming ou em uma rede celular.|

### Hardware

|Nome da configuração|Detalhes|
|----------------|----------------------|
|**Permitir câmera**|Especifica se a câmera do dispositivo pode ser usada.|
|**Permitir armazenamento removível**|Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo.|
|**Permitir Wi-Fi**|Permite usar a funcionalidade Wi-Fi dos dispositivos.<br>(Somente Windows 10 Mobile)|
|**Permitir compartilhamento de Internet**|Permitir usar o compartilhamento de conexão com a Internet no dispositivo móvel.|
|**Permitir configuração manual de Wi-Fi**|Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se podem usar somente as conexões configuradas por um perfil Wi-Fi.<br>(Somente Windows 10 Mobile)|
|**Permitir conexão automática para liberar pontos de acesso Wi-Fi**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.|
|**Permitir localização geográfica**|Especifica se o dispositivo pode usar informações de serviços de localização.|
|**Permitir NFC**|Permite que o dispositivo use sua funcionalidade de Comunicação a Curta Distância.|
|**Permitir Bluetooth**|Habilita o uso da funcionalidade Bluetooth no dispositivo.|
|**Permitir Bluetooth no modo detectável**|Permite que este dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.|
|**Permitir anúncios de Bluetooth**|Permite que os dispositivos recebam anúncios via Bluetooth.|
|**Permitir a redefinição do telefone**|Controla se o usuário pode redefinir seu dispositivo para os padrões de fábrica.|
|**Permitir conexão USB**|Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.|
|**Permitir modo AntiTheft**|Configure se o modo Antitheft do Windows está habilitado.|

### Recursos

|Nome da configuração|Detalhes|
|----------------|----------------------|---------------------|
|**Permitir copiar e colar**|Habilitar ou desabilitar o uso de copiar e colar no dispositivo.<br>(Somente Windows 10 Mobile)|
|**Permitir gravação de voz**|Habilitar ou desabilitar as funcionalidades de gravação de voz no dispositivo.<br>(Somente Windows 10 Mobile)|
|**Permitir Cortana**|Habilitar ou desabilitar a assistente de voz Cortana.|
|**Permitir notificações da central de ações**|Habilitar ou desabilitar notificações da central de ações na tela de bloqueio do dispositivo.<br>(Somente Windows 10 Mobile)|

### Defender

Todas as configurações são somente para Windows 10 Desktop.

|Nome da configuração|Detalhes|
|-|-|
|**Permitir monitoramento em tempo real**|Habilita a verificação em tempo real de malware, spyware e outros softwares indesejados.|
|**Habilitar o monitoramento de comportamento**|Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos.|
|**Ativar o sistema de inspeção de rede**|O NIS(Sistema de Inspeção de Rede) ajuda a proteger dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado.|
|**Verificar todos os downloads**|Controla se o Defender examina todos os arquivos baixados da Internet.|
|**Ativar a verificação de script**|Permite que o Defender examine scripts que são usados no Internet Explorer.|
|**Monitorar atividade de arquivo e programa**|Habilite essa configuração para permitir que o Defender monitore a atividade de arquivos e programas nos dispositivos.|
|**Dias para rastrear o malware resolvido**|Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente. |
|**Permitir acesso à interface do usuário cliente**|Controla se a interface do usuário do Windows Defender está oculta para usuários finais.<br>Quando essa configuração é alterada, ela entrará em vigor na próxima vez em que o computador do usuário final for reiniciado.|
|**Agendar uma verificação rápida diária**|Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.|
|**Agendar uma verificação do sistema**|Permite agendar uma verificação de sistema completa ou rápida que ocorre regularmente no dia e hora que você selecionar.|
|**Limitar uso da CPU durante uma verificação**|Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**)|
|**Pesquisar arquivos mortos**|Permite que o Defender examine arquivos armazenados como arquivos Zip ou Cab.|
|**Verificar mensagens de email**|Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo.|
|**Verificar unidades removíveis**|Permite que o Defender examine unidades removíveis, como cartões USB.|
|**Pesquisar unidades de rede mapeadas**|Permite que o Defender examine arquivos na unidade de rede mapeada.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Pesquisar arquivos abertos de pastas de rede compartilhadas**|Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Intervalo de atualização de assinatura**|Especifique o intervalo no qual o Defender verificará novos arquivos de assinatura.|
|**Permitir proteção de nuvem**|Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.|
|**Solicitar aos usuários o envio de amostras**|Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados sejam enviados automaticamente para a Microsoft.|
|**Detecção de aplicativos potencialmente indesejados**|Esta configuração pode ser usada para proteger os dispositivos Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado.|
|**Arquivos e pastas a serem excluídos quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar um ou mais arquivos e pastas como **C:\Path** ou **ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídas em verificações em tempo real ou programadas.|
|**As extensões de arquivos a serem excluídas quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Quaisquer arquivos com essas extensões não serão incluídos em verificações em tempo real ou programadas.|
|**Processos a serem excluídos quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar um ou mais processos do tipo **.exe**, **.com**, ou **. scr** à lista de exclusões. Esses processos não serão incluídas em verificações em tempo real ou programadas.| 


### Configurações de atualizações

|Nome da configuração|Detalhes|
|----------------|---------------|
|**Permitir atualizações automáticas**|Habilite essa configuração para permitir as atualizações automáticas. Em seguida, configure as seguintes configurações para controlar o comportamento de atualização:<br /><br />**Notificar o download**<br /><br />**Instalação automática no tempo de manutenção**<br /><br />**Instalação automática e reinicialização no tempo de manutenção**<br /><br />**Instalação automática e a reinicialização no horário agendado** **Observação:** quando esta opção é selecionada, você também pode definir as seguintes configurações: **Suprimir notificação para o usuário final** e **Definir dia da instalação de atualizações agendadas**.<br>(Somente Windows 10 Desktop)|
|**Permitir recursos de pré-lançamento**|Permite que a Microsoft implante configurações e recursos de pré-lançamento em dispositivos Windows 10. Você pode selecionar para permitir apenas as configurações, ou todos os recursos e configurações de pré-lançamento a serem instalados.|

## Configurações de política personalizada
Use a **política de configuração personalizada** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar funcionalidades em dispositivos Windows 10 e Windows 10 Mobile. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você implante configurações do Windows 10 que não podem ser configuradas com a política de configuração geral do Intune.



### Configurações gerais de política personalizada

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política para ajudar a identificá-la no console do Intune.|
    |**Descrição**|Forneça uma descrição que proporciona uma visão geral da política e outras informações relevantes que o ajudarão a localizá-la.|

### Configurações de OMA-URI de política personalizada

|Nome da configuração|Detalhes|
    |--------|--------------------|
    |**Nome da configuração**|Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.|
    |**Descrição da configuração**|Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que o ajudarão a localizá-la.|
    |**Tipo de dados**|Selecione o tipo de data em que você especificará essa configuração de OMA-URI. Escolha:<br /><br />-   **Cadeia de caracteres**<br />-   **Cadeia de caracteres (XML)**<br />-   **Data e hora**<br />-   **Inteiro**<br />-   **Ponto flutuante**<br />-   **Booliano**|
    |**OMA-URI (com distinção entre maiúsculas e minúsculas)**|Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
    |**Valor**|Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|


## Configurações personalizadas de URI para dispositivos Windows 10
Este tópico lista as configurações que você pode definir para dispositivos Windows 10 e Windows 10 Mobile em uma **Política Personalizada do Windows 10** do Microsoft Intune.

Todos os dispositivos deverão estar registrados no Intune se você quiser usar a Política de URI Personalizada do Windows.

### Configurações de URI de política

|Nome da política|Detalhes|
|---------------|------------|-----------|
|**​Permitir atualização automática**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - **5** (padrão: **1**)|
|**Dia da instalação agendada**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - Todos os dias (padrão)<br>**1** - domingo<br>**2** - segunda-feira<br>**3** - terça-feira<br>**4** - quarta-feira<br>**5** - quinta-feira<br>**6** - sexta-feira<br>**7** - Sábado|
|**Hora da instalação agendada**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – **23** horas (**0** é meia-noite) (padrão: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - o usuário não é capaz de definir o temporizador para o período de cortesia da senha e o valor é definido como "sempre"<br>**1** - O usuário é capaz de definir o temporizador para o período de cortesia da senha (padrão)|
|**WiFi/AllowWiFi**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitir **usar conexão Wi-Fi**.<br>**1** – **Permitir o uso de conexão Wi-Fi** (padrão)|
|**WiFi/AllowInternetSharing**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitir Compartilhamento de Internet.<br>**1** – Permitir compartilhamento de Internet (padrão)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**WiFi/AllowManualWiFiConfiguration**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não é permitida nenhuma conexão Wi-Fi fora do MDM provisionado.<br>**1** – É permitido adicionar novas SSIDs de rede além das que há foram provisionadas pelo MDM (padrão)|
|**System/AllowLocation**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**System/AllowTelemetry**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitido (configuração Enterprise somente)<br>**1** – Limitado<br>**2** – completo (padrão)<br>**3** - completo e informações de diagnóstico|
|**System/AllowExperimentation**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitido<br>**1**- Somente configurações (padrão)<br>**2**- configurações e experimentação|
|**Security/AntiTheftMode**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - não permitir modo contra roubo<br>**1** - Preferência do usuário (padrão)|
|**Connectivity/AllowUSBConnection**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**System/AllowUserToResetPhone**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Connectivity/AllowCellularDataRoaming**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Connectivity/AllowVPNOverCellular**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - a VPN não é permitida por celular<br>**1** – A VPN pode usar qualquer conexão, incluindo celulares (padrão)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Connectivity/AllowBluetooth**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitir que o usuário ative o Bluetooth.<br>**1** – Reservado. O usuário pode ativar e configurar o Bluetooth (sem suporte no Windows Phone 8.1 para MDM, EAS, desktop Windows 10 ou Windows 10 Mobile)<br>**2** - Permitido. O usuário pode ativar e configurar o Bluetooth (padrão)|
|**Experience/AllowScreenCapture**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Experience/AllowTaskSwitcher**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Experience/AllowVoiceRecording**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Experience/AllowSyncMySettings**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitir roaming<br>**1** – Permitir roaming (padrão)|
|**Experience/AllowManualMDMUnenrollment**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Security/AllowManualRootCertificateInstallation**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Security/AllowAddProvisioningPackages**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Search/DisableBackoff**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** (padrão)<br>**1**|
|**Search/PreventRemoteQueries**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**<br>**1** (padrão)|
|**Search/AllowUsingDiacritics**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br> **0** (padrão)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** (padrão)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** (padrão)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**<br>**1** (padrão)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** (padrão)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Security/RequireProvisioningPackageSignature**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** (padrão)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**TextInput/AllowIMENetworkAccess**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitir<br>O Open Extended Dictionary está desativado.<br>Um usuário não pode:<br>Adicionar um novo Open Extended Dictionary<br /><br />Adicionar um novo arquivo de configuração de integração de pesquisa<br>Usar o recurso do candidato de nuvem<br>Enviar uma palavra registrada pelo usuário<br>Além disso:<br>Um Open Extended Dictionary que foi adicionado antes da habilitação dessa configuração de política não é usado para conversão.<br>Um arquivo de configuração de integração de pesquisa que foi instalado antes da habilitação dessa configuração de política não é usado.<br>**1** - Permitir<br>O Open Extended Dictionary pode ser adicionado e usado por padrão. Além disso, a função de integração de pesquisa pode ser usada por padrão.<br>Um usuário pode:<br>Usar o recurso do candidato de nuvem<br>Enviar uma palavra registrada pelo usuário.|
|**TextInput/AllowIMELogging**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - o log de erros de conversão está desativado. Dados ajustados automaticamente e dados de histórico de entrada não são salvos em um arquivo.<br>**1** - o log de erros de conversão está ativado. Dados ajustados automaticamente e dados de histórico de entrada são salvos em um arquivo (padrão)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**TextInput/AllowJapaneseUserDictionary**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres Shift JIS, são filtrados|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres JIS0208, são filtrados|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres JIS0208 ou EUDC, são filtrados|
|**TextInput/AllowInputPanel**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Bluetooth/AllowDiscoverableMode**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Bluetooth/AllowAdvertising**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowDataSense**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowVPN**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowWorkplace**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowDateTime**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowLanguage**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowRegion**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowSignInOptions**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowYourAccount**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowPowerSleep**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Settings/AllowAutoPlay**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Experience/AllowCortana**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Search/SafeSearchPermissions**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Restrita, filtragem mais elevada contra conteúdo adulto<br>**1** – Moderada, filtragem moderada contra conteúdo somente para adultos (resultados da pesquisa válidos não serão filtrados - padrão)|
|**Experience/AllowCopyPaste**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**Forçar tamanho inicial**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - permitir que o usuário altere o tamanho (padrão)<br>**1** - forçar tela não inteira<br>**2** - forçar tela inteira|
|**Update/RequireDeferUpgrade**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**: não adiar atualização (mantém na ramificação atual, CB - padrão)<br>**1**: possibilitar que atualizações sejam adiadas (dispositivo segue a ramificação atual para empresas, CBB e regras)<br /><br />Para obter mais informações, consulte:<br>[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(Desktop e Mobile)|**Descrição:** política para adiar atualizações de software por até 4 semanas<br /><br />**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br> **0**: aplicar atualizações imediatamente (padrão)<br>**1**-**4**: número de semanas para adiar atualizações de software.<br /><br />Para obter mais informações, consulte:<br>[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(Desktop e Mobile)|**Descrição:** política para adiar atualizações de recursos para até 8 meses<br /><br />**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**: aplicar atualizações imediatamente (padrão)<br>**1**-**8**: número de meses para adiar atualizações de recursos.<br /><br />Para obter mais informações, consulte:<br>[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(Desktop e Mobile)|**Descrição:** permite que um computador CBB pare de receber atualizações por cinco semanas. Isso deve ser usado caso haja um problema com uma atualização.<br /><br />**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**: aplicar atualizações imediatamente (padrão)<br>**1**: pausar atualizações (expira após 5 semanas)|

### Configurações de URI do Windows Defender

|Nome da política|Detalhes|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowBehaviorMonitoring**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowIntrusionPreventionSystem**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowIOAVProtection**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowScriptScanning**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowOnAccessProtection**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**RealTimeScanDirection**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Monitorar todos os arquivos (bidirecional - padrão)<br>**1** – Monitorar arquivos de entrada<br>**2** – Monitorar arquivos de saída|
|**DaysToRetainCleanedMalware**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - **90** – Representa por quanto tempo o malware será retido<br>**Valor padrão** **0** – mantém na pasta de quarentena para sempre e não remove automaticamente|
|**AllowUserUIAccess**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**ScanParameter**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**1** – Verificação rápida (padrão)<br>**2** - varredura completa|
|**ScheduleScanDay**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - Todos os dias (padrão)<br>**1** - segunda-feira<br>**2** - terça-feira<br>**3** - quarta-feira<br>**4** - quinta-feira<br>**5** - sexta-feira<br>**6** - sábado<br>**7** - domingo<br>**8** – Nenhuma varredura agendada|
|**ScheduleScanTime**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - 12:00 AM<br>**60** – 1:00 AM<br>**120** – 2h00 (padrão)<br>**180** – 3:00 AM<br>**240** – 4:00 AM<br>**300** – 5:00 AM<br>**360** – 6:00 AM<br>**420** – 7:00 AM<br>**480** – 8:00 AM<br>**540** – 9:00 AM<br>**600** – 10:00 AM<br>**660** – 11:00 AM<br>**720** – 12:00 PM<br>**780** – 1:00 PM<br>**840** – 2:00 PM<br>**900** – 3:00 PM<br>**960** – 4:00 PM<br>**1020** – 5:00 PM<br>**1080** – 6:00 PM<br>**1140** – 7:00 PM<br>**1200** – 8:00 PM<br>**1260** – 9:00 PM<br>**1320** – 10:00 PM<br>**1381** – Janela de manutenção|
|**ScheduleQuickScanTime**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** - 12:00 AM<br>**60** – 1:00 AM<br>**120** – 2h00 (padrão)<br>**180** – 3:00 AM<br>**240** – 4:00 AM<br>**300** – 5:00 AM<br>**360** – 6:00 AM<br>**420** – 7:00 AM<br>**480** – 8:00 AM<br>**540** – 9:00 AM<br>**600** – 10:00 AM<br>**660** – 11:00 AM<br>**720** – 12:00 PM<br>**780** – 1:00 PM<br>**840** – 2:00 PM<br>**900** – 3:00 PM<br>**960** – 4:00 PM<br>**1020** – 5:00 PM<br>**1080** – 6:00 PM<br>**1140** – 7:00 PM<br>**1200** – 8:00 PM<br>**1260** – 9:00 PM<br>**1320** – 10:00 PM<br>**1380** – 11:00 PM|
|**AVGCPULoadFactor**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:0** - **100** (padrão: **50**)|
|**AllowArchiveScanning**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowEmailScanning**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Tipo de dados:** inteiro<br>**Valores permitidos:**<br>**0** – não permitido (padrão)<br>**1** – permitido|
|**AllowFullScanRemovableDriveScanning**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido (padrão)<br>**1** – permitido|
|**AllowFullScanOnMappedNetworkDrives**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**AllowScanningNetworkFiles**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão) – Também é executado quando o RTP está ativado, quando é definido como permitido|
|**SignatureUpdateInterval**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não verificar assinaturas em um intervalo<br>**1** - verificar assinaturas a cada hora<br>**2** - Verificar assinaturas a cada 2 horas etc.<br>**24** - Verificar assinaturas todos os dias<br>**Valor padrão:** 8 - Verificar assinaturas a cada 8 horas|
|**AllowCloudProtection**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – não permitido<br>**1** – permitido (padrão)|
|**SubmitSamplesConsent**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Sempre solicitar (padrão)<br>**1** – Enviar amostras seguras automaticamente<br>**2** – Nunca enviar<br>**3** – Enviar todas as amostras automaticamente|
|**ExcludedExtensions**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:**<br>*&lt;lista de extensões separadas por ponto e vírgula&gt;* por exemplo, **obj;lib**<br>**Padrão:** nenhuma extensão excluída|
|**ExcludedPaths**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:**<br /><br />*&lt;lista dos caminhos separados por ponto e vírgula&gt;*<br /><br />Exemplo: **c:\test;c:\test1.exe**<br /><br />**Valor padrão:** nenhum caminho será excluído|
|**ExcludedProcesses**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:**<br>*&lt;lista dos caminhos separados por ponto e vírgula&gt;*<br>Exemplo: **c:\test.exe;c:\test1.exe**<br>**Valor padrão:** nenhum processo será excluído|

### Configurações de URI do navegador Microsoft Edge

|Nome da política|Detalhes|
|---------------|------------|-----------|
|**Permitir navegador**<br>(somente no Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**: navegação desativada<br>**1**: navegação ativada (padrão)|
|**AllowSearchSuggestionsinAddressBar**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**: não exibir sugestões de pesquisa<br>**1**: exibir sugestões de pesquisa (padrão)|
|**SendIntranetTraffictoInternetExplorer**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0**: desabilitado (abrir sites da intranet no navegador  Microsoft Edge - padrão)<br>**1** - habilitado (abrir sites de intranet no Internet Explorer).|
|**Permitir Não Rastrear**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – desabilitado (DNT não enviado - padrão)<br>**1** – habilitado (enviar DNT)|
|**Configurar o SmartScreen**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não permitido<br>**1** – Permitir (padrão)|
|**Permitir pop-ups**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Bloquear pop-ups (padrão)<br>**1** – Permitir pop-ups|
|**Permitir cookies**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Não bloquear. Permitir cookies de todos os sites da web (padrão)<br>**1** – Bloquear somente os cookies de terceiros<br>**2** – Bloquear todos os cookies|
|**Permitir salvar senha**<br>(Desktop e Mobile)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – O gerenciador de senha é desabilitado; <br>**1** – O Gerenciador de senha é habilitado (padrão)|
|**Permitir Preenchimento Automático**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br>**0** – Desabilitado (padrão)<br>**1** – Habilitado|
|**Configurar a lista de sites corporativos**<br>(somente no Desktop)|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:<br>0** – Não configurado<br>**1** – Usar a lista de sites do modo corporativo do IE, se configurado (padrão)<br>**2** – Especificar a localização da lista de sites corporativos|

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Aug16_HO1-->


