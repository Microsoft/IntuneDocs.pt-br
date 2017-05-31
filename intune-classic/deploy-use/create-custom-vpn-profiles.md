---
title: "Configurações personalizadas para perfis VPN do Microsoft Intune | Microsoft Docs"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5216730e9736ff4b20abfb19058e82b995d82813
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Configurações personalizadas para perfis VPN do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Criar uma configuração personalizada
É possível usar políticas de configuração personalizada do Intune para criar perfis VPN para:

* Dispositivos que executam o Android 4 e posterior
* Dispositivos Android for Work
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Dispositivos que executam o Windows Phone 8.1 e versões posteriores
* Dispositivos registrados que executam o Windows 10 Desktop
* Dispositivos que executam o Windows 10 Mobile

Esse tipo de política pode ser útil quando as políticas de VPN padrão do Intune não contêm as configurações que você deseja usar.

## <a name="to-create-a-custom-configuration-policy"></a>Para criar uma política de configuração personalizada:

   1. No [console de administração do Intune](https://manage.microsoft.com), escolha **Política** > **Adicionar Política** > *Expandir plataforma* > **Configuração personalizada** > **Criar Política**.
   2. Insira um nome para a política.
   3. Para cada configuração de URI que você deseja especificar, escolha **Adicionar** e forneça as informações solicitadas. Aqui está um exemplo:

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](./media/Intune_Add_VPN_URI.png)

   4.  Depois de inserir todas as configurações de URI, selecione **Salvar política** e implante a política.

Em seguida, [implante a política](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) como de costume.

## <a name="example-uri-settings"></a>Configurações de URI de exemplo

Essas configurações podem ser usadas para criar uma configuração personalizada para uma VPN em uma empresa fictícia chamada Contoso.
Para obter detalhes completos sobre todas as configurações que podem ser usadas, consulte [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx) (CSP de VPNv2).

**VPN nativa da Contoso (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**EAP**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
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
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
verdadeiro

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
verdadeiro

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Em caso de dúvidas sobre como usar essas configurações ou para obter mais detalhes sobre o que elas fazem, confira a [documentação do Provedor de Serviço de Configuração](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

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


### <a name="see-also"></a>Consulte também
[Conexões VPN no Microsoft Intune](vpn-connections-in-microsoft-intune.md)

