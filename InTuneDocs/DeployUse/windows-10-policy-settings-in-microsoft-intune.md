---
title: "Configurações de política do Windows 10 | Microsoft Intune"
description: "Use as configurações de política listadas neste tópico para ajudá-lo a definir as configurações internas e personalizadas para dispositivos Windows 10 Mobile e Windows 10 Desktop."
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
translationtype: Human Translation
ms.sourcegitcommit: b8522406a3c73746b09616c3ec917464cf751312
ms.openlocfilehash: 6e482beb5e2edce648ecb6f1821baa6214fa0f2f


---

# Configurações de política do Intune para dispositivos Windows 10 no Microsoft Intune

Este tópico contém informações para ajudá-lo a entender as configurações de política do Intune que você pode usar para gerenciar dispositivos Windows 10. Leia este tópico junto com os procedimentos em [Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) para definir configurações internas e personalizadas para dispositivos da Área de Trabalho do Windows 10 e Windows Mobile 10 registrados. Você não pode usar essas políticas com computadores que executam o [software de cliente do Intune PC](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Você pode escolher entre dois tipos de política:

- **Política Personalizada** - use a **política personalizada** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows 10 disponibiliza várias configurações por meio do [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Política de configuração geral** - use esse tipo de política para selecionar as configurações da lista interna fornecida com o Microsoft Intune.

## Configurações de política personalizada

Forneça as seguintes configurações em uma política personalizada:

## &nbsp;&nbsp;&nbsp;Geral

Insira um nome e, opcionalmente, uma descrição para essa política para ajudar a identificá-la no console do Intune.

## &nbsp;&nbsp;&nbsp;Configurações de OMA-URI

Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir. Use a [referência de configurações de URI do Windows 10](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) neste tópico para saber mais sobre as configurações que você pode usar: 

- **Nome da configuração** - insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
- **Descrição da configuração** - opcionalmente, insira uma descrição para a configuração.
- **Tipo de dados** - escolha dentre:
    - **Cadeia de caracteres**
    - **Cadeia de caracteres (XML)**
    - **Data e hora**
    - **Inteiro**
    - **Ponto flutuante**
    - **Booliano**
- **OMA-URI (com distinção entre maiúsculas e minúsculas)** - especifique o OMA-URI para o qual você deseja fornecer uma configuração.
- **Valor** - especifique o valor para associar ao OMA-URI que você inseriu.

### Exemplo
Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada. Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.

> ![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-policy-example.png)

## Configurações de URI do Windows 10
Use esta seção para saber mais sobre as configurações de OMA-URI que você pode configurar com uma **política personalizada do Windows 10**.

## &nbsp;&nbsp;&nbsp;Política

|Nome de política e URI|Detalhes|
|---------------|------------|-----------|
|**Permitir atualização automática**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Somente Área de trabalho<br>**Tipo de dados:** inteiro<br />**Valores:** **0** - **5** (padrão: **1**)|
|**Dia da instalação agendada**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Somente dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Todos os dias (padrão)<br>**1** - domingo<br>**2** - segunda-feira<br>**3** - terça-feira<br>**4** - quarta-feira<br>**5** - quinta-feira<br>**6** - sexta-feira<br>**7** - Sábado|
|**Hora da instalação agendada**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – **23** horas (**0** é meia-noite) (padrão: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - o usuário não pode definir o temporizador de período de carência de senha; o valor é definido como "sempre"<br>**1** - o usuário pode definir o temporizador de período de carência de senha (padrão)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não permitir **usar conexão Wi-Fi**.<br>**1** – **Permitir o uso de conexão Wi-Fi** (padrão)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Área de trabalho e dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitir compartilhamento da Internet, **1** – permitir compartilhamento da Internet (padrão)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não é permitida nenhuma conexão Wi-Fi fora do MDM provisionado.<br>**1** – É permitido adicionar novas SSIDs de rede além das que há foram provisionadas pelo MDM (padrão)|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Área de trabalho e dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitido (configuração Enterprise somente)<br>**1** – Limitado<br>**2** – completo (padrão)<br>**3** - completo e informações de diagnóstico|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitido<br>**1**- Somente configurações (padrão)<br>**2**- configurações e experimentação|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - não permitir modo contra roubo<br>**1** - Preferência do usuário (padrão)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - a VPN não é permitida por celular<br>**1** – A VPN pode usar qualquer conexão, incluindo celulares (padrão)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitir que o usuário ative o Bluetooth.<br>**1** – Reservado. O usuário pode ativar e configurar o Bluetooth (sem suporte no Windows Phone 8.1 para MDM, EAS, desktop Windows 10 ou Windows 10 Mobile)<br>**2** - Permitido. O usuário pode ativar e configurar o Bluetooth (padrão)|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitir roaming, **1** – permitir roaming (padrão)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** (padrão), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0**, **1** (padrão)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** (padrão), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** (padrão), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** (padrão), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0**, **1** (padrão)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** (padrão), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** (padrão), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Não permitir<br>O Open Extended Dictionary está desativado.<br>Um usuário não pode:<br>-Adicionar um novo Open Extended Dictionary<br />-Adicionar um novo arquivo de configuração de integração de pesquisa<br>-Usar o recurso do candidato de nuvem<br>-Enviar uma palavra registrada pelo usuário.<br>**1** - Permitir<br>O Open Extended Dictionary pode ser adicionado e usado por padrão. Além disso, a função de integração de pesquisa pode ser usada por padrão.<br>Um usuário pode:<br>Usar o recurso do candidato de nuvem.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - registro em log de erros de conversão desativado.<br>**1** - registro em log de erros de conversão ativado (padrão)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido **1** – permitido (padrão)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres Shift JIS, são filtrados|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br />**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres JIS0208, são filtrados|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Nenhum caractere é filtrado (padrão)<br>**1** - Todos, exceto caracteres JIS0208 ou EUDC, são filtrados|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Restrita, filtragem mais elevada contra conteúdo adulto<br>**1** – Moderada, filtragem moderada contra conteúdo somente para adultos (resultados da pesquisa válidos não serão filtrados - padrão)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**Forçar tamanho inicial**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - permitir que o usuário altere o tamanho (padrão)<br>**1** - forçar tela não inteira<br>**2** - forçar tela inteira|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: não adiar atualização (mantém na ramificação atual, CB - padrão)<br>**1**: possibilitar que atualizações sejam adiadas (dispositivo segue a ramificação atual para empresas, CBB e regras)<br />Para obter detalhes, consulte:<br>[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Área de trabalho e dispositivos móveis<br>**Descrição:** política para adiar atualizações de software por até 4 semanas<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0**: aplicar atualizações imediatamente (padrão)<br>**1**-**4**: número de semanas para adiar atualizações de software.<br />Para obter detalhes, consulte:<br>[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Área de trabalho e dispositivos móveis<br>**Descrição:** política para adiar atualizações de recursos para até 8 meses<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: aplicar atualizações imediatamente (padrão)<br>**1**-**8**: número de meses para adiar atualizações de recursos.<br />Para obter detalhes, consulte:<br>[Introdução ao período de manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plano de implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Área de trabalho e dispositivos móveis<br>**Descrição:** permite que um dispositivo pare de receber atualizações por cinco semanas.<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: aplicar atualizações imediatamente (padrão)<br>**1**: pausar atualizações (expira após 5 semanas)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|Nome de política e URI|Detalhes|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – monitorar todos os arquivos (padrão)<br>**1** – Monitorar arquivos de entrada<br>**2** – Monitorar arquivos de saída|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - **90** – Representa por quanto tempo o malware será retido<br>**Padrão:** **0** – mantém na pasta de quarentena para sempre e não remove automaticamente|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**1** – Verificação rápida (padrão)<br>**2** - varredura completa|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Todos os dias (padrão)<br>**1** - segunda-feira<br>**2** - terça-feira<br>**3** - quarta-feira<br>**4** - quinta-feira<br>**5** - sexta-feira<br>**6** - sábado<br>**7** - domingo<br>**8** – Nenhuma varredura agendada|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - 12:00 AM<br>**60** – 1:00 AM<br>**120** – 2h00 (padrão)<br>**180** – 3:00 AM<br>**240** – 4:00 AM<br>**300** – 5:00 AM<br>**360** – 6:00 AM<br>**420** – 7:00 AM<br>**480** – 8:00 AM<br>**540** – 9:00 AM<br>**600** – 10:00 AM<br>**660** – 11:00 AM<br>**720** – 12:00 PM<br>**780** – 1:00 PM<br>**840** – 2:00 PM<br>**900** – 3:00 PM<br>**960** – 4:00 PM<br>**1020** – 5:00 PM<br>**1080** – 6:00 PM<br>**1140** – 7:00 PM<br>**1200** – 8:00 PM<br>**1260** – 9:00 PM<br>**1320** – 10:00 PM<br>**1381** – Janela de manutenção|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Somente Área de trabalho<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - 12:00 AM<br>**60** – 1:00 AM<br>**120** – 2h00 (padrão)<br>**180** – 3:00 AM<br>**240** – 4:00 AM<br>**300** – 5:00 AM<br>**360** – 6:00 AM<br>**420** – 7:00 AM<br>**480** – 8:00 AM<br>**540** – 9:00 AM<br>**600** – 10:00 AM<br>**660** – 11:00 AM<br>**720** – 12:00 PM<br>**780** – 1:00 PM<br>**840** – 2:00 PM<br>**900** – 3:00 PM<br>**960** – 4:00 PM<br>**1020** – 5:00 PM<br>**1080** – 6:00 PM<br>**1140** – 7:00 PM<br>**1200** – 8:00 PM<br>**1260** – 9:00 PM<br>**1320** – 10:00 PM<br>**1380** – 11:00 PM|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** - **100** (padrão: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br>**Valores:** **0** – não permitido (padrão), **1** – permitido|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido (padrão), **1** – permitido|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão) – também é executado quando o RTP está ativado, caso definido como permitido|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – não verificar assinaturas em um intervalo<br>**1** - verificar assinaturas a cada hora<br>**2** – verificar a cada duas horas etc.<br>**24** – verificar todos os dias<br>**Valor padrão:** 8 – verificar a cada oito horas|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitido, **1** – permitido (padrão)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – Sempre solicitar (padrão)<br>**1** – Enviar amostras seguras automaticamente<br>**2** – Nunca enviar<br>**3** – Enviar todas as amostras automaticamente|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br>*&lt;lista de extensões separadas por ponto e vírgula&gt;* por exemplo, **obj;lib**<br>**Padrão:** nenhuma extensão excluída|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br />*&lt;lista dos caminhos separados por ponto e vírgula&gt;*<br />Exemplo: **c:\test;c:\test1.exe**<br />**Valor padrão:** nenhum caminho será excluído|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:**<br>*&lt;lista dos caminhos separados por ponto e vírgula&gt;*<br>Exemplo: **c:\test.exe;c:\test1.exe**<br>**Valor padrão:** nenhum processo será excluído|

## &nbsp;&nbsp;&nbsp;Navegador de borda

|Nome de política e URI|Detalhes|
|---------------|------------|-----------|
|**Permitir navegador**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0**: navegação desativada, **1**: navegação ativada (padrão)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0**: não mostrar sugestões, **1**: mostrar sugestões (padrão)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: desabilitado (abrir sites da intranet no navegador  Microsoft Edge - padrão)<br>**1** - habilitado (abrir sites de intranet no Internet Explorer).|
|**Permitir Não Rastrear**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Área de trabalho e dispositivos móveis)<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – desabilitado (DNT não enviado - padrão), **1** – habilitado (enviar DNT)|
|**Configurar o SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitir, **1** – permitir (padrão)|
|**Permitir pop-ups**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – bloquear pop-ups (padrão), **1** – permitir pop-ups|
|**Permitir cookies**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – permitir cookies de todos os sites (padrão)<br>**1** – Bloquear somente os cookies de terceiros<br>**2** – Bloquear todos os cookies|
|**Permitir salvar senha**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – O gerenciador de senha é desabilitado; <br>**1** – O Gerenciador de senha é habilitado (padrão)|
|**Permitir Preenchimento Automático**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – desabilitado (padrão), **1** – habilitado|
|**Configurar a lista de sites corporativos**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:<br>**0** – não configurado<br>**1** – usar lista de sites de modo empresarial do IE se configurado (padrão)<br>**2** – especificar o local da lista de sites corporativos|

## Definições de política de configuração geral

Use a **política de configuração geral** do Microsoft Intune para Windows 10 para definir configurações internas para Windows 10 Desktop e dispositivos Windows 10 Mobile registrados. 

## &nbsp;&nbsp;&nbsp;Senha

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Exigir uma senha para desbloquear dispositivos**|-|
|**Tipo de senha necessária**|Especifica se a senha deve ser apenas numérica ou alfanumérica|
|**Tipo de senha necessária** - **Número mínimo de conjuntos de caracteres**|Há quatro conjuntos de caracteres: minúsculas, maiúsculas, símbolos e números. Essa configuração especifica quantos desses conjuntos devem ser incluídos na senha.|
|**Comprimento mínimo da senha**|Aplica-se somente ao Windows 10 Mobile|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Para dispositivos que executam o Windows 10: se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a entrada falhar pelo número de vezes que você especificar. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não será aplicada.<br>Para dispositivos que executam o Windows Mobile 10: depois que a entrada falhar pelo número de vezes que você especificar, o dispositivo será apagado.|
|**Minutos de inatividade antes que a tela se apague**|Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.|
|**Expiração da senha (dias)**|Especifica o período após o qual a senha do dispositivo deve ser alterada.|
|**Lembrar de histórico de senha**|Especifica se você deseja impedir que o usuário final crie senhas usadas anteriormente.|
|**Lembrar histórico de senha** - **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|
|**Exigir senha quando o dispositivo retorna de um estado ocioso**|Se habilitado, o usuário deve inserir uma senha para desbloquear o dispositivo. (Somente Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Criptografia

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Exigir criptografia no dispositivo móvel**|Habilitar a criptografia em dispositivos de destino.<br>(Somente Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;System (sistema)

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir captura de tela**|Permite que o usuário capture a tela do dispositivo como uma imagem. (Somente Windows 10 Mobile)|
|**Permitir cancelamento de registro manual**|Permite que o usuário exclua manualmente a conta da empresa do dispositivo.|
|**Permitir instalação de certificado raiz manual**|Aplica-se ao Windows 10 Mobile|
|**Permitir que o diagnóstico e os dados de uso sejam enviados à Microsoft**|Os possíveis valores são:<br><br>**Não** - Nenhum dado é enviado para a Microsoft<br>**Básico** - informações limitadas são enviadas à Microsoft<br>**Avançado** - dados de diagnóstico avançados são enviados à Microsoft<br>**Completo (recomendado)** - Envia os mesmos dados que **Avançado**, além de dados adicionais sobre o estado do dispositivo|


## &nbsp;&nbsp;&nbsp;Conta e sincronização

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir conta da Microsoft**|Permite que o usuário associe uma conta da Microsoft ao dispositivo.|
|**Permitir a adição de contas não Microsoft manualmente**|Permite que o usuário adicione contas de email a dispositivos que não estão associados uma conta da Microsoft.|
|**Permitir a sincronização de configurações de contas da Microsoft**|Permitir usar configurações de dispositivo e aplicativo associadas a uma conta da Microsoft para sincronização entre dispositivos.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir navegador da web**|Permitir o uso do navegador da Web Microsoft Edge no dispositivo.<br>(Somente Windows 10 Mobile)|
|**Permitir sugestões de pesquisa na barra de endereços**|Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.|
|**Permitir envio de tráfego de intranet no Internet Explorer**|Permite que os usuários abram sites da intranet no Internet Explorer.<br>(Somente Windows 10 Desktop)|
|**Permitir Não Rastrear**|Configura o navegador Microsoft Edge para enviar cabeçalhos Não Rastrear para sites visitados pelos usuários.|
|**Habilitar SmartScreen**|-|
|**Permitir script ativo**|Permite que scripts, como JavaScript, sejam executados no navegador Microsoft Edge.|
|**Permitir pop-ups**|Aplica-se somente à área de trabalho do Windows 10|
|**Permitir cookies**|-|
|**Permitir Preenchimento Automático**|Permite que os usuários possam alterar as configurações de preenchimento automático no navegador.<br>(Somente Windows 10 Desktop)|
|**Permitir Gerenciador de Senhas**|Habilitar ou desabilitar o recurso de Gerenciamento de Senha do Microsoft Edge.|
|**Local do Enterprise Mode Site List**|Especifica onde encontrar a lista de sites que será aberta no modo Empresarial. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop)|

## &nbsp;&nbsp;&nbsp;Aplicativos

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir loja de aplicativo**|Aplica-se somente ao Windows 10 Mobile|



## &nbsp;&nbsp;&nbsp;Celular

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir roaming de Dados**|Permita o roaming entre redes durante o acesso de dados.|
|**Permitir VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.|
|**Permitir roaming de VPN por celular**|Controla se o dispositivo pode acessar conexões VPN quando estiver em roaming ou em uma rede celular.|

## &nbsp;&nbsp;&nbsp;Hardware

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|
|**Permitir câmera**|-|
|**Permitir armazenamento removível**|Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo.|
|**Permitir Wi-Fi**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir compartilhamento de Internet**|Permitir usar o compartilhamento de conexão com a Internet no dispositivo móvel.|
|**Permitir configuração manual de Wi-Fi**|Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se podem usar somente as conexões configuradas por um perfil Wi-Fi.<br>(Somente Windows 10 Mobile)|
|**Permitir conexão automática para liberar pontos de acesso Wi-Fi**|Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.|
|**Permitir localização geográfica**|Especifica se o dispositivo pode usar informações de serviços de localização.|
|**Permitir NFC**|Permite que o dispositivo use sua funcionalidade de Comunicação a Curta Distância.|
|**Permitir Bluetooth**|-|
|**Permitir Bluetooth no modo detectável**|Permite que este dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.|
|**Permitir anúncios de Bluetooth**|Permite que os dispositivos recebam anúncios via Bluetooth.|
|**Permitir a redefinição do telefone**|Controla se o usuário pode redefinir seu dispositivo para os padrões de fábrica.|
|**Permitir conexão USB**|Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.|
|**Permitir modo AntiTheft**|Configure se o modo Antitheft do Windows está habilitado.|

## &nbsp;&nbsp;&nbsp;Recursos

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|----------------------|---------------------|
|**Permitir copiar e colar**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir gravação de voz**|Aplica-se somente ao Windows 10 Mobile|
|**Permitir Cortana**|Habilitar ou desabilitar a assistente de voz Cortana.|
|**Permitir notificações da central de ações**|Habilitar ou desabilitar notificações da central de ações na tela de bloqueio do dispositivo.<br>(Somente Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Windows Defender

Todas as configurações são somente para Windows 10 Desktop.

|Nome da configuração|Informações adicionais (quando necessário)|
|-|-|
|**Permitir monitoramento em tempo real**|Habilita a verificação em tempo real de malware, spyware e outros softwares indesejados.|
|**Habilitar o monitoramento de comportamento**|Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos.|
|**Ativar o sistema de inspeção de rede**|O NIS(Sistema de Inspeção de Rede) ajuda a proteger dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado.|
|**Verificar todos os downloads**|Controla se o Defender examina todos os arquivos baixados da Internet.|
|**Ativar a verificação de script**|Permite que o Defender examine scripts que são usados no Internet Explorer.|
|**Monitorar atividade de arquivo e programa**|Habilite essa configuração para permitir que o Defender monitore a atividade de arquivos e programas nos dispositivos.|
|**Dias para rastrear o malware resolvido**|Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente. |
|**Permitir acesso à interface do usuário cliente**|Controla se a interface do usuário do Windows Defender está oculta para usuários finais.<br>Quando essa configuração é alterada, ela entrará em vigor na próxima vez em que o computador do usuário final for reiniciado.|
|**Agendar uma verificação rápida diária**|Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.|
|**Agendar uma verificação do sistema**|Permite agendar uma verificação de sistema completa ou rápida que ocorre regularmente no dia e hora que você selecionar.|
|**Limitar uso da CPU durante uma verificação**|Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**)|
|**Pesquisar arquivos mortos**|Permite que o Defender examine arquivos armazenados como arquivos Zip ou Cab.|
|**Verificar mensagens de email**|Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo.|
|**Verificar unidades removíveis**|Permite que o Defender examine unidades removíveis, como cartões USB.|
|**Pesquisar unidades de rede mapeadas**|Permite que o Defender examine arquivos na unidade de rede mapeada.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Pesquisar arquivos abertos de pastas de rede compartilhadas**|Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.|
|**Intervalo de atualização de assinatura**|Especifique o intervalo no qual o Defender verificará novos arquivos de assinatura.|
|**Permitir proteção de nuvem**|Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.|
|**Solicitar aos usuários o envio de amostras**|Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados sejam enviados automaticamente para a Microsoft.|
|**Detecção de aplicativos potencialmente indesejados**|Esta configuração pode ser usada para proteger os dispositivos Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado.|
|**Arquivos e pastas a serem excluídos quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar um ou mais arquivos e pastas como **C:\Path** ou **ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídas em verificações em tempo real ou programadas.|
|**As extensões de arquivos a serem excluídas quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Quaisquer arquivos com essas extensões não serão incluídos em verificações em tempo real ou programadas.|
|**Processos a serem excluídos quando executar uma verificação ou usar uma proteção em tempo real**|Adicionar um ou mais processos do tipo **.exe**, **.com**, ou **. scr** à lista de exclusões. Esses processos não serão incluídas em verificações em tempo real ou programadas.| 


## &nbsp;&nbsp;&nbsp;Updates

|Nome da configuração|Informações adicionais (quando necessário)|
|----------------|---------------|
|**Permitir atualizações automáticas**|Habilite essa configuração para permitir as atualizações automáticas. Em seguida, configure as seguintes configurações para controlar o comportamento de atualização:<br />**Notificar o download**<br />**Instalação automática no tempo de manutenção**<br />**Instalação automática e reinicialização no tempo de manutenção**<br />**Instalação automática e a reinicialização no horário agendado** **Observação:** quando esta opção é selecionada, você também pode definir as seguintes configurações: **Suprimir notificação para o usuário final** e **Definir dia da instalação de atualizações agendadas**.<br>(Somente Windows 10 Desktop)|
|**Permitir recursos de pré-lançamento**|Permite que a Microsoft implante configurações e recursos de pré-lançamento em dispositivos Windows 10. Você pode selecionar para permitir apenas as configurações, ou todos os recursos e configurações de pré-lançamento a serem instalados.|

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Oct16_HO1-->


