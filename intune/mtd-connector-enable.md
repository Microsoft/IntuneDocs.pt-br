---
title: "Habilitar o conector de Defesa Contra Ameaças Móveis com o Intune"
titleSuffix: Intune on Azure
description: "Habilite o conector de Defesa Contra Ameaças Móveis no Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 38fb9977ed8af05380a265ee254259acef7b43f0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="aa968-103">Habilitar a Defesa Contra Ameaças Móveis no Intune</span><span class="sxs-lookup"><span data-stu-id="aa968-103">Enable Mobile Threat Defense in Intune</span></span>
<a id="enable-mobile-threat-defense-in-intune" class="xliff"></a>

<span data-ttu-id="aa968-104">Para habilitar a conexão MTD (Defesa contra Ameaças Móveis) no Intune, você já deve ter configurado o Conector do Intune no console da solução MTD.</span><span class="sxs-lookup"><span data-stu-id="aa968-104">To enable the Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Connector in the MTD solution console.</span></span>

## <span data-ttu-id="aa968-105">Para habilitar o conector MTD</span><span class="sxs-lookup"><span data-stu-id="aa968-105">To enable the MTD connector</span></span>
<a id="to-enable-the-mtd-connector" class="xliff"></a>

1. <span data-ttu-id="aa968-106">Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="aa968-106">Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span> <span data-ttu-id="aa968-107">Quando entrar com êxito, você verá o **Painel do Azure**.</span><span class="sxs-lookup"><span data-stu-id="aa968-107">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

2. <span data-ttu-id="aa968-108">No **Painel do Azure**, escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="aa968-108">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="aa968-109">Escolha **Intune** e o **Painel do Intune** se abrirá.</span><span class="sxs-lookup"><span data-stu-id="aa968-109">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="aa968-110">No **Painel do Intune**, escolha **Conformidade do dispositivo** e, depois, **Defesa contra Ameaças Móveis** na seção **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="aa968-110">On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.</span></span>

5. <span data-ttu-id="aa968-111">Na folha **Defesa contra Ameaças Móveis**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa968-111">On the **Mobile Threat Defense** blade, choose **Add**.</span></span>

6. <span data-ttu-id="aa968-112">Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="aa968-112">Choose your MTD solution as the **Mobile Threat Defense connector to setup** from the drop-down list.</span></span>

    ![Configuração do MTD no Portal do Azure no Intune](./media/enable-mtd-connector-1.png)

7. <span data-ttu-id="aa968-114">Habilite as opções de alternância de acordo com os requisitos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="aa968-114">Enable the toggle options according to your organization's requirements.</span></span>

## <span data-ttu-id="aa968-115">Opções de alternância de MTD</span><span class="sxs-lookup"><span data-stu-id="aa968-115">MTD toggle options</span></span>
<a id="mtd-toggle-options" class="xliff"></a>

<span data-ttu-id="aa968-116">Decida quais opções de alternância do MTD você precisa habilitar de acordo com os requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="aa968-116">You can decide which MTD toggle options you need to enable according to your organization's requirements.</span></span> <span data-ttu-id="aa968-117">Veja mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="aa968-117">Here's more details:</span></span>

- <span data-ttu-id="aa968-118">**Conectar dispositivos Android 4.1 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.</span><span class="sxs-lookup"><span data-stu-id="aa968-118">**Connect Android 4.1+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="aa968-119">**Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados sobre um dispositivo nesta plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="aa968-119">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="aa968-120">**Conectar dispositivos iOS 8.0 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.</span><span class="sxs-lookup"><span data-stu-id="aa968-120">**Connect iOS 8.0+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="aa968-121">**Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados sobre um dispositivo nesta plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="aa968-121">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="aa968-122">**Bloquear versões do sistema operacional sem suporte**: bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.</span><span class="sxs-lookup"><span data-stu-id="aa968-122">**Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.</span></span>

- <span data-ttu-id="aa968-123">**Número de dias até que o parceiro seja considerado sem resposta**: número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão.</span><span class="sxs-lookup"><span data-stu-id="aa968-123">**Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost.</span></span> <span data-ttu-id="aa968-124">O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.</span><span class="sxs-lookup"><span data-stu-id="aa968-124">Intune ignores compliance state for unresponsive MTD partners.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="aa968-125">Você deve adicionar e atribuir os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="aa968-125">You must add and assign the MTD apps before creating the device compliance and the conditional access policy rules.</span></span> <span data-ttu-id="aa968-126">Isso garante que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="aa968-126">This ensures that the MTD app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

> [!TIP]
> <span data-ttu-id="aa968-127">Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD na folha Defesa contra Ameaças Móveis.</span><span class="sxs-lookup"><span data-stu-id="aa968-127">You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.</span></span>

## <span data-ttu-id="aa968-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="aa968-128">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="aa968-129">Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis com o Intune</span><span class="sxs-lookup"><span data-stu-id="aa968-129">Create Mobile Threat Defense device compliance policy with Intune</span></span>](mtd-device-compliance-policy-create.md)
