---
title: Configurar gerenciamento de iOS e MAC | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bb44d53c87bec1b6892bf49a65f3df684199ed08
ms.openlocfilehash: 9766b6e64259d809b04e6f6004c25ed88ad72659


---

# Configurar gerenciamento de dispositivos iOS e Mac
Com o Microsoft Intune, você pode habilitar BYOD (“traga seu próprio dispositivo”) para registro de dispositivos iOS e Mac OS X para dar acesso ao email e a aplicativos da empresa para os usuários do iPhone, iPad e Mac. Depois de habilitado, os usuários podem instalar o aplicativo de Portal da Empresa do Intune e seus dispositivos podem ser direcionados a políticas que usam o console de administração do Intune.

Antes que você possa gerenciar dispositivos iOS com o Intune, os dispositivos devem ser capazes de se comunicar com o Intune. A Apple requer uma relação de confiança com o Intune, estabelecida com a importação de um certificado do APNs (Apple Push Notification Service).

1.  **Configurar Intune**<br>
    Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) como **Microsoft Intune** e configure o MDM.

2.  **Obter uma solicitação de assinatura de certificado**<br>
    Como um usuário administrativo, abra o [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e clique em **Baixar a Solicitação de Certificado APNs**. Salve o arquivo (.csr) da solicitação de assinatura do certificado localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.

    ![Caixa de diálogo para carregar certificado do APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Obter um certificado do Apple Push Notification Service**<br>
    Vá para o [Portal de Certificados Apple Push](http://go.microsoft.com/fwlink/?LinkId=269844) e entre com sua ID Apple corporativa para criar o certificado APNs usando o arquivo .csr. Depois de clicar em **Carregar** no Portal Certificados por Push da Apple, você receberá um arquivo .json que não pode ser usado para o APNs. Conclua o download e retorne ao Portal Certificados por Push da Apple para **Certificados de Servidores de Terceiros** e clique em **Download**.

    Baixe o certificado APNs (.pem) e salve o arquivo localmente. Essa ID da Apple deve ser usada no futuro para renovar seu certificado APNs.

4.  **Adicionar o certificado de APNs ao Intune**<br>
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e clique em **Carregar o certificado APNs**. **Vá** até o arquivo de certificado (.pem) e clique em **Abrir** e, em seguida, digite sua **ID Apple**. Com o certificado APNs, o Intune pode registrar e gerenciar dispositivos iOS enviando políticas para dispositivos móveis registrados.

5.  **Diga aos usuários como obter acesso aos recursos da empresa com o portal da empresa**<br>
    Seus usuários precisam saber como registrar seus dispositivos e o que esperar quando eles são abertos no gerenciamento. [O que dizer a seus usuários finais sobre como usar o Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Se sua empresa ou organização adquirir dispositivos iOS para os usuários, esses dispositivos também poderão ser registrados para gerenciamento como [dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


