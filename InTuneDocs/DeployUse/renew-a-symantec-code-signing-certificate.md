---
title: "Renovar um certificado de autenticação de código corporativo da Symantec para usar com o Intune | Microsoft Intune"
description: "Diretrizes para renovar os certificados da Symantec usados para gerenciar determinados dispositivos móveis Windows e Windows Phone"
keywords: 
author: staciebarker
manager: stabar
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8fd2a90025ae9310a214978cd2d42ea7ad035fa3
ms.openlocfilehash: 2479f8065a2bb46e63b0e3971700a8d2c0982755


---

# <a name="renew-a-symantec-enterprise-codesigning-certificate-for-windows-devices"></a>Renovar um certificado de assinatura de código corporativo do Symantec para dispositivos Windows

O certificado da Symantec usado para implantar aplicativos móveis do Windows e do Windows Phone deve ser renovado periodicamente.

## <a name="how-to-renew-the-symantec-enterprise-codesigning-certificate"></a>Como renovar o certificado corporativo de autenticação de código Symantec

1.  Procure um email de renovação enviado da Symantec aproximadamente 14 dias antes da expiração do certificado. O email contém instruções da Symantec sobre como renovar o certificado corporativo.

    Para obter informações adicionais sobre certificados Symantec, visite [www.symantec.com](http://www.symantec.com) ou ligue para 1-877-438-8776 ou 1-650-426-3400.

2.  Vá até o site (exemplo: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) e faça logon com a ID do Editor da Symantec e o email endereçado associado ao certificado. Lembre-se de usar o mesmo computador para iniciar a renovação que você usará para baixar o certificado.

3.  Após a renovação ser aprovada e paga, baixe o certificado.

## <a name="how-to-install-the-updated-certificate-for-windows-phone-80"></a>Como instalar o certificado atualizado para o Windows Phone 8.0

1.  Baixe e assine o Portal da Empresa do Windows Phone mais recente localizado aqui: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Abra o Console de Administração do Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) e vá para **Admin** **Gerenciamento de Dispositivo Móvel** &gt; **Windows Phone** e clique em **Carregar o Aplicativo Assinado**.

3.  Carregue o Portal da Empresa assinado. Você precisará de SSP.xap recentemente assinado e o novo arquivo .PFX que recebeu da Symantec ou o token de registro de aplicativo que foi criado com esse novo arquivo .PFX.

4.  Quando o carregamento for concluído, remova a versão antiga do Portal da empresa no espaço de trabalho **Software** no Console de gerenciamento do Intune.

5.  Assine todos os aplicativos de linha de negócios da empresa novamente usando o mesmo certificado e carregue e substitua os aplicativos existentes.

Fornecer um arquivo .xap do SSP assinado é a única maneira de fornecer o certificado de assinatura de código atualizado. Para dar suporte a aplicativos de linha de negócios assinados, você deve assinar e carregar um aplicativo do Portal da Empresa, mesmo que os usuários instalem o aplicativo do Portal da Empresa na loja.

## <a name="how-to-install-the-updated-certificate-for-windows-phone-81-and-later-devices"></a>Como instalar o certificado atualizado para Windows Phone 8.1 e os dispositivos posteriores

1.  Baixe e assine o Portal da Empresa do Windows Phone no Centro de Download mais recente localizado aqui: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Abra o [Console de Administração do Intune](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) e vá para **Admin** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows Phone** e clique em **Carregar o Aplicativo Assinado**.

3.  Carregue o Portal da Empresa assinado. Você precisará de SSP.xap recentemente assinado e o novo arquivo .PFX que recebeu da Symantec ou o token de registro de aplicativo que foi criado com esse novo arquivo .PFX.

4.  Quando o upload for concluído, remova a versão antiga do Portal da Empresa no espaço de trabalho **Software**  .

5.  Assine todos aplicativos de linha de negócios de empresa novos e atualizados usando o novo certificado. Os aplicativos existentes não precisam ser assinados e reimplantados.


### <a name="see-also"></a>Consulte também
[Configurar o gerenciamento do Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Configurar o gerenciamento do Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


