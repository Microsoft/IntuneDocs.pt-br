---
title: Registrar o dispositivo iOS ou iPadOS com Portal da Empresa do Intune e intercedam
description: Saiba como registrar um dispositivo iOS ou iPadOS e configurar a autenticação de credenciais derivadas com o intercedam.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilver
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 02293b29f8634161582af2348b1cb30039ca3c52
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415705"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-intercede"></a>Configurar o dispositivo iOS ou iPadOS com Portal da Empresa e intercedam

Registre seu dispositivo no aplicativo Portal da Empresa do Intune para ter acesso móvel seguro a emails, arquivos e aplicativos da organização.  Depois que o dispositivo é registrado, ele se torna *gerenciado*. Sua organização pode atribuir políticas e aplicativos ao dispositivo por meio de um provedor de MDM (gerenciamento de dispositivo móvel), como o Intune.  

Durante o registro, você também instalará uma credencial derivada em seu dispositivo. Sua organização pode exigir que você use a credencial derivada como um método de autenticação ao acessar recursos ou para assinar e criptografar emails. 

Provavelmente, você precisará configurar uma credencial derivada se usar um cartão inteligente para:

* Entrar em aplicativos escolares ou de trabalho, Wi-Fi e redes virtuais privadas (VPN)
* Assinar e criptografar emails escolares ou de trabalho usando certificados S/MIME  

Neste artigo, você irá:  

* Registre um dispositivo iOS ou iPadOS móvel com Portal da Empresa do Intune.  
* Obtenha uma credencial derivada do provedor de credenciais derivado de sua organização, [intercedam](https://www.intercede.com/).   


## <a name="what-are-derived-credentials"></a>O que são credenciais derivadas?  
Uma credencial derivada é um certificado derivado de suas credenciais de cartão inteligente e instalado em seu dispositivo. Ele concede acesso remoto a recursos de trabalho, impedindo que usuários não autorizados acessem informações confidenciais.  

As credenciais derivadas são usadas para: 
* Autentique alunos e funcionários que se conectam a aplicativos escolares ou de trabalho, Wi-Fi e VPN
* Assinar e criptografar emails escolares ou de trabalho com certificados S/MIME  

As credenciais derivadas são uma implementação das diretrizes do NIST (National Institute of Standards and Technology) para as credenciais de PIV (Verificação de Identidade Pessoal Derivada) como parte da SP (Publicação Especial) 800-157.  

## <a name="prerequisites"></a>Pré-requisitos

 Para concluir o registro, você deve ter:

* Cartão inteligente ou de estudante fornecido pelo trabalho
* Acesso a um computador ou quiosque de autoatendimento em que você pode entrar com seu cartão inteligente
* Seu dispositivo móvel
* O aplicativo Portal da Empresa do Intune para iOS e iPadOS instalado em seu dispositivo


## <a name="enroll-device"></a>Registrar o dispositivo  
1. Abra o aplicativo Portal da Empresa para iOS/iPadOS em seu dispositivo móvel e entre com sua conta corporativa.  
2. Anote o código que aparece na tela.  

    ![Exemplo de imagem do aplicativo Portal da Empresa com código e mensagem na tela.](./media/copy-code-intercede.png)  
1. Alterne para o dispositivo habilitado para cartão inteligente e vá para https://microsoft.com/devicelogin. 

1. Insira o código que você anotou anteriormente.
 
2. Insira seu cartão inteligente para entrar.   

3. Retorne ao aplicativo Portal da Empresa em seu dispositivo móvel e siga as instruções na tela para registrar seu dispositivo.  
4. Após a conclusão do registro, Portal da Empresa o notificará para configurar seu cartão inteligente. Toque na notificação. Se você não receber uma notificação, verifique seu email.   

    ![Captura de tela de exemplo da notificação por push Portal da Empresa no dispositivo página inicial.](./media/action-required-in-app-intercede.png)  

5. Na tela de **configuração de acesso a cartão inteligente móvel** :  
    a. Toque no link para as instruções de configuração da sua organização. Se sua organização não fornecer instruções adicionais, você será enviado para este artigo.  
    b. Toque em **Iniciar**.  

    ![A captura de tela de exemplo do Portal da Empresa configurar o acesso do cartão inteligente móvel.](./media/smart-card-info-intercede.png)  

6. Alterne para o dispositivo habilitado para cartão inteligente ou o quiosque de autoatendimento e abra o aplicativo MyID. Entre com suas credenciais de trabalho.  
7. Selecione a opção para solicitar sua ID. 
8. Quando perguntado qual perfil você deseja usar, selecione a opção para ativar com uma credencial móvel. Um código QR é exibido.  
9. Retorne ao seu dispositivo móvel. Na tela Portal da Empresa > **obter código QR** , toque em **continuar**.  

    ![A captura de tela de exemplo da Portal da Empresa obter o código QR.](./media/get-qr-code-intercede.png) 
 
10. Toque em **usar câmera** > **OK**.  

    ![Captura de tela de exemplo de um prompt de Portal da Empresa, solicitando permissão para permitir o acesso à câmera.](./media/allow-cp-camera-access-intercede.png)  

11. Digitalize a imagem do código QR que está no dispositivo habilitado para cartão inteligente. 
12. Aguarde Portal da Empresa concluir a configuração do dispositivo.  

## <a name="next-steps"></a>Próximas etapas  
Após a conclusão do registro, você terá acesso aos recursos de trabalho, como email, Wi-Fi e quaisquer aplicativos disponibilizados pela sua organização. Para obter mais informações sobre como obter, Pesquisar, instalar e desinstalar aplicativos no Portal da Empresa consulte:

* [Gerenciar aplicativos no site do Portal da Empresa](manage-apps-cpweb.md)  
* [Usar aplicativos gerenciados no seu dispositivo](use-managed-apps-on-your-device-ios.md)  

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).