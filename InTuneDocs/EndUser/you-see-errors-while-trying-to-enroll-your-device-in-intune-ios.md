---
title: "Você encontra erros ao tentar registrar seu dispositivo iOS no Intune | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 57b6bb6076b24299fb54626aa55850bf8c0c2428
ms.openlocfilehash: df491807386c80dce0f45822fbc64acefda59eb3


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>Você encontra erros ao tentar registrar seu dispositivo iOS no Intune

A tabela a seguir lista os erros que você pode encontrar durante o registro do seu dispositivo iOS no Intune. Compartilhe este link com o administrador de TI. Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).

|Mensagem de erro|Problema|O que dizer ao administrador de TI|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Nenhuma política de registro|Verifique se todos os pré-requisitos de registro, como o certificado APNs (Apple Push Notification Service), foram configurados e se "iOS como plataforma" está habilitado. Para obter instruções, veja [Configurar gerenciamento de dispositivos iOS e Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Você já tem muitos dispositivos móveis registrados.|Antes de registrar outro dispositivo móvel, o usuário deve remover um de seus dispositivos móveis registrados atualmente no Portal da Empresa. Consulte as instruções para o tipo de dispositivo que você está usando: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Há um problema com o certificado que permite que seu dispositivo móvel se comunique com a rede da empresa.<br /><br />Entre em contato com os administradores de TI e informe que você recebeu a mensagem **APNSCertificateNotValid** quando tentou registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|o APNs (Apple Push Notification Service) fornece um canal para chegar aos dispositivos iOS registrados. Se as etapas para obter um certificado APNS não tiverem sido executadas ou se o certificado APNS estiver vencido, as tentativas de registro falharão e essa mensagem será exibida.<br /><br />Examine as informações sobre como configurar usuários em [Sincronizar o Active Directory e adicionar usuários ao Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) e em [Organizando usuários e dispositivos](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Há um problema com o certificado que permite que seu dispositivo móvel se comunique com a rede da empresa.<br /><br />Entre em contato com os administradores de TI e informe que você recebeu a mensagem **APNSNotOnboarded** quando tentou registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|o APNs (Apple Push Notification Service) fornece um canal para chegar aos dispositivos iOS registrados. Se as etapas para obter um certificado APNS não tiverem sido executadas ou se o certificado APNS estiver vencido, as tentativas de registro falharão e essa mensagem será exibida.<br /><br />Para obter mais informações, examine [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) (Configurar gerenciamento de iOS e Mac com o Microsoft Intune).|
|DeviceTypeNotSupported|Você pode ter tentado se registrar usando um dispositivo não iOS. O tipo de dispositivo móvel que você está tentando registrar não tem suporte.<br /><br />Verifique se o dispositivo está executando o iOS versão 8.0 ou posterior.<br /><br />Entre em contato com os administradores de TI e informe que você recebeu a mensagem **DeviceTypeNotSupported** quando tentou registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|Verifique se o dispositivo do usuário está executando o iOS versão 8.0 ou posterior.|
|UserLicenseTypeInvalid|Não é possível registrar seu dispositivo móvel porque sua conta de usuário ainda não é um membro de um grupo de usuário necessário.<br /><br />Entre em contato com os administradores de TI e informe que você recebeu a mensagem **UserLicenseTypeInvalid** quando tentou registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|Antes que possam registrar seus dispositivos, os usuários devem ser membros do grupo de usuários correto. Esta mensagem indica que eles têm o tipo de licença errado para a autoridade de gerenciamento de dispositivo móvel designado. Por exemplo, se o Intune tiver sido designado como a autoridade de gerenciamento de dispositivo móvel e eles estiverem usando uma licença do System Center 2012 R2 Configuration Manager, eles receberão esse erro.<br /><br />Examine os itens a seguir para obter mais informações:<br /><br />Examine [Configurar gerenciamento de iOS e Mac com o Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) e as informações sobre como configurar usuários no [Sincronizar o Active Directory e adicionar usuários ao Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) e em [Organizando usuários e dispositivos](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Seu administrador de TI precisa configurar o modo como os dispositivos móveis são gerenciados na sua empresa.<br /><br />Entre em contato com os administradores de TI e informe que você recebeu a mensagem **MdmAuthorityNotDefined** quando tentou registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|A autoridade de gerenciamento de dispositivo móvel não foi designada no Intune.<br /><br />Examine o item nº 1 na seção "Etapa 6: registrar dispositivos móveis e instalar um aplicativo” em [Começar com uma avaliação de 30 dias do Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|



<!--HONumber=Dec16_HO1-->


