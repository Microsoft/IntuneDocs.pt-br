---
title: Registrar o dispositivo Windows 10 no Portal da Empresa do Intune | Microsoft Docs
description: Etapas para registrar dispositivos Windows 10 no Portal da Empresa do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: df83f2763d5fe7ae26ad30fecca56128aaa8437c
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75856228"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Registrar dispositivos Windows 10 com o Portal da Empresa do Intune

Use o Portal da Empresa do Intune para registrar seu dispositivo Windows 10 sob o gerenciamento da sua organização. Este artigo descreve como registrar dispositivos com Windows 10 versão 1607 e posteriores e Windows 10 versão 1511 e anteriores. Antes de começar, certifique-se de [verificar a versão em seu dispositivo](windows-enrollment-company-portal.md#find-windows-10-version-number) para que você possa seguir as etapas corretas.  

Há suporte para o Windows 10 em vários tipos de dispositivos, incluindo desktop, telefone e tablet. As etapas de registro são as mesmas em qualquer dispositivo sendo usado. No entanto, sua tela pode parecer um pouco diferente das imagens mostradas neste artigo.  
</br>
> [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Registrar o dispositivo Windows 10 versão 1607 e posteriores 
Estas etapas descrevem como registrar um dispositivo que executa o Windows 10 versão 1607 e posteriores.  

1. Vá até **Iniciar**. Se você estiver usando um dispositivo Windows 10 Mobile, prossiga para a lista **Todos os Aplicativos**.

2. Abra o aplicativo **Configurações**. Se o aplicativo não estiver prontamente disponível na lista de aplicativos, acesse a barra de pesquisa e digite "configurações".

3. Selecione **Contas** > **Acessar trabalho ou escola** > **Conectar**.  


    ![Selecione Acessar conta corporativa ou de estudante](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Para acessar a página de entrada do Intune da sua organização, insira seu endereço de email corporativo ou de estudante. Em seguida, selecione **Avançar**.  


   ![Insira sua conta corporativa ou de estudante](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. Entre no Intune com sua conta corporativa ou de estudante.  


    ![Adicionar uma conta corporativa ou de estudante](./media/w10-enroll-rs1-enter-your-credentials.png)  

    Você verá uma mensagem que indica que sua empresa ou escola está registrando o dispositivo.

6. Se a sua organização exigir a configuração de um PIN do Windows Hello, será solicitado que você insira um código de verificação. Insira o código e prossiga com as etapas na tela para criar um PIN.  

7. Na tela **Tudo pronto!** , selecione **Concluir**. Agora, seu dispositivo está registrado.  

8. Para verificar sua conexão, volte para **Configurações** > **Contas** > **Acessar o trabalho ou a escola**.  Sua conta deve estar listada agora.  


    ![Valide se a conexão foi configurada corretamente](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

Ainda não consegue acessar seu email corporativo ou de estudante, bem como arquivos ou outros dados? Saiba como [solucionar problemas da conta](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Registrar o dispositivo Windows 10 versão 1511 e anteriores  
Estas etapas descrevem como registrar um dispositivo que executa o Windows 10, versão 1511 e anteriores.  

1. Vá até **Iniciar**. Se você estiver usando um dispositivo Windows 10 Mobile, prossiga para a lista **Todos os Aplicativos**.

2. Abra o aplicativo **Configurações**. Se o aplicativo não estiver prontamente disponível na lista de aplicativos, acesse a barra de pesquisa e digite "configurações".

3. Selecione **Contas** > **Sua conta**.  


    ![Selecionar sua conta](./media/W10-enroll-2-accounts-your-account.png)  

5. Selecione **Adicionar uma conta corporativa ou de estudante**.  


    ![Selecione adicionar uma conta corporativa ou de estudante](./media/w10-enroll-3-add-work-school-acct.png)  

6. Entre com as suas credenciais corporativas ou de estudante.  


    ![Entrar](./media/W10-enroll-4-sign-in.png)  

Ainda não consegue acessar seu email corporativo ou de estudante, bem como arquivos ou outros dados? Saiba como [solucionar problemas relacionados à conta](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) durante o registro.  

## <a name="it-administrator-support"></a>Suporte do administrador de TI   

Se você for um administrador de TI e encontrar problemas durante o registro de dispositivos, confira [Solucionando problemas de registro de dispositivo do Windows no Microsoft Intune](https://support.microsoft.com/help/4469913). Este artigo lista erros comuns, suas causas e etapas para resolvê-los. 

## <a name="next-steps"></a>Próximas etapas  
Se você precisar de ajuda com o Portal da Empresa ou com o registro, entre em contato com a equipe de suporte de TI da sua empresa. Você encontrará as informações de contato dela no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980). Entre no site com sua conta corporativa ou de estudante.  

 

