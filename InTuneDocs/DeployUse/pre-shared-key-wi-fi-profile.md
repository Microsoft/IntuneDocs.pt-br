---
title: Wi-Fi usando PSK | Microsoft Intune
description: "Use a Configuração Personalizada do Azure para criar um perfil de Wi-Fi com uma chave pré-compartilhada."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8fe47a5843414fbe4add7f77df63c0d6466273cd
ms.openlocfilehash: f15fce6890d6e5850d12115a97bf7331ce515508



---
# Para criar um perfil de Wi-Fi com uma chave pré-compartilhada
Veja aqui como usar a **Configuração Personalizada** do Azure para criar um perfil de Wi-Fi com uma chave pré-compartilhada. Este tópico também apresenta um exemplo de como criar um perfil de Wi-Fi baseado em EAP.

Observação:
-   Talvez seja mais fácil copiar o código de um computador que se conecta à rede, conforme descrito abaixo.
- Para o Android, você também tem a opção de usar este [Gerador de PSK de Android](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) fornecido por Johnathon Biersack.
-   Você pode adicionar várias redes e chaves acrescentando mais Configurações OMA-URI.
-  Para iOS, use o Apple Configurator em uma estação Mac para configurar o perfil. Outra opção é usar este [Gerador de Configuração Móvel de PSK de iOS](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) fornecido por Johnathon Biersack.


1.  Para criar um perfil de Wi-Fi com uma chave pré-compartilhada para Android ou Windows, ou um perfil de Wi-Fi baseado em EAP, ao criar uma política, escolha **Configuração Personalizada** em vez de um perfil de Wi-Fi para a plataforma do dispositivo em questão.

2.  Forneça um nome e uma descrição.
3.  Adicione uma nova configuração de OMA-URI:

   a.   Insira um nome para esta configuração de rede Wi-Fi.

   b.   Insira uma descrição da configuração de OMA-URI ou deixe em branco.

   c.   **Tipo de Dados**: defina isso como "String(XML)"

   d.   **OMA-URI**: 
        
- **Para Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
- **Para Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

Observação: lembre-se de incluir o caractere de ponto no início.

SSID é o SSID para o qual você está criando a política. Por exemplo,
`./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  e.    Campo de Valor: é aqui que você cola o código XML. Veja este exemplo. Cada valor deve ser adaptado às suas configurações de rede. Consulte a seção de comentários do código para ver algumas dicas.


    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
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

## Perfil de Wi-Fi baseado em EAP
Aqui está um exemplo de código XML de um perfil de Wi-Fi baseado em EAP:

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

4.  Clique em OK, salve e implante a política.
Observação. Essa política só pode ser implantada para grupos de usuários

Na próxima vez em que cada dispositivo fizer check-in, a política será aplicada e um perfil de Wi-Fi será criado no dispositivo. O dispositivo poderá conectar-se à rede automaticamente.
## Criar o arquivo XML de uma conexão Wi-Fi existente
Você também pode criar o arquivo XML de uma conexão Wi-Fi existente:
1.     Em um computador que está conectado ou recentemente foi conectado à rede sem fio, abra a seguinte pasta: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}. É melhor usar um computador não conectado a várias redes sem fio, pois você precisará pesquisar em cada perfil para encontrar o correto.
3.     Pesquise nos arquivos XML para localizar aquele com o nome correto.
4.     Depois de localizar o arquivo XML correto, copie e cole o código XML no campo de Dados da página de configurações de OMA-URI.

## Implantar a política

1.  No espaço de trabalho **Política** , selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos ao qual você deseja implantar a política, clique **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - clique em **Cancelar**.

Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.

### Consulte também
[Conexões Wi-Fi no Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


