---
title: Configurar o gerenciamento do dispositivo Windows com o Microsoft Intune | Microsoft Intune
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para computadores Windows, incluindo dispositivos Windows 10 com o Microsoft Intune."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f336cf52cbecd93cb7b2850560327e6024302e0
ms.openlocfilehash: 710e34f8f97377bf57a398f74773788df3794654


---

# Configurar o gerenciamento do dispositivo Windows
Com o Intune, você pode habilitar o registro de dispositivos BYOD ("traga seu próprio dispositivo") para computadores Windows para dar acesso ao email e aplicativos da empresa. Usado com o Azure Active Directory, isso também fornece uma maneira rápida e automática de trazer novos dispositivos Windows 10 para o gerenciamento e obter acesso aos recursos da empresa sem precisar refazer a imagem do computador. Depois de registrados, os usuários podem fazer logon e seus dispositivos podem ser alvo de políticas, aplicativos e configurações usando o console de administração do Intune. Você talvez também queira [Configurar o gerenciamento do Windows Phone com o Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) ou [Gerenciar computadores com o software cliente do Intune](manage-windows-pcs-with-microsoft-intune.md) usando o cliente do Intune.

A criação de um DNS CNAME ajuda os usuários a se registrarem no Intune sem inserir um nome do servidor.

### Configurar o gerenciamento do dispositivo Windows

  1.  Crie o registro de recurso de DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Embora a entrada DNS CNAME seja opcional para o registro do dispositivo do Windows, é recomendável criar um ou mais registros quando necessário, para facilitar as coisas durante o processo de registro de dispositivo Windows. Se nenhum registro CNAME for encontrado, o usuário será solicitado a inserir manualmente o nome do servidor MDM.

  Se houver mais de um domínio verificado, crie um registro CNAME para cada domínio. Os registros de recursos de CNAME deve conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

  Alterações de registro DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

  **EnterpriseEnrollment-s.manage.microsoft.com** – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

  **EnterpriseRegistration.windows.net** – dá suporte a dispositivos Windows 8.1 e Windows 10 Mobile que serão registrado no Azure Active Directory usando sua conta corporativa ou de estudante

  2.  No [console de administração do Intune](http://manage.microsoft.com), clique em **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows**.
  ![Caixa de diálogo de gerenciamento de dispositivo do Windows](../media/enroll-intune-winenr.png)
  3.  Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e clique em **Testar Detecção Automática**.

### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


