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
ms.openlocfilehash: a5dfef35c9f2d2fa543d8b19c2566b25d47b8f72
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
<<<<<<< HEAD
# <a name="enable-mobile-threat-defense-in-intune"></a><span data-ttu-id="03e05-103">Habilitar a Defesa Contra Ameaças Móveis no Intune</span><span class="sxs-lookup"><span data-stu-id="03e05-103">Enable Mobile Threat Defense in Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="03e05-104">Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.</span><span class="sxs-lookup"><span data-stu-id="03e05-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="03e05-105">Para habilitar a conexão MTD (Defesa contra Ameaças Móveis) no Intune, você já deve ter configurado o Conector do Intune no console da solução MTD.</span><span class="sxs-lookup"><span data-stu-id="03e05-105">To enable the Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Connector in the MTD solution console.</span></span>

## <a name="to-enable-the-mtd-connector"></a><span data-ttu-id="03e05-106">Para habilitar o conector MTD</span><span class="sxs-lookup"><span data-stu-id="03e05-106">To enable the MTD connector</span></span>

1. <span data-ttu-id="03e05-107">Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="03e05-107">Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span> <span data-ttu-id="03e05-108">Quando entrar com êxito, você verá o **Painel do Azure**.</span><span class="sxs-lookup"><span data-stu-id="03e05-108">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

2. <span data-ttu-id="03e05-109">No **Painel do Azure**, escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="03e05-109">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="03e05-110">Escolha **Intune** e o **Painel do Intune** se abrirá.</span><span class="sxs-lookup"><span data-stu-id="03e05-110">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="03e05-111">No **Painel do Intune**, escolha **Conformidade do dispositivo** e, depois, **Defesa contra Ameaças Móveis** na seção **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="03e05-111">On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.</span></span>

5. <span data-ttu-id="03e05-112">Na folha **Defesa contra Ameaças Móveis**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="03e05-112">On the **Mobile Threat Defense** blade, choose **Add**.</span></span>

6. <span data-ttu-id="03e05-113">Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="03e05-113">Choose your MTD solution as the **Mobile Threat Defense connector to setup** from the drop-down list.</span></span>

    ![Configuração do MTD no Portal do Azure no Intune](./media/enable-mtd-connector-1.png)

7. <span data-ttu-id="03e05-115">Habilite as opções de alternância de acordo com os requisitos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="03e05-115">Enable the toggle options according to your organization's requirements.</span></span>

## <a name="mtd-toggle-options"></a><span data-ttu-id="03e05-116">Opções de alternância de MTD</span><span class="sxs-lookup"><span data-stu-id="03e05-116">MTD toggle options</span></span>

<span data-ttu-id="03e05-117">Decida quais opções de alternância do MTD você precisa habilitar de acordo com os requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="03e05-117">You can decide which MTD toggle options you need to enable according to your organization's requirements.</span></span> <span data-ttu-id="03e05-118">Veja mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="03e05-118">Here's more details:</span></span>

- <span data-ttu-id="03e05-119">**Conectar dispositivos Android 4.1 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.</span><span class="sxs-lookup"><span data-stu-id="03e05-119">**Connect Android 4.1+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="03e05-120">**Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados sobre um dispositivo nesta plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="03e05-120">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="03e05-121">**Conectar dispositivos iOS 8.0 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.</span><span class="sxs-lookup"><span data-stu-id="03e05-121">**Connect iOS 8.0+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="03e05-122">**Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados sobre um dispositivo nesta plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="03e05-122">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="03e05-123">**Bloquear versões do sistema operacional sem suporte**: bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.</span><span class="sxs-lookup"><span data-stu-id="03e05-123">**Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.</span></span>

- <span data-ttu-id="03e05-124">**Número de dias até que o parceiro seja considerado sem resposta**: número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão.</span><span class="sxs-lookup"><span data-stu-id="03e05-124">**Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost.</span></span> <span data-ttu-id="03e05-125">O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.</span><span class="sxs-lookup"><span data-stu-id="03e05-125">Intune ignores compliance state for unresponsive MTD partners.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="03e05-126">Você deve adicionar e atribuir os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="03e05-126">You must add and assign the MTD apps before creating the device compliance and the conditional access policy rules.</span></span> <span data-ttu-id="03e05-127">Isso garante que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="03e05-127">This ensures that the MTD app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

> [!TIP]
> <span data-ttu-id="03e05-128">Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD na folha Defesa contra Ameaças Móveis.</span><span class="sxs-lookup"><span data-stu-id="03e05-128">You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03e05-129">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="03e05-129">Next steps</span></span>

[<span data-ttu-id="03e05-130">Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis com o Intune</span><span class="sxs-lookup"><span data-stu-id="03e05-130">Create Mobile Threat Defense device compliance policy with Intune</span></span>](mtd-device-compliance-policy-create.md)
=======
# <a name="enable-mobile-threat-defense-in-intune"></a>Habilitar a Defesa Contra Ameaças Móveis no Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

Para habilitar a conexão MTD (Defesa contra Ameaças Móveis) no Intune, você já deve ter configurado o Conector do Intune no console da solução MTD.

## <a name="to-enable-the-mtd-connector"></a>Para habilitar o conector MTD

1. Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune. Quando entrar com êxito, você verá o **Painel do Azure**.

2. No **Painel do Azure**, escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** e o **Painel do Intune** se abrirá.

4. No **Painel do Intune**, escolha **Conformidade do dispositivo** e, depois, **Defesa contra Ameaças Móveis** na seção **Configuração**.

5. Na folha **Defesa contra Ameaças Móveis**, escolha **Adicionar**.

6. Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.

    ![Configuração do MTD no Portal do Azure no Intune](./media/enable-mtd-connector-1.png)

7. Habilite as opções de alternância de acordo com os requisitos de sua organização.

## <a name="mtd-toggle-options"></a>Opções de alternância de MTD

Decida quais opções de alternância do MTD você precisa habilitar de acordo com os requisitos da sua organização. Veja mais detalhes:

- **Conectar dispositivos Android 4.1 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.
    - **Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados sobre um dispositivo nesta plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.
<br></br>
- **Conectar dispositivos iOS 8.0 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.
    - **Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados sobre um dispositivo nesta plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.
<br></br>
- **Bloquear versões do sistema operacional sem suporte**: bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.

- **Número de dias até que o parceiro seja considerado sem resposta**: número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!IMPORTANT] 
> Você deve adicionar e atribuir os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional. Isso garante que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD na folha Defesa contra Ameaças Móveis.

## <a name="next-steps"></a>Próximas etapas

[Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis com o Intune](mtd-device-compliance-policy-create.md)
>>>>>>> live
