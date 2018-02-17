---
title: Registrar seu dispositivo macOS herdado no Intune | Microsoft Docs
description: Descreve como registrar um dispositivo macOS no Intune
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- User help
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 23d996132a6c896bb260b1bc4e46cbc6077583b3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-your-legacy-macos-device-in-intune"></a>Registre seu dispositivo macOS herdado no Intune

Essas instruções funcionarão para dispositivos macOS no OS X Yosemite 10.10 e em versões anteriores. É possível encontrar instruções para registrar dispositivos macOS em versões mais recentes do macOS [aqui](enroll-your-device-in-intune-macos-cp.md).

Obter acesso a aplicativos, dados e recursos da sua organização possibilita fazer seu trabalho. Se estiver usando um dispositivo macOS no trabalho, isso significa instalar um __Perfil de Gerenciamento__. Esse é simplesmente um arquivo configurado pelo suporte de sua empresa que carrega as configurações e informações de acesso para seu Mac. Quer saber mais? Descubra [o que acontece quando você instala o aplicativo do Portal da Empresa e registra o dispositivo no Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

1. Em seu __Encaixe__, localize __Safari__ e abra uma nova janela, em seguida abra o [site de Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
2. Faça logon no Portal da Empresa com sua conta corporativa ou de estudante.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Após o logon, clique no **Menu** no canto superior esquerdo da página e selecione **Meus Dispositivos**.

 ![Uma captura de tela da página de aterrissagem do portal da Web com o portal da Web mostrando que nenhum aplicativo pode ser instalado ainda, com um botão Meus Dispositivos abaixo.](./media/macOS_enroll_001_landing_page.png)

4. Na página __Meus Dispositivos__, você verá uma lista de dispositivos registrados ou apenas uma barra de notificação. Isso depende se você já tiver um dispositivo registrado, macOS ou de outra forma. Para registrar um dispositivo que não está listado, selecione a barra de notificação que informa __Caso seu dispositivo esteja listado, toque aqui para identificá-lo. Também é possível tocar aqui para registrar seu dispositivo se ele não estiver listado__. Se você não tiver nenhum dispositivo registrado, a faixa lerá **Você não tem nenhum dispositivo registrado. Registre este ao tocar aqui.**

  ![Uma captura de tela da página Meu Dispositivo, com alguns dispositivos não identificados acima do prompt da barra de notificação para registrar dispositivos não listados ou identificar aqueles não identificados.](./media/macOS_enroll_002_tap_here_banner.png)

5. Uma janela pop-up será exibida com uma breve explicação sobre por que vocês vão __Identificar ou registrar este dispositivo__. Examine isso, clique em __Registrar__ para continuar.

 ![Identifique ou registre este dispositivo macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. Uma segunda janela pop-up será exibida com uma breve explicação sobre o que vai acontecer quando __Registrar este dispositivo__. Examine isso, clique em __Instalar__ para continuar.

 ![Registrar este dispositivo macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > O Intune precisa de acesso ao seu computador para certificar-se de que o dispositivo é seguro o suficiente para acessar recursos da sua organização. Descubra [o que acontece quando você registra seu dispositivo no Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. As __Preferências do Sistema__ serão abertas e perguntarão se deseja __Instalar "Perfil de Gerenciamento"?__ Clique em __Instalar__ para continuar ou obtenha mais detalhes clicando __Mostrar Perfil__.

 ![Instalar o Perfil de Gerenciamento](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Será exibida uma janela pop-up do macOS. Confirme que deseja fazer alterações, fornecendo o __nome de usuário__ e __senha__ do computador, em seguida, clicando em __OK__. Isso instalará o perfil de gerenciamento em seu Mac.

 ![Janela pop-up de Instalação do Perfil macOS](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Você pode ver algumas mensagens adicionais do seu Mac com mais detalhes sobre o perfil ou se tem certeza de que deseja __Instalar__. Clique em __Continuar__ e __Instalar__ por meio desses para continuar. Depois que a instalação for concluída, você poderá exibir seu recém-instalado __Perfil de Gerenciamento__ na lista de __Perfis de Dispositivo__.

 ![Perfil macOS Instalado](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Alguns perfis podem dizer que **Não São Verificados**. Desde que sejam de sua empresa, isso é normal.

Ainda precisa de ajuda? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
