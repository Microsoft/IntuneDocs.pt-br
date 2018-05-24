---
title: Remova seu dispositivo Windows do Intune
description: Descreve como remover um dispositivo Windows do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a3cad6a73b3455790441c594933d599b2c6e89f9
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="remove-your-windows-device-from-intune-management"></a>Remover seu dispositivo Windows do gerenciamento do Intune

Remova um dispositivo com Windows registrado do Intune quando você não quiser ou precisar mais:  
* Use seu dispositivo para o trabalho ou escola. 
* Acesse email, aplicativos ou outros recursos de trabalho ou estudante.

Após a remoção, não será possível acessar os recursos de trabalho ou estudante no dispositivo. Entre os dispositivos com Windows que podem ser removidos do Intune estão:  
* Dispositivos com Windows 10 
* Computador com Windows 8.1
* Dispositivo móvel com WIndows 8.1
 
Para saber mais sobre o que acontece após a remoção de um dispositivo do gerenciamento do Intune, confira [O que acontece se você remover seu dispositivo do Intune](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Remover seu dispositivo com Windows 10
Execute as etapas a seguir para remover um dispositivo com Windows 10 do Intune.

### <a name="via-the-company-portal-app"></a>Pelo aplicativo Portal da Empresa

1. Abra o aplicativo do Portal da Empresa.
2. Entre com as suas credenciais corporativas ou de estudante.
3. Em **Meus Dispositivos**, selecione o dispositivo que você deseja remover.
4. No canto superior direito do aplicativo, selecione o ícone **Veja mais**.
5. Selecione **Remover**. 
6. Para confirmar a remoção do dispositivo, selecione **Remover dispositivo**.

### <a name="via-device-settings-app"></a>Pelo aplicativo Configurações do dispositivo
1. Abra o aplicativo Configurações. 
2. Acesse **Contas** > **Acessar conta corporativa ou de estudante**.
3. Selecione a conta conectada que você deseja remover > **Desconectar**.
4. Para confirmar a remoção do dispositivo, selecione **Sim**.

## <a name="remove-your-windows-81-computer"></a>Remover seu computador com Windows 8.1
Execute as etapas a seguir para remover um computador com Windows 8.1 do Intune.

1.  Acesse **Configurações do Computador** > **Rede** > **Local de Trabalho**.
2.  Em **Ingresso no Local de Trabalho**, selecione **Sair**.
3.  Em **Ativar o gerenciamento de dispositivo**, selecione **Desligar**.
4.  Na janela pop-up que é aberta, selecione **Desligar**.

## <a name="remove-your-windows-81-mobile-device"></a>Remover seu dispositivo móvel com Windows 8.1
Execute as etapas a seguir para remover um dispositivo móvel com Windows 8.1 do Intune.

1.  Acesse **Configurações** > **Local de trabalho**.
2.  Toque na conta de local de trabalho que deseja cancelar o registro.
3.  Toque em **Excluir** na parte inferior da página.
4.  Na caixa de diálogo **Excluir conta**, toque em **Excluir**.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Remoção de suas informações pessoais depois de remover o Portal da Empresa
Há dois tipos de dados que o Portal da Empresa armazena no seu dispositivo Windows:

-   **Logs de diagnóstico**: dados de atividade de aplicativos padrão que a Microsoft coleta. Isso é apagado automaticamente quando você desinstala o aplicativo Portal da Empresa. Dados de atividade do aplicativo são, por exemplo, dados sobre quanto tempo o aplicativo ficou aberto ou se o aplicativo falhou.
-   **Cache de aplicativo**: arquivos de suporte que são necessários para o aplicativo funcionar, como ícones e configurações.

Para excluir os logs armazenados e o cache, execute uma das seguintes etapas:

* [Desinstalar o aplicativo Portal da Empresa](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) 

* Redefina o aplicativo Portal da Empresa. Abra o aplicativo **Configurações** e selecione > **Aplicativos** > **Portal da Empresa** > **Opções avançadas** > **Redefinir**. 

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
