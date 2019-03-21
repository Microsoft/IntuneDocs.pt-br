---
title: Como redefinir sua senha do site do Portal da Empresa | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e973e18a79c18af6b201194fc1a6534da5fa38a
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "55838029"
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Como redefinir a senha do dispositivo pelo site do Portal da Empresa

Se você perder o PIN ou a senha do dispositivo, use o [site Portal da Empresa](https://portal.manage.microsoft.com) para redefini-lo.  

Se você estiver usando um dispositivo corporativo registrado, talvez a opção para redefinir a senha do dispositivo não seja exibida. Contate o suporte da empresa para redefinir a senha para você.

   > [!NOTE]
   > Não é possível redefinir a senha para dispositivos com Android 7.0 e posterior. Se você esquecer a senha, será necessário redefinir o dispositivo para as configurações de fábrica. 

## <a name="reset-your-passcode"></a>Redefinir senha

1.  Abra o [site Portal da Empresa](https://portal.manage.microsoft.com) e selecione o botão __Menu__ > __Dispositivos__.  

2. Selecione o dispositivo que precisa de uma redefinição de senha.  

    ![Uma captura de tela da página Dispositivos, com dois blocos que mostram dispositivos não identificados, nomeados de maneira genérica. Uma faixa cinza é mostrada diretamente abaixo dos dispositivos e solicita que o usuário identifique o dispositivo que ele está usando ou adicione um novo.](./media/rename-reset-device-step2-1808.png) 

3. Selecione **Redefinir Senha**. Se a opção de senha não estiver visível na parte superior da página, selecione **Mais (…)** > **Redefinir Senha**.   

   ![A página de detalhes do dispositivo de um dispositivo selecionado no site Portal da Empresa, com uma lista de links na parte superior mostrando Renomear, Remover, Redefinir Dispositivo, Redefinir Senha e Bloqueio Remoto. ](./media/rename-reset-device-1808.png)   

    ![Exibição ampliada do ícone Mais, realçado com uma seta vermelha.](./media/rename-reset-device-step3-more-1808.png)  

4. Quando solicitado, clique em **Sair**. Quando solicitado, entre novamente. Você precisa entrar no site Portal da Empresa em até cinco minutos para que ele redefina a senha do dispositivo.  

   > [!NOTE]
   > Você precisa entrar novamente para confirmar sua identidade. Isso é para evitar tentativas mal-intencionadas de redefinir a senha do dispositivo.

   ![Capturas de tela de exemplo mostrando um prompt para sair do Portal da Empresa. Os botões para a entrada do usuário são Sair e Cancelar.](./media/iwp-reset-passcode-popup-1808.png)

5. Será exibida uma mensagem para avisar que a senha do dispositivo existente está prestes a ser removida. Clique em **Redefinir senha** para confirmar.  
    > [!WARNING]
    > Depois de redefinir sua senha, qualquer pessoa que tenha acesso físico ao dispositivo poderá acessar a maioria das informações pessoais e corporativas contidas nele. Se você não estiver com o dispositivo em mãos no momento, não redefina a senha.  

   ![Captura de tela de exemplo que mostra a segunda mensagem de redefinição de senha. Inclui um link para saber mais sobre como definir uma nova senha na documentação e botões individuais para redefinir a senha e cancelar.](./media/iwp-reset-passcode-popup2-1808.png) 

6. Se você estiver redefinindo a senha de um dispositivo iOS, a senha existente será removida. Para dispositivos Android ou Windows, será emitida uma senha temporária para desbloquear o dispositivo e definir uma nova senha. 

   > [!NOTE]
   > Encontre a senha temporária para dispositivos Android e Windows no Portal da Empresa, na página de detalhes do dispositivo. Confira a seção [Configurar uma nova senha](reset-your-passcode-cpwebsite.md#set-up-a-new-passcode) para obter mais descrições de senha específicas do sistema operacional.  
   
7. Em seu dispositivo, acesse **Configurações** e altere a senha temporária. 

8. Um sinalizador aparece na parte superior direita do site Portal da Empresa. Clique para ler a notificação e confirme se a senha foi redefinida com êxito.  

## <a name="set-up-a-new-passcode"></a>Configurar uma nova senha  

Esta seção descreve a redefinição de senha e o comportamento da senha temporária para cada plataforma de dispositivo.  

**Android**: remove a senha existente e cria uma senha temporária composta de letras e números.

**iOS**: remove a senha existente e não cria uma senha temporária. Se você usa o scanner de impressão digital Touch ID para abrir o dispositivo ou fazer compras, é necessário configurá-lo novamente.  

**Windows 10 Mobile**: remove a senha existente e cria uma senha temporária composta de letras e números. Se o reconhecimento do rosto do Windows Hello estiver configurado, ele ainda funcionará com o dispositivo.
    
**Windows Phone 8.1**: remove a senha existente e cria uma senha temporária composta de números.  

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
