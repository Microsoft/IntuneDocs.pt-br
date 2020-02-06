---
title: Preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune
description: As informações neste tópico ajudam você a decidir quando deve usar a Ferramenta de Disposição do Aplicativo e o SDK do Aplicativo para permitir que seus aplicativos de linha de negócios personalizados usem políticas de gerenciamento de aplicativos móveis.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 842af9c8fffcb3755c81260739f4949768e75bac
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912668"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>Preparar aplicativos de linha de negócios para as políticas de proteção de aplicativos

Você pode habilitar seus aplicativos para usar políticas de proteção usando a Ferramenta de Encapsulamento de Aplicativos do Intune ou o SDK de Aplicativos do Intune. Use essas informações para saber mais sobre esses dois métodos e quando usá-los.

## <a name="intune-app-wrapping-tool"></a>Ferramenta de Encapsulamento de Aplicativo do Intune

A Ferramenta de Encapsulamento de Aplicativo é usada principalmente para aplicativos **internos** de linha de negócios (LOB). A ferramenta é um aplicativo de linha de comando que cria um wrapper envolvendo o aplicativo, que permite que o aplicativo seja gerenciado por uma política de proteção de aplicativo do Intune. Ao proteger um aplicativo fornecido por um fornecedor de software independente (ISV), é importante esclarecer se o ISV ainda oferecerá suporte ao aplicativo encapsulado.

O código-fonte para usar a ferramenta não é necessário, mas você precisa de credenciais de assinatura. Para obter mais informações sobre as credenciais de assinatura, consulte o [blog do Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Para acessar a documentação da Ferramenta de Disposição do Aplicativo, confira [Ferramenta de Disposição do Aplicativo do Android](app-wrapper-prepare-android.md) e [Ferramenta de Disposição do Aplicativo do iOS](app-wrapper-prepare-ios.md).

A Ferramenta de Disposição de Aplicativo **não** dá suporte a aplicativos da App Store da Apple ou da Google Play Store. Ele também não dá suporte a alguns recursos que exigem integração do desenvolvedor (consulte a tabela de comparação de recursos a seguir).

Para obter mais informações sobre a Ferramenta de Encapsulamento de Aplicativos para políticas de proteção de aplicativos em dispositivos que não estão registrados no Intune, consulte [Proteger aplicativos e dados de linha de negócios em dispositivos não registrados no Microsoft Intune](../apps/apps-add.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Motivos para usar a Ferramenta de Encapsulamento de Aplicativos

* Seu aplicativo não tem recursos internos para proteção de dados
* Seu aplicativo é implantado internamente
* Você não tem acesso ao código-fonte do aplicativo
* Você não desenvolveu o aplicativo
* Seu aplicativo tem o mínimo de experiências de autenticação do usuário

### <a name="supported-app-development-platforms"></a>Plataformas de desenvolvimento de aplicativo com suporte

|**Ferramenta de Disposição de Aplicativo** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Sim|Sim|
|**Android**|Não – usar as [Associações do Xamarin do SDK de Aplicativo do Intune](app-sdk-xamarin.md).|Sim|

## <a name="intune-app-sdk"></a>SDK do Aplicativo do Intune

O SDK do Aplicativo é projetado principalmente para clientes que têm aplicativos na App Store da Apple e/ou na Google Play Store e desejam gerenciar os aplicativos com o Intune. No entanto, qualquer aplicativo pode tirar proveito da integração do SDK, até mesmo aplicativos de linha de negócios.

Para saber mais sobre o SDK, consulte a [Visão Geral](app-sdk.md). Para começar a usar o SDK, consulte [Getting Started With the Microsoft Intune App SDK](app-sdk-get-started.md) (Introdução ao SDK de Aplicativo do Microsoft Intune).

### <a name="reasons-to-use-the-sdk"></a>Motivos para usar o SDK

* Seu aplicativo não tem recursos internos para proteção de dados
* Seu aplicativo está implantado em uma loja de aplicativos pública, como Google Play ou App Store da Apple
* Você é desenvolvedor de aplicativos e tem experiência técnica para usar o SDK
* Seu aplicativo tem outras integrações de SDK
* Seu aplicativo é atualizado com frequência

### <a name="supported-app-development-platforms"></a>Plataformas de desenvolvimento de aplicativo com suporte

|**SDK do Aplicativo do Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Sim – use [Associações do Xamarin do SDK de Aplicativo do Intune](app-sdk-xamarin.md).|Não|
|**Android**| Sim – use [Associações do Xamarin do SDK de Aplicativo do Intune](app-sdk-xamarin.md).|Não|

## <a name="not-using-an-app-development-platform-listed-above"></a>Não está usando uma plataforma de desenvolvimento de aplicativo listada acima?

A equipe de desenvolvimento do SDK do Intune testa ativamente e mantém o suporte para aplicativos criados com as plataformas nativas do Android, iOS (Obj-C, Swift), Xamarin, Xamarin.Forms e Cordova. Embora alguns clientes tiveram sucesso na integração do SDK do Intune com outras plataformas, como React Native e NativeScript, não fornecemos orientação explícita ou plug-ins para desenvolvedores de aplicativos que usem algo diferente de nossas plataformas que têm suporte. 

## <a name="feature-comparison"></a>Comparação de recursos

Esta tabela lista as configurações que são habilitadas quando um aplicativo usa o SDK do Aplicativo ou a App Wrapping Tool. Alguns recursos exigem que os desenvolvedores de aplicativos apliquem lógica fora da integração básica com o SDK do Intune e, dessa forma, não são habilitadas quando o aplicativo usa a App Wrapping Tool. 

|Recurso|SDK do Aplicativo|Ferramenta de Encapsulamento de Aplicativo|
|-----------|---------------------|-----------|
|Restringir o conteúdo da web a ser exibido em um navegador gerenciado corporativo|X|X|
|Impedir backups do Android, iTunes ou iCloud|X|X|
|Permitir que o aplicativo transfira dados para outros aplicativos|X|X|
|Permitir que o aplicativo receba dados de outros aplicativos|X|X|
|Restringir recortar, copiar e colar com outros aplicativos|X|X|
|Especificar o número de caracteres que podem ser recortados ou copiados de um aplicativo gerenciado|X|X|
|Solicitar PIN simples para acesso|X|X|
|Especificar o número de tentativas antes da redefinição do PIN|X|X|
|Permitir a impressão digital em vez do PIN|X|X|
|Permitir reconhecimento facial, em vez de PIN (somente iOS)|X|X|
|Exigir credenciais corporativas para acesso|X|X|
|Definir uma data de expiração do PIN|X|X|
|Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou root|X|X|
|Criptografar dados do aplicativo|X|X|
|Verificar novamente os requisitos de acesso após uma quantidade especificada de minutos|X|X|
|Especificar o período de cortesia offline|X|X|
|Bloquear captura de tela (somente para Android)|X|X|
|Suporte para MAM sem registro de dispositivo|X|X|
|Apagamento completo de dados de aplicativo|X|X|
|Apagamento Seletivo de dados corporativos e de estudante em cenários com várias identidades <br><br>**Observação:** para iOS, quando o perfil de gerenciamento é removido, o aplicativo também é removido.|X||
|Impedir "Salvar como"|X||
|Configuração do Aplicativo de Destino (ou configuração do aplicativo por meio do "Canal do MAM")|X|X|
|Suporte para múltiplas identidades|X||
|Estilo Personalizável |X|||
|Conexões de VPN do aplicativo sob demanda com mVPN Citrix|X|X| 
|Desabilitar a sincronização de contatos|X|X|
|Desabilitar a impressão|X|X|
|Exigir versão mínima do aplicativo|X|X|
|Exigir sistema operacional mínimo|X|X|
|Exibir versão mínima do patch de segurança do Android (somente Android)|X|X|
|Exigir SDK mínimo do Intune para iOS (somente iOS)|X|X|
|Atestado de dispositivo SafetyNet (somente Android)|X|X|
|Verificação de ameaças em aplicativos (somente Android)|X|X|
|Exigir nível de risco do dispositivo máximo do fornecedor da Defesa contra Ameaças Móveis|X||
|Configurar conteúdo de notificação do aplicativo para contas da organização|X|X|
|Exigir o uso de teclados aprovados ( somente Android)|X|X|
|Exigir política de proteção do aplicativo (acesso condicional)|X||
|Exigir aplicativo cliente aprovado (acesso condicional)|X||

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre as políticas de proteção de aplicativos e o Intune, consulte os tópicos a seguir:

- [Ferramenta de disposição do aplicativo Android](app-wrapper-prepare-android.md)<br>
- [Ferramenta de encapsulamento de aplicativos do iOS](app-wrapper-prepare-ios.md)<br>
- [Usar o SDK para habilitar aplicativos para o gerenciamento de aplicativo móvel](app-sdk.md)
