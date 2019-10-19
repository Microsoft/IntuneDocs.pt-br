---
title: Conectar-se ao Data Warehouse com o Power BI
titleSuffix: Microsoft Intune
description: Você pode baixar um arquivo para uso com o Microsoft Power BI que permite que você carregue relatórios interativos gerados dinamicamente no locatário do Microsoft Intune.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d7a5f67dfd8f7256559cb54d873ed48205ad751
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490418"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Conectar-se ao Data Warehouse com o Power BI

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Você pode usar o aplicativo de Conformidade do Power BI para carregar relatórios interativos gerados dinamicamente para seu locatário do Intune. Além disso, você pode carregar seus dados de locatário no Power BI usando o link OData. O Intune oferece configurações de conexão para seu locatário para que você possa exibir os seguintes exemplos de relatórios e gráficos relacionados a:  

- Dispositivos
- Registro
- Política de proteção de aplicativo
- Política de conformidade
- Perfis de configuração do dispositivo
- Atualizações de software
- Logs de inventário de dispositivo

Também há tendências realçadas para o registro, conformidade, perfil de configuração de dispositivo e atualizações de software. Relatórios e gráficos de exemplo aplicam filtros simples à tela. Para usar filtros avançados, confira o painel **Filtro** no Power BI Desktop.

As etapas a seguir mostram como baixar o arquivo do Power BI e como usar o link OData com o Power BI.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Instalar o Power BI

Instale a última versão do [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). Para obter mais informações, veja [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Carregue os dados e os relatórios usando o Aplicativo Intune Compliance Data Warehouse do Power BI

O aplicativo [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) do Power BI contém informações de conexão para seu locatário e um conjunto de relatórios predefinidos com base no modelo de dados do Data Warehouse.

1. Navegue até a página **AppSource** do aplicativo [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) para iniciar o processo de instalação.
2. Clique no botão **obter agora** e, em seguida, clique em **continuar**.
3. Quando for solicitado a instalar o aplicativo Power BI, clique em **instalar**.
4. Após a conclusão da instalação, clique no bloco aplicativo de **conformidade do Intune (data warehouse)** .
5. Clique no botão **Conectar**. O diálogo **Conectar-se ao Intune Compliance (Data Warehouse)** é exibido.
6. Clique no botão **Entrar**.
7. Entre com uma conta de usuário que tenha acesso ao Intune Data Warehouse para o locatário que tem relatórios que você deseja exibir.
8. Para exibir o painel incluído, clique na guia **painéis** e, em seguida, clique no painel **visão geral de conformidade** .
9. Para exibir todos os relatórios disponíveis, clique na guia **relatórios** e, em seguida, clique no relatório **conformidade v 1.0** . Navegue pelas páginas do relatório clicando nas guias na parte inferior.
10. Para que seja fácil navegar de volta para esses relatórios mais tarde, clique na estrela ao lado do relatório **Compliance V1.0**. Isso adicionará o relatório aos seus favoritos do Power BI.

Como alternativa, você pode instalar o aplicativo do portal do Intune:

1. Entre no portal do Azure e selecione **Monitoring + Management** > **Intune**. Você também pode pesquisar recursos para o Intune.
2. Abra a folha **Configurar o Data Warehouse do Intune**.
3. Selecione **Obter o Aplicativo do Power BI** para acessar e compartilhar relatórios pré-criados do Power BI para seu locatário no navegador.
4. Siga as etapas 2 a 10 acima.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Carregue os dados no Power BI usando o link OData

Com um cliente autenticado no Azure AD, o URL do OData se conecta ao ponto de extremidade RESTful na API do Data Warehouse que expõe o modelo de dados para o cliente de relatório. Siga estas instruções para usar o Power BI Desktop para se conectar e criar seus próprios relatórios. Você não está limitado ao Power BI Desktop, mas pode usar sua ferramenta favorita de análise com a URL do OData, desde que o cliente dê suporte à autenticação OAuth 2.0 e ao padrão de v 4.0 OData.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Clique em **Configurar o Intune data warehouse** na seção **outras tarefas** no lado direito da folha visão geral. A folha **data warehouse do Intune** será exibida.
3. Recupere a URL do feed personalizada da folha de relatório, por exemplo:<br>
    `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
4. Abra o **Power BI Desktop**.
5. Escolha **arquivo** > **obter dados**. Selecione **feed de OData**.
6. Escolha **básica**.
7. Digite ou cole a **URL do OData** na caixa de URL.
8. Selecione **OK**.
9. Se você não tiver se autenticado no Azure AD para seu locatário por meio do cliente do Power BI Desktop, digite suas credenciais. Para obter acesso aos seus dados, você deve ser autorizado no Azure AD (Azure Active Directory) usando OAuth 2.0.  
    1. Selecione **Conta organizacional**.  
    2. Digite seu nome de usuário e senha.  
    3. Selecione **Entrar.**  
    4. Selecione **Conectar**.  
10. Selecione **Carregar**.

## <a name="next-steps"></a>Próximas etapas

Você pode encontrar as respostas para perguntas sobre seu ambiente, como o número de dispositivos registrados por dia na última semana. Você pode obter informações sobre a população de locatário e o cliente Intune usando os relatórios do Intune Data Warehouse Power BI recuperados da folha no Azure. No entanto, o Intune fornece várias maneiras adicionais para estender ou reutilizar os dados. O Power BI e a API do Intune Data Warehouse fornecem uma funcionalidade adicional, por exemplo:

<!-- - You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
- Os dados de locatário são organizados para ajudar a extrair informações de seus dados. Para obter mais informações sobre como os dados são organizados, consulte [Modelo de dados do Data Warehouse](reports-ref-data-model.md).
- Você também pode acessar os dados de uma interface RESTful e incorporá-los no seu próprio aplicativo. Para obter mais informações, consulte [Get data from the Data Warehouse API with a REST client](../reports-proc-data-rest.md) (Obter dados de API do Data Warehouse com um cliente REST).
