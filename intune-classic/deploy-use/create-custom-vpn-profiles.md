---
title: "Configurações personalizadas para perfis VPN do Microsoft Intune"
description: "Use configurações personalizadas para criar perfis de VPN no Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2ee20ce0b9f7794132c3a56046b1680f940b3424
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b8089-103">Configurações personalizadas para perfis VPN do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b8089-103">Custom configurations for Microsoft Intune VPN profiles</span></span>
<a id="custom-configurations-for-microsoft-intune-vpn-profiles" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="b8089-104">Criar uma configuração personalizada</span><span class="sxs-lookup"><span data-stu-id="b8089-104">Create a custom configuration</span></span>
<a id="create-a-custom-configuration" class="xliff"></a>
<span data-ttu-id="b8089-105">É possível usar políticas de configuração personalizada do Intune para criar perfis VPN para:</span><span class="sxs-lookup"><span data-stu-id="b8089-105">You can use Intune custom configuration polices to create VPN profiles for:</span></span>

* <span data-ttu-id="b8089-106">Dispositivos que executam o Android 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="b8089-106">Devices that run Android 4 and later</span></span>
* <span data-ttu-id="b8089-107">Dispositivos Android for Work</span><span class="sxs-lookup"><span data-stu-id="b8089-107">Android for Work devices</span></span>
* <span data-ttu-id="b8089-108">Dispositivos registrados que executam o Windows 8.1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="b8089-108">Enrolled devices that run Windows 8.1 and later</span></span>
* <span data-ttu-id="b8089-109">Dispositivos que executam o Windows Phone 8.1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="b8089-109">Devices that run Windows Phone 8.1 and later</span></span>
* <span data-ttu-id="b8089-110">Dispositivos registrados que executam o Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="b8089-110">Enrolled devices that run Windows 10 desktop</span></span>
* <span data-ttu-id="b8089-111">Dispositivos que executam o Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="b8089-111">Device that run Windows 10 Mobile</span></span>

<span data-ttu-id="b8089-112">Esse tipo de política pode ser útil quando as políticas de VPN padrão do Intune não contêm as configurações que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="b8089-112">This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.</span></span>

## <span data-ttu-id="b8089-113">Para criar uma política de configuração personalizada:</span><span class="sxs-lookup"><span data-stu-id="b8089-113">To create a custom configuration policy:</span></span>
<a id="to-create-a-custom-configuration-policy" class="xliff"></a>

   1. <span data-ttu-id="b8089-114">No [console de administração do Intune](https://manage.microsoft.com), escolha **Política** > **Adicionar Política** > *Expandir plataforma* > **Configuração personalizada** > **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="b8089-114">In the [Intune admin console](https://manage.microsoft.com), choose **Policy** > **Add Policy** > *Expand platform* > **Custom configuration** > **Create Policy**.</span></span>
   2. <span data-ttu-id="b8089-115">Insira um nome para a política.</span><span class="sxs-lookup"><span data-stu-id="b8089-115">Enter a name for the policy.</span></span>
   3. <span data-ttu-id="b8089-116">Para cada configuração de URI que você deseja especificar, escolha **Adicionar** e forneça as informações solicitadas.</span><span class="sxs-lookup"><span data-stu-id="b8089-116">For each URI setting you want to specify, choose **Add**, and provide the requested information.</span></span> <span data-ttu-id="b8089-117">Aqui está um exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8089-117">Here's an example:</span></span>

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](./media/Intune_Add_VPN_URI.png)

   4.  <span data-ttu-id="b8089-119">Depois de inserir todas as configurações de URI, selecione **Salvar política** e implante a política.</span><span class="sxs-lookup"><span data-stu-id="b8089-119">After you've entered all of URI settings, choose **Save policy**, and then deploy the policy.</span></span>

<span data-ttu-id="b8089-120">Em seguida, [implante a política](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) como de costume.</span><span class="sxs-lookup"><span data-stu-id="b8089-120">Then, [deploy the policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) as normal.</span></span>

## <span data-ttu-id="b8089-121">Configurações de URI de exemplo</span><span class="sxs-lookup"><span data-stu-id="b8089-121">Example URI settings</span></span>
<a id="example-uri-settings" class="xliff"></a>

<span data-ttu-id="b8089-122">Essas configurações podem ser usadas para criar uma configuração personalizada para uma VPN em uma empresa fictícia chamada Contoso.</span><span class="sxs-lookup"><span data-stu-id="b8089-122">These settings can be used to create a custom configuration for a VPN in a fictitious company called Contoso.</span></span>
<span data-ttu-id="b8089-123">Para obter detalhes completos sobre todas as configurações que podem ser usadas, consulte [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx) (CSP de VPNv2).</span><span class="sxs-lookup"><span data-stu-id="b8089-123">For full details about all the settings you can use, see [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).</span></span>

<span data-ttu-id="b8089-124">**VPN nativa da Contoso (IKEv2):**</span><span class="sxs-lookup"><span data-stu-id="b8089-124">**Native Contoso VPN (IKEv2):**</span></span><br />
<span data-ttu-id="b8089-125">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers</span><span class="sxs-lookup"><span data-stu-id="b8089-125">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers</span></span>

<span data-ttu-id="b8089-126">**vpn.contoso.com**</span><span class="sxs-lookup"><span data-stu-id="b8089-126">**vpn.contoso.com**</span></span><br />
<span data-ttu-id="b8089-127">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType</span><span class="sxs-lookup"><span data-stu-id="b8089-127">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType</span></span>

<span data-ttu-id="b8089-128">**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType</span><span class="sxs-lookup"><span data-stu-id="b8089-128">**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType</span></span>

<span data-ttu-id="b8089-129">**SplitTunnel**</span><span class="sxs-lookup"><span data-stu-id="b8089-129">**SplitTunnel**</span></span><br />
<span data-ttu-id="b8089-130">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod</span><span class="sxs-lookup"><span data-stu-id="b8089-130">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod</span></span>

<span data-ttu-id="b8089-131">**EAP**</span><span class="sxs-lookup"><span data-stu-id="b8089-131">**Eap**</span></span><br />
<span data-ttu-id="b8089-132">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration</span><span class="sxs-lookup"><span data-stu-id="b8089-132">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration</span></span>
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
<span data-ttu-id="b8089-133">**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**</span><span class="sxs-lookup"><span data-stu-id="b8089-133">**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**</span></span><br />
<span data-ttu-id="b8089-134">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b8089-134">True</span></span>

<span data-ttu-id="b8089-135">**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**</span><span class="sxs-lookup"><span data-stu-id="b8089-135">**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**</span></span><br />
<span data-ttu-id="b8089-136">1</span><span class="sxs-lookup"><span data-stu-id="b8089-136">1</span></span>

<span data-ttu-id="b8089-137">**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**</span><span class="sxs-lookup"><span data-stu-id="b8089-137">**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**</span></span><br />
<span data-ttu-id="b8089-138">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8089-138">Corp.Contoso.com</span></span>

<span data-ttu-id="b8089-139">**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**</span><span class="sxs-lookup"><span data-stu-id="b8089-139">**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**</span></span><br />
<span data-ttu-id="b8089-140">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8089-140">Corp.Contoso.com</span></span>

<span data-ttu-id="b8089-141">**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**</span><span class="sxs-lookup"><span data-stu-id="b8089-141">**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**</span></span><br />
<span data-ttu-id="b8089-142">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8089-142">Corp.Contoso.com</span></span>

<span data-ttu-id="b8089-143">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**</span><span class="sxs-lookup"><span data-stu-id="b8089-143">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**</span></span><br />
<span data-ttu-id="b8089-144">10.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b8089-144">10.0.0.0</span></span>

<span data-ttu-id="b8089-145">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**</span><span class="sxs-lookup"><span data-stu-id="b8089-145">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**</span></span><br />
<span data-ttu-id="b8089-146">8</span><span class="sxs-lookup"><span data-stu-id="b8089-146">8</span></span>

<span data-ttu-id="b8089-147">**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="b8089-147">**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**</span></span><br />
<span data-ttu-id="b8089-148">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b8089-148">true</span></span>

<span data-ttu-id="b8089-149">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**</span><span class="sxs-lookup"><span data-stu-id="b8089-149">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**</span></span><br />
<span data-ttu-id="b8089-150">%PROGRAMFILES%\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="b8089-150">%PROGRAMFILES%\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="b8089-151">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**</span><span class="sxs-lookup"><span data-stu-id="b8089-151">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**</span></span><br />
<span data-ttu-id="b8089-152">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="b8089-152">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="b8089-153">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**</span><span class="sxs-lookup"><span data-stu-id="b8089-153">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**</span></span><br />
<span data-ttu-id="b8089-154">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="b8089-154">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span></span>

<span data-ttu-id="b8089-155">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**</span><span class="sxs-lookup"><span data-stu-id="b8089-155">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**</span></span><br />
<span data-ttu-id="b8089-156">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="b8089-156">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="b8089-157">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**</span><span class="sxs-lookup"><span data-stu-id="b8089-157">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**</span></span><br />
<span data-ttu-id="b8089-158">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="b8089-158">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span></span>

<span data-ttu-id="b8089-159">Em caso de dúvidas sobre como usar essas configurações ou para obter mais detalhes sobre o que elas fazem, confira a [documentação do Provedor de Serviço de Configuração](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="b8089-159">For any questions about how these settings should be used or more details about what they do, customers should refer to the [configuration service provider (CSP) documentation](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).</span></span>

## <span data-ttu-id="b8089-160">Configurações de URI para VPN por aplicativo Android em PulseSecure</span><span class="sxs-lookup"><span data-stu-id="b8089-160">URI settings for Android per-app VPN on PulseSecure</span></span>
<a id="uri-settings-for-android-per-app-vpn-on-pulsesecure" class="xliff"></a>
### <span data-ttu-id="b8089-161">URI PERSONALIZADO PARA LISTA DE PACOTES</span><span class="sxs-lookup"><span data-stu-id="b8089-161">CUSTOM URI FOR PACKAGE LIST</span></span>
<a id="custom-uri-for-package-list" class="xliff"></a>
-  <span data-ttu-id="b8089-162">Tipo de dados = Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b8089-162">Data type = String</span></span>
-  <span data-ttu-id="b8089-163">OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList</span><span class="sxs-lookup"><span data-stu-id="b8089-163">OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList</span></span>
-  <span data-ttu-id="b8089-164">Valor = lista de pacotes separados por delimitador.</span><span class="sxs-lookup"><span data-stu-id="b8089-164">Value = Delimiter separated package list.</span></span>
   - <span data-ttu-id="b8089-165">Delimitadores: ponto e vírgula (;), dois pontos (:), vírgula (,), barra vertical (|)</span><span class="sxs-lookup"><span data-stu-id="b8089-165">Delimiters:  semicolon (;), colon (:), comma (,), Pipe (|)</span></span>

<span data-ttu-id="b8089-166">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="b8089-166">Examples:</span></span>
- <span data-ttu-id="b8089-167">com.android.chrome</span><span class="sxs-lookup"><span data-stu-id="b8089-167">com.android.chrome</span></span>
- <span data-ttu-id="b8089-168">com.android.chrome;com.android.browser</span><span class="sxs-lookup"><span data-stu-id="b8089-168">com.android.chrome;com.android.browser</span></span>

### <span data-ttu-id="b8089-169">URI PERSONALIZADO PARA MODO (OPCIONAL)</span><span class="sxs-lookup"><span data-stu-id="b8089-169">CUSTOM URI FOR MODE (OPTIONAL)</span></span>
<a id="custom-uri-for-mode-optional" class="xliff"></a>
- <span data-ttu-id="b8089-170">Tipo de Dados = Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b8089-170">Data Type = String</span></span>
- <span data-ttu-id="b8089-171">OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode</span><span class="sxs-lookup"><span data-stu-id="b8089-171">OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode</span></span>

> <span data-ttu-id="b8089-172">Anotações</span><span class="sxs-lookup"><span data-stu-id="b8089-172">Notes</span></span>
> - <span data-ttu-id="b8089-173">Usar o mesmo *nome* que você atribuiu ao perfil personalizado</span><span class="sxs-lookup"><span data-stu-id="b8089-173">Use the same *name* that you assigned to the custom profile</span></span>
> - <span data-ttu-id="b8089-174">Valores possíveis: *GLOBAL*, *LISTA DE PERMISSÕES*, *LISTA DE BLOQUEIOS*</span><span class="sxs-lookup"><span data-stu-id="b8089-174">Possible values: *GLOBAL*, *WHITELIST*, *BLACKLIST*</span></span>
> - <span data-ttu-id="b8089-175">O padrão será *GLOBAL* se nenhum PackageList for fornecido (compatibilidade com versões anteriores com perfis de todo o sistema)</span><span class="sxs-lookup"><span data-stu-id="b8089-175">Defaults to *GLOBAL* if no PackageList is provided (backward compatibility with system-wide profiles)</span></span>
> - <span data-ttu-id="b8089-176">O padrão será *LISTA DE PERMISSÕES* se for fornecido um PackageList</span><span class="sxs-lookup"><span data-stu-id="b8089-176">Defaults to *WHITELIST* if a PackageList is provided</span></span>


### <span data-ttu-id="b8089-177">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b8089-177">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="b8089-178">Conexões VPN no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b8089-178">VPN connections in Microsoft Intune</span></span>](vpn-connections-in-microsoft-intune.md)
