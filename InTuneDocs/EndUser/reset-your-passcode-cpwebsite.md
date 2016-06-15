---
# required metadata

title: Redefinir a senha do dispositivo pelo site do Portal da Empresa | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Redefinir a senha do dispositivo pelo site do Portal da Empresa

Se você perder a senha ou o PIN do seu dispositivo para um dispositivo que você registrou no Intune, você poderá usar o [site do Portal da Empresa](http://portal.manage.microsoft.com) para redefini-la. O site do Portal da Empresa é uma página da Web que você pode usar para gerenciar computadores e dispositivos registrados no Intune e para a maioria das mesmas tarefas que você pode fazer ao usar o aplicativo Portal da Empresa.

> [!NOTE] Você não pode ver o botão Redefinição de Senha no site do Portal da Empresa, dependendo de como o administrador de TI tiver configurado o Intune. Não há suporte para a Redefinição de Senha em dispositivos Windows 8.1 e Windows RT.

Para redefinir sua senha:

1.  Abra o [site do Portal da Empresa](http://portal.manage.microsoft.com) e toque no dispositivo cuja senha você deseja redefinir.

2.  Toque em **Redefinir Senha**.

    ![tap-passcode-to-reset](./media/iwp-1-tap-reset-passcode.png)

3.  Toque em **Entrar** e entre novamente com as suas credenciais corporativas ou de estudante. Você precisa entrar novamente em cinco minutos.

    ![sign-out-sign-back-in](./media/iwp-2-sign-out.png)

4.  Toque em **Redefinir Senha**.

    ![tap-reset-passcode](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Verifique a tabela para ver como a Redefinição de Senha funciona em seu dispositivo.

    |Plataforma|Suporte|
    |------------|-----------|
    |Android|Cria uma senha nova, temporária e alfanumérica.|
    |iOS|Remove a senha do dispositivo e não cria uma nova senha temporária. Se estiver usando Touch ID, você precisará configurá-lo novamente no seu dispositivo, porque ele será removido quando você redefinir sua senha.|
    |Windows 10 (somente para dispositivos móveis)|Cria uma senha nova, temporária e alfanumérica. Há suporte para o Windows Hello.|
    |Windows Phone 8.1|Cria uma senha nova, temporária e numérica.|
    Depois de desbloquear o dispositivo, você pode definir uma nova senha indo para **Configurações** em seu dispositivo.

5.  Desbloqueie seu dispositivo e, em seguida, defina uma nova senha ou altere a senha temporária acessando **Configurações** em seu dispositivo.

    Para ver uma notificação confirmando que sua senha foi redefinida com êxito, clique no sinalizador de notificação na parte superior direita do site do Portal da Empresa.

Se você precisar de Ajuda e não for possível encontrar informações de contato do administrador de TI, veja se ele está listado no [site do Portal da Empresa](http://portal.manage.microsoft.com).

### Consulte também
[Usando o Portal da Empresa do Intune](using-the-intune-company-portal-website.md)

<!--HONumber=Jun16_HO1-->


