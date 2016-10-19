---
title: "Solucionar problemas de implantação de aplicativo | Microsoft Intune"
description: "Este tópico ajuda você a solucionar problemas de implantação de aplicativo com o Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: efc280f0a1143cacc252ee9fc9344064aa211cb2


---

# Solucionar problemas de implantação de aplicativo no Microsoft Intune
Se você estiver tendo problemas ao implantar e gerenciar aplicativos com o Intune, comece aqui. Este tópico contém alguns problemas comuns que podem ocorrer, juntamente com as soluções.

## Códigos comuns de erro de implantação do aplicativo

|Código do erro|Possível problema|Resoluções sugeridas|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (erro de cliente)|Para instalar esse aplicativo, você deve ter um sistema habilitado para carregamento.|Verifique se o pacote do aplicativo foi assinado com uma assinatura confiável e instalado em um dispositivo com domínio associado que tenha a política AllowAllTrustedApps habilitada ou um dispositivo que tenha uma licença do Windows Sideloading com a política AllowAllTrustedApps habilitada.|
|0x80073CF0|Não foi possível abrir o pacote.|Possíveis causas:<br /><br />-   O pacote não está assinado.<br />-   O nome do editor não corresponde ao assunto do certificado de assinatura.<br /><br />Consulte o log de eventos de AppxPackagingOM para obter mais informações.|
|0x80073CF3|Falha na atualização do pacote, dependência ou validação de conflito|Possíveis causas:<br /><br />-   O pacote de entrada está em conflito com um pacote instalado.<br />-   Uma dependência de pacote especificada não foi encontrada.<br />-   O pacote não dá suporte à arquitetura de processador correta.<br /><br />Consulte o log de eventos de AppXDeployment-Server para obter mais informações.|
|0x80073CFB|O pacote fornecido já foi instalado e sua reinstalação está bloqueada|Talvez você receba esse erro se estiver instalando um pacote que não é idêntico ao pacote já instalado. Confirme se a assinatura digital também faz parte do pacote. Quando um pacote é recriado ou assinado novamente, ele não é mais idêntico bit a bit ao pacote instalado anteriormente. Duas opções possíveis para corrigir esse erro são as seguintes:<br /><br />-   Aumente o número de versão do aplicativo e recrie e assine novamente o pacote.<br />-   Remova o pacote antigo para cada usuário no sistema antes de instalar o novo pacote.|
|0x87D1041C|Êxito na instalação do aplicativo, mas o aplicativo não foi detectado.|-O aplicativo foi implantado com êxito pelo Intune e subsequentemente desinstalado (possivelmente pelo usuário final). Instrua o usuário a reinstalar o aplicativo do portal da empresa. Os aplicativos necessários serão reinstalados automaticamente na próxima vez em que o dispositivo fizer check-in.|

## Solucionando problemas de aplicativos da Windows Store

As informações no tópico [Solução de problemas de empacotamento, implantação e consulta de aplicativos da Windows Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) ajudam a solucionar problemas comuns que podem ocorrer ao instalar aplicativos da Windows Store, usando o Intune ou por outros meios.

## Solucionando problemas de implantação de aplicativo em PCs gerenciados pelo cliente de software do Intune
Para ajudá-lo a solucionar problemas de implantação de aplicativos em PCs gerenciados pelo cliente de software do Intune, você pode analisar os dois seguintes arquivos de log:
- Pasta %ProgramFiles%\Microsoft\OnlineManagement\Logs
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Além disso, se precisar abrir um caso de suporte para o Intune, ele também será útil para enviar esses logs para a Microsoft.


### Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).



<!--HONumber=Oct16_HO2-->


