---
title: "Configurações de política do Windows Phone 8.1 | Microsoft Intune"
description: "O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos Windows Phone 8.1. Além disso, você pode especificar valores de OMA-URI para criar configurações personalizadas que não estão disponíveis no Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: 3c9c75e5e9e19574a5b4525688103dc95e3d6b9b


---

# Configurações de política do Windows Phone 8.1 no Microsoft Intune

O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos Windows Phone 8.1. Além disso, você pode especificar valores de OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para criar configurações personalizadas que não estão disponíveis no Intune.

## Definições de configuração geral

Use a **Política de configuração geral do Windows Phone (Windows Phone 8.1 e posterior)** do Microsoft Intune para definir as seguintes configurações para dispositivos Windows Phone 8.1:

-   **Configurações de segurança de dispositivo móvel** – Escolha em uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidade do dispositivo.

-   **Aplicativos compatíveis e não compatíveis** – Especifique uma lista de aplicativos compatíveis ou não com sua empresa. Dispositivos Windows Phone podem bloquear ou permitir a instalação desses aplicativos.

### Configurações de aplicabilidade

|Nome da configuração|Detalhes|
|----------------|----------------------------------|
|**Aplicar todas as configurações ao Windows 10**|Permite que as configurações desta política sejam aplicadas a dispositivos Windows 10 Mobile e dispositivos Windows Phone 8.1.|

### Configurações de senha

|Nome da configuração|Detalhes|
|----------------|------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especifica se os usuários devem inserir uma senha para acessar os dispositivos.|
|**Tipo de senha necessária**|Especifica o tipo de senha que será necessário, como apenas com caracteres numéricos ou alfanuméricos.|
|**Tipo de senha necessária – número mínimo de conjuntos de caracteres**|Especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha. Há quatro conjuntos de caracteres: letras minúsculas, letras maiúsculas, símbolos e números. No entanto, para dispositivos iOS, isso especifica que o número de símbolos que devem ser incluídos na senha.|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres necessários na senha.|
|**Permitir senha simples**|Especifica que senhas simples, como “0000” e “1234”, podem ser usadas.|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Especifica o número de vezes que uma senha incorreta pode ser inserida antes que o dispositivo seja apagado.|
|**Minutos de inatividade antes que a tela se apague**|Especifica a quantidade de tempo que um dispositivo deve permanecer ocioso antes que a tela seja bloqueada automaticamente.|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|Sim|Sim|
|**Lembrar de histórico de senha**|Especifica se as senhas usadas anteriormente devem ser lembradas para impedir o usuário de usá-las novamente.|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especifica quantas senhas usadas anteriormente devem ser lembradas.|

### Configurações de criptografia

|Nome da configuração|Detalhes|
|----------------|------|
|**Exigir criptografia no dispositivo móvel**|Exige que os dados em dispositivos móveis com suporte sejam criptografados.|

### Configurações de sistema

|Nome da configuração|Detalhes|
|----------------|-----|
|**Permitir captura de tela**|Permite que o usuário capture o conteúdo da tela como um arquivo de imagem.|
|**Permitir envio de dados diagnósticos**|Permite que o dispositivo envie informações de diagnóstico à Microsoft.|

### Configurações de nuvem – contas e sincronização

|Nome da configuração|Detalhes|
|----------------|------|
|**Permitir conta da Microsoft**|Permite que uma conta da Microsoft seja vinculada ao dispositivo.|

### Configurações de email

|Nome da configuração|Detalhes|
|----------------|-----|
|**Permitir contas de email personalizadas**|Permite que o dispositivo se conecte a contas de email não Microsoft.|

### Configurações de aplicativo - navegador

|Nome da configuração|Detalhes|
|----------------|-----|
|**Permitir navegador da web**|Permite ou bloqueia o navegador da Web interno em dispositivos.|

### Configurações de aplicativo - aplicativos

|Nome da configuração|Detalhes|
|----------------|-----|
|**Permitir loja de aplicativo**|Permite que os usuários se conectem à loja de aplicativos do dispositivo.|

### Configurações de recursos do dispositivo - hardware

|Nome da configuração|Detalhes|
|----------------|-----|
|**Permitir câmera**|Permite ou bloqueia a câmera do dispositivo.|
|**Permitir armazenamento removível**|Permite que o dispositivo use armazenamento removível, como cartões SD.|
|**Permitir Wi-Fi**|Habilita ou desabilita a funcionalidade Wi-Fi do dispositivo.|
|**Permitir compartilhamento de Internet por Wi-Fi**|Permite o uso de compartilhamento de Internet por Wi-Fi no dispositivo.|
|**Permitir conexão automática para liberar pontos de acesso Wi-Fi**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite automaticamente os termos de uso.|
|**Permitir relatórios de pontos de acesso Wi-Fi**|Envia informações sobre conexões Wi-Fi para ajudar o usuário a descobrir conexões próximas.|
|**Permitir localização geográfica**|Permite que o dispositivo utilize informações de localização.|
|**Permitir NFC**|Permite operações que usam comunicação a curta distância.|
|**Permitir Bluetooth**|Habilita ou desabilita a funcionalidade Bluetooth do dispositivo.|

### Configurações de recursos do dispositivo - recursos

|Nome da configuração|Detalhes|
|----------------|----|
|**Permitir copiar e colar**|Permitir a funcionalidade copiar e colar nos dispositivos.|

### Configurações para URLs permitidas e bloqueadas
Na lista de **Aplicativos permitidos e bloqueados**, especifique uma lista de aplicativos que você deseja permitir ou bloquear usando as seguintes informações:

> [!NOTE]
> Uma única política só pode conter uma lista de aplicativos permitidos ou bloqueados. Não é possível especificar ambos na mesma política.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Bloquear a abertura dos aplicativos listados nos dispositivos**|Lista os aplicativos que não são gerenciados pelo Intune, os quais os usuários não têm permissão para instalar e executar.|
|**Permitir somente a instalação dos aplicativos listados nos dispositivos**|Lista os aplicativos que os usuários têm permissão para instalar. Os usuários não podem instalar nenhum outro aplicativo. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.|
|**Adicionar**|Adiciona um aplicativo à lista selecionada. Especifique um nome da sua preferência, a URL para o aplicativo na loja de aplicativos e o editor do aplicativo (opcional). Para obter mais ajuda, consulte “Como especificar URLs para lojas de aplicativos” mais adiante neste tópico.
|**Importar aplicativos**|Importa uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. Use o formato, nome do aplicativo, editor e a URL do aplicativo no arquivo.|
|**Editar**|Permite editar o nome, editor e a URL do aplicativo selecionado.|
|**Excluir**|Exclui o aplicativo selecionado da lista.|
> [!IMPORTANT]
> Se especificar uma lista de aplicativos permitidos para dispositivos Windows Phone 8.1, você deverá adicionar o aplicativo Portal da Empresa a essa lista, caso contrário, ele será bloqueado.


### Informações de referência para aplicativos permitidos e bloqueados

#### Como especificar URLs para lojas de aplicativos
Para especificar uma URL de aplicativo na lista de aplicativos permitidos e bloqueados, use o seguinte formato:

Na [página Aplicativos+Jogos do Windows Phone](http://www.windowsphone.com/en-us/store/overview), procure o aplicativo que você deseja usar.

Abra a página do aplicativo e copie a URL para a área de transferência. Agora você pode usar isso como a URL em uma lista de aplicativos permitidos ou bloqueados.

**Exemplo:** Procure o aplicativo Skype na loja. A URL usada será **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Configurações de política personalizada
Use a **Política de configuração personalizada do Windows Phone** do Microsoft Intune para implantar configurações OMA-URI, que podem ser usadas para controlar funcionalidades em **dispositivos com Windows Phone 8.1**. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade possibilita que você implante configurações do Windows Phone que não podem ser configuradas com a política de configuração geral do Intune. Para obter informações sobre as configurações que você pode definir com essas políticas, consulte [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune).

Para obter ajuda para criar configurações de OMA-URI para dispositivos Windows Phone, consulte [Documentação do protocolo MDM do Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx).

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
    |**Tipo de dados**|Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha:<br /><br />-   **Cadeia de caracteres**<br />-   **Cadeia de caracteres (XML)**<br />-   **Data e hora**<br />-   **Inteiro**<br />-   **Ponto flutuante**<br />-   **Booliano**|
    |**OMA-URI (com distinção entre maiúsculas e minúsculas)**|Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
    |**Valor**|Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO2-->


