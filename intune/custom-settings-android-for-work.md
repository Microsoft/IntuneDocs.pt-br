---
title: "Configurações de perfil personalizadas do Intune para Android for Work"
titleSuffix: Intune on Azure
description: "Saiba como criar configurações de perfil personalizado do Intune para dispositivos Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b48fc7bd784b5d6d531ef5bf28fe835e394b106
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="4a024-103">Criar configurações de perfil personalizadas do Intune para dispositivos com Android for Work</span><span class="sxs-lookup"><span data-stu-id="4a024-103">Create Intune custom profile settings for Android for Work devices</span></span>
<a id="create-intune-custom-profile-settings-for-android-for-work-devices" class="xliff"></a>

<span data-ttu-id="4a024-104">Use a política de configuração personalizada do Android for Work do Intune para atribuir configurações OMA-URI, que podem ser usadas para controlar funcionalidades em dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="4a024-104">Use the Intune Android for Work custom configuration policy to assign OMA-URI settings that can be used to control features on Android for Work devices.</span></span> <span data-ttu-id="4a024-105">Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4a024-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="4a024-106">Essa funcionalidade destina-se a permitir que você atribua configurações do Android que não são configuráveis com as políticas do Intune.</span><span class="sxs-lookup"><span data-stu-id="4a024-106">This capability is intended to allow you to assign Android settings that are not configurable with Intune policies.</span></span> <span data-ttu-id="4a024-107">No momento, o Intune dá suporte a um número limitado de políticas personalizadas do Android.</span><span class="sxs-lookup"><span data-stu-id="4a024-107">Intune supports a limited number of Android custom policies at present.</span></span> <span data-ttu-id="4a024-108">Consulte os exemplos neste tópico para descobrir quais políticas podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="4a024-108">See the examples in this topic to find out which policies you can configure.</span></span>

## <span data-ttu-id="4a024-109">Criar um perfil personalizado</span><span class="sxs-lookup"><span data-stu-id="4a024-109">Create a custom profile</span></span>
<a id="create-a-custom-profile" class="xliff"></a>

1. <span data-ttu-id="4a024-110">Use as instruções em [Como definir configurações personalizadas do dispositivo](custom-settings-configure.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="4a024-110">Use the instructions in [How to configure custom device settings](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="4a024-111">Na folha **Configurações personalizadas do OMA-URI**, escolha **Adicionar** para adicionar uma nova configuração.</span><span class="sxs-lookup"><span data-stu-id="4a024-111">On the **Custom OMA-URI Settings** blade, choose **Add** to add a new setting.</span></span>
3. <span data-ttu-id="4a024-112">Na folha **Adicionar Linha**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4a024-112">On the **Add Row** blade, configure the following:</span></span>
    - <span data-ttu-id="4a024-113">**Nome** - insira um nome exclusivo para as configurações personalizadas do Android for Work para ajudar a identificá-las no portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="4a024-113">**Name** - Enter a unique name for the Android for work custom settings to help you identify it in the Intune portal.</span></span>
    - <span data-ttu-id="4a024-114">**Descrição** - forneça uma descrição que dê uma visão geral da política personalizada do Android e outras informações relevantes que o ajudarão a localizá-la.</span><span class="sxs-lookup"><span data-stu-id="4a024-114">**Description** - Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.</span></span>
    - <span data-ttu-id="4a024-115">**OMA-URI** - insira o OMA-URI para o qual você deseja fornecer uma configuração.</span><span class="sxs-lookup"><span data-stu-id="4a024-115">**OMA-URI** - Enter the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="4a024-116">**Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="4a024-116">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="4a024-117">Escolha entre **Cadeia de caracteres**, **Cadeia de caracteres (arquivo XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante**, **Booliano** ou **Base64 (arquivo)**.</span><span class="sxs-lookup"><span data-stu-id="4a024-117">Choose from **String**, **String (XML file)**, **Date and time**, **Integer**, **Floating point**, **Boolean**, or **Base64 (file)**.</span></span>
    - <span data-ttu-id="4a024-118">**Valor** - especifique o valor a ser associado ao OMA-URI especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4a024-118">**Value** - Specify the value to associate with the OMA-URI that you specified previously.</span></span> <span data-ttu-id="4a024-119">O método usado para fornecer esse valor varia de acordo com o tipo de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="4a024-119">The method you use to supply this value will vary according to the data type you selected.</span></span> <span data-ttu-id="4a024-120">Por exemplo, se você escolher **Data e hora**, selecionará o valor de um seletor de data.</span><span class="sxs-lookup"><span data-stu-id="4a024-120">For example, if you chose **Date and time**, you'll select the value from a date picker.</span></span>
4. <span data-ttu-id="4a024-121">Quando terminar, escolha OK para retornar para às **Configurações Personalizadas de OMA-URI** e, em seguida, adicione mais configurações ou escolha **Criar** para criar o perfil personalizado.</span><span class="sxs-lookup"><span data-stu-id="4a024-121">When you have finished, choose OK to return to the **Custom OMA-URI Settings**, and then add more settings, or choose **Create** to create the custom profile.</span></span>


## <span data-ttu-id="4a024-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4a024-122">Example</span></span>
<a id="example" class="xliff"></a>

<span data-ttu-id="4a024-123">Neste exemplo, você criará um perfil personalizado que pode ser usado para restringir a permissão de ações de copiar e colar entre aplicativos pessoais e de trabalho em dispositivos gerenciados com Android for Work.</span><span class="sxs-lookup"><span data-stu-id="4a024-123">In this example, you'll create a custom profile that can be used to restrict whether copy and paste actions between work and personal apps are allowed on managed Android for Work devices.</span></span>

1. <span data-ttu-id="4a024-124">Use o procedimento neste tópico para criar um perfil personalizado do Android for Work usando os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4a024-124">Use the procedure in this topic to create a custom profile for Android for Work devices using the following values:</span></span>
    - <span data-ttu-id="4a024-125">**Nome** - insira "Bloquear copiar e colar" ou o texto de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="4a024-125">**Name** - Enter "Block copy and paste" or text of your own choosing.</span></span>
    - <span data-ttu-id="4a024-126">**Descrição** - insira "Bloqueia copiar/colar entre aplicativos pessoais e de trabalho" ou o texto de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="4a024-126">**Description** - Enter "Blocks copy/paste between work and personal apps" or text of your own choosing.</span></span>
    - <span data-ttu-id="4a024-127">**OMA-URI** - insira **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.</span><span class="sxs-lookup"><span data-stu-id="4a024-127">**OMA-URI** - Enter **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.</span></span>
    - <span data-ttu-id="4a024-128">**Tipo de dados** - selecione **Booliano** para indicar se o valor para esse OMA-URI é **True** ou **False**.</span><span class="sxs-lookup"><span data-stu-id="4a024-128">**Data type** - Select **Boolean** to indicate that the value for this OMA-URI is either **True** or **False**.</span></span>
    - <span data-ttu-id="4a024-129">**Valor** -selecione **True**.</span><span class="sxs-lookup"><span data-stu-id="4a024-129">**Value** - Select **True**.</span></span>
2. <span data-ttu-id="4a024-130">A configuração deve ficar semelhante a esta imagem.</span><span class="sxs-lookup"><span data-stu-id="4a024-130">You should end up with a setting looking similar to this image.</span></span>
<span data-ttu-id="4a024-131">![Bloquear copiar e colar para Android for Work.](./media/custom-policy-afw-copy-paste.png)</span><span class="sxs-lookup"><span data-stu-id="4a024-131">![Block copy and paste for Android for Work.](./media/custom-policy-afw-copy-paste.png)</span></span>
3. <span data-ttu-id="4a024-132">Agora, quando você atribui esse perfil personalizado aos dispositivos Android for Work que você gerencia, as ações de copiar e colar serão bloqueadas entre aplicativos nos perfis de trabalho e pessoais.</span><span class="sxs-lookup"><span data-stu-id="4a024-132">Now, when you assign this custom profile to Android for Work devices you manage, copy and paste will be blocked between apps in the work, and personal profiles.</span></span>