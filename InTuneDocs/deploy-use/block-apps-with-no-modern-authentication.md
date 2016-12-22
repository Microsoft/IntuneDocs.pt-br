---
title: "Bloquear aplicativos sem autenticação moderna | Microsoft Intune"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 5c95cd8510faa437a33ac25d6602a2bcc57c05d5


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Bloquear aplicativos que não usam autenticação moderna (ADAL)
O acesso condicional para aplicativos com políticas de MAM (AC de MAM) se baseia nos aplicativos que usam [autenticação moderna](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), que é uma implementação do OAuth2. Os aplicativos do Office mais recentes, tanto os móveis como os de área de trabalho, usam autenticação moderna; no entanto, há aplicativos de terceiros e aplicativos do Office mais antigos que usam outros métodos de autenticação, como autenticação básica e autenticação baseada em formulários.

Para bloquear o acesso a esses aplicativos, recomendamos o seguinte:

* Configure as regras de declarações do ADFS para bloquear protocolos de autenticação não moderna. Instruções detalhadas são fornecidas no cenário 3 – [bloquear todo o acesso ao O365, exceto aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).

>[!IMPORTANT]
>O AC de MAM não deve ser usado com a autenticação baseada em certificado do Azure Active Directory (Azure AD). Só é possível ter um deles configurado de cada vez.



### <a name="see-also"></a>Consulte também
[Permitir que somente aplicativos em que há suporte para o Intune acessem os serviços do O365](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Dec16_HO2-->


