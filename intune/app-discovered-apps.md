---
title: Aplicativos Descobertos
titleSuffix: Microsoft Intune
description: Entenda os detalhes sobre os aplicativos detectados que o Intune encontrou em um dispositivo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07dd262f-13e7-4cb2-9cc2-b755d1c276cf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53555a01899cfec15c319e790620b2bfeaa302bc
ms.sourcegitcommit: 948ff8f56639e6dc7091134a0efd8d44efca63f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2019
ms.locfileid: "68590914"
---
# <a name="intune-discovered-apps"></a>Aplicativos descobertos pelo Intune

Os **aplicativos descobertos** pelo Intune são uma lista de aplicativos detectados nos dispositivos registrados no Intune em seu locatário. Eles funcionam como um inventário de software para seu locatário. Os **aplicativos descobertos** são um relatório separado dos relatórios de [instalação do aplicativo](apps-monitor.md). Para dispositivos pessoais, o Intune nunca coleta informações sobre aplicativos que não são gerenciados. Em dispositivos corporativos, qualquer aplicativo, seja um aplicativo gerenciado ou não, é coletado para esse relatório. Veja abaixo a tabela que mapeia o comportamento esperado. Em geral, o relatório é atualizado a cada 7 dias a partir do momento do registro (não uma atualização semanal do locatário inteiro). A única exceção a esse período de atualização são as informações do aplicativo coletadas por meio da Extensão de Gerenciamento do Intune para aplicativos Win32, que são coletadas a cada 24 horas.

## <a name="monitor-discovered-apps-with-intune"></a>Monitorar os aplicativos descobertos com o Intune

O Intune fornece uma lista agregada de aplicativos detectados nos dispositivos registrados no Intune em seu locatário.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No painel **Intune**, selecione **Aplicativos cliente** > **Aplicativos descobertos**.

>[!NOTE]
>Você pode exportar a lista de aplicativos descobertos para um arquivo .csv selecionando **Exportar** na folha **Aplicativos descobertos**.
>
>Atualmente, não há contagens de agregação para aplicativos Win32 descobertos. Esse tipo de dados só pode ser exibido por dispositivo.

O Intune também fornece a lista de aplicativos descobertos para o dispositivo individual em seu locatário. 

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No painel Intune, escolha **Dispositivos** > **Todos os Dispositivos**.
3. Selecione um dispositivo.
4. Para exibir os aplicativos detectados para este dispositivo, escolha **Aplicativos Descobertos** na seção **Monitorar**. 

## <a name="details-of-discovered-apps"></a>Detalhes de aplicativos descobertos

A lista a seguir fornece o tipo de plataforma do aplicativo, os aplicativos monitorados para dispositivos pessoais, os aplicativos monitorados para dispositivos de propriedade da empresa e o ciclo de atualização. Para obter mais informações sobre os tipos de aplicativos compatíveis com o Intune, confira [Tipos de aplicativos no Microsoft Intune](apps-add.md#app-types-in-microsoft-intune).

| Plataforma | Para dispositivos de propriedade pessoal | Para dispositivos de propriedade da empresa | Ciclo de atualização |
|------------------------------------------------------------------------|----------------------------------|--------------------------------------------------|---------------------------------------|
| Windows 10 (aplicativos Win32) OBSERVAÇÃO: [Exige a Extensão de Gerenciamento do Intune](intune-management-extension.md) no dispositivo | Não Aplicável | Todos os aplicativos Win32 encontrados na lista Adicionar/Remover Programas | A cada 24 horas após o registro do dispositivo |
| Windows 10 (aplicativos modernos) | Somente aplicativos modernos gerenciados | Todos os aplicativos modernos instalados no dispositivo | A cada 7 dias após o registro do dispositivo |
| Windows 8.1 | Somente aplicativos gerenciados | Somente aplicativos gerenciados | A cada 7 dias após o registro do dispositivo |
| Windows Phone 8 | Somente aplicativos gerenciados | Somente aplicativos gerenciados | A cada 7 dias após o registro do dispositivo |
| Windows RT | Somente aplicativos gerenciados | Somente aplicativos gerenciados | A cada 7 dias após o registro do dispositivo |
| iOS | Somente aplicativos gerenciados | Todos os aplicativos instalados no dispositivo | A cada 7 dias após o registro do dispositivo |
| macOS | Todos os aplicativos instalados no dispositivo | Todos os aplicativos instalados no dispositivo | A cada 7 dias após o registro do dispositivo |
| Android | Somente aplicativos gerenciados | Todos os aplicativos instalados no dispositivo | A cada 7 dias após o registro do dispositivo |
| Android Enterprise | Somente aplicativos gerenciados | Somente os aplicativos instalados no Perfil de Trabalho | A cada 7 dias após o registro do dispositivo |

O número de aplicativos descobertos pode não corresponder à contagem do status de instalação de aplicativos. Possibilidades de inconsistências incluem:
- Uma alteração de direcionamento de um aplicativo gerenciado instalado pode fazer com que a contagem de instalações na folha de status diminua, mas continue a ser informada nos aplicativos detectados.
- O direcionamento de várias instâncias do mesmo aplicativo em um locatário resultará em contagens diferentes devido à potencial sobreposição de usuários ou dispositivos. Cada instância do aplicativo contará usuários sobrepostos, mas os aplicativos detectados terão contagens duplicadas.
- Os aplicativos detectados e status de aplicativos são coletados em intervalos de tempo diferentes, o que pode causar uma discrepância na contagem de aplicativos.

## <a name="next-steps"></a>Próximas etapas

- [Tipos de aplicativos no Microsoft Intune](apps-add.md#app-types-in-microsoft-intune)
- [Monitorar atribuições e informações de aplicativo com o Microsoft Intune](apps-monitor.md)
