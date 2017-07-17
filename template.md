---
title: "<span data-ttu-id=\"b8fb9-101\">TÍTULO DO ARTIGO | NOME DO SERVIÇO</span><span class=\"sxs-lookup\"><span data-stu-id=\"b8fb9-101\">ARTICLE TITLE | SERVICE NAME</span></span>"
description: 
keywords: 
author: GITHUB USERNAME
manager: ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: GET ONE FROM guidgenerator.com
ms.openlocfilehash: 68090a038cec49009b6bd0ce0515a075f62483b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b8fb9-102">Modelo de markdown e de metadados</span><span class="sxs-lookup"><span data-stu-id="b8fb9-102">Metadata and Markdown Template</span></span>
<a id="metadata-and-markdown-template" class="xliff"></a>

<span data-ttu-id="b8fb9-103">Esse modelo docs.ms contém exemplos de sintaxe de redução e orientações sobre como definir os metadados.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-103">This docs.ms template contains examples of markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="b8fb9-104">Ele está disponível no diretório raiz de cada repositório EM piloto (por exemplo, ~/Azure-RMSDocs-pr /template.md) e deve ser lido como um arquivo de redução, embora você possa consultar [a versão publicada](https://stage.docs.microsoft.com/en-us/rights-management/template) para ver como os exemplos de redução foram processados.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-104">It is available in the root directory of each EM Pilot repository (e.g. ~/Azure-RMSDocs-pr /template.md) and is meant to be read as a markdown file, although you can refer to [the published version](https://stage.docs.microsoft.com/en-us/rights-management/template) to see how the markdown examples rendeer.</span></span>

<span data-ttu-id="b8fb9-105">Ao criar uma um arquivo de markdown, copie o modelo em um novo arquivo, preencha metadados conforme especificado abaixo, defina o cabeçalho H1 acima como o título do artigo e exclua o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-105">When creating a markdown file you shluld copy the template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span> 


## <span data-ttu-id="b8fb9-106">Metadados</span><span class="sxs-lookup"><span data-stu-id="b8fb9-106">Metadata</span></span>
<a id="metadata" class="xliff"></a> 

<span data-ttu-id="b8fb9-107">O bloco de metadados completo está acima, dividido nos campos necessários e opcionais. Consulte as [anotações de referência de metadados OPS](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-107">The full metadata block is above, divided into required fields and optional fields; see the [OPS metadata cheatsheet](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) for more details.</span></span> <span data-ttu-id="b8fb9-108">Algumas observações importantes:</span><span class="sxs-lookup"><span data-stu-id="b8fb9-108">Some key notes:</span></span>

- <span data-ttu-id="b8fb9-109">Você **precisa** ter um espaço entre os dois-pontos (:) e o valor de um elemento de metadados.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="b8fb9-110">Se um elemento de metadados opcional não tiver um valor, remova o comentário do elemento com um # (não deixe em branco ou use "na"). Se você estiver adicionando um valor a um elemento que teve o comentário removido, não deixe de remover o #.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-110">If an optional metadata element does not have a value, comment out the element with a # (do not leave it blank or use "na"); if you are adding a value to an element that was commnted out, be sure to remove the #.</span></span>
- <span data-ttu-id="b8fb9-111">Dois-pontos em um valor (por exemplo, um título) interrompem o analisador de metadados.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-111">Colons in a value (e.g., a title) break the metadata parser.</span></span> <span data-ttu-id="b8fb9-112">Em seu lugar, use a codificação HTML &#58; (por exemplo, "title: Azure Rights Management&#58; noções básicas | Azure RMS").</span><span class="sxs-lookup"><span data-stu-id="b8fb9-112">In their place, use the HTML encoding of &#58; (e.g., "title: Azure Rights Management&#58; the basics | Azure RMS").</span></span>
- <span data-ttu-id="b8fb9-113">**title**: esse título aparecerá nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-113">**title**: This title will appear in search engine results.</span></span> <span data-ttu-id="b8fb9-114">O título deve terminar com uma barra vertical (|) seguida do nome do serviço (por exemplo, veja acima).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-114">The title should end with a pipe (|) followed by the name of the service (e.g. see above).</span></span> <span data-ttu-id="b8fb9-115">O título não precisa (e provavelmente não deve) ser idêntico ao título do seu cabeçalho H1.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-115">The title need not (and probably should not) be identical to the title in your H1 heading.</span></span> <span data-ttu-id="b8fb9-116">Ele deve ter aproximadamente 65 caracteres (incluindo | NOME DO SERVIÇO)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-116">It should be roughly 65 characters (including | SERVICE NAME)</span></span>
- <span data-ttu-id="b8fb9-117">**author**, **manager**, **reviewer**: o campo author deve conter o **nome de usuário Github** do autor, não seu alias.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-117">**author**, **manager**, **reviewer**: The author field should contain the **Github username** of the author, not their alias.</span></span>  <span data-ttu-id="b8fb9-118">Por outro lado, os campos "manager" e "reviewer" devem conter aliases.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-118">The "manager" and "reviewer" fields, on the other hand, should contain aliases.</span></span> <span data-ttu-id="b8fb9-119">ms.reviewer especifica o nome do PM associado ao artigo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-119">ms.reviewer specifies the name of the PM associated with the article or service.</span></span>
- <span data-ttu-id="b8fb9-120">**ms.assetid**: esse é o GUID do artigo do CAPS.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-120">**ms.assetid**: This is the GUID of the article from CAPS.</span></span> <span data-ttu-id="b8fb9-121">Ao criar um novo arquivo de markdown, obtenha um GUID em [https://www.guidgenerator.com](https://www.guidgenerator.com).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-121">When creating a new markdown file, get a GUID from [https://www.guidgenerator.com](https://www.guidgenerator.com).</span></span> 
- <span data-ttu-id="b8fb9-122">**ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: os valores possíveis para esses elementos podem ser encontrados [aqui](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-122">**ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: Possible values for these elements can be found [here](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).</span></span>

## <span data-ttu-id="b8fb9-123">GFM e markdown básico</span><span class="sxs-lookup"><span data-stu-id="b8fb9-123">Basic Markdown and GFM</span></span>
<a id="basic-markdown-and-gfm" class="xliff"></a>

<span data-ttu-id="b8fb9-124">Todos os markdowns básicos e GFM têm suporte.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-124">All basic and Github-flavored markdown is supported.</span></span> <span data-ttu-id="b8fb9-125">Para saber mais sobre estas configurações, confira:</span><span class="sxs-lookup"><span data-stu-id="b8fb9-125">For more information on these, see:</span></span>

- [<span data-ttu-id="b8fb9-126">Sintaxe de markdown de linha de base</span><span class="sxs-lookup"><span data-stu-id="b8fb9-126">Baseline markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="b8fb9-127">Documentação GFM (Github-flavored markdown)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-127">Github-flavored markdown (GFM) documentation</span></span>](https://guides.github.com/features/mastering-markdown)

## <span data-ttu-id="b8fb9-128">Títulos</span><span class="sxs-lookup"><span data-stu-id="b8fb9-128">Headings</span></span>
<a id="headings" class="xliff"></a>

<span data-ttu-id="b8fb9-129">Acima, temos exemplos de cabeçalhos de primeiro e segundo nível.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-129">Examples of first- and second-level headings are above.</span></span> 

<span data-ttu-id="b8fb9-130">Somente um cabeçalho de primeiro nível **pode** existir no seu tópico, que será exibido como o título na página.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-130">There **must** be only one first-level heading in your topic, which will be displayed as the on-page title.</span></span>  

<span data-ttu-id="b8fb9-131">Títulos de segundo nível irão gerar o Sumário na página que aparece na seção "Neste artigo" embaixo do título da página.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-131">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <span data-ttu-id="b8fb9-132">Cabeçalho de terceiro nível</span><span class="sxs-lookup"><span data-stu-id="b8fb9-132">Third-level heading</span></span>
<a id="third-level-heading" class="xliff"></a>
#### <span data-ttu-id="b8fb9-133">Cabeçalho de quarto nível</span><span class="sxs-lookup"><span data-stu-id="b8fb9-133">Fourth-level heading</span></span>
<a id="fourth-level-heading" class="xliff"></a>
##### <span data-ttu-id="b8fb9-134">Cabeçalho de quinto nível</span><span class="sxs-lookup"><span data-stu-id="b8fb9-134">Fifth level heading</span></span>
<a id="fifth-level-heading" class="xliff"></a>
###### <span data-ttu-id="b8fb9-135">Cabeçalho de sexto nível</span><span class="sxs-lookup"><span data-stu-id="b8fb9-135">Sixth-level heading</span></span>
<a id="sixth-level-heading" class="xliff"></a>

## <span data-ttu-id="b8fb9-136">Estilo do texto</span><span class="sxs-lookup"><span data-stu-id="b8fb9-136">Text styling</span></span>
<a id="text-styling" class="xliff"></a>

<span data-ttu-id="b8fb9-137">*Itálico*</span><span class="sxs-lookup"><span data-stu-id="b8fb9-137">*Italics*</span></span> 

<span data-ttu-id="b8fb9-138">**Negrito**</span><span class="sxs-lookup"><span data-stu-id="b8fb9-138">**Bold**</span></span> 

<span data-ttu-id="b8fb9-139">~~Tachado~~</span><span class="sxs-lookup"><span data-stu-id="b8fb9-139">~~Strikethrough~~</span></span>



## <span data-ttu-id="b8fb9-140">Links</span><span class="sxs-lookup"><span data-stu-id="b8fb9-140">Links</span></span>
<a id="links" class="xliff"></a>

<span data-ttu-id="b8fb9-141">Para vincular a um arquivo de markdown no mesmo repositório, use [links relativos](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-141">To link to a markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2).</span></span> 

- <span data-ttu-id="b8fb9-142">Exemplo: [o que é o Azure Rights Management?](./understand-explore/what-is-azure-rights-management.md)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-142">Example: [What is Azure Rights Management](./understand-explore/what-is-azure-rights-management.md)</span></span>

<span data-ttu-id="b8fb9-143">Para vincular a um cabeçalho no mesmo arquivo de markdown, exiba o código-fonte do artigo publicado, localize a ID de cabeçalho (por exemplo, `id="blockquote"`) e vincule usando # + ID (por exemplo, `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-143">To link to a header in the same markdown file, view the source of the published article, find the id of the head (e.g. `id="blockquote"`, and link using # + id (e.g. `#blockquote`).</span></span>

- <span data-ttu-id="b8fb9-144">Exemplo: [Blockquotes](#blockquote)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-144">Example: [Blockquotes](#blockquote)</span></span>

<span data-ttu-id="b8fb9-145">Para vincular a um cabeçalho em um arquivo de markdown no mesmo repositório, use link relativo + link de hashtag.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-145">To link to a header in a markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="b8fb9-146">Exemplo: [visão técnica do processo de inscrição](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-146">Example: [technical overiew of the sign-up process](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)</span></span>

<span data-ttu-id="b8fb9-147">Para vincular a um arquivo externo, use a URL completa como o link.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-147">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="b8fb9-148">Exemplo: [Github](http://www.github.com)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-148">Example: [Github](http://www.github.com)</span></span>

<span data-ttu-id="b8fb9-149">Se aparecer uma URL em um arquivo de markdown, ela será transformada em um link clicável.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-149">If a URL appears in a markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="b8fb9-150">Exemplo: http://www.github.com</span><span class="sxs-lookup"><span data-stu-id="b8fb9-150">Example: http://www.github.com</span></span>

## <span data-ttu-id="b8fb9-151">Listas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-151">Lists</span></span>
<a id="lists" class="xliff"></a>

### <span data-ttu-id="b8fb9-152">Listas ordenadas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-152">Ordered lists</span></span>
<a id="ordered-lists" class="xliff"></a>

1. <span data-ttu-id="b8fb9-153">Isso</span><span class="sxs-lookup"><span data-stu-id="b8fb9-153">This</span></span> 
1. <span data-ttu-id="b8fb9-154">É</span><span class="sxs-lookup"><span data-stu-id="b8fb9-154">Is</span></span>
1. <span data-ttu-id="b8fb9-155">Um</span><span class="sxs-lookup"><span data-stu-id="b8fb9-155">An</span></span>
1. <span data-ttu-id="b8fb9-156">Ordenado</span><span class="sxs-lookup"><span data-stu-id="b8fb9-156">Ordered</span></span>
1. <span data-ttu-id="b8fb9-157">Lista</span><span class="sxs-lookup"><span data-stu-id="b8fb9-157">List</span></span>  


#### <span data-ttu-id="b8fb9-158">Lista ordenada com uma lista incorporada</span><span class="sxs-lookup"><span data-stu-id="b8fb9-158">Ordered list with an embedded list</span></span>
<a id="ordered-list-with-an-embedded-list" class="xliff"></a>

1. <span data-ttu-id="b8fb9-159">Aqui</span><span class="sxs-lookup"><span data-stu-id="b8fb9-159">Here</span></span>
1. <span data-ttu-id="b8fb9-160">vem</span><span class="sxs-lookup"><span data-stu-id="b8fb9-160">comes</span></span>
1. <span data-ttu-id="b8fb9-161">um</span><span class="sxs-lookup"><span data-stu-id="b8fb9-161">an</span></span>
1. <span data-ttu-id="b8fb9-162">inserido</span><span class="sxs-lookup"><span data-stu-id="b8fb9-162">embedded</span></span>
    1. <span data-ttu-id="b8fb9-163">Srta. Rosa</span><span class="sxs-lookup"><span data-stu-id="b8fb9-163">Miss Scarlett</span></span>
    1. <span data-ttu-id="b8fb9-164">Professor Black</span><span class="sxs-lookup"><span data-stu-id="b8fb9-164">Professor Plum</span></span>
1. <span data-ttu-id="b8fb9-165">ordenado</span><span class="sxs-lookup"><span data-stu-id="b8fb9-165">ordered</span></span>
1. <span data-ttu-id="b8fb9-166">lista</span><span class="sxs-lookup"><span data-stu-id="b8fb9-166">list</span></span>


### <span data-ttu-id="b8fb9-167">Listas não ordenadas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-167">Unordered Lists</span></span>
<a id="unordered-lists" class="xliff"></a>

- <span data-ttu-id="b8fb9-168">Isso</span><span class="sxs-lookup"><span data-stu-id="b8fb9-168">This</span></span>
- <span data-ttu-id="b8fb9-169">é</span><span class="sxs-lookup"><span data-stu-id="b8fb9-169">is</span></span>
- <span data-ttu-id="b8fb9-170">a</span><span class="sxs-lookup"><span data-stu-id="b8fb9-170">a</span></span>
- <span data-ttu-id="b8fb9-171">com marcadores</span><span class="sxs-lookup"><span data-stu-id="b8fb9-171">bulleted</span></span>
- <span data-ttu-id="b8fb9-172">lista</span><span class="sxs-lookup"><span data-stu-id="b8fb9-172">list</span></span>


##### <span data-ttu-id="b8fb9-173">Lista não ordenada com uma lista incorporada</span><span class="sxs-lookup"><span data-stu-id="b8fb9-173">Unordered list with an embedded lists</span></span>
<a id="unordered-list-with-an-embedded-lists" class="xliff"></a>

- <span data-ttu-id="b8fb9-174">Isso</span><span class="sxs-lookup"><span data-stu-id="b8fb9-174">This</span></span> 
- <span data-ttu-id="b8fb9-175">com marcadores</span><span class="sxs-lookup"><span data-stu-id="b8fb9-175">bulleted</span></span> 
- <span data-ttu-id="b8fb9-176">lista</span><span class="sxs-lookup"><span data-stu-id="b8fb9-176">list</span></span>
    - <span data-ttu-id="b8fb9-177">Dona Violeta</span><span class="sxs-lookup"><span data-stu-id="b8fb9-177">Mrs. Peacock</span></span>
    - <span data-ttu-id="b8fb9-178">Sr. Marinho</span><span class="sxs-lookup"><span data-stu-id="b8fb9-178">Mr. Green</span></span>
- <span data-ttu-id="b8fb9-179">contém</span><span class="sxs-lookup"><span data-stu-id="b8fb9-179">contains</span></span>  
- <span data-ttu-id="b8fb9-180">outro</span><span class="sxs-lookup"><span data-stu-id="b8fb9-180">other</span></span>
    1. <span data-ttu-id="b8fb9-181">Coronel Mostarda</span><span class="sxs-lookup"><span data-stu-id="b8fb9-181">Colonel Mustard</span></span>
    1. <span data-ttu-id="b8fb9-182">Dona Branca</span><span class="sxs-lookup"><span data-stu-id="b8fb9-182">Mrs. White</span></span>
- <span data-ttu-id="b8fb9-183">listas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-183">lists</span></span>


## <span data-ttu-id="b8fb9-184">Régua horizontal</span><span class="sxs-lookup"><span data-stu-id="b8fb9-184">Horizontal rule</span></span>
<a id="horizontal-rule" class="xliff"></a>

---

## <span data-ttu-id="b8fb9-185">Tabelas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-185">Tables</span></span>
<a id="tables" class="xliff"></a>

| <span data-ttu-id="b8fb9-186">Tabelas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-186">Tables</span></span>        | <span data-ttu-id="b8fb9-187">São</span><span class="sxs-lookup"><span data-stu-id="b8fb9-187">Are</span></span>           | <span data-ttu-id="b8fb9-188">Legais</span><span class="sxs-lookup"><span data-stu-id="b8fb9-188">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="b8fb9-189">a col. 3 está</span><span class="sxs-lookup"><span data-stu-id="b8fb9-189">col 3 is</span></span>      | <span data-ttu-id="b8fb9-190">alinhada à direita</span><span class="sxs-lookup"><span data-stu-id="b8fb9-190">right-aligned</span></span> | <span data-ttu-id="b8fb9-191">R$ 1600</span><span class="sxs-lookup"><span data-stu-id="b8fb9-191">$1600</span></span> |
| <span data-ttu-id="b8fb9-192">a col. 2 está</span><span class="sxs-lookup"><span data-stu-id="b8fb9-192">col 2 is</span></span>      | <span data-ttu-id="b8fb9-193">centralizada</span><span class="sxs-lookup"><span data-stu-id="b8fb9-193">centered</span></span>      |   <span data-ttu-id="b8fb9-194">R$ 12</span><span class="sxs-lookup"><span data-stu-id="b8fb9-194">$12</span></span> |
| <span data-ttu-id="b8fb9-195">a coluna 1 é, por padrão,</span><span class="sxs-lookup"><span data-stu-id="b8fb9-195">col 1 is default</span></span> | <span data-ttu-id="b8fb9-196">alinhada à esquerda</span><span class="sxs-lookup"><span data-stu-id="b8fb9-196">left-aligned</span></span>     |    <span data-ttu-id="b8fb9-197">R$ 1</span><span class="sxs-lookup"><span data-stu-id="b8fb9-197">$1</span></span> |


## <span data-ttu-id="b8fb9-198">Código</span><span class="sxs-lookup"><span data-stu-id="b8fb9-198">Code</span></span>
<a id="code" class="xliff"></a>

### <span data-ttu-id="b8fb9-199">Codeblock</span><span class="sxs-lookup"><span data-stu-id="b8fb9-199">Codeblock</span></span>
<a id="codeblock" class="xliff"></a>

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <span data-ttu-id="b8fb9-200">Código em linha</span><span class="sxs-lookup"><span data-stu-id="b8fb9-200">In-line code</span></span>
<a id="in-line-code" class="xliff"></a>

<span data-ttu-id="b8fb9-201">Este é um exemplo de `in-line code`.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-201">This is an example of `in-line code`.</span></span>

## <span data-ttu-id="b8fb9-202">Blockquotes</span><span class="sxs-lookup"><span data-stu-id="b8fb9-202">Blockquotes</span></span>
<a id="blockquotes" class="xliff"></a>

> <span data-ttu-id="b8fb9-203">A seca já durava dez milhões de anos, e o reino dos terríveis lagartos havia terminado há tempos.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-203">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="b8fb9-204">Aqui no Equador, no continente que um dia seria conhecido como África, a batalha pela sobrevivência atingiu um novo clímax de ferocidade, e o vencedor ainda não era conhecido.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-204">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="b8fb9-205">Nesta terra estéril e desértica, apenas os pequenos, os velozes ou os selvagens poderiam prosperar, ou mesmo ter esperança de sobreviver.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-205">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <span data-ttu-id="b8fb9-206">Imagens</span><span class="sxs-lookup"><span data-stu-id="b8fb9-206">Images</span></span>
<a id="images" class="xliff"></a>

### <span data-ttu-id="b8fb9-207">Imagem Estática</span><span class="sxs-lookup"><span data-stu-id="b8fb9-207">Static Image</span></span>
<a id="static-image" class="xliff"></a>

![este é o texto alternativo](./media/AzRMS_elements.png)

### <span data-ttu-id="b8fb9-209">Imagem Vinculada</span><span class="sxs-lookup"><span data-stu-id="b8fb9-209">Linked Image</span></span>
<a id="linked-image" class="xliff"></a>

[![texto alternativo para imagem vinculada](./media/AzRMS_elements.png)]<span data-ttu-id="b8fb9-210">(https://azure.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-210">(https://azure.microsoft.com)</span></span> 

### <span data-ttu-id="b8fb9-211">Gif animado</span><span class="sxs-lookup"><span data-stu-id="b8fb9-211">Animated gif</span></span>
<a id="animated-gif" class="xliff"></a>

![gif animado](./media/hololens.gif)

## <span data-ttu-id="b8fb9-213">Alertas</span><span class="sxs-lookup"><span data-stu-id="b8fb9-213">Alerts</span></span>
<a id="alerts" class="xliff"></a>

### <span data-ttu-id="b8fb9-214">Observação</span><span class="sxs-lookup"><span data-stu-id="b8fb9-214">Note</span></span>
<a id="note" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="b8fb9-215">Isso é uma OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="b8fb9-215">This is NOTE</span></span>

### <span data-ttu-id="b8fb9-216">Aviso</span><span class="sxs-lookup"><span data-stu-id="b8fb9-216">Warning</span></span>
<a id="warning" class="xliff"></a>

> [!WARNING]
> <span data-ttu-id="b8fb9-217">Isso é um AVISO</span><span class="sxs-lookup"><span data-stu-id="b8fb9-217">This is WARNING</span></span>

### <span data-ttu-id="b8fb9-218">Dica</span><span class="sxs-lookup"><span data-stu-id="b8fb9-218">Tip</span></span>
<a id="tip" class="xliff"></a>

> [!TIP]
> <span data-ttu-id="b8fb9-219">Isso é uma DICA</span><span class="sxs-lookup"><span data-stu-id="b8fb9-219">This is TIP</span></span>

### <span data-ttu-id="b8fb9-220">Importante</span><span class="sxs-lookup"><span data-stu-id="b8fb9-220">Important</span></span>
<a id="important" class="xliff"></a>

> [!IMPORTANT]
> <span data-ttu-id="b8fb9-221">Isso é IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="b8fb9-221">This is IMPORTANT</span></span>

## <span data-ttu-id="b8fb9-222">Vídeos</span><span class="sxs-lookup"><span data-stu-id="b8fb9-222">Videos</span></span>
<a id="videos" class="xliff"></a>

### <span data-ttu-id="b8fb9-223">Channel 9</span><span class="sxs-lookup"><span data-stu-id="b8fb9-223">Channel 9</span></span>
<a id="channel-9" class="xliff"></a>

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <span data-ttu-id="b8fb9-224">Youtube</span><span class="sxs-lookup"><span data-stu-id="b8fb9-224">Youtube</span></span>
<a id="youtube" class="xliff"></a>

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <span data-ttu-id="b8fb9-225">docs.ms extentions</span><span class="sxs-lookup"><span data-stu-id="b8fb9-225">docs.ms extentions</span></span>
<a id="docsms-extentions" class="xliff"></a>

### <span data-ttu-id="b8fb9-226">Botão</span><span class="sxs-lookup"><span data-stu-id="b8fb9-226">Button</span></span>
<a id="button" class="xliff"></a>

> [!div class="button"]
[<span data-ttu-id="b8fb9-227">links de botão</span><span class="sxs-lookup"><span data-stu-id="b8fb9-227">button links</span></span>](/rights-management)

### <span data-ttu-id="b8fb9-228">Seletor</span><span class="sxs-lookup"><span data-stu-id="b8fb9-228">Selector</span></span>
<a id="selector" class="xliff"></a>

> [!div class="op_single_selector"]
- [<span data-ttu-id="b8fb9-229">foo</span><span class="sxs-lookup"><span data-stu-id="b8fb9-229">foo</span></span>](/rights-management/template.md)
- [<span data-ttu-id="b8fb9-230">barra</span><span class="sxs-lookup"><span data-stu-id="b8fb9-230">bar</span></span>](/rights-management/scratch.md)

### <span data-ttu-id="b8fb9-231">Passo a passo</span><span class="sxs-lookup"><span data-stu-id="b8fb9-231">Step-By-Step</span></span>
<a id="step-by-step" class="xliff"></a>

>[!div class="step-by-step"]
<span data-ttu-id="b8fb9-232">[Pré](https://www.example.com)
[Avançar](https://www.example.com)</span><span class="sxs-lookup"><span data-stu-id="b8fb9-232">[Pre](https://www.example.com)
[Next](https://www.example.com)</span></span>