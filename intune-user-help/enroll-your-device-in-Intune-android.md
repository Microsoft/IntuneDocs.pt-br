---
title: <span data-ttu-id="f7a4a-101">Registrar seu dispositivo Android no Intune | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="f7a4a-101">Enroll your Android device in Intune | Microsoft Docs</span></span>
description: <span data-ttu-id="f7a4a-102">Descreve como registrar um dispositivo Android no Intune</span><span class="sxs-lookup"><span data-stu-id="f7a4a-102">Describes how to enroll an Android device in Intune</span></span>
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: e12f8d31abc4e067a6339e93cc21680921ce88e4
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <a name="enroll-your-android-device-in-intune"></a><span data-ttu-id="f7a4a-103">Registrar seu dispositivo Android no Intune</span><span class="sxs-lookup"><span data-stu-id="f7a4a-103">Enroll your Android device in Intune</span></span>

<span data-ttu-id="f7a4a-104">Se sua empresa ou escola usa o Microsoft Intune, você pode registrar seu dispositivo Android para obter acesso a email, arquivos e outros recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-104">If your company or school uses Microsoft Intune, you can enroll your Android device to get access to company email, files, and other resources.</span></span> <span data-ttu-id="f7a4a-105">Quando você registra os dispositivos, o departamento de TI pode gerenciar recursos corporativos ou de estudante e mantê-los seguros, dando-lhe a liberdade de usar seu dispositivo preferido para realizar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-105">When you enroll your devices, your IT department can manage those work or school resources, keep them secure, and give you the freedom to use your preferred device to get your work done.</span></span> <span data-ttu-id="f7a4a-106">Para saber mais sobre registro, consulte [What happens when I install and Company Portal app and enroll my device? (O que acontece quando instalo o aplicativo Portal da Empresa e registro meu dispositivo?)](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)</span><span class="sxs-lookup"><span data-stu-id="f7a4a-106">To learn more about enrollment, see [What happens when I install and Company Portal app and enroll my device?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

<span data-ttu-id="f7a4a-107">Essas instruções de registro destinam-se a dispositivos Samsung KNOX Android e nativos.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-107">These enrollment instructions are for native and Samsung KNOX Android devices.</span></span> <span data-ttu-id="f7a4a-108">O Samsung KNOX é um tipo de segurança que certos dispositivos Samsung usam para proporcionar proteção adicional além da fornecida pelo Android de maneira nativa.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-108">Samsung KNOX is a type of security that certain Samsung devices use to provide additional protection outside of what native Android provides.</span></span> <span data-ttu-id="f7a4a-109">Para verificar se você tem um dispositivo Samsung KNOX, vá para **Configurações** > **Sobre o dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-109">To check if you have a Samsung KNOX device, go to **Settings** > **About device**.</span></span> <span data-ttu-id="f7a4a-110">Se você não vê a “versão do KNOX” listada, tem um dispositivo Android nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-110">If you don't see "KNOX version" listed there, you have a native Android device.</span></span>

<span data-ttu-id="f7a4a-111">Antes ou após o registro, você poderá ser solicitado a escolher uma categoria que melhor descreva como você usa o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-111">Before or after enrolling, you may be asked to choose a category that best describes how you use your device.</span></span> <span data-ttu-id="f7a4a-112">O administrador de TI usa essa categoria para ajudar a verificar os aplicativos aos quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-112">Your IT admin uses this category to help check the apps that you have access to.</span></span>

<span data-ttu-id="f7a4a-113">Se houver erro ao tentar registrar o dispositivo no Intune, você pode [enviar erros de registro ao administrador de TI](send-enrollment-errors-to-your-it-admin-android.md).</span><span class="sxs-lookup"><span data-stu-id="f7a4a-113">If you get an error while you try to enroll your device in Intune, you can [send enrollment errors to your IT admin](send-enrollment-errors-to-your-it-admin-android.md).</span></span>

<span data-ttu-id="f7a4a-114">**Para registrar seu dispositivo Android:**</span><span class="sxs-lookup"><span data-stu-id="f7a4a-114">**To enroll your Android device:**</span></span>

1.  <span data-ttu-id="f7a4a-115">Instale o aplicativo gratuito Portal da Empresa do Intune do [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).</span><span class="sxs-lookup"><span data-stu-id="f7a4a-115">Install the free Intune Company Portal app from [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).</span></span>

2.  <span data-ttu-id="f7a4a-116">Abra o aplicativo Portal da Empresa do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-116">Open the Microsoft Intune Company Portal app.</span></span>

3.  <span data-ttu-id="f7a4a-117">Na tela de **Boas-vindas** do Portal da Empresa, toque em **Entrar** e entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-117">On the Company Portal **Welcome** screen, tap **Sign in**, and then sign in with your work or school account.</span></span>

    ![O aplicativo do Portal da Empresa para a tela de boas-vindas do Android, que pede ao usuário para entrar com sua conta corporativa ou de estudante necessária.](./media/and-enroll-0-welcome-screen.png)   

4.  <span data-ttu-id="f7a4a-120">Se o seu administrador de TI tiver configurado termos e condições da empresa, toque em **ACEITAR** para aceitar os termos.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-120">If your IT admin set up company terms and conditions, tap **ACCEPT** to accept the terms.</span></span> <span data-ttu-id="f7a4a-121">Esta tela pode ser um pouco diferente da imagem abaixo com base na versão do Android que você está usando no momento.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-121">This screen may differ slightly from the image below based on the version of Android you're currently using.</span></span>

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  <span data-ttu-id="f7a4a-123">Conecte-se no aplicativo do Portal da Empresa usando sua conta e senha corporativa ou de estudante e, em seguida, toque em **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-123">Sign in to the Company Portal app using your work or school account and password, and then tap **Sign in**.</span></span>

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  <span data-ttu-id="f7a4a-125">Na tela **Configuração de Acesso da Empresa**, toque em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-125">On the **Company Access Setup** screen, tap **BEGIN**.</span></span>

    ![Tela Configuração de acesso da empresa](./media/and-enroll-4a-comp-access-setup.png)

    > [!NOTE]
    > <span data-ttu-id="f7a4a-127">Os triângulos amarelos não significam que você já tem um erro.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-127">The yellow triangles don't mean you've already got an error.</span></span> <span data-ttu-id="f7a4a-128">Esses ícones indicam que ainda há etapas a serem concluídas no processo de registro.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-128">Those icons indicate that there are still steps to be completed in the enrollment process.</span></span>

7. <span data-ttu-id="f7a4a-129">Na tela **Por que registrar seu dispositivo?** leia sobre o que você pode fazer ao registrar o dispositivo e, em seguida, toque em **CONTINUAR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-129">On the **Why enroll your device?** screen, read about what you can do when you enroll your device, and then tap **CONTINUE**.</span></span>

    ![Tela Por que registrar seu dispositivo](./media/and-enroll-4b-why-enroll.png)

8.  <span data-ttu-id="f7a4a-131">Examine uma lista do que o administrador de TI pode e não pode ver em seu dispositivo e toque em **CONTINUAR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-131">Review a list of what your IT admin can and can't see on your device, and then tap **CONTINUE**.</span></span>

    ![Configurações de privacidade](./media/and-enroll-4c-we-care-privacy.png)

9.  <span data-ttu-id="f7a4a-133">Na tela **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **REGISTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-133">On the **What comes next** screen, read about what happens during enrollment, and then tap **ENROLL**.</span></span>

    ![Tela O que vem em seguida](./media/and-enroll-4d-what-comes-next.png)

10.  <span data-ttu-id="f7a4a-135">Se você estiver usando o Android 6.0 ou posterior, execute esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-135">If you're using Android 6.0 or later, do this step.</span></span> <span data-ttu-id="f7a4a-136">Caso contrário, vá para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-136">Otherwise, go to the next step.</span></span>

    <span data-ttu-id="f7a4a-137">Se o administrador de TI tiver configurado algumas políticas, você poderá ver as seguintes mensagens:</span><span class="sxs-lookup"><span data-stu-id="f7a4a-137">If your IT admin has set up certain policies, you may see the following messages:</span></span>
    -   <span data-ttu-id="f7a4a-138">**Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?**</span><span class="sxs-lookup"><span data-stu-id="f7a4a-138">**Allow Company Portal to make and manage phone calls?**</span></span>

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    <span data-ttu-id="f7a4a-140">Se você vir essa mensagem, toque em **PERMITIR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-140">If you see this message, tap **ALLOW**.</span></span> <span data-ttu-id="f7a4a-141">É seguro tocar em PERMITIR, porque a **Microsoft nunca faz nem gerencia suas chamadas telefônicas**!</span><span class="sxs-lookup"><span data-stu-id="f7a4a-141">It is safe to tap ALLOW because **Microsoft never makes or manages your phone calls**!</span></span> <span data-ttu-id="f7a4a-142">O Google controla o texto da mensagem, e a Microsoft não pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-142">Google controls the message text, and Microsoft cannot change it.</span></span> <span data-ttu-id="f7a4a-143">Ao permitir o acesso, você está apenas autorizando o dispositivo a enviar o número IMEI (Identidade de Equipamentos Móveis Internacional) para o Intune.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-143">When you allow access, all you're doing is letting your device send your device's international mobile station equipment identity (IMEI) number to Intune.</span></span> <span data-ttu-id="f7a4a-144">O IMEI é um número, como um número de série, que identifica exclusivamente um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-144">The IMEI number is like a serial number that uniquely identifies a mobile device.</span></span>

    <span data-ttu-id="f7a4a-145">Se você negar acesso, a mensagem será exibida novamente na próxima vez que você entrar no Portal da Empresa, mas você poderá desligar as mensagens futuras tocando na caixa **Nunca perguntar novamente**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-145">If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box.</span></span> <span data-ttu-id="f7a4a-146">Se você decidir posteriormente permitir o acesso, acesse **Configurações** &gt; **Aplicativos** &gt; **Portal da Empresa** &gt; **Permissões** &gt; **Telefone** e ative a permissão.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-146">If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.</span></span>

    -   <span data-ttu-id="f7a4a-147">**Permitir que o Portal da Empresa acesse seus contatos?**</span><span class="sxs-lookup"><span data-stu-id="f7a4a-147">**Allow Company Portal to access your contacts?**</span></span>

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

        <span data-ttu-id="f7a4a-149">Se você vir essa mensagem, toque em **PERMITIR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-149">If you see this message, tap **ALLOW**.</span></span> <span data-ttu-id="f7a4a-150">É seguro tocar em PERMITIR, porque a **Microsoft nunca acessa seus contatos!**</span><span class="sxs-lookup"><span data-stu-id="f7a4a-150">It is safe to tap ALLOW because **Microsoft never accesses your contacts!**</span></span> <span data-ttu-id="f7a4a-151">O Google controla o texto da mensagem, e a Microsoft não pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-151">Google controls the message text, and Microsoft cannot change it.</span></span> <span data-ttu-id="f7a4a-152">Ao permitir acesso, ele apenas autorizará o aplicativo do Portal da Empresa a criar, usar e gerenciar sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-152">When you allow access, it only lets the Company Portal app create, use, and manage your work account.</span></span>

        <span data-ttu-id="f7a4a-153">Se você negar acesso, a mensagem será exibida novamente na próxima vez que você entrar no Portal da Empresa, mas você poderá desligar as mensagens futuras tocando na caixa **Nunca perguntar novamente**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-153">If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box.</span></span> <span data-ttu-id="f7a4a-154">Se você decidir posteriormente permitir o acesso, acesse **Configurações** &gt; **Aplicativos** &gt; **Portal da Empresa** &gt; **Permissões** &gt; **Telefone** e ative a permissão.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-154">If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.</span></span>

11.  <span data-ttu-id="f7a4a-155">Na tela **Ativar administrador do dispositivo**, clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-155">On the **Activate device administrator** screen, tap **Activate**.</span></span>

    ![Tela Ativar administrador do dispositivo](./media/and-enroll-5-activate.png)

    <span data-ttu-id="f7a4a-157">A função de administrador do dispositivo é aquela que o Portal da Empresa precisa para gerenciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-157">The device administrator role is one that the Company Portal needs to manage your device.</span></span> <span data-ttu-id="f7a4a-158">Ela permite que seu administrador veja determinadas coisas - como quantas vezes você tentou desbloquear sua tela - e tome algumas atitudes.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-158">It allows your admin to see certain things - like how many times you've attempted to unlock your screen - and to take some actions.</span></span>

    <span data-ttu-id="f7a4a-159">O importante a lembrar é que são ações realizadas em nome da segurança.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-159">The key to remember is that these are actions that are taken in the name of security.</span></span> <span data-ttu-id="f7a4a-160">Seu administrador de TI não está tentando violar sua privacidade ou apagar suas informações sem qualquer motivo, mas quer ter certeza de que os dados corporativos são mantidos seguros.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-160">Your IT admin isn't trying to violate your privacy or erase your information for no reason, but wants to make sure that corporate data is kept safe.</span></span>

    <span data-ttu-id="f7a4a-161">A Microsoft não controla essa mensagem, e sabemos que seu conteúdo pode parecer um pouco drástico.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-161">Microsoft does not control this message, and we understand that its phrasing can seem somewhat drastic.</span></span> <span data-ttu-id="f7a4a-162">Não há uma maneira para o Portal da Empresa exibir apenas as restrições e acessos que são relevantes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-162">There's not a way for the Company Portal to display just the restrictions and access that are relevant to your organization.</span></span> <span data-ttu-id="f7a4a-163">Todos são concedidos de uma vez nesta tela.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-163">All of them are granted at once on this screen.</span></span> <span data-ttu-id="f7a4a-164">Entre em contato com o administrador de TI para saber mais sobre como usar as informações de contato no [site do Portal da Empresa](http://portal.manage.microsoft.com) se você tiver dúvidas específicas ao uso individual de sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-164">Contact your IT admin for more information using the contact information in the [Company Portal website](http://portal.manage.microsoft.com) if you have questions specific to your individual organization's use.</span></span>

12.  <span data-ttu-id="f7a4a-165">Siga os prompts para inserir um PIN ou senha.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-165">Follow the prompts to enter a PIN or password.</span></span> <span data-ttu-id="f7a4a-166">Se já tiver configurado um PIN ou senha neste dispositivo, você não verá esta tela ou será solicitado a inserir um novo PIN ou senha.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-166">If you already set up a PIN or password on this device, you won't see this screen or be required to enter a new PIN or password.</span></span>

    ![Inserir o PIN ou a senha](./media/and-enroll-6-PIN-native.png)

13.  <span data-ttu-id="f7a4a-168">Se você estiver usando um dispositivo Samsung KNOX, toque em **Confirmar** e você verá uma mensagem informando que seu dispositivo está sendo registrado.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-168">If you are using a Samsung KNOX device, tap **Confirm**, and you’ll see a message that your device is being enrolled.</span></span> <span data-ttu-id="f7a4a-169">Se você estiver usando um dispositivo Android nativo, basta observar a tela abaixo mostrando que o dispositivo está sendo registrado.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-169">If you are using a native Android device, just notice the following screen that shows that your device is being enrolled.</span></span>

    ![Política de privacidade do Samsung KNOX](./media/and-enroll-7-knox-privacy-policy.png)

    <span data-ttu-id="f7a4a-171">Esta tela mostra que seu dispositivo está sendo registrado.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-171">This screen shows that your device is being enrolled.</span></span>

    ![Tela de registro do dispositivo](./media/and-enroll-8-device-enrolling.png)

14. <span data-ttu-id="f7a4a-173">Quando a tela **Configuração de Acesso da Empresa** for exibida, toque em **CONTINUAR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-173">When the **Company Access Setup** screen appears, tap **CONTINUE**.</span></span> <span data-ttu-id="f7a4a-174">Se uma mensagem indicar que o dispositivo está fora de conformidade, siga as instruções para corrigir o problema e, em seguida, toque em **CONTINUAR**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-174">If a message indicates that your device is out of compliance, follow the instructions to fix the issue, and then tap **CONTINUE**.</span></span>

    ![O dispositivo não é compatível, mas está registrado](./media/and-enroll-9a-noncompliant-enrolled-device.png)

    ![Problemas de conformidade do dispositivo aparecem nessa resolução](./media/and-enroll-9b-resolve-compliance-issues.png)

    <span data-ttu-id="f7a4a-177">Você pode encontrar mais informações sobre os problemas tocando neles.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-177">You can find out more about the issues by tapping on them.</span></span>

    ![Problemas de conformidade do dispositivo expandidos](./media/and-enroll-9c-resolve-compliance-issues-expanded.png)

    ![Tela Configuração de acesso da empresa](./media/and-enroll-9d-comp-access-setup.png)  

15. <span data-ttu-id="f7a4a-180">Na tela **Configuração de Acesso da Empresa completa**, toque em **CONCLUÍDO**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-180">On the **Company Access Setup complete** screen, tap **DONE**.</span></span> <span data-ttu-id="f7a4a-181">Agora, seu dispositivo está registrado.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-181">Your device is now enrolled.</span></span>

    ![Tela Configuração de acesso da empresa concluída](./media/and-enroll-10-comp-access-setup-complete.png)

<span data-ttu-id="f7a4a-183">Antes de tentar instalar aplicativos corporativos, acesse **Configurações** &gt; **Segurança** e ative **Fontes desconhecidas**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-183">Before you try to install company apps, go to **Settings** &gt; **Security**, and turn on **Unknown sources**.</span></span> <span data-ttu-id="f7a4a-184">Se não ativar essa opção antes de tentar instalar os aplicativos, você verá a mensagem: “Instalação bloqueada”.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-184">If you don't turn on this option before you try to install apps, you'll see the following message: "Install blocked.</span></span> <span data-ttu-id="f7a4a-185">Por motivos de segurança, seu dispositivo está definido para bloquear as instalações de aplicativos obtidos de fontes desconhecidas."</span><span class="sxs-lookup"><span data-stu-id="f7a4a-185">For security reasons, your device is set to block installations of apps obtained from unknown sources."</span></span> <span data-ttu-id="f7a4a-186">Você pode tocar em **Configurações** na caixa de diálogo de erro para ir para a opção **Fontes desconhecidas**.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-186">You can tap **Settings** on the error dialog box to go to the **Unknown sources** option.</span></span>

> [!Note]
> <span data-ttu-id="f7a4a-187">Se sua organização estiver usando software de gerenciamento de despesas de telecomunicações, você terá algumas etapas adicionais para concluir antes de o dispositivo estar totalmente inscrito.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-187">If your organization is using telecom expense management software, you will have an additional few steps to complete before your device is fully enrolled.</span></span> <span data-ttu-id="f7a4a-188">Saiba mais [aqui](enroll-your-device-with-telecom-expense-management-android.md).</span><span class="sxs-lookup"><span data-stu-id="f7a4a-188">Find out more [here](enroll-your-device-with-telecom-expense-management-android.md).</span></span>

<span data-ttu-id="f7a4a-189">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="f7a4a-189">Still need help?</span></span> <span data-ttu-id="f7a4a-190">Entre em contato com o administrador de TI (consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com) para obter as informações de contato) ou escreva para a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">equipe de Android da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f7a4a-190">Contact your IT admin (check the [Company Portal website](http://portal.manage.microsoft.com) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.</span></span>
