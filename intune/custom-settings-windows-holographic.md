---
title: Configurações personalizadas para dispositivos do Windows Holographic for Business no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil personalizado para usar as configurações de OMA-URI para dispositivos que executam o Windows Holographic for Business no Microsoft Intune. Você pode definir as configurações do CSP (provedor de serviço de configuração) de política AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates e ApplicationLaunchRestrictions.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7272e8e088ae2c2ecad1756233281c42a80a279b
ms.sourcegitcommit: 2061f7a442efc96c8afd5db764d11531563c7e39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "32328071"
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>Configurações de dispositivo personalizadas para dispositivos que executam o Windows Holographic for Business no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 Use o perfil **personalizado** do Microsoft Intune para Windows Holographic for Business para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows Holographic for Business disponibiliza muitas configurações de CSPs (Provedores de Serviço de Configuração). Para uma visão geral sobre CSP, consulte [Introdução aos CSPs (Provedores de Serviço de Configuração) para profissionais de TI](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Para CSPs específicos compatíveis com o Windows Holographic, consulte [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Se você estiver procurando uma configuração específica, lembre-se que o [perfil de restrição de dispositivo do Windows Holographic for Business](device-restrictions-windows-holographic.md) contém várias configurações internas e não necessita que você especifique valores personalizados.

## <a name="create-the-custom-oma-uri-profile"></a>Criar o perfil personalizado do OMA-URI

1. Use as instruções em [Definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Em **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Em **Configurações personalizadas de OMA-URI**, clique em **Adicionar** para adicionar um novo valor. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
4. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir:
  - **Nome da configuração**: insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
  - **Descrição da configuração**: opcionalmente, insira uma descrição para a configuração.
  - **Tipo de dados**: escolha dentre:
    - **Cadeia de caracteres**
    - **Cadeia de caracteres (XML)**
    - **Data e hora**
    - **Inteiro**
    - **Ponto flutuante**
    - **Booliano**
  - **OMA-URI (com diferenciação de maiúsculas e minúsculas)**: insira o OMA-URI para o qual você deseja fornecer uma configuração.
  - **Valor**: insira o valor que você deseja associar ao OMA-URI inserido.
5. Quando terminar, volte para **Criar Perfil** e clique em **Criar**. O perfil é criado e exibido na lista de perfis.

## <a name="recommended-custom-settings"></a>Configurações personalizadas recomendadas

As configurações a seguir são úteis para dispositivos que executam o Windows Holographic for Business:

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Inteiro<br/>0 – não permitido<br/>1 – permitido (padrão)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Inteiro<br/>0 – serviço de atualização não é permitido <br/>1 – serviço de atualização é permitido (padrão).|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Inteiro<br/>0 – não permitido<br/>1 – permitido (padrão)|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Inteiro<br/>0 – não configurado. O dispositivo instala todas as atualizações aplicáveis.<br/>1 – o dispositivo instala somente as atualizações que são aplicáveis e que estão na lista de Atualizações Aprovadas. Defina essa política como 1 se o TI deseja controlar a implantação de atualizações em dispositivos, como quando há necessidade de testes antes da implantação.|

### <a name="scheduledinstalltimehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Inteiro de 0 a 23, em que 0 = 12 AM e 23 = 11 PM<br/>O valor padrão é 3.|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Cadeia de caracteres<br/>URL – o dispositivo verifica atualizações no servidor do WSUS na URL especificada.<br/>Não configurado – o dispositivo verifica se há atualizações no Microsoft Update.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Importante**<br/>Você deve ler e aceitar os Termos de Licença atualizados em nome dos usuários finais. Se não fizer isso, ocasionará uma violação de obrigações contratuais ou legais.|Nó para aprovações de atualização e aceitação de Termos de Licença em nome do usuário final.<br/><br/>Para saber mais, confira [Atualizar CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Importante**<br/>O artigo AppLocker CSP usa exemplos com XML de escape. Para definir as configurações com perfis personalizados do Intune, você deve usar XML sem formatação.|Cadeia de caracteres<br/>Para saber mais, confira [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).|

### <a name="deletionpolicyhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Inteiro<br/>0 – exclusão imediata quando o dispositivo retorna para um estado sem usuários ativos no momento<br/>1 – exclusão no limite de capacidade de armazenamento (padrão)<br/>2 – exclusão no limite de capacidade de armazenamento e no limite de inatividade de perfil|

### <a name="enableprofilemanagerhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Booliano<br/>True – habilitar<br/>False – desabilitar (padrão)|

### <a name="profileinactivitythresholdhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Inteiro<br/>O valor padrão é 30.|


### <a name="storagecapacitystartdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Inteiro<br/>O valor padrão é 25.|

### <a name="storagecapacitystopdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de dados|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Inteiro<br/>O valor padrão é 50.|

## <a name="find-the-policies-you-can-configure"></a>Localizar as políticas que você pode configurar

Você pode encontrar uma lista completa de todos os CSPs (Provedores de Serviço de Configuração) compatíveis com o Windows Holographic em [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Nem todas as configurações são compatíveis com todas as versões do Windows Holographic. A tabela no artigo do Windows informa quais versões são compatíveis com cada CSP.

Além disso, o Intune não é compatível com todas as configurações listadas no artigo. Para saber se o Intune é compatível com a configuração desejada, abra o artigo dessa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.
