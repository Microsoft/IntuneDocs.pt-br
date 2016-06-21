---
# required metadata

title: Enviar logs de dados de diagnóstico para o administrador de TI usando email | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Enviar logs de dados de diagnóstico para o administrador de TI usando email

Se receber um erro em seu dispositivo Android enquanto estiver trabalhando com aplicativos da empresa ou escolares ou enquanto estiver no aplicativo do Portal da Empresa, você poderá enviar logs de dados de diagnóstico para ajudar o administrador de TI a descobrir e corrigir o erro. Para incluir todos os detalhes nos logs, o que torna mais fácil para o administrador de TI descobrir o problema, ative o Log Detalhado. Você pode ler mais sobre [registro detalhado](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md).

Para ativar o log detalhado:

1.  Abra o aplicativo do Portal da Empresa.

2.  Toque em **Menu** &gt; **Configurações**.

    > [!NOTE] 
    > **Menu** pode ser um botão de software ou de hardware, dependendo do tipo de dispositivo Android que você tem.

3.  Em **Dados de Diagnóstico**, toque em **Enviar Dados**.

    > [!NOTE]
    > **Se você estiver usando apenas dispositivos com Android 6.0 ou posteriores:** ao tocar em **Enviar Dados**, verá a mensagem **Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?**. 

    Essa mensagem é enganosa, porque a **Microsoft nunca acessa fotos, mídia ou arquivos em seu dispositivo!** O Google controla o texto da mensagem, então a Microsoft não pode alterá-lo.  Quando você permite o acesso, tudo o que está fazendo é permitir que seu dispositivo grave logs de dados no cartão SD do dispositivo, o que permite que você mova esses logs usando um cabo USB.

    Se você negar acesso, a mensagem será exibida novamente na próxima vez que você tocar em **Enviar Dados**, mas você pode desligar as mensagens futuras tocando na caixa de seleção **Nunca Perguntar Novamente**.  Se você decidir posteriormente permitir o acesso, acesse **Configurações** &gt; **Aplicativos** &gt; **Portal da Empresa** &gt; **Permissões** &gt; **Armazenamento** e ativar a permissão.

4.  Siga os prompts para escolher um aplicativo de email para ser usado para enviar os logs para o administrador de TI. O aplicativo criará um email pré-endereçado com todos os logs anexados.


### Consulte também
[Usando seu dispositivo Android com o Intune](using-your-android-device-with-intune.md)

<!--HONumber=Jun16_HO2-->


