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
ms.openlocfilehash: f66c0695c7e3d1f4bb7a5ca3abceeb13f6af41f2
ms.sourcegitcommit: 3c4ea8d6809a63042705b5ed4f25ba80f522070e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="see-device-details-in-intune"></a>Consultar detalhes do dispositivo no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O recurso **Dispositivos** fornece detalhes adicionais sobre os dispositivos que você gerencia, incluindo o hardware e os aplicativos instalados.

Este artigo mostra como exibir todos os dispositivos e suas propriedades no portal do Azure.

## <a name="view-the-device-details"></a>Exibir os detalhes do dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** > **Todos os dispositivos** > selecione um de seus dispositivos listados para abrir os detalhes:

   - **Visão geral** mostra o nome do dispositivo e lista algumas das principais propriedades do dispositivo, incluindo se ele é um dispositivo BYOD (traga seu próprio dispositivo), quando foi feito seu check-in e muito mais. Selecione **Mais** para também:
     - Remover os dados da empresa
     - Excluir o dispositivo
     - Bloquear o dispositivo remotamente
     - Apagar
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

## <a name="next-steps"></a>Próximas etapas
Veja o que mais você pode fazer para [gerenciar seus dispositivos](device-management.md) com o Intune.