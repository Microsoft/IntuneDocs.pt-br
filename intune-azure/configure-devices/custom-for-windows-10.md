---
title: "Configurações personalizadas do Intune para dispositivos Windows 10 | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda sobre as configurações que você pode usar em um perfil personalizado do Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: bc740d9e43e2937757075bf84735fe611433f6f0
ms.lasthandoff: 02/16/2017


---

# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Configurações personalizadas do dispositivo para dispositivos Windows 10 no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 Use o perfil **personalizado** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows 10 disponibiliza várias configurações por meio do [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](how-to-configure-custom-settings.md) para começar.
2. Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Na folha **Configurações personalizadas do OMA-URI**, clique em **Adicionar** para adicionar um novo valor. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
4. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir. Use a lista neste tópico para saber mais sobre as configurações que você pode usar:
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
5. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.
O perfil será criado e aparecerá na folha da lista de perfis.

## <a name="example"></a>Exemplo
Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada. Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.

> ![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-policy-example.png)


## <a name="policy-settings"></a>Configurações de política

|Nome de política e URI|Detalhes|
|---------------|------------|-----------|
|**Permitir Atualização Automática**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Somente Área de trabalho<br>**Tipo de dados:** inteiro<br />**Valores:** **0** - **5** (padrão: **1**)|
|**Agendar Dia Para Instalação**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Somente dispositivos móveis<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - Todos os dias (padrão)<br>**1** - domingo<br>**2** - segunda-feira<br>**3** - terça-feira<br>**4** - quarta-feira<br>**5** - quinta-feira<br>**6** - sexta-feira<br>**7** - Sábado|
|**Agendar Horário para Instalação**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – **23** horas (**0** é meia-noite) (padrão: **3**)|
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
|**Forçar Tamanho Inicial**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - permitir que o usuário altere o tamanho (padrão)<br>**1** - forçar tela não inteira<br>**2** - forçar tela inteira|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: não adiar atualização (mantém na ramificação atual, CB - padrão)<br>**1**: possibilitar que atualizações sejam adiadas (dispositivo segue a ramificação atual para empresas, CBB e regras)<br />Para obter detalhes, consulte:<br>[Introdução à manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planejar a implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Área de trabalho e dispositivos móveis<br>**Descrição:** política para adiar atualizações de software por até 4 semanas<br />**Tipo de dados:** inteiro<br />**Valores:**<br> **0**: aplicar atualizações imediatamente (padrão)<br>**1**-**4**: número de semanas para adiar atualizações de software.<br />Para obter detalhes, consulte:<br>[Introdução à manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planejar a implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Área de trabalho e dispositivos móveis<br>**Descrição:** política para adiar atualizações de recursos para até 8 meses<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: aplicar atualizações imediatamente (padrão)<br>**1**-**8**: número de meses para adiar atualizações de recursos.<br />Para obter detalhes, consulte:<br>[Introdução à manutenção do Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planejar a implantação do Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Área de trabalho e dispositivos móveis<br>**Descrição:** permite que um dispositivo pare de receber atualizações por cinco semanas.<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: aplicar atualizações imediatamente (padrão)<br>**1**: pausar atualizações (expira após 5 semanas)|

## <a name="windows-defender-settings"></a>Configurações do Windows Defender

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
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - 12h00<br>**60** – 1h00<br>**120** – 2h00 (padrão)<br>**180** – 3h00<br>**240** – 4h00<br>**300** – 5h00<br>**360** – 6h00<br>**420** – 7h00<br>**480** – 8h00<br>**540** – 9h00<br>**600** – 10h00<br>**660** – 11h00<br>**720** – 00h00<br>**780** – 13h00<br>**840** – 14h00<br>**900** – 15h00<br>**960** – 16h00<br>**1020** – 17h00<br>**1080** – 18h00<br>**1140** – 19h00<br>**1200** – 20h00<br>**1260** – 21h00<br>**1320** – 22h00<br>**1381** – Janela de manutenção|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Somente Área de trabalho<br>**Tipo de dados:** inteiro<br />**Valores:**<br>**0** - 12h00<br>**60** – 1h00<br>**120** – 2h00 (padrão)<br>**180** – 3h00<br>**240** – 4h00<br>**300** – 5h00<br>**360** – 6h00<br>**420** – 7h00<br>**480** – 8h00<br>**540** – 9h00<br>**600** – 10h00<br>**660** – 11h00<br>**720** – 00h00<br>**780** – 13h00<br>**840** – 14h00<br>**900** – 15h00<br>**960** – 16h00<br>**1020** – 17h00<br>**1080** – 18h00<br>**1140** – 19h00<br>**1200** – 20h00<br>**1260** – 21h00<br>**1320** – 22h00<br>**1380** – 23h00|
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

## <a name="edge-browser-settings"></a>Configurações do navegador Edge

|Nome de política e URI|Detalhes|
|---------------|------------|-----------|
|**Permitir Navegador**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Somente dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0**: navegação desativada, **1**: navegação ativada (padrão)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0**: não mostrar sugestões, **1**: mostrar sugestões (padrão)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0**: desabilitado (abrir sites da intranet no navegador  Microsoft Edge - padrão)<br>**1** - habilitado (abrir sites de intranet no Internet Explorer).|
|**Permitir Não Rastrear**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Área de trabalho e dispositivos móveis)<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – desabilitado (DNT não enviado - padrão), **1** – habilitado (enviar DNT)|
|**Configurar SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – não permitir, **1** – permitir (padrão)|
|**Permitir Pop-ups**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – bloquear pop-ups (padrão), **1** – permitir pop-ups|
|**Permitir Cookies**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – permitir cookies de todos os sites (padrão)<br>**1** – Bloquear somente os cookies de terceiros<br>**2** – Bloquear todos os cookies|
|**Permitir Salvar Senha**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Área de trabalho e dispositivos móveis<br />**Tipo de dados:** inteiro<br />**Valores:**<br>**0** – O gerenciador de senha é desabilitado; <br>**1** – O Gerenciador de senha é habilitado (padrão)|
|**Permitir Preenchimento Automático**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Somente Área de trabalho<br />**Tipo de dados:** inteiro<br />**Valores:** **0** – desabilitado (padrão), **1** – habilitado|
|**Configurar Lista de Sites Empresariais**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Somente Área de trabalho<br />**Tipo de dados:** cadeia de caracteres<br />**Valores:<br>**0** – não configurado<br>**1** – usar lista de sites de modo empresarial do IE se configurado (padrão)<br>**2** – especificar o local da lista de sites corporativos|

