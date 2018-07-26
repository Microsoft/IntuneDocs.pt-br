---
title: Perfil de VPN por aplicativo personalizado para Android
titlesuffix: Microsoft Intune
description: Saiba como criar um perfil VPN por aplicativo para dispositivos Android gerenciados pelo Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d8357a63f80552ff4b6ebd6d1da2998e675dd00
ms.sourcegitcommit: 08e1b0d45c84eb9525a0a59f5540d41434da2814
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39146672"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Use um perfil personalizado do Microsoft Intune para criar um perfil de VPN por aplicativo para dispositivos Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você pode criar um perfil de VPN por aplicativo para dispositivos Android 5.0 e posterior gerenciados pelo Intune. Primeiro, crie um perfil de VPN que use o tipo de conexão Pulse Secure ou Citrix. Em seguida, crie uma política de configuração personalizada que associa o perfil de VPN com aplicativos específicos.

Após atribuir a política aos grupos de usuários ou de dispositivos Android, os usuários deverão iniciar o cliente de VPN Citrix ou Pulse Secure. O cliente VPN então permite somente que tráfego dos aplicativos especificados use a conexão VPN aberta.

> [!NOTE]
>
> Para este perfil, há suporte apenas para o tipo de conexão Pulse Secure e Citrix.


## <a name="step-1-create-a-vpn-profile"></a>Etapa 1: Criar um perfil de VPN


1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
2. No painel da lista de perfis, escolha **Criar perfil**.
3. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil de VPN.
4. Na lista suspensa **Plataforma**, escolha **Android**.
5. Na lista suspensa **Tipo de perfil**, escolha **VPN**.
3. Escolha **Configurações** > **Definir** e defina o perfil VPN de acordo com as configurações em [Como definir as configurações de VPN](vpn-settings-configure.md) e [Configurações VPN do Intune para dispositivos Android](vpn-settings-android.md).

Anote o valor de **Nome da Conexão** que você especificou ao criar o perfil de VPN. Esse nome será necessário na próxima etapa. Por exemplo, **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Etapa 2: Criar uma política de configuração personalizada

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
3. No painel de perfis, clique em **Criar perfil**.
4. No painel **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil personalizado.
5. Na lista suspensa **Plataforma**, escolha **Android**.
6. Na lista suspensa **Tipo de perfil**, escolha **Personalizado**.
7. Escolha **Configurações** > **Definir**.
3. No painel **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
    - Insira um nome para a configuração.
    - Para **OMA-URI**, especifique esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/PackageList**, em que *Nome* é o nome da conexão que você anotou na Etapa 1. Nesse exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Para **Tipo de dados**, especifique **Cadeia de caracteres**.
    - Em **Valor**, crie uma lista separada por ponto e vírgula dos pacotes a serem associados ao perfil. Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: **com.microsoft.office.excel;com.android.chrome**.

![Exemplo de política personalizada de VPN por aplicativo Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Definir sua lista de aplicativos como lista de bloqueios ou lista de permissões (opcional)
  Você pode especificar uma lista de aplicativos que *não podem* usar a conexão VPN usando o valor **BLACKLIST**. Todos os outros aplicativos se conectam por meio da VPN.
Como alternativa, você pode usar o valor **WHITELIST** para especificar uma lista de aplicativos que *podem* usar a conexão VPN. Os aplicativos que não estão na lista não se conectam por meio da VPN.
  1.    No painel **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
  2.    Insira um nome para a configuração.
  3.    Para **OMA-URI**, use esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/Mode**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1. Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  4.    Para **Tipo de dados**, especifique **Cadeia de caracteres**.
  5.    Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Etapa 3: atribuir ambas as políticas

Use as instruções em [Como atribuir perfis de dispositivo](device-profile-assign.md) para atribuir os dois perfis para os dispositivos ou usuários necessários.
