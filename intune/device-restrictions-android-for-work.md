---
title: "Configurações de restrição de dispositivo do Intune para Android for Work"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos Android for Work."
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
ms.openlocfilehash: ca51c413e3148039b05a9d05a9a511e7158c9a1c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo Android for Work no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Configurações de perfil de trabalho
- **Compartilhamento de dados entre perfis de trabalho e pessoais** – use essa configuração para controlar se os aplicativos no perfil de trabalho podem ser compartilhados com aplicativos no perfil pessoal. Essa configuração controla as ações de compartilhamento em aplicativos (por exemplo, a opção **Compartilhar...** no aplicativo de navegador Chrome) e não se aplica ao comportamento da área de transferência copiar/colar. Ao contrário das [configurações de política de proteção do aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), as configurações de restrição de dispositivo são gerenciadas no portal do Intune e usam a partição de perfil de trabalho do Android for Work para isolar os aplicativos gerenciados. Escolha:
    - **Restrições de compartilhamento padrão** - esse é o comportamento de compartilhamento padrão do dispositivo que varia dependendo da versão do Android em execução. Por padrão, há permissão para o compartilhamento do perfil pessoal com o perfil de trabalho. Também por padrão, o compartilhamento do perfil de trabalho com o perfil pessoal é bloqueado. Isso impede o compartilhamento de dados do perfil de trabalho com o perfil pessoal. O Google não oferece uma maneira de bloquear o compartilhamento do perfil pessoal com o perfil de trabalho em dispositivos que executam versões 6.0 e posterior.   
    - **Os aplicativos no perfil de trabalho podem lidar com solicitações de compartilhamento do perfil pessoal** - use esta opção para habilitar o recurso interno do Android que permite o compartilhamento do perfil pessoal para o perfil de trabalho. Quando habilitada, uma solicitação de compartilhamento de um aplicativo no perfil pessoal pode ser compartilhada com aplicativos no perfil de trabalho. Esse é o comportamento padrão para dispositivos Android executando versões anteriores à 6.0.
    - **Permitir compartilhamento entre limites** – o habilita compartilhamento no limite do perfil de trabalho em ambas as orientações. Quando você seleciona essa configuração, os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos sem selo no perfil pessoal. Use essa configuração com cuidado, pois isso permite que os aplicativos gerenciados no perfil de trabalho sejam compartilhados com aplicativos no lado não gerenciado do dispositivo.

-   **Notificações de perfil de trabalho enquanto o dispositivo estiver bloqueado** – controla se os aplicativos no perfil de trabalho podem exibir dados em notificações quando o dispositivo está bloqueado.
-   **Permissões de aplicativo padrão** - Define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, o usuário deve conceder determinadas permissões necessárias por aplicativos quando o aplicativo é iniciado. Essa configuração de política permite que você decida se os usuários deverão conceder permissões para todos os aplicativos no perfil de trabalho. Por exemplo, você atribui um aplicativo ao perfil de trabalho que exige o acesso à localização. Normalmente, esse aplicativo solicita que o usuário aprove ou negue o acesso à localização para o aplicativo. Essa política permite que você decida se todas as permissões devem ser concedidas automaticamente sem aviso, negadas automaticamente sem aviso ou permitir que o usuário final decida. Escolha:
    -   **Padrão do dispositivo**
    -   **Prompt**
    -   **Concessão automática**
    -   **Negação automática**

    O estado de concessão das permissões pode ser definido de forma mais detalhada para aplicativos específicos, com a definição de uma política de Configuração de Aplicativo para um aplicativo individual (em **Aplicativos Móveis** > **Políticas de configuração de aplicativo**).

### <a name="work-profile-password"></a>Senha do perfil de trabalho
- **Exigir Senha de Perfil de Trabalho** – (Android 7.0 e posterior com o perfil de trabalho habilitado) Defina uma política de senha que se aplica apenas aos aplicativos no perfil de trabalho. Por padrão, o usuário final tem a opção de usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.
- **Tamanho mínimo da senha** – insira o número mínimo de caracteres que a senha do usuário deve conter (de **4**-**16**)
- **Máximo de minutos de inatividade até a tela ser bloqueada** – selecione o tempo antes que um dispositivo inativo exija que um usuário insira novamente a senha do perfil de trabalho para executar um aplicativo no perfil de trabalho.
- **Número de falhas de entrada antes de apagar o dispositivo** – insira o número de vezes que uma senha incorreta pode ser inserida antes que o perfil de trabalho seja apagado do dispositivo.
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
- **Smart Lock e outros agentes de confiança** – permite que você controle o recurso Smart Lock em dispositivos compatíveis. Essa funcionalidade do telefone, às vezes conhecida como agente de confiança, permite desabilitar ou ignorar a senha do perfil de trabalho se o dispositivo está em uma localização confiável (por exemplo, quando ele está conectado a um dispositivo Bluetooth específico ou quando está próximo a uma marcação NFC). Use essa configuração para impedir que os usuários configurem o Smart Lock.

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
