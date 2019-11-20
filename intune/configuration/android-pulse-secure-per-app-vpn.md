---
title: Perfil de VPN por aplicativo personalizado para Android
titleSuffix: Microsoft Intune
description: Saiba como criar um perfil VPN por aplicativo para dispositivos Android gerenciados pelo Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3683d2aeada791c6ec827e915e02365a336e6045
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059668"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Use um perfil personalizado do Microsoft Intune para criar um perfil de VPN por aplicativo para dispositivos Android

[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Você pode criar um perfil de VPN por aplicativo para dispositivos Android 5.0 e posterior gerenciados pelo Intune. Primeiro, crie um perfil de VPN que use o tipo de conexão Pulse Secure ou Citrix. Em seguida, crie uma política de configuração personalizada que associa o perfil de VPN com aplicativos específicos.

Após atribuir a política aos grupos de usuários ou de dispositivos Android, os usuários deverão iniciar o cliente de VPN Citrix ou Pulse Secure. O cliente VPN então permite somente que tráfego dos aplicativos especificados use a conexão VPN aberta.

> [!NOTE]
>
> Para este perfil, há suporte apenas para o tipo de conexão Pulse Secure e Citrix.

## <a name="step-1-create-a-vpn-profile"></a>Etapa 1: Criar um perfil VPN

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um nome ideal de perfil é **Perfil VPN por aplicativo Android para toda a empresa**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Android**.
    - **Tipo de perfil**: Selecione **VPN**.

4. Escolha **Configurações** > **Definir** e defina o perfil VPN de acordo com as configurações em [Como definir as configurações de VPN](vpn-settings-configure.md) e [Configurações VPN do Intune para dispositivos Android](vpn-settings-android.md).

Anote o valor de **Nome da Conexão** que você especificou ao criar o perfil de VPN. Esse nome será necessário na próxima etapa. Por exemplo, **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Etapa 2: Criar uma política de configuração personalizada

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para o perfil personalizado. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um bom nome de perfil é **Perfil VPN Android OMA-URI para toda a empresa**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Android**.
    - **Tipo de perfil**: Selecione **Personalizado**.

4. Escolha **Configurações** > **Definir**.
5. No painel **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
    - **Nome**: Insira um nome para sua configuração.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **OMA-URI**: Insira `./Vendor/MSFT/VPN/Profile/*Name*/PackageList`, em que *Nome* é o nome da conexão que você anotou na Etapa 1. Neste exemplo, a cadeia de caracteres é `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList`.
    - **Tipo de dados**: Insira **Cadeia de caracteres**.
    - **Valor**: Insira uma lista separada por ponto e vírgula dos pacotes a serem associados ao perfil. Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: `com.microsoft.office.excel;com.android.chrome`.

![Exemplo de política personalizada de VPN por aplicativo Android](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Definir sua lista de aplicativos como lista de bloqueios ou lista de permissões (opcional)

Você pode inserir uma lista de aplicativos que *não podem* usar a conexão VPN usando o valor **BLACKLIST**. Todos os outros aplicativos se conectam por meio da VPN. Ou, você pode usar o valor **WHITELIST** para inserir uma lista de aplicativos que *podem* usar a conexão VPN. Os aplicativos que não estão na lista não se conectam por meio da VPN.

1. No painel **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
2. Insira um nome para a configuração.
3. Em **OMA-URI**, insira `./Vendor/MSFT/VPN/Profile/*Name*/Mode`, em que *Nome* é o perfil VPN que você anotou na Etapa 1. Em nosso exemplo, a cadeia de caracteres é `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. Em **Tipo de dados**, insira **Cadeia de caracteres**.
5. Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.

## <a name="step-3-assign-both-policies"></a>Etapa 3: Atribuir ambas as políticas

[Atribua ambos os perfis de dispositivo](device-profile-assign.md) aos usuários ou dispositivos necessários.
