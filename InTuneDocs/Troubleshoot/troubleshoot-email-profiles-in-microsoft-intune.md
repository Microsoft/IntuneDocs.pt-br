---
title: Solucionar problemas de perfis de email | Microsoft Intune
description: "Problemas com o perfil de email e como resolvê-los."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 08/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb0aeac2f94dfde50d9398b09c6b21c7ae40624
ms.openlocfilehash: 79076b65fe85adeaffd5435915cb5eca2a15413f


---

# Solucionar problemas de perfis de email no Microsoft Intune
Aqui estão relacionados alguns problemas com o perfil de email e como resolvê-los.

Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.


## Não é possível enviar imagens da conta de email
Os usuários que têm contas de email configuradas automaticamente não podem enviar imagens de seus dispositivos.
Isso ocorre quando a opção **Permitir que o email seja enviado de aplicativos de terceiros** não está habilitada.

### Solução do Intune

1.  Abra o Console de administração do Microsoft Intune, selecione **Política** Carga de trabalho &gt;**Política de configuração**.

2.  Selecione o perfil de email e clique em **Editar**.

3.  Selecione a opção **Permitir que o email seja enviado de aplicativos de terceiros.**

### Configuration Manager integrado à solução Intune

1.  Abra o console do Configuration Manager &gt; **Ativos e Conformidade**.

2.  Expanda **Visão geral** -&gt; **Configurações de Conformidade** -&gt; **Acesso aos Recursos da Empresa** e selecione **Perfis de Email**.

3.  Clique com o botão direito do mouse no perfil de email e abra as **Propriedades**.

4.  Na guia **Configurações de Sincronização**, selecione **Permitir que o email seja enviado de aplicativos de terceiros**.


## O dispositivo já tem um perfil de email instalado

Se o usuário instalou um perfil de email antes de provisionar um perfil pelo Intune, o resultado da implantação do perfil de email Intune depende da plataforma de dispositivo:

-**iOS**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e endereço de email. O perfil de email duplicado criado pelo usuário bloqueia a implantação de um perfil criado pelo administrador do Intune. Isso é um problema comum, pois usuários do iOS normalmente vão criar um perfil de email e, depois, se registrar. O portal da empresa informará ao usuário que ele não é compatível devido ao seu perfil de email configurado manualmente e solicitará que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser implantado. Para evitar o problema, instrua os usuários a se registrar antes de instalar um perfil de email e permitir que o Intune implante o perfil.

-**Windows**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e endereço de email. O Intune substituirá o perfil de email existente criado pelo usuário.

-**Samsung KNOX**: o Intune identifica uma conta de email duplicada com base no endereço de email e depois a substitui pelo perfil do Intune. Se o usuário configurar essa conta, ela será substituída novamente pelo perfil do Intune. Observe que isso pode causar alguma confusão ao usuário cuja configuração de conta for substituída.

Como o Samsung KNOX não usa o nome do host para identificar o perfil, é recomendável que você não crie vários perfis de email para implantar o mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.

## Erro 0x87D1FDE8 para dispositivo KNOX
**Problema**: depois de criar e implantar um perfil de email do Exchange Active Sync para Samsung KNOX para vários dispositivos Android, eles reportam o erro **0x87D1FDE8** ou **falha na correção** na guia Política das &gt; propriedades do dispositivo.

Examine a configuração do seu perfil de EAS para Samsung KNOX e a política de origem. Não há suporte para a opção de sincronização das Samsung Notes e essa opção não deve estar selecionada em seu perfil. Certifique-se de que os dispositivos tiveram tempo suficiente, se até 24 horas, para processar a política.

## Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).



<!--HONumber=Aug16_HO1-->


