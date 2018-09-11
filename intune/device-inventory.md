---
title: Exibir detalhes do dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Exiba os detalhes do dispositivo, incluindo sistemas operacionais, espaço de armazenamento, fabricante e modelo. Obtenha uma lista de aplicativos instalados, verifique as políticas de conformidade e configure o TeamViewer com o Microsoft Intune no Azure. Semelhante à exibição de inventário dos dispositivos que você gerencia.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a658182800f480f27097e078f28adc95c35aa3ea
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313171"
---
# <a name="see-device-details-in-intune"></a>Consultar detalhes do dispositivo no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O recurso **Dispositivos** fornece detalhes adicionais sobre os dispositivos que você gerencia, incluindo o hardware e os aplicativos instalados.

Este artigo mostra como exibir todos os dispositivos e suas propriedades no portal do Azure.

## <a name="view-the-device-details"></a>Exibir os detalhes do dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** > **Todos os dispositivos** > selecione um de seus dispositivos listados para abrir os detalhes:

   - **Visão geral** mostra o nome do dispositivo e lista algumas das principais propriedades do dispositivo, incluindo se ele é um dispositivo BYOD (traga seu próprio dispositivo), quando foi feito seu check-in e muito mais. Você pode executar as seguintes ações no dispositivo:
      - [Desativar](devices-wipe.md#retire)
        - [Apagamento](devices-wipe.md#wipe)
        - [Bloqueio remoto](device-remote-lock.md)
        - [Sincronizar dispositivo](device-sync.md)
        - [Redefinir senha](device-passcode-reset.md)
        - [Reiniciar](device-restart.md) (somente Windows)
        - [Novo Início](device-fresh-start.md) (somente Windows)
     - Iniciar uma sessão de assistência remota
   - Use **Propriedades** para atribuir uma [categoria de dispositivo que você criar](device-group-mapping.md) e altere a propriedade do dispositivo para um dispositivo pessoal ou um dispositivo corporativo.
   - **Hardware** inclui muitos detalhes sobre o dispositivo, incluindo a ID do dispositivo, o sistema operacional e a versão, o espaço de armazenamento, o modelo e o fabricante, as configurações de acesso condicional e mais detalhes.
   - **Aplicativos descobertos** lista todos os aplicativos que Intune encontrou instalados no dispositivo e as respectivas versões. Você também pode **Exportar** a lista de aplicativos para um arquivo .csv.
   - **Conformidade do dispositivo** lista todas as políticas de conformidade atribuídas e se o dispositivo está ou não em conformidade.
   - **Configuração do dispositivo** mostra todas as políticas de configuração de dispositivo atribuídas ao dispositivo e se a política foi bem-sucedida ou falhou.

O Intune coleta uma lista de aplicativos que estão somente em dispositivos corporativos. Os aplicativos não são verificados em dispositivos pessoais. Em computadores Windows 10, são listados apenas os aplicativos modernos para dispositivos corporativos. O Intune não coleta informações sobre aplicativos Win32 no dispositivo. Dependendo da operadora usada pelos dispositivos, nem todos os aplicativos podem ser coletados.

|Plataforma|Para dispositivos pessoais|Para dispositivos corporativos|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (sem o cliente do Configuration Manager)|Somente aplicativos gerenciados|Somente aplicativos gerenciados|
|Windows 8.1 (sem o cliente do Configuration Manager)|Somente aplicativos gerenciados|Somente aplicativos gerenciados|  
|Windows Phone 8|Somente aplicativos gerenciados|Somente aplicativos gerenciados|  
|Windows RT|Somente aplicativos gerenciados|Somente aplicativos gerenciados|  
|iOS|Somente aplicativos gerenciados|Todos os aplicativos instalados no dispositivo|
|macOS|Todos os aplicativos instalados no dispositivo|Todos os aplicativos instalados no dispositivo|  
|Android|Somente aplicativos gerenciados|Todos os aplicativos instalados no dispositivo|  

## <a name="hardware-device-details"></a>Detalhes do dispositivo de hardware

### <a name="windows-and-ios-device-details"></a>Detalhes do dispositivo Windows e iOS:
|Detalhes|Descrição|  
|--------------|----------------------|  
|Nome|O nome do dispositivo.|
|Nome de gerenciamento|O nome do dispositivo usado somente no console. Alterar esse nome não mudará o nome do dispositivo.|
|UDID|A ID de Dispositivo Exclusiva do dispositivo.|
|ID de Dispositivo do Intune|Um GUID (Identificador global exclusivo) que identifica com exclusividade o dispositivo.|
|Número de série|O número de série do dispositivo atribuído pelo fabricante.|
|Dispositivo compartilhado|Se **Sim**, o dispositivo é compartilhado por mais de um usuário.|
|Registro aprovado pelo usuário|Se **Sim**, então o dispositivo tem um registro de usuário aprovado, que permite aos administradores gerenciar determinadas configurações de segurança no dispositivo.|
|Sistema operacional|O sistema operacional usado no dispositivo.|
|Versão do sistema operacional|Versão do sistema operacional do dispositivo.|
|Idioma do sistema operacional|O idioma definido para o sistema operacional no dispositivo.|
|Espaço de armazenamento total|O espaço de armazenamento total no dispositivo (em gigabytes).|
|Espaço de armazenamento gratuito|O espaço de armazenamento não usado no dispositivo (em gigabytes).|


### <a name="windows-ios-and-macos-device-details"></a>Detalhes do dispositivo Windows, iOS e macOS
|Detalhes|Descrição|  
|--------------|----------------------|  
|IMEI|Identificação Internacional de Equipamento Móvel do dispositivo.|
|MEID|O identificador de equipamento móvel do dispositivo.|
|Fabricante|O fabricante do dispositivo.|
|Modelo|O modelo do dispositivo.|
|Número do telefone|O número do telefone atribuído ao dispositivo.|
|Operadora da assinatura|A operadora sem fio do dispositivo.|
|Tecnologia celular|O sistema de rádio usado pelo dispositivo.|
|MAC Wi-Fi|O endereço MAC (Controle de Acesso à Mídia) do dispositivo.|
|ICCID|Identificador de Cartão de Circuito Integrado, o número de identificação exclusivo de um cartão SIM.|
|Data registrada|A data e hora em que o dispositivo foi registrado no Intune.|
|Último contato|A data e hora em que o dispositivo se conectou pela última vez no Intune.|
|Código de bypass do bloqueio de ativação|O código que pode ser usado para ignorar o bloqueio de ativação.|
|Azure AD registrado|Se **Sim**, o dispositivo está registrado no diretório do Azure.|
|Conformidade|O estado de conformidade do dispositivo.|
|EAS ativado|Se **Sim**, então o dispositivo está sincronizado com uma caixa de correio do Exchange.|
|ID de ativação de EAS|O identificador Exchange ActiveSync do dispositivo.|
|Supervisionado|Se **Sim**, os administradores têm controle aprimorado sobre o dispositivo.|
|Criptografado|Se **Sim**, os dados armazenados no dispositivo estão criptografados.|



## <a name="next-steps"></a>Próximas etapas
Veja o que mais você pode fazer para [gerenciar seus dispositivos](device-management.md) com o Intune.