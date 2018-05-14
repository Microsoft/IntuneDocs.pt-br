---
title: Remover seu dispositivo Windows no Intune | Microsoft Docs
description: Descreve como remover um dispositivo Windows do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/28/2018
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
ms.openlocfilehash: 89a69f7d5cda31658cc9faf068a2a37698fdd93c
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="remove-your-windows-device-from-intune"></a>Remova seu dispositivo Windows do Intune

Se o seu dispositivo estiver registrado com o Intune, mas você não quiser mais usar seu dispositivo do Windows para acessar o email da escola ou do trabalho, aplicativos ou outros recursos, remova o seu dispositivo do gerenciamento. Depois que você remover seu dispositivo do Intune, não poderá mais acessar esses recursos. Para obter mais informações sobre o que acontece quando você remove um dispositivo do gerenciamento, veja [O que acontece quando você cancela o registro do dispositivo no Intune?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Remover seu dispositivo com Windows 10

1.  Na sua lista de aplicativos, toque no aplicativo **Portal da Empresa** .

2.  Entre com as suas credenciais corporativas ou de estudante.

3.  Em **Meus Dispositivos**selecione o dispositivo cujo registro deseja cancelar.

4.  Toque em **Remover** &gt; **Remover**.

## <a name="remove-your-windows-81-computer"></a>Remover seu computador com Windows 8.1

1.  Acesse **Configurações de Computador** &gt; **Rede** &gt; **Local de Trabalho**.

2.  Em **Ingresso no Local de Trabalho**, selecione **Sair**.

3.  Em **Ativar o gerenciamento de dispositivo**, selecione **Desligar**.

4.  Na janela pop-up que é aberta, selecione **Desligar**.

## <a name="remove-your-windows-phone-81-mobile-device"></a>Remover seu dispositivo móvel com Windows Phone 8.1

1.  Vá para **Configurações** &gt; **Local de trabalho**.

2.  Toque na conta de local de trabalho que deseja cancelar o registro.

3.  Toque em **Excluir** na parte inferior da página.

4.  Na caixa de diálogo **Excluir conta**, toque em **Excluir**.

## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Remoção de suas informações pessoais depois de remover o Portal da Empresa

Há dois tipos de dados que o Portal da Empresa armazena no seu dispositivo Windows:

-   **Logs de diagnóstico**: dados de atividade de aplicativos padrão que a Microsoft coleta, como há quanto tempo o aplicativo foi aberto ou se está em estado de falha, são automaticamente apagados quando o aplicativo do Portal da Empresa é desinstalado.
-   **Cache de aplicativo**: armazenamento de certos arquivos de suporte necessários para o aplicativo funcionar, como ícones e configurações.

São necessárias algumas etapas para excluir completamente essas informações.

### <a name="uninstall-the-company-portal"></a>Desinstalar o Portal da Empresa  

[Desinstalar o aplicativo do Portal da Empresa](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) removerá os dados de aplicativo armazenados no seu dispositivo.  

### <a name="reset-the-company-portal"></a>Redefinir o Portal da Empresa

Você pode redefinir o restante dos dados de aplicativo do Portal da Empresa redefinindo o aplicativo em Configurações. Abra **Configurações** > **Aplicativos e Recursos** > **Portal da Empresa** > **Opções avançadas** > **Redefinir**.

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
