---
title: Usar os relatórios de Conformidade de Atualizações para Atualizações do Windows no Microsoft Intune
titleSuffix: Microsoft Intune
description: Use a Conformidade de Atualizações do OMS para exibir dados de relatório para Atualizações do Windows implantadas com o Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 09f3cafc16d8a08885731aa244a089367c6c0933
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728098"
---
# <a name="intune-compliance-reports-for-updates"></a>Relatórios de conformidade do Intune para atualizações
Ao usar o Intune para implantar uma atualização do Windows em dispositivos Windows 10, exiba os detalhes sobre a conformidade de atualizações usando o Intune ou uma solução gratuita chamada *Conformidade de Atualizações*, que faz parte do OMS (Microsoft Operations Management Suite).

## <a name="use-intune"></a>Usar o Intune
Para examinar um relatório de política no status de implantação para os anéis de atualização do Windows 10 que você configurou: 
1. Entre no [Portal do Azure](https://portal.azure.com/).
2. Escolha **Todos os serviços**, filtre pelo **Intune** e selecione **Microsoft Intune**.
3. Selecione **Atualizações de software** > **Visão geral**. É possível ver informações gerais sobre o status de todos os anéis de atualização que você atribuiu.
4. Abra um dos seguintes relatórios:  

   **Para todos os anéis de implantação**:
   1. Em **Atualizações de software** > **Anéis de Atualização do Windows 10**
   2. Na **seção Monitorar**, escolha **Por estado de implantação do grupo de atualização**.  

   **Para anéis de implantação específicos**:  

   1. Em **Atualizações de software** > **Anéis de atualização do Windows 10**, escolha o anel de implantação a ser examinado.  
   2. Na seção **Monitorar**, escolha entre os seguintes relatórios para exibir informações mais detalhadas sobre o grupo de atualização:  
      - **Status do dispositivo**  
      - **Status do usuário**  

## <a name="use-update-compliance"></a>Usar a Conformidade de Atualizações
É possível monitorar as distribuições de atualização do Windows 10 usando a [Conformidade de Atualizações](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor), uma solução do Windows Analytics. A Conformidade de Atualizações é oferecida por meio do portal do Azure e está disponível gratuitamente para dispositivos que atendam aos seus [pré-requisitos](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Quando você usar essa solução, implante uma ID comercial em quaisquer dispositivos Windows 10 gerenciados pelo Intune para os quais você deseja relatar a conformidade de atualizações.  

No console do Intune, use as configurações OMA-URI de uma política personalizada para configurar a ID comercial. Para obter detalhes, consulte [Configurações da política do Intune para os dispositivos do Windows 10 no Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

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

