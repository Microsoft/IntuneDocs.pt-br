---
title: "Configurações de email do Intune para dispositivos Windows 10 | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões de email em dispositivos Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f16c9dfb41cb2cfe07ce473a131dac767dee9c74
ms.openlocfilehash: 02b1acca12cfd78afa932319fc389b78bea58e64


---

# <a name="email-profile-settings-for-windows-10-devices-in-intune-azure-preview"></a>Configurações de perfil de email para dispositivos Windows 10 na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **Servidor de email** – O nome do host do seu servidor Exchange.
- **Nome da conta** – O nome de exibição para a conta de email que será exibida aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD** – Esse é o atributo no AD (Active Directory) ou Azure AD, que será usado para gerar o nome de usuário para este perfil de email. Selecione o **Endereço SMTP Primário**, como o **user1@contoso.com** ou **Nome UPN**, como **user1** ou **user1@contoso.com**.
- **Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado. Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.


## <a name="security-settings"></a>Configurações de segurança

- **SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.



## <a name="synchronization-settings"></a>Configurações de sincronização

- **Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.
- **Sincronizar agendamento** – Selecione o agendamento pelo qual os dispositivos sincronizarão os dados do servidor Exchange. Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados assim que eles chegam, ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.

## <a name="content-sync-settings"></a>Configurações de sincronização de conteúdo

- **Tipo de conteúdo a ser sincronizado** – Selecione os tipos de conteúdo que você deseja sincronizar dos dispositivos:
    - **Contatos**
    - **Calendário**
    - **Tarefas**



<!--HONumber=Feb17_HO1-->


