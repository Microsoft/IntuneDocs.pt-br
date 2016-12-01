---
title: "Preparar aplicativos para o gerenciamento de aplicativo móvel | Microsoft Intune"
description: "As informações neste tópico ajudam você a decidir quando deve usar a Ferramenta de Disposição do Aplicativo e o SDK do Aplicativo para permitir que seus aplicativos de linha de negócios personalizados usem políticas de gerenciamento de aplicativos móveis."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376c9bce811ffd986242678929469f3e28bfad4c
ms.openlocfilehash: e145baf0f7366f331e8d1df994a8fa40ec693227


---

# <a name="decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune"></a>Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune
Você pode habilitar seus aplicativos para usar políticas de MAM (gerenciamento de aplicativo móvel) usando a Ferramenta de Encapsulamento de Aplicativo do Intune ou o SDK de Aplicativo do Intune. Use essas informações para saber mais sobre esses dois métodos e quando usá-los.

## <a name="intune-app-wrapping-tool"></a>Ferramenta de Encapsulamento de Aplicativo do Intune
A Ferramenta de Encapsulamento de Aplicativo é usada principalmente para aplicativos internos de linha de negócios (LOB). A ferramenta é um aplicativo de linha de comando que cria um wrapper em torno do aplicativo, o que permite que o aplicativo seja gerenciado por uma política de MAM do Intune.

O código-fonte para usar a ferramenta não é necessário, mas você precisa de credenciais de assinatura.  Para obter mais informações sobre as credenciais de assinatura, consulte o [blog do Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Para obter a documentação da Ferramenta de Disposição de Aplicativo, consulte [Ferramenta de Disposição do Aplicativo Android ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) e [Ferramenta de Disposição do Aplicativo iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

A Ferramenta de Disposição de Aplicativo **não** dá suporte a aplicativos da App Store da Apple ou da Google Play Store. Ele também não dá suporte a alguns recursos que exigem integração do desenvolvedor (consulte a tabela de comparação de recursos a seguir).

Você deve usar a Ferramenta de Encapsulamento de Aplicativo, em vez do SDK, se o aplicativo já tiver sido escrito ou se o código-fonte não estiver disponível.

Para obter mais informações sobre a Ferramenta de Disposição de Aplicativo para MAM em dispositivos que não estão registrados no Intune, consulte [Proteger dados e aplicativos de linha de negócios em dispositivos não registrados no Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### <a name="supported-app-development-platforms"></a>Plataformas de desenvolvimento de aplicativo com suporte

|**Ferramenta de Disposição de Aplicativo** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Sim|Sim|
|**Android**| Não |Sim|

## <a name="intune-app-sdk"></a>SDK do Aplicativo do Intune
O SDK do Aplicativo é projetado principalmente para clientes que têm aplicativos na App Store da Apple e/ou na Google Play Store e desejam gerenciar os aplicativos com o Intune. No entanto, qualquer aplicativo pode tirar proveito da integração do SDK, até mesmo aplicativos de linha de negócios.

Para saber mais sobre o SDK, consulte a [Visão Geral](/intune/develop/intune-app-sdk). Para começar a usar o SDK, consulte [Getting Started With the Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started) (Introdução ao SDK de Aplicativo do Microsoft Intune).

### <a name="supported-app-development-platforms"></a>Plataformas de desenvolvimento de aplicativo com suporte

|**SDK do Aplicativo do Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Sim – usar o componente Xamarin do SDK de Aplicativo do Intune.|Sim – usar o plug-in Cordova do SDK de Aplicativo do Intune.|
|**Android**| Sim – usar o Componente Xamarin do SDK de Aplicativo do Intune.|Sim – usar o plug-in Cordova do SDK de Aplicativo do Intune.|

## <a name="feature-comparison"></a>Comparação de recursos
Esta tabela lista as configurações que você pode usar para o SDK do Aplicativo e a Ferramenta de Encapsulamento de Aplicativo.

> [!NOTE]
> A Ferramenta de Disposição de Aplicativo só pode ser usada quando você estiver usando o Intune autônomo ou o Intune com o Configuration Manager.

|Recurso|SDK do Aplicativo|Ferramenta de Encapsulamento de Aplicativo|
|-----------|---------------------|-----------|
|Restringir o conteúdo da web a ser exibido em um navegador gerenciado corporativo|X|X|
|Evitar backups do Android, iTunes ou iCloud|X|X|
|Permitir que o aplicativo transfira dados para outros aplicativos|X|X|
|Permitir que o aplicativo receba dados de outros aplicativos|X|X|
|Restringir recortar, copiar e colar com outros aplicativos|X|X|
|Solicitar PIN simples para acesso|X|X|
|Substituir o PIN do aplicativo interno pelo PIN do Intune|X||
|Especificar o número de tentativas antes da redefinição do PIN|X|X|
|Exigir a impressão digital em vez do PIN (somente iOS)<br></br>**Observação:** disponível apenas em ambientes de MAM.|X||
|Exigir credenciais corporativas para acesso|X|X|
|Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou root|X|X|
|Criptografar dados do aplicativo|X|X|
|Verificar novamente os requisitos de acesso após uma quantidade especificada de minutos|X|X|
|Especificar o período de cortesia offline|X|X|
|Bloquear captura de tela (somente para Android)|X|X|
|Apagamento completo|X|X|
|Apagamento seletivo <br></br>**Observação:** para iOS, quando o perfil de gerenciamento é removido, o aplicativo também é removido.|X||
|Impedir "Salvar como" |X||
|Suporte para múltiplas identidades|X||
|Suporte para MAM sem registro de dispositivo|X|X|
### <a name="see-also"></a>Consulte também

[Ferramenta de disposição do aplicativo Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Ferramenta de disposição do aplicativo iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Usar o SDK para habilitar aplicativos para o gerenciamento de aplicativo móvel](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO3-->


