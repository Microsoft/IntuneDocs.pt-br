---
# required metadata

title: Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune
Você pode habilitar seus aplicativos para usar políticas de gerenciamento de aplicativo móvel usando a Ferramenta de Encapsulamento de Aplicativos do Intune ou o SDK de Aplicativos do Intune. Use essas informações para saber mais sobre esses dois métodos e quando usá-los.

## Ferramenta de Encapsulamento de Aplicativo do Intune
A Ferramenta de Encapsulamento de Aplicativo é usada principalmente para aplicativos internos de linha de negócios (LOB). A ferramenta é um aplicativo de linha de comando que cria um wrapper no aplicativo, que permite que o aplicativo seja gerenciado por uma política de gerenciamento de aplicativos móveis do Intune. O código-fonte para usar a ferramenta não é necessário, mas você precisa de credenciais de assinatura.  Para obter mais informações sobre as credenciais de assinatura, consulte o [blog do Intune](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx). Para obter a documentação da Ferramenta de disposição de aplicativo, consulte [Ferramenta de disposição do aplicativo Android ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) e [Ferramenta de disposição do aplicativo iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

A Ferramenta de Encapsulamento de Aplicativo não dá suporte a aplicativos na Windows Store ou Play Store ou a recursos que exigem integração do tempo de desenvolvimento (consulte a tabela de comparação de recursos a seguir).

Você deve usar a Ferramenta de Encapsulamento de Aplicativo, em vez do SDK, se o aplicativo já tiver sido escrito ou se o código-fonte não estiver disponível.

## SDK do Aplicativo do Intune
O SDK do Aplicativo é projetado principalmente para clientes que têm aplicativos na Windows Store ou Play Store e desejam a capacidade de gerenciar os aplicativos com o Intune. No entanto, qualquer aplicativo podem tirar proveito da integração do SDK, mesmo se for um aplicativo LOB.

Para integrar o SDK, você precisa ter acesso ao código-fonte do aplicativo. Para obter instruções sobre como integrar o SDK, consulte [Microsoft Intune App SDK (SDK do aplicativo Microsoft Intune)](https://msdn.microsoft.com/library/mt627769.aspx).

## Comparação de recursos
Esta tabela lista as configurações que você pode usar para o SDK do Aplicativo e a Ferramenta de Encapsulamento de Aplicativo.

> [!NOTE]
> A Ferramenta de disposição do aplicativo só pode ser usada quando você estiver usando o Intune Standalone ou o Intune com o Configuration Manager.

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

### Consulte também
[Ferramenta de disposição do aplicativo Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Ferramenta de disposição do aplicativo iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Use o SDK para habilitar aplicativos para o gerenciamento de aplicativos móveis](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->

