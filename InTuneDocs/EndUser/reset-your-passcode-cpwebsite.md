---
title: Redefinir a senha do dispositivo pelo site do Portal da Empresa | Microsoft Intune
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2aea845bc00c153f070e04abb67582a5d5a726ca
ms.openlocfilehash: 47b36616f7a8ee23d4d47b41a1db2c41c185c6f5


---


# Redefinir a senha do dispositivo pelo site do Portal da Empresa

Se você perder a senha ou o PIN do seu dispositivo para um dispositivo que você registrou no Intune, você poderá usar o [site do Portal da Empresa](http://portal.manage.microsoft.com) para redefini-la. Você pode usar o site do Portal da Empresa para gerenciar computadores e dispositivos que você registrou no Intune e para realizar a maioria das mesmas tarefas que você pode fazer quando usa o aplicativo de Portal da Empresa.

> [!NOTE]
> Você pode não ver o botão **Redefinir Senha** no site do Portal da Empresa, dependendo de como o administrador de TI tiver configurado o Intune. Não há suporte para a redefinição de senha em dispositivos Windows 8.1.

Para redefinir sua senha:

1.  Abra o [site do Portal da Empresa](http://portal.manage.microsoft.com) e escolha o dispositivo cuja senha você deseja redefinir.

2.  Escolha **Redefinir Senha**.

    ![Detalhes do dispositivo com o botão Redefinir Senha](./media/iwp-screen-with-all-options.png)

3.  Escolha **Entrar** e entre novamente com as suas credenciais corporativas ou de estudante. Você precisa entrar novamente em cinco minutos.

    ![Mensagem de redefinição com o botão de saída](./media/iwp-2-sign-out.png)

4.  Escolha **Redefinir Senha**.

    ![Mensagem que explica o que acontece quando você redefine a senha](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Verifique a tabela para ver como **Redefinir Senha** funciona em seu dispositivo.

    |Plataforma|Suporte|
    |------------|-----------|
    |Android|Cria uma senha temporária alfanumérica.|
    |iOS|Remove a senha do dispositivo e não cria uma senha temporária. Se estiver usando Touch ID, você precisará configurá-lo novamente no seu dispositivo, porque ele será removido quando você redefinir sua senha.|
    |Windows 10 (somente para dispositivos móveis)|Cria uma senha temporária alfanumérica. Há suporte para o Windows Hello.|
    |Windows Phone 8.1|Cria uma senha temporária numérica.|
    Depois de desbloquear o dispositivo, você pode definir uma nova senha indo para **Configurações** em seu dispositivo.

5.  Desbloqueie seu dispositivo e, em seguida, defina uma nova senha ou altere a senha temporária acessando **Configurações** em seu dispositivo.

    Para ver uma notificação confirmando que sua senha foi redefinida com êxito, clique no sinalizador de notificação na parte superior direita do site do Portal da Empresa.

Ainda precisa de ajuda? Entre em contato com seu administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO3-->


