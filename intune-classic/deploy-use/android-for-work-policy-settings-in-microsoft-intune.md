---
title: "Configurações de política do Android for Work"
description: "Crie políticas que controlam as configurações e os recursos nos dispositivos Android for Work que você gerencia com o Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0938e4b788ef11a773854531f570e63809389fad
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Configurações de política do Android for Work no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune fornece uma variedade de configurações gerais internas que você pode definir em [dispositivos Android para Trabalho](android-for-work.md).

## <a name="general-configuration-policy"></a>Política de configuração geral

Use a **política de configuração geral do Android for Work** do Intune para definir a segurança e as configurações de perfil de trabalho para dispositivos Android for Work.

Se a configuração que está procurando não aparecer nesse tópico, você poderá criá-la usando uma política personalizada do Android que lhe permite usar configurações de OMA-URI para controlar o dispositivo. Para obter mais informações, vá até [Configurações de política personalizadas](#custom-policy-settings) mais adiante neste tópico.

> [!TIP]
> Os dispositivos são criptografados automaticamente quando você provisiona um perfil de trabalho. Não é possível alterar essa configuração.

### <a name="password-settings"></a>Configurações de senha

|Nome da configuração|Detalhes|
|----------------|-|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especifica se uma senha é necessária nos dispositivos gerenciados. Escolha:<br><br>- **Complexa** – requer pelo menos uma letra, um número e um símbolo<br>- **Alfanumérica** – requer pelo menos um número e um caractere alfabético<br>- **Alfabética** – requer pelo menos letras ou símbolos<br>- **Numérica complexa** – requer caracteres numéricos que não sejam repetidos ou consecutivos<br>- **Numérica**<br><br>Se essa configuração não estiver habilitada, não haverá nenhum requisito de complexidade.|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres ou números na senha.|
|**Minutos de inatividade antes que o dispositivo seja bloqueado**|Especifica o número de minutos sem atividade do usuário antes da tela do dispositivo ser bloqueada automaticamente.|
|**Permitir Smart Lock e outros agentes de confiança**<br>(Android 6 e versões posteriores)|Permite controlar o recurso Smart Lock em dispositivos Android compatíveis. Essa capacidade do telefone, às vezes conhecida como agente de confiança, permitirá desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo estiver em um local confiável (por exemplo, quando ele está conectado a um dispositivo Bluetooth específico ou quando está perto de uma marca NFC). Você pode usar essa configuração para impedir que os usuários configurem o Smart Lock.|
|**Número de falhas de conexão repetidas antes da remoção do perfil de trabalho**|Especifica o número de falhas de conexão repetidas permitido antes da remoção do perfil de trabalho do dispositivo. O apagamento de dispositivo completo não é executado nesse caso.|
|**Lembrar histórico de senha**|Impede a reutilização de senhas usadas anteriormente.|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que deverão ser lembradas.|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|
|**Permitir desbloqueio por impressão digital**<br>(Android 6 e versões posteriores)|Permite que você use uma impressão digital para desbloquear dispositivos com esse recurso.|


### <a name="work-profile-settings"></a>Configurações de perfil de trabalho

|Nome da configuração|Detalhes|
|----------------|-|
|**Permitir o compartilhamento de dados entre perfis pessoais e de trabalho**|Permite que os aplicativos do perfil de trabalho compartilhem dados com os aplicativos do perfil pessoal do usuário. Escolha:<br><br>- **Evitar qualquer compartilhamento em limites**<br>- **Os aplicativos no perfil de trabalho podem lidar com a solicitação de compartilhamento do perfil pessoal**<br>- **Nenhuma restrição sobre compartilhamento**|
|**Ocultar notificações de perfil de trabalho quanto o dispositivo estiver bloqueado**<br>(Android 6 e versões posteriores)|Decidir se deseja mostrar notificações do perfil de trabalho quando o dispositivo estiver bloqueado.|
|**Configurar política de permissão de aplicativo padrão**<br>(Android 6 e versões posteriores)|Define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, algumas permissões exigidas pelos aplicativos são solicitadas ao usuário final em tempo de execução.  Essa configuração de política permite que TI decida como e se os usuários serão solicitados a conceder permissões para aplicativos no perfil de trabalho. <br/><br/>Por exemplo, TI pode enviar um aplicativo para o perfil de trabalho que requer acesso local.  Normalmente esse aplicativo exibiria uma caixa de diálogo para o usuário perguntando se ele quer conceder acesso local ao aplicativo e o usuário pode aprová-la ou recusá-la.  Essa política permite que TI decida se todas as permissões devem ser concedidas automaticamente sem aviso, negadas automaticamente sem aviso ou permitir que o usuário final decida.|


## <a name="custom-policy-settings"></a>Configurações de política personalizada
Use a **Política de configuração personalizada do Android for Work** do Microsoft Intune para implantar configurações OMA-URI, que podem ser usadas para controlar funcionalidades em dispositivos Android for Work. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você implante configurações do Android que não são configuráveis com as políticas do Intune.
No momento, o Intune dá suporte a um número limitado de políticas personalizadas do Android. Consulte os exemplos neste tópico para descobrir quais políticas podem ser configuradas.

### <a name="general-settings"></a>Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política personalizada do Android para ajudar a identificá-la no console do Intune.|
    |**Descrição**|Forneça uma descrição que dê uma visão geral da política personalizada do Android e outras informações relevantes que o ajudarão a localizá-la.|

### <a name="oma-uri-settings"></a>Configurações de OMA-URI

   |Nome da configuração|Detalhes|
    |--------|--------------------|
    |**Nome da configuração**|Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.|
    |**Descrição da configuração**|Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que o ajudarão a localizá-la.|
    |**Tipo de dados**|Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha **Cadeia de Caracteres, Cadeia de Caracteres (XML), Data e Hora, Número Inteiro, Ponto Flutuante**, ou **Booliano**.|
    |**OMA-URI (diferencia maiúsculas de minúsculas)**|Especifique o OMA-URI para o qual você deseja fornecer uma configuração.|
    |**Valor**|Especifique o valor a ser associado ao OMA-URI especificado anteriormente.|

### <a name="examples"></a>Exemplos

- [Criar um perfil de Wi-Fi com uma chave pré-compartilhada](pre-shared-key-wi-fi-profile.md)
- [Usar uma política personalizada para criar um perfil de VPN por aplicativo para dispositivos Android](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
