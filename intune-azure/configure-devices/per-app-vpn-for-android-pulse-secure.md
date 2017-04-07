---
title: "Perfil VPN por aplicativo para Android – Pulse Secure"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como criar um perfil VPN por aplicativo para dispositivos Android gerenciados pelo Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 2c79f5f796152e930c4a952388541383ab50e595
ms.lasthandoff: 03/17/2017


---

# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Use um perfil personalizado do Microsoft Intune para criar um perfil de VPN por aplicativo para dispositivos Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Você pode criar um perfil de VPN por aplicativo para dispositivos Android 5.0 e posterior gerenciados pelo Intune. Primeiro, crie um perfil de VPN que usa o tipo de conexão Pulse Secure. Em seguida, crie uma política de configuração personalizada que associa o perfil de VPN com aplicativos específicos.

Depois que você implantar a política para os grupos de usuários ou o dispositivo Android, os usuários deverão iniciar o PulseSecure VPN. O PulseSecure permitirá o tráfego apenas de aplicativos especificados para usar a conexão VPN aberta.

> [!NOTE]
>
> Para este perfil, há suporte apenas para o tipo de conexão Pulse Secure.


## <a name="step-1-create-a-vpn-profile"></a>Etapa 1: Criar um perfil de VPN


1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha da lista de perfis, escolha **Criar Perfil**.
3. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil VPN.
4. Na lista suspensa **Plataforma**, escolha **Android**.
5. Na lista suspensa **Tipo de perfil**, escolha **VPN**.
3. Escolha **Configurações** > **Definir** e defina o perfil VPN de acordo com as configurações em [Como definir as configurações de VPN](how-to-configure-vpn-settings.md) e [Configurações VPN do Intune para dispositivos Android](vpn-for-android.md).

Anote o nome do perfil de VPN para uso na etapa seguinte. Por exemplo, **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Etapa 2: Criar uma política de configuração personalizada

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, clique em **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil personalizado.
5. Na lista suspensa **Plataforma**, escolha **Android**.
6. Na lista suspensa **Tipo de perfil**, escolha **Personalizado**.
7. Escolha **Configurações** > **Definir**.
3. Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
    - Insira um nome para a configuração.
    - Para **Tipo de dados**, especifique **Cadeia de caracteres**.
    - Para **OMA-URI**, especifique esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/PackageList**, em que*Nome* é o nome do perfil de VPN que você anotou na Etapa 1. Nesse exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Em **Valor**, crie uma lista separada por ponto e vírgula dos pacotes a serem associados ao perfil. Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: **com.microsoft.office.excel;com.android.chrome**.

![Exemplo de política personalizada de VPN por aplicativo Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Definir sua lista de aplicativos como lista de bloqueios ou lista de permissões (opcional)
  Você pode especificar uma lista de aplicativos que *não podem* usar a conexão VPN usando o valor **BLACKLIST**. Todos os outros aplicativos se conectarão por meio da VPN.
Como alternativa, você pode usar o valor **WHITELIST** para especificar uma lista de aplicativos que *podem* usar a conexão VPN. Aplicativos que não estão na lista não se conectarão por meio da VPN.
  1.    Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
  2.    Insira um nome para a configuração.
  3.    Para **Tipo de dados**, especifique **Cadeia de caracteres**.
  4.    Para **OMA-URI**, use esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/Mode**, em que*Nome* é o nome do perfil de VPN que você anotou na Etapa 1. Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  5.    Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Etapa 3: atribuir ambas as políticas

Use as instruções em [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md) para atribuir os dois perfis para os dispositivos ou usuários necessários.

