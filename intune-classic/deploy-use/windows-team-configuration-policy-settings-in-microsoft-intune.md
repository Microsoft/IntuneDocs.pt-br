---
title: "Definições da política de configuração do Windows Team"
description: "Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 6e0f0ea969ed78f2daf482438b056c8b4eb1a316
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Definições de política de configuração do Windows Team no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub.

|Nome da configuração|Detalhes|
|----------------|-----------|
|**Permitir que a tela seja ativada automaticamente quando alguém estiver na sala**|Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.|
|**Exigir PIN para projeção sem fio**|Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.|
|**Configurar uma janela de manutenção para atualizações do dispositivo**|Configura a o intervalo em que atualizações podem ocorrer no dispositivo. Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).|
|**Habilitar Azure Operational Insights**|Os Insights Operacionais do Azure, parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.<br /><br />Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.|
|**Habilitar projeção sem fio Miracast**|Habilite esta opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.<br /><br />Se você habilitar essa opção, em **Escolher Canal do Miracast**, selecione o canal do Miracast usado para o conteúdo do projeto.|
|**Escolher as informações da reunião exibidas na tela de boas-vindas**|Se você habilitar essa opção, você poderá escolher as informações que serão exibidas no bloco **Reuniões** da tela **Bem-vindo**. Você pode:<br /><br />-   **Mostrar somente organizador e hora**<br />-   **Mostrar organizador, hora e entidade (a entidade é oculta para reuniões particulares)**|
|**URL da imagem de tela de fundo da tela de bloqueio**|Habilite essa configuração para exibir um plano de fundo personalizado na tela **Boas-Vindas** dos dispositivos com Windows 10 Team a partir da URL especificada.<br /><br />A imagem deve estar no formato PNG e a URL deve começar com **https://**.|


### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


