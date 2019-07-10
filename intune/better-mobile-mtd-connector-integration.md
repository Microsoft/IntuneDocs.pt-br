---
title: Configurar a integração do Better Mobile ao Intune
titleSuffix: Intune on Azure
description: Integração do conector do Better Mobile com o Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a7072d7d3d24578e0f82ea21eb653906dfa30b4c
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67546967"
---
# <a name="integrate-better-mobile-with-intune"></a>Integrar o Better Mobile com o Intune

Conclua as etapas a seguir para integrar a solução de Defesa contra Ameaças do Better Mobile ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas a seguir devem ser concluídas no [console de admin do Better Mobile](https://aad.bmobi.net).

Antes de iniciar o processo de integração do Better Mobile ao Intune, verifique se você tem o seguinte:

- Assinatura do Microsoft Intune

- Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:

    - Entrada e leitura de perfil do usuário

    - Acessar diretório como o usuário conectado

    - Ler dados do diretório

    - Enviar informações do dispositivo para o Intune

- Credenciais de administrador para acessar o console de admin do Better Mobile.

### <a name="better-mobile-app-authorization"></a>Autorização de aplicativo Better Mobile

O processo de autorização de aplicativo do Better Mobile é o seguinte:

- Permitir que o serviço do Better Mobile comunique informações relacionadas ao estado de integridade do dispositivo novamente para o Intune.

- O Better Mobile é sincronizado com a associação do Azure AD Enrollment Group para preencher o banco de dados de seu dispositivo.

- Permitir que o console de administrador do Better Mobile use o SSO (Logon Único) do Azure AD.

- Permitir que o aplicativo Better Mobile se conecte usando o SSO do Azure AD.

## <a name="to-set-up-better-mobile-integration"></a>Para configurar a integração do Better Mobile

1. Acesse o [console de admin do Better Mobile](https://aad.bmobi.net) e entre com suas credenciais.
2. Escolha **Integração** > **EMM/MDM** > **ADICIONAR CONTA**.

     ![Imagem do console de administração do Better Mobile](media/better_mobile_console.png)
 
3. Escolha **Intune**.
4. Ao lado de **NOME DA CONTA**, digite um descritor. 
5. Na janela **Logon Microsoft**, insira suas credenciais do Intune.
6. Na janela **Permissões solicitadas**, escolha **Aceitar**.
7. Procure os grupos de Segurança do Azure AD dos quais você deseja que o Better Mobile sincronize dispositivos e selecione-os na lista. Em seguida, selecione **Continuar**.
8. Selecione **Concluído**.
9. A página **Adicionar conta** é exibida novamente. Feche a página. 

## <a name="next-steps"></a>Próximas etapas

- [Configurar aplicativos Cliente Melhores](mtd-apps-ios-app-configuration-policy-add-assign.md)
