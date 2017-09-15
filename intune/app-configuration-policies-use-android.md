---
title: "Usar políticas de configuração de aplicativo do Intune para o Android for Work"
titlesuffix: Azure portal
description: "Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo Android for Work quando ele é executado."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b73202a1a68bd2dd3dcbfa86c21cb09ae00056c
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Como usar as políticas de configuração de aplicativo do Microsoft Intune no Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use as políticas de configuração de aplicativo do Microsoft Intune para fornecer as configurações que podem estar disponíveis quando os usuários executam um aplicativo Android for Work. Nem todos os aplicativos dão suporte à configuração de aplicativo. Verifique com o desenvolvedor do aplicativo se ele criou o aplicativo para dar suporte a políticas de configuração de aplicativo.

As políticas de configuração de aplicativo podem ajudá-lo a predefinir as configurações de aplicativo disponíveis para os usuários antes que eles executem o aplicativo. Alguns aplicativos Android dão suporte a opções de configurações gerenciadas que podem ser definidas no Portal do Azure com o [designer de configuração](#use-configuration-designer). Algumas definições de configuração em aplicativos (como aquelas com os tipos Pacote) não podem ser configuradas com o designer de configuração.  Você precisará usar o [editor de JSON](#use-json-editor) para esses valores.   As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.

Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.

## <a name="use-configuration-designer"></a>Usar o designer de configuração

1. No Portal do Azure, escolha **Aplicativos móveis**. Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.
2. Defina os seguintes detalhes:
    - **Nome** – O nome do perfil que será exibido no Portal do Azure
    - **Descrição** – a descrição do perfil que será exibida no Portal do Azure
    - **Plataforma** – selecione **Android**
    - A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.
3. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.  Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune
4. Selecione **Definições de configuração**.
5. Em **Formato de definições de configuração**, selecione **Usar o designer de configuração**.
6. Escolha **Adicionar**. Uma lista das definições de configuração disponíveis é exibida. A lista inclui:
    - **Chaves de configuração** – nome da configuração.
    - **Tipo de valor** – a configuração que pode ser definida, por exemplo, **Booliano** ou **Cadeia de caracteres**.
    - **Descrição** – uma descrição da definição de configuração.
7. Marque as caixas de seleção das configurações que você deseja definir com esse perfil e, em seguida, clique em **OK**.
8. É exibida uma lista das configurações selecionadas com o **Valor de configuração** disponível. Especifique um valor para cada configuração e, em seguida, clique em **OK**.

## <a name="use-json-editor"></a>Usar o editor de JSON

1. No Portal do Azure, escolha **Aplicativos móveis**. Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.
2. Defina os seguintes detalhes:
    - **Nome** – O nome do perfil que será exibido no Portal do Azure
    - **Descrição** – a descrição do perfil que será exibida no Portal do Azure
    - **Plataforma** – selecione **Android**
    - A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.
3. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.  Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.
5. Selecione **Definições de Configuração**.
6. Em **Formato de definições de configuração**, selecione **Inserir editor de JSON**.
7. No editor, é possível definir os valores JSON para as definições de configuração. Escolha **Baixar modelo de JSON** para baixar um arquivo de exemplo que, em seguida, pode ser configurado.
8. Quando terminar, escolha **OK** e, em seguida, clique em **Adicionar**.

A política será criada e aparecerá na folha da lista de políticas.



Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Pré-configurar o estado de concessão de permissões para aplicativos

Você também pode pré-configurar a permissão para que os aplicativos acessem os recursos do dispositivo Android. Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso à localização ou à câmera do dispositivo solicitam que os usuários aceite ou negue as permissões. Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final deverá conceder a permissão de aplicativo para usar o microfone.

1. No Portal do Azure, escolha **Aplicativos móveis**. Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.
2. Defina os seguintes detalhes:
    - **Nome** – O nome do perfil que será exibido no Portal do Azure
    - **Descrição** – a descrição do perfil que será exibida no Portal do Azure
    - **Plataforma** – selecione **Android**
    - A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.
3. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.  Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.
5. Selecione **Permissões** e, em seguida, escolha **Adicionar**.
6. Selecione na lista de permissões de aplicativo disponíveis e, em seguida, escolha **OK**.
7. Selecione uma opção para cada permissão a ser concedida com esta política:
    - **Prompt** – solicite que o usuário aceite ou negue.
    - **Concessão automática** – aprove automaticamente sem notificar o usuário.
    - **Negação automática** – negue automaticamente sem notificar o usuário.
8. Para atribuir a política de configuração de aplicativo, selecione a política de configuração de aplicativo, selecione **Atribuição** e, em seguida, selecione **Selecionar grupos**.
9. Selecione os grupos de usuários a serem atribuídos e, em seguida, escolha **Selecionar**.
10. Escolha **Salvar** para atribuir a política.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.

