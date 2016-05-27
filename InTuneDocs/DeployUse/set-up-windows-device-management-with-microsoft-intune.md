---
# required metadata

title: Configurar o gerenciamento do dispositivo Windows com o Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurar o gerenciamento do dispositivo Windows
Com o Intune, você pode habilitar o registro de dispositivos BYOD ("traga seu próprio dispositivo") para computadores Windows para dar acesso ao email e aplicativos da empresa. Usado com o Azure Active Directory, isso também fornece uma maneira rápida e automática de trazer novos dispositivos Windows 10 para o gerenciamento e obter acesso aos recursos da empresa sem precisar refazer a imagem do computador. Depois de registrados, os usuários podem fazer logon e seus dispositivos podem ser alvo de políticas, aplicativos e configurações usando o console de administração do Intune. Você talvez também queira [Configurar o gerenciamento do Windows Phone com o Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) ou [Gerenciar computadores com o software cliente do Intune](manage-windows-pcs-with-microsoft-intune.md) usando o cliente do Intune.

A criação de um DNS CNAME ajuda os usuários a se registrarem no Intune sem inserir um nome do servidor.

### Configurar o gerenciamento do dispositivo Windows

  1.  Crie o registro de recurso de DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Se houver mais de um domínio verificado, crie um registro CNAME para cada domínio. Os registros de recurso CNAME devem conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

    DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

    **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

    **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  No [Console de administração do Intune](http://manage.microsoft.com), clique em **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows**.
  ![Caixa de diálogo de gerenciamento de dispositivo do Windows](../media/enroll-intune-winenr.png)
  3.  Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e clique em **Testar Detecção Automática**.

### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


