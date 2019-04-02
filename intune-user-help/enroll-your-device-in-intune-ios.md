---
title: Configurar o acesso do dispositivo iOS aos recursos de sua empresa | Microsoft Docs
description: Descreve como fazer seu dispositivo iOS ser gerenciado pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: ee0f438d929abd6b5b90acbaeeddc41e3ce11f98
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490635"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Configurar o acesso do dispositivo iOS aos recursos de sua empresa  

Registre seu dispositivo iOS no aplicativo Portal da Empresa do Intune para obter acesso seguro ao email, aos arquivos e aos aplicativos da organização.

Antes de acessar os dados proprietários em um dispositivo corporativo ou pessoal, é necessário gerenciar seu dispositivo. Depois que seu dispositivo se tornar gerenciado, sua organização atribuirá políticas e aplicativos ao dispositivo por meio de um provedor de MDM (gerenciamento de dispositivo móvel), como o Intune. 

Para manter o acesso a informações corporativas ou de estudante em seu dispositivo, é necessário configurá-lo para corresponder às configurações preferenciais da sua organização. Este artigo descreve como usar o Portal da empresa para registrar você dispositivo e manter os requisitos de configuração de sua organização. 

> [!NOTE]
> Se você tentou acessar o email da empresa no aplicativo de email e recebeu um prompt para gerenciar seu dispositivo, você está no lugar certo. Siga as instruções abaixo para obter acesso ao seu email e a outros recursos da empresa em seu dispositivo iOS.  

## <a name="what-to-expect-from-the-company-portal-app"></a>O que esperar do aplicativo Portal da Empresa  

### <a name="security"></a>Segurança   
Durante a instalação inicial, o aplicativo requer que você se autentique na organização. Em seguida, ele informa sobre as configurações do dispositivo que você deve atualizar. Por exemplo, as organizações geralmente definem os requisitos de mínimo e máximo de caracteres de senha que você deverá atender.     

### <a name="protection"></a>Proteção  
Depois que o dispositivo for registrado, o aplicativo Portal da Empresa continuará a verificar se o dispositivo está protegido. Se você instalar um aplicativo de uma fonte não confiável, por exemplo, o aplicativo o alertará e, às vezes, revogará o acesso aos dados da empresa. Uma política assim é comum em organizações e geralmente exige que você desinstale o aplicativo não confiável antes de recuperar o acesso.  

### <a name="setting-notifications"></a>Definindo notificações  
Se, após o registro, sua organização impuser um novo requisito de segurança, como a autenticação multifator, o aplicativo Portal da Empresa emitirá uma notificação. Você terá a oportunidade de ajustar as configurações para que possa continuar a trabalhar usando seu dispositivo.  

Para saber mais sobre o registro, confira [O que acontece quando eu instalo o aplicativo Portal da Empresa e registro meu dispositivo?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Registrar seu dispositivo iOS   

> [!IMPORTANT]
> As capturas de tela desta seção mostram a experiência para dispositivos que executam o iOS versão 12.1 e versões anteriores. Quando aplicável, incluímos instruções específicas para o iOS versão 12.2 e posteriores. Se você perceber que sua experiência é diferente de capturas de tela mostradas, consulte as 12.2 instruções.      

Vá para a App store para baixar e instalar o [aplicativo de Portal da empresa Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) ao seu dispositivo. Durante o registro, você também precisará uma conexão Wi-Fi e acesso para o Safari. 

Se você pausar por mais de alguns minutos, durante o registro, o aplicativo pode fechar ou finalizar a instalação. Se isso acontecer, abra o aplicativo de Portal da empresa e tente novamente.  

1. Abra o Portal da Empresa e entre com sua conta corporativa ou de estudante. 

    ![Captura de tela de exemplo de aplicativo de Portal da empresa, de entrada.](./media/ios-01-cp-enroll-1903.PNG)  

2. Quando solicitado para receber notificações do Portal da empresa, toque em **permitir.** Portal da empresa usa notificações para alertá-lo se, por exemplo, as configurações do dispositivo precisarão ser atualizadas. 

    ![Captura de tela de exemplo da home page do Portal da empresa, o prompt de "Notificações".](./media/ios-04-cp-enroll-1903.PNG)  

3. Sobre o **configurar o acesso** tela, selecione **começar.**  

     ![Captura de tela de exemplo do Portal da empresa, a tela "Set up acesso".](./media/ios-05-cp-enroll-1903.PNG)  

4. Leia a lista de informações de dispositivo, sua organização pode ver ou não. [Detalhes adicionais sobre este tópico](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) podem ser encontrados por meio de **Saiba mais** link. Quando tiver terminado, toque **continuar**.  

    ![Captura de tela de exemplo de aplicativo de Portal da empresa, "O que vemos minha organização", com o botão continuar.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. O **próximas etapas?** tela resume as etapas restantes. Essas etapas podem ser diferentes dependendo da sua versão do iOS. 
    * **iOS 12.2 e posterior**: sua experiência em vez disso, pode exigir que você:  

        a. **Permitir o download do perfil de gerenciamento**: seu navegador abrirá o site de Portal da empresa e solicitará que você permita o download. O download será salvo no seu aplicativo de configurações.  

        b. **Abra o aplicativo de configurações e instalar o perfil**: você precisará ir para o aplicativo de configurações e instalar o perfil de gerenciamento.  

        c. **Retorne ao aplicativo Portal da empresa**: você precisará retornar para o aplicativo de Portal da empresa para concluir a instalação.  

    Quando estiver pronto para baixar o perfil de gerenciamento, toque **continuar**.  

6. Safari abre o site de Portal da empresa. Quando solicitado a baixar o perfil de configuração, toque **permitir**.  
    * **iOS 12.2 e posterior**: Aguarde até que o perfil para concluir o download no Safari e toque em **feito**. Em seguida, abra o aplicativo **Configurações** em seu dispositivo.  

    > [!IMPORTANT]
    > Você deve ir para o **configurações** aplicativo e instalar este perfil dentro de 8 minutos de baixá-lo. Se você não fizer isso, o perfil será removido e você terá que reiniciar o registro. 

7. No **as configurações** aplicativo, toque em **instalar o perfil baixado** > **instalar**. Se **instalar o perfil baixado** não aparecem como uma opção, vá para **gerais** > **perfis**. Se você não vir o perfil, você talvez precise baixá-lo novamente.  

    ![Captura de tela de exemplo do aplicativo configurações, a configuração de instalar o perfil baixado, com um selo vermelho que indica um perfil baixado recentemente.](./media/ios-10-cp-enroll-1903.PNG)  
    
8. Se solicitado, insira sua senha do dispositivo. Em seguida, toque **instalar**.      

9. A tela seguinte é um aviso de sistema padrão para o gerenciamento de dispositivo. Para saber mais sobre o que sua organização pode e não pode ver no seu dispositivo, consulte o relevantes [artigo do Intune docs](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). Para continuar a instalação, toque em **instalar**. Se for solicitado que você confie no gerenciamento remoto, toque em **confiança**.  

    ![Captura de tela de exemplo de aplicativo de configurações, a tela de aviso de sistema padrão para o certificado raiz e o gerenciamento de dispositivo móvel.](./media/ios-15-cp-enroll-1903.PNG)  

10. Após a instalação for concluída, toque em **feito**. Para verificar que o perfil foi instalado, vá para o **perfis e gerenciamento de dispositivo** configurações. Você deve ver o perfil listado em **gerenciamento de dispositivo móvel**.   

    ![Captura de tela de exemplo de configurações de aplicativo, perfis e gerenciamento de dispositivo configurações, mostrando o perfil de gerenciamento.](./media/ios-00-cp-enroll-1903.PNG)  


11. Retorne ao aplicativo **Portal da Empresa**. Portal da empresa começam a sincronizar e configurar seu dispositivo. Portal da empresa pode solicitar que você atualize as configurações de dispositivos adicionais. Se ele, toque em **continuar**.

    ![Captura de tela de exemplo do Portal da empresa, tela de "Set up acesso", com um triângulo amarelo ao lado do requisito de configuração.](./media/ios-12-cp-enroll-1903.PNG)  

12. Você saberá que a instalação é concluída quando todos os itens na lista de mostram um círculo verde. Toque em **Concluído**.  
    
    ![Captura de tela de exemplo do Portal da empresa, "você está pronto!" tela, mostrando todos os círculos verdes.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Se sua organização monitora os limites de voz e dados, ou fornece um dispositivo da empresa, você pode ter mais algumas etapas para concluir. Se você for solicitado a instalar o **Datalert** aplicativo, consulte [registrar seu dispositivo no gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se sua organização faz parte do programa de registro de dispositivo da Apple, descubra [como registrar seu dispositivo da empresa](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Próximas etapas  
Encontre aplicativos que lhe ajudarão no trabalho ou escola. Saiba mais [como aplicativos são disponibilizados](use-managed-apps-on-your-device-ios.md) para você por meio do Portal da empresa.  

Ainda precisa de ajuda? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
