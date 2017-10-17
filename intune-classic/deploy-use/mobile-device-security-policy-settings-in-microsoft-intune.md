---
title: "Configurações de política de segurança para dispositivos móveis"
description: "Use o Intune para definir uma ampla variedade de configurações que você pode implantar em dispositivos gerenciados na sua organização."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 34da6fb95a6a2b292f8f2e1d787bef179fe2301b
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="mobile-device-security-policy-settings-in-microsoft-intune"></a>Configurações de política de segurança de dispositivo móvel no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

> [!IMPORTANT]
> Agora, o Microsoft Intune apresenta políticas de configuração separadas para cada plataforma de dispositivo. Essas políticas contêm as configurações mais atualizadas que você pode usar. Você pode continuar usando a política de segurança de dispositivo móvel e todas as implantações existentes ainda funcionarão. No entanto, você deve planejar a migração para as novas políticas de configuração assim que possível, pois a política de segurança de dispositivo móvel será removida no futuro.

Você pode usar políticas de segurança de dispositivo móvel do Intune para configurar uma ampla variedade de configurações que pode implantar em dispositivos gerenciados na sua organização. Essas configurações são usadas para controlar a funcionalidade e a segurança de seus dispositivos.

Você pode criar e implantar políticas de segurança de dispositivo móvel para os seguintes tipos de dispositivo:

-   Dispositivos Windows RT 8.1 e Windows 8.1 registrados

-   Windows RT

-   Windows Phone 8 e Windows Phone 8.1

-   iOS

-   Android e Samsung KNOX Standard

> [!NOTE]
> Algumas configurações não são aplicáveis a alguns dispositivos. Consulte a tabela abaixo para obter uma lista completa das configurações que você pode definir.
> A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para aplicativos do Portal da Empresa do Windows 8. O Microsoft Intune também preterirá o suporte para as plataformas Windows Phone 8 e WinRT. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8 ou WinRT. É possível continuar a gerenciar dispositivos Windows Phone 8, WinRT e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.

## <a name="security-settings"></a>Configurações de segurança

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Não|Não|Sim|Sim|Sim|
|**Tipo de senha necessária**<br /><br />Esta configuração especifica o tipo de senha que será necessário, apenas com caracteres numéricos ou alfanuméricos.|Sim|Sim|Sim|Sim|Não|
|**Tipo de senha necessária – número mínimo de conjuntos de caracteres**<br /><br />Há quatro conjuntos de caracteres: letras minúsculas, letras maiúsculas, símbolos e números. Essa configuração especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha. No entanto, para dispositivos iOS, ela especifica o número de caracteres de símbolo que devem ser incluídos na senha.|Sim|Sim|Sim|Sim|Não|
|**Comprimento mínimo da senha**|Sim|Sim|Sim|Sim|Sim|
|**Permitir senha simples**<br /><br />Senhas simples incluem “0000” e “1234”.|Não|Não|Sim|Sim|Não|
|**Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado**|Sim|Sim|Sim|Sim|Sim|
|**Minutos de inatividade antes que a tela se apague**<sup>1</sup>|Sim|Sim|Sim|Sim|Sim|
|**Expiração da senha (dias)**|Sim|Sim|Sim|Sim|Sim|
|**Lembrar histórico de senha**|Sim|Sim|Sim|Sim|Sim|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Sim|Sim|Sim|Sim|Sim|
|**Qualidade da senha**|Não|Não|Não|Não|Sim|
|**Permitir senha de imagem e PIN**|Sim|Sim|Não|Não|Não|
|**Minutos de inatividade antes de a senha ser necessária**|Não|Não|Não|Sim|Não|
|**Permitir desbloqueio por impressão digital**|Não|Não|Não|iOS 7 e posterior|Não|
<sup>1</sup>Para dispositivos iOS, ao definir as configurações **Minutos de inatividade antes que a tela seja desligada** e **Minutos de inatividade antes que a senha seja solicitada**, elas serão aplicadas em sequência. Por exemplo, se você define o valor de ambas as configurações para **5** minutos, a tela desliga automaticamente após 5 minutos e o dispositivo é bloqueado após outros 5 minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo é bloqueado 5 minutos depois de o usuário desligar a tela.

Quando você implantar uma política de tamanho da senha em dispositivos que executam o Windows RT, os usuários serão forçados a redefinir sua senha, mesmo que a senha atual esteja em conformidade com os requisitos da política.

## <a name="encryption-settings"></a>Configurações de criptografia

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exigir criptografia no dispositivo móvel**<sup>1</sup><br /><br />Para dispositivos Windows Phone 8, defina como **Sim**.<br /><br />Para habilitar a criptografia em dispositivos iOS, habilite a configuração **Exigir senha para desbloquear dispositivos móveis**.|Sim|Não|Sim|Não|Sim|
|**Exigir criptografia em cartões de armazenamento**<br /><br />Esta configuração se aplica também a dispositivos gerenciados pelo Exchange ActiveSync.|N/D|N/D|N/D <br />Aplicativos e dados associados são criptografados automaticamente.|N/D|Sim|
<sup>1</sup>Consulte mais informações sobre dispositivos que executam o Windows 8.1:

-   Para impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](http://support.microsoft.com/kb/3013816) em cada dispositivo.

-   Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.

-   Para a criptografia funcionar, o dispositivo deve atender aos requisitos de certificação de hardware [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) da Microsoft.

-   Quando você impõe a criptografia em um dispositivo, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive. Não é possível recuperar essa chave em nome de um usuário.

## <a name="malware-settings"></a>Configurações de malware

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exigir firewall de rede**|Sim|Não|Não|Não|Não|
|**Habilitar SmartScreen**|Sim|Não|Não|Não|Não|

## <a name="system-settings"></a>Configurações de sistema

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exigir atualizações automáticas**|Sim|Não|Não|Não|Não|
|**Exigir atualizações automáticas – Classificação mínima das atualizações a serem instaladas automaticamente**<br /><br />Escolha a classificação das atualizações que serão instaladas automaticamente:<br /><br />- **Importante**. Instala todas as atualizações classificadas como importantes.<br /><br />- **Recomendado**. Instala todas as atualizações classificadas como importantes ou recomendadas.|Sim|Não|Não|Não|Não|
|**Permitir captura de tela**|Não|Não|Somente Windows Phone 8.1|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir centro de controle na tela de bloqueio**|Não|Não|Não|iOS 7 e posterior|Não|
|**Permitir exibição de notificação na tela de bloqueio**|Não|Não|Não|iOS 7 e posterior|Não|
|**Permitir exibição atual na tela de bloqueio**|Não|Não|Não|iOS 7 e posterior|Não|
|**Controle de conta de usuário**|Sim|Não|Não|Não|Não|
|**Permitir envio de dados de diagnóstico**|Sim|Não|Somente Windows Phone 8.1|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir certificados TLS não confiáveis**|Não|Não|Não|Sim|Não|
|**Permitir o software de carteira pessoal enquanto estiver bloqueado**|Não|Não|Não|Sim|Não|
|**Permitir redefinição de fábrica**|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|


## <a name="cloud-settings--documents-and-data"></a>Configurações de nuvem – documentos e dados

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir backup no iCloud**|Não|Não|Não|Sim|Não|
|**Permitir sincronização de documento no iCloud**|Não|Não|Não|Sim|Não|
|**Permitir sincronização do Fluxo de Fotos para o iCloud**|Não|Não|Não|Sim|Não|
|**Exigir backup criptografado**|Não|Não|Não|Sim|Não|
|**URL de pastas de trabalho**<br /><br />Esta configuração define a URL da pasta de trabalho para permitir que os documentos sejam sincronizados em todos os dispositivos.|Sim|Não|Não|Não|Não|
|**Permitir backup do Google**|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|

## <a name="cloud-settings--accounts-and-synchronization"></a>Configurações de nuvem – contas e sincronização

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir conta da Microsoft**|Não|Não|Somente Windows Phone 8.1|Não|Não|
|**Permitir sincronização automática da conta do Google**|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|

## <a name="email-settings"></a>Configurações de email

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir que os usuários baixem anexos de email**<sup>1</sup>|N/D|N/D|N/D|N/D|N/D|
|**Período de sincronização de email** <br /><br />Esta configuração se aplica também a dispositivos gerenciados pelo Exchange ActiveSync.|N/D|N/D|N/D|N/D|N/D|
|**Permitir que dispositivos móveis que não dão suporte total a essas configurações sejam sincronizados com o Exchange (Exchange ActiveSync)** <br /><br />Esta configuração se aplica também a dispositivos gerenciados pelo Exchange ActiveSync.|N/D|N/D|N/D|N/D|N/D|
|**Tornar a conta da Microsoft opcional em um aplicativo Windows Mail**|Sim|Não|Não|Não|Não|
|**Permitir contas de email personalizadas**|Não|Não|Somente Windows Phone 8.1|Não|Não|

## <a name="application-settings---browser"></a>Configurações de aplicativo - navegador

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir o navegador da Web**|Não|Não|Somente Windows Phone 8.1|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir preenchimento automático**|Sim|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir bloqueador de pop-up**|Sim|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir cookies**|Não|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir plug-ins**|Sim|Não|Não|Não|Não|
|**Permitir scripts ativos**|Sim|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir aviso de fraude**|Sim|Não|Não|Sim|Não|
|**Permitir site de intranet para entrada de palavra única**<br /><br />(Esta configuração permite o uso de uma única palavra para direcionar o Internet Explorer a um site – por exemplo, “Bing”.)|Sim|Não|Não|Não|Não|
|**Permitir detecção automática de rede intranet**|Sim|Não|Não|Não|Não|
|**Nível de segurança para Internet**|Sim|Não|Não|Não|Não|
|**Nível de segurança para a intranet**|Sim|Não|Não|Não|Não|
|**Nível de segurança para sites confiáveis**|Sim|Não|Não|Não|Não|
|**Nível de segurança para sites restritos**|Sim|Não|Não|Não|Não|
|**Enviar cabeçalho Não Rastrear**|Sim|Não|Não|Não|Não|
|**Permitir o acesso ao menu em Modo Empresarial**|Sim|Não|Não|Não|Não|
|**Local do Enterprise Mode Site List**|Sim|Não|Não|Não|Não|

## <a name="application-settings---apps"></a>Configurações de aplicativo - aplicativos

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir repositório de aplicativos**|Não|Não|Somente Windows Phone 8.1|Sim|Sim (Samsung KNOX Standard somente)|
|**Exigir uma senha para acessar o repositório de aplicativos**|Não|Não|Não|Sim|Não|
|**Permitir compras no aplicativo**|Não|Não|Não|Sim|Não|
|**Permitir documentos gerenciados em outros aplicativos não gerenciados**|Não|Não|Não|iOS 7 e posterior|Não|
|**Permitir documentos não gerenciados em outros aplicativos gerenciados**|Não|Não|Não|iOS 7 e posterior|Não|
|**Permitir videoconferência**|Não|Não|Não|Sim|Não|
|**Permitir conteúdo somente para adultos no repositório de mídia**|Não|Não|Não|Sim|Não|
|**Permitir instalação de aplicativos**|Não|Não|Não|iOS 6 e posterior|Não|

## <a name="application-settings---gaming"></a>Configurações de aplicativo - jogos

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir amigos no Game Center**|Não|Não|Não|Sim|Não|
|**Permitir jogo para vários participantes**|Não|Não|Não|Sim|Não|

## <a name="device-capabilities-settings---hardware"></a>Configurações de recursos do dispositivo - hardware

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir câmera**|Não|Não|Somente Windows Phone 8.1|Sim|Sim|
|**Permitir armazenamento removível**|Não|Não|Sim|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir Wi-Fi**|Não|Não|Somente Windows Phone 8.1|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir compartilhamento de internet por Wi-Fi**|Não|Não|Somente Windows Phone 8.1|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir conexão automática para pontos de acesso Wi-Fi gratuitos**|Não|Não|Somente Windows Phone 8.1|Não|Não|
|**Permitir relatório de ponto de acesso Wi-Fi**<br /><br />Esta configuração envia informações sobre conexões Wi-Fi para ajudar a descobrir conexões próximas.|Não|Não|Somente Windows Phone 8.1|Não|Não|
|**Permitir localização geográfica**<br /><br />Esta configuração permite que o dispositivo utilize informações de localização.|Não|Não|Somente Windows Phone 8.1|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir NFC**<br /><br />Esta configuração permite operações que usam comunicação a curta distância.|Não|Não|Somente Windows Phone 8.1|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir Bluetooth**|Não|Não|Somente Windows Phone 8.1|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir desligamento**<br>Se essa configuração estiver desabilitada, a configuração **Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado** não funcionará para dispositivos Samsung KNOX Standard.|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|

## <a name="device-capabilities-settings---cellular"></a>Configurações de recursos do dispositivo - celular

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir roaming de voz**|Não|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir roaming de dados**|Sim|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir sincronização automática enquanto em roaming**|Não|Não|Não|Sim|Não|
|**Permitir mensagens SMS/MMS**|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|

## <a name="device-capabilities-settings---features"></a>Configurações de recursos do dispositivo - recursos

|Nome da configuração|Windows 8.1 e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|iOS|Android e Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Permitir assistente de voz**|Não|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir assistente de voz quando o dispositivo estiver bloqueado**|Não|Não|Não|Sim|Não|
|**Permitir discagem de voz**|Não|Não|Não|Sim|Sim (Samsung KNOX Standard somente)|
|**Permitir copiar e colar**|Não|Não|Somente Windows Phone 8.1|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir compartilhamento de área de transferência entre aplicativos**|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|
|**Permitir YouTube**|Não|Não|Não|Não|Sim (Samsung KNOX Standard somente)|

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
