---

title: "Configurações de política do Android e Samsung KNOX | Microsoft Intune"
description: "Crie políticas que controlam as configurações e os recursos nos dispositivos Android que você gerencia com o Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8465ab2ead21b825141c1aa6e77c02a9b7061a66
ms.openlocfilehash: 5e7ba0d4546c13106e32359c9578a6f0a49d6de7


---

# Configurações de política do Android e Samsung KNOX no Microsoft Intune

O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos Android. Além disso, você pode especificar valores de OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para criar configurações personalizadas que não estão disponíveis no Intune.

## Política de configuração geral

Use a **Política de configuração geral do Android** do Intune para definir configurações para:

-   **Configurações de segurança de dispositivo móvel** – Escolha em uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidade do dispositivo.

-   **Modo de quiosque** (somente para dispositivos Samsung KNOX) – bloqueie um dispositivo para permitir que somente certos recursos funcionem. Por exemplo, você pode permitir que um dispositivo execute apenas um aplicativo gerenciado que você especificar ou pode desabilitar os botões de volume em um dispositivo. Essas configurações podem ser usadas para um modelo de demonstração de um dispositivo ou um dispositivo que é dedicado a apenas uma função, como um dispositivo de ponto de venda.

-   **Aplicativos compatíveis e não compatíveis** - especifique uma lista de aplicativos que são compatíveis ou não com sua empresa. Nos dispositivos Android e iOS, o **Relatório de aplicativos incompatíveis** pode ser usado para exibir a compatibilidade de aplicativos especificados na lista em relação as aplicativos que os usuários instalaram. O relatório não pode de fato bloquear a instalação do aplicativo.

> [!TIP]
> Você pode configurar os termos e condições de usuários para garantir que eles reconhecem que todos os aplicativos no seu dispositivo, incluindo aplicativos pessoais, serão avaliados, e aplicativos incompatíveis serão bloqueados, ou relatados como não compatível. Os usuários devem aceitar esses termos e condições antes de registrar seus dispositivos e usar o portal da empresa para obter aplicativos. Para saber mais sobre os termos e condições de uso, consulte [Terms and condition policy settings in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) (Configurações de políticas de termos e condições no Microsoft Intune).

Se a configuração que está procurando não aparecer nesse tópico, você poderá criá-la usando uma política personalizada do Android que lhe permite usar configurações de OMA-URI para controlar o dispositivo. Para obter mais informações, vá até [Configurações de política personalizadas](#custom-policy-settings) mais adiante neste tópico.

### Configurações de senha

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especifica se uma senha será exigida nos dispositivos com suporte.|Sim|Sim|
|**Comprimento mínimo da senha**|Especifica o comprimento mínimo da senha.|Sim|Sim|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Especifica o número de falhas de entrada repetidas permitido antes do dispositivo ser apagado.|Sim|Sim|
|**Minutos de inatividade antes que a tela se apague**|Especifica o número de minutos de inatividade antes de a tela do dispositivo ser bloqueada automaticamente.|Sim|Sim|
|**Expiração da senha (dias)**|Especifica o número de dias antes que uma senha precise ser alterada.|Sim|Sim|
|**Lembrar de histórico de senha**|Especifica o número de senhas usadas anteriormente que deverão ser lembradas.|Sim|Sim|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Evita a reutilização de senhas anteriores.|Sim|Sim|
|**Qualidade da senha**|Especifica o nível necessário de complexidade de senha e se dispositivos biométricos podem ser usados.|Sim|Sim|
|**Permitir desbloqueio de impressão digital**|Permite o uso de uma digital para desbloquear o dispositivo.|Não|Sim|
|**Permitir Smart Lock e outros agentes de confiança**<br>(Android 5 e posterior)|Permite controlar o recurso Smart Lock em dispositivos Android compatíveis. Essa capacidade do telefone, às vezes conhecida como agente de confiança, permitirá desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo estiver em um local confiável (por exemplo, quando ele está conectado a um dispositivo Bluetooth específico ou quando está perto de uma marca NFC). Você pode usar essa configuração para impedir que os usuários configurem o Smart Lock.|Sim|Não|

### Configurações de criptografia

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Exigir criptografia no dispositivo móvel**|Requer que os arquivos no dispositivo móvel sejam criptografados.|Sim|Sim|
|**Exigir criptografia em cartões de memória**|Especifica se o cartão de memória do dispositivo deve ser criptografado.|Não|Sim|

### Configurações de sistema

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir captura de tela**|Permite que o usuário capture o conteúdo da tela como uma imagem.|Não|Sim|
|**Permitir envio de dados diagnósticos**|Permite que o dispositivo envie informações de diagnóstico para o Google.|Não|Sim|
|**Permitir redefinição de fábrica**|Permite que o usuário execute uma redefinição de fábrica no dispositivo.|Não|Sim|

### Configurações de nuvem – documentos e dados

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------------------|----------------|
|**Permitir backup do Google**|Permite o uso do backup do Google.|Não|Sim|

### Configurações de nuvem – contas e sincronização

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir sincronização automática da conta do Google**|Permite que as configurações de conta do Google sejam sincronizadas automaticamente.|Não|Sim|

### Configurações de aplicativo - navegador

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir navegador da web**|Especifica se o navegador da Web padrão do dispositivo pode ser usado.|Não|Sim|
|**Permitir preenchimento automático**|Permite que a função de preenchimento automático do navegador da Web seja usada.|Não|Sim|
|**Permitir bloqueador de pop-up**|Permite o uso do bloqueador de pop-up no navegador da Web.|Não|Sim|
|**Permitir cookies**|Permite que o navegador da Web do dispositivo use cookies.|Não|Sim|
|**Permitir script ativo**|Permite que o navegador da Web do dispositivo use script ativo.|Não|Sim|

### Configurações de aplicativo - aplicativos

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir armazenamento do Google Play**|Permite ao usuário acessar o Google Play Store no dispositivo.|Não|Sim|

### Configurações de recursos do dispositivo - hardware

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir câmera**|Permite o uso da câmera do dispositivo.|Sim|Sim|
|**Permitir armazenamento removível**|Permite que o dispositivo use o armazenamento removível, como um cartão SD.|Não|Sim|
|**Permitir Wi-Fi**|Permite o uso das funcionalidades de Wi-Fi do dispositivo.|Não|Sim|
|**Permitir compartilhamento de Internet por Wi-Fi**|Permite o uso de compartilhamento de Internet por Wi-Fi no dispositivo.|Não|Sim|
|**Permitir localização geográfica**|Permite que o dispositivo utilize informações de localização.|Não|Sim|
|**Permitir NFC**|Permite operações que usam comunicação de curta distância se o dispositivo der suporte a ela.|Não|Sim|
|**Permitir Bluetooth**|Permite o uso de Bluetooth no dispositivo.|Não|Sim|
|**Permitir desligamento**|Permite que o usuário desligue o dispositivo.<br /><br />Se essa configuração estiver desabilitada, a configuração **Número de falhas de entrada repetidas permitido antes do apagamento do dispositivo** não funcionará para dispositivos Samsung KNOX.|Não|Sim|

### Configurações de recursos do dispositivo - celular

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir roaming de Voz**|Permite roaming de voz quando o dispositivo estiver em uma rede de celular.|Não|Sim|
|**Permitir roaming de Dados**|Permite roaming de dados quando o dispositivo estiver em uma rede de celular.|Não|Sim|
|**Permitir mensagens SMS/MMS**|Permite o uso de mensagens SMS e MMS no dispositivo.|Não|Sim|

### Configurações de recursos do dispositivo - recursos

|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Permitir assistência de voz**|Permite o uso de software do assistente de voz no dispositivo.|Não|Sim|
|**Permitir discagem de voz**|Habilita ou desabilita o recurso de discagem de voz no dispositivo.|Não|Sim|
|**Permitir copiar e colar**|Permite as funções de copiar e colar no dispositivo.|Não|Sim|
|**Permitir compartilhamento de área de transferência entre aplicativos**|Permite o uso da área de transferência para copiar e colar entre aplicativos.|Não|Sim|
|**Permitir YouTube**|Permite o uso do YouTube no dispositivo.|Não|Sim|

### Configurações para aplicativos compatíveis e não compatíveis
Na lista **Aplicativos Compatíveis &amp; Incompatíveis**, especifique uma lista de aplicativos compatíveis ou incompatíveis que usam as seguintes informações:

> [!NOTE]
> Uma única política só pode conter somente uma lista de aplicativos compatíveis ou de aplicativos incompatíveis. Não é possível especificar ambos na mesma política.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Reportar não conformidade quando os usuários instalam os aplicativos listados**|Lista os aplicativos que não são gerenciados pelo Intune e os que você não deseja que os usuários instalem e executem. Se os usuários instalarem um desses aplicativos, ele será listado no relatório de aplicativos não compatíveis.|
|**Não relatar não conformidade quando os usuários instalam os aplicativos listados**|Lista os aplicativos que você deseja permitir. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.|
|**Adicionar**|Adiciona um aplicativo à lista selecionada. Especifique o nome do aplicativo, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.<br /><br />Para obter mais informações, consulte [Especificar URLs para lojas de aplicativos](#specify-urls-to-app-stores) mais adiante neste tópico.|
|**Importar aplicativos**|Importa uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. Use o formato, nome do aplicativo, editor e a URL do aplicativo no arquivo.|
|**Editar**|Permite editar o nome, editor e a URL do aplicativo selecionado.|
|**Excluir**|Exclui o aplicativo selecionado da lista.|

### Configurações do modo de quiosque
Especifique as configurações a seguir para **dispositivos Samsung KNOX**:

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Selecione um aplicativo gerenciado que poderá ser executado quando o dispositivo estiver em modo de quiosque**|Selecione **Procurar** e, em seguida, selecione o aplicativo gerenciado que poderá ser executado quando o dispositivo estiver no modo de quiosque (aplicativos especificados como um link para a loja não tem suporte no momento). Nenhum outro aplicativo poderá ser executado no dispositivo.|
|**Permitir o uso dos botões de volume**|Habilita ou desabilita o uso dos botões de volume no dispositivo.|
|**Permitir que o botão de ativação e suspensão da tela**|Habilita ou desabilita o botão de ativação e suspensão da tela no dispositivo.|

### Informações de referência para aplicativos compatíveis e não compatíveis

#### Monitore aplicativos compatíveis e não compatíveis
Use o **Relatório de aplicativos incompatíveis** para exibir a compatibilidade de aplicativos permitidos e bloqueados.

###### Executar o relatório de aplicativos incompatíveis

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Relatórios** &gt; **Relatório de Aplicativos Incompatíveis**.

2.  Selecione os grupos de dispositivos que deseja verificar. Depois, escolha se deseja verificar se há aplicativos compatíveis, aplicativos incompatíveis ou ambos. Por fim, escolha **Exibir Relatório**.

#### Especificar URLs para lojas de aplicativos
Para especificar uma URL de aplicativo na lista de aplicativos compatíveis e incompatíveis, siga estas etapas:

Na [seção Aplicativos do Google Play](https://play.google.com/store/apps), pesquise o aplicativo que você deseja usar.

Abra a página de instalação do aplicativo e copie a URL para a área de transferência. Agora você pode usar essa URL na lista de aplicativos compatíveis ou incompatíveis.

Exemplo: pesquise Google Play para Microsoft Office Mobile. A URL usada será **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Configurações de política personalizada
Use a **Política de configuração personalizada do Android** do Microsoft Intune para implantar configurações OMA-URI, que podem ser usadas para controlar funcionalidades em dispositivos Android. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você implante configurações do Android que não são configuráveis com as políticas do Intune.

> [!NOTE]
> Atualmente, as políticas personalizadas do Android dão suporte apenas à definição de configurações de Wi-Fi para dispositivos Android que incluem uma chave pré-compartilhada.

### Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política personalizada do Android para ajudar a identificá-la no console do Intune.|
    |**Descrição**|Forneça uma descrição que dê uma visão geral da política personalizada do Android e outras informações relevantes que o ajudarão a localizá-la.|

### Configurações de OMA-URI

   |Nome da configuração|Detalhes|
    |--------|--------------------|
    |**Nome da configuração**|Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.|
    |**Descrição da configuração**|Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que o ajudarão a localizá-la.|
    |**Tipo de dados**|Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha **Cadeia de Caracteres, Cadeia de Caracteres (XML), Data e Hora, Número Inteiro, Ponto Flutuante**, ou **Booliano**.|
    |**OMA-URI (com distinção entre maiúsculas e minúsculas)**|Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
    |**Valor**|Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|

### Exemplos

- [Para criar um perfil de Wi-Fi com uma chave pré-compartilhada](pre-shared-key-wi-fi-profile.md)
- [Usar uma política personalizada para criar um perfil de VPN por aplicativo para dispositivos Android](per-app-vpn-for-android-pulse-secure.md)

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO1-->


