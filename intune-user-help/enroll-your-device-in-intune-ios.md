---
title: Configurar o acesso do dispositivo iOS aos recursos de sua empresa | Microsoft Docs
description: Descreve como fazer seu dispositivo iOS ser gerenciado pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: bd9fd38fdc244bc48333496c2f266ff039e55585
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75855556"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Configurar o acesso do dispositivo iOS aos recursos de sua empresa  

Registre seu dispositivo iOS no aplicativo Portal da Empresa do Intune para obter acesso seguro ao email, aos arquivos e aos aplicativos da organização.

Depois que o dispositivo é registrado, ele se torna *gerenciado*. Sua organização pode atribuir políticas e aplicativos ao dispositivo por meio de um provedor de MDM (gerenciamento de dispositivo móvel), como o Intune.  

> [!NOTE]
> Não vendemos os dados coletados por nossos serviços para terceiros por nenhum motivo.  

Para manter o acesso a informações corporativas ou de estudante em seu dispositivo, você precisará configurá-lo para corresponder às configurações preferenciais da sua organização. Este artigo descreve como usar o Portal da Empresa para registrar seu dispositivo e manter os requisitos de configuração de sua organização.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

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

Vá para a App Store para baixar e instalar o [aplicativo Portal da Empresa do Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) em seu dispositivo. Você também precisará manter uma conexão Wi-Fi e ter acesso ao Safari durante o registro. 

Pausar por mais de alguns minutos durante o registro pode fazer o aplicativo fechar ou finalizar a instalação. Se isso acontecer, abra o aplicativo de Portal da Empresa e tente novamente.  

1. Abra o Portal da Empresa e entre com sua conta corporativa ou de estudante.  

2. Quando solicitado a receber notificações do Portal da Empresa, toque em **Permitir.** O Portal da Empresa usa notificações para alertá-lo se, por exemplo, suas configurações do dispositivo precisarem ser atualizadas.  

3. Na tela **Configurar acesso**, selecione **Começar.**   

    ![Captura de tela de exemplo do Portal da Empresa, a tela "Configurar acesso".](./media/ios-enrollment-checklist-1909.PNG)  

4. A tela **selecionar dispositivo e tipo de registro** é exibida e solicita o tipo de dispositivo.  
    * Toque **(organização) possui este dispositivo** se você recebeu seu dispositivo da sua organização. Em seguida, pule para [proteger o dispositivo inteiro](###secure-entire-device) neste artigo para concluir a instalação.  
    * Toque em **eu proprietário deste dispositivo** se você estiver usando um dispositivo pessoal que trouxe de casa. Em seguida, continue para a próxima etapa.  

    Se você não vir essa tela, pule para [proteger o dispositivo inteiro](enroll-your-device-in-intune-ios.md#secure-entire-device) para concluir a instalação.  
    
    ![Exemplo de captura de tela de Portal da Empresa "selecionar dispositivo e tipo de registro", opções de tipo de dispositivo.](./media/ios-device-type-1909.PNG)  


5. Escolha como proteger os dados em seu dispositivo depois que ele for registrado.  
    * Toque em **proteger todo o dispositivo** para proteger todos os aplicativos e dados no dispositivo. Em seguida, vá para [proteger o dispositivo inteiro](enroll-your-device-in-intune-ios.md#secure-entire-device) para concluir a instalação.
    * Toque em **proteger aplicativos e dados relacionados ao trabalho somente** para proteger somente os aplicativos e dados que você acessa com sua conta corporativa. Em seguida, vá para [proteger dados e aplicativos relacionados ao trabalho](enroll-your-device-in-intune-ios.md#secure-work-related-apps-and-data).  

    ![Exemplo de captura de tela de Portal da Empresa "selecionar dispositivo e tipo de registro", opções de tipo de registro.](./media/ios-enrollment-type-1909.PNG)  


### <a name="secure-entire-device"></a>Proteger o dispositivo inteiro  

1. Na tela **Gerenciamento e privacidade do dispositivo** , leia a lista de informações do dispositivo que sua organização pode e não consegue ver. Toque em **Continuar**.  


 > [!IMPORTANT]
> Estas próximas etapas e telas variam conforme sua versão do iOS. Siga as etapas para a sua versão do iOS. 

2. O Safari abre o site de Portal da Empresa em seu dispositivo. Quando solicitado a baixar o perfil de configuração, toque em **Permitir**. Se você estiver em um dispositivo que executa:  
    * iOS 12.2 e posterior: quando o download for concluído, toque em **Fechar**. Em seguida, prossiga para a etapa 3.  
    * iOS 12,1 e anterior: quando o download for concluído, você será redirecionado automaticamente para o aplicativo de configurações. Pule para a etapa 4.  
 
    Se você acidentalmente tocar em **Ignorar**, atualize a página. Você será solicitado a abrir o aplicativo Portal da Empresa. Quando estiver lá, toque em **baixar novamente**.

  > [!NOTE]
  > Você deve instalar o perfil de gerenciamento conforme descrito nas próximas etapas dentro de 8 minutos de baixá-lo. Se você não fizer isso, o perfil será removido e você precisará reiniciar o registro.  

3. Quando for solicitado a abrir Portal da Empresa, toque em **abrir**. Leia as informações na tela **como instalar o perfil de gerenciamento** .  

4. Vá para o aplicativo Configurações e toque **em registrar em < nome da organização >** ou **perfil baixado**.  

    ![Captura de tela de exemplo do aplicativo de configurações, opção registrar na organização.](./media/enroll-in-organization-ios-1909.PNG)  

   Se nenhuma das opções aparecer, vá para **geral** > **perfis & gerenciamento de dispositivo**> perfil de **Gerenciamento**. Se você não vir um perfil de gerenciamento, talvez precise baixá-lo novamente.  

5. Toque em **Instalar**.  
    
6. Insira a senha do seu dispositivo. Em seguida, toque em **Instalar**.    

7. A tela seguinte é um aviso padrão do sistema sobre o gerenciamento de dispositivo. Para continuar a instalação, toque em **Instalar**. Se for solicitado a confiar no gerenciamento remoto, toque em **Confiar**.  

8. Quando a instalação for concluída, toque em **Concluído**. Para verificar se o perfil foi instalado, acesse as configurações **Perfis e Gerenciamento de Dispositivo**. Você deve ver o perfil listado em **Gerenciamento de Dispositivo Móvel**.   

    ![Captura de tela de exemplo do aplicativo Configurações, configurações de Perfis e Gerenciamento de Dispositivo, mostrando o perfil de gerenciamento.](./media/ios-12-cp-enroll-1904.PNG)  

9. Retorne ao aplicativo Portal da Empresa. O Portal da Empresa começará a sincronizar e configurar seu dispositivo. O Portal da Empresa pode solicitar que você atualize configurações de dispositivos adicionais. Se solicitar, toque em **Continuar**.  

10. Você saberá que a instalação está concluída quando todos os itens na lista mostrarem uma marca de seleção verde. Toque em **Concluído**.   

> [!Note]
> Se a sua organização monitora os limites de voz e dados ou fornece a você um dispositivo de propriedade da empresa, talvez você precise concluir mais algumas etapas. Se você for solicitado a instalar o aplicativo **Datalert**, veja [registrar seu dispositivo no gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se a sua organização faz parte do Programa de Registro de Dispositivos da Apple, descubra [como registrar seu dispositivo de propriedade da empresa](enroll-your-device-dep-ios.md).  

### <a name="secure-work-related-apps-and-data"></a>Proteger aplicativos e dados relacionados ao trabalho  
1. A tela **baixar Microsoft Authenticator** é exibida (se você já tiver o autenticador, não verá essa tela, portanto, pule para a etapa 2).  
    1. Toque em **baixar na loja de aplicativos**.
    2. Quando a loja de aplicativos abrir, instale o aplicativo. 
    3. Volte para Portal da Empresa e toque em **continuar**.    
    
   Depois de instalar o Microsoft Authenticator, você não precisará fazer mais nada com o aplicativo. Ele só precisa estar presente em seu dispositivo. 

   ![Captura de tela de exemplo de Portal da Empresa, "baixar Microsoft Authenticator".](./media/download-ms-authenticator-1909.PNG)  

2. Na tela **Gerenciamento e privacidade do dispositivo** , leia a lista de informações do dispositivo que sua organização pode e não consegue ver. Toque em **Continuar**.  


 > [!IMPORTANT]
> Estas próximas etapas e telas variam conforme sua versão do iOS. Siga as etapas para a sua versão do iOS. 

3. O Safari abre o site de Portal da Empresa em seu dispositivo. Quando solicitado a baixar o perfil de configuração, toque em **Permitir**. Se você estiver em um dispositivo que executa:  
    * iOS 12.2 e posterior: quando o download for concluído, toque em **Fechar**. Em seguida, prossiga para a etapa 4.  
    * iOS 12,1 e anterior: quando o download for concluído, você será redirecionado automaticamente para o aplicativo de configurações. Vá para a etapa 5.  
 
    Se você acidentalmente tocar em **Ignorar**, atualize a página. Você será solicitado a abrir o aplicativo Portal da Empresa. No aplicativo, você pode tocar em **Baixar novamente**.

  > [!NOTE]
  > Você deve instalar o perfil de gerenciamento conforme descrito nas próximas etapas dentro de 8 minutos de baixá-lo. Se você não fizer isso, o perfil será removido e você precisará reiniciar o registro.  

4. Quando for solicitado a abrir Portal da Empresa, toque em **abrir**. Leia as informações na tela **como instalar o perfil de gerenciamento** . 

5. Vá para o aplicativo Configurações e toque **em registrar em < nome da organização >** ou **perfil baixado**.  

    ![Captura de tela de exemplo do aplicativo de configurações, opção registrar na organização.](./media/enroll-in-organization-ios-1909.PNG)  

   Se nenhuma das opções aparecer, vá para **geral** > **perfis & gerenciamento de dispositivo**> perfil de **Gerenciamento**. Se você não vir um perfil de gerenciamento, talvez precise baixá-lo novamente.   


6. Na tela de **registro do usuário** , toque em **registrar meu iPhone**.  

    ![Captura de tela de exemplo do aplicativo de configurações, de registro de usuário, realçando o botão registrar.](./media/user-enrollment-information-1909.PNG)  

7. Insira a senha do dispositivo. Em seguida, toque em **Instalar**.  

8. Na tela de **entrada** , insira a senha para sua ID da Apple gerenciada. Na maioria dos casos, essas credenciais serão as mesmas que você usa para entrar em sua conta corporativa ou de estudante, a menos que sua organização tenha fornecido um conjunto diferente de credenciais. 
9. Toque **em entrar**.  
10. Uma mensagem de êxito aparecerá brevemente na tela depois que o perfil for instalado. Para verificar se o perfil está instalado, acesse os **perfis & gerenciamento de dispositivo** configurações. Você deverá ver o perfil listado em  **Gerenciamento de Dispositivo Móvel.**  

    ![Captura de tela de exemplo do aplicativo Configurações, configurações de Perfis e Gerenciamento de Dispositivo, mostrando o perfil de gerenciamento.](./media/ios-12-cp-enroll-1904.PNG)  

11. Retorne ao aplicativo Portal da Empresa. O Portal da Empresa começará a sincronizar e configurar seu dispositivo. O Portal da Empresa pode solicitar que você atualize configurações de dispositivos adicionais. Se solicitar, toque em **Continuar**.    

12. Você saberá que a instalação está concluída quando todos os itens na lista mostrarem uma marca de seleção verde. Toque em **concluído**.  

## <a name="it-administrator-support"></a>Suporte do administrador de TI  
Se você for um administrador de TI e encontrar problemas durante o registro de dispositivos, consulte [Solucionando problemas de registro de dispositivo iOS no Microsoft Intune](https://support.microsoft.com/en-us/help/4039809). Este artigo lista erros comuns, suas causas e etapas para resolvê-los.  

## <a name="next-steps"></a>Próximas etapas  
Encontre aplicativos que o ajudarão no trabalho ou na escola. Saiba [como aplicativos são disponibilizados](use-managed-apps-on-your-device-ios.md) para você por meio do Portal da Empresa.  

Ainda precisa de ajuda? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
