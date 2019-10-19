---
title: Configurações personalizadas – Dispositivos Windows Holographic for Business – Microsoft Intune
description: Adicione ou crie um perfil personalizado para usar as configurações de OMA-URI para dispositivos que executam o Windows Holographic for Business no Microsoft Intune, incluindo Microsoft Hololens. Você pode definir as configurações do CSP (provedor de serviço de configuração) de política AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates e ApplicationLaunchRestrictions.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.article: article
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.topic: reference
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54c38bac5ddf9eee1dd5f1dc6d544de3fa2395ab
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506910"
---
# <a name="use-custom-settings-for-windows-holographic-for-business-devices-in-intune"></a>Usar configurações personalizadas para dispositivos do Windows Holographic for Business no Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos Windows Holographic for Business usando "perfis personalizados". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações e recursos de dispositivos que não são internos ao Intune.

Os perfis personalizados do Windows Holographic for Business usam as configurações do OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir os diversos recursos. Essas configurações geralmente são usadas pelos fabricantes de dispositivos móveis para controlar os recursos do dispositivo.

O Windows Holographic for Business disponibiliza muitas configurações de CSPs (Provedores de Serviço de Configuração). Para uma visão geral sobre CSP, consulte [Introdução aos CSPs (Provedores de Serviço de Configuração) para profissionais de TI](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Para CSPs específicos compatíveis com o Windows Holographic, consulte [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Se você estiver procurando uma configuração específica, lembre-se de que o [perfil de restrição de dispositivo do Windows Holographic for Business](device-restrictions-windows-holographic.md) inclui várias configurações internas. Dessa forma, talvez você não precise inserir valores personalizados.

Este artigo mostra como criar um perfil personalizado para dispositivos Windows Holographic for Business. Também inclui uma lista das configurações OMA-URI recomendadas.

## <a name="create-the-profile"></a>Criar o perfil

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `hololens custom profile`.
    - **Descrição:** insira uma descrição para o perfil.
    - **Plataforma**: escolha **Windows 10 e posterior**.
    - **Tipo de perfil**: escolha **Personalizado**.

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    - **Nome**: insira um nome exclusivo para a configuração de OMA-URI para ajudar você a identificá-la na lista de configurações.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
    - **OMA-URI** (com diferenciação de maiúsculas e minúsculas): insira o OMA-URI que você deseja usar como configuração.
    - **Tipo de dados**: escolha o tipo de dados que você usará para essa configuração de OMA-URI. Suas opções:

        - Cadeia de caracteres
        - Cadeia de caracteres (arquivo XML)
        - Data e hora
        - Inteiro
        - Ponto flutuante
        - Booliano
        - Base64 (arquivo)

    - **Valor** – insira o valor de dados que você deseja associar ao OMA-URI inserido. O valor depende do tipo de dados selecionado. Por exemplo, se você escolher **Data e hora**, selecione o valor em um seletor de data.

    Depois de adicionar algumas configurações, você pode selecionar **Exportar**. **Exportar** cria uma lista de todos os valores que você adicionou em um arquivo de valores separados por vírgulas (.csv).

5. Selecione **OK** para salvar suas alterações. Continue a adicionar mais configurações conforme necessário.
6. Quando terminar, escolha **OK** > **Criar** para criar o perfil do Intune. Ao concluir, seu perfil é mostrado na lista **Configuração do dispositivo – Perfis**.

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

Você pode encontrar uma lista completa de todos os CSPs (Provedores de Serviço de Configuração) compatíveis com o Windows Holographic em [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Nem todas as configurações são compatíveis com todas as versões do Windows Holographic. A tabela em [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) lista as versões com suporte para cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas em [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Para saber se o Intune é compatível com a configuração desejada, abra o artigo dessa configuração. Cada página de configuração mostra a operação com suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md).

Veja como criar um perfil personalizado em [dispositivos Windows 10](../custom-settings-windows-10.md).
