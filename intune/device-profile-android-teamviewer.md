---
title: Administrar dispositivos remotamente no Microsoft Intune – Azure | Microsoft Docs
description: Exibir as funções necessárias para usar o TeamViewer, como instalar o conector do TeamViewer e diretrizes passo a passo para administrar dispositivos remotamente usando o Microsoft Intune no Portal do Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/05/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd2d9f0a0caf87eb75ba3a9cdc123e69425ceb8b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61509715"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Usar o TeamViewer para administrar remotamente os dispositivos do Intune

Os dispositivos gerenciados pelo Intune podem ser administrados remotamente usando o [TeamViewer](https://www.teamviewer.com). O TeamViewer é um programa de terceiros que você compra separadamente. Este tópico mostra como configurar o TeamViewer no Intune e como administrar remotamente um dispositivo. 

## <a name="prerequisites"></a>Pré-requisitos

- Use um dispositivo compatível. Dispositivos Android, Windows, iOS e macOS gerenciados pelo Intune são compatíveis com administração remota. Talvez o TeamViewer não seja compatível com o Windows Holographic (HoloLens), o Windows Team (Surface Hub) ou o Windows 10 S. Para obter informações sobre compatibilidade, consulte o [TeamViewer](https://www.teamviewer.com) e saiba mais sobre as atualizações.

- O administrador do Intune no Portal do Azure precisa ter as seguintes [funções do Intune](role-based-access-control.md):  

    - **Atualizar assistência remota**: permite que os administradores modifiquem as configurações do conector do TeamViewer
    - **Solicitar assistência remota**: permite que os administradores iniciem uma nova sessão de assistência remota para qualquer usuário. Os usuários com essa função não são limitados por qualquer função do Intune dentro de um escopo. Além disso, usuários ou grupos de dispositivos atribuídos com uma função do Intune dentro de um escopo também podem solicitar assistência remota. 

- Uma conta do [TeamViewer](https://www.teamviewer.com) com as credenciais de conexão. Apenas algumas licenças do TeamViewer podem dar suporte à integração com o Intune. Para ver as necessidades específicas do TeamViewer, confira [TeamViewer Integration Partner: Microsoft Intune](https://www.teamviewer.com/integrations/microsoft-intune/) (Parceiro de Integração do TeamViewer: Microsoft Intune).

Ao usar o TeamViewer, você permite que o Conector do TeamViewer para o Intune crie sessões do TeamViewer, leia dados do Active Directory e salve o token de acesso de conta do TeamViewer.

## <a name="configure-the-teamviewer-connector"></a>Configurar o conector do TeamViewer

Para fornecer assistência remota aos dispositivos, configure o conector do TeamViewer do Intune, de acordo com as seguintes etapas:

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** e pesquise o **Microsoft Intune**.
2. Em **Microsoft Intune**, selecione **Dispositivos** e, em seguida, selecione **Conector do TeamViewer**.
3. Selecione **Conectar** e, em seguida, aceite o contrato de licença.
4. Selecione **Efetuar logon no TeamViewer para autorizar**.
5. Uma página da Web é aberta no site do TeamViewer. Insira suas credenciais da licença do TeamViewer e, em seguida, **Entre**.

## <a name="remotely-administer-a-device"></a>Administrar um dispositivo remotamente

Depois que o conector está configurado, você está pronto para administrar remotamente um dispositivo. Use as etapas a seguir: 

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** e pesquise o **Microsoft Intune**.
2. Em **Microsoft Intune**, selecione **Dispositivos** e, em seguida, selecione **Todos os dispositivos**.
3. Na lista, selecione o dispositivo que você deseja administrar remotamente. Nas propriedades do dispositivo, selecione **Nova Sessão de Assistência Remota**.
4. Depois que o Intune se conectar ao serviço do TeamViewer, você verá algumas informações sobre o dispositivo. **Conecte-se** para iniciar a sessão remota.

![Usar o TeamViewer para administrar remotamente um dispositivo Android – exemplo](./media/android-teamviewer.png)

Quando você inicia uma sessão remota, os usuários veem um sinalizador de notificação no ícone do aplicativo Portal da Empresa no dispositivo. Uma notificação também aparece quando o aplicativo é aberto. Os usuários podem então aceitar a solicitação de assistência remota.

> [!NOTE]
> Os dispositivos Windows registrados usando métodos "sem usuário", como o DEM e o WCD, não mostram a notificação do TeamViewer no aplicativo Portal da Empresa. Nesses cenários, é recomendável usar o portal do TeamViewer para gerar a sessão.

No TeamViewer, você pode realizar uma série de ações no dispositivo, incluindo assumir o controle dele. Para saber todos os detalhes do que você pode fazer, consulte as [Diretrizes do TeamViewer](https://www.teamviewer.com/support/documents/).

Quando concluído, feche a janela do TeamViewer.
