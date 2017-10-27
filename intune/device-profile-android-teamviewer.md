---
title: Como administrar dispositivos remotamente usando o TeamViewer
titlesuffix: Azure portal
description: Saiba como administrar dispositivos remotamente usando o TeamViewer."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8bb3061baf42b011c98cf7b196e939448f91cff4
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2017
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a>Fornecer assistência remota para dispositivos gerenciados pelo Intune

O Intune pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que seja possível fornecer assistência remota aos usuários dos dispositivos que você gerencia. Use as informações deste tópico para começar a trabalhar.

## <a name="before-you-start"></a>Antes de começar

### <a name="supported-devices"></a>Dispositivos com suporte

Há suporte para administração remota para os seguintes dispositivos gerenciados pelo Intune:

- Dispositivos Android gerenciados pelo Intune
- Dispositivos Windows gerenciados pelo Intune que executam Windows 10, Windows 10 Mobile e posterior.

>[!NOTE]
>Não há suporte no software TeamViewer para Windows Holographic (HoloLens), Windows Team (Surface Hub) e Windows 10 S



### <a name="required-permissions"></a>Permissões necessárias

Verifique se o usuário do portal do Azure tem as seguintes permissões atribuídas a ele como uma [função do Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):
- Para permitir que o administrador modifique as configurações de conector do TeamViewer, conceda a permissão **Atualizar Assistência Remota**.
- Para permitir que o administrador inicie uma nova solicitação de assistência remota, conceda a permissão **Solicitar Assistência Remota**. Os usuários com a permissão **Solicitar Assistência Remota** podem solicitar o início de uma sessão para qualquer usuário. Eles não são limitados por qualquer escopo de atribuição de função do Intune. Os escopos de atribuição de função do Intune não limitam os dispositivos ou os usuários para os quais as solicitações de Assistência Remota podem ser iniciadas.

>[!NOTE]
>Ao habilitar o TeamViewer, você permite que o Conector do TeamViewer para o Intune crie sessões do TeamViewer, leia dados do Active Directory e salve o token de acesso de conta do TeamViewer.

### <a name="configure-the-intune-teamviewer-connector"></a>Configurar o conector do TeamViewer para o Intune

Para que seja possível fornecer assistência remota aos dispositivos, será necessário configurar o conector do Intune TeamViewer, seguindo as seguintes etapas:


1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Instalação** > **Conector do TeamViewer**.
5. Na folha **Conector do TeamViewer**, clique em **Habilitar** e, em seguida, exiba e aceite o contrato de licença de serviço do TeamViewer.
6. Escolha **Fazer Logon no TeamViewer e Autorizar**.
7. Uma página da Web é aberta no site do TeamViewer. Insira suas credenciais de licença do TeamViewer e, em seguida, clique em **Entrar**.


## <a name="how-to-remotely-administer-a-device"></a>Como administrar um dispositivo remotamente

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Gerenciar** > **Todos os dispositivos**.
5. Selecione o dispositivo que você deseja administrar remotamente e, em seguida, na folha de propriedades do dispositivo, escolha **Mais** > **Nova Sessão de Assistência Remota**.
6. Depois que o Intune se conectar ao serviço do TeamViewer, você verá algumas informações sobre o dispositivo. Escolha **Conectar** para iniciar a sessão remota.

![Exemplo do TeamViewer para Android](./media/android-teamviewer.png)

Na janela do TeamViewer, você pode executar uma variedade de ações remotas no dispositivo, incluindo o controle remoto do dispositivo. Para obter detalhes completos das ações que podem ser realizadas, consulte a [documentação do TeamViewer](https://www.teamviewer.com/support/documents/).

Quando tiver concluído, feche a janela do TeamViewer.

## <a name="next-steps"></a>Próximas etapas

Um usuário final verá um sinalizador de notificação no ícone do aplicativo do Portal da Empresa no dispositivo e também verá uma notificação quando o aplicativo for aberto. Em seguida, ele poderá aceitar a solicitação de assistência remota.

