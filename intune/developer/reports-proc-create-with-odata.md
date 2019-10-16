---
title: Criar um relatório do Intune do feed OData com o Power BI
titleSuffix: Microsoft Intune
description: Crie uma visualização de mapa de árvore usando o Power BI Desktop com um filtro interativo da API do Data Warehouse do Intune.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1a508a6c9bf834268a797f028a32c7651cf394c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733472"
---
# <a name="create-an-intune-report-from-the-odata-feed-with-power-bi"></a>Criar um relatório do Intune do feed OData com o Power BI

Este artigo explica como criar uma visualização de mapa de arquivo de seus dados do Intune usando Power BI Desktop que os usuários têm um filtro interativo. Por exemplo, seu CFO pode gostar de saber como a distribuição geral de dispositivos é comparada entre dispositivos de propriedade da empresa e dispositivos pessoais. O mapa de árvore fornece informações sobre o número total de tipos de dispositivo. Você pode examinar o número de dispositivos iOS, Android e Windows que são de propriedade da empresa ou de propriedade pessoal.

## <a name="overview-of-creating-the-chart"></a>Visão geral da criação do gráfico

Para criar este gráfico, você vai:
1. Instalar o Power BI Desktop se ele ainda não estiver instalado.
2. Conectar-se ao modelo de dados do Data Warehouse do Intune e recuperar os dados atuais para o modelo.
3. Criar ou gerenciar as relações do modelo de dados.
4. Criar o gráfico com os dados da tabela **Dispositivos**.
5. Criar um filtro interativo.
6. Exibir o gráfico concluído.

### <a name="a-note-about-tables-and-entities"></a>Uma observação sobre tabelas e entidades

Trabalha-se com tabelas no Power BI. Uma tabela contém campos de dados. Cada campo de dados tem um tipo de dados. O campo pode conter apenas dados daquele tipo de dados. Os tipos de dados são números, texto, datas e assim por diante. As tabelas no Power BI são preenchidas com os dados históricos recentes do seu locatário quando você carrega o modelo. Embora os dados específicos sejam alterados com o tempo, a estrutura da tabela não será alterada, a menos que o modelo de dados subjacente seja atualizado.

É possível que você fique confuso com o uso do termo *entidade* e *tabela*. O modelo de dados pode ser acessado por meio de um feed OData (Protocolo Open Data). No universo do OData, os contêineres que são chamados de tabelas no Power BI são chamados de entidades. Esses dois termos referem-se à mesma coisa que contém seus dados. Para obter mais informações sobre OData, consulte a [visão geral do OData](/odata/overview).

## <a name="install-power-bi-desktop"></a>Instalar o Power BI Desktop

Instale a última versão do Power BI Desktop. Você pode baixar o Power BI Desktop em: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Conecte-se ao feed OData do Data Warehouse do Intune do seu locatário

> [!Note]  
> Você precisa de permissão para **Relatórios** no Intune. Para obter mais informações, consulte [Autorização](../reports-api-url.md).

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Abra o painel do **Data Warehouse do Intune** selecionando o link do Data Warehouse em **Outras tarefas**, no lado direito da folha **Microsoft Intune – Visão geral**.
3. Copie a URL personalizada do feed. Por exemplo: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
4. Abra o Power BI Desktop.
5. Na BarraDeMenu, selecione **arquivo** > **obter dados** > **feed OData**.
6. Cole a URL de feed personalizada, que você copiou da etapa anterior, na caixa URL na janela **feed OData** .
7. Selecione **Básico**.

    ![Feed OData do Intune Data Warehouse de seu locatário](./media/reports-proc-create-with-odata/reports-create-01-odatafeed.png)

8. Selecione **OK**.
9. Selecione **Conta da organização** e entre com suas credenciais do Intune.

    ![Credenciais de conta organizacional](./media/reports-proc-create-with-odata/reports-create-02-org-account.png)

10. Selecione **Conectar**. O navegador será aberto e mostrará a lista de tabelas no Data Warehouse do Intune.

    ![Captura de tela do Navegador – a lista de tabelas do Data Warehouse](./media/reports-proc-create-with-odata/reports-create-02-loadentities.png)

11. Selecione as tabelas **Dispositivos** e **ownerTypes**.  Selecione **Carregar**. O Power BI carrega os dados no modelo.

## <a name="create-a-relationship"></a>Criar uma relação

Você pode importar várias tabelas para analisar não apenas os dados em uma única tabela, mas também os dados relacionados entre as tabelas. O Power BI tem um recurso chamado **detecção automática** que tenta localizar e criar relações para você. As tabelas no Data Warehouse foram criadas para funcionar com o recurso de detecção automática no Power BI. No entanto, mesmo se o Power BI não localizar as relações automaticamente, você ainda poderá gerenciá-las.

![Gerenciar relações de dados relacionados em tabelas](./media/reports-proc-create-with-odata/reports-create-03-managerelationships.png)

1. Selecione **Gerenciar Relações**.
2. Selecione **Detectar automaticamente...** se o Power BI ainda não tiver detectado as relações.

A relação é exibida em uma coluna De para uma coluna Para. Neste exemplo, o campo de dados **ownerTypeKey** na tabela **Dispositivos** é vinculado ao campo de dados **ownerTypeKey** na tabela **ownerTypes**. Use a relação para pesquisar o nome simples do código de tipo de dispositivo na tabela **Dispositivos**.

## <a name="create-a-treemap-visualization"></a>Criar uma visualização de mapa de árvore

Um gráfico de mapa de árvore mostra dados hierárquicos, como caixas dentro de caixas. Cada branch da hierarquia é uma caixa que contém caixas menores, mostrando sub-branches. Você pode usar Power BI área de trabalho para criar um mapa de estrutura de dados de locatário do Intune que mostra quantidades relativas de tipos de fabricante de dispositivo.

![Visualizações de mapa de árvore do Power BI](./media/reports-proc-create-with-odata/reports-create-03-treemap.png)

1. No painel **visualizações** , localize e selecione **mapa**de página. O gráfico de **mapa** de plano será adicionado à tela de relatório.
2. No painel **campos** , localize a tabela `devices`.
3. Expanda a tabela `devices` e selecione o campo de dados `manufacturer`.
4. Arraste o campo de dados `manufacturer` para a tela relatório e solte-o no gráfico **mapa** de plano.
5. Arraste o campo de dados `deviceKey` da tabela `devices` para o painel **visualizações** e solte-o na seção **valores** na caixa rotulada **adicionar campos de dados aqui**.  

Agora você tem uma representação visual que mostra a distribuição dos fabricantes de dispositivos na sua organização.

![Mapa de árvore com os dados – a distribuição dos fabricantes de dispositivos](./media/reports-proc-create-with-odata/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Adicionar um filtro

Você pode adicionar um filtro no mapa de árvore para poder responder perguntas adicionais usando o aplicativo.

1. Para adicionar um filtro, selecione a tela de relatório e, em seguida, o **ícone Segmentação** (![Mapa de árvore com modelo de dados e relações suportadas](./media/reports-proc-create-with-odata/reports-create-slicer.png)) em **Visualizações**. A visualização de **segmentação** vazia será exibida na tela.
2. No painel **campos** , localize a tabela `ownerTypes`.
3. Expanda a tabela `ownerTypes` e selecione o campo de dados `ownerTypeName`.
4. Arraste o campo de dados `onwerTypeName` da tabela `ownerTypes` para o painel **filtros** e solte-o na seção **filtros nesta página** na caixa denominada **adicionar campos de dados aqui**.  

   Na tabela `OwnerTypes`, há um campo de dados chamado @no__t-qual contém um dado sobre se um dispositivo é de propriedade da empresa ou pessoal. Como você deseja mostrar nomes amigáveis nesse filtro, procure a tabela `ownerTypes` e arraste o **ownerTypeName** para a segmentação de dados. Este exemplo mostra como o modelo de dados dá suporte a relações entre as tabelas.

![Mapa de árvore com o filtro – dá suporte a relações entre tabelas](./media/reports-proc-create-with-odata/reports-create-08_ownertype.png)

Agora você tem um filtro interativo que pode ser usado para alternar entre dispositivos de propriedade da empresa e de propriedade pessoal. Use esse filtro para ver como a distribuição é alterada.

1. Selecione **empresa** dentro da segmentação para ver a distribuição de dispositivos de propriedade da empresa.
2. Selecione **pessoal** na segmentação para ver os dispositivos de propriedade pessoal.

## <a name="next-steps"></a>Próximas etapas

- Saiba mais sobre [criar e gerenciar relações](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) no Power BI Desktop na documentação do Power BI.
- Consulte o [Modelo de Data Warehouse do Intune](reports-ref-data-model.md).
