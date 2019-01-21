---
title: Criar um relatório do feed OData com o Power BI
titlesuffix: Microsoft Intune
description: Crie uma visualização de mapa de árvore usando o Power BI Desktop com um filtro interativo da API do Data Warehouse do Intune.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: cc7e61d7b5dd0d7ff16836602b8d959683a971e7
ms.sourcegitcommit: 513c59a23ca5dfa80a3ba6fc84068503a4158757
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54210713"
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>Criar um relatório do feed OData com o Power BI

Este artigo descreve como criar uma visualização de mapa de árvore usando o Power BI Desktop com um filtro interativo. Por exemplo, seu CFO pode querer saber como a distribuição geral dos dispositivos é comparada apenas com os dispositivos de propriedade da empresa ou de propriedade pessoal. O mapa de árvore fornece informações sobre o número total de tipos de dispositivo. Você pode examinar o número de dispositivos iOS, Android e Windows que são de propriedade da empresa ou de propriedade pessoal.

### <a name="overview-of-creating-the-chart"></a>Visão geral da criação do gráfico

Para criar este gráfico, é necessário:
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

Instale a última versão do Power BI Desktop. Você pode fazer o download do Power BI Desktop em: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Conecte-se ao feed OData do Data Warehouse do Intune do seu locatário

> [!Note]  
> Você precisa de permissão para **Relatórios** no Intune. Para obter mais informações, consulte [Autorização](reports-api-url.md).

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Abra o painel **Data Warehouse do Intune**.
4. Copie a URL personalizada do feed. Por exemplo: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Abra o Power BI Desktop.
6. Escolha **Obter dados** > **Feed Odata**.
7. Cole a URL personalizada do feed na caixa de URL na janela **Feed OData**.
8. Selecione **Básico**.

    ![Feed OData do Intune Data Warehouse de seu locatário](media/reports-create-01-odatafeed.png)

9. Selecione **OK**.
10. Selecione **Conta da organização** e entre com suas credenciais do Intune.

    ![Credenciais de conta organizacional](media/reports-create-02-org-account.png)

11. Selecione **Conectar**. O navegador será aberto e mostrará a lista de tabelas no Data Warehouse do Intune.

    ![Captura de tela do Navegador – a lista de tabelas do Data Warehouse](media/reports-create-02-loadentities.png)

12. Selecione as tabelas **Dispositivos** e **ownerTypes**.  Selecione **Carregar**. O Power BI carrega os dados no modelo.

## <a name="create-a-relationship"></a>Criar uma relação

Você pode importar várias tabelas para analisar não apenas os dados em uma única tabela, mas também os dados relacionados entre as tabelas.  O PowerBI tem um recurso chamado **detecção automática** que tenta localizar e criar relações para você. As tabelas no Data Warehouse foram criadas para funcionar com o recurso de detecção automática do PowerBI. No entanto, mesmo se o PowerBI não localizar as relações automaticamente, você ainda poderá gerenciá-las.

![Gerenciar relações de dados relacionados em tabelas](media/reports-create-03-managerelationships.png)

1. Selecione **Gerenciar Relações**.
2. Selecione **Detectar automaticamente...** se o Power BI ainda não tiver detectado as relações.

A relação é exibida em uma coluna De para uma coluna Para. Neste exemplo, o campo de dados **ownerTypeKey** na tabela **Dispositivos** é vinculado ao campo de dados **ownerTypeKey** na tabela **ownerTypes**. Use a relação para pesquisar um nome simples do código de tipo de dispositivo na tabela **Dispositivos**.

## <a name="create-a-treemap-visualization"></a>Criar uma visualização de mapa de árvore

Um gráfico de mapa de árvore mostra dados hierárquicos, como caixas dentro de caixas. Cada branch da hierarquia é uma caixa que contém caixas menores, mostrando sub-branches. Você pode usar o Power BI Desktop para criar um mapa de árvore dos dados do Intune.

![Visualizações de mapa de árvore do Power BI](media/reports-create-03-treemap.png)

1. Selecione um tipo de gráfico. Selecione **Mapa de árvore**.
2. No modelo de dados, encontre a tabela **Dispositivos**.
3. Expanda a **tabela Dispositivos** e selecione o campo de dados **Fabricante** no painel **Campos**.
4. Arraste o campo de dados **Fabricante** para o gráfico Mapa de árvore na tela do relatório.
5. Arraste o campo de dados **deviceKey** da tabela **Dispositivos** para a seção **Valores** no painel **Visualizações** e solte na caixa rotulada **Arraste o campo de dados aqui**.  

Agora você tem uma representação visual que mostra a distribuição dos fabricantes de dispositivos na sua organização.

![Mapa de árvore com os dados – a distribuição dos fabricantes de dispositivos](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Adicionar um filtro

Você pode adicionar um filtro no mapa de árvore para poder responder perguntas adicionais usando o aplicativo.


1. Para adicionar um filtro, selecione a tela de relatório e, em seguida, o **ícone Segmentação** (![Mapa de árvore com modelo de dados e relações suportadas](media/reports-create-slicer.png)) em **Visualizações**.
2. Localize a tabela **ownerTypes** e arraste o campo de dados **ownerTypeName** na seção **Filtros** no painel **visualizações**.  

   Na tabela Dispositivos, há um campo de dados chamado **OwnerTypeKey** que contém um código que indica se o dispositivo é de propriedade pessoal ou da empresa. Como você deseja mostrar nomes amigáveis nesse filtro, procure a tabela **ownerTypes** e arraste o **ownerTypeName**. Este exemplo mostra como o modelo de dados dá suporte a relações entre as tabelas.

![Mapa de árvore com o filtro – dá suporte a relações entre tabelas](media/reports-create-08_ownertype.png)

Agora você tem um filtro interativo que pode ser usado para alternar entre dispositivos de propriedade da empresa e de propriedade pessoal. Use esse filtro para ver como a distribuição é alterada.

1. Selecione **Empresa** para ver a distribuição de dispositivos de propriedade da empresa.
2. Selecione **Pessoal** para ver os dispositivos de propriedade pessoal.

## <a name="next-steps"></a>Próximas etapas

 - Saiba mais sobre [criar e gerenciar relações](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) no Power BI Desktop na documentação do Power BI.
 - Consulte o [Modelo de Data Warehouse do Intune](https://docs.microsoft.com/intune/reports-ref-data-model).
