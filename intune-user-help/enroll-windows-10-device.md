---
title: Registrar o dispositivo Windows 10 no Portal de empresa do Intune | Microsoft Docs
description: Etapas para registrar dispositivos Windows 10 no Portal de empresa do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/11/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4eb5dbb150559de7ad30a598fb78a4fa78033c42
ms.sourcegitcommit: fdc6261f4ed695986e06d18353c10660a4735362
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58068837"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Registrar dispositivos Windows 10 com o Portal da empresa do Intune

Use o Portal da empresa Intune para registrar seu dispositivo Windows 10 sob o gerenciamento da sua organização. Este artigo descreve como registrar dispositivos com Windows 10 versão 1607 e posterior e Windows 10 versão 1511 e anteriores. Antes de começar, verifique se você [verificar a versão em seu dispositivo](windows-enrollment-company-portal.md#find-windows-10-version-number) para que você pode seguir as etapas corretas.  

Há suporte para o Windows 10 em vários tipos de dispositivos, incluindo a área de trabalho, telefone e tablet. As etapas de registro são os mesmos em qualquer dispositivo que você está usando. No entanto, sua tela pode parecer um pouco diferentes das imagens mostradas neste artigo.  

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]  

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Registrar o dispositivo posterior e Windows 10 versão 1607 
Estas etapas descrevem como registrar um dispositivo que executa o Windows 10, versão 1607 e posterior.  

1. Vá até **Iniciar**. Se você estiver usando um dispositivo Windows 10 Mobile, vá para o **todos os aplicativos** lista.

2. Abra o aplicativo **Configurações**. Se o aplicativo não está prontamente disponível na lista de aplicativos, vá para a barra de pesquisa e o tipo "configurações".

3. Selecione **Contas** > **Acessar trabalho ou escola** > **Conectar**.  


    ![Selecione Acessar conta corporativa ou de estudante](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Insira seu endereço de email corporativo ou de estudante e selecione **Avançar**.  


   ![Insira sua conta corporativa ou de estudante](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. Entre no Intune com sua conta corporativa ou de estudante.  


    ![Adicionar uma conta corporativa ou de estudante](./media/w10-enroll-rs1-enter-your-credentials.png)  

    Você verá uma mensagem que indica que sua empresa ou escola está registrando o dispositivo.

6. Se sua organização exige que você configure um PIN do Windows Hello, você será solicitado a inserir um código de verificação. Insira o código e prossiga com as etapas na tela para criar um PIN.  

7. Na tela **Tudo pronto!**, selecione **Concluir**. Agora, seu dispositivo está registrado.  

8. Para verificar sua conexão, vá para **as configurações** > **contas** > **acessar trabalho ou escola**.  Sua conta deve agora estar listada.  


    ![Valide se a conexão foi configurada corretamente](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

Ainda não consegue acessar seu email corporativo ou de estudante, bem como arquivos ou outros dados? Saiba como [solucionar problemas de conta](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Registrar o Windows 10 versão 1511 e dispositivo anterior  
Estas etapas descrevem como registrar um dispositivo que executa o Windows 10, versão 1511 e anteriores.  

1. Vá até **Iniciar**. Se você estiver usando um dispositivo Windows 10 Mobile, vá para o **todos os aplicativos** lista.

2. Abra o aplicativo **Configurações**. Se o aplicativo não está prontamente disponível na lista de aplicativos, vá para a barra de pesquisa e o tipo "configurações".

3. Selecione **contas** > **sua conta**.  


    ![Selecionar sua conta](./media/W10-enroll-2-accounts-your-account.png)  

5. Selecione **Adicionar uma conta corporativa ou de estudante**.  


    ![Selecione adicionar uma conta corporativa ou de estudante](./media/w10-enroll-3-add-work-school-acct.png)  

6. Entre com as suas credenciais corporativas ou de estudante.  


    ![Entrar](./media/W10-enroll-4-sign-in.png)  

Ainda não consegue acessar seu email corporativo ou de estudante, bem como arquivos ou outros dados? Saiba como [solucionar problemas de conta](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).   

## <a name="next-steps"></a>Próximas etapas  

Para obter ajuda, entre em contato com o suporte de sua empresa. Você pode encontrar sua organização informações de TI sobre o [site do Portal da empresa](https://go.microsoft.com/fwlink/?linkid=2010980). Entre no site com sua conta corporativa ou de estudante.  

 

