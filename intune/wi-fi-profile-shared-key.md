---
title: "Para criar um perfil de Wi-Fi com uma chave pré-compartilhada"
titleSuffix: Intune on Azure
description: "Use um perfil personalizado do Intune para criar um perfil de Wi-Fi com uma chave pré-compartilhada."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b56a6da04ae53a812a7d153de2618b72fa14ec44
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="53f3a-103">Use um perfil de dispositivo personalizado do Microsoft Intune para criar um perfil de Wi-Fi com uma chave pré-compartilhada</span><span class="sxs-lookup"><span data-stu-id="53f3a-103">Use a Microsoft Intune custom device profile to create a Wi-Fi profile with a pre-shared key</span></span>
<a id="use-a-microsoft-intune-custom-device-profile-to-create-a-wi-fi-profile-with-a-pre-shared-key" class="xliff"></a>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="53f3a-104">Veja aqui como usar os **Perfis de dispositivos personalizados** do Intune para criar um perfil de Wi-Fi com uma chave pré-compartilhada.</span><span class="sxs-lookup"><span data-stu-id="53f3a-104">Here's how to use Intune’s **Custom device profiles** to create a Wi-Fi profile with a pre-shared key.</span></span> <span data-ttu-id="53f3a-105">Este tópico também apresenta um exemplo de como criar um perfil de Wi-Fi baseado em EAP.</span><span class="sxs-lookup"><span data-stu-id="53f3a-105">This topic also has an example of how to create an EAP-based Wi-Fi profile.</span></span>

> [!NOTE]
-   <span data-ttu-id="53f3a-106">Talvez seja mais fácil copiar o código de um computador que se conecta à rede, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="53f3a-106">You might find it easier to copy the code from a computer that connects to that network, as described below.</span></span>
- <span data-ttu-id="53f3a-107">Para o Android, você também tem a opção de usar este [Gerador de PSK de Android](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) fornecido por Johnathon Biersack.</span><span class="sxs-lookup"><span data-stu-id="53f3a-107">For Android, you also have the option of using this [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) provided by Johnathon Biersack.</span></span>
-   <span data-ttu-id="53f3a-108">Você pode adicionar várias redes e chaves acrescentando mais Configurações OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="53f3a-108">You can add multiple networks and keys by adding more OMA-URI settings.</span></span>
-  <span data-ttu-id="53f3a-109">Para iOS, use o Apple Configurator em uma estação Mac para configurar o perfil.</span><span class="sxs-lookup"><span data-stu-id="53f3a-109">For iOS, use Apple Configurator on a Mac station to set up the profile.</span></span> <span data-ttu-id="53f3a-110">Outra opção é usar este [Gerador de Configuração Móvel de PSK de iOS](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) fornecido por Johnathon Biersack.</span><span class="sxs-lookup"><span data-stu-id="53f3a-110">Alternatively, use this [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) provided by Johnathon Biersack.</span></span>


1.  <span data-ttu-id="53f3a-111">Para criar um perfil de Wi-Fi com uma chave pré-compartilhada para Android ou Windows, ou um perfil de Wi-Fi baseado em EAP, ao criar um perfil de dispositivo, escolha **Personalizado** para a plataforma do dispositivo em vez do perfil de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="53f3a-111">To create a Wi-Fi profile with a pre-shared key for Android or Windows or an EAP-based Wi-Fi profile, when you create a device profile choose **Custom** for that device platform rather than a Wi-Fi profile.</span></span>

2.  <span data-ttu-id="53f3a-112">Forneça um nome e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="53f3a-112">Provide a name and description.</span></span>
3.  <span data-ttu-id="53f3a-113">Adicione uma nova configuração de OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="53f3a-113">Add a new OMA-URI setting:</span></span>

   <span data-ttu-id="53f3a-114">a.</span><span class="sxs-lookup"><span data-stu-id="53f3a-114">a.</span></span>   <span data-ttu-id="53f3a-115">Insira um nome para esta configuração de rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="53f3a-115">Enter a name for this Wi-Fi network setting.</span></span>

   <span data-ttu-id="53f3a-116">b.</span><span class="sxs-lookup"><span data-stu-id="53f3a-116">b.</span></span>   <span data-ttu-id="53f3a-117">Insira uma descrição da configuração de OMA-URI ou deixe em branco.</span><span class="sxs-lookup"><span data-stu-id="53f3a-117">Enter a description of the OMA-URI setting or leave blank.</span></span>

   <span data-ttu-id="53f3a-118">c.</span><span class="sxs-lookup"><span data-stu-id="53f3a-118">c.</span></span>   <span data-ttu-id="53f3a-119">**Tipo de Dados**: defina isso como **String**.</span><span class="sxs-lookup"><span data-stu-id="53f3a-119">**Data Type**: Set to **String**.</span></span>

   <span data-ttu-id="53f3a-120">d.</span><span class="sxs-lookup"><span data-stu-id="53f3a-120">d.</span></span>   <span data-ttu-id="53f3a-121">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="53f3a-121">**OMA-URI**:</span></span>

    - <span data-ttu-id="53f3a-122">**Para Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span><span class="sxs-lookup"><span data-stu-id="53f3a-122">**For Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span></span>
    - <span data-ttu-id="53f3a-123">**Para Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span><span class="sxs-lookup"><span data-stu-id="53f3a-123">**For Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span></span>

    > [!NOTE]
<span data-ttu-id="53f3a-124">Lembre-se de incluir o caractere de ponto no início.</span><span class="sxs-lookup"><span data-stu-id="53f3a-124">Be sure to include the dot character at the beginning.</span></span>

    <span data-ttu-id="53f3a-125">SSID é o SSID para o qual você está criando a política.</span><span class="sxs-lookup"><span data-stu-id="53f3a-125">SSID is the SSID for which you’re creating the policy.</span></span> <span data-ttu-id="53f3a-126">Por exemplo, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.</span><span class="sxs-lookup"><span data-stu-id="53f3a-126">For example, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span></span>

  <span data-ttu-id="53f3a-127">e.</span><span class="sxs-lookup"><span data-stu-id="53f3a-127">e.</span></span> <span data-ttu-id="53f3a-128">**Campo de Valor** é onde você cola o código XML.</span><span class="sxs-lookup"><span data-stu-id="53f3a-128">**Value Field** is where you paste your XML code.</span></span> <span data-ttu-id="53f3a-129">Veja este exemplo.</span><span class="sxs-lookup"><span data-stu-id="53f3a-129">Here’s an example.</span></span> <span data-ttu-id="53f3a-130">Cada valor deve ser adaptado às suas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="53f3a-130">Each value should be adapted to your network settings.</span></span> <span data-ttu-id="53f3a-131">Consulte a seção de comentários do código para ver algumas dicas.</span><span class="sxs-lookup"><span data-stu-id="53f3a-131">See the comments section of the code for some pointers.</span></span>
4. <span data-ttu-id="53f3a-132">Escolha **OK**, salve e atribua a política.</span><span class="sxs-lookup"><span data-stu-id="53f3a-132">Choose **OK**, save, and then assign the policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53f3a-133">Esta política só pode ser atribuída a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="53f3a-133">This policy can only be assigned to user groups.</span></span>

<span data-ttu-id="53f3a-134">Na próxima vez em que cada dispositivo fizer check-in, a política será aplicada e um perfil de Wi-Fi será criado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53f3a-134">The next time each device checks in, the policy will be applied, and a Wi-Fi profile will be created on the device.</span></span> <span data-ttu-id="53f3a-135">O dispositivo poderá conectar-se à rede automaticamente.</span><span class="sxs-lookup"><span data-stu-id="53f3a-135">The device will be able to connect to the network automatically.</span></span>

## <span data-ttu-id="53f3a-136">Perfil de Wi-Fi do Android ou do Windows</span><span class="sxs-lookup"><span data-stu-id="53f3a-136">Android or Windows Wi-Fi profile</span></span>
<a id="android-or-windows-wi-fi-profile" class="xliff"></a>

<span data-ttu-id="53f3a-137">Aqui está um exemplo de código XML de um perfil de Wi-Fi do Android ou do Windows:</span><span class="sxs-lookup"><span data-stu-id="53f3a-137">Here’s an example of the XML code for an Android or Windows Wi-Fi profile:</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="53f3a-138">`<protected>false</protected>`deve ser definido como **false**, pois **true** poderia fazer o dispositivo esperar uma senha criptografada e tentar descriptografá-la, o que poderia causar uma falha de conexão.</span><span class="sxs-lookup"><span data-stu-id="53f3a-138">`<protected>false</protected>`must be set to **false**, as **true** could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.</span></span>
>
>  <span data-ttu-id="53f3a-139">`<hex>53534944</hex>` deve ser definido como o valor hexadecimal de `<name><SSID of wifi profile></name>`.</span><span class="sxs-lookup"><span data-stu-id="53f3a-139">`<hex>53534944</hex>` should be set to the hexadecimal value of `<name><SSID of wifi profile></name>`.</span></span>
>  <span data-ttu-id="53f3a-140">Dispositivos Windows 10 podem retornar um erro falso *A correção 0x87D1FDE8 falhou*, mas ainda ser provisionado com o perfil.</span><span class="sxs-lookup"><span data-stu-id="53f3a-140">Windows 10 devices may return a false *0x87D1FDE8 Remediation failed* error, but will still be provisioned with the profile.</span></span>

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>networkKey</keyType>
        <protected>false</protected>
        <keyMaterial>MyPassword</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <span data-ttu-id="53f3a-141">Perfil de Wi-Fi baseado em EAP</span><span class="sxs-lookup"><span data-stu-id="53f3a-141">EAP-based Wi-Fi profile</span></span>
<a id="eap-based-wi-fi-profile" class="xliff"></a>
<span data-ttu-id="53f3a-142">Aqui está um exemplo de código XML de um perfil de Wi-Fi baseado em EAP:</span><span class="sxs-lookup"><span data-stu-id="53f3a-142">Here’s  an example of the XML code for an EAP-based Wi-Fi profile:</span></span>

```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <span data-ttu-id="53f3a-143">Criar o arquivo XML de uma conexão Wi-Fi existente</span><span class="sxs-lookup"><span data-stu-id="53f3a-143">Create the XML file from an existing Wi-Fi connection</span></span>
<a id="create-the-xml-file-from-an-existing-wi-fi-connection" class="xliff"></a>
<span data-ttu-id="53f3a-144">Você também pode criar o arquivo XML de uma conexão Wi-Fi existente:</span><span class="sxs-lookup"><span data-stu-id="53f3a-144">You can also create an XML file from an existing Wi-Fi connection:</span></span>
1. <span data-ttu-id="53f3a-145">Em um computador que está conectado ou recentemente foi conectado à rede sem fio, abra a seguinte pasta: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.</span><span class="sxs-lookup"><span data-stu-id="53f3a-145">On a computer that is connected to or has recently connected to the wireless network, open the following folder: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.</span></span>

    <span data-ttu-id="53f3a-146">É melhor usar um computador não conectado a várias redes sem fio, pois você precisará pesquisar em cada perfil para encontrar o correto.</span><span class="sxs-lookup"><span data-stu-id="53f3a-146">It’s best to use a computer that has not connected to many wireless networks, because you’ll have to search through each profile to find the right one.</span></span>
3.     <span data-ttu-id="53f3a-147">Pesquise nos arquivos XML para localizar aquele com o nome correto.</span><span class="sxs-lookup"><span data-stu-id="53f3a-147">Search through the XML files to locate the one with the right name.</span></span>
4.     <span data-ttu-id="53f3a-148">Depois de localizar o arquivo XML correto, copie e cole o código XML no campo de Dados da página de configurações de OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="53f3a-148">After you have located the correct XML file, copy and paste the XML code into the Data field of the OMA-URI settings page.</span></span>
