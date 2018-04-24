---
title: Como criar perfis VPN personalizados com o Microsoft Intune
titleSuffix: ''
description: Use configurações personalizadas para criar perfis de VPN no Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Como criar perfis de VPN personalizados no Microsoft Intune

É possível usar as políticas de configuração personalizada do Intune para criar perfis VPN para as seguintes plataformas:

* Android 4 e posterior
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Windows Phone 8.1 e posterior
* Dispositivos registrados que executam o Windows 10 Desktop 
* Windows 10 Mobile

Esse tipo de política pode ser útil quando as políticas de VPN padrão do Intune não contiverem as configurações que você deseja usar.

## <a name="to-create-a-custom-configuration-policy"></a>Para criar uma política de configuração personalizada:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
5. No painel de perfis, escolha **Criar perfil**.
6. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de VPN.
7. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo personalizado:
    - **Android**
    - **Android for Work**
    - **iOS** (configurado usando um arquivo exportado do Apple Configurator).
    - **macOS** (configurado usando um arquivo exportado do Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.
7. No painel **Configurações personalizadas de OMA-URI**, para cada configuração de URI que você deseja especificar, escolha **Adicionar**, forneça as informações solicitadas e escolha **OK**. Aqui está um exemplo:

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](./media/Intune_Add_VPN_URI.png)

4.  Depois de inserir todas as configurações de URI necessárias, escolha **OK** e, em seguida, no painel **Criar perfil**, selecione **Criar**.

O perfil é criado e aparece no painel da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).




