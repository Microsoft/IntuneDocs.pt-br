---
title: Perfis de provisionamento de aplicativo iOS no Microsoft Intune
titleSuffix: ''
description: O Intune fornece as ferramentas para atribuir de forma proativa um novo perfil de provisionamento a dispositivos que têm aplicativos que estão se aproximando da expiração.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/14/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c0b5f087494e8033cb9645d0a08edd4e1c481a2c
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584945"
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
2. No painel do **Intune**, escolha **Aplicativos cliente** > **Perfis de provisionamento de aplicativo iOS** > **Criar perfil**.
3. Na página **Conceitos Básicos**, adicione os seguintes valores:
    - **Nome** – forneça um nome para essa política de perfil de provisionamento móvel.
    - **Descrição** – de maneira opcional, forneça uma descrição para a política.
    - **Carregar arquivo de perfil**: escolha o ícone **Abrir** e selecione um arquivo de Perfil de Configuração Móvel da Apple (com a extensão `.mobileprovision`) que você baixou do [site do Desenvolvedor da Apple](https://developer.apple.com/).

   A **Data de validade** será populada com base em um valor no arquivo Perfil de Configuração Móvel da Apple que você adicionou acima.<br>

   <img alt="Create profile - Basics" src="~/apps/media/app-provisioning-profile-ios/app-provisioning-profile-ios-01.png">

4. Clique em **Avançar: Marcas de escopo**.<br>
   Na página **Marcas de escopo**, você pode configurar opcionalmente marcas de escopo para determinar quem pode ver o perfil de provisionamento de aplicativos iOS no Intune. Saiba mais sobre marcas de escopo em [Usar controle de acesso baseado em função e marcas de escopo para TI distribuída](../fundamentals/scope-tags.md).
5. Clique em **Avançar: Atribuições**.<br>
   A página **Atribuições** permite que você possa atribuir o perfil a usuários e dispositivos. É importante observar que você pode atribuir um perfil a um dispositivo seja ou não esse dispositivo gerenciado pelo Intune.
6. Clique em **Avançar: Examinar + criar** para examinar os valores que você inseriu para o perfil.
7. Quando terminar, clique em **Criar** para criar o perfil de provisionamento de aplicativos iOS no Intune. 

## <a name="next-steps"></a>Próximas etapas

Atribua o perfil aos dispositivos iOS necessários. Para saber mais, use as etapas em [Como atribuir perfis de dispositivo](../device-profile-assign.md).
