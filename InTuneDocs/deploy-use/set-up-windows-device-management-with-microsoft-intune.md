---
title: Configurar o gerenciamento de dispositivo Windows com o Microsoft Intune | Microsoft Docs
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para dispositivos Windows com o Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 115eae8e2d733397eb4b0f025789ca7d0522a845
ms.openlocfilehash: 5dc90c1e1ddba91fe8bbb4530eb09bca0c9e3ac9


---

# <a name="set-up-windows-device-management"></a>Configurar o gerenciamento do dispositivo Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use um dos métodos a seguir para configurar o registro para dispositivos do Windows:

- [**Registro automático do Windows 10 e Windows 10 Mobile com o Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium) 
 -  Esse método é aplicável somente a dispositivos Windows 10 e Windows 10 Mobile.
 -  Você deve ter o Azure Active Directory Premium para usar esse método. Caso contrário, use o método de registro para Windows 8.1 e Windows Phone 8.1.
 -  Se você optar por não habilitar o registro automático, use o método de registro para Windows 8.1 e Windows Phone 8.1.


- [**Registro do Windows 8.1 e Windows Phone 8.1 configurando CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname) 
 - Você deve usar esse método para registrar dispositivos Windows 8.1 e Windows Phone 8.1.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Configurar o registro do Windows 8.1 e Windows Phone 8.1 configurando CNAME
Você pode permitir que os usuários instalem e registrem seus dispositivos usando o Portal da Empresa do Intune. Se você criar registros de recursos de DNS CNAME, os usuários se conectam e se registram no Intune sem inserir um nome do servidor.

1. **Configurar Intune**<br>
Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de MDM (gerenciamento de dispositivo móvel)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) como **Microsoft Intune** e configure o MDM.

2. **Criar CNAMEs** (opcional)<br>
Criar registros de recurso DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para enterpriseenrollment-s.manage.microsoft.com.

    Embora a criação de entradas de DNS CNAME seja opcional, os registros CNAME facilitam o registro para os usuários. Se não for possível encontrar nenhum CNAME de registro, os usuários deverão inserir manualmente o nome do servidor MDM, enrollment.manage.microsoft.com.    

    Registros de recursos de CNAME devem conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

  `EnterpriseEnrollment-s.manage.microsoft.com` – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

  `EnterpriseRegistration.windows.net` – dá suporte a dispositivos Windows 8.1 e Windows 10 Mobile que serão registrados no Azure Active Directory usando sua conta corporativa ou de estudante

  Se sua empresa usa vários domínios para credenciais de usuário, crie registros CNAME para cada domínio.

  Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

3.  **Verificar CNAME**<br>No [console de administração do Intune](http://manage.microsoft.com), escolha **Admin** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e escolha **Testar Detecção Automática**.

4.  **Diga aos usuários como registrar seus dispositivos e o que esperar quando eles forem incluídos no gerenciamento.**

    Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Windows no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Para obter mais informações sobre as tarefas do usuário final, consulte [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Consulte também
[Pré-requisitos para registrar dispositivos no Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO3-->


