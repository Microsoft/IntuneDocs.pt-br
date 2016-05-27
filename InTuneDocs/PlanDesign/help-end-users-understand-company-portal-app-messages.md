---
# required metadata

title: Ajudar usuários finais a compreender as mensagens do aplicativo do Portal da Empresa | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ajudar usuários finais a compreender as mensagens do aplicativo do Portal da Empresa

As informações a seguir aplicam-se somente aos dispositivos Android 6.0 e posteriores. Durante o registro de dispositivo, os usuários finais veem duas mensagens, que aparecem durante o processo de registro:

- Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?
- Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?

Consulte os parágrafos a seguir para obter detalhes sobre essas mensagens e informações que você pode compartilhar com seus usuários finais sobre eles.

## Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?

### Texto da mensagem e onde ele é exibido
O texto da mensagem é **Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?**, e é exibido quando os usuários entram no aplicativo do Portal da Empresa pela primeira vez para iniciar o registro do dispositivo.

### O que a mensagem significa
A mensagem está solicitando que os usuários permitam que o IMEI e o número de telefone do dispositivo sejam enviados ao serviço Intune e apareçam no console do Administrador, na página Hardware.

> [!NOTE]
> **O aplicativo de Portal da Empresa nunca faz ou gerencia chamadas telefônicas!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

Para ver a página **Hardware**, vá para **Grupos** > **Todos os dispositivos móveis** > **Dispositivos**. Selecione o dispositivo do usuário e vá para **Exibir propriedades** > **Hardware**.

### O que acontece se os usuários permitirem ou negarem o acesso
Se os usuários permitirem o acesso, o IMEI e o número de telefone do dispositivo serão exibidos na página Hardware no console do Administrador.

Se os usuários negarem o acesso, eles poderão continuar a usar o aplicativo do Portal da Empresa e registrar seus dispositivos, mas o IMEI e o número de telefone do dispositivo dos usuários ficarão em branco na página Hardware no console do Administrador. Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente.

Se os usuários permitem, mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entrarem no aplicativo do Portal da Empresa após o registro.</br></br>Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.

### Para onde enviar os usuários para obter mais informações
[Entrar para o aplicativo do Portal da Empresa](/Intune/EndUser/sign-in-to-the-company-portal-app-android)

## Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?

### Texto da mensagem e onde ele é exibido
O texto da mensagem é **Permitir que o Portal da Empresa acesse fotos, mídia e arquivos em seu dispositivo?**, é exibida quando os usuários tocam em **Enviar dados** para enviar logs de dados ao administrador de TI.

### O que a mensagem significa
A mensagem está solicitando que os usuários permitam que seu dispositivo grave logs de dados no cartão SD do dispositivo e que habilite esses logs a serem movidos usando um cabo USB.   

> [!NOTE]
> **O aplicativo do Portal da Empresa nunca acessa fotos, mídia e arquivos dos usuários!** O texto da mensagem é controlado pelo Google e não pode ser alterado.

### O que acontece se os usuários permitirem ou negarem o acesso
Se os usuários permitirem o acesso, os logs serão copiados para o cartão SD.

Se os usuários negarem o acesso, eles ainda podem enviar logs de dados, mas os logs não serão copiados para o cartão SD do dispositivo.

Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente. Se os usuários permitirem, mas posteriormente negarem o acesso, a mensagem será exibida na próxima vez que os usuários tentarem enviar logs. Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Armazenamento** e ativar a permissão.

### Para onde enviar os usuários para obter mais informações
[Enviar logs de dados de diagnóstico para seu administrador de TI usando o email](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Consulte também
[O que dizer a seus usuários finais sobre como usar o Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune.md)


<!--HONumber=May16_HO1-->


