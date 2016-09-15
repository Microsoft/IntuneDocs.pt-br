---
title: Configurar o gerenciamento do dispositivo Windows com o Microsoft Intune | Microsoft Intune
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para computadores Windows, incluindo dispositivos Windows 10 com o Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 9b063c1e6b1ff5dcab16fce958ede49303284b18


---

# Configurar o gerenciamento do dispositivo Windows

Como administrador do Intune, você pode habilitar o registro e o gerenciamento de computadores Windows de duas maneiras:

- **[Registro automático com o Azure AD](#azure-active-directory-enrollment)** - usuários do Windows 10 e do Windows 10 Mobile registram seus dispositivos adicionando uma conta corporativa ou de estudante para o dispositivo
- **[Registro do Portal da empresa](#company-portal-app-enrollment)** - dispositivos Windows 8.1 e posteriores são registrados baixando e instalando o aplicativo de Portal da Empresa e, em seguida, inserindo as credenciais de sua conta corporativa ou de estudante no aplicativo.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Configurar registro de aplicativo de Portal da Empresa
Você pode permitir que os usuários registrem seus dispositivos instalando e registrando seus dispositivos com o aplicativo do Portal da Empresa do Intune. A criação de um DNS CNAME ajuda os usuários a se registrarem no Intune sem inserir um nome do servidor.

1. **Configurar Intune**<br>
Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) como **Microsoft Intune** e configure o MDM.

2. **Criar CNAMEs** (opcional)<br>Crie registros **CNAME** de recurso DNS para o domínio de sua empresa para simplificar o registro. Embora a criação de entradas de DNS CNAME seja opcional, a criação de registros CNAME facilita o registro para os usuários. Se nenhum registro CNAME de registro for encontrado, os usuários serão solicitados a inserir manualmente o nome do servidor MDM `https://manage.microsoft.com`.  Os registros de recursos de CNAME deve conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

  `EnterpriseRegistration.windows.net` – dá suporte a dispositivos Windows 8.1 e Windows 10 Mobile que serão registrados no Azure Active Directory usando sua conta corporativa ou de estudante

  Se sua empresa usa vários domínios para credenciais de usuário, crie registros CNAME para cada domínio.

  Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Alterações de registro DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

3.  **Verificar CNAME**<br>No [console de administração do Intune](http://manage.microsoft.com), clique em **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e clique em **Testar Detecção Automática**.

  ![Caixa de diálogo de gerenciamento de dispositivo do Windows](../media/enroll-intune-winenr.png)

4.  **Etapas opcionais**<br>A etapa **Adicionar chaves de sideload** não é necessária para o Windows 10. A etapa **Carregar Certificado de Assinatura de Código** só é necessária se você vai distribuir aplicativos de LOB (linha de negócios) para dispositivos não disponíveis na Windows Store. [Saiba mais](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Informar os usuários**<br>Você precisará dizer aos usuários como registrar seus dispositivos e o que esperar quando eles forem incluídos no gerenciamento:
      - [O que dizer a seus usuários finais sobre como usar o Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Diretrizes do usuário final para dispositivos Windows](../enduser/using-your-windows-device-with-intune.md)

### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


