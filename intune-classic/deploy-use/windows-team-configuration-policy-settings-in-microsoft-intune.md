---
title: Definições da política de configuração do Windows Team
description: Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Definições de política de configuração do Windows Team no Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub.


|                                  Nome da configuração                                   |                                                                                                                                                                Detalhes                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Permitir que a tela seja ativada automaticamente quando alguém estiver na sala</strong>   |                                                                                                                         Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.                                                                                                                          |
|              <strong>Exigir PIN para projeção sem fio</strong>               |                                                                                                             Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.                                                                                                             |
|          <strong>Configurar uma janela de manutenção para atualizações do dispositivo</strong>           |                                                                                          Configura a o intervalo em que atualizações podem ocorrer no dispositivo. Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).                                                                                           |
|               <strong>Habilitar Azure Operational Insights</strong>                |                  Os Insights Operacionais do Azure, parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.<br /><br />Para se conectar aos Insights Operacionais do Azure, você deve especificar uma <strong>ID do Espaço de Trabalho</strong> e uma <strong>Chave do Espaço de Trabalho</strong>.                   |
|              <strong>Habilitar projeção sem fio Miracast</strong>               |                                          Habilite esta opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.<br /><br />Se você habilitar essa opção, em <strong>Escolher Canal do Miracast</strong>, selecione o canal do Miracast usado para o conteúdo do projeto.                                           |
| <strong>Escolher as informações da reunião exibidas na tela de boas-vindas</strong> | Se você habilitar essa opção, você poderá escolher as informações que serão exibidas no bloco <strong>Reuniões</strong> da tela <strong>Bem-vindo</strong>. Você pode:<br /><br />-   <strong>Mostrar somente organizador e hora</strong><br />-   <strong>Mostrar organizador, hora e entidade (a entidade é oculta para reuniões particulares)</strong> |
|                <strong>URL da imagem de tela de fundo da tela de bloqueio</strong>                 |                                           Habilite essa configuração para exibir um plano de fundo personalizado na tela <strong>Boas-Vindas</strong> dos dispositivos com Windows 10 Team a partir da URL especificada.<br /><br />A imagem deve estar no formato PNG e a URL deve começar com <strong>https://</strong>.                                            |

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

