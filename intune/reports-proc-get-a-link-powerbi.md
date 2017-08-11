---
title: Conectar-se ao Data Warehouse com o Power BI | Microsoft Docs
description: "Você pode baixar um arquivo para uso com o Microsoft Power BI que permite que você carregue relatórios interativos, gerados dinamicamente para seu locatário do Intune."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a9d99b71b9f84eea45ae597ed0f69010f6e95805
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Conectar-se ao Data Warehouse com o Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você pode baixar um arquivo para uso com o Microsoft Power BI que permite que você carregue relatórios interativos, gerados dinamicamente para seu locatário do Intune. O arquivo do Data Warehouse Power BI (pbix) contém as configurações de conexão para seu locatário e os seguintes exemplos de relatórios e gráficos: 

  -  Dispositivos
  -  Registro
  -  Política de proteção de aplicativo
  -  Política de conformidade
  -  Perfis de configuração do dispositivo
  -  Atualizações de software
  -  Logs de inventário de dispositivo

Também há tendências realçadas para o registro, conformidade, perfil de configuração de dispositivo e atualizações de software. Relatórios e gráficos de exemplo aplicam filtros simples à tela. Para usar filtros avançados, confira o painel **Filtro** no Power BI Desktop. 

As etapas a seguir mostram como baixar o arquivo do Power BI e como usar o link OData com o Power BI.

## <a name="install-power-bi"></a>Instalar o Power BI

Instale a última versão do Power BI Desktop. Você pode baixar o Power BI Desktop em: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) 

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Carregue os dados e relatórios usando o arquivo do Power BI (pbix)

O arquivo do Power BI (pbix) contém informações de conexão para seu locatário e um conjunto de relatórios predefinidos com base no modelo de dados do Data Warehouse. Abra o arquivo no Power BI Desktop e entre no Azure AD. O relatório carrega os dados de seu locatário do Intune.

1.  Entre no portal do Azure e selecione **Monitoring + Management** > **Intune**. Também é possível pesquisar recursos para o **Intune**.  
2.  Abra a folha **API Microsoft Intune Data Aarehouse (Visualização)**.
3.  Clique em **Baixar arquivo do PowerBI**. O arquivo com uma extensão (pbix) é baixado no local especificado.
4.  Abra o arquivo com o Power BI. O *Intune Data Warehouse Reports* é carregado, mas pode levar alguns segundos para obter os dados de seu locatário.
5.  Clique em **Atualizar** para carregar os dados de locatário e examinar os relatórios.
6.  Se o Power BI não tiver autenticado com suas credenciais do Azure Active Directory, o Power BI solicitará que você forneça suas credenciais. Ao selecionar suas credenciais, escolha **Conta organizacional** como seu método de autenticação.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Carregue os dados no Power BI usando o link OData

Com um cliente autenticado no Azure AD, o URL do OData se conecta ao ponto de extremidade RESTful na API do Data Warehouse que expõe o modelo de dados para o cliente de relatório. Siga estas instruções para usar o Power BI Desktop para se conectar e criar seus próprios relatórios. Você não está limitado ao Power BI Desktop, mas pode usar sua ferramenta favorita de análise com a URL do OData, desde que o cliente dê suporte à autenticação OAuth 2.0 e ao padrão de v 4.0 OData.

1.  Recupere o **URL do OData** da folha de relatório, por exemplo, `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
2.  Abra o **Power BI Desktop**.
3.  Selecione **Início** > **Obter dados**. Selecione **feed de OData**.
4.  Escolha **básica**.
5.  Digite ou cole a **URL do OData** na caixa de URL.
6.  Clique em **OK**.
7.  Se você não tiver se autenticado no Azure AD para seu locatário por meio do cliente do Power BI Desktop, digite suas credenciais.  
    a.  Selecione **Conta organizacional**.  
    b.  Digite seu nome de usuário e senha.  
    c.  Clique em **Entrar.**  
    d.  Clique em **Conectar**.  
8.  Clique em **Carregar**.

## <a name="next-steps"></a>Próximas etapas

Você pode encontrar as respostas para perguntas sobre seu ambiente, como o número de dispositivos registrados por dia na última semana. Você pode obter informações sobre a população de locatário e o cliente Intune que usam os relatórios usando o arquivo Intune Data Warehouse Power BI (pbix) recuperado da folha no Azure. No entanto, o Intune fornece várias maneiras adicionais para estender ou reutilizar os dados. Há muito mais que você pode fazer com o Power BI e a API Intune Data Warehouse, por exemplo:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Os dados de locatário são organizados para ajudar a extrair informações de seus dados. Para obter mais informações sobre como os dados são organizados, consulte [Modelo de dados do Data Warehouse](reports-ref-data-model.md). 
<!-- -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md). -->