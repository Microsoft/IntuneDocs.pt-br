---
title: "Teste e validação do Intune"
description: "Este artigo ajudará você com todos os detalhes que precisam ser considerados ao testar e validar a solução somente na nuvem do Intune em seu ambiente."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ea2974c4724564cd8f9972fdb238b06d1b100e6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="62e76-103">Teste e validação do Intune</span><span class="sxs-lookup"><span data-stu-id="62e76-103">Intune testing and validation</span></span>
<a id="intune-testing-and-validation" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="62e76-104">A fase de teste deve ser realizada durante e após a fase de implementação. Você precisará ter contas, grupos e dispositivos de teste para testar todos os cenários de TI (administrador) e de usuário final (caso de uso) necessários identificados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="62e76-104">The testing phase should be during and after the implementation phase, you will need to have test accounts, groups, and devices for testing all required IT (admin) and end user (use case) scenarios previously identified.</span></span>

<span data-ttu-id="62e76-105">É recomendável incorporar a equipe de suporte de TI/assistência técnica na fase de teste para que a documentação de suporte seja criada e a equipe de suporte de TI/assistência técnica fique satisfeita de dar suporte ao produto.</span><span class="sxs-lookup"><span data-stu-id="62e76-105">It's recommended to incorporate your IT support/helpdesk staff in the testing phase so that support documentation is created, and the IT support/helpdesk staff become comfortable supporting the product.</span></span> <span data-ttu-id="62e76-106">Se um componente ou cenário não funcionar de acordo com os casos de uso, lembre-se de documentar as alterações necessárias e incluir o motivo da alteração.</span><span class="sxs-lookup"><span data-stu-id="62e76-106">If a component or scenario does not function based on the use cases, make sure to document the necessary changes and include the reason a change was made.</span></span>

## <span data-ttu-id="62e76-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="62e76-107">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="62e76-108">É recomendável documentar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="62e76-108">It’s recommended to document the following:</span></span>

-   <span data-ttu-id="62e76-109">**Critérios de teste:** identifica os parâmetros de comparação com os quais comparar.</span><span class="sxs-lookup"><span data-stu-id="62e76-109">**Test criteria:** Identifies the benchmarks to be measured against.</span></span>

-   <span data-ttu-id="62e76-110">**Componentes de design:** deve haver, pelo menos, um critério de teste.</span><span class="sxs-lookup"><span data-stu-id="62e76-110">**Design components:** must exist in at least 1 testing criteria.</span></span>

<span data-ttu-id="62e76-111">Se não houver nenhum componente de design em, pelo menos, um critério de teste alinhado a um requisito ou cenário, considere se o componente de design é necessário ou não.</span><span class="sxs-lookup"><span data-stu-id="62e76-111">If a design component does not exist in at least 1 test criteria that aligns to a requirement or scenario, consider whether the design component is required or not.</span></span> <span data-ttu-id="62e76-112">Além disso, garanta que você tem os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="62e76-112">In addition, make sure to have the following items:</span></span>

-   <span data-ttu-id="62e76-113">**Contas:** as contas usadas no teste devem ser contas de teste licenciadas para o EMS e o Office 365 para testar todos os cenários de caso de uso.</span><span class="sxs-lookup"><span data-stu-id="62e76-113">**Accounts:** The accounts used in testing should be test accounts that are licensed for EMS and Office 365 to test all use case scenarios.</span></span>

-   <span data-ttu-id="62e76-114">**Dispositivos:** os dispositivos usados neste ponto devem ser dispositivos de teste que potencialmente possam ser apagados ou redefinidos para os padrões de fábrica.</span><span class="sxs-lookup"><span data-stu-id="62e76-114">**Devices:** The devices used at this point should be test devices that could potentially be wiped or reset to factory defaults.</span></span>

-   <span data-ttu-id="62e76-115">**Componentes de integração:** todos os componentes de integração (Certificate Connector, conector de serviço a serviço do Intune para o Exchange hospedado e Exchange Connector local do Intune) devem ser instalados e configurados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="62e76-115">**Integration components:** All integration components (Certificate Connector, Intune service to service connector for hosted Exchange, and Intune on-premises Exchange connector) should be installed and configured if needed.</span></span>

<span data-ttu-id="62e76-116">Alterações de design podem ser necessárias para considerar problemas imprevistos.</span><span class="sxs-lookup"><span data-stu-id="62e76-116">Design changes could be needed to accommodate unforeseen difficulties.</span></span> <span data-ttu-id="62e76-117">Além disso, todas as alterações de design devem ser totalmente documentadas com o motivo de cada alteração.</span><span class="sxs-lookup"><span data-stu-id="62e76-117">In addition, all design changes should be fully documented with the reason for each change.</span></span> <span data-ttu-id="62e76-118">Aqui temos um exemplo para ilustrar o que uma alteração poderia ser:</span><span class="sxs-lookup"><span data-stu-id="62e76-118">Here's an example to illustrate what a change could be:</span></span>

-   <span data-ttu-id="62e76-119">Você pode perceber que não atende aos requisitos do NDES (Serviço de Registro de Dispositivo de Rede) e também descobrir que os perfis de VPN e Wi-Fi podem ser configurados com uma AC raiz, atendendo aos mesmos requisitos sem uma implementação de NDES.</span><span class="sxs-lookup"><span data-stu-id="62e76-119">You might realize that you don’t meet the requirements of Network Device Enrollment Service (NDES), and you also learn that the VPN and Wi-Fi profiles can be configured with a root CA satisfying the same requirements without a NDES implementation.</span></span>

<span data-ttu-id="62e76-120">Você pode enfrentar desafios ou problemas que exigem diretrizes técnicas ou uma solução de problemas especializada durante o processo de teste e validação.</span><span class="sxs-lookup"><span data-stu-id="62e76-120">You might experience challenges or issues that require technical guidance, or specialized troubleshooting during the testing and validation process.</span></span> <span data-ttu-id="62e76-121">É recomendável buscar assistência por meio dos canais do Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62e76-121">It’s recommended to seek assistance through the Microsoft support channels.</span></span>

-   [<span data-ttu-id="62e76-122">Saiba como obter suporte do Intune</span><span class="sxs-lookup"><span data-stu-id="62e76-122">Learn how to get Intune support</span></span>](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   <span data-ttu-id="62e76-123">[Dicas gerais de solução de problemas para o Microsoft Intune](/intune-classic/troubleshoot/general-troubleshooting-tips-for-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="62e76-123">[General troubleshooting tips for Microsoft Intune](/intune-classic/troubleshoot/general-troubleshooting-tips-for-microsoft-intune).</span></span>

-   [<span data-ttu-id="62e76-124">Saiba como obter suporte para o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="62e76-124">Learn how to get support for Microsoft Intune.</span></span>](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [<span data-ttu-id="62e76-125">Contatar o suporte telefônico assistido do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="62e76-125">Contact assisted phone support for Microsoft Intune</span></span>](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <span data-ttu-id="62e76-126">Teste de validação funcional</span><span class="sxs-lookup"><span data-stu-id="62e76-126">Functional validation testing</span></span>
<a id="functional-validation-testing" class="xliff"></a>

<span data-ttu-id="62e76-127">A validação funcional consiste em testar cada componente e configuração para determinar se estão funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="62e76-127">Functional validation consists of testing each component and configuration to determine if it is working correctly.</span></span> <span data-ttu-id="62e76-128">Veja um exemplo de teste de validação na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="62e76-128">An example of validation testing is in the table below.</span></span>

![Seção 9 tabela 1](./media/section-9-image-1-table.PNG)

## <span data-ttu-id="62e76-130">Teste de validação de caso de uso</span><span class="sxs-lookup"><span data-stu-id="62e76-130">Use case validation testing</span></span>
<a id="use-case-validation-testing" class="xliff"></a>

<span data-ttu-id="62e76-131">O teste de validação de caso de uso deve ser realizado para verificar se os cenários estão completos e funcionais.</span><span class="sxs-lookup"><span data-stu-id="62e76-131">Use case validation testing should be performed to verify the scenarios are complete and functional.</span></span> <span data-ttu-id="62e76-132">Há dois tipos de cenários de caso de uso: administrador de TI e usuário final.</span><span class="sxs-lookup"><span data-stu-id="62e76-132">There are two types of use case scenarios, IT admin and end user.</span></span>

### <span data-ttu-id="62e76-133">Administrador de TI</span><span class="sxs-lookup"><span data-stu-id="62e76-133">IT Admin</span></span>
<a id="it-admin" class="xliff"></a>

<span data-ttu-id="62e76-134">O teste de validação do administrador de TI deve ser realizado para validar se uma ação Administrativa executada em um dispositivo ou usuário está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="62e76-134">IT Admin validation testing should be performed to validate that Administrative action performed on a device or user functions correctly.</span></span> <span data-ttu-id="62e76-135">Abaixo temos um exemplo de cenário de validação de ponta a ponta do administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="62e76-135">Below is an example of an IT admin end to end validation scenario.</span></span>

![Seção 9 tabela 2](./media/section-9-image-2-table.PNG)

### <span data-ttu-id="62e76-137">Usuário final</span><span class="sxs-lookup"><span data-stu-id="62e76-137">End user</span></span>
<a id="end-user" class="xliff"></a>

<span data-ttu-id="62e76-138">O teste de validação do usuário final deve ser realizado para validar se a experiência do usuário final ocorre como esperado e é apresentada corretamente em todas as comunicações com o usuário.</span><span class="sxs-lookup"><span data-stu-id="62e76-138">End user validation testing should be performed to validate that the end user experience is as expected and presented correctly in all user communications.</span></span> <span data-ttu-id="62e76-139">É importante validar se a experiência do usuário final está correta, pois uma falha na validação poderá levar a taxas de adoção mais baixas e um maior volume de chamadas de assistência técnica.</span><span class="sxs-lookup"><span data-stu-id="62e76-139">It is important to validate the end user experience is correct as failure to validate can lead to lower adoption rates and higher volume of helpdesk calls.</span></span>

![Seção 9 tabela 3](./media/section-9-image-3-table.PNG)

## <span data-ttu-id="62e76-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="62e76-141">Next Steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="62e76-142">Agora que você testou e validou os cenários de caso de uso e funcionais do Intune, você está pronto para a distribuição de produção do Intune.</span><span class="sxs-lookup"><span data-stu-id="62e76-142">Now that you have tested and validated your Intune functional and user case scenarios, you're ready for your Intune production rollout.</span></span> <span data-ttu-id="62e76-143">Consulte [Recursos adicionais](planning-guide-resources.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="62e76-143">Refer to [Additional resources](planning-guide-resources.md) for more information.</span></span>
