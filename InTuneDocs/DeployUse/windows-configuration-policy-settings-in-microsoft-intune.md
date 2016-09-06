---
title: "Configurações de política do Windows | Microsoft Intune"
description: "Use a Política de configuração geral do Windows (Windows 8.1 e posterior) do Intune para definir as configurações para dispositivos Windows 8.1 e Windows 8 registrados."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7fdfe64a18fe359ee4b3b4507ef4108ad65ab573
ms.openlocfilehash: 3102e4637c61bbae002fb30947acd1f82204ac93


---

# Configurações de política do Windows no Microsoft Intune
Use a **Política de configuração geral do Windows (Windows 8.1 e posterior)** do Microsoft Intune para definir as seguintes configurações para dispositivos Windows 8.1 e Windows 8 registrados:

## Configurações de aplicabilidade

|Nome da configuração|Detalhes|
|----------------|----------------------------------|
|**Aplicar todas as configurações ao Windows 10**|Permite que as configurações desta política sejam aplicadas a dispositivos Windows 10 além de dispositivos Windows 8 e Windows 8.1.|

## Configurações de segurança

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Tipo de senha necessária**|Especifica o tipo de senha necessário, como apenas com caracteres numéricos ou alfanuméricos.|Sim|Sim|
|**Tipo de senha necessária – número mínimo de conjuntos de caracteres**|Especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha. Há quatro conjuntos de caracteres: letras minúsculas, letras maiúsculas, símbolos e números. No entanto, para dispositivos iOS, essa configuração especifica o número de símbolos que devem ser incluídos na senha.|Sim|Sim|
|**Comprimento mínimo da senha**<sup>1</sup>|Define o tamanho mínimo necessário (em caracteres) para a senha.|Sim|Sim|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Apagará o dispositivo se houver falha neste número de tentativas de entrada.|Sim|Sim|
|**Minutos de inatividade antes que a tela se apague**|Especifica o número de minutos que um dispositivo deve permanecer ocioso antes que uma senha seja necessária para desbloqueá-lo.| Sim|Sim|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|Sim|Sim|
|**Lembrar de histórico de senha**|Especifica se o usuário pode definir senhas usadas anteriormente.|Sim|Sim|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|Sim|Sim|
|**Permitir senha de imagem e PIN**|Habilita o uso de uma senha com imagem e PIN. Uma senha com imagem permite que o usuário entre fazendo gestos em uma imagem. Um PIN permite que os usuários entrem rapidamente com um código de quatro dígitos.|Sim|Sim|
<sup>1</sup> Quando você implantar uma política de tamanho da senha em dispositivos que executam o Windows RT, os usuários serão forçados a redefinir sua senha, mesmo que a senha atual esteja em conformidade com os requisitos da política.

## Configurações de criptografia

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Exigir criptografia no dispositivo móvel**<sup>1</sup>|Exige que os arquivos no dispositivo sejam criptografados.<br>Para dispositivos Windows Phone 8, defina como **Sim**.|Sim|Não|
<sup>1</sup> Informações adicionais sobre dispositivos que executam o Windows 8.1

-   Para impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](http://support.microsoft.com/kb/3013816) em cada dispositivo.

-   Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.

-   Para a criptografia funcionar, o dispositivo deve atender aos requisitos de certificação de hardware [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) da Microsoft.

-   Quando você impõe a criptografia em um dispositivo, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive. Não é possível recuperar essa chave em nome de um usuário.

## Configurações de malware

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Requer firewall de rede**|Exige que o Firewall do Windows esteja ativado.|Sim|Não|
|**Habilitar SmartScreen**|Exige o uso do Windows SmartScreen.|Sim|Não|

## Configurações de sistema

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Requer atualizações automáticas**|Ativa a configuração de atualizações automáticas em dispositivos.|Sim|Não|
|**Requer atualizações automáticas – Classificação mínima das atualizações a serem instaladas automaticamente**|Escolhe a classificação das atualizações que serão instaladas automaticamente:<br /><br />-   **Importante** – Instala todas as atualizações classificadas como importantes.<br />-   **Recomendado** – Instala todas as atualizações classificadas como importantes ou recomendadas.|Sim|Não|
|**Controle de conta de usuário**|Exige o uso de UAC (Controle de Conta de Usuário ) em dispositivos.|Sim|Não|
|**Permitir envio de dados diagnósticos**|Permite que o dispositivo envie informações de diagnóstico à Microsoft.|Sim|Não|


## Configurações de nuvem – documentos e dados

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**URL de pastas de trabalho**|Define a URL da pasta de trabalho para permitir que os documentos sejam sincronizados em todos os dispositivos.|Sim|Não|

## Configurações de email

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Tornar a conta da Microsoft opcional em aplicativo de correio do Windows**|Habilita o acesso ao aplicativo de Email do Windows sem uma conta da Microsoft.|Sim|Não|

## Configurações de aplicativo - navegador

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Permitir preenchimento automático**|Habilita os usuários a alterarem as configurações de preenchimento automático no navegador.|Sim|Não|
|**Permitir bloqueador de pop-up**|Habilita ou desabilita o bloqueador de pop-ups do navegador.|Sim|Não|
|**Permitir plug-ins**|Habilita os usuários a adicionar plug-ins ao Internet Explorer.|Sim|Não|
|**Permitir script ativo**|Habilita o navegador a executar scripts, como scripts do ActiveX.|Sim|Não|
|**Permitir aviso de fraude**|Habilita ou desabilita avisos de sites fraudulentos potenciais.|Sim|Não|
|**Permitir site de intranet para entrada de palavra única**|Habilita o uso de uma única palavra para direcionar o Internet Explorer a um site, como o Bing.|Sim|Não|
|**Permitir detecção automática de rede intranet**|Permite configurar a segurança para sites de intranet no Internet Explorer.|Sim|Não|
|**Nível de segurança para Internet**|Define o nível de segurança do Internet Explorer para sites da Internet.|Sim|Não|
|**Nível de segurança para a intranet**|Define o nível de segurança do Internet Explorer para sites da intranet.|Sim|Não|
|**Nível de segurança para sites confiáveis**|Configura o nível de segurança para a zona de sites confiáveis.|Sim|Não|
|**Nível de segurança para sites restritos**|Configura o nível de segurança para a zona de sites restritos.|Sim|Não|
|**Enviar cabeçalho Do Not Track**|Envia um cabeçalho Não Rastrear para os sites visitados no Internet Explorer.|Sim|Não|
|**Permitir acesso ao menu Modo Empresarial**|Permite aos usuários acessar as opções de menu do modo Empresarial do Internet Explorer.<br>Se selecionar essa configuração, você também poderá especificar um **Local de relatório de log**, que contém uma URL para um relatório que mostra os sites para os quais os usuários ativaram o acesso do modo Empresarial.|Sim|Não|
|**Local do Enterprise Mode Site List**|Especifica o local da lista de sites que usarão o modo Empresarial quando ele estiver ativo.|Sim|Não|

## Configurações de recursos do dispositivo - celular

|Nome da configuração|Detalhes|Windows 8.1 e Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Permitir roaming de Dados**|Habilita o roaming de dados quando o dispositivo estiver em uma rede de celular.|Sim|Não|



### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


