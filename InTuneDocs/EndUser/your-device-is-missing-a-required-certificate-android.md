---
# required metadata

title: Falta ao dispositivo um certificado necessário | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Falta ao dispositivo um certificado necessário
Se o dispositivo Android não estiver registrado no Intune e ele não tiver um certificado que normalmente vem instalado no telefone, você não conseguirá entrar no aplicativo Portal da Empresa Android. Quando você tentar entrar, verá a seguinte mensagem:

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

Para resolver esse problema e obter o certificado necessário:

1.  Em um navegador, navegue até a [página do certificado Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Localize e baixe o certificado Baltimore CyberTrust Root (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Da parte superior, arraste para baixo para abrir as notificações e, em seguida, toque em **BaltimoreCyberTrustRoot.crt** na lista de notificações.

4.  Na tela **Nome do Certificado**, aceite o nome do certificado padrão.

5. Certifique-se de que o **Uso da Credencial** é definido como **Usado para aplicativos e VPN**, e, em seguida, toque em **OK**.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Feche o navegador da Web e o aplicativo Portal da Empresa.

7. Abra o aplicativo Portal da Empresa. Agora, você poderá entrar no aplicativo Portal da Empresa. Se você precisar de Ajuda, entre em contato com o administrador de TI.

Ainda precisa de ajuda? Entre em contato com seu administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).

<!--HONumber=Jun16_HO2-->


