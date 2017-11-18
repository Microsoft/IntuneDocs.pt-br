---
title: Registrar seu dispositivo macOS no Intune com o Portal da Empresa | Microsoft Docs
description: Descreve como registrar um dispositivo macOS no Intune com o aplicativo Portal da Empresa
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a49df5ee93138bd15052bfd630633b443e026e5d
ms.sourcegitcommit: e692be57ec7044dfc224b70941affbfd7efba421
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Registrar seu dispositivo macOS no Intune com o aplicativo Portal da Empresa

Obter acesso a aplicativos, dados e recursos da sua organização facilita o seu trabalho. Sua organização está usando o Intune para [gerenciar o acesso a esses recursos](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), o que exige que você baixe o aplicativo Portal da Empresa para macOS. Essas instruções funcionarão para dispositivos macOS no sistema operacional X El Capitan 10.11 e posteriores.

> [!NOTE]
> É possível encontrar instruções para registrar dispositivos macOS em versões anteriores do macOS [aqui](enroll-your-device-in-intune-macos-legacy.md).

1. Em seu __Encaixe__, localize __Safari__ e abra uma nova janela, em seguida abra o [site de Portal da Empresa](https://portal.manage.microsoft.com).

2. Faça logon no Portal da Empresa com sua conta corporativa ou de estudante.

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Após o logon, clique no **Menu** no canto superior esquerdo da página e selecione **Meus Dispositivos**.

   ![Uma captura de tela da página de aterrissagem do portal da Web com o portal da Web mostrando que nenhum aplicativo pode ser instalado ainda, com um botão Meus Dispositivos abaixo.](./media/macOS_enroll_001_landing_page.png)

4. Na página __Meus Dispositivos__, você verá uma lista de dispositivos registrados ou apenas uma barra de notificação. Isso depende se você já tiver um dispositivo registrado, macOS ou de outra forma. Para registrar um dispositivo que não está listado, selecione a barra de notificação que informa __Caso seu dispositivo esteja listado, toque aqui para identificá-lo. Também é possível tocar aqui para registrar seu dispositivo se ele não estiver listado__. Se você não tiver nenhum dispositivo registrado, a faixa lerá **Você não tem nenhum dispositivo registrado. Registre este ao tocar aqui.**

    ![Uma captura de tela da página Meu Dispositivo, com alguns dispositivos não identificados acima do prompt da barra de notificação para registrar dispositivos não listados ou identificar aqueles não identificados.](./media/macOS_enroll_002_tap_here_banner.png)

5. Baixe o aplicativo do Portal da Empresa para seu dispositivo macOS para continuar registrando.

    ![O aviso que solicita que o usuário baixe o aplicativo do Portal da Empresa macOS. O aviso tem o texto listado na etapa em cima de um botão que diz "Baixar" no canto inferior direito.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. O Mac verificará se é seguro abrir o download de **CompanyPortal.pkg**. Abra o instalador e passe pelo processo de instalação.

7. Quando o instalador terminar, abra a pasta **Aplicativos** ou a **Barra inicial** e abra o **Portal da Empresa**.

8. O Mac mostrará uma mensagem informando **"CompanyPortal" é um aplicativo baixado da Internet. Tem certeza de que deseja abri-lo?** Clique em **Abrir**.

  > [!NOTE]
  > O Intune precisa de acesso ao seu computador para certificar-se de que o dispositivo é seguro o suficiente para acessar recursos da sua organização. Se o computador se recusar a abrir o aplicativo Portal da Empresa, tente [desativar o Gatekeeper](https://support.apple.com/HT202491) e, em seguida, abrir o aplicativo.

9. A primeira tela exibida no aplicativo Portal da Empresa solicitará que você **Entre** com a mesma conta corporativa ou de estudante usada para fazer logon no site do Portal da Empresa.

10. O Portal da Empresa confirmará as informações da conta e mostrará o status do **Registro do Dispositivo** e da **Conformidade do Dispositivo**. Haverá triângulos amarelos informando que você precisará executar algumas ações para garantir que o Mac esteja seguro para ser usado no trabalho. Clique em **Iniciar** para começar a [registrar seu dispositivo no gerenciamento](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

11. O Mac começará a ser registrado no gerenciamento. Poderá ser solicitado que você forneça informações de logon do computador durante esse tempo. Esse processo de registro pode levar alguns minutos. Durante esse tempo, você pode fazer outras coisas em seu computador. Uma mensagem será exibida quando a Instalação do Acesso da Empresa for concluída para informá-lo que ela já terminou.

Ainda precisa de ajuda? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://portal.manage.microsoft.com).
