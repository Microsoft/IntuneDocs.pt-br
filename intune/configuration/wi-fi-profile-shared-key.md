---
title: Criar perfil de WiFi com chave pré-compartilhada – Microsoft Intune – Azure | Microsoft Docs
description: Use um perfil personalizado para criar um perfil de Wi-Fi com uma chave pré-compartilhada e obtenha um exemplo de código XML para perfis de Wi-Fi baseados em EAP, Android e Windows no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 175be4d51b034745ce6fab050f68be277f1d4858
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723756"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key---intune"></a>Use um perfil de dispositivo personalizado para criar um perfil de WiFi com uma chave pré-compartilhada – Intune
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

As PSK (chaves pré-compartilhadas) normalmente são usadas para autenticar usuários em redes WiFi ou em LANs sem fio. Com o Intune, é possível criar um perfil de WiFi usando uma chave pré-compartilhada. Para criar o perfil, use o recurso **Perfis de dispositivo personalizados** no Intune. Este artigo também inclui alguns exemplos de como criar um perfil de Wi-Fi baseado em EAP.

> [!IMPORTANT]
>- Usar uma chave pré-compartilhada com Windows 10 faz com que um erro de correção apareça no Intune. Quando isso acontece, o perfil de Wi-Fi é adequadamente atribuído ao dispositivo, e o perfil funciona conforme o esperado.
>- Se você exportar um perfil de Wi-Fi que inclua uma chave pré-compartilhada, o arquivo deverá estar protegido. A chave está em texto sem formatação, portanto, é sua responsabilidade protegê-la.

## <a name="before-you-begin"></a>Antes de começar

- Talvez seja mais fácil copiar o código de um computador que se conecta a essa rede, conforme será descrito mais adiante neste artigo.
- Você pode adicionar várias redes e chaves acrescentando mais Configurações OMA-URI.
- Para iOS, use o Apple Configurator em uma estação Mac para configurar o perfil.
- PSK requer uma cadeia de caracteres de 64 dígitos hexadecimais ou uma frase secreta de 8 a 63 caracteres ASCII imprimíveis. Alguns caracteres, como o asterisco (*), não são permitidos.

## <a name="create-a-custom-profile"></a>Criar um perfil personalizado
É possível criar um perfil personalizado com uma chave pré-compartilhada para um perfil de Wi-Fi baseado em Android, Windows ou EAP. Para criar o perfil usando o portal do Azure, confira [Criar configurações personalizadas do dispositivo](custom-settings-configure.md). Ao criar o perfil de dispositivo, escolha **Personalizado** para a plataforma do dispositivo. Não selecione o perfil de WiFi. Ao escolher personalizado, certifique-se de: 

1. Inserir um nome e uma descrição do perfil.
2. Adicionar uma nova configuração de OMA-URI com as seguintes propriedades: 

   a. Insira um nome para esta configuração de rede Wi-Fi.

   b. (Opcional) Insira uma descrição da configuração do OMA-URI ou deixe em branco.

   c. Defina o **Tipo de Dados** como **Cadeia de Caracteres**.

   d. **OMA-URI**:

   - **Para Android**: ./Vendor/MSFT/WiFi/Profile/SSID/Settings
   - **Para Windows**: ./Vendor/MSFT/WiFi/Profile/SSID/WlanXml

     > [!NOTE]
     > Lembre-se de incluir o caractere de ponto no início.

     SSID é o SSID para o qual você está criando a política. Por exemplo, se o Wi-Fi chama-se `Hotspot-1`, insira `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

   e. **Campo de Valor** é onde você cola o código XML. Confira os exemplos neste artigo. Atualize cada valor de acordo com as suas configurações de rede. A seção de comentários do código inclui alguns ponteiros.
3. Selecione **OK**, salvar e, em seguida, atribua a política.

    > [!NOTE]
    > Esta política só pode ser atribuída a grupos de usuários.

Na próxima vez em que cada dispositivo fizer check-in, a política será aplicada e será criado um perfil de Wi-Fi no dispositivo. Assim, o dispositivo poderá se conectar à rede automaticamente.

## <a name="android-or-windows-wi-fi-profile-example"></a>Exemplo de perfil de Wi-Fi do Windows ou do Android

O exemplo a seguir inclui o código XML para um perfil de Wi-Fi do Windows ou do Android. O exemplo é fornecido para mostrar o formato adequado e fornecer mais detalhes. Ele é apenas um exemplo e não se destina como uma configuração recomendada para o seu ambiente.

### <a name="important-considerations"></a>Considerações importantes

- `<protected>false</protected>` precisa ser definido como **false**. Quando for **true**, poderá fazer com que o dispositivo espere uma senha criptografada e tente descriptografá-la, podendo resultar em uma falha na conexão.

- `<hex>53534944</hex>` deve ser definido como o valor hexadecimal de `<name><SSID of wifi profile></name>`. Os dispositivos Windows 10 podem retornar um erro `x87D1FDE8 Remediation failed` falso, mas o dispositivo ainda conterá o perfil.

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

## <a name="eap-based-wi-fi-profile-example"></a>Exemplo de perfil de Wi-Fi baseado em EAP
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
2. Abra um prompt de comando como administrador (clique com o botão direito do mouse em `cmd` > **Executar como administrador**)
3. Execute `netsh wlan show profiles`. Os nomes de todos os perfis são listados.
4. Execute `netsh wlan export profile name="YourProfileName" folder=c:\Wifi`. Este comando cria um arquivo chamado `Wi-Fi-YourProfileName.xml` em c:\Wifi.

    - Se você está exportando um perfil de Wi-Fi que contém uma chave pré-compartilhada, adicione `key=clear` ao comando:
  
      `netsh wlan export profile name="YourProfileName" key=clear folder=c:\Wifi`

      `key=clear` exporta a chave em texto sem formatação, o que é necessário para usar o perfil com êxito.

Já com o arquivo XML, copie e cole a sintaxe XML em configurações OMA-URI > **Tipo de dados**. [Criar um perfil personalizado](#create-a-custom-profile) (neste artigo) lista as etapas.

> [!TIP]
> `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}` também inclui todos os perfis no formato XML.

## <a name="best-practices"></a>Práticas recomendadas

- Antes de implantar um perfil de Wi-Fi com a PSK, confirme se o dispositivo pode se conectar ao ponto de extremidade diretamente.

- Ao trocar as chaves (senhas ou frases secretas), espere um tempo de inatividade e planeje as implantações. Considere enviar por push novos perfis de Wi-Fi durante horário não comercial. Além disso, avise os usuários que a conectividade pode ser afetada.

- Para uma transição suave, verifique se o dispositivo do usuário final tem uma conexão alternativa com a Internet. Por exemplo, o usuário final deve ser capaz de voltar para o Wi-Fi de convidado (ou alguma outra rede Wi-Fi) ou ter conectividade celular para se comunicar com o Intune. A conexão adicional permite que o usuário receba atualizações de política enquanto o perfil de WiFi corporativo está sendo atualizado no dispositivo.
