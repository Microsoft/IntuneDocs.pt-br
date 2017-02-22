---
title: Como criar perfis VPN personalizados com o Microsoft Intune | Microsoft Docs
description: "Use configurações personalizadas para criar perfis de VPN no Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: e92593062ad2ed7a4098922715106f47f4e78d4f


---

# <a name="how-to-create-custom-vpn-profiles-with-microsoft-intune"></a>Como criar perfis VPN personalizados com o Microsoft Intune

## <a name="create-a-custom-configuration"></a>Criar uma configuração personalizada
É possível usar políticas de configuração personalizada do Intune para criar perfis VPN para:

* Dispositivos que executam o Android 4 e posterior
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Dispositivos que executam o Windows Phone 8.1 e versões posteriores
* Dispositivos registrados que executam o Windows 10 Desktop 
* Dispositivos que executam o Windows 10 Mobile

Esse tipo de política pode ser útil quando as políticas de VPN padrão do Intune não contêm as configurações que você deseja usar.

## <a name="to-create-a-custom-configuration-policy"></a>Para criar uma política de configuração personalizada:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
5. Na folha de perfis, escolha **Criar Perfil**.
6. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de VPN.
7. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo personalizado:
    - **Android**
    - **iOS** (configurado usando um arquivo exportado do Apple Configurator).
    - **macOS** (configurado usando um arquivo exportado do Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.
7. Na folha **Configurações personalizadas de OMA-URI**, para cada configuração de URI que você deseja especificar, escolha **Adicionar**, forneça as informações solicitadas e escolha **OK**. Aqui está um exemplo:

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](./media/Intune_Add_VPN_URI.png)

4.  Depois de inserir todas as configurações de URI necessárias, escolha **OK** e, em seguida, na folha **Criar Perfil**, escolha **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).

## <a name="example-uri-settings"></a>Configurações de URI de exemplo

Essas configurações podem ser usadas para criar uma configuração personalizada para uma VPN em uma empresa fictícia chamada Contoso.
Para obter detalhes completos sobre todas as configurações que podem ser usadas, consulte [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx) (CSP de VPNv2).

VPN de Contoso nativa (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Para solucionar dúvidas sobre como essas configurações devem ser usadas ou obter mais detalhes sobre o que elas fazem, os clientes devem consultar a documentação do CSP (provedor de serviços de configuração): https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>Configurações de URI para VPN por aplicativo Android em PulseSecure
### <a name="custom-uri-for-package-list"></a>URI PERSONALIZADO PARA LISTA DE PACOTES
-  Tipo de dados = Cadeia de caracteres
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Valor = lista de pacotes separados por delimitador.
   - Delimitadores: ponto e vírgula (;), dois pontos (:), vírgula (,), barra vertical (|)

Exemplos:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>URI PERSONALIZADO PARA MODO (OPCIONAL)
- Tipo de Dados = Cadeia de caracteres
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Anotações
> - Usar o mesmo *nome* que você atribuiu ao perfil personalizado
> - Valores possíveis: *GLOBAL*, *LISTA DE PERMISSÕES*, *LISTA DE BLOQUEIOS*
> - O padrão será *GLOBAL* se nenhum PackageList for fornecido (compatibilidade com versões anteriores com perfis de todo o sistema)
> - O padrão será *LISTA DE PERMISSÕES* se for fornecido um PackageList






<!--HONumber=Feb17_HO1-->


