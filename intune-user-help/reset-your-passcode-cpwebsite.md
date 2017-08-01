---
title: Como redefinir sua senha do site do Portal da Empresa | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ae85e523a2c5b87e172a2bfc01254f87093c71b1
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Como redefinir a senha do dispositivo pelo site do Portal da Empresa

Se você perder a senha ou o PIN do seu dispositivo para um dispositivo que você registrou no Intune, você poderá usar o [site do Portal da Empresa](http://portal.manage.microsoft.com) para redefini-la. Você pode usar o site do Portal da Empresa para gerenciar computadores e dispositivos que você registrou no Intune e para realizar a maioria das mesmas tarefas que você pode fazer quando usa o aplicativo de Portal da Empresa.

> [!NOTE]
> É possível que você não veja o botão Redefinir Senha no site do Portal da Empresa se utilizar um dispositivo corporativo registrado. Nesse caso, será necessário entrar em contato com seu administrador de TI para redefinir a senha para você.

Para redefinir sua senha:

1.  No [site do Portal da Empresa](http://portal.manage.microsoft.com), toque no botão de __menu__ ![Uma imagem pequena do botão de menu, três barras horizontais empilhadas em paralelo.](/intune/media/CP_hamburger_menu.png) e, em seguida, selecione __Meus Dispositivos__.

2. Na página __Meus Dispositivos__, selecione o nome do dispositivo cuja senha você deseja redefinir.

  ![Uma captura de tela da página Meu Dispositivo, com alguns dispositivos não identificados acima do prompt da barra de notificação para registrar dispositivos não listados ou identificar aqueles não identificados.](./media/macOS_enroll_002_tap_here_banner.png)

3.  O dispositivo será aberto em uma janela pop-up. Selecione o botão **Redefinir Senha**.

    ![Todas as opções para um dispositivo selecionado no site do Portal da Empresa, incluindo Renomear, Remover, Redefinir Dispositivo, Redefinir Senha e Bloqueio Remoto. ](./media/iwp-screen-with-all-options.png)

4.  Uma barra de notificação será exibida solicitando que você confirme se deseja redefinir a senha e informando que o dispositivo o desconectará após essa ação. Em seguida, você precisará aguardar 5 minutos antes de se conectar novamente.

  ![A barra de notificação de redefinição de senha com o aviso sobre como redefinir a senha do dispositivo e como o usuário será desconectado. Os botões para a entrada do usuário são Sair e Cancelar.](./media/iwp-reset-passcode-popup.png)

5.  Selecione **Sair** e você receberá uma mensagem final informando sobre a remoção da senha do dispositivo. Se você não tiver o dispositivo com você, não remova a senha, pois qualquer pessoa que tiver acesso físico ao dispositivo poderá acessar a maior parte das informações contidas nele – pessoais ou corporativas. 

  ![A segunda barra de notificação de redefinição de senha com o aviso sobre como redefinir a senha do dispositivo e como a senha será removida dele. Ela também informa como definir uma nova senha acessando as configurações do dispositivo.](./media/iwp-reset-passcode-2nd-popup.png)

  Dispositivos diferentes têm tipos diferentes de senhas.

  **Android**: remove a senha existente e cria uma senha temporária com letras e números 
  
  > [!NOTE]
  > Não é possível redefinir a senha para dispositivos com Android 7.0 e posterior. Será necessário redefinir esses dispositivos para as configurações de fábrica se você esquecer sua senha.

  **iOS**: remove a senha existente e não cria uma senha temporária. Se você estiver usando o scanner de impressão digital de ID de Toque para abrir o dispositivo ou fazer compras, será necessário configurá-lo novamente.

  **Windows 10 Mobile**: remove a senha existente e cria uma senha temporária com letras e números. Se você estiver usando o reconhecimento do rosto do Windows Hello para fazer logon, ele ainda terá suporte.
    
  **Windows Phone 8.1**: remove a senha existente e cria uma senha temporária com números

  Para dispositivos Android e Windows, a senha temporária aparecerá nos **Detalhes do Dispositivo**. 

6.  Desbloqueie seu dispositivo e defina uma nova senha ou altere a senha temporária acessando as **Configurações** de seu dispositivo.

Para ver uma notificação confirmando que sua senha foi redefinida com êxito, clique no sinalizador de notificação na parte superior direita do site do Portal da Empresa.

Ainda precisa de ajuda? Entre em contato com o administrador de TI. Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).
