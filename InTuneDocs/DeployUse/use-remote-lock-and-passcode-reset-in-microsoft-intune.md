---
title: "Usar bloqueio remoto e redefinição de senha | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
translationtype: Human Translation
ms.sourcegitcommit: 6d9b79a09eef2546d78a19e061ba5cc3f24f645c
ms.openlocfilehash: 34379881b8299a2e3f9886b14b6d83e9dfe83373

---
# Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha
O Microsoft Intune fornece funcionalidades de bloqueio remoto e redefinição de senha.

## Bloquear um dispositivo remotamente
Se um usuário perder o dispositivo, você poderá bloquear o dispositivo remotamente. A tabela abaixo lista como o bloqueio remoto funciona em diferentes plataformas remotas.

|Plataforma|Bloqueio remoto|
|------------|---------------|
|iOS|Com suporte|
|Android|Com suporte|
|Windows 10 Mobile|Com suporte|
|Windows Phone 8 e Windows Phone 8.1|Com suporte|
|Windows RT 8.1 e Windows RT|Suportado se o usuário atual do dispositivo for o mesmo usuário que registrou o dispositivo.|
|Windows 8.1|Suportado se o usuário atual do dispositivo for o mesmo usuário que registrou o dispositivo.|


### Para bloquear um dispositivo móvel remotamente usando o console do Intune

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**.

2.  Clique em **Todos os Dispositivos Gerenciados Diretamente** para exibir os dispositivos registrados no Intune ou **Todos os Dispositivos de Gerenciados pelo Exchange ActiveSync**.

    > [!TIP]
    > Você também pode navegar para um dispositivo por usuário. Escolha **Todos os Usuários**. Na página de propriedades do usuário, escolha **Dispositivos** e selecione o nome do dispositivo móvel que deseja apagar.

3.  Na lista, clique no dispositivo ou nos dispositivos que deseja bloquear. Na barra de tarefas, escolha **Tarefas Remotas** e selecione **Bloqueio Remoto**.

## Redefinir a senha em um dispositivo
Se um usuário esquecer sua senha, você poderá ajudá-lo removendo a senha de um dispositivo ou impondo uma nova senha temporária em um dispositivo. A tabela abaixo lista como a redefinição de senha funciona em diferentes plataformas remotas.

|Plataforma|Redefinição de senha|
|------------|------------------|
|iOS|Suportado para limpar a senha de um dispositivo. Não cria uma nova senha temporária.|
|Android|Suportado e uma senha temporária é criada.|
|Windows 10 Mobile|Com suporte|
|Windows Phone 8 e Windows Phone 8.1|Com suporte|
|Windows RT 8.1 e Windows RT|Sem suporte|
|Windows 8.1|Sem suporte|

### Para redefinir uma senha

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**.

2.  Clique em **Todos os Dispositivos Gerenciados Diretamente** para exibir os dispositivos registrados no Intune ou **Todos os Dispositivos de Gerenciados pelo Exchange ActiveSync**.

    > [!TIP]
    > Você também pode navegar para um dispositivo por usuário. Clique em **Todos os Usuários**. Na página de propriedades do usuário, clique em **Dispositivos** e clique no nome do dispositivo móvel que deseja apagar.

3.  Na lista, clique no dispositivo ou nos dispositivos que deseja bloquear. Na barra de tarefas, escolha **Tarefas Remotas** e selecione **Redefinição de Senha**.


### Consulte também
[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md)
[Apagamento seletivo do Windows para o gerenciamento de dados de dispositivos](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jun16_HO4-->


