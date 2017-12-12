---
title: "Configurações de política do Windows 10"
description: "Use as configurações de política listadas neste tópico para ajudá-lo a definir configurações internas e personalizadas para dispositivos Windows 10 Mobile e Windows 10 Desktop registrados."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fff34b145660e1d0e78e05de467629f9421fcf7a
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Configurações de política do Intune para dispositivos Windows 10 no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico contém informações para ajudá-lo a entender as configurações de política do Intune que você pode usar para gerenciar dispositivos Windows 10. Leia este tópico junto com os procedimentos em [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Você pode escolher entre dois tipos de política:

- **Política Personalizada**: use a **política personalizada** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows 10 disponibiliza várias configurações de CSP, por exemplo o [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Política de configuração geral**: Use esse tipo de política para selecionar as configurações da lista interna fornecida com o Microsoft Intune.

## <a name="custom-policy-settings"></a>Configurações de política personalizada

Forneça as seguintes configurações em uma política personalizada.

### <a name="general-settings"></a>Configurações gerais

Insira um nome e uma descrição opcional para a política para ajudar a identificá-la no console do Intune.

### <a name="oma-uri-settings"></a>Configurações de OMA-URI

Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir:

- **Nome da configuração**: insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações. Encontre mais informações sobre as configurações de URI em [Provedor de serviço de configuração de política (CSP de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Descrição da configuração**: opcionalmente, insira uma descrição para a configuração.
- **Tipo de dados**: escolha entre os seguintes tipos de dados:
    - **Cadeia de caracteres**
    - **Cadeia de caracteres (XML)**
    - **Data e hora**
    - **Inteiro**
    - **Ponto flutuante**
    - **Booliano**
- **OMA-URI (com distinção entre maiúsculas e minúsculas)**: especifique o OMA-URI para o qual você deseja fornecer uma configuração.
- **Valor**: especifique o valor para associar ao OMA-URI que você inseriu.

### <a name="example"></a>Exemplo
Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada. Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.

> ![Exemplo de política personalizada que contém configurações de VPN](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>Como localizar as políticas que você pode configurar

Você encontrará uma lista completa de todos os provedores de serviço de configuração (CSP) a que o Windows 10 dá suporte na [Referência do provedor do serviço de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) na biblioteca de documentação do Windows.

Nem todas as configurações são compatíveis com todas as versões do Windows 10. A tabela no tópico do Windows informa quais versões têm suporte para cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas no tópico. Para saber se o Intune oferece suporte à configuração desejada, abra o tópico para essa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.

## <a name="general-configuration-policy-settings"></a>Definições de política de configuração geral

Use a **política de configuração geral** do Microsoft Intune para Windows 10 para definir configurações internas para Windows 10 Desktop e dispositivos Windows 10 Mobile registrados.

### <a name="password"></a>Senha

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Exigir uma senha para desbloquear dispositivos**|-|
|**Tipo de senha necessária**|Especifica se a senha deve ser apenas numérica ou alfanumérica|
|**Tipo de senha necessária** - **Número mínimo de conjuntos de caracteres**| Especifica quantos dos conjuntos de caracteres (letras minúsculas, letras maiúsculas, números e símbolos) devem ser incluídos na senha|
|**Comprimento mínimo da senha**|Aplica-se somente ao Windows 10 Mobile|
|**Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado**.|Para dispositivos que executam o Windows 10: se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a entrada falhar o número de vezes que você especificar. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não será aplicada.<br>Para dispositivos que executam o Windows Mobile 10: depois que a entrada falhar o número de vezes que você especificar, o dispositivo será apagado.|
|**Minutos de inatividade antes que a tela se apague**|Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada|
|**Expiração da senha (dias)**|Especifica o período após o qual a senha do dispositivo deve ser alterada|
|**Lembrar histórico de senha**|Especifica se você deseja impedir que o usuário crie senhas usadas anteriormente|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo|
|**Exigir uma senha quando o dispositivo volta do estado ocioso**|Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo (somente para Windows 10 Mobile)|

### <a name="encryption"></a>Criptografia

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Exigir criptografia no dispositivo móvel**|Habilita a criptografia em dispositivos de destino<br>(Somente Windows 10 Mobile)|

### <a name="system"></a>System (sistema)

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir captura de tela**|Permite que o usuário capture a tela do dispositivo como uma imagem (somente para Windows 10 Mobile)|
|**Permitir cancelamento de registro manual**|Permite que o usuário exclua manualmente a conta de trabalho do dispositivo|
|**Permitir instalação de certificado raiz manual**|Aplica-se ao Windows 10 Mobile|
|**Permitir que o diagnóstico e os dados de uso sejam enviados à Microsoft**|Os possíveis valores são:<br><br>**Não** - Nenhum dado é enviado para a Microsoft<br>**Básico** – Informações limitadas são enviadas à Microsoft<br>**Avançado** - dados de diagnóstico avançados são enviados à Microsoft<br>**Completo (recomendado)** - Envia os mesmos dados que **Avançado**, além de dados adicionais sobre o estado do dispositivo|


### <a name="account-and-synchronization"></a>Conta e sincronização

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir conta da Microsoft**|Permite que o usuário associe uma conta da Microsoft ao dispositivo|
|**Permitir adicionar contas que não são da Microsoft manualmente**|Permite que o usuário adicione contas de email a dispositivos que não estão associadas uma conta da Microsoft|
|**Permitir a sincronização de configurações de contas da Microsoft**|Permitir configurações de dispositivo e aplicativo associadas a uma conta da Microsoft para sincronização entre dispositivos|

### <a name="microsoft-edge"></a>Microsoft Edge

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir o navegador da Web**|Permite o uso do navegador da Web Microsoft Edge no dispositivo<br>(Somente Windows 10 Mobile)|
|**Permitir sugestões de pesquisa na barra de endereços**|Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa|
|**Permitir tráfego intranet no Internet Explorer**|Permite que os usuários abram sites da intranet no Internet Explorer<br>(Somente Windows 10 Desktop)|
|**Permitir Não Rastrear**|Configura o navegador Microsoft Edge para enviar cabeçalhos Não Rastrear para sites visitados pelos usuários|
|**Habilitar SmartScreen**||
|**Permitir scripts ativos**|Permite que scripts, como JavaScript, sejam executados no navegador Edge|
|**Permitir pop-ups**|Aplica-se somente à área de trabalho do Windows 10|
|**Permitir cookies**||
|**Permitir Preenchimento Automático**|Habilita os usuários a alterarem as configurações de preenchimento automático no navegador<br>(Somente Windows 10 Desktop)|
|**Permitir Gerenciador de Senhas**|Habilita ou desabilita o recurso de Gerenciador de Senhas do Edge|
|**Local do Enterprise Mode Site List**|Especifica onde encontrar a lista de sites que será aberta no modo Enterprise. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop)|

### <a name="apps"></a>Aplicativos

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir repositório de aplicativos**|Aplica-se somente ao Windows 10 Mobile|



### <a name="cellular"></a>Celular

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permite roaming de dados**|Permitir roaming entre redes durante o acesso de dados|
|**Permitir VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular|
|**Permitir roaming de VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando estiver em roaming ou em uma rede celular|

### <a name="hardware"></a>Hardware

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir câmera**|-|
|**Permitir armazenamento removível**|Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo|
|**Permitir Wi-Fi**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir compartilhamento de Internet**|Permite o uso de compartilhamento de conexão com a Internet no dispositivo móvel|
|**Permitir configuração manual de Wi-Fi**|Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi<br>(Somente Windows 10 Mobile)|
|**Permitir conexão automática para pontos de acesso Wi-Fi gratuitos**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente|
|**Permitir localização geográfica**|Especifica se o dispositivo pode usar informações de serviços de localização|
|**Permitir NFC**|Permite que o dispositivo use sua funcionalidade de Comunicação a Curta Distância|
|**Permitir Bluetooth**|-|
|**Permitir modo detectável de Bluetooth**|Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth|
|**Permitir anúncios de Bluetooth**|Permite que os dispositivos recebam anúncios via Bluetooth|
|**Permitir a redefinição do telefone**|Controla se o usuário pode redefinir seu dispositivo para os padrões de fábrica|
|**Permitir conexão USB**|Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB|
|**Permitir modo AntiTheft**|Configure se o modo AntiTheft do Windows está habilitado|

### <a name="features"></a>Recursos

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir copiar e colar**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir gravação de voz**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir Cortana**|Habilitar ou desabilitar a assistente de voz Cortana|
|**Permitir notificações da central de ações**|Habilitar ou desabilitar notificações da central de ações na tela de bloqueio do dispositivo<br>(Somente Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Todas as configurações são somente para Windows 10 Desktop.

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir monitoramento em tempo real**|Habilita a verificação em tempo real de malware, spyware e outros softwares indesejados|
|**Habilitar o monitoramento de comportamento**|Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos|
|**Habilitar Sistema de Inspeção de Rede**|O NIS (Sistema de Inspeção de Rede) ajuda a proteger dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado|
|**Verificar todos os downloads**|Controla se o Defender examina todos os arquivos baixados da Internet|
|**Permitir verificação de script**|Permite que o Defender examine scripts que são usados no Internet Explorer|
|**Monitorar atividade de arquivo e programa**|Permite que o Defender monitore a atividade de arquivos e programas nos dispositivos|
|**Dias para acompanhar malware resolvido**|Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente. |
|**Permitir acesso à interface do usuário cliente**|Controla se a interface do usuário do Windows Defender fica oculta para usuários finais.<br>Quando alterada, esta configuração entra em vigor na próxima vez em que o computador do usuário for reiniciado.|
|**Agendar uma verificação rápida diária**|Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar|
|**Agendar uma verificação do sistema**|Permite agendar uma verificação de sistema completa ou rápida que ocorre regularmente no dia e hora que você selecionar|
|**Limitar o uso da CPU durante uma verificação**|Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**)|
|**Verificar arquivos mortos**|Permite que o Defender examine Verificar arquivamentos, como arquivos .zip ou .cab.|
|**Verificar mensagens de email**|Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo|
|**Verificar unidades removíveis**|Permite que o Defender examine unidades removíveis, como cartões USB|
|**Verificar unidades de rede mapeadas**|Permite que o Defender examine arquivos em unidades de rede mapeadas.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Verificar arquivos abertos de pastas compartilhadas na rede**|Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC).<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Intervalo de atualização de assinatura**|Especifica o intervalo no qual o Defender verifica novos arquivos de assinatura.|
|**Permitir proteção de nuvem**|Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.|
|**Solicitar aos usuários o envio de amostras**|Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados sejam enviados automaticamente para a Microsoft|
|**Detecção de Aplicativo Potencialmente Indesejado**|Protege dispositivos Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado.|
|**Arquivos e pastas a serem excluídos ao executar uma verificação ou usar a proteção em tempo real**|Adiciona um ou mais arquivos e pastas como **C:\Path** ou **ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.|
|**Extensões de arquivo a serem excluídas ao executar uma verificação ou usar a proteção em tempo real**|Adicionar uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Arquivos com essas extensões não serão incluídos em verificações em tempo real ou programadas.|
|**Processos a serem excluídos ao executar uma verificação ou usar a proteção em tempo real**|Adiciona um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos não serão incluídas em verificações em tempo real ou programadas.|


### <a name="updates"></a>Updates

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|---------------|
|**Permitir atualizações automáticas**|Permite atualizações automáticas. Defina as seguintes configurações para controlar o comportamento de atualização:<br />**Notificar o download**<br />**Instalação automática no tempo de manutenção**<br />**Instalação automática e reinicialização no tempo de manutenção**<br />**Instalar automaticamente e reiniciar no horário agendado**: observe que quando esta opção é selecionada, você também pode definir as seguintes configurações: **Suprimir notificação para usuário final** e **Defina o dia de instalação das atualizações agendadas**.<br>(Somente Windows 10 Desktop)|
|**Permitir recursos de pré-lançamento**|Permite que a Microsoft implante configurações e recursos de pré-lançamento em dispositivos Windows 10. Você pode selecionar para permitir apenas as configurações, ou todos os recursos e configurações de pré-lançamento a serem instalados.|

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
