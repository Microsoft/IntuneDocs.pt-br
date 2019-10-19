---
title: Configurar o acesso do dispositivo iOS aos recursos de sua empresa | Microsoft Docs
description: Descreve como fazer seu dispositivo iOS ser gerenciado pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/12/2019
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: e468042ab81d563c9fa4b272661508a340d61aa9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506239"
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

    ![Captura de tela de exemplo do aplicativo Portal da Empresa, Entrada.](./media/ios-01-cp-enroll-1904.PNG)  

2. Quando solicitado a receber notificações do Portal da Empresa, toque em **Permitir.** O Portal da Empresa usa notificações para alertá-lo se, por exemplo, suas configurações do dispositivo precisarem ser atualizadas. 

    ![Captura de tela de exemplo da home page do Portal da Empresa, prompt de "Notificações".](./media/ios-02-cp-enroll-1904.PNG)  

3. Na tela **Configurar acesso**, selecione **Começar.**  

     ![Captura de tela de exemplo do Portal da Empresa, a tela "Configurar acesso".](./media/ios-03-cp-enroll-1904.PNG)  

4. Leia a lista de informações do dispositivo que sua organização pode e não pode ver. Toque em **Continuar**.  

5. Leia as instruções na tela **O que vem a seguir?** . Quando você estiver pronto para baixar e instalar o perfil de gerenciamento, toque em **Continuar**.  

 > [!IMPORTANT]
> Estas próximas etapas e telas variam conforme sua versão do iOS. Siga as etapas para a sua versão do iOS. 

6. O Safari abre o site de Portal da Empresa em seu dispositivo. Quando solicitado a baixar o perfil de configuração, toque em **Permitir**. Se você estiver em um dispositivo que executa:  
    * iOS 12.2 e posteriores: quando o download for concluído, toque em **Concluído.** Prossiga para a etapa 7 neste artigo.
    * iOS 12.1 e anteriores: você será redirecionado automaticamente para o aplicativo de Configurações. Vá para a etapa 8 neste artigo.  
 
    Se você acidentalmente tocar em **Ignorar**, atualize a página. Você será solicitado a abrir o aplicativo Portal da Empresa. No aplicativo, você pode tocar em **Baixar novamente**.

  > [!NOTE]
  > Você deve instalar o perfil de gerenciamento conforme descrito nas próximas etapas dentro de 8 minutos de baixá-lo. Se você não fizer isso, o perfil será removido e você precisará reiniciar o registro.  

7. iOS 12.2 e versões posteriores: quando solicitado a abrir o Portal da Empresa, toque em **Abrir**. A tela **Instalando o Perfil de Gerenciamento** lista as etapas para instalar o perfil.

    ![Captura de tela de exemplo do Portal da Empresa, tela de Instalando Perfil de Gerenciamento.](./media/ios-07-cp-enroll-1904.PNG)  

8. Vá para o aplicativo Configurações e toque em **Perfil Baixado**.  

    Se **Perfil Baixado** não aparecer como uma opção, acesse **Geral** > **Perfis**. Se você não vir o perfil, talvez precise baixá-lo novamente.  

    ![Captura de tela de exemplo do aplicativo Configurações, configuração de Perfil Baixado.](./media/ios-1904-settings-badge.PNG)  

9. Toque em **Instalar**.  
    
10. Insira a senha do seu dispositivo. Em seguida, toque em **Instalar**.    

    ![Captura de tela de exemplo do aplicativo Configurações, tela Instalando Perfil, com um cursor no botão **Instalar**.](./media/ios-10-cp-enroll-1904.PNG)  


11. A tela seguinte é um aviso padrão do sistema para o gerenciamento de dispositivo. Para continuar a instalação, toque em **Instalar**. Se for solicitado a confiar no gerenciamento remoto, toque em **Confiar**.  

    ![Captura de tela de exemplo do aplicativo Configurações, tela de aviso padrão do sistema para o certificado raiz e o gerenciamento de dispositivo móvel.](./media/ios-11-cp-enroll-1904.PNG)  

12. Quando a instalação for concluída, toque em **Concluído**. Para verificar se o perfil foi instalado, acesse as configurações **Perfis e Gerenciamento de Dispositivo**. Você deve ver o perfil listado em **Gerenciamento de Dispositivo Móvel**.   

    ![Captura de tela de exemplo do aplicativo Configurações, configurações de Perfis e Gerenciamento de Dispositivo, mostrando o perfil de gerenciamento.](./media/ios-12-cp-enroll-1904.PNG)  

13. Retorne ao aplicativo Portal da Empresa. O Portal da Empresa começará a sincronizar e configurar seu dispositivo. O Portal da Empresa pode solicitar que você atualize configurações de dispositivos adicionais. Se solicitar, toque em **Continuar**.  

    ![Captura de tela de exemplo do Portal da Empresa, tela de "Configurar acesso", com um triângulo amarelo ao lado do requisito de configuração.](./media/ios-13-cp-enroll-1904.PNG)  

14. Você saberá que a instalação está concluída quando todos os itens na lista mostrarem um círculo verde. Toque em **Concluído**.   
    
    ![Captura de tela de exemplo do Portal da Empresa, tela "Tudo pronto!" mostrando todos os círculos verdes.](./media/ios-14-cp-enroll-1904.PNG)  

> [!Note]
> Se a sua organização monitora os limites de voz e dados ou fornece a você um dispositivo de propriedade da empresa, talvez você precise concluir mais algumas etapas. Se você for solicitado a instalar o aplicativo **Datalert**, veja [registrar seu dispositivo no gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se a sua organização faz parte do Programa de Registro de Dispositivos da Apple, descubra [como registrar seu dispositivo de propriedade da empresa](enroll-your-device-dep-ios.md).  

## <a name="it-administrator-support"></a>Suporte do administrador de TI  
Se você for um administrador de TI e encontrar problemas durante o registro de dispositivos, consulte [Solucionando problemas de registro de dispositivo iOS no Microsoft Intune](https://support.microsoft.com/en-us/help/4039809). Este artigo lista erros comuns, suas causas e etapas para resolvê-los.  

## <a name="next-steps"></a>Próximas etapas  
Encontre aplicativos que o ajudarão no trabalho ou na escola. Saiba [como aplicativos são disponibilizados](use-managed-apps-on-your-device-ios.md) para você por meio do Portal da Empresa.  

Ainda precisa de ajuda? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
