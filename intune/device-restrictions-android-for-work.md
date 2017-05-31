---
title: "Configurações de restrição de dispositivo do Intune para Android for Work | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as configurações do Intune que você pode usar para controlar as configurações do dispositivo e as funcionalidades dos dispositivos Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 857522ef4931407accf98b2a2ad97334278c138f
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo Android for Work no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Configurações de perfil de trabalho
-     **Dados compartilhados entre perfis de trabalho e pessoais** - use esta configuração para controlar se os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos no perfil pessoal. Escolha:
    - **Restrições de compartilhamento padrão** - esse é o comportamento de compartilhamento padrão do dispositivo que varia dependendo da versão do Android em execução. Por padrão, há permissão para o compartilhamento do perfil pessoal para o perfil de trabalho. Também por padrão, o compartilhamento entre o perfil de trabalho e o perfil pessoal é bloqueado. Isso evita o vazamento de dados do perfil de trabalho para o pessoal. O Google não oferece uma forma de bloquear dados do perfil pessoal para o perfil de trabalho em dispositivos com versões anteriores à 6.0.  
    - **Os aplicativos no perfil de trabalho podem lidar com solicitações de compartilhamento do perfil pessoal** - use esta opção para habilitar o recurso interno do Android que permite o compartilhamento do perfil pessoal para o perfil de trabalho. Quando estiver habilitada, uma solicitação de compartilhamento iniciada a partir de um aplicativo no perfil pessoal será capaz de compartilhar com aplicativos no perfil de trabalho. Esse é o comportamento padrão para dispositivos Android executando versões anteriores à 6.0.
    - **Aplicativos no perfil pessoal podem lidar com solicitações de compartilhamento do perfil de trabalho** - permite o compartilhamento além do limite do perfil de trabalho em ambas as direções. Quando você seleciona essa configuração, os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos não gerenciados no perfil pessoal.  Use essa configuração com cuidado, pois isso permite que os dados gerenciados no perfil de trabalho sejam transferidos para o lado não gerenciado do dispositivo.


-     **Notificações de perfil de trabalho enquanto o dispositivo estiver bloqueado** - controla se os aplicativos no perfil de trabalho podem exibir notificações na tela quando o dispositivo estiver bloqueado.
-     **Permissões de aplicativo padrão** - Define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, algumas permissões exigidas pelos aplicativos são solicitadas ao usuário final em tempo de execução. Essa configuração de política permite que você decida como e se os usuários serão solicitados a conceder permissões para aplicativos no perfil de trabalho.
Por exemplo, você envia um aplicativo para o perfil de trabalho que requer acesso local. Normalmente esse aplicativo exibiria uma caixa de diálogo para o usuário perguntando se ele quer conceder acesso local ao aplicativo e o usuário pode aprová-la ou recusá-la. Essa política permite que você decida se todas as permissões devem ser concedidas automaticamente sem aviso, negadas automaticamente sem aviso ou permitir que o usuário final decida. Escolha:
    -     **Padrão do dispositivo**
    -     **Prompt**
    -     **Concessão automática**
    -     **Negação automática**

## <a name="password"></a>Senha

- **Tamanho mínimo da senha** - insira o número mínimo de caracteres que a senha do usuário deve conter (de **4**-**14**)
- **Máximo de minutos de inatividade até a tela ser bloqueada** - selecione o tempo decorrido até um dispositivo inativo ser bloqueado automaticamente.
- **Número de falhas de entrada antes de apagar o dispositivo** – Insira o número de vezes que uma senha incorreta pode ser inserida antes que todos os dados do dispositivo sejam apagados.
- **Expiração da senha (dias)** – insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**).
- **Tipo de senha necessária** - selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
    - **Padrão do dispositivo**
    - **Biométrico de segurança baixa**
    - **Necessária**
    - **Pelo menos, numérico**
    - **Numérico complexo** - (números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos)
    - **Pelo menos, alfabético**
    - **Pelo menos, alfanumérico**
    - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores** - insira o número de novas senhas que devem ter sido usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio por impressão digital** - impede que um usuário final use o scanner de impressão digital do dispositivo para desbloqueá-lo.
- **Smart Lock e outros agentes de confiança** – permite que você controle o recurso Smart Lock em dispositivos compatíveis. Essa capacidade do telefone, às vezes conhecida como agente de confiança, permitirá desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo estiver em um local confiável (por exemplo, quando ele está conectado a um dispositivo Bluetooth específico ou quando está perto de uma marca NFC). Use essa configuração para impedir que os usuários configurem o Smart Lock.

## <a name="custom-policy-settings"></a>Configurações de política personalizada
Use a **Política de configuração personalizada do Android for Work** do Microsoft Intune para atribuir configurações OMA-URI, que podem ser usadas para controlar funcionalidades em dispositivos Android for Work. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você atribua configurações do Android que não são configuráveis com as políticas do Intune.
No momento, o Intune dá suporte a um número limitado de políticas personalizadas do Android. Consulte os exemplos neste tópico para descobrir quais políticas podem ser configuradas.

### <a name="general-settings"></a>Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome** |Insira um nome exclusivo para a política personalizada do Android para ajudar a identificá-la no console do Intune.|
    |**Descrição** |Forneça uma descrição que dê uma visão geral da política personalizada do Android e outras informações relevantes que o ajudarão a localizá-la.|

### <a name="oma-uri-settings"></a>Configurações de OMA-URI

  |Nome da configuração|Detalhes|
  |--------|--------------------|
  |**Nome** |Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.|
  |**Descrição** |Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que o ajudarão a localizá-la.|
    |**OMA-URI (diferencia maiúsculas de minúsculas)** |Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
  |**Tipo de dados** |Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha **Cadeia de Caracteres, Cadeia de Caracteres (XML), Data e Hora, Número Inteiro, Ponto Flutuante**, ou **Booliano**.|
  |**Valor** |Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|

