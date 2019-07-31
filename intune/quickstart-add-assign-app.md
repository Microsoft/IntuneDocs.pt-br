---
title: Início Rápido – Adicionar e atribuir um aplicativo cliente
titleSuffix: Microsoft Intune
description: Neste início rápido, você usará o Microsoft Intune para adicionar e atribuir um aplicativo cliente.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dab6f5c8-1ebb-42c4-a7a7-7af001f94e15
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd310cea29a3dac7a178d88c0f29d1a4e36ad37d
ms.sourcegitcommit: d2ac912b834c4840de9cc92ba1815b6ecfbfb52b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68482803"
---
# <a name="quickstart-add-and-assign-a-client-app"></a>Início Rápido: Adicionar e atribuir um aplicativo cliente

Neste início rápido, você usará o Intune para adicionar e atribuir um aplicativo cliente à força de trabalho da sua empresa. Uma das prioridades do administrador é garantir que os usuários finais tenham acesso aos aplicativos necessários para realizar seu trabalho. 

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir este início rápido, é preciso [criar um usuário](quickstart-create-user.md), [criar um grupo](quickstart-create-group.md) e [registrar um dispositivo](quickstart-setup-auto-enrollment.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um [Administrador Global ou um Administrador de Serviços do Intune](users-add.md#types-of-administrators). Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="add-the-client-app-to-intune"></a>Adicione o aplicativo cliente ao Intune

Um aplicativo pode ser incluído para que o Intune possa gerenciar os aspectos do aplicativo. 

Use as seguintes etapas para adicionar um aplicativo ao Intune:
1. No [Intune](https://aka.ms/intuneportal), selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. 
2. Selecione **Windows 10** na seção **Pacote do Office 365** da caixa suspensa **Tipo de aplicativo**.
3. Selecione **Configurar Pacote de Aplicativos** para selecionar os aplicativos do Office a serem atribuídos ao usuário do Intune.
4. Clique em **OK** para aceitar os aplicativos selecionados padrão.
5. Selecione **Informações do Pacote de Aplicativo**.
6. Insira o **pacote de aplicativo do Microsoft Office 365** como **Nome do Pacote**.
7. Insira o **pacote de aplicativo do Microsoft Office 365** como a **Descrição do Pacote**.
8. Clique em **Sim** próximo a **Exibir isso como um aplicativo em destaque no Portal da Empresa**.
9. Clique em **OK**.

    ![Captura de tela da adição de informações do aplicativo](media/quickstart-add-assign-app/quickstart-add-assign-app-01.png)

10. Selecione **Configurações do Pacote de Aplicativos**.
11. Na caixa suspensa **Canal de Atualização**, selecione **Mensal**.
12. Clique em **OK** > **Adicionar**.

## <a name="assign-the-app-to-a-group"></a>Atribuir um aplicativo a um grupo

Depois de adicionar um aplicativo ao Microsoft Intune, é possível atribuí-lo a grupos de usuários ou dispositivos.

> [!NOTE]
> Este início rápido se baseia nos guias de início rápido anteriores desta série. Consulte [pré-requisitos](quickstart-add-assign-app.md#prerequisites) neste início rápido para obter detalhes.

Use as seguintes etapas para atribuir um aplicativo a um grupo:
1. No [Intune](https://aka.ms/intuneportal), selecione **Aplicativos cliente** > **Aplicativos**. 
2. Selecione o aplicativo que deseja atribuir a um grupo.
3. Clique em **Atribuições** > **Adicionar grupo** para exibir a folha **Adicionar grupo**.
4. Selecione **Disponível para dispositivos registrados** na caixa suspensa **Tipo de atribuição**. 
5. Clique em **Grupos Incluídos** > **Selecionar grupos a serem incluídos** > **Testadores Contoso**.
6. Clique em **Selecionar** > **OK** > **OK** > **Salvar** para atribuir o grupo.

Agora você atribuiu o aplicativo ao grupo **Testadores Contoso**.

## <a name="install-the-app-on-the-enrolled-device"></a>Instalar o aplicativo no dispositivo registrado

Você deve instalar e usar o aplicativo do Portal da Empresa para instalar o aplicativo **Tarefas Pendentes do Contoso** disponibilizado pelo Intune. Use as etapas a seguir para verificar se o aplicativo está disponível para o usuário do dispositivo registrado.

1. Faça logon no seu dispositivo registrado do Windows 10 Desktop.

    > [!IMPORTANT]
    > O dispositivo deve estar [registrado no Intune](quickstart-enroll-windows-device.md). Além disso, você deve entrar no dispositivo usando uma conta contida no grupo atribuído ao aplicativo.

2. No menu **Iniciar**, abra a **Microsoft Store**. Em seguida, localize o aplicativo do **Portal da Empresa** e instale-o.
3. Inicie o aplicativo do **Portal da Empresa**.
4. Clique no aplicativo que adicionou usando o Intune. Neste início rápido, você adicionou o aplicativo do **pacote de aplicativos do Microsoft Office 365**.

    > [!NOTE]
    > Caso não tenha atribuído com êxito todos os aplicativos ao usuário do Intune, você verá a seguinte mensagem: *Seu administrador de TI não disponibilizou nenhum aplicativo para você.*

5. Clique em **Instalar**.

Se a empresa precisar que você atribua o aplicativo do Portal da Empresa à sua força de trabalho, você poderá atribuir manualmente o aplicativo do Portal da Empresa do Windows 10 diretamente do Intune. Para obter mais informações, confira [Adicionar manualmente o aplicativo do Portal da Empresa do Windows 10 usando o Microsoft Intune](store-apps-company-portal-app.md).

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você adicionou aplicativos ao Intune, atribuiu aplicativos a um grupo e instalou os aplicativos no dispositivo registrado do Windows 10 Desktop. Para obter mais informações sobre como gerenciar aplicativos no Intune, confira [O que é o gerenciamento de aplicativos do Microsoft Intune?](app-management.md)

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Criar e atribuir uma política de proteção de aplicativo](quickstart-create-assign-app-policy.md)
