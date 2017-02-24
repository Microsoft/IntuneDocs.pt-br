---
title: Configurar o gerenciamento do iOS e do Mac | Microsoft Docs
description: "Habilite MDM (gerenciamento de dispositivo móvel) para dispositivos iOS, inclusive iPads e iPhones, bem como dispositivos Mac OS X com o Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: afca2af0b07b939adc66c8804f04a1125e12001b
ms.openlocfilehash: 9c71a83f9514187753360fa9c2085584d1b76711


---

# <a name="set-up-ios-and-mac-device-management"></a>Configurar gerenciamento de dispositivos iOS e Mac

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e dispositivos macOS, além de permitir acesso a aplicativos e ao email da empresa aos usuários. Um certificado APNs (Apple Push Notification Service) é necessário para o Intune gerenciar dispositivos iOS e Mac. Depois que o certificado for adicionado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos ou o administrador poderá configurar o [gerenciamento de dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Configurar Intune**<br>
    Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](prerequisites-for-enrollment.md#step-2-set-mdm-authority) como **Microsoft Intune** e configure o MDM.

2.  **Obtenha uma solicitação de assinatura de certificado**<br>
    Como usuário administrativo, abra o [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e escolha **Baixar a Solicitação de Certificado APNs**. Salve o arquivo (.csr) da solicitação de assinatura do certificado localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.

    ![Caixa de diálogo para carregar certificado do APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Obtenha um certificado do serviço Apple Push Notification**<br>
    Vá para o [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) e entre com sua ID da Apple corporativa para criar o certificado APNs usando o arquivo .csr. Depois de clicar em **Carregar** no Portal Apple Push Certificates, você receberá um arquivo .json que não pode ser usado para o APNs. Conclua o download e retorne ao Portal Certificados por Push da Apple para **Certificados de Servidores de Terceiros** e escolha **Download**.

    Baixe o certificado APNs (.pem) e salve o arquivo localmente.

    > [!NOTE]
    > Todo ano, você precisa renovar (não substituir) este certificado APNs. Use essa mesma ID Apple para entrar no Portal de Certificados por Push da Apple para renovar o certificado e, em seguida, use as mesmas instruções deste tópico para baixar o certificado e, em seguida, carregá-lo no Intune.

4.  **Adicionar o certificado de APNs ao Intune**<br>
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e escolha **Carregar o certificado APNs**. Vá até o arquivo de certificado (.pem), escolha **Abrir** e digite sua **ID da Apple**. Com o certificado APNs, o Intune pode registrar e gerenciar dispositivos iOS enviando políticas para dispositivos móveis registrados.

5.  **Informe aos usuários como registrar seus dispositivos para obter acesso aos recursos da empresa.**

    Para obter instruções sobre o registro de usuário final, confira [Registrar seu dispositivo iOS no Intune](../enduser/enroll-your-device-in-intune-ios.md) e [Registrar seu dispositivo macOS no Intune](../enduser/enroll-your-device-in-intune-macos.md). O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.

    Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:
    - [Recursos sobre a experiência do usuário final com o Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
    - [Diretrizes do usuário final para dispositivos iOS e Mac](../enduser/using-your-ios-or-macOS-device-with-intune.md)

Se sua empresa ou organização adquirir dispositivos iOS para os usuários, esses dispositivos também poderão ser registrados para gerenciamento como [dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Consulte Também
[Pré-requisitos para registro no Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO3-->


