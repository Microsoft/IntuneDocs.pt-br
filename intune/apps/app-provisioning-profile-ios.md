---
title: Perfis de provisionamento de aplicativo iOS no Microsoft Intune
titleSuffix: ''
description: O Intune fornece as ferramentas para atribuir de forma proativa um novo perfil de provisionamento a dispositivos que têm aplicativos que estão se aproximando da expiração.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 624c6cec2a887396cb6ef6508ab26a16d72f8f7c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725316"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Usar os perfis de provisionamento de aplicativo iOS para impedir que os aplicativos expirem

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

## <a name="introduction"></a>Introdução

Os aplicativos de linha de negócios do iOS da Apple atribuídos a iPhones e iPads são criados com um perfil de provisionamento incluído e código assinado com um certificado. Quando o aplicativo é executado, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento. As validações a seguir ocorrem:

- **Integridade do arquivo de instalação** – o iOS compara os detalhes de aplicativos com a chave pública do certificado de assinatura de empresa. Se eles forem diferentes, o conteúdo dos aplicativos poderá ter sido alterado e ele não terá permissão para se executado.
- **Imposição de funcionalidades** – o iOS tenta aplicar as funcionalidades do aplicativo do perfil de provisionamento corporativo (não perfis de provisionamento de desenvolvedor individuais) contidas no arquivo de instalação (.ipa) do aplicativo.


A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Enquanto o certificado ainda for válido, o Intune fornecerá as ferramentas para atribuir proativamente um novo perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.
Depois que o certificado expirar, você deverá assinar o aplicativo novamente com um novo certificado e inserir um novo perfil de provisionamento com a chave do novo certificado.

Como administrador, você pode incluir e excluir grupos de segurança para atribuir a configuração de provisionamento de aplicativo do iOS. Por exemplo, você pode atribuir uma configuração de provisionamento de aplicativo iOS a Todos os Usuários, mas excluir um grupo executivo.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Como criar um perfil de provisionamento de aplicativo móvel iOS

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, escolha **Aplicativos clientes**.
1. Na carga de trabalho **Aplicativos clientes**, escolha **Gerenciar** > **Perfis de provisionamento de aplicativo iOS**.
2. No painel da lista de perfis, escolha **Criar perfil**.
3. No painel **Criar perfil**, configure os valores a seguir:
    - **Nome** – forneça um nome para essa política de perfil de provisionamento móvel.
    - **Descrição** – de maneira opcional, forneça uma descrição para a política.
    - **Carregar arquivo de perfil**: escolha o ícone **Abrir** e selecione um arquivo de Perfil de Configuração Móvel da Apple (com a extensão `.mobileprovision`) que você baixou do [site do Desenvolvedor da Apple](https://developer.apple.com/).
4. Ao terminar, escolha **Criar**.

## <a name="next-steps"></a>Próximas etapas

Atribua o perfil aos dispositivos iOS necessários. Para saber mais, use as etapas em [Como atribuir perfis de dispositivo](../device-profile-assign.md).