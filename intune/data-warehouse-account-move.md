---
title: Mover os dados da conta do Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Entenda como fazer backup dos dados de Data Warehouse do Intune ao mover a sua conta.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ee3ccbf9-82fc-4fbf-9d3d-8f05e431d090
ms.reviewer: aanavath
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: 7b13cfdcaa29edfc780126f3d1d76f5a9e46360f
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43330289"
---
# <a name="move-your-intune-data-warehouse-account-data"></a>Mover os dados da conta do Intune Data Warehouse 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ao solicitar uma mudança de conta, você estará solicitando que o seu data center seja alterado para outro local. Após a mudança, o Data Warehouse será redefinido e começará a gravar dados no novo local com base no dia especificado em que a mudança começar. Para fazer backup de seus dados de Data Warehouse anteriores, conclua as etapas a seguir **antes** da mudança da sua conta. A maioria das tabelas de Data Warehouse retém dados por 30 dias, de modo que qualquer intervalo nessas tabelas não estará disponível 30 dias após a mudança da sua conta. Para saber mais sobre os períodos de retenção de tabelas específicas, veja [Modelo de dados do Data Warehouse](reports-ref-data-model.md). 

## <a name="back-up-your-data-warehouse-data"></a>Fazer backup dos dados do Data Warehouse 

Para fazer backup dos dados do Data Warehouse, você deverá salvar seus dados do Data Warehouse em um arquivo *.csv* usando a API do Data Warehouse:  

1. Se você for um usuário pela primeira vez da API do Data Warehouse, siga o processo de uso único fornecido no artigo a seguir, [Obter dados da API do Data Warehouse do Intune com um cliente REST](reports-proc-data-rest.md).
2. Use o exemplo do PowerShell intitulado [Acessar o Data Warehouse do Intune com o PowerShell](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/PowerShell) para baixar todos os seus dados em arquivos CSV. 

## <a name="back-up-your-trend-charts-from-the-azure-portal"></a>Fazer backup dos gráficos de tendências do Portal do Azure

Alguns gráficos de tendências no modo de exibição no Portal do Azure serão redefinidos. Você pode fazer backup desses gráficos executando o seguinte script em **Gráfico**:   

### <a name="terms--conditions-acceptance-reports"></a>Relatórios de aceitação dos termos e condições
1. No Portal do Azure, navegue até **Microsoft Intune** -> **Registro de Dispositivo** -> **Termos e Condições**.
2. Para cada item dos **Termos e Condições**, selecione **Relatório de Aceitação** seguido por **Exportar**.
3. Salve o relatório localmente.
 
### <a name="app-protection-reports"></a>Relatórios de proteção do aplicativo  
1. No Portal do Azure, navegue até **Microsoft Intune** -> **Aplicativos Clientes** -> **Status de proteção do aplicativo**.
2. Clique no ícone de download (⤓) para salvar cada relatório.

### <a name="device-configuration-charts"></a>Gráficos de configuração do dispositivo 
1. No Portal do Azure, navegue até **Microsoft Intune** -> **DeviceConfiguration**.
2. Usando o [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer) da Microsoft, baixe os dados por trás dos gráficos. 
    - Para obter o status de implantação de todos os perfis de configuração de dispositivo para todos os dispositivos, veja [Status de implantação de dispositivo](https://graph.microsoft.com/beta/reports/deviceConfigurationDeviceActivity/content).

    - Para obter o status de implantação de todos os perfis de configuração de dispositivo para todos os usuários, veja [Status de implantação de usuário](https://graph.microsoft.com/beta/reports/deviceConfigurationUserActivity/content).

    - Para obter o status de implantação de perfil, veja [Fornecer o status de implantação](https://graph.microsoft.com/beta/deviceManagement/deviceConfigurations?$select=id,displayName,lastModifiedDateTime,deviceStatusOverview&$expand=deviceStatusOverview).
  
    > [!NOTE]
    > Você deve ter um token válido de autenticação para acessar a configuração do dispositivo e as informações de status de implantação.

## <a name="device-enrollment-charts"></a>Gráficos de registro de dispositivo
1. No Portal do Azure, navegue até **Microsoft Intune** -> **DeviceEnrollment**.
2. Usando o [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer) da Microsoft, baixe os dados por trás dos gráficos.
    - Para obter o status do registro, veja 
    - Para obter as principais falhas de registro desta semana, 
    - Para obter o status do registro, copie essa [consulta de status de registro](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentFailureTrends()/content) e cole-a no [Gerenciador de gráficos](https://developer.microsoft.com/graph/graph-explorer).
    - Para obter as principais falhas do registro, copie essa [consulta de falhas de registro](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentTopFailures(period=null)/content) e cole-a no [Gerenciador de gráficos](https://developer.microsoft.com/graph/graph-explorer).

    > [!NOTE]
    > Você deve ter um token válido de autenticação para acessar os dados de registro do dispositivo. 

## <a name="after-a-data-warehouse-account-move"></a>Depois de uma mudança de conta do Data Warehouse

Depois da mudança de conta do Data Warehouse, você verá no Intune que o Data Warehouse foi redefinido e seus dados agora estão armazenados no novo local. As opções de gráficos e exportação serão redefinidas e você verá uma notificação, que o direcionará para um artigo explicando por que os gráficos foram redefinidos.  

## <a name="data-warehouse-move-example"></a>Exemplo de mudança do Data Warehouse 

O cliente X solicita uma mudança de conta para começar em 06/01/2018. Em resposta à solicitação, o cliente receberá um link para ver a documentação que detalha as etapas a serem executadas se desejar fazer backup de seu Data Warehouse anterior. Em 06/01/2018, o Data Warehouse e os gráficos que ele suporta serão redefinidos e começarão a armazenar dados no novo data center. 

## <a name="next-steps"></a>Próximas etapas

 - Conheça as [novidades de cada semana no Intune](whats-new.md). Saiba mais também sobre as próximas alterações, avisos importantes sobre o serviço e informações sobre versões anteriores.
 - Leia o [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
