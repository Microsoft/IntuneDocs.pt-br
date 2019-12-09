---
title: Configurar o Google Chrome para dispositivos Android usando o Intune
titleSuffix: Microsoft Intune
description: Use as políticas de configuração do Intune com o Google Chrome para dispositivos Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: c344a518890a2309a7805d61a5675e2646029bbb
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564036"
---
# <a name="configure-google-chrome-for-android-devices-using-intune"></a>Configurar o Google Chrome para dispositivos Android usando o Intune 

Você pode usar uma política de configuração de aplicativos do Intune para configurar o Google Chrome para dispositivos Android. As configurações do aplicativo podem ser aplicadas automaticamente. Por exemplo, você pode definir especificamente os indicadores e as URLs que deseja bloquear ou permitir.

## <a name="prerequisites"></a>Pré-requisitos

- O dispositivo Android Enterprise do usuário deve estar registrado no Intune. Para saber mais, confira [Configurar o registro de dispositivos de perfil de trabalho Android Enterprise](~/enrollment/android-work-profile-enroll.md).
- O Google Chrome é adicionado como um aplicativo gerenciado do Google Play. Para obter mais informações sobre o Google Play gerenciado, confira [Conectar sua conta do Intune à sua conta gerenciada do Google Play](~/enrollment/connect-intune-android-enterprise.md).

## <a name="add-the-google-chrome-app-to-intune"></a>Adicionar o aplicativo Google Chrome ao Intune

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar** e adicione o aplicativo **Google Play Gerenciado**.
3. Acesse o Google Play gerenciado, pesquise por **Google Chrome** e aprove.

    ![Pesquisar e aprovar o Google Chrome](~/apps/media/apps-configure-chrome-android/search.png)

4. Atribua o Google Chrome a um grupo de usuários como um tipo de aplicativo necessário. O Google Chrome será implantado automaticamente quando o dispositivo estiver registrado no Intune.

Para obter detalhes adicionais sobre como adicionar um aplicativo gerenciado do Google Play ao Intune, confira [Aplicativos gerenciados da Google Play Store](~/apps/apps-add-android-for-work.md#managed-google-play-store-apps).

## <a name="add-app-configuration-for-managed-ae-devices"></a>Adicionar configuração de aplicativo em dispositivos AE gerenciados

1. No painel [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), selecione **Políticas de configuração de aplicativos** > **Adicionar**.
2. Adicione o nome da política, escolha **Dispositivos gerenciados**, em Tipo de registro do dispositivo, e **Android**, em Plataforma.

    ![Adicionar política de configuração do Google Chrome](~/apps/media/apps-configure-chrome-android/add-policy.png)

3. Clique em **Aplicativo associado** e selecione **Google Chrome**.

    ![Na opção Aplicativo associado, selecione Google Chrome](~/apps/media/apps-configure-chrome-android/associated-app.png)

4. Clique em **Definições de configuração**, selecione **Usar designer de configuração** e clique em **Adicionar** para selecionar as chaves de configuração.

    ![Adicionar Usar o designer de configuração](~/apps/media/apps-configure-chrome-android/configuration.png)

    Veja abaixo exemplos de configurações comuns:
    - **Bloquear o acesso a uma lista de URLs**: `["*"]`
    - **Permitir o acesso a uma lista de URLs**: `["baidu.com", "youtube.com", "chromium.org", "chrome://*"]`
    - **Indicadores gerenciados**: `[{"toplevel_name": "My managed bookmarks folder"  },  {"url": "baidu.com",   "name": "Baidu"},  {"url": "youtube.com", "name": "Youtube"},  {"name": "Chrome links",  "children": [{"url": "chromium.org", "name": "Chromium"},    {"url": "dev.chromium.org", "name": "Chromium Developers"}]}]`
    - **Disponibilidade no modo de navegação anônima**: `Incognito mode disabled`

    Depois que as definições de configuração forem adicionadas com o designer de configuração, elas serão listadas em uma tabela. 

    ![Configurações padrão](~/apps/media/apps-configure-chrome-android/common-settings.png)

    As configurações acima criam indicadores e bloqueiam o acesso a todas as URLs, exceto `baidu.com`, `yahoo.com`, `chromium.org` e `chrome://`.

5. Clique em **OK** e em **Adicionar** para incluir sua política de configuração ao Intune.
6. Atribua essa política de configuração a um grupo de usuários. Para saber mais, confira [Atribuir aplicativos a grupos com o Microsoft Intune](~/apps/apps-deploy.md). 

## <a name="verify-the-device-settings"></a>Verifique as configurações do dispositivo

Depois que o dispositivo Android estiver registrado no Android Enterprise, o aplicativo gerenciado do Google Chrome com o ícone do portfólio será implantado automaticamente.
 
   <img alt="Managed Google Chrome with the portfolio icon" src="~/apps/media/apps-configure-chrome-android/chrome-icon.png" width="350">

Inicie o Google Chrome para ver as configurações aplicadas.

   Indicadores:<br>
   <img alt="Bookmarks" src="~/apps/media/apps-configure-chrome-android/bookmarks.png" width="350">

   URL bloqueada:<br>
   <img alt="Blocked URL" src="~/apps/media/apps-configure-chrome-android/blocked-url.png" width="350">

   Permitir URL:<br>
   <img alt="Allow URL" src="~/apps/media/apps-configure-chrome-android/allowed-url.png" width="350">

   Guia anônima:<br>
   <img alt="Incognito tab" src="~/apps/media/apps-configure-chrome-android/incognito-tab.png" width="350">

## <a name="troubleshooting"></a>Solução de problemas

1. Verifique o portal do Intune para monitorar o status de implantação da política.

    ![Monitorar o status de implantação da política](~/apps/media/apps-configure-chrome-android/monitor-status.png)

2. Inicie o Google Chrome e acesse **chrome://policy**. Podemos confirmar se as configurações foram aplicadas com sucesso.

    ![Confirmar se as configurações foram aplicadas com sucesso](~/apps/media/apps-configure-chrome-android/confirm.png)

## <a name="additional-information"></a>Informações adicionais

- [Adicionar políticas de configuração de aplicativo para dispositivos Android Enterprise gerenciados](~/app-configuration-policies-use-android.md)
- [Lista de políticas do Chrome Enterprise](https://cloud.google.com/docs/chrome-enterprise/policies/)

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre dispositivos Android Enterprise totalmente gerenciados, confira [Configurar o registro do Intune para dispositivos Android Enterprise totalmente gerenciados](~/enrollment/android-fully-managed-enroll.md).
