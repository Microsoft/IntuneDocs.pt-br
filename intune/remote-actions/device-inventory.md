---
title: Exibir detalhes do dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Exiba os detalhes do dispositivo, incluindo sistemas operacionais, espaço de armazenamento, fabricante e modelo. Obtenha uma lista de aplicativos instalados, verifique as políticas de conformidade e configure o TeamViewer com o Microsoft Intune no Azure. Semelhante à exibição de inventário dos dispositivos que você gerencia.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e88371ac1ab51340f0f897d835f78562bed7d252
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727968"
---
# <a name="see-device-details-in-intune"></a>Consultar detalhes do dispositivo no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O recurso **Dispositivos** fornece detalhes adicionais sobre os dispositivos que você gerencia, incluindo o hardware e os aplicativos instalados.

Este artigo mostra como exibir todos os dispositivos e suas propriedades no portal do Azure.

## <a name="view-the-device-details"></a>Exibir os detalhes do dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecione **Dispositivos** > **Todos os dispositivos** > selecione um de seus dispositivos listados para abrir os detalhes:

   - **Visão geral** mostra o nome do dispositivo e descreve algumas das principais propriedades do dispositivo, por exemplo, se ele é do tipo BYOD (traga seu próprio dispositivo), o horário do check-in e muito mais. Você pode fazer o seguinte no dispositivo:
      - [Desativar](devices-wipe.md#retire)
      - [Apagamento](devices-wipe.md#wipe)
      - [Bloqueio remoto](device-remote-lock.md)
      - [Sincronizar dispositivo](device-sync.md)
      - [Redefinir senha](device-passcode-reset.md)
      - [Reiniciar](device-restart.md) (somente Windows)
      - [Novo Início](device-fresh-start.md) (somente Windows)
      - Iniciar uma sessão de assistência remota
   - Use **Propriedades** para atribuir uma [categoria de dispositivo que você criar](../enrollment/device-group-mapping.md) e altere a propriedade do dispositivo para um dispositivo pessoal ou um dispositivo corporativo.
   - **Hardware** inclui vários detalhes sobre o dispositivo, como a ID, o sistema operacional e a versão, o espaço de armazenamento e outros detalhes.
   - **Aplicativos descobertos** lista todos os aplicativos que Intune encontrou instalados no dispositivo e as respectivas versões. Para saber mais, confira [Aplicativos descobertos do Microsoft Intune](../apps/app-discovered-apps.md).
   - **Conformidade do dispositivo** lista todas as políticas de conformidade atribuídas e se o dispositivo está ou não em conformidade.
   - **Configuração do dispositivo** mostra todas as políticas de configuração de dispositivo atribuídas ao dispositivo e se a política foi bem-sucedida ou falhou.

## <a name="hardware-device-details"></a>Detalhes do dispositivo de hardware
Dependendo da operadora usada pelos dispositivos, nem todos os detalhes podem ser coletados

> [!Note]  
> O inventário de hardware e software é atualizado no serviço do Intune a cada sete dias.

|Detalhes|Descrição|Plataforma| 
|--------------|----------------------|----|  
|Nome|O nome do dispositivo.|Windows, iOS|
|Nome de gerenciamento|O nome do dispositivo usado somente no console. Alterar esse nome não mudará o nome do dispositivo.|Windows, iOS|
|UDID|A ID de Dispositivo Exclusiva do dispositivo.|Windows, iOS|
|ID de Dispositivo do Intune|Um GUID (Identificador global exclusivo) que identifica com exclusividade o dispositivo.|Windows, iOS|
|Número de série|O número de série do dispositivo atribuído pelo fabricante.|Windows, iOS|
|Dispositivo compartilhado|Se **Sim**, o dispositivo é compartilhado por mais de um usuário.|Windows, iOS|
|Registro aprovado pelo usuário|Se **Sim**, então o dispositivo tem um registro de usuário aprovado, que permite aos administradores gerenciar determinadas configurações de segurança no dispositivo.|Windows, iOS|
|Sistema operacional|O sistema operacional usado no dispositivo.|Windows, iOS|
|Versão do sistema operacional|Versão do sistema operacional do dispositivo.|Windows, iOS|
|Idioma do sistema operacional|O idioma definido para o sistema operacional no dispositivo.|Windows, iOS|
|Número da versão|O número de build do sistema operacional.|Android|
|Nível do patch de segurança|O nível do patch de segurança do dispositivo.|Android|
|Espaço de armazenamento total|O espaço de armazenamento total no dispositivo (em gigabytes).|Windows, iOS|
|Espaço de armazenamento gratuito|O espaço de armazenamento não usado no dispositivo (em gigabytes).|Windows, iOS|
|IMEI|Identificação Internacional de Equipamento Móvel do dispositivo.|Windows, iOS, Android|
|MEID|O identificador de equipamento móvel do dispositivo.|Windows, iOS, Android|
|Fabricante|O fabricante do dispositivo.|Windows, iOS, Android|
|Modelo|O modelo do dispositivo.|Windows, iOS, Android|
|Número do telefone|O número do telefone atribuído ao dispositivo.|Windows, iOS, Android|
|Operadora da assinatura|A operadora sem fio do dispositivo.|Windows, iOS, Android|
|Tecnologia celular|O sistema de rádio usado pelo dispositivo.|Windows, iOS, Android|
|MAC Wi-Fi|O endereço MAC (Controle de Acesso à Mídia) do dispositivo.|Windows, iOS, Android|
|ICCID|Identificador de Cartão de Circuito Integrado, o número de identificação exclusivo de um cartão SIM.|Windows, iOS, Android|
|Data registrada|A data e hora em que o dispositivo foi registrado no Intune.|Windows, iOS, Android|
|Último contato|A data e hora em que o dispositivo se conectou pela última vez no Intune.|Windows, iOS, Android|
|Código de bypass do bloqueio de ativação|O código que pode ser usado para ignorar o bloqueio de ativação.|Windows, iOS, Android|
|Azure AD registrado|Se **Sim**, o dispositivo está registrado no diretório do Azure.|Windows, iOS, Android|
|Registrado no Intune|Se **Sim**, o dispositivo está registrado no Microsoft Intune|Windows, iOS, Android|
|Conformidade|O estado de conformidade do dispositivo.|Windows, iOS, Android|
|EAS ativado|Se **Sim**, então o dispositivo está sincronizado com uma caixa de correio do Exchange.|Windows, iOS, Android|
|ID de ativação de EAS|O identificador Exchange ActiveSync do dispositivo.|Windows, iOS, Android|
|Supervisionado|Se **Sim**, os administradores têm controle aprimorado sobre o dispositivo.|Windows, iOS, Android|
|Criptografado|Se **Sim**, os dados armazenados no dispositivo estão criptografados.|Windows, iOS, Android|



## <a name="next-steps"></a>Próximas etapas
Veja o que mais você pode fazer para [gerenciar seus dispositivos](device-management.md) com o Intune.
