---
title: Instalar o software cliente do computador
description: "Use este guia para ajudá-lo a ter os computadores Windows gerenciados pelo software cliente do Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
ms.date: 03/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 356ada64224f8982baf93ddaccb44df123c4568c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="fa239-103">Instalar o cliente de software Intune em computadores Windows</span><span class="sxs-lookup"><span data-stu-id="fa239-103">Install the Intune software client on Windows PCs</span></span>
<a id="install-the-intune-software-client-on-windows-pcs" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="fa239-104">Computadores Windows podem ser registrados instalando o software cliente do Intune.</span><span class="sxs-lookup"><span data-stu-id="fa239-104">Windows PCs can be enrolled by installing the Intune client software.</span></span> <span data-ttu-id="fa239-105">É possível instalar o software cliente do Intune usando os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="fa239-105">The Intune client software can be installed by using the following methods:</span></span>

- <span data-ttu-id="fa239-106">Pelo administrador de TI, usando um destes métodos: instalação manual, política de grupo ou instalação incluída em uma imagem de disco</span><span class="sxs-lookup"><span data-stu-id="fa239-106">By the IT admin, using one of these methods: manual installation, Group Policy, or installation included in a disk image</span></span>

- <span data-ttu-id="fa239-107">Por usuários finais, instalando o software cliente manualmente</span><span class="sxs-lookup"><span data-stu-id="fa239-107">By end users, who manually install the client software</span></span>

<span data-ttu-id="fa239-108">O software cliente do Intune conta com o software mínimo necessário para registrar o PC no gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="fa239-108">The Intune client software contains the minimum software necessary to enroll the PC in Intune management.</span></span> <span data-ttu-id="fa239-109">Depois de registrar um PC, o software cliente do Intune baixa o software cliente completo que é necessário para o gerenciamento do PC.</span><span class="sxs-lookup"><span data-stu-id="fa239-109">After a PC has been enrolled, the Intune client software then downloads the full client software required for PC management.</span></span>

<span data-ttu-id="fa239-110">Esta série de downloads reduz o impacto sobre a largura de banda da rede e diminui o tempo necessário para registrar inicialmente o computador no Intune.</span><span class="sxs-lookup"><span data-stu-id="fa239-110">This series of downloads reduces the impact on the network's bandwidth and minimizes the time required to initially enroll the PC in Intune.</span></span> <span data-ttu-id="fa239-111">Ela também garante que o cliente tenha o software mais recente disponível após a conclusão do download do segundo.</span><span class="sxs-lookup"><span data-stu-id="fa239-111">It also ensures that the client has the most recent software available after the second download has finished.</span></span>

## <span data-ttu-id="fa239-112">Baixe o software cliente do Intune</span><span class="sxs-lookup"><span data-stu-id="fa239-112">Download the Intune client software</span></span>
<a id="download-the-intune-client-software" class="xliff"></a>

<span data-ttu-id="fa239-113">Todos os métodos, exceto quando os próprios usuários instalam o software cliente do Intune, exigem que os administradores de TI baixem primeiro o software a fim de implantá-lo posteriormente para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="fa239-113">All methods, except those in which users install the Intune client software themselves, require that IT admins download the software first so that it can be subsequently deployed to end users.</span></span>

1.  <span data-ttu-id="fa239-114">No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Administração** &gt; **Download de Software Cliente**.</span><span class="sxs-lookup"><span data-stu-id="fa239-114">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Client Software Download**.</span></span>

  ![Baixe o Intune no computador cliente](../media/pc-sa-client-download.png)

2.  <span data-ttu-id="fa239-116">Na página **Download de Software Cliente**, clique em **Baixar Software Cliente**.</span><span class="sxs-lookup"><span data-stu-id="fa239-116">On the **Client Software Download** page, click **Download Client Software**.</span></span> <span data-ttu-id="fa239-117">Em seguida, salve o pacote **Microsoft_Intune_Setup.zip** que contém o software em um local seguro na sua rede.</span><span class="sxs-lookup"><span data-stu-id="fa239-117">Then save the **Microsoft_Intune_Setup.zip** package that contains the software to a secure location on your network.</span></span>

<span data-ttu-id="fa239-118">O pacote de instalação do software cliente do Intune contém informações exclusivas e específicas sobre sua conta, que estão disponíveis por meio de um certificado inserido.</span><span class="sxs-lookup"><span data-stu-id="fa239-118">The Intune client software installation package contains unique and specific information, which is available through an embedded certificate, about your account.</span></span> <span data-ttu-id="fa239-119">Se usuários não autorizados obtiverem acesso ao pacote de instalação, eles poderão registrar computadores na conta representada por seu certificado integrado e poderão obter acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="fa239-119">If unauthorized users gain access to the installation package, they can enroll PCs to the account that is represented by its embedded certificate and might gain access to company resources.</span></span>

3.  <span data-ttu-id="fa239-120">Extraia o conteúdo do pacote de instalação para o local seguro na sua rede.</span><span class="sxs-lookup"><span data-stu-id="fa239-120">Extract the contents of the installation package to the secure location on your network.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa239-121">Não renomeie ou remova o arquivo **ACCOUNTCERT** extraído. Caso contrário, ocorrerá uma falha na instalação do software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-121">Do not rename or remove the **ACCOUNTCERT** file that is extracted, or the client software installation will fail.</span></span>

## <span data-ttu-id="fa239-122">Implante manualmente o software cliente</span><span class="sxs-lookup"><span data-stu-id="fa239-122">Deploy the client software manually</span></span>
<a id="deploy-the-client-software-manually" class="xliff"></a>

<span data-ttu-id="fa239-123">Nos computadores em que o software cliente será instalado, vá para a pasta na qual os arquivos de instalação do software cliente foram colocados.</span><span class="sxs-lookup"><span data-stu-id="fa239-123">On the computer(s) on which the client software is going to be installed, go to the folder where the client software installation files are located.</span></span> <span data-ttu-id="fa239-124">Em seguida, execute **Microsoft_Intune_Setup.exe** para instalar o software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-124">Then run **Microsoft_Intune_Setup.exe** to install the client software.</span></span>

> [!NOTE]
> <span data-ttu-id="fa239-125">O status da instalação será exibido ao passar o mouse sobre o ícone na barra de tarefas no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-125">The status of the installation is displayed when you hover over the icon in the taskbar on the client PC.</span></span>

## <span data-ttu-id="fa239-126">Implante o software cliente usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="fa239-126">Deploy the client software by using Group Policy</span></span>
<a id="deploy-the-client-software-by-using-group-policy" class="xliff"></a>

1.  <span data-ttu-id="fa239-127">Na pasta que contém os arquivos **Microsoft_Intune_Setup.exe** e **MicrosoftIntune.accountcert**, execute o seguinte comando para extrair os programas de instalação baseados no Windows Installer para computadores de 32 e 64 bits:</span><span class="sxs-lookup"><span data-stu-id="fa239-127">In the folder that contains the files **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, run the following command to extract the Windows Installer-based installation programs for 32-bit and 64-bit computers:</span></span>

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  <span data-ttu-id="fa239-128">Copie os arquivos **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** e **MicrosoftIntune.accountcert** para uma localização da rede que possa ser acessada por todos os computadores nos quais o software cliente será instalado.</span><span class="sxs-lookup"><span data-stu-id="fa239-128">Copy the **Microsoft_Intune_x86.msi** file, the **Microsoft_Intune_x64.msi** file, and the **MicrosoftIntune.accountcert** file to a network location that can be accessed by all computers on which the client software is going to be installed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa239-129">Não separe ou renomeie os arquivos ou ocorrerá uma falha na instalação do software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-129">Do not separate or rename the files or the client software installation will fail.</span></span>

3.  <span data-ttu-id="fa239-130">Use a Política de grupo para implantar o software nos computadores da sua rede.</span><span class="sxs-lookup"><span data-stu-id="fa239-130">Use Group Policy to deploy the software to computers on your network.</span></span>

    <span data-ttu-id="fa239-131">Para obter mais informações sobre como usar a Política de Grupo para implantar software automaticamente, consulte [Política de Grupo para Iniciantes](https://technet.microsoft.com/library/hh147307.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa239-131">For more information about how to use Group Policy to automatically deploy software, see [Group Policy for Beginners](https://technet.microsoft.com/library/hh147307.aspx).</span></span>

## <span data-ttu-id="fa239-132">Implante o software cliente como parte de uma imagem</span><span class="sxs-lookup"><span data-stu-id="fa239-132">Deploy the client software as part of an image</span></span>
<a id="deploy-the-client-software-as-part-of-an-image" class="xliff"></a>
<span data-ttu-id="fa239-133">É possível implantar o software cliente do Intune em computadores como parte de uma imagem do sistema operacional, usando o seguinte procedimento como guia:</span><span class="sxs-lookup"><span data-stu-id="fa239-133">You can deploy the Intune client software to computers as part of an operating system image by using the following procedure as a guide:</span></span>

1.  <span data-ttu-id="fa239-134">Copie os arquivos de instalação do cliente **Microsoft_Intune_Setup.exe** e **MicrosoftIntune.accountcert** na pasta **%Systemdrive%\Temp\Microsoft_Intune_Setup** no computador de referência.</span><span class="sxs-lookup"><span data-stu-id="fa239-134">Copy the client installation files, **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, to the **%Systemdrive%\Temp\Microsoft_Intune_Setup** folder on the reference computer.</span></span>

2.  <span data-ttu-id="fa239-135">Crie a entrada de registro **WindowsIntuneEnrollPending** , adicionando o seguinte comando ao script **SetupComplete.cmd** :</span><span class="sxs-lookup"><span data-stu-id="fa239-135">Create the **WindowsIntuneEnrollPending** registry entry by adding the following command to the **SetupComplete.cmd** script:</span></span>

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  <span data-ttu-id="fa239-136">Adicione o seguinte comando a **setupcomplete.cmd** para executar o pacote de registro com o argumento de linha de comando /PrepareEnroll:</span><span class="sxs-lookup"><span data-stu-id="fa239-136">Add the following command to **setupcomplete.cmd** to run the enrollment package with the /PrepareEnroll command-line argument:</span></span>

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > <span data-ttu-id="fa239-137">O script **SetupComplete.cmd** permite que a Instalação do Windows efetue modificações no sistema antes que um usuário faça logon.</span><span class="sxs-lookup"><span data-stu-id="fa239-137">The **SetupComplete.cmd** script enables Windows Setup to make modifications to the system before a user signs on.</span></span> <span data-ttu-id="fa239-138">O argumento de linha de comando **/PrepareEnroll** prepara um computador definido como destino de forma que ele seja automaticamente registrado no Intune após a conclusão da Instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="fa239-138">The **/PrepareEnroll** command-line argument prepares a targeted computer to be automatically enrolled in Intune after Windows Setup finishes.</span></span>

4.  <span data-ttu-id="fa239-139">Coloque o **SetupComplete.cmd** na pasta **%Windir%\Setup\Scripts** do computador de referência.</span><span class="sxs-lookup"><span data-stu-id="fa239-139">Put **SetupComplete.cmd** in the **%Windir%\Setup\Scripts** folder on the reference computer.</span></span>

5.  <span data-ttu-id="fa239-140">Capture uma imagem do computador de referência e implante-a nos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="fa239-140">Capture an image of the reference computer and then deploy this to targeted computers.</span></span>

    <span data-ttu-id="fa239-141">Quando o computador definido como destino for reiniciado após a conclusão da instalação do Windows, a chave do Registro **WindowsIntuneEnrollPending** será criada.</span><span class="sxs-lookup"><span data-stu-id="fa239-141">When the targeted computer restarts at the completion of Windows Setup, the **WindowsIntuneEnrollPending** registry key is created.</span></span> <span data-ttu-id="fa239-142">O pacote de registro verifica se o computador está registrado.</span><span class="sxs-lookup"><span data-stu-id="fa239-142">The enrollment package checks to see if the computer is enrolled.</span></span> <span data-ttu-id="fa239-143">Se o computador estiver inscrito, nenhuma outra ação adicional será executada.</span><span class="sxs-lookup"><span data-stu-id="fa239-143">If the computer is enrolled, no further action is taken.</span></span> <span data-ttu-id="fa239-144">Se o computador não estiver registrado, o pacote de registro criará uma Tarefa de registro automática do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fa239-144">If the computer is not enrolled, the enrollment package creates a Microsoft Intune Automatic Enrollment Task.</span></span>

    <span data-ttu-id="fa239-145">Quando a tarefa de Registro automático do Intune for executada no próximo horário agendado, ela verificará a existência do valor do registro **WindowsIntuneEnrollPending** e tentará registrar o computador definido como destino no Intune.</span><span class="sxs-lookup"><span data-stu-id="fa239-145">When the automatic enrollment task runs at the next scheduled time, it checks the existence of the **WindowsIntuneEnrollPending** registry value, and it tries to enroll the targeted PC in Intune.</span></span> <span data-ttu-id="fa239-146">Se a inscrição falhar por algum motivo, haverá uma nova tentativa na próxima vez que a tarefa for executada.</span><span class="sxs-lookup"><span data-stu-id="fa239-146">If the enrollment fails for any reason, the enrollment is retried the next time the task runs.</span></span> <span data-ttu-id="fa239-147">As tentativas continuam por um mês.</span><span class="sxs-lookup"><span data-stu-id="fa239-147">The retries continue for a month.</span></span>

    <span data-ttu-id="fa239-148">A tarefa de registro automático do Intune, o valor do Registro **WindowsIntuneEnrollPending** e o certificado da conta serão excluídos do computador definido como destino quando o registro for concluído com êxito ou depois de um mês (o que ocorrer primeiro).</span><span class="sxs-lookup"><span data-stu-id="fa239-148">The Intune Automatic Enrollment Task, the **WindowsIntuneEnrollPending** registry value, and the account certificate are deleted from the targeted computer either when the enrollment is successful or after a month (whichever comes first).</span></span>

## <span data-ttu-id="fa239-149">Instrua os usuários a se registrarem por conta própria</span><span class="sxs-lookup"><span data-stu-id="fa239-149">Instruct users to self-enroll</span></span>
<a id="instruct-users-to-self-enroll" class="xliff"></a>

<span data-ttu-id="fa239-150">Os usuários podem instalar o software cliente do Intune visitando o [site do Portal da Empresa](https://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fa239-150">Users install the Intune client software by going to the [Company Portal website](https://portal.manage.microsoft.com).</span></span> <span data-ttu-id="fa239-151">As informações exatas que os usuários visualizam no portal da Web podem variar, de acordo com a Autoridade de MDM da sua conta e a plataforma e versão do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="fa239-151">The exact information that users see in the web portal varies, depending on your account's MDM Authority and the OS platform/version of the user's PC.</span></span>

<span data-ttu-id="fa239-152">Se os usuários ainda não tiverem recebido uma licença do Intune ou se a autoridade de MDM da organização não tiver sido definida para o Intune, as opções de registro não serão exibidas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="fa239-152">If users haven't been assigned an Intune license or if the organization's MDM Authority hasn't been set to Intune, users aren't shown any options to enroll.</span></span>

<span data-ttu-id="fa239-153">Se os usuários tiverem recebido uma licença do Intune e a autoridade de MDM da organização tiver sido definida para o Intune:</span><span class="sxs-lookup"><span data-stu-id="fa239-153">If users have been assigned an Intune license, and the organization's MDM Authority has been set to Intune:</span></span>

- <span data-ttu-id="fa239-154">Os usuários do Windows 7 ou Windows 8 podem ver APENAS a opção de registro no Intune, baixando e instalando o software cliente do PC exclusivo de sua organização.</span><span class="sxs-lookup"><span data-stu-id="fa239-154">Windows 7 or Windows 8 PC users are shown ONLY the option to enroll to Intune by downloading and installing the PC client software that is unique to their organization.</span></span>

- <span data-ttu-id="fa239-155">Os usuários de do Windows 8.1 ou Windows 10 têm duas opções de registro:</span><span class="sxs-lookup"><span data-stu-id="fa239-155">Windows 10 or Windows 8.1 PC users are shown two enrollment options:</span></span>

  -  <span data-ttu-id="fa239-156">**Registrar o PC como um dispositivo móvel**: os usuários clicam no botão **Saiba mais sobre como se registrar** e recebem instruções sobre como registrar seu PC como um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="fa239-156">**Enroll PC as a mobile device**: Users choose the **Find Out How to Enroll** button and are taken to instructions on how to enroll their PC as a mobile device.</span></span> <span data-ttu-id="fa239-157">Esse botão é exibido em destaque, porque o registro do MDM é considerado padrão e a opção de registro preferida.</span><span class="sxs-lookup"><span data-stu-id="fa239-157">This button is prominently displayed, because MDM enrollment is considered to be the default and preferred enrollment option.</span></span> <span data-ttu-id="fa239-158">No entanto, a opção de MDM não é aplicável a esse tópico, que aborda somente a instalação do software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-158">However, the MDM option is not applicable to this topic, which covers only the client software installation.</span></span>
  - <span data-ttu-id="fa239-159">**Registrar o PC usando o software cliente do Intune**: você precisará pedir que os usuários selecionem o link **Clique aqui para baixá-lo**, que leva à instalação do software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-159">**Enroll PC using the Intune client software**: You'll need to tell your users to select the **Click here to download it** link, which takes them through the client software installation.</span></span>

<span data-ttu-id="fa239-160">A tabela a seguir resume as opções.</span><span class="sxs-lookup"><span data-stu-id="fa239-160">The following table summarizes the options.</span></span>

  ![Opções de registro padrão por plataforma](../media/default-enrollment-options-table.png)

<span data-ttu-id="fa239-162">As capturas de tela a seguir mostram o que os usuários veem ao registrar seus dispositivos usando o software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-162">The following screenshots show what users see as they enroll their devices using the software client.</span></span>

<span data-ttu-id="fa239-163">Primeiro, solicita-se que os usuários identifiquem ou registrem seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fa239-163">Users are first prompted to identify or to enroll their device.</span></span>

  ![identificar ou registrar dispositivo](../media/identify-device-or-enroll.png)

<span data-ttu-id="fa239-165">Para que os usuários instalem o software cliente do PC, você deverá pedir que eles selecionem o link **Clique aqui para baixá-lo**, que permite aos usuários baixar o software cliente do PC e os conduz pelo processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="fa239-165">To have your users install the PC client software, you'll need to tell them to select the **Click here to download it** link, which enables users to download the PC client software and takes them through the installation process.</span></span> <span data-ttu-id="fa239-166">O botão **Saiba mais sobre como se registrar** leva os usuários para a documentação sobre como se registrar usando o registro do MDM, algo que não é relevante para essas instruções do software cliente.</span><span class="sxs-lookup"><span data-stu-id="fa239-166">The **Find out how to enroll** button takes users to documentation about how to enroll using MDM enrollment, which is not relevant to these software client instructions.</span></span>

  ![selecione o link Clique aqui para baixá-lo](../media/enroll-your-windows-device.png)

<span data-ttu-id="fa239-168">Quando os usuários clicarem no link, eles verão o botão **Baixar Software**, o qual eles devem selecionar para iniciar a instalação do software cliente do PC.</span><span class="sxs-lookup"><span data-stu-id="fa239-168">When users click the link, they see a **Download Software** button, which they select to start the PC client software installation.</span></span>

  ![selecionar o botão de Baixar Software](../media/download-pc-client-software.png)

<span data-ttu-id="fa239-170">Em seguida, pede-se aos usuários que insiram suas credenciais corporativas.</span><span class="sxs-lookup"><span data-stu-id="fa239-170">Users are then asked to sign in with their corporate credentials.</span></span>

  ![Entre usando as suas credenciais](../media/sign-in-to-intune.png)

<span data-ttu-id="fa239-172">Os usuários são levados para a página de boas-vindas da instalação.</span><span class="sxs-lookup"><span data-stu-id="fa239-172">Users are taken to the Welcome page for the installation.</span></span>

  ![Página de boas-vindas da instalação do cliente do PC](../media/welcome-to-pc-agent-install-wizard.png)

<span data-ttu-id="fa239-174">Os usuários devem clicar em **Avançar** para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="fa239-174">Users choose **Next**, and the installation starts.</span></span>

  ![Página de boas-vindas da instalação do cliente do PC](../media/welcome-to-pc-agent-install-wizard.png)

<span data-ttu-id="fa239-176">Quando a instalação for concluída, os usuários devem clicar em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fa239-176">When the installation completes, users choose **Finish**.</span></span>

  ![Concluir a instalação do cliente do PC](../media/completed-the-setup-wizard.png)

<span data-ttu-id="fa239-178">Se os usuários tentarem registrar seu PC como um dispositivo móvel depois de ter feito o registro usando o software cliente do Intune no PC, eles verão a tela de erro a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa239-178">If users try to enroll their PC as a mobile device after having already enrolled using the Intune PC client software, they see the following error screen.</span></span>

  ![Tela mostrada se PC já for registrado](../media/page-shown-if-pc-already-enrolled.png)

## <span data-ttu-id="fa239-180">Monitorar e validar a implantação com êxito do cliente</span><span class="sxs-lookup"><span data-stu-id="fa239-180">Monitor and validate successful client deployment</span></span>
<a id="monitor-and-validate-successful-client-deployment" class="xliff"></a>
<span data-ttu-id="fa239-181">Use um dos procedimentos a seguir para ajudá-lo a monitorar e a validar a implantação do cliente com êxito.</span><span class="sxs-lookup"><span data-stu-id="fa239-181">Use one of the following procedures to help you monitor and validate successful client deployment.</span></span>

### <span data-ttu-id="fa239-182">Para verificar a instalação do software cliente usando o console de administrador do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fa239-182">To verify the installation of the client software from the Microsoft Intune administrator console</span></span>
<a id="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console" class="xliff"></a>

1.  <span data-ttu-id="fa239-183">No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Computadores**.</span><span class="sxs-lookup"><span data-stu-id="fa239-183">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Computers**.</span></span>

2.  <span data-ttu-id="fa239-184">Na lista, encontre os computadores que se comunicam com o Intune ou procure um computador gerenciado específico, digitando o nome do computador (ou qualquer parte do nome) na caixa **Pesquisar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fa239-184">In the list, find the computers that are communicating with Intune, or search for a specific managed computer by typing the computer name (or any part of the name) in the **Search devices** box.</span></span>

3.  <span data-ttu-id="fa239-185">Examine o status do computador no painel inferior do console.</span><span class="sxs-lookup"><span data-stu-id="fa239-185">Examine the status of the computer in the bottom pane of the console.</span></span> <span data-ttu-id="fa239-186">Resolva todos os erros.</span><span class="sxs-lookup"><span data-stu-id="fa239-186">Resolve any errors.</span></span>

### <span data-ttu-id="fa239-187">Para criar um relatório de inventário do computador para exibir todos os computadores registrados</span><span class="sxs-lookup"><span data-stu-id="fa239-187">To create a computer inventory report to display all enrolled computers</span></span>
<a id="to-create-a-computer-inventory-report-to-display-all-enrolled-computers" class="xliff"></a>

1.  <span data-ttu-id="fa239-188">No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Relatórios** &gt; **Relatórios de Inventário do Computador**.</span><span class="sxs-lookup"><span data-stu-id="fa239-188">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Reports** &gt; **Computer Inventory Reports**.</span></span>

2.  <span data-ttu-id="fa239-189">Na página **Criar Novo Relatório**, deixe todos os campos com os valores padrão (a menos que deseje aplicar filtros) e clique em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="fa239-189">On the **Create New Report** page, leave the default values in all fields (unless you want to apply filters), and then click **View Report**.</span></span>

3.  <span data-ttu-id="fa239-190">A página **Relatório de inventário do computador** é aberta em uma nova janela e exibe todos os computadores registrados com sucesso no Intune.</span><span class="sxs-lookup"><span data-stu-id="fa239-190">The **Computer Inventory Report** page opens in a new window that displays all computers that are successfully enrolled in Intune.</span></span>

    > [!TIP]
    > <span data-ttu-id="fa239-191">Clique em qualquer cabeçalho de coluna no relatório para classificar a lista pelo conteúdo dessa coluna.</span><span class="sxs-lookup"><span data-stu-id="fa239-191">Click any column heading in the report to sort the list by the contents of that column.</span></span>

## <span data-ttu-id="fa239-192">Desinstalar o software cliente do Windows</span><span class="sxs-lookup"><span data-stu-id="fa239-192">Uninstall the Windows client software</span></span>
<a id="uninstall-the-windows-client-software" class="xliff"></a>

<span data-ttu-id="fa239-193">Há duas maneiras de cancelar o registro de software cliente do Windows:</span><span class="sxs-lookup"><span data-stu-id="fa239-193">There are two ways to unenroll the Windows client software:</span></span>

- <span data-ttu-id="fa239-194">No console de administração do Intune (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="fa239-194">From the Intune admin console (recommended method)</span></span>
- <span data-ttu-id="fa239-195">De um prompt de comando no cliente</span><span class="sxs-lookup"><span data-stu-id="fa239-195">From a command prompt on the client</span></span>

### <span data-ttu-id="fa239-196">Cancelar o registro usando o console de administração do Intune</span><span class="sxs-lookup"><span data-stu-id="fa239-196">Unenroll by using the Intune admin console</span></span>
<a id="unenroll-by-using-the-intune-admin-console" class="xliff"></a>

<span data-ttu-id="fa239-197">Para cancelar o registro do cliente de software usando o console de administração do Intune, vá para **Grupos** > **Todos os Computadores** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fa239-197">To unenroll the software client by using the Intune admin console, go to **Groups** > **All Computers** > **Devices**.</span></span> <span data-ttu-id="fa239-198">Clique com o botão direito do mouse no cliente e selecione **Desativar/Apagar**.</span><span class="sxs-lookup"><span data-stu-id="fa239-198">Right-click the client, and select **Retire/Wipe**.</span></span>

### <span data-ttu-id="fa239-199">Cancelar o registro usando um prompt de comando no cliente</span><span class="sxs-lookup"><span data-stu-id="fa239-199">Unenroll by using a command prompt on the client</span></span>
<a id="unenroll-by-using-a-command-prompt-on-the-client" class="xliff"></a>

<span data-ttu-id="fa239-200">Usando um prompt de comandos com privilégios elevados, execute um dos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa239-200">Using an elevated command prompt, run one of the following commands.</span></span>

<span data-ttu-id="fa239-201">**Método 1**:</span><span class="sxs-lookup"><span data-stu-id="fa239-201">**Method 1**:</span></span>

    ```
    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune
    ```

<span data-ttu-id="fa239-202">**Método 2**</span><span class="sxs-lookup"><span data-stu-id="fa239-202">**Method 2**</span></span><br><span data-ttu-id="fa239-203">Observe que todos esses agentes estão instalados em cada SKU do Windows:</span><span class="sxs-lookup"><span data-stu-id="fa239-203">Note that all of these agents are installed on every SKU of Windows:</span></span>

    ```
    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall<br>
    wmic product where name="Microsoft Intune Notification Service" call uninstall<br>
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall<br>
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall<br>
    wmic product where name="Microsoft Policy Platform" call uninstall<br>
    wmic product where name="Microsoft Security Client" call uninstall<br>
    wmic product where name="Microsoft Online Management Client" call uninstall<br>
    wmic product where name="Microsoft Online Management Client Service" call uninstall<br>
    wmic product where name="Microsoft Easy Assist v2" call uninstall<br>
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall<br>
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall<br>
    wmic product where name="Windows Firewall Configuration Provider" call uninstall<br>
    wmic product where name="Microsoft Intune Center" call uninstall<br>
    wmic product where name="Microsoft Online Management Update Manager" call uninstall<br>
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall<br>
    wmic product where name="Microsoft Intune" call uninstall<br>
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall<br>
    wmic product where name="Windows Intune Notification Service" call uninstall<br>
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall<br>
    wmic product where name="Windows Online Management Policy Agent" call uninstall<br>
    wmic product where name="Windows Policy Platform" call uninstall<br>
    wmic product where name="Windows Security Client" call uninstall<br>
    wmic product where name="Windows Online Management Client" call uninstall<br>
    wmic product where name="Windows Online Management Client Service" call uninstall<br>
    wmic product where name="Windows Easy Assist v2" call uninstall<br>
    wmic product where name="Windows Intune Monitoring Agent" call uninstall<br>
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall<br>
    wmic product where name="Windows Firewall Configuration Provider" call uninstall<br>
    wmic product where name="Windows Intune Center" call uninstall<br>
    wmic product where name="Windows Online Management Update Manager" call uninstall<br>
    wmic product where name="Windows Online Management Agent Installer" call uninstall<br>
    wmic product where name="Windows Intune" call uninstall
    ```

> [!TIP]
> <span data-ttu-id="fa239-204">O cancelamento de registro do cliente deixará um registro do lado do serviço obsoleto para o cliente afetado.</span><span class="sxs-lookup"><span data-stu-id="fa239-204">Client unenrollment will leave a stale sever-side record for the affected client.</span></span> <span data-ttu-id="fa239-205">O processo de cancelamento de registro é assíncrono e há nove agentes para desinstalação, portanto, pode demorar até 30 minutos para concluir.</span><span class="sxs-lookup"><span data-stu-id="fa239-205">The unenrollment process is asynchronous, and there are nine agents to uninstall, so it may take up to 30 mins to complete.</span></span>

### <span data-ttu-id="fa239-206">Verificar o status do cancelamento de registro</span><span class="sxs-lookup"><span data-stu-id="fa239-206">Check the unenrollment status</span></span>
<a id="check-the-unenrollment-status" class="xliff"></a>

<span data-ttu-id="fa239-207">Verifique o "%ProgramFiles%\Microsoft\OnlineManagement" e certifique-se de que somente os diretórios a seguir sejam exibidos à esquerda:</span><span class="sxs-lookup"><span data-stu-id="fa239-207">Check "%ProgramFiles%\Microsoft\OnlineManagement" and ensure that only the following directories are shown on the left:</span></span>

- <span data-ttu-id="fa239-208">AgentInstaller</span><span class="sxs-lookup"><span data-stu-id="fa239-208">AgentInstaller</span></span>
- <span data-ttu-id="fa239-209">Logs</span><span class="sxs-lookup"><span data-stu-id="fa239-209">Logs</span></span>
- <span data-ttu-id="fa239-210">Updates</span><span class="sxs-lookup"><span data-stu-id="fa239-210">Updates</span></span>
- <span data-ttu-id="fa239-211">Comum</span><span class="sxs-lookup"><span data-stu-id="fa239-211">Common</span></span>

### <span data-ttu-id="fa239-212">Remover a pasta OnlineManagement</span><span class="sxs-lookup"><span data-stu-id="fa239-212">Remove the OnlineManagement folder</span></span>
<a id="remove-the-onlinemanagement-folder" class="xliff"></a>

<span data-ttu-id="fa239-213">O processo de cancelamento de registro não remove a pasta OnlineManagement.</span><span class="sxs-lookup"><span data-stu-id="fa239-213">The unenrollment process does not remove the OnlineManagement folder.</span></span> <span data-ttu-id="fa239-214">Aguarde 30 minutos após a desinstalação e, em seguida, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="fa239-214">Wait 30 minutes after the uninstall, and then run this command.</span></span> <span data-ttu-id="fa239-215">Se você o executar muito cedo, a desinstalação poderá ser deixada em um estado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="fa239-215">If you run it too soon, the uninstall could be left in an unknown state.</span></span> <span data-ttu-id="fa239-216">Para remover a pasta, inicie um prompt elevado e execute:</span><span class="sxs-lookup"><span data-stu-id="fa239-216">To remove the folder, start an elevated prompt and run:</span></span>

    ```
    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".
    ```

### <span data-ttu-id="fa239-217">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fa239-217">See also</span></span>
<a id="see-also" class="xliff"></a>
<span data-ttu-id="fa239-218">[Gerenciar computadores Windows com o Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
[Solucionar problemas de instalação do cliente](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="fa239-218">[Manage Windows PCs with Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
[Troubleshoot client setup](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)</span></span>
