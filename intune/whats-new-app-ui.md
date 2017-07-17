---
title: "Atualizações da interface do usuário para aplicativos de usuário final do Intune"
description: "Descubra o que mudou na interface do usuário para aplicativos que funcionam em dispositivos de usuários finais com o Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e2e1eb6da9114c689aae5eb06f7d7c780f35817
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ea2b5-103">Atualizações da interface do usuário para aplicativos de usuário final do Intune</span><span class="sxs-lookup"><span data-stu-id="ea2b5-103">UI updates for Intune end user apps</span></span>
<a id="ui-updates-for-intune-end-user-apps" class="xliff"></a>
<span data-ttu-id="ea2b5-104">Saiba quais atualizações foram feitas na interface do usuário para os aplicativos que os usuários finais vão encontrar nesta versão do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-104">Learn what updates we've made to the UI for apps that your end users will see in this release of Microsoft Intune.</span></span> <span data-ttu-id="ea2b5-105">Isso pode ajudá-lo nas comunicações com usuários e na atualização da documentação personalizada que você criou para dar suporte à sua implantação.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-105">This can help you with user communications and any updating custom documentation that you've created to support your deployment.</span></span> <span data-ttu-id="ea2b5-106">Isso também pode ajudá-lo a entender como solucionar melhor os problemas enfrentados caso seja necessário ligar para a assistência técnica para obter suporte usando o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-106">It can also help you understand how to better troubleshoot any issues they're facing should they call helpdesk for support using the Company Portal.</span></span>

## <span data-ttu-id="ea2b5-107">Semana de 12 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="ea2b5-107">Week of June 12, 2017</span></span>
<a id="week-of-june-12-2017" class="xliff"></a>

### <span data-ttu-id="ea2b5-108">O aplicativo de Portal da Empresa para Android agora tem uma nova experiência do usuário final para as Políticas de Proteção do Aplicativo <!--1305217--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-108">Company Portal app for Android now has a new end user experience for App Protection Policies <!--1305217--></span></span>
<a id="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--" class="xliff"></a>
<span data-ttu-id="ea2b5-109">Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-109">Based on customer feedback, we've modified the Company Portal app for Android to show an **Access Company Content** button.</span></span> <span data-ttu-id="ea2b5-110">A intenção é impedir que os usuários finais passem pelo processo de registro desnecessariamente quando eles só precisam acessar os aplicativos que dão suporte às Políticas de Proteção de Aplicativo, um recurso de gerenciamento de aplicativos móveis do Intune.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-110">The intent is to prevent end users from unnecessarily going through the enrollment process when they only need to access apps that support App Protection Policies, a feature of Intune mobile application management.</span></span>

<span data-ttu-id="ea2b5-111">O usuário deverá tocar no botão **Acessar Conteúdo da Empresa** em vez de iniciar o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-111">The user will tap on the **Access Company Content** button instead of beginning to enroll the device.</span></span>

![Uma imagem do aplicativo de Portal da Empresa Android, que mostra em texto grande “Acessar Conteúdo da Empresa” no meio em vez de oferecer opções de registro imediatamente, como é o caso padrão](./media/and_access_company_content_after_1706.png)

<span data-ttu-id="ea2b5-113">O usuário é levado para o site de Portal da Empresa para autorizar o uso do aplicativo no dispositivo, no qual o site do Portal da Empresa verifica as credenciais.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-113">The user then is taken to the Company Portal website to authorize the app for use on their device, where the Company Portal website verifies their credentials.</span></span>

![Uma imagem do site do Portal da Empresa, confirmando a entrada.](./media/and_iwp_sign_in_auth_page_after_1706.png)

<span data-ttu-id="ea2b5-115">O dispositivo ainda pode ser registrado no gerenciamento completo tocando no menu de **ação**.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-115">The device can still be enrolled into full management by tapping on the **action** menu.</span></span>

![Uma imagem do aplicativo de Portal da Empresa para Android, mostrando o menu no canto superior direito da tela com uma opção para ainda registrar o dispositivo.](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <span data-ttu-id="ea2b5-117">Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-117">Improvements to app syncing with Windows 10 Creators Update <!--676505--></span></span>
<a id="improvements-to-app-syncing-with-windows-10-creators-update---676505--" class="xliff"></a>

<span data-ttu-id="ea2b5-118">O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703).</span><span class="sxs-lookup"><span data-stu-id="ea2b5-118">The Company Portal app for Windows 10 will now automatically initiate a sync for app install requests for devices with Windows 10 Creators Update (version 1703).</span></span> <span data-ttu-id="ea2b5-119">Isso reduzirá o problema de paralisação de instalações de aplicativo durante o estado de "Sincronização pendente".</span><span class="sxs-lookup"><span data-stu-id="ea2b5-119">This will reduce the issue of app installs stalling during the "Pending Sync" state.</span></span> <span data-ttu-id="ea2b5-120">Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-120">In addition, users will be able to manually initiate a sync from within the app.</span></span>

![Uma imagem do aplicativo de Portal da Empresa do Windows 10, em que o download do Microsoft Word está em um estado pendente na loja de aplicativos do Portal da Empresa.](./media/w10_download_pending_after_1706.png)

![Uma imagem do aplicativo de Portal da Empresa do Windows 10, com o novo estado de sincronização automática mostrando com uma mensagem de status que indica que o dispositivo está sendo sincronizado e tentando baixar o aplicativo.](./media/w10_download_pending_syncing_after_1706.png)

### <span data-ttu-id="ea2b5-123">Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938---></span><span class="sxs-lookup"><span data-stu-id="ea2b5-123">New guided experience for Windows 10 Company Portal <!---1058938---></span></span>
<a id="new-guided-experience-for-windows-10-company-portal----1058938---" class="xliff"></a>
<span data-ttu-id="ea2b5-124">O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-124">The Company Portal app for Windows 10 will include a guided Intune walkthrough experience for devices that have not been identified or enrolled.</span></span> <span data-ttu-id="ea2b5-125">A nova experiência fornece instruções passo a passo que guiam o usuário pelo registro no Azure Active Directory (necessário para os recursos do Acesso Condicional) e pelo registro do MDM (necessário para os recursos de gerenciamento de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="ea2b5-125">The new experience provides step-by-step instructions that guide the user through registering into Azure Active Directory (required for Conditional Access features) and MDM enrollment (required for device management features).</span></span> <span data-ttu-id="ea2b5-126">A experiência guiada estará acessível na home page do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-126">The guided experience will be accessible from the Company Portal home page.</span></span> <span data-ttu-id="ea2b5-127">Os usuários poderão continuar usando o aplicativo se não concluírem o registro, mas terão funcionalidade limitada.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-127">Users can continue to use the app if they do not complete registration and enrollment, but will experience limited functionality.</span></span>

<span data-ttu-id="ea2b5-128">Esta atualização só é visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-128">This update is only visible on devices running Windows 10 Anniversary Update (build 1607) or higher.</span></span>

![Uma imagem da página de aterrissagem do aplicativo de Portal da Empresa do Windows 10, com uma mensagem de status no meio da lista de “dispositivos”, que indica a um usuário que o dispositivo usado ainda não foi configurado para uso corporativo e que o usuário deve selecionar a mensagem para iniciar a configuração.](./media/win10_guided_enroll_select_setup_after_1706.png)

![Uma imagem da página de configuração do aplicativo de Portal da Empresa do Windows 10, que avisa ao usuário que ele precisa adicionar uma conta corporativa ao dispositivo para poder registrá-lo no gerenciamento.](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Uma imagem da página Adicionar conta corporativa a este dispositivo do aplicativo de Portal da Empresa do Windows 10, que indica ao usuário que ele precisará acessar o aplicativo Configurações e selecionar “Conectar” para concluir o registro.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Uma imagem da tela Registrar no gerenciamento do aplicativo de Portal da Empresa do Windows 10, que mostra uma mensagem de status concluído dizendo que o dispositivo do usuário agora está registrado e que o botão “Avançar” deve ser tocado para continuar.](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Uma imagem da tela de conclusão do aplicativo de Portal da Empresa do Windows 10, informando ao usuário que está tudo pronto e que o dispositivo está registrado com uma conta corporativa devidamente adicionada.](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <span data-ttu-id="ea2b5-135">Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-135">New menu action to easily remove Company Portal <!--1164569--></span></span>
<a id="new-menu-action-to-easily-remove-company-portal---1164569--" class="xliff"></a>
<span data-ttu-id="ea2b5-136">De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-136">Based on user feedback, the Company Portal app for Android has added a new menu action to initiate the removal of Company Portal from your device.</span></span> <span data-ttu-id="ea2b5-137">Essa ação remove o dispositivo do gerenciamento do Intune, de forma que o aplicativo possa ser removido do dispositivo pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-137">This action removes the device from Intune management so that the app can be removed from the device by the user.</span></span>

![Uma imagem do aplicativo do Portal da Empresa do Android, com o menu de ação aberto no canto superior direito.](./media/android_remove_cp_menu_action_after_1705.png)

![Uma imagem da caixa de diálogo de confirmação, que está disponível após a seleção da nova opção “Remover o Portal da Empresa” no menu de ação.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <span data-ttu-id="ea2b5-143">Semana de 5 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="ea2b5-143">Week of June 5, 2017</span></span>
<a id="week-of-june-5-2017" class="xliff"></a>

### <span data-ttu-id="ea2b5-144">Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS</span><span class="sxs-lookup"><span data-stu-id="ea2b5-144">Improvements to the app tiles in the Company Portal app for iOS</span></span>
<a id="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios" class="xliff"></a>
<span data-ttu-id="ea2b5-145">Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-145">We updated the design of the app tiles on the homepage to reflect the branding color you set for the Company Portal.</span></span>

<span data-ttu-id="ea2b5-146">**Antes**</span><span class="sxs-lookup"><span data-stu-id="ea2b5-146">**Before**</span></span>

![Uma imagem do aplicativo do Portal da Empresa para iOS antes da atualização, que mostrava imagens de preenchimento predefinidas para “Todos os aplicativos”, “Aplicativos em destaque” e “Categorias”.](./media/cp_ios_homepage_before_1705.png)

<span data-ttu-id="ea2b5-148">**Depois**</span><span class="sxs-lookup"><span data-stu-id="ea2b5-148">**After**</span></span>

![Uma imagem do aplicativo do Portal da Empresa para iOS após a atualização, que agora reflete a capacidade de selecionar as cores relevantes para sua organização.](./media/cp_ios_homepage_after_1705.png)

### <span data-ttu-id="ea2b5-150">Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS</span><span class="sxs-lookup"><span data-stu-id="ea2b5-150">Account picker now available for the Company Portal app for iOS</span></span>
<a id="account-picker-now-available-for-the-company-portal-app-for-ios" class="xliff"></a>
<span data-ttu-id="ea2b5-151">Se os usuários usavam suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft em seus dispositivos iOS, talvez eles vejam nosso novo seletor de conta ao entrar no Portal da Empresa pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-151">If users have used their work or school account to sign in to other Microsoft apps on their iOS device, then they may see our new account picker when signing into the Company Portal for the first time.</span></span>

![Uma imagem do seletor de conta, que mostra um usuário de teste “Ricardo Santos” escolhendo entre um de seus dois endereços de email.](./media/cp_ios_multi-account-selector-after-1705.png)

## <span data-ttu-id="ea2b5-154">Abril de 2017</span><span class="sxs-lookup"><span data-stu-id="ea2b5-154">April 2017</span></span>
<a id="april-2017" class="xliff"></a>

### <span data-ttu-id="ea2b5-155">Novos ícones para o navegador gerenciado e o Portal da Empresa<!--918433, 918431--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-155">New icons for the Managed Browser and the Company Portal <!--918433, 918431--></span></span>
<a id="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--" class="xliff"></a>

<span data-ttu-id="ea2b5-156">O navegador gerenciado está recebendo ícones atualizados para versões de Android e iOS do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-156">The Managed Browser is receiving updated icons for both the Android and iOS versions of the app.</span></span> <span data-ttu-id="ea2b5-157">O novo ícone conterá o emblema Intune atualizado para torná-lo mais consistente com outros aplicativos no Enterprise Mobility + Security (EM+S).</span><span class="sxs-lookup"><span data-stu-id="ea2b5-157">The new icon will contain the updated Intune badge to make it more consistent with other apps in Enterprise Mobility + Security (EM+S).</span></span>

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

<span data-ttu-id="ea2b5-158">O Portal da Empresa também está recebendo ícones atualizados para as versões do Windows, iOS e Android do aplicativo para aprimorar a consistência com outros aplicativos EM+S.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-158">The Company Portal is also receiving updated icons for the Android, iOS, and Windows versions of the app to improve consistency with other apps in EM+S.</span></span> <span data-ttu-id="ea2b5-159">Esses ícones serão liberados gradualmente em plataformas a partir de abril até o fim de maio.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-159">These icons will be gradually released across platforms from April to late May.</span></span>

### <span data-ttu-id="ea2b5-160">Indicador de progresso de conexão no Portal da Empresa Android<!--953374--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-160">Sign-in progress indicator in Android Company Portal <!--953374--></span></span>
<a id="sign-in-progress-indicator-in-android-company-portal---953374--" class="xliff"></a>

<span data-ttu-id="ea2b5-161">Uma atualização para o aplicativo de Portal da empresa Android mostra um indicador de progresso de conexão quando o usuário inicia ou reinicia o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-161">An update to the Android Company Portal app shows a sign-in progress indicator when the user launches or resumes the app.</span></span> <span data-ttu-id="ea2b5-162">O indicador avança por novos status, começando com "Conectando …", e "Fazendo logon..." e "Verificando os requisitos de segurança..." antes de permitir que o usuário acesse o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-162">The indicator progresses through new statuses, beginning with "Connecting...", then "Signing in...", then "Checking for security requirements..." before allowing the user to access the app.</span></span>

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <span data-ttu-id="ea2b5-163">Status de instalação do aplicativo aprimorado para o aplicativo de Portal da empresa do Windows 10 <!--676495--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-163">Improved app install status for the Windows 10 Company Portal app <!--676495--></span></span>
<a id="improved-app-install-status-for-the-windows-10-company-portal-app---676495--" class="xliff"></a>
<span data-ttu-id="ea2b5-164">Agora, o aplicativo de Portal da Empresa do Windows 10 fornece uma barra de progresso da instalação na página de detalhes do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-164">The Windows 10 Company Portal app now provides an install progress bar on the app details page.</span></span> <span data-ttu-id="ea2b5-165">Isso tem suporte para aplicativos modernos em dispositivos com a Atualização de Aniversário do Windows 10 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-165">This is supported for modern apps on devices running the Windows 10 Anniversary Update and up..</span></span>

<span data-ttu-id="ea2b5-166">__Antes__ ![Uma imagem da versão anterior da tela de carregamento, em que o status simplesmente mostrava “Instalando”.](./media/cp_win10_install_status_before_1704.png)</span><span class="sxs-lookup"><span data-stu-id="ea2b5-166">__Before__ ![An image of the previous version of the loading screen, where the status simply said 'installing.'](./media/cp_win10_install_status_before_1704.png)</span></span>

<span data-ttu-id="ea2b5-167">__Depois__ ![Uma imagem da versão atualizada da tela de carregamento, que agora exibe uma barra de progresso da instalação.](./media/cp_win10_install_status_after_1704.png)</span><span class="sxs-lookup"><span data-stu-id="ea2b5-167">__After__ ![An image of the updated version of the loading screen, which now shows an install progress bar.](./media/cp_win10_install_status_after_1704.png)</span></span>

## <span data-ttu-id="ea2b5-168">Fevereiro de 2017</span><span class="sxs-lookup"><span data-stu-id="ea2b5-168">February 2017</span></span>
<a id="february-2017" class="xliff"></a>

### <span data-ttu-id="ea2b5-169">Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622, announced 1702--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-169">New user experience for the Company Portal app for Android <!--621622, announced 1702--></span></span>
<a id="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--" class="xliff"></a>
<span data-ttu-id="ea2b5-170">A partir de março, o aplicativo de Portal da empresa para Android seguirá [as diretrizes de design de material](https://material.io/guidelines/material-design/introduction.html) para criar uma aparência mais moderna.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-170">Beginning in March, the Company Portal app for Android will follow [material design guidelines](https://material.io/guidelines/material-design/introduction.html) to create a more modern look and feel.</span></span> <span data-ttu-id="ea2b5-171">Essa experiência do usuário aprimorada inclui:</span><span class="sxs-lookup"><span data-stu-id="ea2b5-171">This improved user experience includes:</span></span>

* <span data-ttu-id="ea2b5-172">__Cores__: cabeçalhos de guia podem ser coloridos de acordo com sua paleta de cores personalizada.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-172">__Colors__: tab headers can be colored according to your custom color palette.</span></span>

![À esquerda, uma imagem do aplicativo Portal da Empresa para Android antes da atualização.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* <span data-ttu-id="ea2b5-176">__Interface__: os botões __Aplicativos em Destaque__ e __Todos os Aplicativos__ foram atualizados na guia __Aplicativos__.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-176">__Interface__: __Featured Apps__ and __All Apps__ buttons have been updated in the __Apps__ tab.</span></span> <span data-ttu-id="ea2b5-177">O botão __Pesquisa__ agora é um botão de ação flutuante.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-177">The __Search__ button is now a floating action button.</span></span>

![À esquerda, uma imagem do aplicativo Portal da Empresa para Android antes da atualização.](./media/CP_Android_AppsTab_BeforeAfter.png)

* <span data-ttu-id="ea2b5-181">__Navegação__: Todos os Aplicativos mostra uma exibição com guias de __Em Destaque__, __Todos__ e __Categorias__ para facilitar a navegação.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-181">__Navigation__: All Apps shows a tabbed view of __Featured__, __All__ and __Categories__ for easier navigation.</span></span> <span data-ttu-id="ea2b5-182">__Contatar TI__ foi otimizada para melhor legibilidade.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-182">__Contact IT__ has been streamlined for improved readability.</span></span>

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <span data-ttu-id="ea2b5-183">Janeiro de 2017</span><span class="sxs-lookup"><span data-stu-id="ea2b5-183">January 2017</span></span>
<a id="january-2017" class="xliff"></a>

### <span data-ttu-id="ea2b5-184">Modernizando o site Portal da Empresa <!--753980, announced 1701--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-184">Modernizing the Company Portal website <!--753980, announced 1701--></span></span>
<a id="modernizing-the-company-portal-website---753980-announced-1701--" class="xliff"></a>
<span data-ttu-id="ea2b5-185">A partir de fevereiro, o site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-185">Beginning in February, the Company Portal website will support apps that are targeted to users who do not have managed devices.</span></span> <span data-ttu-id="ea2b5-186">O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu hambúrguer",</span><span class="sxs-lookup"><span data-stu-id="ea2b5-186">The website will align with other Microsoft products and services by using a new contrasting color scheme, dynamic illustrations, and a "hamburger menu,"</span></span> ![Imagem pequena do menu hambúrguer que foi adicionado no canto superior esquerdo do site do Portal da Empresa](./media/CP_hamburger_menu.png) <span data-ttu-id="ea2b5-188">que conterá detalhes de contato do suporte técnico e informações sobre dispositivos gerenciados existentes.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-188">which will contain helpdesk contact details and information on existing managed devices.</span></span> <span data-ttu-id="ea2b5-189">A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-189">The landing page will be rearranged to emphasize apps that are available to users, with carousels for Featured and Recently Updated apps.</span></span>

![À esquerda, uma imagem da versão atual do site de Portal da Empresa com a versão anterior da exibição de Aplicativos, Meus Dispositivos e Destacados e Categorias.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <span data-ttu-id="ea2b5-192">Em breve na interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ea2b5-192">Coming soon in the UI</span></span>
<a id="coming-soon-in-the-ui" class="xliff"></a>
<span data-ttu-id="ea2b5-193">Esses são os planos de aprimoramento da experiência do usuário por meio da atualização de nossa interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-193">These are the plans for ways we will be improving the user experience by updating our user interface.</span></span>

> [!Note]
> <span data-ttu-id="ea2b5-194">Observe que as imagens abaixo podem ser visualizações, e o produto anunciado pode ser diferente das versões apresentadas.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-194">Please note that the images below may be previews, and the announced product may differ from the presented versions.</span></span>

### <span data-ttu-id="ea2b5-195">Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123--></span><span class="sxs-lookup"><span data-stu-id="ea2b5-195">Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123--></span></span>
<a id="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--" class="xliff"></a>

<span data-ttu-id="ea2b5-196">Anunciamos uma mudança que entrará em vigor nos próximos meses, destinada a melhorar a experiência de entrada para aplicativos Portal da Empresa do Intune para Android, iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-196">We are announcing a change that is coming in the next few months that will improve the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows.</span></span> <span data-ttu-id="ea2b5-197">A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-197">The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change.</span></span> <span data-ttu-id="ea2b5-198">Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-198">In addition, users can now sign in to the Company Portal from another device with a generated, single-use code.</span></span> <span data-ttu-id="ea2b5-199">Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-199">This is especially useful in cases when users need to sign in without credentials.</span></span>  

<span data-ttu-id="ea2b5-200">Abaixo você pode ver a experiência de início de sessão anterior, a nova experiência de entrada com as credenciais e a nova experiência de entrada através de outro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-200">Below you can see the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device.</span></span>

<span data-ttu-id="ea2b5-201">__Experiência de início de sessão anterior__</span><span class="sxs-lookup"><span data-stu-id="ea2b5-201">__Previous sign in experience__</span></span>

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site.](./media/cp_ios_aad_signin_before_1704_001.png)

![Depois de tocar em Entrar, o usuário insere as credenciais nesta página, que solicita um email e uma senha de usuário e também oferece meios para resolver falhas de senha.](./media/cp_ios_aad_signin_before_1704_002.png)

![Depois de fornecer a senha, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_before_1704_003.png)

<span data-ttu-id="ea2b5-207">__Nova experiência de início de sessão__</span><span class="sxs-lookup"><span data-stu-id="ea2b5-207">__New sign in experience__</span></span>

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site.](./media/cp_ios_aad_signin_after_1704_001.png)

![O usuário é solicitado a fornecer somente o endereço de email em vez do email e da senha na mesma tela.](./media/cp_ios_aad_signin_after_1704_002.png)

![É solicitada a senha do usuário, depois que seu endereço de email é aceito.](./media/cp_ios_aad_signin_after_1704_003.png)

![Depois de concluir o processo de autenticação, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

<span data-ttu-id="ea2b5-214">__Nova experiência de início de sessão ao entrar em outro dispositivo__</span><span class="sxs-lookup"><span data-stu-id="ea2b5-214">__New sign in experience when signing in from another device__</span></span>

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

<span data-ttu-id="ea2b5-218">Toque no link __Entrar de outro dispositivo__.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-218">Tap the __Sign in from another device__ link.</span></span>

![São fornecidas instruções para acessar a página aka.ms/devicelogin com uma senha exclusiva do seu computador de trabalho e, em seguida, usar o código para entrar.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

<span data-ttu-id="ea2b5-220">Inicie um navegador e acesse [https://aka.ms/devicelogin](https://aka.ms/devicelogin).</span><span class="sxs-lookup"><span data-stu-id="ea2b5-220">Launch a browser and go to [https://aka.ms/devicelogin](https://aka.ms/devicelogin).</span></span>

![Uma imagem do navegador do usuário em seu computador de trabalho em vez de seu aplicativo Portal da Empresa.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

<span data-ttu-id="ea2b5-223">Insira o código que você viu no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-223">Enter the code you saw in the Company Portal app.</span></span> <span data-ttu-id="ea2b5-224">Ao selecionar __Continuar__, você será capaz de se autenticar usando qualquer método que tenha suporte pela sua empresa, como um cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-224">When you select __Continue__, you will be able to authenticate in the using any method that is supported by your company, such as a smartcard.</span></span>

![O usuário inseriu o código exclusivo no campo, e o site de "Logon do dispositivo" pediu uma confirmação de que o Portal da Empresa do Intune era o aplicativo correto a receber autorização para entrar.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Uma página de confirmação, informando que o usuário entrou no aplicativo Portal da Empresa em seu dispositivo, e que essa página poderá ser fechada.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

<span data-ttu-id="ea2b5-227">O aplicativo Portal da Empresa começará a entrar.</span><span class="sxs-lookup"><span data-stu-id="ea2b5-227">The Company Portal app will begin signing in.</span></span>

![Depois de concluir o processo de autenticação, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)
### <span data-ttu-id="ea2b5-229">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ea2b5-229">See also</span></span>
<a id="see-also" class="xliff"></a>
* [<span data-ttu-id="ea2b5-230">Blog do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ea2b5-230">Microsoft Intune Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=273882)
* [<span data-ttu-id="ea2b5-231">Mapa da Plataforma de Nuvem</span><span class="sxs-lookup"><span data-stu-id="ea2b5-231">Cloud Platform roadmap</span></span>](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [<span data-ttu-id="ea2b5-232">Novidades do Intune</span><span class="sxs-lookup"><span data-stu-id="ea2b5-232">What's new in Intune</span></span>](https://docs.microsoft.com/intune/whats-new)
