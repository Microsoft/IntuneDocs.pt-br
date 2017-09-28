---
title: "Configurar a integração do Check Point SandBlast com o Intune"
titlesuffix: Azure portal
description: "Configurar a integração do Check Point SandBlast com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a4560ab65ecd1d30492ae2a1a2f136511195c674
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a>Integrar O Check Point SandBlast Mobile com o Intune

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE] 
> As etapas a seguir precisam ser tomadas no [console do Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/).

Antes de iniciar o processo de integração do Check Point SandBlast Mobile com o Intune, verifique se que você tem o seguinte:

-   Assinatura do Microsoft Intune

-   Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:

    -   Entrada e leitura de perfil do usuário

    -   Acessar diretório como o usuário conectado

    -   Ler dados do diretório

    -   Enviar informações do dispositivo para o Intune

-   Credenciais de administrador para acessar o console de verificar o console de MTD do Check Point SandBlast Mobile.

### <a name="check-point-sandblast-app-authorization"></a>Autorização de aplicativo do Check Point SandBlast

O processo de autorização do aplicativo do Check Point SandBlast consiste no seguinte:

-   Permitir que o serviço Check Point SandBlast Mobile comunique informações relacionadas ao estado de integridade do dispositivo de volta para o Intune.

-   O CheckPoint SandBlast Mobile sincroniza-se com a associação de Grupo de Registro do Azure AD para popular o banco de dados do respectivo dispositivo.

-   Permitir que o console de administração do Check Point SandBlast use o SSO (logon único) do Azure AD.

-   Permitir que o aplicativo Check Point SandBlast Mobile entre usando o SSO do Azure AD.

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a>Para configurar a integração do Check Point SandBlast Mobile

1.  Vá para o [console do Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/) e entre com suas credenciais.

2.  Clique na guia **Configurações**.

3.  Escolha **Gerenciamento de dispositivo**, seguido de **Configurações**.

4.  Escolha **Microsoft Intune** na lista suspensa **Serviço MDM**.

5.  Depois de configurar o Microsoft Intune como o serviço MDM, a janela **Configuração do Microsoft Intune** aparece; escolha **Adicionar à minha organização** para cada plataforma de dispositivo (iOS, Android e Windows) para autorizar o Check Point SandBlast Mobile a se comunicar com o Intune e o Azure AD.

    ![Configuração do Intune de MTD da Check Point](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Você deve adicionar todas as plataformas de dispositivo para prosseguir para a próxima etapa.

6.  Escolha **Aceitar** para autorizar o aplicativo Check Point SandBlast Mobile a se comunicar com o Intune e o Azure Active Directory.

7.  Depois que de habilitar todas as plataformas de dispositivo, você precisa inserir o grupo de segurança do Azure AD.

8.  Escolha **Verificar** e, uma vez que o grupo de segurança do Azure AD é verificado com êxito, escolha **Salvar**.

## <a name="next-steps"></a>Próximas etapas

- [Configurar a integração dos aplicativos Check Point SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)