---
title: Configurar o gerenciamento do Windows 10 Mobile e do Windows Phone | Microsoft Intune
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para dispositivos Windows 10 Mobile ou Windows Phone com o Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0b4bf6aa6fa9d693c0458562e7fcb71fc8000bb4
ms.openlocfilehash: 46bd457af51d3fac513cfc36af1766e1e37222cd


---


# Configurar o gerenciamento do Windows 10 Mobile e do Windows Phone com o Microsoft Intune

Como administrador do Intune, você pode habilitar o registro e o gerenciamento de dispositivos Windows Mobile 10 e Windows Phone de duas maneiras:

- **[Registro automático com o Azure Active Directory](#azure-active-directory-enrollment)** – usuários do Windows 10 e do Windows 10 Mobile registram seus dispositivos adicionando uma conta corporativa ou de estudante para o dispositivo
- **[Registro no Portal da Empresa](#company-portal-app-enrollment)** – usuários do Windows Phone 8.1 e posteriores registram seus dispositivos baixando e instalando o aplicativo de Portal da Empresa e inserindo as credenciais de sua conta corporativa ou de estudante no aplicativo.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Registro de aplicativo no Portal da Empresa
Você pode permitir que os usuários instalem e registrem seus dispositivos usando o aplicativo do Portal da Empresa do Intune. Se você criar registros de recursos de DNS CNAME, os usuários se conectam e se registram no Intune sem inserir um nome do servidor. Se gerenciar dispositivos Windows Phone 8.0 ou precisar implantar o Portal da Empresa em dispositivos Windows Phone, você também precisará baixar e assinar o aplicativo do Portal da Empresa. Consulte [Set up Windows Phone 8.0 management](set-up-windows-phone-8.0-management-with-microsoft-intune.md) (Configurar o gerenciamento do Windows Phone 8.0).

1.  **Configurar Intune**<br>Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de MDM (gerenciamento de dispositivo móvel)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) como **Microsoft Intune** e configure o MDM.

2.  **Criar CNAMEs** (opcional)<br>Criar registros de recurso DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para manage.microsoft.com. Se houver mais de um domínio verificado, crie um registro CNAME para cada domínio. Os registros de recursos de CNAME deve conter as seguintes informações:

  |TYPE|Nome do host|Aponta para|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

  `EnterpriseRegistration.windows.net` – dá suporte a dispositivos Windows 8.1 e Windows 10 Mobile que serão registrados no Azure Active Directory usando sua conta corporativa ou de estudante

  Se sua empresa usa vários domínios para credenciais de usuário, crie registros CNAME para cada domínio.

  Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com. Alterações em registros DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

3.  **Verificar CNAME**<br>No [Console do administrador do Intune](http://manage.microsoft.com), escolha **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows Phone**. Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e escolha **Testar Detecção Automática**.

    ![Caixa de diálogo Configurar o gerenciamento de dispositivo móvel para Windows](../media/windows-phone-enrollment.png)

4.  **Etapas opcionais**<br>A etapa **Adicionar chaves de sideload** não é necessária para o Windows 10. A etapa **Carregar Certificado de Assinatura de Código** será necessária somente se você for distribuir aplicativos de LOB (linha de negócios) que não estão disponíveis da Windows Store para dispositivos. [Saiba mais](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

5.  **Informar os usuários**<br>Seus usuários precisam saber como registrar seus dispositivos e o que esperar após eles passarem a fazer parte do gerenciamento.
    - [O que dizer a seus usuários finais sobre como usar o Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Diretrizes do usuário final para dispositivos Windows](../enduser/using-your-windows-device-with-intune.md)

Nenhum trabalho adicional é necessário, a menos que você vá implantar o Portal da Empresa em dispositivos.  As etapas 2 e 3 no console do administrador podem ser ignoradas com segurança.



<!--HONumber=Oct16_HO3-->


