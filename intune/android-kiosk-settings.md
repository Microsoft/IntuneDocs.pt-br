---
title: Configurações de quiosque para Android no Microsoft Intune – Azure | Microsoft Docs
description: Configure seus dispositivos de quiosque Android como quiosques de um único aplicativo e de vários aplicativos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5cd16a351beefd851d51175717abd4400382c216
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185229"
---
# <a name="kiosk-settings-for-android-devices-in-intune"></a>Configurações de quiosque para dispositivos Android no Intune

Você pode configurar um dispositivo no modo de quiosque de aplicativo único ou de vários aplicativos usando as definições de configuração do dispositivo. Quando um dispositivo está no modo de quiosque, o uso do dispositivo é limitado aos aplicativos ou links da Web definidos pelo perfil de restrição. 

## <a name="restrict-an-android-kiosk-device-to-a-single-app"></a>Restringir o um dispositivo de quiosque Android a um único aplicativo

Quando o perfil de restrição de um dispositivo de quiosque está definido como **Modo de quiosque** = **quiosque de um único aplicativo**, os usuários só podem acessar um único aplicativo. Quando um dispositivo configurado nesse modo é iniciado, o aplicativo específico também é iniciado. Os usuários são impedidos de abrir novos aplicativos e alterar o aplicativo em execução.

1. Verifique se o aplicativo que você deseja usar no dispositivo do quiosque foi [implantado no dispositivo](apps-deploy.md) e se você atribui o aplicativo ao grupo de dispositivos criado para os dispositivos de quiosque.
2. Acesse o [portal do Intune](https://portal.azure.com) e escolha **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Na folha **Criar perfil**, especifique os campos a seguir:
     - **Nome**
     - **Plataforma**: Android Enterprise
     - **Tipo de perfil**: somente o Proprietário do Dispositivo > Restrições do dispositivo
4. Escolha **Configurações** > **Quiosque**.
5. Para **Modo de quiosque**, escolha **Quiosque de um único aplicativo**.
6. Escolha **Selecionar um aplicativo gerenciado** e, em seguida, selecione o aplicativo do Google Play gerenciado que você deseja que seja o único aplicativo disponível para dispositivos que usam esse perfil.
7. Escolha **OK** > **OK** > **OK** > **Criar**.
8. Escolha o perfil que você acabou de criar > **Atribuições**.
9. Em **Atribuir a**, escolha **Grupos selecionados**.
10. Escolha **Selecionar grupos a serem incluídos** > escolha o grupo de dispositivos que você criou para seus dispositivos de quiosque > **Selecionar**.

## <a name="restrict-a-kiosk-device-to-a-set-of-apps-or-web-links"></a>Restringir um dispositivo de quiosque a um conjunto de aplicativos ou links da Web

Quando o perfil de restrição do dispositivo de quiosque está definido como **Modo de quiosque** = **Quiosque de vários aplicativos**, os usuários podem acessar apenas o número limitado de aplicativos que você configura. Você também pode definir um conjunto de links da Web que os usuários podem visitar. Quando a política está aplicada, são exibidos ícones para os aplicativos permitidos na tela inicial dos usuários.

Para definir um dispositivo de quiosque Android para vários aplicativos, siga estas etapas principais:

1. [Importar e implantar o aplicativo Tela Inicial Gerenciada por meio do Google Play gerenciado](#import-and-deploy-the-managed-home-screen-app)
2. [Adicionar e atribuir aplicativos que podem ser usados no modo de quiosque](#add-and-assign-apps-that-can-be-used-in-kiosk-mode)
3. (Opcional) [Adicionar links da Web que podem ser usados no modo de quiosque](#add-web-links-that-can-be-used-in-kiosk-mode)

### <a name="import-and-deploy-the-managed-home-screen-app"></a>Importar e implantar o aplicativo Tela Inicial Gerenciada

1. Navegue até a [página da Tela Inicial Gerenciada no Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) e entre com a mesma conta usada para outros aplicativos do Google Play.
2. Escolha **Aprovar**.
3. Acesse o [Portal do Intune](https://portal.azure.com) e escolha **Aplicativos clientes** > **Google Play Gerenciado** > **Sincronizar**.
4. Escolha **Aplicativos** > **Tela Inicial Gerenciada** > **Atribuições** > **Adicionar grupo**.
5. Em **Tipo de atribuição**, escolha **Obrigatória**.
6. Escolher **Grupos Incluídos** > **Selecionar grupos a serem incluídos** > escolha o grupo de dispositivos que você criou para seus dispositivos de quiosque > **Selecionar** > **OK** > **OK** > **Salvar**.

> [!NOTE]
> Quando você adicionar o aplicativo Tela Inicial Gerenciada ao perfil de quiosque de vários aplicativos, um ícone será adicionado. Porém, nada acontece quando você seleciona o ícone. Como resultado, você não precisa adicionar o aplicativo Tela Inicial Gerenciada ao perfil de quiosque de vários aplicativos.

### <a name="add-and-assign-apps-that-can-be-used-in-kiosk-mode"></a>Adicionar e atribuir aplicativos que podem ser usados no modo de quiosque

Para cada aplicativo que você deseja disponibilizar nos dispositivos de quiosque, siga estas etapas:

1. [Adicione o aplicativo ao Intune](store-apps-android.md).
2. Escolha **Aplicativos clientes** > **Aplicativos** > escolha o aplicativo > **Atribuições** > **Adicionar grupo**.
3. Em **Tipo de atribuição**, escolha **Obrigatória**.
4. Escolher **Grupos Incluídos** > **Selecionar grupos a serem incluídos** > escolha o grupo de dispositivos que você criou para seus dispositivos de quiosque > **Selecionar** > **OK** > **OK** > **Salvar**.

### <a name="add-web-links-that-can-be-used-in-kiosk-mode"></a>Adicionar links da Web que podem ser usados no modo de quiosque

1. Acesse o [Portal do Intune](https://portal.azure.com) e escolha **Aplicativos clientes** > **Aplicativos** > **Adicionar**.
2. Em **Tipo de aplicativo**, escolha **Link da Web**.
3. Escolha **Configurar** e forneça as informações necessárias. Você não precisa adicionar uma imagem de logotipo porque ela será recuperada automaticamente do favicon.ico do site.
4. Escolha **OK** > **Adicionar**.

Verifique se você implantou um aplicativo Web aos dispositivos de quiosque. Para obter mais informações, veja [Adicionar aplicativos Web para o Microsoft Intune](web-app.md).

### <a name="create-a-multi-app-kiosk-profile"></a>Criar um perfil de quiosque de vários aplicativos

1. Acesse o [portal do Intune](https://portal.azure.com) e escolha **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Na folha **Criar perfil**, especifique os campos a seguir:
     - **Nome**: digite um nome intuitivo
     - **Plataforma**: Android Enterprise
     - **Tipo de perfil**: somente o Proprietário do Dispositivo > Restrições do dispositivo
4. Escolha **Configurações** > **Quiosque**.
5. Para **Modo de quiosque**, escolha **Quiosque de vários aplicativos**.
6. Escolha **Adicionar** e, em seguida, selecione os aplicativos ou links da Web que você deseja disponibilizar aos dispositivos que usam esse perfil.
7. Escolha **OK** > **OK** > **OK** > **Criar**.
8. Escolha o perfil que você acabou de criar > **Atribuições**.
9. Em **Atribuir a**, escolha **Grupos selecionados**.
10. Escolha **Selecionar grupos a serem incluídos** > escolha o grupo de dispositivos que você criou para seus dispositivos de quiosque > **Selecionar** > **Salvar**.

## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
