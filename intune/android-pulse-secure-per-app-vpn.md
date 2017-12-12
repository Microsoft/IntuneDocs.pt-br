---
title: "Perfil VPN por aplicativo para Android – Pulse Secure"
titlesuffix: Azure portal
description: Saiba como criar um perfil de VPN por aplicativo para dispositivos Android gerenciados pelo Intune.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c5b8e85ded2ea515f361c91c61744956b8112757
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Use um perfil personalizado do Microsoft Intune para criar um perfil de VPN por aplicativo para dispositivos Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você pode criar um perfil de VPN por aplicativo para dispositivos Android 5.0 e posterior gerenciados pelo Intune. Primeiro, crie um perfil de VPN que usa o tipo de conexão Pulse Secure. Em seguida, crie uma política de configuração personalizada que associa o perfil de VPN com aplicativos específicos.

Depois que você atribuir a política para os grupos de usuários ou o dispositivo Android, os usuários deverão iniciar o PulseSecure VPN. Em seguida, o PulseSecure permite que somente o tráfego dos aplicativos especificados use a conexão VPN aberta.

> [!NOTE]
>
> Para este perfil, há suporte apenas para o tipo de conexão Pulse Secure.


## <a name="step-1-create-a-vpn-profile"></a>Etapa 1: Criar um perfil de VPN


1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha da lista de perfis, escolha **Criar Perfil**.
3. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil VPN.
4. Na lista suspensa **Plataforma**, escolha **Android**.
5. Na lista suspensa **Tipo de perfil**, escolha **VPN**.
3. Escolha **Configurações** > **Definir** e defina o perfil VPN de acordo com as configurações em [Como definir as configurações de VPN](vpn-settings-configure.md) e [Configurações VPN do Intune para dispositivos Android](vpn-settings-android.md).

Anote o valor de **Nome da Conexão** que você especificou ao criar o perfil de VPN. Esse nome será necessário na próxima etapa. Por exemplo, **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Etapa 2: Criar uma política de configuração personalizada

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
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
    - Para **OMA-URI**, especifique esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/PackageList**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1. Nesse exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Em **Valor**, crie uma lista separada por ponto e vírgula dos pacotes a serem associados ao perfil. Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: **com.microsoft.office.excel;com.android.chrome**.

![Exemplo de política personalizada de VPN por aplicativo Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Definir sua lista de aplicativos como lista de bloqueios ou lista de permissões (opcional)
  Você pode especificar uma lista de aplicativos que *não podem* usar a conexão VPN usando o valor **BLACKLIST**. Todos os outros aplicativos se conectam por meio da VPN.
Como alternativa, você pode usar o valor **WHITELIST** para especificar uma lista de aplicativos que *podem* usar a conexão VPN. Os aplicativos que não estão na lista não se conectam por meio da VPN.
  1.    Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
  2.    Insira um nome para a configuração.
  3.    Para **Tipo de dados**, especifique **Cadeia de caracteres**.
  4.    Para **OMA-URI**, use esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/Mode**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1. Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  5.    Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Etapa 3: atribuir ambas as políticas

Use as instruções em [Como atribuir perfis de dispositivo](device-profile-assign.md) para atribuir os dois perfis para os dispositivos ou usuários necessários.
