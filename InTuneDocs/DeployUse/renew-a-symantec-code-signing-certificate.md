---
# required metadata

title: Renovar um certificado de assinatura de código corporativo do Symantec para usar com o Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Renovar um certificado de assinatura de código corporativo do Symantec para dispositivos Windows

O certificado da Symantec usado para gerenciar determinados dispositivos móveis do Windows e Windows Phone deve ser renovado periodicamente. Para dispositivos Windows Phone 8.0, um aplicativo do Portal da Empresa assinado e o certificado de assinar código são necessários para o registro do dispositivo. Dispositivos Windows Phone posteriores podem usar o aplicativo de portal da empresa baixado do repositório. Um certificado de assinar código também é necessário para implantar aplicativos de linha de negócios.

## Como renovar o certificado corporativo de autenticação de código Symantec

1.  Procure um email de renovação enviado da Symantec aproximadamente 14 dias antes da expiração do certificado. O email contém instruções da Symantec sobre como renovar o certificado corporativo.

    Para obter informações adicionais sobre certificados Symantec, visite [www.symantec.com](http://www.symantec.com) ou ligue para 1-877-438-8776 ou 1-650-426-3400.

2.  Vá até o site (exemplo: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) e faça logon com a ID do Editor da Symantec e o email endereçado associado ao certificado. Lembre-se de usar o mesmo computador para iniciar a renovação que você usará para baixar o certificado.

3.  Após a renovação ser aprovada e paga, baixe o certificado.

## Como instalar o certificado atualizado para o Windows Phone 8.0

1.  Baixe e assine o Portal da Empresa do Windows Phone mais recente localizado aqui: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Abra o Console de Administração do Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) e vá para **Admin**, **Gerenciamento de Dispositivos Móveis** &gt; **Windows Phone** e clique em **Carregar o Aplicativo Assinado**.

3.  Carregue o Portal da Empresa assinado. Você precisará de SSP.xap recentemente assinado e o novo arquivo .PFX que recebeu da Symantec ou o token de registro de aplicativo que foi criado com esse novo arquivo .PFX.

4.  Quando o carregamento for concluído, remova a versão antiga do Portal da empresa no espaço de trabalho **Software** no Console de gerenciamento do Intune.

5.  Assine todos os aplicativos de linha de negócios da empresa novamente usando o mesmo certificado e carregue e substitua os aplicativos existentes.

Fornecer um arquivo .xap do SSP assinado é a única maneira de fornecer o certificado de assinatura de código atualizado. Para dar suporte a aplicativos de linha de negócios assinados, você deve assinar e carregar um aplicativo do Portal da Empresa, mesmo que os usuários instalem o aplicativo do Portal da Empresa na loja.

## Como instalar o certificado atualizado para Windows Phone 8.1 e os dispositivos posteriores

1.  Baixe e assine o Portal da Empresa do Windows Phone no Centro de Download mais recente localizado aqui: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Abra o [Console de Administração do Intune](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) e vá para **Admin** &gt; **Gerenciamento de Dispositivos Móveis** &gt; **Windows Phone** e clique em **Carregar o Aplicativo Assinado**.

3.  Carregue o Portal da Empresa assinado. Você precisará de SSP.xap recentemente assinado e o novo arquivo .PFX que recebeu da Symantec ou o token de registro de aplicativo que foi criado com esse novo arquivo .PFX.

4.  Quando o upload for concluído, remova a versão antiga do Portal da Empresa no espaço de trabalho **Software**  .

5.  Assine todos aplicativos de linha de negócios de empresa novos e atualizados usando o novo certificado. Os aplicativos existentes não precisam ser assinados e reimplantados.


### Consulte também
[Configurar o gerenciamento do Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Configurar o gerenciamento do Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


