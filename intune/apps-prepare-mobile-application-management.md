---
title: "Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune"
description: "As informações neste tópico ajudam você a decidir quando deve usar a Ferramenta de Disposição do Aplicativo e o SDK do Aplicativo para permitir que seus aplicativos de linha de negócios personalizados usem políticas de gerenciamento de aplicativos móveis."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8b218ce38a7e76135a62b1155dbf9060ba511cc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="prepare-line-of-business-apps-for-mam"></a>Preparar a linha de aplicativos de negócios para o MAM

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Você pode habilitar seus aplicativos para usar políticas de MAM (gerenciamento de aplicativo móvel) usando a Ferramenta de Encapsulamento de Aplicativo do Intune ou o SDK de Aplicativo do Intune. Use essas informações para saber mais sobre esses dois métodos e quando usá-los.

## <a name="intune-app-wrapping-tool"></a>Ferramenta de Encapsulamento de Aplicativo do Intune
A Ferramenta de Encapsulamento de Aplicativo é usada principalmente para aplicativos internos de linha de negócios (LOB). A ferramenta é um aplicativo de linha de comando que cria um wrapper em torno do aplicativo, o que permite que o aplicativo seja gerenciado por uma política de MAM do Intune.

O código-fonte para usar a ferramenta não é necessário, mas você precisa de credenciais de assinatura.  Para obter mais informações sobre as credenciais de assinatura, consulte o [blog do Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Para obter a documentação da Ferramenta de Disposição de Aplicativo, consulte [Ferramenta de Disposição do Aplicativo Android ](app-wrapper-prepare-android.md) e [Ferramenta de Disposição do Aplicativo iOS](app-wrapper-prepare-ios.md).

A Ferramenta de Disposição de Aplicativo **não** dá suporte a aplicativos da App Store da Apple ou da Google Play Store. Ele também não dá suporte a alguns recursos que exigem integração do desenvolvedor (consulte a tabela de comparação de recursos a seguir).


Para obter mais informações sobre a Ferramenta de Disposição de Aplicativo para MAM em dispositivos que não estão registrados no Intune, consulte [Proteger dados e aplicativos de linha de negócios em dispositivos não registrados no Microsoft Intune](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Motivos para usar a Ferramenta de Encapsulamento de Aplicativos:
* Seu aplicativo não tem recursos internos de proteção de dados.
* Seu aplicativo é simples.
* Seu aplicativo é implantado internamente.
* Você não tem acesso ao código-fonte do aplicativo
* Você não desenvolveu o aplicativo.
* Seu aplicativo tem experiências de autenticação mínimas do usuário.


### <a name="supported-app-development-platforms"></a>Plataformas de desenvolvimento de aplicativo com suporte

|**Ferramenta de Disposição de Aplicativo** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Sim|Sim|
|**Android**| Não |Sim|

## <a name="intune-app-sdk"></a>SDK do Aplicativo do Intune
O SDK do Aplicativo é projetado principalmente para clientes que têm aplicativos na App Store da Apple e/ou na Google Play Store e desejam gerenciar os aplicativos com o Intune. No entanto, qualquer aplicativo pode tirar proveito da integração do SDK, até mesmo aplicativos de linha de negócios.

Para saber mais sobre o SDK, consulte a [Visão Geral](app-sdk.md). Para começar a usar o SDK, consulte [Getting Started With the Microsoft Intune App SDK](app-sdk-get-started.md) (Introdução ao SDK de Aplicativo do Microsoft Intune).

### <a name="reasons-to-use-the-sdk"></a>Motivos para usar o SDK
* Seu aplicativo não tem recursos internos de proteção de dados.
* Seu aplicativo é complexo e contém muitas experiências.
* Seu aplicativo é implantado em uma loja de aplicativos pública, como Google Play ou App Store da Apple.
* Você é um desenvolvedor de aplicativos e tem experiência técnica para usar o SDK.
* Seu aplicativo tem outras integrações de SDK.
* Seu aplicativo é atualizado com frequência.

### <a name="supported-app-development-platforms"></a>Plataformas de desenvolvimento de aplicativo com suporte

|**SDK do Aplicativo do Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Sim – usar o [Componente Xamarin do SDK de Aplicativo do Intune](app-sdk-xamarin.md).|Sim – usar o [plug-in Cordova do SDK de Aplicativo do Intune](app-sdk-cordova.md).|
|**Android**| Sim – usar o [Componente Xamarin do SDK de Aplicativo do Intune](app-sdk-xamarin.md).|Sim – usar o [plug-in Cordova do SDK de Aplicativo do Intune](app-sdk-cordova.md).|

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
|Permitir a impressão digital em vez do PIN |X|X|
|Exigir credenciais corporativas para acesso|X|X|
|Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou root|X|X|
|Criptografar dados do aplicativo|X|X|
|Verificar novamente os requisitos de acesso após uma quantidade especificada de minutos|X|X|
|Especificar o período de cortesia offline|X|X|
|Bloquear captura de tela (somente para Android)|X|X|
|Suporte para MAM sem registro de dispositivo|X|X|
|Apagamento completo|X|X|
|Apagamento seletivo <br></br>**Observação:** para iOS, quando o perfil de gerenciamento é removido, o aplicativo também é removido.|X||
|Impedir "Salvar como" |X||
|Configuração de aplicativo direcionado |X||
|Suporte para múltiplas identidades|X||
|Estilo Personalizável |X|||
### <a name="see-also"></a>Consulte também

[Ferramenta de disposição do aplicativo Android](app-wrapper-prepare-android.md)</br>
[Ferramenta de disposição do aplicativo iOS](app-wrapper-prepare-ios.md)</br>
[Usar o SDK para habilitar aplicativos para o gerenciamento de aplicativo móvel](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
