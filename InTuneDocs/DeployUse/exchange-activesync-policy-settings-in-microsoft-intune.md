---
title: "Configurações de política do Exchange ActiveSync | Microsoft Intune"
description: "Use a política do Exchange ActiveSync do Intune para definir as configurações que permitem controlar recursos e funcionalidades em dispositivos gerenciados pelo Exchange ActiveSync."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 727d28cff074124b5401f6c2931f87df3a9d2d23
ms.openlocfilehash: d8f7de4013c1bdf6174cd4e1d7491514b11a14a3


---

# Configurações de política do Exchange ActiveSync no Microsoft Intune
Use a política do **Exchange ActiveSync** do Microsoft Intune para definir configurações que controlam diversos recursos e funcionalidades em dispositivos que são gerenciados pelo Exchange ActiveSync.


## Configurações de senha

|Nome da configuração|Detalhes
|----------------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especifica se os dispositivos devem ser bloqueados usando uma senha.<br>(não aplicável a dispositivos que executam o Windows RT).|
|**Tipo de senha necessária**|Especifica o tipo de senha necessária, por exemplo, apenas numérica ou alfanumérica.|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres necessários na senha do dispositivo.|
|**Permitir senha simples**|Especifica se você pode usar senhas simples, que incluem '0000' e '1234'.|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Especifica o número de vezes em que o usuário pode inserir uma senha incorreta antes de apagar o dispositivo.|
|**Expiração da senha (dias)**|Especifica o número de dias após os quais a senha do dispositivo deve ser alterada.
|**Lembrar de histórico de senha**|Especifica se deve ser permitido o uso de senhas usadas anteriormente.|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que não podem ser utilizadas novamente.|
|**Minutos de inatividade antes de a senha ser necessária**|Especifica a quantidade de tempo que um dispositivo deve permanecer ocioso antes que a tela seja bloqueada.

## Configurações de criptografia

|Nome da configuração|Detalhes|
|----------------|
|**Exigir criptografia no dispositivo móvel**<sup>1</sup>|Requer que os dados em um dispositivo sejam criptografados quando tiverem suporte.<br><br>Para dispositivos Windows Phone 8, defina como **Sim**.<br /><br />Para habilitar a criptografia em dispositivos iOS, habilite a configuração **Exigir uma senha para desbloquear dispositivos móveis**.|
|**Exigir criptografia em cartões de memória**|Exige que os dados armazenados externamente, como em um cartão SD, sejam criptografados (em dispositivos com suporte).
<sup>1</sup> Informações adicionais sobre dispositivos que executam o Windows 8.1

-   Se deseja impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](http://support.microsoft.com/kb/3013816) em cada dispositivo.

-   Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.

-   Se desejar que a criptografia funcione para Windows 8.1, o dispositivo deve atender aos requisitos de certificação de hardware [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) da Microsoft.

-   Se você impuser a criptografia em um dispositivo Windows 8.1, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive. Não é possível recuperar essa chave em nome de um usuário.

## Configurações de email

|Nome da configuração|Detalhes
|----------------|
|**Permitir que usuários baixem anexos de email**|Especifica se anexos de email podem ser baixados no dispositivo móvel.|
|**Período de sincronização de email**|Especifica o número de dias de email recebido que serão sincronizados com o dispositivo.
|**Permitir que dispositivos móveis que não dão suporte total às configurações do Exchange Sync sincronizem com o Exchange**|Especifica se o acesso do Exchange deve ser permitido em dispositivos que não oferecem suporte a uma ou mais configurações do Exchange ActiveSync.

## Configurações do navegador

|Nome da configuração|Detalhes
|----------------|-
|**Permitir navegador da web**|Especifica se o navegador da Web no dispositivo pode ser usado.<br>(Não disponível para Windows RT ou Windows Phone).

## Configurações de hardware

|Nome da configuração|Detalhes
|----------------|
|**Permitir câmera**|Especifica se a câmera no dispositivo pode ser usada.<br>(Não disponível para Windows RT ou Windows Phone).



### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO5-->


