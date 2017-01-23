---
title: "Bloqueio remoto e redefinição de senha | Microsoft Docs"
description: "O Intune fornece funcionalidades de bloqueio remoto e redefinição de senha."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 641ca955c2790dc3029e8408d32a66b7b0418a12

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha
O Microsoft Intune fornece funcionalidades de bloqueio remoto e redefinição de senha.

## <a name="lock-a-device-remotely"></a>Bloquear um dispositivo remotamente
Se um usuário perder um dispositivo, você poderá bloquear o dispositivo remotamente. A tabela abaixo lista como o bloqueio remoto funciona em diferentes plataformas móveis.

|Plataforma|Bloqueio remoto|
|------------|---------------|
|macOS|Sem suporte|
|iOS|Com suporte|
|Android|Com suporte|
|Windows 10 e Windows 10 Mobile|Com suporte|
|Windows Phone 8 e Windows Phone 8.1|Com suporte|
|Windows RT 8.1 e Windows RT|Suportado se o usuário atual do dispositivo for o mesmo usuário que registrou o dispositivo.|
|Windows 8.1|Suportado se o usuário atual do dispositivo for o mesmo usuário que registrou o dispositivo.|

Não há suporte para o bloqueio remoto para computadores com Windows registrados com o cliente de software do Intune.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Para bloquear um dispositivo móvel remotamente usando o console do Intune

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**.

2.  Clique em **Todos os Dispositivos Gerenciados Diretamente** para exibir os dispositivos registrados no Intune ou **Todos os Dispositivos de Gerenciados pelo Exchange ActiveSync**.

    > [!TIP]
    > Você também pode navegar para um dispositivo por usuário. Escolha **Todos os Usuários**. Na página de propriedades do usuário, escolha **Dispositivos** e selecione o nome do dispositivo móvel que deseja bloquear.

3.  Na lista, clique no dispositivo ou nos dispositivos que deseja bloquear. Na barra de tarefas, escolha **Tarefas Remotas** e selecione **Bloqueio Remoto**.

## <a name="reset-the-passcode-on-a-device"></a>Redefinir a senha em um dispositivo
Se um usuário esquecer a senha, você poderá ajudá-lo removendo a senha de um dispositivo ou impondo uma nova senha temporária em um dispositivo. A tabela a seguir lista como a redefinição de senha funciona em diferentes plataformas remotas.

|Plataforma|Redefinição de senha|
|------------|------------------|
|macOS|Sem suporte|
|iOS|Suportado para limpar a senha de um dispositivo. Não cria uma nova senha temporária.|
|Android|Suporte em versões anteriores ao Android 7.0. Cria uma senha temporária.|
|Windows 10 Mobile|Com suporte|
|Windows Phone 8 e Windows Phone 8.1|Com suporte|
|Windows RT 8.1|Sem suporte|
|Windows 8.1|Sem suporte|
|Windows 10 Desktop|Sem suporte|

Não há suporte para a redefinição de senha para computadores com Windows registrados com o cliente de software do Intune.

### <a name="reset-a-passcode"></a>Redefinir uma senha

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**.

2.  Clique em **Todos os Dispositivos Gerenciados Diretamente** para exibir os dispositivos registrados no Intune ou **Todos os Dispositivos de Gerenciados pelo Exchange ActiveSync**.

    > [!TIP]
    > Você também pode navegar para um dispositivo por usuário. Clique em **Todos os Usuários**. Na página de propriedades do usuário, clique em **Dispositivos** e clique no nome do dispositivo móvel que deseja apagar.

3.  Na lista, clique no dispositivo ou nos dispositivos que deseja bloquear. Na barra de tarefas, escolha **Tarefas Remotas** e selecione **Redefinição de Senha**.


### <a name="see-also"></a>Consulte também
[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md) e [Apagamento seletivo do Windows para o gerenciamento de dados de dispositivos](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Dec16_HO2-->


