---
title: "Criar um relatório do feed OData com o Power BI | Microsoft Docs"
description: "Crie uma visualização de mapa de árvore usando o Power BI Desktop com um filtro interativo da API do Data Warehouse do Intune."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 37f36aca0d58f5d87b9d54a1a4bdf18eb011b40b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2017
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>Criar um relatório do feed OData com o Power BI

Neste tutorial, você vai criar uma visualização de mapa de árvore usando o Power BI Desktop com um filtro interativo. Por exemplo, seu CFO pode querer saber como a distribuição geral dos dispositivos é comparada apenas com os dispositivos de propriedade da empresa ou de propriedade pessoal. O mapa de árvore fornece informações sobre o número total de tipos de dispositivo. Você pode examinar o número de dispositivos iOS, Android e Windows que são de propriedade da empresa ou de propriedade pessoal.

### <a name="overview-of-creating-the-chart"></a>Visão geral da criação do gráfico

Para criar este gráfico, você vai:
1. Instalar o Power BI Desktop se ele ainda não estiver instalado.
2. Conectar-se ao modelo de dados do Data Warehouse do Intune e recuperar os dados atuais para o modelo.
3. Criar ou gerenciar as relações do modelo de dados.
4. Criar o gráfico com os dados da tabela **Dispositivos**.
5. Criar um filtro interativo.
6. Exibir o gráfico concluído.

### <a name="a-note-about-tables-and-entities"></a>Uma observação sobre tabelas e entidades

Trabalha-se com tabelas no Power BI. Uma tabela contém campos de dados. Cada campo de dados tem um tipo de dados. O campo pode conter apenas dados daquele tipo de dados. Os tipos de dados são números, texto, datas e assim por diante. As tabelas no Power BI são preenchidas com os dados históricos recentes do seu locatário quando você carrega o modelo. Embora os dados específicos sejam alterados com o tempo, a estrutura da tabela não será alterada, a menos que o modelo de dados subjacente seja atualizado.

É possível que você fique confuso com o uso do termo _entidade_ e _tabela_. O modelo de dados fica acessível por meio de um feed OData. No universo do OData, os contêineres que são chamados de tabelas no Power BI são chamados de entidades. Esses dois termos referem-se à mesma coisa que contém seus dados.

## <a name="install-power-bi-desktop"></a>Instalar o Power BI Desktop

Instale a última versão do Power BI Desktop. Você pode baixar o Power BI Desktop em: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Conecte-se ao feed OData do Data Warehouse do Intune do seu locatário

> [!Note]  
> Você precisa de permissão para **Relatórios** no Intune. Para obter mais informações, consulte [Autorização](reports-api-url.md).

1. Entre no Portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
3. Abra a folha **Data Warehouse do Intune**.
4. Copie a URL personalizada do feed. Por exemplo: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Abra o Power BI Desktop.
6. Escolha **Obter dados** > **Feed Odata**.
7. Cole a URL personalizada do feed na caixa de URL na janela **Feed OData**.
8. Selecione **Básico**.

    ![Feed OData](media/reports-create-01-odatafeed.png)

9. Clique em **OK**.
10. Selecione **Conta da organização** e entre com suas credenciais do Intune. 

    ![Credenciais de conta organizacional](media/reports-create-02-org-account.png)

11. Clique em **Conectar**. O navegador será aberto e mostrará a lista de tabelas no Data Warehouse do Intune. 

    ![O navegador](media/reports-create-02-loadentities.png)

12. Selecione as tabelas **Dispositivos** e **ownerTypes**.  Clique em **Carregar**. O Power BI carrega os dados no modelo.

## <a name="create-a-relationship"></a>Criar uma relação 

Você pode importar várias tabelas para analisar não apenas os dados em uma única tabela, mas também os dados relacionados entre as tabelas.  O PowerBI tem um recurso chamado **detecção automática** que tenta localizar e criar relações para você. As tabelas no Data Warehouse foram criadas para funcionar com o recurso de detecção automática do PowerBI. No entanto, mesmo se o PowerBI não localizar as relações automaticamente, você ainda poderá gerenciá-las.

![Gerenciar relações](media/reports-create-03-managerelationships.png)

1. Clique em **Gerenciar Relações**.
2. Clique em **Detecção automática...** se o PowerBI ainda não tiver detectado as relações.  
A relação é exibida em uma coluna De para uma coluna Para. Neste exemplo, o campo de dados **ownerTypeKey** na tabela **Dispositivos** é vinculado ao campo de dados **ownerTypeKey** na tabela **ownerTypes**. Use a relação para pesquisar um nome simples do código de tipo de dispositivo na tabela **Dispositivos**.

## <a name="create-a-treemap-visualization"></a>Criar uma visualização de mapa de árvore

Um gráfico de mapa de árvore mostra dados hierárquicos, como caixas dentro de caixas. Cada branch da hierarquia é uma caixa que contém caixas menores, mostrando sub-branches. Você pode usar o Power BI Desktop para criar um mapa de árvore dos dados do Intune.

![Visualizações > mapa de árvore](media/reports-create-03-treemap.png)

1. Selecione um tipo de gráfico. Selecione **Mapa de árvore**.
2. No modelo de dados, encontre a tabela **Dispositivos**.
3. Expanda a **tabela Dispositivos** e selecione o campo de dados **Fabricante** no painel **Campos**.
4. Arraste o campo de dados **Fabricante** para o gráfico Mapa de árvore na tela do relatório.
5. Arraste o campo de dados **deviceKey** da tabela **Dispositivos** para a seção **Valores** no painel **Visualizações** e solte na caixa rotulada **Arraste o campo de dados aqui**.  
Agora você tem um visual que mostra a distribuição dos fabricantes de dispositivos em sua organização.

![Mapa de árvore com os dados](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Adicionar um filtro

Você pode adicionar um filtro no mapa de árvore para poder responder perguntas adicionais usando o aplicativo. 

1. Clique na tela de relatório e, em seguida, clique no **ícone Segmentação** (![Mapa de árvore com os dados](media/reports-create-slicer.png)) em **Visualizações** para adicionar um filtro.
2. Localize a tabela **ownerTypes** e arraste o campo de dados **ownerTypeName** na seção **Filtros** no painel **visualizações**.  
   Na tabela Dispositivos, há um campo de dados chamado **OwnerTypeKey** que contém um código que indica se o dispositivo é de propriedade pessoal ou da empresa. Como você deseja mostrar nomes amigáveis nesse filtro, procure a tabela **ownerTypes** e arraste o **ownerTypeName**. Este é um exemplo de como o modelo de dados dá suporte para relações entre tabelas.

![Mapa de árvore com filtro](media/reports-create-08_ownertype.png)

Agora você tem um filtro interativo que pode ser usado para alternar entre dispositivos de propriedade da empresa e de propriedade pessoal para ver como a distribuição é alterada.

1. Clique em **Empresa** para ver a distribuição de dispositivos de propriedade da empresa.
2. Clique em **Pessoal** para ver os dispositivos de propriedade pessoal.

## <a name="next-steps"></a>Próximas etapas

 - Saiba mais sobre [criar e gerenciar relações](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) no Power BI Desktop na documentação do Power BI.
 - Consulte o [Modelo de Data Warehouse do Intune](https://docs.microsoft.com/intune/reports-ref-data-model).