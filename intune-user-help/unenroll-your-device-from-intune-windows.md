---
title: Remover seu dispositivo Windows do gerenciamento do Intune
description: Descreve como remover um dispositivo Windows do gerenciamento do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/03/2018
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
ms.openlocfilehash: 5984ac8ebe825a187b33945699a5fadc27e0c0cc
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828407"
---
# <a name="remove-your-windows-device-from-management"></a>Remover seu dispositivo Windows do gerenciamento

Remova um dispositivo Windows registrado do gerenciamento quando você não desejar nem precisar mais:  
* Use seu dispositivo para o trabalho ou escola. 
* Acesse email, aplicativos ou outros recursos de trabalho ou estudante.

Após cancelar o registro do dispositivo, você perderá o acesso do dispositivo aos recursos corporativos ou de estudante. É possível remover os seguintes dispositivos Windows do gerenciamento.  
* Dispositivos com Windows 10 
* Computador com Windows 8.1
* Telefone Windows 8.1
 
Para saber mais sobre o que acontece após a remoção de um dispositivo do gerenciamento, confira [What happens if you remove your device from Intune](what-happens-if-you-unenroll-your-device-from-intune-windows.md) (O que acontecerá se você remover seu dispositivo do Intune).  

## <a name="remove-your-windows-10-device"></a>Remover seu dispositivo com Windows 10
Conclua as etapas a seguir para remover um dispositivo Windows 10 do gerenciamento.

### <a name="remove-in-company-portal-app-home-page"></a>Remova no aplicativo Portal da Empresa, **página inicial**  

1. Abra o aplicativo do Portal da Empresa.
2. Na **Página inicial**, vá para baixo na seção **Meus dispositivos**.
3. Selecione o dispositivo que deseja remover.
3. No canto superior direito do aplicativo, selecione o ícone **Veja mais**.
4. Selecione **Remover**. 
5. Para confirmar a remoção do dispositivo, selecione **Remover**.  

### <a name="remove-in-company-portal-app-device-context-menu"></a>Remover no aplicativo Portal da Empresa, menu de contexto do aplicativo  

1. Abra o aplicativo Portal da Empresa e acesse **Meus dispositivos**.

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, Página inicial, realçando a seção Meus dispositivos.](./media/1809_CheckAccess_Context_Select_Device.png)

2. Clique com o botão direito do mouse ou pressione e segure um dispositivo para abrir seu [menu de contexto](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus).  

3. Selecione **Remover**.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, Página inicial. O menu de contexto do dispositivo está visível na seção **Meus dispositivos** da página e mostra as ações "Renomear", "Remover" e "Verificar acesso".](./media/1809_DeviceContextMenu_Windows_CP.png)  

5. Na confirmação, clique em **Saiba mais** para ler como seu acesso aos recursos corporativos e de estudante podem ser alterados. Para confirmar a remoção do dispositivo, selecione **Remover**.   

     ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, Página inicial. O campo Renomear é exibido sobre o dispositivo em que um usuário pode digitar o novo nome e clicar em Renomear ou Cancelar.](./media/1808_RemoveDevice_Popup.png)  


### <a name="remove-in-device-settings-app"></a>Remover no aplicativo Configurações do dispositivo
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

## <a name="remove-your-windows-81-phone"></a>Remover seu telefone Windows 8.1
Conclua as seguintes etapas para remover um telefone Windows 8.1 do Intune.

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

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
