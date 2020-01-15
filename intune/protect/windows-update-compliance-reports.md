---
title: Usar os relatórios de Conformidade de Atualizações para Atualizações do Windows no Microsoft Intune
titleSuffix: Microsoft Intune
description: Use a Conformidade de Atualizações do OMS para exibir dados de relatório para Atualizações do Windows implantadas com o Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f1e493e0d2d562c0f69454d1999e82b528c724a2
ms.sourcegitcommit: e4602481a25a5e12379f673dfe801c611f51c35b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75731272"
---
# <a name="intune-compliance-reports-for-updates"></a>Relatórios de conformidade do Intune para atualizações

Ao usar o Intune para implantar uma atualização do Windows em dispositivos Windows 10, exiba os detalhes sobre a conformidade de atualizações usando o Intune ou uma solução gratuita chamada *Conformidade de Atualizações*, que faz parte do OMS (Microsoft Operations Management Suite).

## <a name="use-intune"></a>Usar o Intune

Para examinar um relatório de política no status de implantação para os anéis de atualização do Windows 10 que você configurou:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Visão geral** > **Status de atualização de software**. É possível ver informações gerais sobre o status de todos os anéis de atualização que você atribuiu.

3. Para exibir detalhes adicionais, selecione **Monitorar**. Em seguida, abaixo de **Atualizações de software**, selecione **Por estado de implantação de anel de atualização** e escolha o anel de implantação a ser revisado.

   Na seção **Monitorar**, escolha entre os seguintes relatórios para exibir informações mais detalhadas sobre o grupo de atualização:

   - **Status do dispositivo**– Isso mostrará o status de configuração do dispositivo, para obter mais detalhes, confira [Update deviceConfigurationDeviceStatus]( https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationdevicestatus-update?view=graph-rest-1.0).

   - **Status do usuário**– Isso mostrará o nome de usuário, o status e a data do último relatório, para obter mais detalhes, confira [List deviceConfigurationUserStatuses](https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationuserstatus-list?view=graph-rest-1.0).

   - **Status de atualização do usuário final**– Isso mostrará o estado de atualização do dispositivo Windows, para obter mais detalhes, confira [windowsUpdateState](https://docs.microsoft.com/graph/api/resources/intune-shared-windowsupdatestate?view=graph-rest-beta).

## <a name="use-update-compliance"></a>Usar a Conformidade de Atualizações

É possível monitorar as distribuições de atualização do Windows 10 usando a [Conformidade de Atualizações](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor), uma solução do Windows Analytics. A Conformidade de Atualizações é oferecida por meio do portal do Azure e está disponível gratuitamente para dispositivos que atendam aos seus [pré-requisitos](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Quando você usar essa solução, implante uma ID comercial em quaisquer dispositivos Windows 10 gerenciados pelo Intune para os quais você deseja relatar a conformidade de atualizações.  

No Intune, você usa as configurações OMA-URI de uma política personalizada para configurar a ID comercial. Confira [Usar configurações personalizadas para dispositivos Windows 10 no Intune](../configuration/custom-settings-windows-10.md).

O caminho OMA-URI (diferencia maiúsculas de minúsculas) para configurar a ID comercial é: *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*  

Por exemplo, você pode usar os seguintes valores em **Adicionar ou editar a configuração OMA-URI**:

- **Nome da Configuração**: ID comercial do Windows Analytics
- **Descrição da Configuração**: configurando a ID comercial para soluções do Windows Analytics
- **OMA-URI** (diferencia maiúsculas de minúsculas): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Tipo de dados**: Cadeia de caracteres
- **Valor**: \<use o GUID mostrado na guia Telemetria do Windows em seu workspace OMS>

> [!NOTE]
> Para obter mais informações sobre o MS DM Server, consulte [CSP (provedor de serviços de configuração) do DMClient]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Próximas etapas

[Gerenciar atualizações de software no Intune](windows-update-for-business-configure.md)
