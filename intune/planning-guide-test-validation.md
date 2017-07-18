---
title: "<span data-ttu-id=\"6baeb-101\">Teste e validação do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"6baeb-101\">Intune testing and validation</span></span>"
description: "<span data-ttu-id=\"6baeb-102\">Os detalhes que você precisa considerar quando você está testando e validando uma solução somente em nuvem do Intune em seu ambiente.</span><span class=\"sxs-lookup\"><span data-stu-id=\"6baeb-102\">The details you need to consider when you are testing and validating an Intune cloud-only solution in your environment.</span></span>"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: ddeb71c6a678ff42b5075d65c2bb4e0d89ae47f1
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2017
---
# <a name="intune-testing-and-validation"></a><span data-ttu-id="6baeb-103">Teste e validação do Intune</span><span class="sxs-lookup"><span data-stu-id="6baeb-103">Intune testing and validation</span></span>

<span data-ttu-id="6baeb-104">A fase de teste ocorre durante e após a fase de implementação.</span><span class="sxs-lookup"><span data-stu-id="6baeb-104">The testing phase occurs both during and after the implementation phase.</span></span> <span data-ttu-id="6baeb-105">Você precisa testar contas, grupos e dispositivos para testar todos os cenários de TI (administrador) e de usuário final (caso de uso) exigidos que você identificou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6baeb-105">You need test accounts, groups, and devices for testing all required IT (admin) and end user (use case) scenarios you have previously identified.</span></span>

<span data-ttu-id="6baeb-106">Recomendamos que você incorpore a equipe de suporte de TI e de assistência técnica na fase de teste para que a documentação de suporte seja criada e a equipe de suporte de TI e de assistência técnica fique satisfeita de dar suporte ao produto.</span><span class="sxs-lookup"><span data-stu-id="6baeb-106">We recommend that you incorporate your IT support and helpdesk staff in the testing phase so that support documentation is created, and the IT support and helpdesk staff become comfortable supporting the product.</span></span> <span data-ttu-id="6baeb-107">Se um componente ou cenário não funcionar de acordo com os casos de uso, lembre-se de documentar as alterações necessárias e incluir o motivo da alteração.</span><span class="sxs-lookup"><span data-stu-id="6baeb-107">If a component or scenario does not function based on the use cases, make sure to document the necessary changes, and include the reason a change was made.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6baeb-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6baeb-108">Before you begin</span></span>

<span data-ttu-id="6baeb-109">Recomendamos que você documente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6baeb-109">We recommend that you document the following:</span></span>

-   <span data-ttu-id="6baeb-110">**Critérios de teste:** identifique os parâmetros de comparação com os quais comparar.</span><span class="sxs-lookup"><span data-stu-id="6baeb-110">**Test criteria:** Identify the benchmarks to be measured against.</span></span>

-   <span data-ttu-id="6baeb-111">**Componentes de design:** devem existir em pelo menos um critério de teste.</span><span class="sxs-lookup"><span data-stu-id="6baeb-111">**Design components:** Must exist in at least one testing criteria.</span></span>

<span data-ttu-id="6baeb-112">Se não houver nenhum componente de design em pelo menos um critério de teste alinhado a um requisito ou cenário, considere se o componente de design é necessário ou não.</span><span class="sxs-lookup"><span data-stu-id="6baeb-112">If a design component does not exist in at least one test criteria that aligns to a requirement or scenario, consider whether the design component is required or not.</span></span> <span data-ttu-id="6baeb-113">Além disso, garanta que você tem os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="6baeb-113">In addition, make sure to have the following items:</span></span>

-   <span data-ttu-id="6baeb-114">**Contas:** as contas de teste licenciadas para o EMS e o Office 365 para testar todos os cenários de caso de uso.</span><span class="sxs-lookup"><span data-stu-id="6baeb-114">**Accounts:** Test accounts that are licensed for EMS and Office 365 to test all use-case scenarios.</span></span>

-   <span data-ttu-id="6baeb-115">**Dispositivos:** dispositivos que podem ser apagados ou redefinidos para as configurações padrão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="6baeb-115">**Devices:** Test devices that can be wiped or reset to factory defaults.</span></span>

-   <span data-ttu-id="6baeb-116">**Componentes de integração:** todos os componentes de integração (Certificate Connector, conector de serviço a serviço do Intune para o Exchange hospedado e Exchange connector local do Intune) devem ser instalados e configurados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="6baeb-116">**Integration components:** All integration components (certificate connector, Intune service-to-service connector for hosted Exchange, and Intune on-premises Exchange connector) should be installed and configured if needed.</span></span>

<span data-ttu-id="6baeb-117">Alterações de design podem ser necessárias para a adequação a problemas imprevistos.</span><span class="sxs-lookup"><span data-stu-id="6baeb-117">You may need design changes to accommodate unforeseen difficulties.</span></span> <span data-ttu-id="6baeb-118">Além disso, todas as alterações de design devem ser totalmente documentadas com o motivo de cada alteração.</span><span class="sxs-lookup"><span data-stu-id="6baeb-118">In addition, all design changes should be fully documented with the reason for each change.</span></span> <span data-ttu-id="6baeb-119">Aqui temos um exemplo para ilustrar o que uma alteração poderia ser:</span><span class="sxs-lookup"><span data-stu-id="6baeb-119">Here's an example to illustrate what a change could be:</span></span>

<blockquote><span data-ttu-id="6baeb-120">Você percebe que não atende aos requisitos do NDES (Serviço de Registro de Dispositivo de Rede) e também descobre que os perfis de VPN e Wi-Fi podem ser configurados com uma AC raiz, atendendo aos mesmos requisitos sem uma implementação de NDES.</span><span class="sxs-lookup"><span data-stu-id="6baeb-120">You realize that you don’t meet the requirements of Network Device Enrollment Service (NDES), and you also learn that the VPN and Wi-Fi profiles can be configured with a root CA satisfying the same requirements without an NDES implementation.</span></span></blockquote>

<span data-ttu-id="6baeb-121">Você pode enfrentar desafios ou problemas que exigem diretrizes técnicas ou uma solução de problemas especializada durante o processo de teste e validação.</span><span class="sxs-lookup"><span data-stu-id="6baeb-121">You might experience challenges or issues that require technical guidance or specialized troubleshooting during the testing and validation process.</span></span> <span data-ttu-id="6baeb-122">Recomendamos que você busque assistência por meio dos canais de Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6baeb-122">We recommend that you seek assistance through the Microsoft support channels.</span></span>

-   [<span data-ttu-id="6baeb-123">Saiba como obter suporte do Intune</span><span class="sxs-lookup"><span data-stu-id="6baeb-123">Learn how to get Intune support</span></span>](get-support.md)

-   [<span data-ttu-id="6baeb-124">Contatar o suporte telefônico assistido do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6baeb-124">Contact assisted phone support for Microsoft Intune</span></span>](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a><span data-ttu-id="6baeb-125">Teste de validação funcional</span><span class="sxs-lookup"><span data-stu-id="6baeb-125">Functional validation testing</span></span>

<span data-ttu-id="6baeb-126">A validação funcional consiste em testar cada componente e configuração para determinar se estão funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="6baeb-126">Functional validation consists of testing each component and configuration to determine if it is working correctly.</span></span> <span data-ttu-id="6baeb-127">Veja um exemplo de teste de validação na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="6baeb-127">An example of validation testing is in the table below.</span></span>

![Seção 9 tabela 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a><span data-ttu-id="6baeb-129">Teste de validação de caso de uso</span><span class="sxs-lookup"><span data-stu-id="6baeb-129">Use-case validation testing</span></span>

<span data-ttu-id="6baeb-130">Realize o teste de validação de caso de uso para verificar se os cenários estão completos e funcionais.</span><span class="sxs-lookup"><span data-stu-id="6baeb-130">Perform use-case validation testing to verify the scenarios are complete and functional.</span></span> <span data-ttu-id="6baeb-131">Há dois tipos de cenários de caso de uso: administrador de TI e usuário final.</span><span class="sxs-lookup"><span data-stu-id="6baeb-131">There are two types of use-case scenarios: IT admin and end user.</span></span>

### <a name="it-admin"></a><span data-ttu-id="6baeb-132">Administrador de TI</span><span class="sxs-lookup"><span data-stu-id="6baeb-132">IT admin</span></span>

<span data-ttu-id="6baeb-133">Realize o teste de validação do administrador de TI para validar se ações administrativas executadas em um dispositivo ou usuário funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="6baeb-133">Perform IT admin validation testing to validate that administrative actions performed on a device or user function correctly.</span></span> <span data-ttu-id="6baeb-134">Abaixo temos um exemplo de cenário de validação de ponta a ponta do administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="6baeb-134">Below is an example of an IT admin end-to-end validation scenario.</span></span>

![Seção 9 tabela 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a><span data-ttu-id="6baeb-136">Usuário final</span><span class="sxs-lookup"><span data-stu-id="6baeb-136">End user</span></span>

<span data-ttu-id="6baeb-137">Realize o teste de validação do usuário final para validar se a experiência do usuário final ocorre como esperado e é apresentada corretamente em todas as comunicações com o usuário.</span><span class="sxs-lookup"><span data-stu-id="6baeb-137">Perform end-user validation testing to validate that the end-user experience is as expected and presented correctly in all user communications.</span></span> <span data-ttu-id="6baeb-138">É importante validar que a experiência do usuário final está correta.</span><span class="sxs-lookup"><span data-stu-id="6baeb-138">It is important to validate that the end-user experience is correct.</span></span> <span data-ttu-id="6baeb-139">Se você não conseguir validar, isso poderá resultar em reduzir as taxas de adoção e volumes maiores de chamadas de assistência técnica.</span><span class="sxs-lookup"><span data-stu-id="6baeb-139">If you fail to validate, it can lead to lower adoption rates and higher volumes of helpdesk calls.</span></span>

![Seção 9 tabela 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a><span data-ttu-id="6baeb-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6baeb-141">Next steps</span></span>

<span data-ttu-id="6baeb-142">Agora que você testou e validou os cenários de caso de uso e funcionais do Intune, você está pronto para a [distribuição de produção do Intune](planning-guide-rollout-plan.md).</span><span class="sxs-lookup"><span data-stu-id="6baeb-142">Now that you have tested and validated your Intune functional and use-case scenarios, you're ready for your [Intune production rollout](planning-guide-rollout-plan.md).</span></span>

<span data-ttu-id="6baeb-143">Consulte [recursos adicionais](planning-guide-resources.md) para obter mais informações e modelos de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6baeb-143">See [additional resources](planning-guide-resources.md) for more planning templates and information.</span></span>
