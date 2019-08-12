---
title: O dispositivo não tem um certificado | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: NOINDEX, NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: a91a6c934ba3b1a32ea2ef10da0256019fc25392
ms.sourcegitcommit: 549352bdea93cc2809e3e0010bfcc10bd44dc728
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68862129"
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Seu dispositivo Android não tem um certificado que normalmente vem instalado no telefone

Se o dispositivo não estiver registrado no Intune e não tiver um certificado que normalmente vem instalado no telefone, você não conseguirá entrar no aplicativo Portal da Empresa. Quando você tentar entrar, verá a seguinte mensagem:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

É possível corrigir esse problema obtendo o certificado necessário na [página de certificados do Digicert](https://www.digicert.com/digicert-root-certificates.htm).

1. Encontre e baixe o certificado __Baltimore CyberTrust Root__ . Também é possível baixá-lo diretamente [aqui](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

2. Arraste para baixo da parte superior da tela para exibir a lista das notificações recentes e toque em **BaltimoreCyberTrustRoot.crt**.

3. Seu dispositivo solicitará que você **Nomeie o Certificado**. Não altere o nome padrão do certificado exibido.

4. Certifique-se de que o **Uso da Credencial** é definido como **Usado para aplicativos e VPN**, e, em seguida, toque em **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. Feche o navegador e o aplicativo Portal da Empresa.

6. Abra o aplicativo Portal da Empresa. Agora, você poderá entrar no aplicativo Portal da Empresa. Se você ainda não conseguir usar o aplicativo Portal da Empresa, contate o suporte de sua empresa usando as informações fornecidas no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obter mais instruções.

>[!NOTE]
> Se a instalação desse certificado não resolver o problema e você receber outra mensagem “Certificado ausente”, será necessário realizar etapas adicionais para [instalar o certificado ausente](your-device-is-missing-an-IT-required-certificate-android.md).

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
