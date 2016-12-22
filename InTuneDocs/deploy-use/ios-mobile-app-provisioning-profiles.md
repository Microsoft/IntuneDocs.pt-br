---
title: Perfis de provisionamento do aplicativo | Microsoft Intune
description: "O Intune fornece as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 409433dbe5ca777b33b21a2655e15cde8003b4a2
ms.openlocfilehash: d67b26b23e65d4a144c1efda1494de1df94cc33c


---

# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Usar políticas de perfil de provisionamento móvel do iOS para impedir que os aplicativos expirem


Os aplicativos de linha de negócios de iOS da Apple implantados em iPhones e iPads são criados com um perfil de provisionamento incluído e código assinado com um certificado. Quando o aplicativo é executado, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento. As validações a seguir ocorrem:

- **Integridade do arquivo de instalação** – o iOS compara os detalhes de aplicativos com a chave pública do certificado de assinatura de empresa. Se eles forem diferentes, o conteúdo dos aplicativos poderá ter sido alterado e ele não poderá ser executado.
- **Imposição de funcionalidades** – o iOS tenta aplicar as funcionalidades do aplicativo do perfil de provisionamento corporativo (não perfis de provisionamento de desenvolvedor individuais) contidas no arquivo de instalação (.ipa) do aplicativo.


A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Enquanto o certificado ainda for válido, o Intune fornecerá as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.
Depois que o certificado expirar, você deverá assinar o aplicativo novamente com um novo certificado e inserir um novo perfil de provisionamento com a chave do novo certificado.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>Como descobrir quando um aplicativo de linha de negócios expirará

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** > **Aplicativos**.
2. Na lista de aplicativos, examine a coluna **Data de expiração** para ver a data de expiração do aplicativo. Você também pode definir a lista suspensa **Filtros** como **Expirado/prestes a expirar** para ver apenas os aplicativos para os quais é necessário tomar providências.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>Como criar uma política de perfil de provisionamento móvel iOS


1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Visão Geral** > **Adicionar Política**.
2. Na caixa de diálogo **Criar Nova Política**, selecione **iOS** > **Política de perfil de provisionamento móvel** e selecione **Criar Política**.
3. Na página **Geral**, defina os seguintes valores:
    - **Nome** – forneça um nome para essa política de perfil de provisionamento móvel.
    - **Descrição** – de maneira opcional, forneça uma descrição para a política.
    - **Arquivo do perfil de configuração** – Clique em **Importar** e escolha um arquivo de Perfil de Configuração Móvel da Apple (com a extensão **.mobileprovision**) que você baixou do site do Desenvolvedor da Apple.
4. Quando terminar, selecione **Salvar Política**.
5. Agora, implante a política aos dispositivos iOS necessários. Para obter mais informações, consulte [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).



<!--HONumber=Dec16_HO2-->


