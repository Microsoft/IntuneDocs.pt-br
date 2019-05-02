---
title: Configurar o acesso do dispositivo iOS aos recursos de sua empresa | Microsoft Docs
description: Descreve como fazer seu dispositivo iOS ser gerenciado pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d0c7ac239a67a51ba7165771206883f3c46f5f55
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292417"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Configurar o acesso do dispositivo iOS aos recursos de sua empresa  

Registre seu dispositivo iOS no aplicativo Portal da Empresa do Intune para obter acesso seguro ao email, aos arquivos e aos aplicativos da organização.

Depois que o dispositivo é registrado, ele se torna *gerenciados*. Sua organização pode atribuir políticas e aplicativos para o dispositivo por meio de um provedor MDM (gerenciamento) do dispositivo móvel, como o Intune.  

Para manter o acesso a informações corporativas ou de estudante em seu dispositivo, é necessário configurá-lo para corresponder às configurações preferenciais da sua organização. Este artigo descreve como usar o Portal da empresa para registrar você dispositivo e manter os requisitos de configuração de sua organização. 

> [!NOTE]
> Se você tentou acessar o email da empresa no aplicativo de email e recebeu um prompt para gerenciar seu dispositivo, você está no lugar certo. Siga as instruções abaixo para obter acesso ao seu email e a outros recursos da empresa em seu dispositivo iOS.  

## <a name="what-to-expect-from-the-company-portal-app"></a>O que esperar do aplicativo Portal da Empresa  

### <a name="security"></a>Segurança   
Durante a instalação inicial, o aplicativo requer que você se autentique na organização. Em seguida, ele informa sobre as configurações do dispositivo que você deve atualizar. Por exemplo, as organizações geralmente definem os requisitos de mínimo e máximo de caracteres de senha que você deverá atender.     

### <a name="protection"></a>Proteção  
Depois que o dispositivo for registrado, o aplicativo Portal da Empresa continuará a verificar se o dispositivo está protegido. Se você instalar um aplicativo de uma fonte não confiável, por exemplo, o aplicativo o alertará e, às vezes, revogará o acesso aos dados da empresa. Esse tipo de política é comum em organizações e geralmente exige que você desinstale o aplicativo não confiável antes de recuperar o acesso.  

### <a name="setting-notifications"></a>Definindo notificações  
Se, após o registro, sua organização impuser um novo requisito de segurança, como a autenticação multifator, o aplicativo Portal da Empresa emitirá uma notificação. Você terá a oportunidade de ajustar as configurações para que possa continuar a trabalhar usando seu dispositivo.  

Para saber mais sobre o registro, confira [O que acontece quando eu instalo o aplicativo Portal da Empresa e registro meu dispositivo?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Registrar seu dispositivo iOS  

Vá para a App store para baixar e instalar o [aplicativo de Portal da empresa Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) em seu dispositivo. Você também precisará manter uma conexão Wi-Fi e ter acesso ao Safari durante o registro. 

Pausa por mais de alguns minutos durante o registro pode fazer com que o aplicativo fechar ou finalizar a instalação. Se isso acontecer, abra o aplicativo de Portal da empresa e tente novamente.  

1. Abra o Portal da Empresa e entre com sua conta corporativa ou de estudante. 

    ![Captura de tela de exemplo de aplicativo de Portal da empresa, de entrada.](./media/ios-01-cp-enroll-1903.PNG)  

2. Quando solicitado para receber notificações do Portal da empresa, toque em **permitir.** Portal da empresa usa notificações para alertá-lo se, por exemplo, as configurações do dispositivo precisarão ser atualizadas. 

    ![Captura de tela de exemplo da home page do Portal da empresa, o prompt de "Notificações".](./media/ios-04-cp-enroll-1903.PNG)  

3. Sobre o **configurar o acesso** tela, selecione **começar.**  

     ![Captura de tela de exemplo do Portal da empresa, a tela "Set up acesso".](./media/ios-05-cp-enroll-1903.PNG)  

4. Leia a lista de informações de dispositivo, sua organização pode ver ou não. Em seguida, toque **continuar**.  

5. Leia as instruções sobre o **próximas etapas?** tela. Quando você estiver pronto para baixar e instalar o perfil de gerenciamento, toque em **continuar**.  

 > [!IMPORTANT]
> Essas etapas e telas de Avançar variam de acordo com sua versão do iOS. Siga as etapas para a sua versão do iOS. 

6. Safari abre o site de Portal da empresa em seu dispositivo. Quando solicitado a baixar o perfil de configuração, toque **permitir**. Se você estiver em um dispositivo que executa:  
    * iOS 12.2 e posterior: quando o download for concluído, toque em **feito.** Continue para a etapa 7 neste artigo.
    * iOS 12.1 e anterior: você será redirecionado automaticamente para o aplicativo de configurações. Vá para a etapa 8 neste artigo.  
 
    Se você acidentalmente tocar **ignorar**, atualize a página. Você será solicitado a abrir o aplicativo de Portal da empresa. No aplicativo, você pode tocar **baixar novamente**.

  > [!NOTE]
  > Você deve instalar o perfil de gerenciamento, conforme descrito nas próximas etapas dentro de 8 minutos de baixá-lo. Se você não fizer isso, o perfil será removido e você terá que reiniciar o registro.  

7. iOS 12.2 e versões posteriores: quando solicitado a abrir o Portal da empresa, toque **abrir**. O **instalar o perfil de gerenciamento** tela lista as etapas para instalar o perfil.

    ![Captura de tela de exemplo do Portal da empresa, tela de instalação do perfil de gerenciamento.](./media/ios-1904-settings-icon.PNG)  

8. Vá para o aplicativo de configurações e toque **perfil baixado**.  

    Se **perfil baixado** não aparecem como uma opção, vá para **gerais** > **perfis**. Se você não vir o perfil, você talvez precise baixá-lo novamente.  

    ![Captura de tela de exemplo do aplicativo configurações, o perfil baixado a configuração.](./media/ios-1904-settings-badge.PNG)  

9. Toque em **Instalar**.  
    
10. Altere a senha do seu dispositivo Em seguida, toque **instalar**.    

    ![Captura de tela de exemplo do aplicativo configurações, tela instalar perfil, com um cursor no * * instalar * * botão.](./media/ios-1904-password-install.PNG)  


11. A tela seguinte é um aviso de sistema padrão para o gerenciamento de dispositivo. Para continuar a instalação, toque em **instalar**. Se for solicitado para o gerenciamento remoto de confiança, toque em **confiança**.  

    ![Captura de tela de exemplo de aplicativo de configurações, a tela de aviso de sistema padrão para o certificado raiz e o gerenciamento de dispositivo móvel.](./media/ios-15-cp-enroll-1903.PNG)  

12. Após a instalação for concluída, toque em **feito**. Para verificar que o perfil foi instalado, vá para o **perfis e gerenciamento de dispositivo** configurações. Você deve ver o perfil listado em **gerenciamento de dispositivo móvel**.   

    ![Captura de tela de exemplo de configurações de aplicativo, perfis e gerenciamento de dispositivo configurações, mostrando o perfil de gerenciamento.](./media/ios-00-cp-enroll-1903.PNG)  

13. Retorne ao aplicativo Portal da Empresa. Portal da empresa começam a sincronizar e configurar seu dispositivo. Portal da empresa pode solicitar que você atualize as configurações de dispositivos adicionais. Se ele, toque em **continuar**.  

    ![Captura de tela de exemplo do Portal da empresa, tela de "Set up acesso", com um triângulo amarelo ao lado do requisito de configuração.](./media/ios-12-cp-enroll-1903.PNG)  

14. Você saberá que a instalação é concluída quando todos os itens na lista de mostram um círculo verde. Toque em **Concluído**.   
    
    ![Captura de tela de exemplo do Portal da empresa, "você está pronto!" tela, mostrando todos os círculos verdes.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Se sua organização monitora os limites de voz e dados, ou fornece um dispositivo da empresa, você pode ter mais algumas etapas para concluir. Se você for solicitado a instalar o **Datalert** aplicativo, consulte [registrar seu dispositivo no gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se sua organização faz parte do programa de registro de dispositivo da Apple, descubra [como registrar seu dispositivo da empresa](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Próximas etapas  
Encontre aplicativos que lhe ajudarão no trabalho ou escola. Saiba mais [como aplicativos são disponibilizados](use-managed-apps-on-your-device-ios.md) para você por meio do Portal da empresa.  

Ainda precisa de ajuda? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
