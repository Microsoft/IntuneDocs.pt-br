---
# required metadata

title: Configurações de política do Windows Phone 8.1 no Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurações de política do Windows Phone 8.1 no Microsoft Intune

## Definições de configuração geral

Use a **Política de configuração geral do Windows Phone** do Microsoft Intune para definir as seguintes configurações para dispositivos Windows Phone 8.1:

-   **Configurações de segurança de dispositivo móvel** – Escolha em uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidade do dispositivo.

-   **Aplicativos compatíveis e não compatíveis** - especifique uma lista de aplicativos que são compatíveis ou não com sua empresa. Dispositivos Windows Phone podem bloquear ou permitir a instalação desses aplicativos.

### Configurações de senha

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especifica se os usuários devem inserir uma senha para acessar os dispositivos.|Sim|Sim|
|**Tipo de senha necessária**|Especifica o tipo de senha necessária, por exemplo, apenas numérica ou alfanumérica.|Sim|Sim|
|**Tipo de senha necessária – número mínimo de conjuntos de caracteres**|Há quatro conjuntos de caracteres: minúsculas, maiúsculas, símbolos e números. Essa configuração especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha). No entanto, para dispositivos iOS, isso especifica que o número de caracteres de símbolo deve ser incluído na senha)|Sim|Sim|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres necessários na senha.|Sim|Sim|
|**Permitir senha simples**|Senhas simples incluem '0000' e '1234'|Sim|Sim|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Especifica o número de vezes que uma senha incorreta pode ser lembrada antes que o dispositivo seja apagado.|Sim|Sim|
|**Minutos de inatividade antes que a tela se apague**|Especifica a quantidade de tempo que um dispositivo deve permanecer ocioso antes que a tela seja bloqueada automaticamente.|Sim|Sim|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|Sim|Sim|
|**Lembrar de histórico de senha**|Especifica se as senhas usadas anteriormente devem ser lembradas para impedir o usuário de usá-las novamente.|Sim|Sim|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especifica quantas senhas usadas anteriormente devem ser lembradas.|Sim|Sim|

### Configurações de criptografia

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Exigir criptografia no dispositivo móvel**|Exige que os dados em dispositivos móveis com suporte sejam criptografados.<br>Para dispositivos Windows Phone 8, você deve definir esta opção para **Sim**.|Sim|Sim|

### Configurações de sistema

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir captura de tela**|Permite que o usuário capture o conteúdo da tela como um arquivo de imagem.|Não|Sim|
|**Permitir envio de dados diagnósticos**|Permite que o dispositivo envie informações de diagnóstico à Microsoft.|Não|Sim|

### Configurações de nuvem – contas e sincronização

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir conta da Microsoft**|Permite que uma conta da Microsoft seja vinculada ao dispositivo.|Não|Sim|

### Configurações de email

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir contas de email personalizadas**|Permite que o dispositivo se conecte a contas de email não Microsoft.|Não|Sim|

### Configurações de aplicativo - navegador

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir navegador da web**|Permite ou bloqueia o navegador da Web interno em dispositivos.|Não|Sim|

### Configurações de aplicativo - aplicativos

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir loja de aplicativo**|Permite que os usuários se conectem à loja de aplicativos do dispositivo.|Não|Sim|

### Configurações de recursos do dispositivo - hardware

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir câmera**|Permitir ou bloquear a câmera do dispositivo.|Não|Sim|
|**Permitir armazenamento removível**|Permite que o dispositivo use armazenamento removível, por exemplo, um cartão SD.|Sim|Sim|
|**Permitir Wi-Fi**|Habilita ou desabilita a funcionalidade Wi-Fi do dispositivo.|Não|Sim|
|**Permitir compartilhamento de Internet por Wi-Fi**|Permitir o uso de compartilhamento de Internet por Wi-Fi no dispositivo.|Não|Sim
|**Permitir conexão automática para liberar pontos de acesso Wi-Fi**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceitar automaticamente os termos de uso.|Não|Sim|
|**Permitir relatórios de pontos de acesso Wi-Fi**|Enviar informações sobre conexões Wi-Fi para ajudar a descobrir conexões próximas.|Não|Sim|
|**Permitir localização geográfica**|Permite que o dispositivo utilize informações de localização.|Não|Sim|
|**Permitir NFC**|Permite operações que usam comunicação a curta distância.|Não|Sim|
|**Permitir Bluetooth**|Habilita ou desabilita a funcionalidade Bluetooth do dispositivo.|Não|Sim|

### Configurações de recursos do dispositivo - recursos

|Nome da configuração|Detalhes|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Permitir copiar e colar**|Permitir a funcionalidade copiar e colar nos dispositivos.|Não|Sim|

### Configurações para aplicativos compatíveis e não compatíveis
Na lista **Aplicativos Compatíveis &amp; Incompatíveis**, especifique uma lista de aplicativos compatíveis ou incompatíveis usando as seguintes informações:

> [!NOTE]
> Uma única política só pode conter uma lista de compatibilidade ou de incompatibilidade. Não é possível especificar ambos na mesma política.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Bloquear a abertura dos aplicativos listados nos dispositivos**|Lista os aplicativos que não são gerenciados pelo Intune, para os quais os usuários não têm permissão para instalar e executar.|
|**Permitir somente a instalação dos aplicativos listados nos dispositivos**|Lista os aplicativos que os usuários têm permissão para instalar. Os usuários não podem instalar nenhum outro aplicativo. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.|
|**Adicionar**|Adiciona um aplicativo à lista selecionada. Especifique um nome da sua preferência, opcionalmente o editor do aplicativo, e a URL para o aplicativo na loja de aplicativos. Para obter mais ajuda, consulte “Como especificar URLs para lojas de aplicativos” mais adiante neste tópico.
|**Importar aplicativos**|Importa uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. Use o formato, nome do aplicativo, editor e a URL do aplicativo no arquivo.|
|**Editar**|Permite editar o nome, editor e a URL do aplicativo selecionado.|
|**Excluir**|Exclui o aplicativo selecionado da lista.|
> [!IMPORTANT]
> Se você especificar uma lista de aplicativos permitidos para dispositivos Windows Phone 8.1, deverá adicionar o aplicativo Portal da empresa a essa lista, caso contrário, ele será bloqueado.


### Informações de referência para aplicativos compatíveis e não compatíveis

#### Como especificar URLs para lojas de aplicativos
Para especificar uma URL de aplicativo na lista de aplicativos compatíveis e incompatíveis, use o seguinte formato:

Na [página Aplicativos+Jogos do Windows Phone](http://www.windowsphone.com/en-us/store/overview) , procure o aplicativo que você deseja usar.

Abra a página do aplicativo e copie a URL para a área de transferência. Agora você pode usar essa URL na lista de aplicativos compatíveis ou incompatíveis.

**Exemplo:** Procure o aplicativo Skype na loja. A URL usada será **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Configurações de política personalizada 
Use a **Política de configuração personalizada do Windows Phone** do Microsoft Intune para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em **dispositivos Windows Phone 8.1**. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você implante configurações do Windows Phone que não podem ser configuradas com a política de configuração geral do Intune. Para obter informações sobre as configurações que você pode definir com essas políticas, consulte [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune).

Para obter ajuda para a criação de configurações de OMA-URI para dispositivos Windows Phone, consulte [Windows Phone 8.1 MDM protocol documentation](http://technet.microsoft.com/library/dn499787.aspx) (Documentação do protocolo MDM do Windows Phone 8.1).

### Configurações gerais

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Nome**|Insira um nome exclusivo para a política para ajudar a identificá-la no console do Intune.|
|**Descrição**|Forneça uma descrição que proporciona uma visão geral da política e outras informações relevantes que o ajudarão a localizá-la.|

### Configurações de OMA-URI

Na seção de **Configurações de OMA-URI**, clique em **Adicionar** para adicionar uma configuração. Você também pode editar ou excluir uma configuração existente.

Na caixa de diálogo **Adicionar ou Editar Configuração de OMA-URI**, especifique as seguintes informações:

|Nome da configuração|Detalhes|
    |--------|--------------------|
    |**Nome da configuração**|Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.|
    |**Descrição da configuração**|Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que o ajudarão a localizá-la.|
    |**Tipo de dados**|Selecione o tipo de data em que você especificará essa configuração de OMA-URI. Escolha:<br /><br />-   **Cadeia de caracteres**<br />-   **Cadeia de caracteres (XML)**<br />-   **Data e hora**<br />-   **Inteiro**<br />-   **Ponto flutuante**<br />-   **Booliano**|
    |**OMA-URI (com distinção entre maiúsculas e minúsculas)**|Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
    |**Valor**|Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->

