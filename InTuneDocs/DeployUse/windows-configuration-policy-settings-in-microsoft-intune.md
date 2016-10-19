---
title: "Configurações de política do Windows | Microsoft Intune"
description: "Use a Política de configuração geral do Windows (Windows 8.1 e posterior) do Intune para definir as configurações para dispositivos Windows 8.1 e Windows 8 registrados."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 532bb416e1496fce02312e80eb4090fec9ed80ad
ms.openlocfilehash: 7df712388e8d069667e8864284e38fb6c89012f7


---

# Configurações de política do Windows no Microsoft Intune
Use a **Política de configuração geral do Windows (Windows 8.1 e posterior)** do Microsoft Intune para definir as seguintes configurações para dispositivos Windows 8, Windows 8.1 e Windows RT 8.1 registrados:

## Configurações de aplicabilidade

|Nome da configuração|Detalhes|
|----------------|----------------------------------|
|**Aplicar todas as configurações ao Windows 10**|Permite que as configurações desta política sejam aplicadas a dispositivos Windows 10 além de dispositivos Windows 8 e Windows 8.1.|

## Configurações de segurança

|Nome da configuração|Detalhes|
|----------------|------|
|**Tipo de senha necessária**|Especifica o tipo de senha necessário, como apenas com caracteres numéricos ou alfanuméricos.|
|**Tipo de senha necessária – número mínimo de conjuntos de caracteres**|Especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha. Há quatro conjuntos de caracteres: letras minúsculas, letras maiúsculas, símbolos e números. No entanto, para dispositivos iOS, essa configuração especifica o número de símbolos que devem ser incluídos na senha.|
|**Comprimento mínimo da senha**|Define o tamanho mínimo necessário (em caracteres) para a senha.|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Apagará o dispositivo se houver falha neste número de tentativas de entrada.|
|**Minutos de inatividade antes que a tela se apague**|Especifica o número de minutos que um dispositivo deve permanecer ocioso antes que uma senha seja necessária para desbloqueá-lo.|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|
|**Lembrar de histórico de senha**|Especifica se o usuário pode definir senhas usadas anteriormente.|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|
|**Permitir senha de imagem e PIN**|Habilita o uso de uma senha com imagem e PIN. Uma senha com imagem permite que o usuário entre fazendo gestos em uma imagem. Um PIN permite que os usuários entrem rapidamente com um código de quatro dígitos.|

## Configurações de criptografia

|Nome da configuração|Detalhes|
|----------------|-----|
|**Exigir criptografia no dispositivo móvel**<sup>1</sup>|Exige que os arquivos no dispositivo sejam criptografados.|
<sup>1</sup> Informações adicionais sobre dispositivos que executam o Windows 8.1

-   Para impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](http://support.microsoft.com/kb/3013816) em cada dispositivo.

-   Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.

-   Para a criptografia funcionar, o dispositivo deve atender aos requisitos de certificação de hardware [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) da Microsoft.

-   Quando você impõe a criptografia em um dispositivo, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive. Não é possível recuperar essa chave em nome de um usuário.

## Configurações de malware

|Nome da configuração|Detalhes|
|----------------|-----|
|**Requer firewall de rede**|Exige que o Firewall do Windows esteja ativado.|
|**Habilitar SmartScreen**|Exige o uso do Windows SmartScreen.|

## Configurações de sistema

|Nome da configuração|Detalhes|
|----------------|-------|
|**Requer atualizações automáticas**|Ativa a configuração de atualizações automáticas em dispositivos.|
|**Requer atualizações automáticas – Classificação mínima das atualizações a serem instaladas automaticamente**|Escolhe a classificação das atualizações que serão instaladas automaticamente:<br /><br />-   **Importante** – Instala todas as atualizações classificadas como importantes.<br />-   **Recomendado** – Instala todas as atualizações classificadas como importantes ou recomendadas.|
|**Controle de conta de usuário**|Exige o uso de UAC (Controle de Conta de Usuário ) em dispositivos.|
|**Permitir envio de dados diagnósticos**|Permite que o dispositivo envie informações de diagnóstico à Microsoft.|


## Configurações de nuvem – documentos e dados

|Nome da configuração|Detalhes|
|----------------|------|
|**URL de pastas de trabalho**|Define a URL da pasta de trabalho para permitir que os documentos sejam sincronizados em todos os dispositivos.|

## Configurações de email

|Nome da configuração|Detalhes|
|----------------|-----|
|**Tornar a conta da Microsoft opcional em aplicativo de correio do Windows**|Habilita o acesso ao aplicativo de Email do Windows sem uma conta da Microsoft.|

## Configurações de aplicativo - navegador

|Nome da configuração|Detalhes|
|----------------|-----|
|**Permitir preenchimento automático**|Habilita os usuários a alterarem as configurações de preenchimento automático no navegador.|
|**Permitir bloqueador de pop-up**|Habilita ou desabilita o bloqueador de pop-ups do navegador.|
|**Permitir plug-ins**|Habilita os usuários a adicionar plug-ins ao Internet Explorer.|
|**Permitir script ativo**|Habilita o navegador a executar scripts, como scripts do ActiveX.|
|**Permitir aviso de fraude**|Habilita ou desabilita avisos de sites fraudulentos potenciais.|
|**Permitir site de intranet para entrada de palavra única**|Habilita o uso de uma única palavra para direcionar o Internet Explorer a um site, como o Bing.|
|**Permitir detecção automática de rede intranet**|Permite configurar a segurança para sites de intranet no Internet Explorer.|
|**Nível de segurança para Internet**|Define o nível de segurança do Internet Explorer para sites da Internet.|
|**Nível de segurança para a intranet**|Define o nível de segurança do Internet Explorer para sites da intranet.|
|**Nível de segurança para sites confiáveis**|Configura o nível de segurança para a zona de sites confiáveis.|
|**Nível de segurança para sites restritos**|Configura o nível de segurança para a zona de sites restritos.|
|**Enviar cabeçalho Do Not Track**|Envia um cabeçalho Não Rastrear para os sites visitados no Internet Explorer.|
|**Permitir acesso ao menu Modo Empresarial**|Permite aos usuários acessar as opções de menu do modo Empresarial do Internet Explorer.<br>Se selecionar essa configuração, você também poderá especificar um **Local de relatório de log**, que contém uma URL para um relatório que mostra os sites para os quais os usuários ativaram o acesso do modo Empresarial.|
|**Local do Enterprise Mode Site List**|Especifica o local da lista de sites que usarão o modo Empresarial quando ele estiver ativo.|

## Configurações de recursos do dispositivo - celular

|Nome da configuração|Detalhes|
|----------------|----|
|**Permitir roaming de Dados**|Habilita o roaming de dados quando o dispositivo estiver em uma rede de celular.|



### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO2-->


