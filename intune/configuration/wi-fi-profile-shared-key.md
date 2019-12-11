---
title: Criar perfil de Wi-Fi com chave pré-compartilhada no Microsoft Intune – Azure | Microsoft Docs
description: Use um perfil personalizado para criar um perfil de Wi-Fi com uma chave pré-compartilhada e obtenha um exemplo de código XML para perfis de Wi-Fi baseados em EAP, Android e Windows no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 02d1311be0943d93f80f2f5a1c3f421d476af1e5
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059836"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key-in-intune"></a>Use um perfil de dispositivo personalizado para criar um perfil de Wi-Fi com uma chave pré-compartilhada no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

As PSK (chaves pré-compartilhadas), normalmente, são usadas para autenticar usuários em redes Wi-Fi ou em LANs sem fio. Com o Intune, é possível criar um perfil de WiFi usando uma chave pré-compartilhada. Para criar o perfil, use o recurso **Perfis de dispositivo personalizados** no Intune. Este artigo também inclui alguns exemplos de como criar um perfil de Wi-Fi baseado em EAP.

Esse recurso é compatível com:

- Android
- Windows
- Wi-Fi baseado em EAP

> [!IMPORTANT]
> - Usar uma chave pré-compartilhada com Windows 10 faz com que um erro de correção seja exibido no Intune. Quando isso acontece, o perfil de Wi-Fi é adequadamente atribuído ao dispositivo, e o perfil funciona conforme o esperado.
> - Se você exportar um perfil de Wi-Fi que inclua uma chave pré-compartilhada, o arquivo deverá estar protegido. A chave está em texto sem formatação, portanto, é sua responsabilidade protegê-la.

## <a name="before-you-begin"></a>Antes de começar

- Talvez seja mais fácil copiar o código de um computador que se conecta a essa rede, conforme será descrito mais adiante neste artigo.
- Você pode adicionar várias redes e chaves acrescentando mais Configurações OMA-URI.
- Para iOS, use o Apple Configurator em uma estação Mac para configurar o perfil.
- PSK requer uma cadeia de caracteres de 64 dígitos hexadecimais ou uma frase secreta de 8 a 63 caracteres ASCII imprimíveis. Alguns caracteres, como o asterisco (*), não são permitidos.

## <a name="create-a-custom-profile"></a>Criar um perfil personalizado

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política é **Configurações personalizadas de perfil de Wi-Fi do OMA-URI para dispositivos Android**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha sua plataforma.
    - **Tipo de perfil**: Selecione **Personalizado**.

4. Em **Configurações**, selecione **Adicionar**. Insira uma nova configuração de OMA-URI com as seguintes propriedades:

    1. **Nome**: Insira um nome para a configuração de OMA-URI.
    2. **Descrição**: Insira uma descrição para a configuração de OMA-URI. Essa configuração é opcional, mas recomendada.
    3. **OMA-URI**: Insira uma das seguintes opções:

        - **Para Android**: `./Vendor/MSFT/WiFi/Profile/SSID/Settings`
        - **Para Windows**: `./Vendor/MSFT/WiFi/Profile/SSID/WlanXml`

        > [!NOTE]
        > Lembre-se de incluir o caractere de ponto no início.

        SSID é o SSID para o qual você está criando a política. Por exemplo, se o Wi-Fi chama-se `Hotspot-1`, insira `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

    4. **Tipo de dados**: Selecione **Cadeia de caracteres**.

    5. **Valor**: Cole seu código XML. Veja os [exemplos](#android-or-windows-wi-fi-profile-example) neste artigo. Atualize cada valor de acordo com as suas configurações de rede. A seção de comentários do código inclui alguns ponteiros.

5. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

Seu perfil será mostrado na lista de perfis. Em seguida, [atribua este perfil](../device-profile-assign.md) a seus grupos de usuários. Esta política só pode ser atribuída a grupos de usuários.

Na próxima vez em que cada dispositivo fizer check-in, a política será aplicada e será criado um perfil de Wi-Fi no dispositivo. Assim, o dispositivo poderá se conectar à rede automaticamente.

## <a name="android-or-windows-wi-fi-profile-example"></a>Exemplo de perfil de Wi-Fi do Windows ou do Android

O exemplo a seguir inclui o código XML para um perfil de Wi-Fi do Windows ou do Android. O exemplo é fornecido para mostrar o formato adequado e fornecer mais detalhes. Ele é apenas um exemplo e não se destina como uma configuração recomendada para o seu ambiente.

### <a name="what-you-need-to-know"></a>O que você precisa saber

- `<protected>false</protected>` precisa ser definido como **false**. Quando for **true**, poderá fazer com que o dispositivo espere uma senha criptografada e tente descriptografá-la, podendo resultar em uma falha na conexão.

- `<hex>53534944</hex>` deve ser definido como o valor hexadecimal de `<name><SSID of wifi profile></name>`. Os dispositivos Windows 10 podem retornar um erro `x87D1FDE8 Remediation failed` falso, mas o dispositivo ainda contém o perfil.

- XML tem caracteres especiais, como o `&` (e comercial). O uso de caracteres especiais pode impedir o funcionamento esperado do XML. 

### <a name="example"></a>Exemplo

``` xml
<!--
<hex>53534944</hex> = The hexadecimal value of <name><SSID of wifi profile></name>
<Name of wifi profile> = Name of profile shown to users. It could be <name>Your Company's Network</name>.
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped. It could be <name>Your Company's Network</name>.
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network, such as AES.
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Plain text of the password to connect to the network
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
        <keyType>passPhrase</keyType>
        <protected>false</protected>
        <keyMaterial>password</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

### <a name="eap-based-wi-fi-profile-example"></a>Exemplo de perfil de Wi-Fi baseado em EAP
O exemplo a seguir inclui o código XML para um perfil de Wi-Fi baseado em EAP: O exemplo é fornecido para mostrar o formato adequado e fornecer mais detalhes. Ele é apenas um exemplo e não se destina como uma configuração recomendada para o seu ambiente.


```xml
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

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Criar o arquivo XML de uma conexão Wi-Fi existente

Você também pode criar o arquivo XML de uma conexão Wi-Fi existente. Em um computador com Windows, use as seguintes etapas:

1. Crie uma pasta local para os perfis Wi-Fi exportados, como c:\WiFi.
2. Abra um prompt de comando como administrador (clique com o botão direito do mouse em `cmd` > **Executar como administrador**).
3. Execute `netsh wlan show profiles`. Os nomes de todos os perfis são listados.
4. Execute `netsh wlan export profile name="YourProfileName" folder=c:\Wifi`. Este comando cria um arquivo chamado `Wi-Fi-YourProfileName.xml` em c:\Wifi.

    - Se você está exportando um perfil de Wi-Fi que inclui uma chave pré-compartilhada, adicione `key=clear` ao comando:
  
        `netsh wlan export profile name="YourProfileName" key=clear folder=c:\Wifi`

        `key=clear` exporta a chave em texto sem formatação, o que é necessário para usar o perfil com êxito.

Já com o arquivo XML, copie e cole a sintaxe XML em configurações OMA-URI > **Tipo de dados**. [Criar um perfil personalizado](#create-a-custom-profile) (neste artigo) lista as etapas.

> [!TIP]
> `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}` também inclui todos os perfis no formato XML.

## <a name="best-practices"></a>Práticas recomendadas

- Antes de implantar um perfil de Wi-Fi com a PSK, confirme se o dispositivo pode se conectar ao ponto de extremidade diretamente.

- Ao trocar chaves (senhas ou frases secretas), espere o tempo de inatividade e planeje as implantações. Considere enviar por push novos perfis de Wi-Fi durante horário não comercial. Além disso, avise os usuários que a conectividade pode ser afetada.

- Para uma transição suave, verifique se o dispositivo do usuário final tem uma conexão alternativa com a Internet. Por exemplo, o usuário final deve poder voltar para o Wi-Fi de convidado (ou alguma outra rede Wi-Fi) ou ter conectividade celular para se comunicar com o Intune. A conexão adicional permite que o usuário receba atualizações de política enquanto o perfil de WiFi corporativo está sendo atualizado no dispositivo.

## <a name="next-steps"></a>Próximas etapas

Lembre-se de [atribuir o perfil](device-profile-assign.md) e de [monitorar](device-profile-monitor.md) o status dele.
