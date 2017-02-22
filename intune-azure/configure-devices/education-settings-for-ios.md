---
title: "Definir configurações de educação Intune para iOS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as definições que você pode usar para controlar as configurações de educação em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: e52fdf8c30a680d62071cd31e308dd0180e8b9dc


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Como definir configurações de educação do Intune para dispositivos iOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Criar um perfil de dispositivo que contém configurações de educação iOS

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, selecione **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de atualização de edição.
5. Na lista suspensa **Plataforma**, escolha **iOS**.
6. Na lista suspensa **Tipos de perfil**, escolha **Educação**.
7. Na folha **Educação**, selecione o seguinte:
    - **Arquivo de certificado de raiz do professor**
    - **Professor PKCS12 / perfil PFX**
    - **Arquivo de certificado de raiz do aluno**
    - **Aluno PKCS12 / perfil PFX**
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.



<!--HONumber=Feb17_HO1-->


