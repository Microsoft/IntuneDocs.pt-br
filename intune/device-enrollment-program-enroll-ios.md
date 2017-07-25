---
<<<<<<< HEAD
title: "<span data-ttu-id=\"07a81-101\">Registrar dispositivos iOS – Programa de registro de dispositivos</span><span class=\"sxs-lookup\"><span data-stu-id=\"07a81-101\">Enroll iOS devices - Device Enrollment Program</span></span>"
titleSuffix: Intune on Azure
description: <span data-ttu-id="07a81-102">Saiba como registrar dispositivos iOS de propriedade corporativa usando o Programa de registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="07a81-102">Learn how to enroll corporate-owned iOS devices using the Device Enrollment Program."</span></span>
=======
title: "Registrar dispositivos iOS – Programa de registro de dispositivos"
titleSuffix: Intune on Azure
description: Saiba como registrar dispositivos iOS de propriedade corporativa usando o Programa de registro de dispositivos.
>>>>>>> live
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 654a19dd6f1e5f4fd2bda771b0df95b87944db75
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
<<<<<<< HEAD
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a><span data-ttu-id="07a81-103">Configurar o registro de dispositivo iOS com o Programa de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="07a81-103">Set up iOS device enrollment with Device Enrollment Program</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="07a81-104">Este tópico ajuda os administradores de TI a habilitar o registro de dispositivos iOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-104">This topic helps IT admins enable iOS device enrollment for devices purchased through Apple's [Device Enrollment Program (DEP)](https://deploy.apple.com).</span></span> <span data-ttu-id="07a81-105">O Microsoft Intune pode implantar um perfil de registro “sem fio” em dispositivos iOS comprados por meio do DEP.</span><span class="sxs-lookup"><span data-stu-id="07a81-105">Microsoft Intune can deploy an enrollment profile “over the air” to devices purchased through DEP.</span></span> <span data-ttu-id="07a81-106">O administrador nunca precisa tocar em nenhum dispositivo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="07a81-106">The administrator never has to touch each managed device.</span></span> <span data-ttu-id="07a81-107">Um perfil de DEP contém as configurações de gerenciamento que são aplicadas aos dispositivos durante o registro, incluindo opções do Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="07a81-107">A DEP profile contains management settings that are applied to devices during enrollment including Setup Assistant options.</span></span>

<span data-ttu-id="07a81-108">Para habilitar o registro de DEP, você pode usar ambos os portais do Intune e do Apple DEP.</span><span class="sxs-lookup"><span data-stu-id="07a81-108">To enable DEP enrollment, you use both the Intune and Apple DEP portals.</span></span> <span data-ttu-id="07a81-109">É necessário também um número de pedido de compra ou uma lista de IDs a fim de atribuí-los ao Microsoft Intune para gerenciamento no Portal da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-109">A list of IDs or purchase order number is also required so you can assign them to Intune for management in the Apple portal.</span></span>

>[!NOTE]
><span data-ttu-id="07a81-110">O registro DEP não pode ser usado com o [gerenciador de registro de dispositivos](device-enrollment-manager-enroll.md).</span><span class="sxs-lookup"><span data-stu-id="07a81-110">DEP enrollment can't be used with the [device enrollment manager](device-enrollment-manager-enroll.md).</span></span>

<span data-ttu-id="07a81-111">**Etapas para habilitar programas de registro da Apple**</span><span class="sxs-lookup"><span data-stu-id="07a81-111">**Steps to enable enrollment programs from Apple**</span></span>
1. [<span data-ttu-id="07a81-112">Obter um token Apple DEP e atribuir dispositivos</span><span class="sxs-lookup"><span data-stu-id="07a81-112">Get an Apple DEP token and assign devices</span></span>](#get-the-apple-dep-token)
2. [<span data-ttu-id="07a81-113">Criar um perfil de registro</span><span class="sxs-lookup"><span data-stu-id="07a81-113">Create an enrollment profile</span></span>](#create-an-apple-enrollment-profile)
3. [<span data-ttu-id="07a81-114">Sincronize dispositivos gerenciados por DEP</span><span class="sxs-lookup"><span data-stu-id="07a81-114">Synchronize DEP-managed devices</span></span>](#sync-managed-device)
4. [<span data-ttu-id="07a81-115">Atribuir o perfil DEP a dispositivos</span><span class="sxs-lookup"><span data-stu-id="07a81-115">Assign DEP profile to devices</span></span>](#assign-an-enrollment-profile-to-devices)
5. [<span data-ttu-id="07a81-116">Distribuir dispositivos para usuários</span><span class="sxs-lookup"><span data-stu-id="07a81-116">Distribute devices to users</span></span>](#end-user-experience-with-managed-devices)

## <a name="get-the-apple-dep-token"></a><span data-ttu-id="07a81-117">Obter o token Apple DEP</span><span class="sxs-lookup"><span data-stu-id="07a81-117">Get the Apple DEP token</span></span>

<span data-ttu-id="07a81-118">Antes de poder registrar dispositivos iOS de propriedade corporativa com o DEP (Programa de registro de dispositivos) da Apple, você precisa de um token DEP (.p7m) da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-118">Before you can enroll corporate-owned iOS devices with Apple's Device Enrollment Program (DEP), you need a DEP token (.p7m) file from Apple.</span></span> <span data-ttu-id="07a81-119">Esse token permite que o Intune sincronize informações sobre os dispositivos de sua empresa que fazem parte do DEP.</span><span class="sxs-lookup"><span data-stu-id="07a81-119">This token lets Intune sync information about DEP-participating devices that your corporation owns.</span></span> <span data-ttu-id="07a81-120">Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis.</span><span class="sxs-lookup"><span data-stu-id="07a81-120">It also permits Intune to perform enrollment profile uploads to Apple and to assign devices to those profiles.</span></span>

> [!NOTE]
> <span data-ttu-id="07a81-121">Caso exclua o token do console clássico do Microsoft Intune antes de migrar para o Microsoft Azure, o Intune poderá restaurar um token de DEP da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-121">If you delete the token from the Intune classic console before migrating to Azure, Intune might restore a deleted Apple DEP token.</span></span> <span data-ttu-id="07a81-122">Você pode excluir o token de DEP novamente no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="07a81-122">You can delete the DEP token again from the Azure portal.</span></span> <span data-ttu-id="07a81-123">Você pode excluir o token de DEP novamente no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="07a81-123">You can delete the DEP token again from the Azure portal.</span></span>

<span data-ttu-id="07a81-124">**Pré-requisitos**</span><span class="sxs-lookup"><span data-stu-id="07a81-124">**Prerequisites**</span></span>
- [<span data-ttu-id="07a81-125">Apple MDM Push Certificate</span><span class="sxs-lookup"><span data-stu-id="07a81-125">Apple MDM Push certificate</span></span>](apple-mdm-push-certificate-get.md)
- <span data-ttu-id="07a81-126">Inscrição no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)</span><span class="sxs-lookup"><span data-stu-id="07a81-126">Signed up for [Apple's Device Enrollment Program](http://deploy.apple.com)</span></span>

<span data-ttu-id="07a81-127">**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token de DEP da Apple.**</span><span class="sxs-lookup"><span data-stu-id="07a81-127">**Step 1. Download an Intune public key certificate required to create an Apple DEP token.**</span></span><br>
1. <span data-ttu-id="07a81-128">No Portal do Intune, escolha **Registro de dispositivo** e, em seguida, **Registro da Apple** e **Token do Programa de Registro**.</span><span class="sxs-lookup"><span data-stu-id="07a81-128">In the Intune portal, choose **Device enrollment**, and then choose **Apple enrollment**, choose **Enrollment Program Token**.</span></span>

  ![Captura de tela mostrando o painel do Token do Programa de Registro, no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-add.png)

2. <span data-ttu-id="07a81-130">Selecione **Baixar sua chave pública** para baixar e salvar a chave de criptografia (.pem) localmente.</span><span class="sxs-lookup"><span data-stu-id="07a81-130">Select **Download your public key** to download and save the encryption key (.pem) file locally.</span></span> <span data-ttu-id="07a81-131">O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-131">The .pem file is used to request a trust-relationship certificate from the Apple Device Enrollment Program portal.</span></span>

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-download.png)

<span data-ttu-id="07a81-133">**Etapa 2. Criar e baixar um token Apple DEP.**</span><span class="sxs-lookup"><span data-stu-id="07a81-133">**Step 2. Create and download an Apple DEP token.**</span></span><br>
1. <span data-ttu-id="07a81-134">Selecione **Criar um token por meio do Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa.</span><span class="sxs-lookup"><span data-stu-id="07a81-134">Select **Create a token via Apple's Device Enrollment Program** to open Apple's Deployment Program portal, and sign in with your company Apple ID.</span></span> <span data-ttu-id="07a81-135">Você pode usar essa ID da Apple para renovar seu token de DEP.</span><span class="sxs-lookup"><span data-stu-id="07a81-135">You can use this Apple ID to renew your DEP token.</span></span>

  ![Captura de tela mostrando o painel do Token do Programa de Registro, no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-create.png)

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-sign.png)
2.  <span data-ttu-id="07a81-138">No [portal de Programas de Implantação](https://deploy.apple.com) da Apple, selecione **Começar** para **Programa de registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="07a81-138">In Apple's [Deployment Programs portal](https://deploy.apple.com), select **Get Started** for **Device Enrollment Program**.</span></span>

   ![Captura de tela do Programa de Registro clicando em Iniciar no Programa de registro de dispositivos.](./media/enrollment-program-token-started.png)

3. <span data-ttu-id="07a81-140">Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.</span><span class="sxs-lookup"><span data-stu-id="07a81-140">On the **Manage Servers** page, choose **Add MDM Server**.</span></span>
4. <span data-ttu-id="07a81-141">Insira o **Nome do servidor MDM** e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07a81-141">Enter the **MDM Server Name**, and then choose **Next**.</span></span> <span data-ttu-id="07a81-142">O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="07a81-142">The server name is for your reference to identify the mobile device management (MDM) server.</span></span> <span data-ttu-id="07a81-143">Não é o nome ou URL do servidor Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="07a81-143">It is not the name or URL of the Microsoft Intune server.</span></span>

   ![Captura de tela da adição de um nome do servidor MDM para DEP e, em seguida, clique em Avançar.](./media/enrollment-program-token-add-server.png)

5. <span data-ttu-id="07a81-145">A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**.</span><span class="sxs-lookup"><span data-stu-id="07a81-145">The **Add &lt;ServerName&gt;** dialog box opens, stating **Upload Your Public Key**.</span></span> <span data-ttu-id="07a81-146">Escolha **Escolher Arquivo…**</span><span class="sxs-lookup"><span data-stu-id="07a81-146">Choose **Choose File…**</span></span> <span data-ttu-id="07a81-147">para carregar o arquivo .pem e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07a81-147">to upload the .pem file, and then choose **Next**.</span></span>

   ![Captura de tela mostrando a escolha do botão Arquivo de chave pública e, em seguida, o clique em Avançar.](./media/enrollment-program-token-choose-file.png)
6.  <span data-ttu-id="07a81-149">A caixa de diálogo **Adicionar &lt;ServerName&gt;** mostra um link **Seu Token do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="07a81-149">The **Add &lt;ServerName&gt;** dialog box shows a **Your Server Token** link.</span></span> <span data-ttu-id="07a81-150">Baixe o arquivo do token (.p7m) do servidor em seu computador e escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="07a81-150">Download the server token (.p7m) file to your computer, and then choose **Done**.</span></span>
   <span data-ttu-id="07a81-151">![Captura de tela da escolha do botão de arquivo de chave pública e, em seguida, clique em Avançar.](./media/enrollment-program-token-your-token.png)</span><span class="sxs-lookup"><span data-stu-id="07a81-151">![Screenshot of choosing the public key file button and then clicking Next.](./media/enrollment-program-token-your-token.png)</span></span>
7. <span data-ttu-id="07a81-152">Acesse **Programas de Implantação** &gt; **Programa de Registro de Dispositivos** &gt; **Gerenciar Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="07a81-152">Go to  **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Manage Devices**.</span></span>
8. <span data-ttu-id="07a81-153">Em **Escolher dispositivos por**, especifique como os dispositivos são identificados:</span><span class="sxs-lookup"><span data-stu-id="07a81-153">Under **Choose Devices By**, specify how devices are identified:</span></span>
    - <span data-ttu-id="07a81-154">**Número de série**</span><span class="sxs-lookup"><span data-stu-id="07a81-154">**Serial Number**</span></span>
    - <span data-ttu-id="07a81-155">**Número do pedido**</span><span class="sxs-lookup"><span data-stu-id="07a81-155">**Order Number**</span></span>
    - <span data-ttu-id="07a81-156">**Carregar o arquivo CSV**.</span><span class="sxs-lookup"><span data-stu-id="07a81-156">**Upload CSV File**.</span></span>

   ![Captura de tela que especifica de especificação para escolher dispositivos pelo número de série, definindo a ação de escolha como Atribuir ao servidor e selecionando o nome do servidor.](./media/enrollment-program-token-specify-serial.png)

9. <span data-ttu-id="07a81-158">Para **Escolher Ação**, selecione **Atribuir ao Servidor**, selecione o &lt;Nome do Servidor&gt; especificado para o Microsoft Intune e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="07a81-158">For **Choose Action**, select **Assign to Server**, select the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.</span></span> <span data-ttu-id="07a81-159">O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.</span><span class="sxs-lookup"><span data-stu-id="07a81-159">The Apple portal assigns the specified devices to the Intune server for management and then displays **Assignment Complete**.</span></span>

   <span data-ttu-id="07a81-160">No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.</span><span class="sxs-lookup"><span data-stu-id="07a81-160">In the Apple portal, go to **Deployment Programs** &gt; **Device Enrollment Program** &gt; **View Assignment History** to see a list of devices and their MDM server assignment.</span></span>

<span data-ttu-id="07a81-161">**Etapa 3. Insira a ID da Apple usada para criar o token de programa de registro.**</span><span class="sxs-lookup"><span data-stu-id="07a81-161">**Step 3. Enter the Apple ID used to create your enrollment program token.**</span></span><br><span data-ttu-id="07a81-162">No Portal do Intune, forneça a ID da Apple para referência futura.</span><span class="sxs-lookup"><span data-stu-id="07a81-162">In the Intune portal, provide the Apple ID for future reference.</span></span> <span data-ttu-id="07a81-163">Use essa ID para renovar seu token de programa de registro para evitar a necessidade de registrar novamente todos os seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="07a81-163">Use this ID to renew your enrollment program token to avoid needing to re-enroll all your devices.</span></span>

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/enrollment-program-token-apple-id.png)

<span data-ttu-id="07a81-165">**Etapa 4. Navegue apara o token do programa de registro a ser carregado.**</span><span class="sxs-lookup"><span data-stu-id="07a81-165">**Step 4. Browse to your enrollment program token to upload.**</span></span><br>
<span data-ttu-id="07a81-166">Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="07a81-166">Go to the certificate (.pem) file, choose **Open**, and then choose **Upload**.</span></span> <span data-ttu-id="07a81-167">Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.</span><span class="sxs-lookup"><span data-stu-id="07a81-167">With the push certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.</span></span> <span data-ttu-id="07a81-168">O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.</span><span class="sxs-lookup"><span data-stu-id="07a81-168">Intune automatically synchronizes with Apple to see your enrollment program account.</span></span>

## <a name="create-an-apple-enrollment-profile"></a><span data-ttu-id="07a81-169">Criar um perfil de registro da Apple</span><span class="sxs-lookup"><span data-stu-id="07a81-169">Create an Apple enrollment profile</span></span>
=======
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Configurar o registro de dispositivo iOS com o Programa de registro de dispositivos

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico ajuda os administradores de TI a habilitar o registro de dispositivos iOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple. O Microsoft Intune pode implantar um perfil de registro “sem fio” em dispositivos iOS comprados por meio do DEP. O administrador nunca precisa tocar em nenhum dispositivo gerenciado. Um perfil de DEP contém as configurações de gerenciamento que são aplicadas aos dispositivos durante o registro, incluindo opções do Assistente de Configuração.

Para habilitar o registro de DEP, você pode usar ambos os portais do Intune e do Apple DEP. É necessário também um número de pedido de compra ou uma lista de IDs a fim de atribuí-los ao Microsoft Intune para gerenciamento no Portal da Apple.

>[!NOTE]
>O registro DEP não pode ser usado com o [gerenciador de registro de dispositivos](device-enrollment-manager-enroll.md).

**Etapas para habilitar programas de registro da Apple**
1. [Obter um token Apple DEP e atribuir dispositivos](#get-the-apple-dep-token)
2. [Criar um perfil de registro](#create-an-apple-enrollment-profile)
3. [Sincronize dispositivos gerenciados por DEP](#sync-managed-device)
4. [Atribuir o perfil DEP a dispositivos](#assign-an-enrollment-profile-to-devices)
5. [Distribuir dispositivos para usuários](#end-user-experience-with-managed-devices)

## <a name="get-the-apple-dep-token"></a>Obter o token Apple DEP

Antes de poder registrar dispositivos iOS de propriedade corporativa com o DEP (Programa de registro de dispositivos) da Apple, você precisa de um token DEP (.p7m) da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos de sua empresa que fazem parte do DEP. Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis.

> [!NOTE]
> Caso exclua o token do console clássico do Microsoft Intune antes de migrar para o Microsoft Azure, o Intune poderá restaurar um token de DEP da Apple. Você pode excluir o token de DEP novamente no portal do Azure. Você pode excluir o token de DEP novamente no portal do Azure.

**Pré-requisitos**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Inscrição no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)

**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token de DEP da Apple.**<br>
1. No Portal do Intune, escolha **Registro de dispositivo** e, em seguida, **Registro da Apple** e **Token do Programa de Registro**.

  ![Captura de tela mostrando o painel do Token do Programa de Registro, no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-add.png)

2. Selecione **Baixar sua chave pública** para baixar e salvar a chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-download.png)

**Etapa 2. Criar e baixar um token Apple DEP.**<br>
1. Selecione **Criar um token por meio do Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.

  ![Captura de tela mostrando o painel do Token do Programa de Registro, no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-create.png)

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-sign.png)
2.  No [portal de Programas de Implantação](https://deploy.apple.com) da Apple, selecione **Começar** para **Programa de registro de dispositivos**.

   ![Captura de tela do Programa de Registro clicando em Iniciar no Programa de registro de dispositivos.](./media/enrollment-program-token-started.png)

3. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.
4. Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

   ![Captura de tela da adição de um nome do servidor MDM para DEP e, em seguida, clique em Avançar.](./media/enrollment-program-token-add-server.png)

5. A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.

   ![Captura de tela mostrando a escolha do botão Arquivo de chave pública e, em seguida, o clique em Avançar.](./media/enrollment-program-token-choose-file.png)
6.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** mostra um link **Seu Token do Servidor**. Baixe o arquivo do token (.p7m) do servidor em seu computador e escolha **Concluído**.
   ![Captura de tela da escolha do botão de arquivo de chave pública e, em seguida, clique em Avançar.](./media/enrollment-program-token-your-token.png)
7. Acesse **Programas de Implantação** &gt; **Programa de Registro de Dispositivos** &gt; **Gerenciar Dispositivos**.
8. Em **Escolher dispositivos por**, especifique como os dispositivos são identificados:
    - **Número de série**
    - **Número do pedido**
    - **Carregar o arquivo CSV**.

   ![Captura de tela que especifica de especificação para escolher dispositivos pelo número de série, definindo a ação de escolha como Atribuir ao servidor e selecionando o nome do servidor.](./media/enrollment-program-token-specify-serial.png)

9. Para **Escolher Ação**, selecione **Atribuir ao Servidor**, selecione o &lt;Nome do Servidor&gt; especificado para o Microsoft Intune e, em seguida, clique em **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

**Etapa 3. Insira a ID da Apple usada para criar o token de programa de registro.**<br>No Portal do Intune, forneça a ID da Apple para referência futura. Use essa ID para renovar seu token de programa de registro para evitar a necessidade de registrar novamente todos os seus dispositivos.

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/enrollment-program-token-apple-id.png)

**Etapa 4. Navegue apara o token do programa de registro a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple

Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
2. Em **Programa de Registro para a Apple**, selecione **Perfis de Programa de Registro** e, em seguida, selecione **Criar** na folha **Perfis de Programa de Registro**.

  ![Captura de tela mostrando a escolha da opção Criar link para criar um novo perfil do Programa de Registro.](./media/enrollment-program-profile-create.png)

3. Na folha **Criar Perfil de Registro**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes.

  ![Captura de tela da especificação de nome, descrição e, em seguida, escolha de Registrar com a afinidade de usuário para um novo perfil de programa de registro.](./media/enrollment-program-profile-name.png)
Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil são registrados com ou sem a afinidade de usuário.

 - **Registrar com a afinidade do usuário** – O usuário é afiliado aos dispositivos durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. Escolha **afinidade de usuário** para dispositivos que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.

 > [!NOTE]
 > A MFA (Autenticação Multifator) não funciona durante o registro em dispositivos gerenciados por programa de registro com a afinidade de usuário. Após o registro, a MFA funciona conforme o esperado nesses dispositivos. Novos usuários que precisam alterar a senha ao se conectarem pela primeira vez não podem receber uma solicitação durante o registro em dispositivos. Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro e deverão redefinir a senha em um dispositivo diferente.

 >[!NOTE]
 >O gerenciamento de programa de registro com afinidade de usuário requer que [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints) esteja habilitado para solicitar tokens do usuário. [Saiba mais sobre o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (inclusive o Aplicativo do Portal da Empresa usado para instalar aplicativos LOB) não funcionam.

4. Escolha as **Configurações de Gerenciamento de Dispositivo** para definir as seguintes configurações de perfil:

  ![Captura de tela mostrando a escolha do Modo de Gerenciamento. O dispositivo apresenta as seguintes configurações: Supervisionado, Registro Bloqueado e Permitir Emparelhamento definido como Negar todos. O recurso Certificados do Apple Configurator está desabilitado para um novo perfil do Programa de Registro.](./media/enrollment-program-profile-mode.png)
    - **Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão. Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados.

    - **Registro bloqueado** – (Requer o Modo de Gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento. Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações. Depois de registrar o dispositivo, não é possível alterar esta configuração sem restaurar as configurações de fábrica.
>>>>>>> live

<span data-ttu-id="07a81-170">Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.</span><span class="sxs-lookup"><span data-stu-id="07a81-170">A device enrollment profile defines the settings applied to a group of devices during enrollment.</span></span>

1. <span data-ttu-id="07a81-171">No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.</span><span class="sxs-lookup"><span data-stu-id="07a81-171">In the Intune portal, choose **Device enrollment**, and then choose **Apple Enrollment**.</span></span>
2. <span data-ttu-id="07a81-172">Em **Programa de Registro para a Apple**, selecione **Perfis de Programa de Registro** e, em seguida, selecione **Criar** na folha **Perfis de Programa de Registro**.</span><span class="sxs-lookup"><span data-stu-id="07a81-172">Under **Enrollment Program for Apple**, select **Enrollment Program Profiles**, and then select **Create** on the **Enrollment Program Profiles** blade.</span></span>

<<<<<<< HEAD
  ![Captura de tela mostrando a escolha da opção Criar link para criar um novo perfil do Programa de Registro.](./media/enrollment-program-profile-create.png)

3. <span data-ttu-id="07a81-174">Na folha **Criar Perfil de Registro**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos.</span><span class="sxs-lookup"><span data-stu-id="07a81-174">On the **Create Enrollment Profile** blade, enter a **Name** and **Description** for the profile for administrative purposes.</span></span> <span data-ttu-id="07a81-175">Os usuários não veem esses detalhes.</span><span class="sxs-lookup"><span data-stu-id="07a81-175">Users do not see these details.</span></span>

  <span data-ttu-id="07a81-176">![Captura de tela da especificação de nome, descrição e, em seguida, escolha de Registrar com a afinidade de usuário para um novo perfil de programa de registro.](./media/enrollment-program-profile-name.png)</span><span class="sxs-lookup"><span data-stu-id="07a81-176">![Screenshot of specifying the name description, and then choosing Enroll with user affinity for a new enrollment program profile.](./media/enrollment-program-profile-name.png)</span></span>
<span data-ttu-id="07a81-177">Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil são registrados com ou sem a afinidade de usuário.</span><span class="sxs-lookup"><span data-stu-id="07a81-177">For **User Affinity**, choose whether devices with this profile enroll with or without user affinity.</span></span>

 - <span data-ttu-id="07a81-178">**Registrar com a afinidade do usuário** – O usuário é afiliado aos dispositivos durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa.</span><span class="sxs-lookup"><span data-stu-id="07a81-178">**Enroll with user affinity** - User are affiliated with devices during setup and can then be permitted to access company data and email.</span></span> <span data-ttu-id="07a81-179">Escolha **afinidade de usuário** para dispositivos que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07a81-179">Choose **user affinity** for devices that belong to users and that need to use the company portal for services like installing apps.</span></span>

 > [!NOTE]
 > <span data-ttu-id="07a81-180">A MFA (Autenticação Multifator) não funciona durante o registro em dispositivos gerenciados por programa de registro com a afinidade de usuário.</span><span class="sxs-lookup"><span data-stu-id="07a81-180">Multifactor authentication (MFA) doesn't work during enrollment on enrollment program-managed devices with user affinity.</span></span> <span data-ttu-id="07a81-181">Após o registro, a MFA funciona conforme o esperado nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="07a81-181">After enrollment, MFA works as expected on these devices.</span></span> <span data-ttu-id="07a81-182">Novos usuários que precisam alterar a senha ao se conectarem pela primeira vez não podem receber uma solicitação durante o registro em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="07a81-182">New users who are required to change their password when they first sign in cannot be prompted during enrollment on devices.</span></span> <span data-ttu-id="07a81-183">Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro e deverão redefinir a senha em um dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="07a81-183">Additionally, users with expired passwords aren't prompted to reset their password during enrollment and must reset the password from a different device.</span></span>

 >[!NOTE]
 ><span data-ttu-id="07a81-184">O gerenciamento de programa de registro com afinidade de usuário requer que [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints) esteja habilitado para solicitar tokens do usuário.</span><span class="sxs-lookup"><span data-stu-id="07a81-184">Enrollment program management with user affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints) to be enabled to request user token.</span></span> <span data-ttu-id="07a81-185">[Saiba mais sobre o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).</span><span class="sxs-lookup"><span data-stu-id="07a81-185">[Learn more about WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).</span></span>

 - <span data-ttu-id="07a81-186">**Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário.</span><span class="sxs-lookup"><span data-stu-id="07a81-186">**Enroll without user affinity** - The device is not affiliated with a user.</span></span> <span data-ttu-id="07a81-187">Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local.</span><span class="sxs-lookup"><span data-stu-id="07a81-187">Use this affiliation for devices that perform tasks without accessing local user data.</span></span> <span data-ttu-id="07a81-188">Aplicativos que exigem afiliação do usuário (inclusive o Aplicativo do Portal da Empresa usado para instalar aplicativos LOB) não funcionam.</span><span class="sxs-lookup"><span data-stu-id="07a81-188">Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) can’t work.</span></span>

4. <span data-ttu-id="07a81-189">Escolha as **Configurações de Gerenciamento de Dispositivo** para definir as seguintes configurações de perfil:</span><span class="sxs-lookup"><span data-stu-id="07a81-189">Select **Device Management Settings** to configure the following profile settings:</span></span>

  ![Captura de tela mostrando a escolha do Modo de Gerenciamento.](./media/enrollment-program-profile-mode.png)
    - <span data-ttu-id="07a81-193">**Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão.</span><span class="sxs-lookup"><span data-stu-id="07a81-193">**Supervised** - a management mode that enables more management options and disabled Activation Lock by default.</span></span> <span data-ttu-id="07a81-194">Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados.</span><span class="sxs-lookup"><span data-stu-id="07a81-194">If you leave the check box blank, you have limited management capabilities.</span></span>

    - <span data-ttu-id="07a81-195">**Registro bloqueado** – (Requer o Modo de Gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="07a81-195">**Locked enrollment** - (Requires Management Mode = Supervised) Disables iOS settings that could allow removal of the management profile.</span></span> <span data-ttu-id="07a81-196">Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações.</span><span class="sxs-lookup"><span data-stu-id="07a81-196">If you leave the check box blank, it allows the management profile to be removed from the Settings menu.</span></span> <span data-ttu-id="07a81-197">Depois de registrar o dispositivo, não é possível alterar esta configuração sem restaurar as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="07a81-197">After device enrollment, you cannot change this setting without factory resetting the device.</span></span>

    - <span data-ttu-id="07a81-198">**Permitir Emparelhamento** – Especifica se os dispositivos iOS podem sincronizar com computadores.</span><span class="sxs-lookup"><span data-stu-id="07a81-198">**Allow Pairing** - Specifies whether iOS devices can sync with computers.</span></span> <span data-ttu-id="07a81-199">Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.</span><span class="sxs-lookup"><span data-stu-id="07a81-199">If you choose **Allow Apple Configurator by certificate**, you must choose a certificate under **Apple Configurator Certificates**.</span></span>

    - <span data-ttu-id="07a81-200">**Certificados do Apple Configurator** – Se que você escolheu **Permitir Apple Configurator por certificado** em **Permitir Emparelhamento**, selecione um Certificado do Apple Configurator para ser importado.</span><span class="sxs-lookup"><span data-stu-id="07a81-200">**Apple Configurator Certificates** - If you chose **Allow Apple Configurator by certificate** under **Allow Pairing**, select an Apple Configurator Certificate to import.</span></span>

  <span data-ttu-id="07a81-201">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="07a81-201">Choose **Save**.</span></span>

5. <span data-ttu-id="07a81-202">Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil:</span><span class="sxs-lookup"><span data-stu-id="07a81-202">Select **Setup Assistant Settings** to configure the following profile settings:</span></span>

  ![Captura de tela mostrando a escolha das definições de configuração com as configurações disponíveis para um novo perfil do Programa de Registro.](./media/enrollment-program-profile-settings.png)
    - <span data-ttu-id="07a81-204">**Nome do Departamento** – Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação.</span><span class="sxs-lookup"><span data-stu-id="07a81-204">**Department Name** - Appears when users tap **About Configuration** during activation.</span></span>

    - <span data-ttu-id="07a81-205">**Telefone do Departamento** – Exibido quando o usuário clica no botão **Precisa de ajuda** durante a ativação.</span><span class="sxs-lookup"><span data-stu-id="07a81-205">**Department Phone** - Appears when the user clicks the **Need Help** button during activation.</span></span>
    - <span data-ttu-id="07a81-206">**Opções do Assistente de Instalação** – Essas configurações opcionais podem ser configuradas no menu **Configurações** do iOS.</span><span class="sxs-lookup"><span data-stu-id="07a81-206">**Setup Assistant Options** - These optional settings can be set up later in the iOS **Settings** menu.</span></span>
        - <span data-ttu-id="07a81-207">**Senha** - Solicitar senha durante a ativação.</span><span class="sxs-lookup"><span data-stu-id="07a81-207">**Passcode** - Prompt for passcode during activation.</span></span> <span data-ttu-id="07a81-208">Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira.</span><span class="sxs-lookup"><span data-stu-id="07a81-208">Always require a passcode unless the device is secured or has access controlled in some other manner.</span></span> <span data-ttu-id="07a81-209">Por exemplo, o modo de quiosque restringe o dispositivo a um único aplicativo.</span><span class="sxs-lookup"><span data-stu-id="07a81-209">For example, kiosk mode restricts the device to one app.</span></span>
        - <span data-ttu-id="07a81-210">**Serviços de Localização** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-210">**Location Services** - If enabled, Setup Assistant prompts for the service during activation</span></span>
        - <span data-ttu-id="07a81-211">**Restaurar** - Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-211">**Restore** - If enabled, Setup Assistant prompts for iCloud backup during activation</span></span>
        - <span data-ttu-id="07a81-212">**ID da Apple** – se estiver habilitado, o iOS solicitará aos usuários uma ID da Apple quando o Intune tentar instalar um aplicativo sem uma ID.</span><span class="sxs-lookup"><span data-stu-id="07a81-212">**Apple ID** - If enabled, iOS prompts users for an Apple ID when Intune attempts to install an app without an ID.</span></span> <span data-ttu-id="07a81-213">Uma ID da Apple é necessária para baixar aplicativos na App Store iOS, incluindo aqueles instalados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="07a81-213">An Apple ID is required to download iOS App Store apps, including those apps installed by Intune.</span></span>
        - <span data-ttu-id="07a81-214">**Termos e Condições** - Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-214">**Terms and Conditions** - If enabled, Setup Assistant prompts users to accept Apple's terms and conditions during activation</span></span>
        - <span data-ttu-id="07a81-215">**ID de Toque** – Se habilitada, o Assistente de Configuração solicitará o serviço durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-215">**Touch ID** - If enabled, Setup Assistant prompts for this service during activation</span></span>
        - <span data-ttu-id="07a81-216">**Apple Pay** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-216">**Apple Pay** - If enabled, Setup Assistant prompts for this service during activation</span></span>
        - <span data-ttu-id="07a81-217">**Zoom** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-217">**Zoom** - If enabled, Setup Assistant prompts for this service during activation</span></span>
        - <span data-ttu-id="07a81-218">**Siri** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-218">**Siri** - If enabled, Setup Assistant prompts for this service during activation</span></span>
        - <span data-ttu-id="07a81-219">**Dados de Diagnóstico** – Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação</span><span class="sxs-lookup"><span data-stu-id="07a81-219">**Diagnostic Data** - If enabled, Setup Assistant prompts for this service during activation</span></span>

    <span data-ttu-id="07a81-220">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="07a81-220">Choose **Save**.</span></span>
9. <span data-ttu-id="07a81-221">Para salvar as configurações de perfil, selecione **Criar** na folha **Criar Perfil de Registro**.</span><span class="sxs-lookup"><span data-stu-id="07a81-221">To save the profile settings, select **Create** on the **Create Enrollment Profile** blade.</span></span> <span data-ttu-id="07a81-222">O perfil de registro aparece na lista de Perfis de Registro do Programa de Registro da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-222">The enrollment profile appears in the Apple Enrollment Program Enrollment Profiles list.</span></span>

## <a name="sync-managed-devices"></a><span data-ttu-id="07a81-223">Sincronizar dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="07a81-223">Sync managed devices</span></span>
<span data-ttu-id="07a81-224">Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com o Apple para ver os dispositivos gerenciados no Portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="07a81-224">Now that Intune has permission to manage your devices, you can synchronize Intune with Apple to see your managed devices in the Intune portal.</span></span>

1. <span data-ttu-id="07a81-225">No Portal do Intune, escolha **Registro de Dispositivo** &gt; **Registro da Apple** &gt; **Dispositivos do Programa de Registro**.</span><span class="sxs-lookup"><span data-stu-id="07a81-225">In the Intune portal, choose **Device enrollment** &gt;  **Apple Enrollment** &gt; **Enrollment Program Devices**.</span></span>
2. <span data-ttu-id="07a81-226">Em **Dispositivos do Programa de Registro**, selecione **Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="07a81-226">Under **Enrollment Program Devices**, select **Sync**.</span></span> <span data-ttu-id="07a81-227">A folha **Sincronização** é exibida.</span><span class="sxs-lookup"><span data-stu-id="07a81-227">The **Sync** blade appears.</span></span>

  ![Captura de tela mostrando o nó Dispositivos do Programa de Registro selecionado e o Link de Sincronização escolhido.](./media/enrollment-program-device-sync.png)
3. <span data-ttu-id="07a81-229">Na folha **Sincronizar**, selecione **Solicitar Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="07a81-229">On the **Sync** blade, select **Request Sync**.</span></span> <span data-ttu-id="07a81-230">A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.</span><span class="sxs-lookup"><span data-stu-id="07a81-230">The progress bar shows the amount of time you must wait before requesting Sync again.</span></span>

  ![Captura de tela mostrando a folha Sincronização com o link Solicitar sincronização escolhido.](./media/enrollment-program-device-request-sync.png)

  <span data-ttu-id="07a81-232">Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="07a81-232">To comply with Apple’s terms for acceptable enrollment program traffic, Intune imposes the following restrictions:</span></span>
     -  <span data-ttu-id="07a81-233">Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias.</span><span class="sxs-lookup"><span data-stu-id="07a81-233">A full sync can run no more than once every seven days.</span></span> <span data-ttu-id="07a81-234">Durante uma sincronização completa, o Microsoft Intune atualiza todos os números de série da Apple atribuídos à nossa plataforma.</span><span class="sxs-lookup"><span data-stu-id="07a81-234">During a full sync, Intune refreshes every Apple serial number assigned to Intune.</span></span> <span data-ttu-id="07a81-235">Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.</span><span class="sxs-lookup"><span data-stu-id="07a81-235">If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.</span></span>
     -  <span data-ttu-id="07a81-236">Qualquer solicitação de sincronização tem 15 minutos para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="07a81-236">Any sync request is given 15 minutes to finish.</span></span> <span data-ttu-id="07a81-237">Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.</span><span class="sxs-lookup"><span data-stu-id="07a81-237">During this time or until the request succeeds, the **Sync** button is disabled.</span></span>
     - <span data-ttu-id="07a81-238">O Intune sincroniza dispositivos novos e removidos com a Apple a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="07a81-238">Intune syncs new and removed devices with Apple every 24 hours.</span></span>
     
4. <span data-ttu-id="07a81-239">No espaço de trabalho dos Dispositivos do Programa de Registro, escolha **Atualizar** para ver seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="07a81-239">In the Enrollment Program Devices workspace, choose **Refresh** to see your devices.</span></span>

## <a name="assign-an-enrollment-profile-to-devices"></a><span data-ttu-id="07a81-240">Atribuir um perfil de registro aos dispositivos</span><span class="sxs-lookup"><span data-stu-id="07a81-240">Assign an enrollment profile to devices</span></span>
<span data-ttu-id="07a81-241">Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.</span><span class="sxs-lookup"><span data-stu-id="07a81-241">You must assign an enrollment program profile to devices before they can enroll.</span></span>

>[!NOTE]
><span data-ttu-id="07a81-242">Você também pode atribuir números de série aos perfis na folha **Números de Série da Apple**.</span><span class="sxs-lookup"><span data-stu-id="07a81-242">You can also assign serial numbers to profiles from the **Apple Serial Numbers** blade.</span></span>

1. <span data-ttu-id="07a81-243">No portal do Intune, escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, selecione **Perfis do Programa de Registro**.</span><span class="sxs-lookup"><span data-stu-id="07a81-243">In the Intune portal, choose **Device enrollment** > **Apple Enrollment**, and then select **Enrollment Program Profiles**.</span></span>
2. <span data-ttu-id="07a81-244">Na lista de **Perfis do Programa de Registro**, selecione o perfil que você deseja atribuir aos dispositivos e, em seguida, selecione **Atribuir dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="07a81-244">From the list of **Enrollment Program Profiles**, select the profile you want to assign to devices and then select **Assign devices**.</span></span>

 ![Captura de tela mostrando a folha Sincronização com o link Solicitar sincronização escolhido.](./media/enrollment-program-device-assign.png)

3. <span data-ttu-id="07a81-246">Selecione **Atribuir** e, em seguida, selecione os dispositivos que você deseja atribuir a esse perfil.</span><span class="sxs-lookup"><span data-stu-id="07a81-246">Select **Assign** and then select the devices you want to assign this profile.</span></span> <span data-ttu-id="07a81-247">Filtre para exibir os dispositivos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="07a81-247">You can filter to view available devices:</span></span>
  - <span data-ttu-id="07a81-248">**não atribuído**</span><span class="sxs-lookup"><span data-stu-id="07a81-248">**unassigned**</span></span>
  - <span data-ttu-id="07a81-249">**qualquer**</span><span class="sxs-lookup"><span data-stu-id="07a81-249">**any**</span></span>
  - <span data-ttu-id="07a81-250">**&lt;nome do perfil&gt;**</span><span class="sxs-lookup"><span data-stu-id="07a81-250">**&lt;profile name&gt;**</span></span>
4. <span data-ttu-id="07a81-251">Selecionar os dispositivos que deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="07a81-251">Select the devices you want to assign.</span></span> <span data-ttu-id="07a81-252">A caixa de seleção acima da coluna seleciona até mil dispositivos relacionados; em seguida, clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="07a81-252">The checkbox above the column selects up to 1000 listed devices, and then click **Assign**.</span></span> <span data-ttu-id="07a81-253">Para registrar mais de 1000 dispositivos, repita as etapas de atribuição até que todos os dispositivos sejam atribuídos a um perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="07a81-253">To enroll more than 1000 devices, repeat the assignment steps until all devices are assigned an enrollment profile.</span></span>

  ![Captura de tela do botão Atribuir para atribuir o perfil do programa de registro no Portal do Intune](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a><span data-ttu-id="07a81-255">Experiência do usuário final com dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="07a81-255">End-user experience with managed devices</span></span>

<span data-ttu-id="07a81-256">Agora você pode distribuir dispositivos para os usuários.</span><span class="sxs-lookup"><span data-stu-id="07a81-256">You can now distribute devices to users.</span></span> <span data-ttu-id="07a81-257">Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune.</span><span class="sxs-lookup"><span data-stu-id="07a81-257">Devices with user affinity require each user be assigned an Intune license.</span></span> <span data-ttu-id="07a81-258">Um dispositivo ativado só pode ser aplicado a um perfil de registro após restaurar as respectivas configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="07a81-258">An activated device cannot apply an enrollment profile until the device is factory reset.</span></span> <span data-ttu-id="07a81-259">Quando o dispositivo iOS gerenciado pelo Programa de Registro é ativado, o dispositivo do usuário exibe as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="07a81-259">When the enrollment program-managed iOS device is turned on, the user sees the following options on their device:</span></span>  

1. <span data-ttu-id="07a81-260">**Configurar dispositivo iOS** – Você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="07a81-260">**Set Up iOS device** - Users can choose from the following options:</span></span>
  - <span data-ttu-id="07a81-261">**Configurar como novo dispositivo**</span><span class="sxs-lookup"><span data-stu-id="07a81-261">**Set Up as New device**</span></span>
  - <span data-ttu-id="07a81-262">**Restaurar do Backup do iCloud**</span><span class="sxs-lookup"><span data-stu-id="07a81-262">**Restore from iCloud Backup**</span></span>
  - <span data-ttu-id="07a81-263">**Restaurar do Backup do iTunes**</span><span class="sxs-lookup"><span data-stu-id="07a81-263">**Restore from iTunes Backup**</span></span>
2. <span data-ttu-id="07a81-264">Os usuários serão informados de que a **&lt;organização&gt; configurará o dispositivo automaticamente.**</span><span class="sxs-lookup"><span data-stu-id="07a81-264">Users are informed **&lt;Your Organization&gt; will automatically configure your device.**</span></span> <span data-ttu-id="07a81-265">Os detalhes de configuração adicionais a seguir também estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="07a81-265">The following additional configuration details are also available:</span></span>

  <span data-ttu-id="07a81-266">**A configuração permite à &gt;organização** gerenciar este dispositivo por conexão sem fio.&lt;</span><span class="sxs-lookup"><span data-stu-id="07a81-266">**Configuration allows &lt;Your Organization&gt; to manage this device over the air.**</span></span>

  <span data-ttu-id="07a81-267">**Um administrador pode ajudar você a configurar as contas de email e rede, instalar e configurar aplicativos e gerenciar as configurações remotamente.**</span><span class="sxs-lookup"><span data-stu-id="07a81-267">**An administrator can help you set up email and network accounts, install and configure apps, and manage settings remotely.**</span></span>

  <span data-ttu-id="07a81-268">**Um administrador pode desabilitar recursos, instalar e remover aplicativos, monitorar e restringir o tráfego de Internet e apagar remotamente esse dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="07a81-268">**An administrator may disable features, install and remove apps, monitor and restrict your Internet traffic and remotely erase this device.**</span></span>

  <span data-ttu-id="07a81-269">**A configuração é fornecida por:<br> &lt;sua organização&gt; equipe do iOS<br> &lt;endereço&gt;**</span><span class="sxs-lookup"><span data-stu-id="07a81-269">**Configuration is provided by:<br> &lt;Your organization&gt; iOS Team<br> &lt;Address&gt;**</span></span>

3. <span data-ttu-id="07a81-270">O nome de usuário e senha corporativo ou de estudante são solicitados dos usuários.</span><span class="sxs-lookup"><span data-stu-id="07a81-270">Users are prompted for their work or school username and password.</span></span>
4. <span data-ttu-id="07a81-271">A ID da Apple é solicitada dos usuários.</span><span class="sxs-lookup"><span data-stu-id="07a81-271">Users are prompted for their Apple ID.</span></span> <span data-ttu-id="07a81-272">Uma ID da Apple é necessária para instalar o aplicativo de Portal da Empresa do Intune e outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07a81-272">An Apple ID is required to install the Intune Company Portal app and other apps.</span></span> <span data-ttu-id="07a81-273">Depois que as credenciais são fornecidas, o dispositivo instala um perfil de gerenciamento que não pode ser removido.</span><span class="sxs-lookup"><span data-stu-id="07a81-273">After credentials are provided, the device installs a management profile that cannot be removed.</span></span> <span data-ttu-id="07a81-274">O perfil de gerenciamento do Intune é exibido em **Configurações** > **Geral** > **Gerenciamento de Dispositivo** no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07a81-274">The Intune management profile is displayed in **Settings** > **General** > **Device Management** on the device.</span></span>

<span data-ttu-id="07a81-275">Os usuários agora podem concluir a configuração seus dispositivos da empresa usando o Portal da Empresa do Intune ou o Assistente de Instalação da Apple.</span><span class="sxs-lookup"><span data-stu-id="07a81-275">Users can now finish setting up their company-owned device using either the Intune Company portal or Apple Setup Assistant.</span></span>
=======
  Escolha **Salvar**.

5. Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil:

  ![Captura de tela mostrando a escolha das definições de configuração com as configurações disponíveis para um novo perfil do Programa de Registro.](./media/enrollment-program-profile-settings.png)
    - **Nome do Departamento** – Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação.

    - **Telefone do Departamento** – Exibido quando o usuário clica no botão **Precisa de ajuda** durante a ativação.
    - **Opções do Assistente de Instalação** – Essas configurações opcionais podem ser configuradas no menu **Configurações** do iOS.
        - **Senha** - Solicitar senha durante a ativação. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira. Por exemplo, o modo de quiosque restringe o dispositivo a um único aplicativo.
        - **Serviços de Localização** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Restaurar** - Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação
        - **ID da Apple** – se estiver habilitado, o iOS solicitará aos usuários uma ID da Apple quando o Intune tentar instalar um aplicativo sem uma ID. Uma ID da Apple é necessária para baixar aplicativos na App Store iOS, incluindo aqueles instalados pelo Intune.
        - **Termos e Condições** - Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação
        - **ID de Toque** – Se habilitada, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Apple Pay** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Zoom** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Siri** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Dados de Diagnóstico** – Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação

    Selecione **Salvar**.
9. Para salvar as configurações de perfil, selecione **Criar** na folha **Criar Perfil de Registro**. O perfil de registro aparece na lista de Perfis de Registro do Programa de Registro da Apple.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com o Apple para ver os dispositivos gerenciados no Portal do Intune.

1. No Portal do Intune, escolha **Registro de Dispositivo** &gt; **Registro da Apple** &gt; **Dispositivos do Programa de Registro**.
2. Em **Dispositivos do Programa de Registro**, selecione **Sincronização**. A folha **Sincronização** é exibida.

  ![Captura de tela mostrando o nó Dispositivos do Programa de Registro selecionado e o Link de Sincronização escolhido.](./media/enrollment-program-device-sync.png)
3. Na folha **Sincronizar**, selecione **Solicitar Sincronização**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.

  ![Captura de tela mostrando a folha Sincronização com o link Solicitar sincronização escolhido.](./media/enrollment-program-device-request-sync.png)

  Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
     -  Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Microsoft Intune atualiza todos os números de série da Apple atribuídos à nossa plataforma. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -  Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.
     - O Intune sincroniza dispositivos novos e removidos com a Apple a cada 24 horas.
     
4. No espaço de trabalho dos Dispositivos do Programa de Registro, escolha **Atualizar** para ver seus dispositivos.

## <a name="assign-an-enrollment-profile-to-devices"></a>Atribuir um perfil de registro aos dispositivos
Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.

>[!NOTE]
>Você também pode atribuir números de série aos perfis na folha **Números de Série da Apple**.

1. No portal do Intune, escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, selecione **Perfis do Programa de Registro**.
2. Na lista de **Perfis do Programa de Registro**, selecione o perfil que você deseja atribuir aos dispositivos e, em seguida, selecione **Atribuir dispositivos**.

 ![Captura de tela mostrando a folha Sincronização com o link Solicitar sincronização escolhido.](./media/enrollment-program-device-assign.png)

3. Selecione **Atribuir** e, em seguida, selecione os dispositivos que você deseja atribuir a esse perfil. Filtre para exibir os dispositivos disponíveis:
  - **não atribuído**
  - **qualquer**
  - **&lt;nome do perfil&gt;**
4. Selecionar os dispositivos que deseja atribuir. A caixa de seleção acima da coluna seleciona até mil dispositivos relacionados; em seguida, clique em **Atribuir**. Para registrar mais de 1000 dispositivos, repita as etapas de atribuição até que todos os dispositivos sejam atribuídos a um perfil de registro.

  ![Captura de tela do botão Atribuir para atribuir o perfil do programa de registro no Portal do Intune](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Experiência do usuário final com dispositivos gerenciados

Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Um dispositivo ativado só pode ser aplicado a um perfil de registro após restaurar as respectivas configurações de fábrica. Quando o dispositivo iOS gerenciado pelo Programa de Registro é ativado, o dispositivo do usuário exibe as seguintes opções:  

1. **Configurar dispositivo iOS** – Você pode escolher entre as seguintes opções:
  - **Configurar como novo dispositivo**
  - **Restaurar do Backup do iCloud**
  - **Restaurar do Backup do iTunes**
2. Os usuários serão informados de que a **&lt;organização&gt; configurará o dispositivo automaticamente.** Os detalhes de configuração adicionais a seguir também estão disponíveis:

  **A configuração permite à &gt;organização** gerenciar este dispositivo por conexão sem fio.&lt;

  **Um administrador pode ajudar você a configurar as contas de email e rede, instalar e configurar aplicativos e gerenciar as configurações remotamente.**

  **Um administrador pode desabilitar recursos, instalar e remover aplicativos, monitorar e restringir o tráfego de Internet e apagar remotamente esse dispositivo.**

  **A configuração é fornecida por:<br> &lt;sua organização&gt; equipe do iOS<br> &lt;endereço&gt;**

3. O nome de usuário e senha corporativo ou de estudante são solicitados dos usuários.
4. A ID da Apple é solicitada dos usuários. Uma ID da Apple é necessária para instalar o aplicativo de Portal da Empresa do Intune e outros aplicativos. Depois que as credenciais são fornecidas, o dispositivo instala um perfil de gerenciamento que não pode ser removido. O perfil de gerenciamento do Intune é exibido em **Configurações** > **Geral** > **Gerenciamento de Dispositivo** no dispositivo.

Os usuários agora podem concluir a configuração seus dispositivos da empresa usando o Portal da Empresa do Intune ou o Assistente de Instalação da Apple.
>>>>>>> live
