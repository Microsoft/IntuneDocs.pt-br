---
title: Como criar perfis VPN personalizados com o Microsoft Intune
titleSuffix: Azure portal
description: "Use configurações personalizadas para criar perfis de VPN no Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7a3ab162ee950527c8d78123b4fd0a44c8bd7f29
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Como criar perfis de VPN personalizados no Microsoft Intune

## <a name="create-a-custom-configuration"></a>Criar uma configuração personalizada
É possível usar políticas de configuração personalizada do Intune para criar perfis VPN para:

* Dispositivos que executam o Android 4 e posterior
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Dispositivos que executam o Windows Phone 8.1 e versões posteriores
* Dispositivos registrados que executam o Windows 10 Desktop 
* Dispositivos que executam o Windows 10 Mobile

Esse tipo de política pode ser útil quando as políticas de VPN padrão do Intune não contêm as configurações que você deseja usar.

## <a name="to-create-a-custom-configuration-policy"></a>Para criar uma política de configuração personalizada:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
4. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
5. Na folha de perfis, escolha **Criar Perfil**.
6. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de VPN.
7. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo personalizado:
    - **Android**
    - **iOS** (configurado usando um arquivo exportado do Apple Configurator).
    - **macOS** (configurado usando um arquivo exportado do Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.
7. Na folha **Configurações personalizadas de OMA-URI**, para cada configuração de URI que você deseja especificar, escolha **Adicionar**, forneça as informações solicitadas e escolha **OK**. Aqui está um exemplo:

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](./media/Intune_Add_VPN_URI.png)

4.  Depois de inserir todas as configurações de URI necessárias, escolha **OK** e, em seguida, na folha **Criar Perfil**, escolha **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).




