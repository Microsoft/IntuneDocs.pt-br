---
# required metadata

title: Configurações de política do Windows 10 no Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurações de política do Windows 10 no Microsoft Intune

Use as configurações de política listadas neste tópico para ajudar a definir as configurações Windows 10 desktops e dispositivos móveis Windows 10 registrados.

## Definições de política de configuração geral

Use a **política de configuração geral** da Microsoft para Windows 10 para definir configurações para Windows 10 desktops e dispositivos Windows 10 Mobile registrados:


### Senha

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Exigir uma senha para desbloquear dispositivos**|Requer uma senha nos dispositivos com suporte.|Sim|Sim|
|**Tipo de senha necessária**|Especifica o tipo de senha que será necessário, apenas com caracteres numéricos ou alfanuméricos|Sim|Sim|
|**Tipo de senha necessária** - **Número mínimo de conjuntos de caracteres**|Há quatro conjuntos de caracteres: minúsculas, maiúsculas, símbolos e números. Essa configuração especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha.|Sim|Sim|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres que na senha do dispositivo deve conter.|Não|Sim|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Apaga o dispositivo se houver falha neste número de tentativas de logon.|Sim|Sim|
|**Minutos de inatividade antes que a tela se apague**|Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.|Sim|Sim|
|**Expiração da senha (dias)**|Especifica o período após o qual a senha do dispositivo deve ser alterada.|Sim|Sim|
|**Lembrar de histórico de senha**|Especifica se você deseja impedir que o usuário final crie senhas usadas anteriormente.|Sim|Sim|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|Sim|Sim|
|**Permitir senha de imagem e PIN**|Permite que você use gestos simples em uma imagem ou um PIN simples para fazer logon.|Sim|Não|
|**Exigir senha quando o dispositivo retorna de um estado ocioso**|Se habilitado, o usuário deverá inserir uma senha para desbloquear o dispositivo de um estado ocioso.|Não|Sim|

### Criptografia

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Exigir criptografia no dispositivo móvel**|Habilita a criptografia em dispositivos de destino.|Não|Sim|

### Sistema

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir captura de tela**|Permite que o usuário capture a tela do dispositivo como uma imagem.|Não|Sim|
|**Permitir cancelamento de registro manual**|Permite que o usuário exclua manualmente a conta da empresa do dispositivo.|Sim|Sim|
|**Permitir instalação de certificado raiz manual**|Especifica se o usuário pode instalar manualmente os certificados raiz|Não|Sim|
|**Permitir que o diagnóstico e os dados de uso sejam enviados à Microsoft**|Determina a quantidade de dados de diagnóstico e de uso que são enviadas dos dispositivos para a Microsoft.<br>**Não** - Nenhum dado é enviado para a Microsoft<br>**Básico** - O dispositivo envia apenas informações limitadas para a Microsoft<br>**Avançado** - Envia dados de diagnóstico avançados para a Microsoft<br>**Completo (recomendado)** - Envia os mesmos dados que **Avançado**, além de dados adicionais sobre o estado do dispositivo|Sim|Sim|


### Conta e sincronização

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir conta da Microsoft**|Permite que o usuário associe uma conta da Microsoft ao dispositivo.|Sim|Sim|
|**Permitir a adição de contas não Microsoft manualmente**|Permite que o usuário adicione contas de email a dispositivos que não estão associados uma conta da Microsoft.|Sim|Sim|
|**Permitir a sincronização de configurações de contas da Microsoft**|Permitir usar configurações de dispositivo e aplicativo associadas a uma conta da Microsoft para sincronização entre dispositivos.|Sim|Sim|

### Configurações de email

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Tornar a conta da Microsoft opcional em aplicativo de correio do Windows**|Configure isso para remover o requisito de uma conta da Microsoft no Email do Windows.|Sim|Não|



### Microsoft Edge

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir navegador da web**|Permitir o uso do navegador da Web Edge no dispositivo.|Não|Sim|
|**Permitir sugestões de pesquisa na barra de endereços**|Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.|Sim|Sim|
|**Permitir envio de tráfego de intranet no Internet Explorer**|Permite que os usuários abram sites da intranet no Internet Explorer.|Sim|Não|
|**Permitir Não Rastrear**|Configura o navegador Edge para enviar cabeçalhos Não Rastrear para sites visitados pelos usuários.|Sim|Sim|
|**Habilitar SmartScreen**|Habilita a configuração do navegador SmartScreen nos dispositivos.|Sim|Sim|
|**Permitir script ativo**|Permite que scripts, como JavaScript, sejam executados no navegador Edge.|Sim|Sim|
|**Permitir pop-ups**|Habilita ou desabilita o bloqueador de pop-ups do navegador.|Sim|Não|
|**Permitir cookies**|Habilita ou desabilita cookies.|Sim|Sim|
|**Permitir Preenchimento Automático**|Permite que os usuários possam alterar as configurações de preenchimento automático no navegador.|Sim|Não|
|**Permitir Gerenciador de Senhas**|Habilitar ou desabilitar o recurso de Gerenciamento de Senha do Edge.|Sim|Sim|
|**Local do Enterprise Mode Site List**|Especifica onde encontrar a lista de sites que será aberta no modo Empresarial. Os usuários não podem editar essa lista.|Sim|Não|

### Aplicativos

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir loja de aplicativo**|Permite ao usuário acessar a loja de aplicativos no dispositivo.|Não|Sim|



### Celular

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir roaming de Dados**|Permita o roaming entre redes durante o acesso de dados.|Sim|Sim|
|**Permitir VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.|Sim|Sim|
|**Permitir roaming de VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando estiver em roaming ou em uma rede celular.|Sim|Sim|

### Hardware

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir câmera**|Especifica se a câmera do dispositivo pode ser usada.|Sim|Sim|
|**Permitir armazenamento removível**|Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo.|Sim|Sim|
|**Permitir Wi-Fi**|Permite usar a funcionalidade Wi-Fi dos dispositivos.|Não|Sim|
|**Permitir compartilhamento de Internet**|Permitir usar o compartilhamento de conexão com a Internet no dispositivo móvel.|Sim|Sim|
|**Permitir configuração manual de Wi-Fi**|Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se podem usar somente as conexões configuradas por um perfil Wi-Fi.|Não|Sim|
|**Permitir conexão automática para liberar pontos de acesso Wi-Fi**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.|Sim|Sim|
|**Permitir localização geográfica**|Especifica se o dispositivo pode usar informações de serviços de localização.|Sim|Sim|
|**Permitir NFC**|Permite que o dispositivo use sua funcionalidade de Comunicação a Curta Distância.|Sim|Sim|
|**Permitir Bluetooth**|Habilita o uso da funcionalidade Bluetooth no dispositivo.|Sim|Sim|
|**Permitir Bluetooth no modo detectável**|Permite que este dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.|Sim|Sim|
|**Permitir anúncios de Bluetooth**|Permite que os dispositivos recebam anúncios via Bluetooth.|Sim|Sim|
|**Permitir modo conectável de Bluetooth** **Importante:** |Essa configuração não tem mais suporte do Windows 10 e será removida no futuro.|Sim|Sim|
|**Permitir a redefinição do telefone**|Controla se o usuário pode redefinir seu dispositivo para os padrões de fábrica.|Sim|Sim|
|**Permitir conexão USB**|Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.|Sim|Sim|
|**Permitir modo AntiTheft**|Configure se o modo Antitheft do Windows está habilitado.|Sim|Sim|

### Recursos

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Permitir copiar e colar**|Habilitar ou desabilitar o uso de copiar e colar no dispositivo.|Não|Sim|
|**Permitir gravação de voz**|Habilitar ou desabilitar as funcionalidades de gravação de voz no dispositivo.|Não|Sim|
|**Permitir Cortana**|Habilitar ou desabilitar a assistente de voz Cortana.|Sim|Sim|
|**Permitir notificações da central de ações**|Habilitar ou desabilitar notificações da central de ações na tela de bloqueio do dispositivo.|Não|Sim|

### Defender

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|-|-|
|**Permitir monitoramento em tempo real**|Habilita a verificação em tempo real de malware, spyware e outros softwares indesejados.|Sim|Não|
|**Habilitar o monitoramento de comportamento**|Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos.|Sim|Não
|**Ativar o sistema de inspeção de rede**|O NIS(Sistema de Inspeção de Rede) ajuda a proteger dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado.|Sim|Não
|**Verificar todos os downloads**|Controla se o Defender examina todos os arquivos baixados da Internet.|Sim|Não
|**Ativar a verificação de script**|Permite que o Defender examine scripts que são usados no Internet Explorer.|Sim|Não
|**Monitorar atividade de arquivo e programa**|Habilite essa configuração para permitir que o Defender monitore a atividade de arquivos e programas nos dispositivos.|Sim|Não
|**Dias para rastrear o malware resolvido**|Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente. |Sim|Não
|**Permitir acesso à interface do usuário cliente**|Controla se a interface do usuário do Windows Defender está oculta para usuários finais.<br>Quando essa configuração é alterada, ela entrará em vigor na próxima vez em que o computador do usuário final for reiniciado.|Sim|Não
|**Agendar uma verificação rápida diária**|Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.|Sim|Não
|**Agendar uma verificação do sistema**|Permite agendar uma verificação de sistema completa ou rápida que ocorre regularmente no dia e hora que você selecionar.|Sim|Não
|**Limitar uso da CPU durante uma verificação**|Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**)|Sim|Não
|**Pesquisar arquivos mortos**|Permite que o Defender examine arquivos armazenados como arquivos Zip ou Cab.|Sim|Não
|**Verificar mensagens de email**|Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo.|Sim|Não
|**Verificar unidades removíveis**|Permite que o Defender examine unidades removíveis, como cartões USB.|Sim|Não
|**Pesquisar unidades de rede mapeadas**|Permite que o Defender examine arquivos na unidade de rede mapeada.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|Sim|Não
|**Pesquisar arquivos abertos de pastas de rede compartilhadas**|Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|Sim|Não
|**Intervalo de atualização de assinatura**|Especifique o intervalo no qual o Defender verificará novos arquivos de assinatura.|Sim|Não
|**Permitir proteção de nuvem**|Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.|Sim|Não
|**Solicitar aos usuários o envio de amostras**|Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados sejam enviados automaticamente para a Microsoft.|Sim|Não
|**Arquivos e pastas a serem excluídos quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar um ou mais arquivos e pastas como **C:\Path** ou **ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídas em verificações em tempo real ou programadas.|Sim|Não
|**As extensões de arquivos a serem excluídas quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Quaisquer arquivos com essas extensões não serão incluídos em verificações em tempo real ou programadas.|Sim|Não
|**Processos a serem excluídos quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar um ou mais processos do tipo **.exe**, **.com**, ou **. scr** à lista de exclusões. Esses processos não serão incluídas em verificações em tempo real ou programadas.|Sim|Não| 


### Configurações de atualizações

|Nome da configuração|Detalhes|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Permitir atualizações automáticas**|Habilite essa configuração para permitir as atualizações automáticas. Em seguida, configure as seguintes configurações para controlar o comportamento de atualização:<br /><br />**Notificar o download**<br /><br />**Instalação automática no tempo de manutenção**<br /><br />**Instalação automática e reinicialização no tempo de manutenção**<br /><br />**Instalação automática e a reinicialização no horário agendado** **Observação:** quando esta opção é selecionada, você também pode definir as seguintes configurações: **Suprimir notificação para o usuário final** e **Definir dia da instalação de atualizações agendadas**.|Sim|Não|

## Configurações de política personalizada
Use a **política de configuração personalizada** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar funcionalidades em dispositivos Windows 10 e Windows 10 Mobile. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você implante configurações do Windows 10 que não podem ser configuradas com a política de configuração geral do Intune. Para obter informações sobre as configurações que você pode definir com essas políticas, consulte [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune).

Para obter uma lista de configurações de OMA-URI que você pode definir em dispositivos Windows 10 registrados, consulte Personalizar configurações de URI para dispositivos Windows 10 mais adiante neste tópico.

### Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política para ajudar a identificá-la no console do Intune.|
    |**Descrição**|Forneça uma descrição que proporciona uma visão geral da política e outras informações relevantes que o ajudarão a localizá-la.|

### Configurações de OMA-URI

|Nome da configuração|Detalhes|
    |--------|--------------------|
    |**Nome da configuração**|Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.|
    |**Descrição da configuração**|Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que o ajudarão a localizá-la.|
    |**Tipo de dados**|Selecione o tipo de data em que você especificará essa configuração de OMA-URI. Escolha:<br /><br />-   **Cadeia de caracteres**<br />-   **Cadeia de caracteres (XML)**<br />-   **Data e hora**<br />-   **Inteiro**<br />-   **Ponto flutuante**<br />-   **Booliano**|
    |**OMA-URI (com distinção entre maiúsculas e minúsculas)**|Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
    |**Valor**|Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|


## Configurações personalizadas de URI para dispositivos Windows 10
Este tópico lista as configurações que você pode definir para dispositivos Windows 10 e Windows 10 Mobile em uma **Política Personalizada do Windows 10** do Microsoft Intune.


> [!NOTE]
> Na coluna **Dá suporte** da tabela a seguir, são usados os seguintes valores:
> 
> -   **Desktop** – A configuração dá suporte somente a computadores Windows 10 Professional e Enterprise registrados com o Intune.
> -   **Mobile** – a configuração dá suporte somente a dispositivos Windows Mobile 10.
> -   **Ambos** – a configuração dá suporte a dispositivos móveis e desktop.
> 
> Todos os dispositivos deverão estar registrados no Intune se você quiser usar a Política de URI Personalizada do Windows.

### Política

|Nome da política|Dá suporte|Detalhes|
|---------------|------------|-----------|
|**​Permitir atualização automática**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** - **5**<br /><br />**Valor padrão:** 1|
|**Dia da instalação agendada**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - todos os dias.<br /><br />**1** - domingo<br /><br />**2** - segunda-feira<br /><br />**3** - terça-feira<br /><br />**4** - quarta-feira<br /><br />**5** - quinta-feira<br /><br />**6** - sexta-feira<br /><br />**7** - sábado.<br /><br />**Valor padrão:** 0|
|**Hora da instalação agendada**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:0** – **23** horas (0 é meia-noite)<br /><br />**Valor padrão:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - o usuário não é capaz de definir o temporizador para o período de cortesia da senha e o valor é definido como "sempre"<br /><br />**1** - o usuário é capaz de definir o temporizador para o período de cortesia da senha<br /><br />**Valor padrão:** 1|
|**WiFi/AllowWiFi**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitir o **uso de conexão Wi-Fi**.<br /><br />**1** – **Permitir o uso de conexão Wi-Fi**.<br /><br />**Valor padrão:** 1|
|**WiFi/AllowInternetSharing**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitir Compartilhamento de Internet.<br /><br />**1** – Permitir Compartilhamento de Internet.<br /><br />**Valor padrão:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não é permitida nenhuma conexão Wi-Fi fora do MDM provisionado.<br /><br />**1** – É permitido adicionar novas SSIDs de rede além das que há foram provisionadas pelo MDM.<br /><br />**Valor padrão:** 1|
|**System/AllowLocation**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**System/AllowTelemetry**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitido (configuração Enterprise somente)<br /><br />**1** – Limitado<br /><br />**2** – Completo<br /><br />**3** - completo e informações de diagnóstico<br /><br />**Valor padrão:** 2|
|**System/AllowExperimentation**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitido<br /><br />**1**- somente configurações<br /><br />**2**- configurações e experimentação<br /><br />**Valor padrão:** 1|
|**Security/AntiTheftMode**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - não permitir modo contra roubo<br /><br />**1** - Preferência do usuário<br /><br />**Valor padrão:** 1|
|**Connectivity/AllowUSBConnection**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**System/AllowUserToResetPhone**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Connectivity/AllowCellularDataRoaming**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Connectivity/AllowVPNOverCellular**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - a VPN não é permitida por celular<br /><br />**1** – A VPN pode usar qualquer conexão, incluindo celulares.<br /><br />**Valor padrão:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Connectivity/AllowBluetooth**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitir que o usuário ative o Bluetooth.<br /><br />**1** – Reservado. O usuário pode ativar e configurar o Bluetooth (sem suporte no Windows Phone 8.1 para MDM, EAS, desktop Windows 10 ou Windows 10 Mobile)<br /><br />**2** - Permitido. O usuário pode ativar e configurar o Bluetooth.<br /><br />**Valor padrão:** 2|
|**Experience/AllowScreenCapture**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Experience/AllowTaskSwitcher**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Experience/AllowVoiceRecording**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Experience/AllowSyncMySettings**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitir roaming<br /><br />**1** – Permitir roaming<br /><br />**Valor padrão:** 1|
|**Experience/AllowManualMDMUnenrollment**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Security/AllowManualRootCertificateInstallation**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Security/AllowAddProvisioningPackages**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Search/DisableBackoff**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 0|
|**Search/PreventRemoteQueries**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 1|
|**Search/AllowUsingDiacritics**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 0|
|**Search/AlwaysUseAutoLangDetection**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 0|
|**Search/DisableRemovableDriveIndexing**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 0|
|**Security/AllowRemoveProvisioningPackage**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Security/RequireProvisioningPackageSignature**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**<br /><br />**1**<br /><br />**Valor padrão:** 0|
|**AboveLock/AllowActionCenterNotifications**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**TextInput/AllowIMENetworkAccess**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não permitir<br /><br />O Open Extended Dictionary está desativado.<br /><br />Um usuário não pode:<br /><br />Adicionar um novo Open Extended Dictionary<br /><br />Adicionar um novo arquivo de configuração de integração de pesquisa<br /><br />Usar o recurso do candidato de nuvem<br /><br />Enviar uma palavra registrada pelo usuário<br /><br />Além disso:<br /><br />Um Open Extended Dictionary que foi adicionado antes da habilitação dessa configuração de política não é usado para conversão.<br /><br />Um arquivo de configuração de integração de pesquisa que foi instalado antes da habilitação dessa configuração de política não é usado.<br /><br />**1** - Permitir<br /><br />O Open Extended Dictionary pode ser adicionado e usado por padrão. Além disso, a função de integração de pesquisa pode ser usada por padrão.<br /><br />Um usuário pode:<br /><br />Usar o recurso do candidato de nuvem<br /><br />Enviar uma palavra registrada pelo usuário<br /><br />**Valor padrão:**|
|**TextInput/AllowKoreanExtendedHanja**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**TextInput/AllowIMELogging**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - o log de erros de conversão está desativado. Dados ajustados automaticamente e dados de histórico de entrada não são salvos em um arquivo.<br /><br />**1** - o log de erros de conversão está ativado. Dados ajustados automaticamente e dados de histórico de entrada são salvos em um arquivo.<br /><br />**Valor padrão:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**TextInput/AllowJapaneseUserDictionary**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - todos, exceto caracteres JIS, são filtrados<br /><br />**1** - nenhum caractere é filtrado<br /><br />**Valor padrão:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - todos, exceto caracteres JIS0208, são filtrados<br /><br />**1** - nenhum caractere é filtrado<br /><br />**Valor padrão:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - todos, exceto caracteres JIS0208 ou EUDC, são filtrados<br /><br />**1** - Nenhum caractere é filtrado.<br /><br />**Valor padrão:** 1|
|**TextInput/AllowInputPanel**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Bluetooth/AllowDiscoverableMode**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Bluetooth/AllowAdvertising**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowDataSense**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowVPN**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowWorkplace**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowDateTime**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowLanguage**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowRegion**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowSignInOptions**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowYourAccount**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowPowerSleep**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Settings/AllowAutoPlay**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Experience/AllowCortana**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Search/SafeSearchPermissions**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Restrita, filtragem mais elevada contra conteúdo adulto<br /><br />**1** – Moderada, filtragem moderada contra conteúdo adulto (resultados de pesquisa válidos não serão filtrados)<br /><br />**Valor padrão:** 1|
|**Experience/AllowCopyPaste**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**Forçar tamanho inicial**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - permitir que o usuário altere o tamanho<br /><br />**1** - forçar tela não inteira<br /><br />**2** - forçar tela inteira<br /><br />**Valor padrão:** 0|
|**Update/RequireDeferUpgrade**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**: não adiar atualização (mantém na ramificação atual, CB)<br /><br />**1**: possibilitar que atualizações sejam adiadas (dispositivo segue a ramificação atual para empresas, CBB e regras)<br /><br />**Valor padrão:0**<br /><br />Para obter mais informações, consulte:<br /><br />[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Ambos|**Descrição:** política para adiar atualizações de software por até 4 semanas<br /><br />**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:** 0: aplicar as atualizações imediatamente; 1-4: número de semanas para adiar atualizações de software.<br /><br />**Valor padrão:0**<br /><br /><br />Para obter mais informações, consulte:<br /><br />[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Ambos|**Descrição:** política para adiar atualizações de recursos para até 8 meses<br /><br />**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:** 0: aplicar as atualizações imediatamente; 1-8: número de semanas para adiar atualizações de recurso.<br /><br />**Valor padrão:0**<br /><br />Para obter mais informações, consulte:<br /><br />[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Ambos|**Descrição:** permite que um computador CBB pare de receber atualizações por cinco semanas. Isso deve ser usado caso haja um problema com uma atualização.<br /><br />**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0**: aplicar atualizações imediatamente (padrão)<br /><br />**1**: pausar atualizações (expira após 5 semanas)<br /><br />**Valor padrão:0**|

### Windows Defender

|Nome da política|Dá suporte|Detalhes|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowBehaviorMonitoring**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowIntrusionPreventionSystem**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowIOAVProtection**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowScriptScanning**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowOnAccessProtection**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**RealTimeScanDirection**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – monitorar todos os arquivos (bidirecional)<br /><br />**1** – Monitorar arquivos de entrada<br /><br />**2** – Monitorar arquivos de saída<br /><br />**Valor padrão:** 0|
|**DaysToRetainCleanedMalware**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** - **90** – Representa por quanto tempo o malware será retido<br /><br />**Valor padrão:** 0 – mantém na pasta de quarentena para sempre e não remove automaticamente|
|**AllowUserUIAccess**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**ScanParameter**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**1** – Varredura rápida<br /><br />**2** - varredura completa<br /><br />**Valor padrão:** 1|
|**ScheduleScanDay**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - todos os dias<br /><br />**1** - segunda-feira<br /><br />**2** - terça-feira<br /><br />**3** - quarta-feira<br /><br />**4** - quinta-feira<br /><br />**5** - sexta-feira<br /><br />**6** - sábado<br /><br />**7** - domingo<br /><br />**8** – Nenhuma varredura agendada<br /><br />**Valor padrão:** 0|
|**ScheduleScanTime**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - 12:00 AM<br /><br />**60** – 1:00 AM<br /><br />**120** – 2:00 AM<br /><br />**180** – 3:00 AM<br /><br />**240** – 4:00 AM<br /><br />**300** – 5:00 AM<br /><br />**360** – 6:00 AM<br /><br />**420** – 7:00 AM<br /><br />**480** – 8:00 AM<br /><br />**540** – 9:00 AM<br /><br />**600** – 10:00 AM<br /><br />**660** – 11:00 AM<br /><br />**720** – 12:00 PM<br /><br />**780** – 1:00 PM<br /><br />**840** – 2:00 PM<br /><br />**900** – 3:00 PM<br /><br />**960** – 4:00 PM<br /><br />**1020** – 5:00 PM<br /><br />**1080** – 6:00 PM<br /><br />**1140** – 7:00 PM<br /><br />**1200** – 8:00 PM<br /><br />**1260** – 9:00 PM<br /><br />**1320** – 10:00 PM<br /><br />**1381** – Janela de manutenção<br /><br />**Valor padrão:** 120|
|**ScheduleQuickScanTime**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** - 12:00 AM<br /><br />**60** – 1:00 AM<br /><br />**120** – 2:00 AM<br /><br />**180** – 3:00 AM<br /><br />**240** – 4:00 AM<br /><br />**300** – 5:00 AM<br /><br />**360** – 6:00 AM<br /><br />**420** – 7:00 AM<br /><br />**480** – 8:00 AM<br /><br />**540** – 9:00 AM<br /><br />**600** – 10:00 AM<br /><br />**660** – 11:00 AM<br /><br />**720** – 12:00 PM<br /><br />**780** – 1:00 PM<br /><br />**840** – 2:00 PM<br /><br />**900** – 3:00 PM<br /><br />**960** – 4:00 PM<br /><br />**1020** – 5:00 PM<br /><br />**1080** – 6:00 PM<br /><br />**1140** – 7:00 PM<br /><br />**1200** – 8:00 PM<br /><br />**1260** – 9:00 PM<br /><br />**1320** – 10:00 PM<br /><br />**1380** – 11:00 PM<br /><br />**Valor padrão:** 120|
|**AVGCPULoadFactor**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** - **100**<br /><br />**Valor padrão:** 50|
|**AllowArchiveScanning**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowEmailScanning**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 0|
|**AllowFullScanRemovableDriveScanning**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 0|
|**AllowFullScanOnMappedNetworkDrives**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**AllowScanningNetworkFiles**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1 – Também é executado quando o RTP está ativado, quando é definido como permitido|
|**SignatureUpdateInterval**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Não verificar assinaturas em um intervalo<br /><br />**1** - verificar assinaturas a cada hora<br /><br />**2** - Verificar assinaturas a cada 2 horas etc.<br /><br />**24** - Verificar assinaturas todos os dias<br /><br />**Valor padrão:** 8 - Verificar assinaturas a cada 8 horas|
|**AllowCloudProtection**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – não permitido<br /><br />**1** – permitido<br /><br />**Valor padrão:** 1|
|**SubmitSamplesConsent**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:**<br /><br />**0** – Sempre solicitar<br /><br />**1** – Enviar amostras seguras automaticamente<br /><br />**2** – Nunca enviar<br /><br />**3** – Enviar todas as amostras automaticamente<br /><br />**Valor padrão:** 0|
|**ExcludedExtensions**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:**<br /><br />*&lt;lista de extensões separadas por ponto e vírgula&gt;* por exemplo, **obj;lib**<br /><br />**Valor padrão:** nenhuma extensão excluída|
|**ExcludedPaths**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:**<br /><br />*&lt;lista dos caminhos separados por ponto e vírgula&gt;*<br /><br />Exemplo: **c:\test;c:\test1.exe**<br /><br />**Valor padrão:** nenhum caminho será excluído|
|**ExcludedProcesses**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos:**<br /><br />*&lt;lista dos caminhos separados por ponto e vírgula&gt;*<br /><br />Exemplo: **c:\test.exe;c:\test1.exe**<br /><br />**Valor padrão:** nenhum processo será excluído|

### Navegador de borda

|Nome da política|Dá suporte|Detalhes|
|---------------|------------|-----------|
|**Permitir navegador**|Celular|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0**: navegação desabilitada; **1**: navegação habilitada.<br /><br />**Valor padrão:** 1|
|**AllowSearchSuggestionsinAddressBar**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0**: não mostrar sugestões de pesquisa; **1**: mostrar sugestões de pesquisa.<br /><br />**Valor padrão:** 1|
|**SendIntranetTraffictoInternetExplorer**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0**: desabilitado (sites de intranet aberta no navegador Edge); **1** -habilitado (sites de intranet aberta no Internet Explorer).<br /><br />**Valor padrão:** 0|
|**Permitir Não Rastrear**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** – desabilitado (DNT não enviado); **1** – habilitado (enviar DNT)<br /><br />**Valor padrão:** 0|
|**Configurar o SmartScreen**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** – não permitir; **1** – permitir<br /><br />**Valor padrão:** 1|
|**Permitir pop-ups**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** – bloquear pop-ups; **1** – permitir pop-ups<br /><br />**Valor padrão:** 0|
|**Permitir cookies**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** – não bloquear. Permitir cookies de todos os sites; **1** – bloquear somente cookies de terceiros; **2** – bloquear todos os cookies<br /><br />**Valor padrão:** 0|
|**Permitir salvar senha**|Ambos|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos:0** – o gerenciador de senhas está desabilitado; <br />                        **1** – o gerenciador de senhas está habilitado<br /><br />**Valor padrão:** 1|
|**Permitir Preenchimento Automático**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Tipo de dados:** inteiro<br /><br />**Valores permitidos: 0** – desabilitado; **1** – habilitado<br /><br />**Valor padrão:** 0|
|**Configurar a lista de sites corporativos**|Área de Trabalho|**Caminho de URI completo:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Tipo de dados:** cadeia de caracteres<br /><br />**Valores permitidos: 0** – não configurado; **1** – use a lista de sites de modo empresarial do IE se configurado; **2** – especifique o local da lista de sites corporativos<br /><br />**Valor padrão:** 1|

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


