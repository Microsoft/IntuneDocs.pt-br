---
title: MTD do Check Point SandBlast com o Microsoft Intune
titlesuffix: ''
description: Como configurar o MTD (Defesa contra Ameaças Móveis) do Check Point SandBlast com o Intune para controlar o acesso de dispositivos móveis aos seus recursos corporativos.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b864d78fd7bfd7fb4e177b568b3587bc1e28b209
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
ms.locfileid: "29777198"
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

    ![Imagem mostrando a configuração do Intune do MTD da Check Point](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Você deve adicionar todas as plataformas de dispositivo para prosseguir para a próxima etapa.

6.  Escolha **Aceitar** para autorizar o aplicativo Check Point SandBlast Mobile a se comunicar com o Intune e o Azure Active Directory.

7.  Depois que de habilitar todas as plataformas de dispositivo, você precisa inserir o grupo de segurança do Azure AD.

8.  Escolha **Verificar** e, uma vez que o grupo de segurança do Azure AD é verificado com êxito, escolha **Salvar**.

## <a name="next-steps"></a>Próximas etapas

- [Configurar a integração dos aplicativos Check Point SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)