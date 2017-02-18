---
title: "Configurações da política do Windows 10 | Microsoft Docs"
description: "Use as configurações de política listadas neste tópico para ajudá-lo a definir configurações internas e personalizadas para dispositivos Windows 10 Mobile e Windows 10 Desktop registrados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 5a1a861096bdfae461b6ad05e424f770796279a2


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Configurações de política do Intune para dispositivos Windows 10 no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico contém informações para ajudá-lo a entender as configurações de política do Intune que você pode usar para gerenciar dispositivos Windows 10. Leia este tópico, bem como os procedimentos em [Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md), para definir configurações internas e personalizadas para dispositivos Windows 10 Desktop e Windows 10 Mobile registrados. Você não pode usar essas políticas com computadores que executam o [software de cliente do Intune PC](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Você pode escolher entre dois tipos de política:

- **Política Personalizada**: use a **política personalizada** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows 10 disponibiliza várias configurações por meio do [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Política de configuração geral**: Use esse tipo de política para selecionar as configurações da lista interna fornecida com o Microsoft Intune.

## <a name="custom-policy-settings"></a>Configurações de política personalizada

Forneça as seguintes configurações em uma política personalizada.

### <a name="general"></a>Geral

Insira um nome e uma descrição opcional para a política para ajudar a identificá-la no console do Intune.

### <a name="oma-uri-settings"></a>Configurações de OMA-URI

Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir. Use a [referência de configurações de URI do Windows 10](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) neste tópico para saber mais sobre as configurações que você pode usar:

- **Nome da configuração**: insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
- **Descrição da configuração**: opcionalmente, insira uma descrição para a configuração.
- **Tipo de dados**: escolha entre os seguintes tipos de dados:
    - **Cadeia de caracteres**
    - **Cadeia de caracteres (XML)**
    - **Data e hora**
    - **Inteiro**
    - **Ponto flutuante**
    - **Booliano**
- **OMA-URI (com distinção entre maiúsculas e minúsculas)**: especifique o OMA-URI para o qual você deseja fornecer uma configuração.
- **Valor**: especifique o valor para associar ao OMA-URI que você inseriu.

### <a name="example"></a>Exemplo
Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada. Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.

> ![Exemplo de política personalizada que contém configurações de VPN](./media/custom-policy-example.png)

## <a name="windows-10-uri-settings"></a>Configurações de URI do Windows 10
Use esta seção para saber mais sobre as configurações de OMA-URI que você pode configurar com uma **política personalizada do Windows 10**.

### <a name="policy"></a>Política

|Nome de política e URI|Detalhes|
|---------------|------------|-----------|
|**Permitir Atualização Automática**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Somente Área de trabalho<br>**Tipo de dados:** inteiro<br />**Valores:** **0** - **5** (padrão: **1**)|
|**Agendar Dia Para Instalação**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Somente dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Todos os dias (padrão)<br>**1** - domingo<br>**2** - segunda-feira<br>**3** - terça-feira<br>**4** - quarta-feira<br>**5** - quinta-feira<br>**6** - sexta-feira<br>**7** - Sábado|
|**Agendar Horário para Instalação**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** – **23** horas (**0** é meia-noite) (padrão: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – O usuário não pode definir o temporizador de período de carência de senha; o valor é definido como "sempre que"<br>**1** – O usuário pode definir o temporizador de período de carência de senha (padrão)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não permitir o **uso de conexão Wi-Fi**<br>**1** – permitir o **uso de conexão Wi-Fi** (padrão)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Área de trabalho e dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitir compartilhamento de Internet <br> **1** – permitir compartilhamento de Internet (padrão)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – permitir somente conexões Wi-Fi que podem ser configuradas com MDM.<br>**1** – é permitido adicionar novas SSIDs de rede, além de SSIDs que já tenham sido criadas pelo MDM (padrão)|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Área de trabalho e dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não permitido (configuração Enterprise somente)<br>**1** – Limitado<br>**2** – completo (padrão)<br>**3** - completo e informações de diagnóstico|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitido<br>**1**- Somente configurações (padrão)<br>**2**- configurações e experimentação|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitir modo AntiTheft<br>**1** – preferência do usuário (padrão)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br>**1** – permitido (padrão)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - a VPN não é permitida por celular<br>**1** – a VPN pode usar qualquer conexão, incluindo celular (padrão)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitir que o usuário ative o Bluetooth.<br>**1** – Reservado. O usuário pode ativar e configurar o Bluetooth (sem suporte no Windows Phone 8.1 para MDM, EAS, desktop Windows 10 Desktop ou Windows 10 Mobile).<br>**2** - Permitido. O usuário pode ativar e configurar o Bluetooth (padrão).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitir roaming<br> **1** – Permitir roaming (padrão)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** – Não permitido<br> **1** – permitido (padrão)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** – Não permitido<br> **1** – permitido (padrão)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** (padrão)<br> **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0**<br> **1** (padrão)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** (padrão)<br> **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** (padrão)<br> **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** (padrão)<br> **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0**<br> **1** (padrão)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** (padrão)<br> **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** (padrão)<br> **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não permitir.<br>O Open Extended Dictionary está desativado.<br>Um usuário não pode:<br>– Adicionar um novo Dicionário Estendido Aberto.<br />– Adicionar um novo arquivo de configuração de integração de pesquisa.<br>– Usar o recurso do candidato de nuvem.<br>-Enviar uma palavra registrada pelo usuário.<br>**1** - Permitir<br>O Open Extended Dictionary pode ser adicionado e usado por padrão. Além disso, a função de integração de pesquisa pode ser usada por padrão.<br>Um usuário pode:<br>– Usar o recurso do candidato de nuvem.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Registro em log de erros de conversão desativado<br>**1** - registro em log de erros de conversão ativado (padrão)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido <br>**1** – permitido (padrão)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres Shift JIS, são filtrados|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br />**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres JIS0208, são filtrados|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres JIS0208 ou EUDC, são filtrados|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Restrita, filtragem mais elevada contra conteúdo adulto<br>**1** – Moderada, filtragem moderada contra conteúdo somente para adultos (resultados da pesquisa válidos não serão filtrados) (padrão)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**Forçar Tamanho Inicial**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – permitir que o usuário altere o tamanho (padrão)<br>**1** – forçar tela não inteira<br>**2** – forçar tela inteira|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não adiar atualização (permanece no branch atual, CB) (padrão)<br>**1** – possibilitar que atualizações sejam adiadas (o dispositivo segue o branch atual para empresas, CBB e regras)<br />Para obter detalhes, consulte:<br>[Introdução à manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planejar a implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Área de trabalho e dispositivos móveis<br>**Descrição:** política para adiar atualizações de software por até 4 semanas<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** – aplicar atualizações imediatamente (padrão)<br>**1**-**4** – número de semanas pelo qual as atualizações de software serão adiadas<br />Para obter detalhes, consulte:<br>[Introdução à manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planejar a implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Área de trabalho e dispositivos móveis<br>**Descrição:** política para adiar atualizações de recursos por até 8 meses<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – aplicar atualizações imediatamente (padrão)<br>**1**-**8** – número de meses pelo qual as atualizações de recursos serão adiadas<br />Para obter detalhes, consulte:<br>[Introdução à manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planejar a implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Área de trabalho e dispositivos móveis<br>**Descrição:** permite que um dispositivo pare de receber atualizações por cinco semanas.<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – aplicar atualizações imediatamente (padrão)<br>**1** – pausar atualizações (expira após cinco semanas)|

### <a name="windows-defender"></a>Windows Defender

|Nome de política e URI|Detalhes|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0** – Não permitido<br> **1** – permitido (padrão)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – monitorar todos os arquivos (padrão)<br>**1** – Monitorar arquivos de entrada<br>**2** – Monitorar arquivos de saída|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - **90** – representa por quanto tempo o malware será retido<br>**0** – mantém malware na pasta de quarentena para sempre e não remove automaticamente (padrão)|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**1** – Verificação rápida (padrão)<br>**2** - varredura completa|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Todos os dias (padrão)<br>**1** - segunda-feira<br>**2** - terça-feira<br>**3** - quarta-feira<br>**4** - quinta-feira<br>**5** - sexta-feira<br>**6** - sábado<br>**7** - domingo<br>**8** – Nenhuma varredura agendada|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - 12h00<br>**60** – 1h00<br>**120** – 2h00 (padrão)<br>**180** – 3h00<br>**240** – 4h00<br>**300** – 5h00<br>**360** – 6h00<br>**420** – 7h00<br>**480** – 8h00<br>**540** – 9h00<br>**600** – 10h00<br>**660** – 11h00<br>**720** – 00h00<br>**780** – 13h00<br>**840** – 14h00<br>**900** – 15h00<br>**960** – 16h00<br>**1020** – 17h00<br>**1080** – 18h00<br>**1140** – 19h00<br>**1200** – 20h00<br>**1260** – 21h00<br>**1320** – 22h00<br>**1381** – Janela de manutenção|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Somente Área de trabalho<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - 12h00<br>**60** – 1h00<br>**120** – 2h00 (padrão)<br>**180** – 3h00<br>**240** – 4h00<br>**300** – 5h00<br>**360** – 6h00<br>**420** – 7h00<br>**480** – 8h00<br>**540** – 9h00<br>**600** – 10h00<br>**660** – 11h00<br>**720** – 00h00<br>**780** – 13h00<br>**840** – 14h00<br>**900** – 15h00<br>**960** – 16h00<br>**1020** – 17h00<br>**1080** – 18h00<br>**1140** – 19h00<br>**1200** – 20h00<br>**1260** – 21h00<br>**1320** – 22h00<br>**1380** – 23h00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** - **100** (padrão: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br>**Valores:<br>** **0** – não permitido (padrão)<br> **1** – permitido|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido (padrão)<br> **1** – permitido|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão) – também é executado quando o RTP está ativado, quando é definido como permitido|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não verificar assinaturas em um intervalo<br>**1** - verificar assinaturas a cada hora<br>**2** – verificar a cada duas horas <br>**24** – verificar todos os dias<br>**8** – verificar a cada oito horas (padrão)|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitido<br> **1** – permitido (padrão)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Sempre solicitar (padrão)<br>**1** – Enviar amostras seguras automaticamente<br>**2** – Nunca enviar<br>**3** – Enviar todas as amostras automaticamente|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br>*&lt;Lista de extensões separadas por ponto e vírgula&gt;* por exemplo, **obj;lib**<br>**Padrão –** nenhuma extensão excluída|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br />*&lt;Lista dos caminhos separados por ponto e vírgula&gt;*<br />Exemplo: **c:\test;c:\test1.exe**<br />**Padrão –** nenhum caminho é excluído|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br>*&lt;Lista dos caminhos separados por ponto e vírgula&gt;*<br>Exemplo: **c:\test.exe;c:\test1.exe**<br>**Padrão –** nenhum processo é excluído|

### <a name="edge-browser"></a>Navegador de borda

|Nome de política e URI|Detalhes|
|---------------|------------|-----------|
|**Permitir Navegador**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – navegação desativada <br>**1** – navegação ativada (padrão)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não mostrar sugestões<br> **1** – exibir sugestões de pesquisa (padrão)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – desabilitado (abrir sites da intranet no navegador Microsoft Edge – padrão)<br>**1**: habilitado (abrir sites da intranet no Internet Explorer)|
|**Permitir Não Rastrear**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Área de trabalho e dispositivos móveis)<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – desabilitado (DNT não enviado – padrão)<br> **1** – habilitado (enviar DNT)|
|**Configurar SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – não permitir<br> **1** – Permitir (padrão)|
|**Permitir Pop-ups**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:<br>** **0** – bloquear pop-ups (padrão)<br> **1** – Permitir pop-ups|
|**Permitir Cookies**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – permitir cookies de todos os sites (padrão)<br>**1** – Bloquear somente os cookies de terceiros<br>**2** – Bloquear todos os cookies|
|**Permitir Salvar Senha**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – o Gerenciador de Senhas é desabilitado <br>**1** – o Gerenciador de Senhas é habilitado (padrão)|
|**Permitir Preenchimento Automático**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores**:<br> **0** – Desabilitado (padrão)<br> **1** – Habilitado|
|**Configurar Lista de Sites Empresariais**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br>**0** – não configurado<br>**1** – Usar a lista de sites do modo corporativo do IE, se configurado (padrão)<br>**2** – Especificar a localização da lista de sites corporativos|

## <a name="general-configuration-policy-settings"></a>Definições de política de configuração geral

Use a **política de configuração geral** do Microsoft Intune para Windows 10 para definir configurações internas para Windows 10 Desktop e dispositivos Windows 10 Mobile registrados.

### <a name="password"></a>Senha

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Exigir uma senha para desbloquear dispositivos**|-|
|**Tipo de senha necessária**|Especifica se a senha deve ser apenas numérica ou alfanumérica|
|**Tipo de senha necessária** - **Número mínimo de conjuntos de caracteres**| Especifica quantos dos conjuntos de caracteres (letras minúsculas, letras maiúsculas, números e símbolos) devem ser incluídos na senha|
|**Comprimento mínimo da senha**|Aplica-se somente ao Windows 10 Mobile|
|**Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado**.|Para dispositivos que executam o Windows 10: se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a entrada falhar o número de vezes que você especificar. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não será aplicada.<br>Para dispositivos que executam o Windows Mobile 10: depois que a entrada falhar o número de vezes que você especificar, o dispositivo será apagado.|
|**Minutos de inatividade antes que a tela se apague**|Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada|
|**Expiração da senha (dias)**|Especifica o período após o qual a senha do dispositivo deve ser alterada|
|**Lembrar histórico de senha**|Especifica se você deseja impedir que o usuário crie senhas usadas anteriormente|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo|
|**Exigir uma senha quando o dispositivo volta do estado ocioso**|Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo (somente para Windows 10 Mobile)|

### <a name="encryption"></a>Criptografia

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Exigir criptografia no dispositivo móvel**|Habilita a criptografia em dispositivos de destino<br>(Somente Windows 10 Mobile)|

### <a name="system"></a>System (sistema)

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir captura de tela**|Permite que o usuário capture a tela do dispositivo como uma imagem (somente para Windows 10 Mobile)|
|**Permitir cancelamento de registro manual**|Permite que o usuário exclua manualmente a conta de trabalho do dispositivo|
|**Permitir instalação de certificado raiz manual**|Aplica-se ao Windows 10 Mobile|
|**Permitir que o diagnóstico e os dados de uso sejam enviados à Microsoft**|Os possíveis valores são:<br><br>**Não** - Nenhum dado é enviado para a Microsoft<br>**Básico** – Informações limitadas são enviadas à Microsoft<br>**Avançado** - dados de diagnóstico avançados são enviados à Microsoft<br>**Completo (recomendado)** - Envia os mesmos dados que **Avançado**, além de dados adicionais sobre o estado do dispositivo|


### <a name="account-and-synchronization"></a>Conta e sincronização

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir conta da Microsoft**|Permite que o usuário associe uma conta da Microsoft ao dispositivo|
|**Permitir adicionar contas que não são da Microsoft manualmente**|Permite que o usuário adicione contas de email a dispositivos que não estão associadas uma conta da Microsoft|
|**Permitir a sincronização de configurações de contas da Microsoft**|Permitir configurações de dispositivo e aplicativo associadas a uma conta da Microsoft para sincronização entre dispositivos|

### <a name="microsoft-edge"></a>Microsoft Edge

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir o navegador da Web**|Permite o uso do navegador da Web Microsoft Edge no dispositivo<br>(Somente Windows 10 Mobile)|
|**Permitir sugestões de pesquisa na barra de endereços**|Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa|
|**Permitir tráfego intranet no Internet Explorer**|Permite que os usuários abram sites da intranet no Internet Explorer<br>(Somente Windows 10 Desktop)|
|**Permitir Não Rastrear**|Configura o navegador Microsoft Edge para enviar cabeçalhos Não Rastrear para sites visitados pelos usuários|
|**Habilitar SmartScreen**||
|**Permitir scripts ativos**|Permite que scripts, como JavaScript, sejam executados no navegador Edge|
|**Permitir pop-ups**|Aplica-se somente à área de trabalho do Windows 10|
|**Permitir cookies**||
|**Permitir Preenchimento Automático**|Habilita os usuários a alterarem as configurações de preenchimento automático no navegador<br>(Somente Windows 10 Desktop)|
|**Permitir Gerenciador de Senhas**|Habilita ou desabilita o recurso de Gerenciador de Senhas do Edge|
|**Local do Enterprise Mode Site List**|Especifica onde encontrar a lista de sites que será aberta no modo Enterprise. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop)|

### <a name="apps"></a>Aplicativos

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir repositório de aplicativos**|Aplica-se somente ao Windows 10 Mobile|



### <a name="cellular"></a>Celular

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permite roaming de dados**|Permitir roaming entre redes durante o acesso de dados|
|**Permitir VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular|
|**Permitir roaming de VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando estiver em roaming ou em uma rede celular|

### <a name="hardware"></a>Hardware

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir câmera**|-|
|**Permitir armazenamento removível**|Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo|
|**Permitir Wi-Fi**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir compartilhamento de Internet**|Permite o uso de compartilhamento de conexão com a Internet no dispositivo móvel|
|**Permitir configuração manual de Wi-Fi**|Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi<br>(Somente Windows 10 Mobile)|
|**Permitir conexão automática para pontos de acesso Wi-Fi gratuitos**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente|
|**Permitir localização geográfica**|Especifica se o dispositivo pode usar informações de serviços de localização|
|**Permitir NFC**|Permite que o dispositivo use sua funcionalidade de Comunicação a Curta Distância|
|**Permitir Bluetooth**|-|
|**Permitir modo detectável de Bluetooth**|Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth|
|**Permitir anúncios de Bluetooth**|Permite que os dispositivos recebam anúncios via Bluetooth|
|**Permitir a redefinição do telefone**|Controla se o usuário pode redefinir seu dispositivo para os padrões de fábrica|
|**Permitir conexão USB**|Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB|
|**Permitir modo AntiTheft**|Configure se o modo AntiTheft do Windows está habilitado|

### <a name="features"></a>Recursos

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir copiar e colar**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir gravação de voz**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir Cortana**|Habilitar ou desabilitar a assistente de voz Cortana|
|**Permitir notificações da central de ações**|Habilitar ou desabilitar notificações da central de ações na tela de bloqueio do dispositivo<br>(Somente Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Todas as configurações são somente para Windows 10 Desktop.

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir monitoramento em tempo real**|Habilita a verificação em tempo real de malware, spyware e outros softwares indesejados|
|**Habilitar o monitoramento de comportamento**|Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos|
|**Habilitar Sistema de Inspeção de Rede**|O NIS (Sistema de Inspeção de Rede) ajuda a proteger dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado|
|**Verificar todos os downloads**|Controla se o Defender examina todos os arquivos baixados da Internet|
|**Permitir verificação de script**|Permite que o Defender examine scripts que são usados no Internet Explorer|
|**Monitorar atividade de arquivo e programa**|Permite que o Defender monitore a atividade de arquivos e programas nos dispositivos|
|**Dias para acompanhar malware resolvido**|Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente. |
|**Permitir acesso à interface do usuário cliente**|Controla se a interface do usuário do Windows Defender fica oculta para usuários finais.<br>Quando alterada, esta configuração entra em vigor na próxima vez em que o computador do usuário for reiniciado.|
|**Agendar uma verificação rápida diária**|Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar|
|**Agendar uma verificação do sistema**|Permite agendar uma verificação de sistema completa ou rápida que ocorre regularmente no dia e hora que você selecionar|
|**Limitar o uso da CPU durante uma verificação**|Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**)|
|**Verificar arquivos mortos**|Permite que o Defender examine Verificar arquivamentos, como arquivos .zip ou .cab.|
|**Verificar mensagens de email**|Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo|
|**Verificar unidades removíveis**|Permite que o Defender examine unidades removíveis, como cartões USB|
|**Verificar unidades de rede mapeadas**|Permite que o Defender examine arquivos em unidades de rede mapeadas.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Verificar arquivos abertos de pastas compartilhadas na rede**|Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC).<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Intervalo de atualização de assinatura**|Especifica o intervalo no qual o Defender verifica novos arquivos de assinatura.|
|**Permitir proteção de nuvem**|Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.|
|**Solicitar aos usuários o envio de amostras**|Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados sejam enviados automaticamente para a Microsoft|
|**Detecção de Aplicativo Potencialmente Indesejado**|Protege dispositivos Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado.|
|**Arquivos e pastas a serem excluídos ao executar uma verificação ou usar a proteção em tempo real**|Adiciona um ou mais arquivos e pastas como **C:\Path** ou **ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.|
|**Extensões de arquivo a serem excluídas ao executar uma verificação ou usar a proteção em tempo real**|Adicionar uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Arquivos com essas extensões não serão incluídos em verificações em tempo real ou programadas.|
|**Processos a serem excluídos ao executar uma verificação ou usar a proteção em tempo real**|Adiciona um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos não serão incluídas em verificações em tempo real ou programadas.|


### <a name="updates"></a>Updates

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|---------------|
|**Permitir atualizações automáticas**|Permite atualizações automáticas. Defina as seguintes configurações para controlar o comportamento de atualização:<br />**Notificar o download**<br />**Instalação automática no tempo de manutenção**<br />**Instalação automática e reinicialização no tempo de manutenção**<br />**Instalar automaticamente e reiniciar no horário agendado**: observe que quando esta opção é selecionada, você também pode definir as seguintes configurações: **Suprimir notificação para usuário final** e **Defina o dia de instalação das atualizações agendadas**.<br>(Somente Windows 10 Desktop)|
|**Permitir recursos de pré-lançamento**|Permite que a Microsoft implante configurações e recursos de pré-lançamento em dispositivos Windows 10. Você pode selecionar para permitir apenas as configurações, ou todos os recursos e configurações de pré-lançamento a serem instalados.|

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->


