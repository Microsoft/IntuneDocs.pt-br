---
title: Configurar gerenciamento de iOS e MAC | Microsoft Intune
description: "Habilite MDM (gerenciamento de dispositivo móvel) para dispositivos iOS, inclusive iPads e iPhones, bem como dispositivos Mac OS X com o Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b3f6323912707d56d23380217a07e6474593d83f
ms.openlocfilehash: f93f7bfe99e878691dccd24c124a781c8607e7c6


---

# Configurar gerenciamento de dispositivos iOS e Mac
Para obter ajuda para configurar seu dispositivo iOS ou Mac, consulte [Usando seu dispositivo iOS ou Mac OS X com o Intune](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md).

O Intune possibilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e dispositivos Mac OS X, além de conceder aos usuários acesso a aplicativos e email da empresa. Um certificado APNs (Apple Push Notification Service) é necessário para o Intune gerenciar dispositivos iOS e Mac. Depois que o certificado for adicionado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos ou o administrador poderá configurar o [gerenciamento de dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Configurar Intune**<br>
    Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](prerequisites-for-enrollment.md#set-mobile-device-management-authority) como **Microsoft Intune** e configure o MDM.

2.  **Obter uma solicitação de assinatura de certificado**<br>
    Como usuário administrativo, abra o [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e escolha **Baixar a Solicitação de Certificado APNs**. Salve o arquivo (.csr) da solicitação de assinatura do certificado localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.

    ![Caixa de diálogo para carregar certificado do APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Obter um certificado do Apple Push Notification Service**<br>
    Vá para o [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) e entre com sua ID da Apple corporativa para criar o certificado APNs usando o arquivo .csr. Depois de clicar em **Carregar** no Portal Apple Push Certificates, você receberá um arquivo .json que não pode ser usado para o APNs. Conclua o download e retorne ao Portal Certificados por Push da Apple para **Certificados de Servidores de Terceiros** e escolha **Download**.

    Baixe o certificado APNs (.pem) e salve o arquivo localmente. Essa ID da Apple deve ser usada posteriormente para renovar seu certificado APNs.

4.  **Adicionar o certificado de APNs ao Intune**<br>
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e escolha **Carregar o certificado APNs**. Vá até o arquivo de certificado (.pem), escolha **Abrir** e digite sua **ID da Apple**. Com o certificado APNs, o Intune pode registrar e gerenciar dispositivos iOS enviando políticas para dispositivos móveis registrados.

5.  **Diga aos usuários como obter acesso aos recursos da empresa com o portal da empresa**<br>
    Seus usuários precisam saber como registrar seus dispositivos e o que esperar após eles passarem a fazer parte do gerenciamento.
    - [O que dizer a seus usuários finais sobre como usar o Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Diretrizes do usuário final para dispositivos iOS e Mac](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Se sua empresa ou organização adquirir dispositivos iOS para os usuários, esses dispositivos também poderão ser registrados para gerenciamento como [dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Consulte também
[Pré-requisitos para registrar-se no Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Oct16_HO3-->


