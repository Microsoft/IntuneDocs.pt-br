---
title:
- TÍTULO DO ARTIGO | NOME DO SERVIÇO
description: ''
keywords: ''
author:
- GITHUB USERNAME
manager:
- ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: ''
ms.service: ''
ms.technology: ''
ms.assetid:
- GET ONE FROM guidgenerator.com
ms.openlocfilehash: ed2d00541c2d89efd0f8cd6aa60f29c527656fc0
ms.sourcegitcommit: 5178aec0244e023e73546f3d10f1a76eaf1f4a3e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76971816"
---
# <a name="metadata-and-markdown-template"></a>Modelo de markdown e de metadados

Esse modelo do docs.ms contém exemplos de sintaxe de markdown, bem como uma orientação sobre como configurar os metadados. Ele está disponível no diretório raiz de cada repositório EM piloto (por exemplo, ~/Azure-RMSDocs-pr /template.md) e deve ser lido como um arquivo de redução, embora você possa consultar [a versão publicada](https://stage.docs.microsoft.com/en-us/rights-management/template) para ver como os exemplos de redução foram processados.

Ao criar uma um arquivo de markdown, copie o modelo em um novo arquivo, preencha metadados conforme especificado abaixo, defina o cabeçalho H1 acima como o título do artigo e exclua o conteúdo. 


## <a name="metadata"></a>Metadados 

O bloco de metadados completo está acima, dividido nos campos necessários e opcionais. Consulte as [anotações de referência de metadados OPS](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) para obter mais detalhes. Algumas observações importantes:

- Você **precisa** ter um espaço entre os dois-pontos (:) e o valor de um elemento de metadados.
- Se um elemento de metadados opcional não tiver um valor, remova o comentário do elemento com um # (não deixe em branco ou use "na"). Se você estiver adicionando um valor a um elemento que teve o comentário removido, não deixe de remover o #.
- Dois pontos em um valor (por exemplo, um título) quebram o analisador de metadados. Em seu lugar, use a codificação HTML de &#58; (por exemplo, "title: Azure Rights Management&#58; as noções básicas | Azure RMS").
- **title**: esse título aparecerá nos resultados do mecanismo de pesquisa. O título deve terminar com uma barra vertical (|) seguida pelo nome do serviço (por exemplo, veja acima). O título não precisa (e provavelmente não deve) ser idêntico ao título em seu título H1. Ele deve ter aproximadamente 65 caracteres (incluindo | NOME DO SERVIÇO)
- **author**, **manager**, **reviewer**: o campo author deve conter o **Nome de usuário do GitHub** do autor, não seu alias.  Por outro lado, os campos "manager" e "reviewer", devem conter aliases. ms.reviewer especifica o nome do PM associado ao artigo ou serviço.
- **ms.assetid**: esse é o GUID do artigo de CAPS. Ao criar um novo arquivo markdown, obtenha um GUID em [https://www.guidgenerator.com](https://www.guidgenerator.com). 
- **ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: os valores possíveis para esses elementos podem ser encontrados [aqui](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).

## <a name="basic-markdown-and-gfm"></a>Markdown Básico e GFM

Todo markdown básico e do tipo Github têm suporte. Para saber mais sobre eles, confira:

- [Sintaxe de markdown de linha de base](https://daringfireball.net/projects/markdown/syntax)
- [Documentação de GFM (markdown do tipo Github)](https://guides.github.com/features/mastering-markdown)

## <a name="headings"></a>Títulos

Veja acima os exemplos de títulos de primeiro e segundo nível. 

**Deve** haver apenas um título de primeiro nível em seu tópico, que será exibido como o título da página.  

Títulos de segundo nível gerarão o Sumário na página que aparece na seção "Neste artigo" embaixo do título da página.

### <a name="third-level-heading"></a>Título de terceiro nível
#### <a name="fourth-level-heading"></a>Título de quarto nível
##### <a name="fifth-level-heading"></a>Título de quinto nível
###### <a name="sixth-level-heading"></a>Título de sexto nível

## <a name="text-styling"></a>Estilo do texto

*Itálico* 

**Negrito** 

~~Tachado~~



## <a name="links"></a>Links

Para vincular a um arquivo markdown no mesmo repositório, use [links relativos](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2). 

- Exemplo: [O que é o Azure Rights Management](./understand-explore/what-is-azure-rights-management.md)

Para vincular a um título no mesmo arquivo markdown, exiba a origem do artigo publicado, localize a id do cabeçalho (por exemplo, `id="blockquote"`, e vincule usando #+id (por exemplo, `#blockquote`).

- Exemplo: [Blockquotes](#blockquote)

Para vincular a um título em um arquivo markdown no mesmo repositório, use link relativo+vinculação por hashtag.

- Exemplo: [visão geral técnica do processo de inscrição](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)

Para vincular a um arquivo externo, use a URL completa como o link.

- Exemplo: [Github](http://www.github.com)

Se aparecer uma URL em um arquivo markdown, ela será transformada em um link clicável.

- Exemplo: http://www.github.com

## <a name="lists"></a>Listas

### <a name="ordered-lists"></a>Listas ordenadas

1. Esta 
1. é
1. uma
1. Ordenado
1. Lista  


#### <a name="ordered-list-with-an-embedded-list"></a>Lista ordenada com uma lista incorporada

1. Esta
1. é
1. uma
1. lista
    1. inserida
    1. Professor Black
1. ordenado
1. lista


### <a name="unordered-lists"></a>Listas não ordenadas

- Esta
- é
- a
- lista
- lista


#### <a name="unordered-list-with-an-embedded-lists"></a>Lista não ordenada com uma lista incorporada

- Esta 
- com marcadores 
- lista
  - Dona Violeta
  - Sr. Marinho
- contém  
- outro
    1. Coronel Mostarda
    1. Dona Branca
- listas


## <a name="horizontal-rule"></a>Régua horizontal

---

## <a name="tables"></a>Tabelas

| Tabelas        | São           | Legais  |
| ------------- |:-------------:| -----:|
| a col. 3 está      | alinhada à direita | $1600 |
| a col. 2 está      | centralizada      |   $12 |
| a coluna 1 assume o padrão de | alinhada à esquerda     |    R$ 1 |


## <a name="code"></a>Código

### <a name="codeblock"></a>Codeblock

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a>In-line code (código embutido)

Este é um exemplo de `in-line code`.

## <a name="blockquotes"></a>Blockquotes (citações em bloco)

> A seca já durava dez milhões de anos, e o reino dos terríveis lagartos havia terminado muito antes disso. Aqui no Equador, no continente que um dia seria conhecido como África, a batalha pela existência atingiu um novo clímax de ferocidade, e o vencedor ainda não era conhecido. Nesta terra estéril e desértica, apenas os pequenos, os velozes ou os selvagens poderiam prosperar, ou mesmo ter esperança de sobreviver.

## <a name="images"></a>Imagens

### <a name="static-image"></a>Imagem Estática

![este é o texto alt](./media/AzRMS_elements.png)

### <a name="linked-image"></a>Imagem vinculada

[![texto alt para imagem vinculada](./media/AzRMS_elements.png)](https://azure.microsoft.com) 

### <a name="animated-gif"></a>Gif animado

![gif animado](./media/hololens.gif)

## <a name="alerts"></a>Alertas

### <a name="note"></a>Observação

> [!NOTE]
> Isso é uma OBSERVAÇÃO

### <a name="warning"></a>Aviso

> [!WARNING]
> Isto é um AVISO

### <a name="tip"></a>Dica

> [!TIP]
> Isso é uma DICA

### <a name="important"></a>Importante

> [!IMPORTANT]
> Isso é IMPORTANTE

## <a name="videos"></a>Vídeos

### <a name="channel-9"></a>Channel 9

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <a name="youtube"></a>Youtube

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <a name="docsms-extensions"></a>Extensões docs.ms

### <a name="button"></a>Botão

> [!div class="button"]
[links de botão](/rights-management)

### <a name="selector"></a>Seletor

> [!div class="op_single_selector"]
- [foo](/rights-management/template.md)
- [bar](/rights-management/scratch.md)

### <a name="step-by-step"></a>Passo a passo

>[!div class="step-by-step"]
[Anterior](https://www.example.com)
[Próximo](https://www.example.com)
