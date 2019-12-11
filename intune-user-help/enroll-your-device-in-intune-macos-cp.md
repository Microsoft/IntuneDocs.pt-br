---
title: Registrar seu Mac com o Portal da Empresa do Intune | Microsoft Docs
description: Saiba como registrar seu Mac no Intune com o aplicativo Portal da Empresa.
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: kakyker
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba285fc9de58b3fb739a16722e0e05e36e840e87
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74098163"
---
# <a name="enroll-your-macos-device-using-the-company-portal-app"></a>Registrar seu dispositivo macOS usando o aplicativo Portal da Empresa  

Registre seu dispositivo macOS no aplicativo Portal da Empresa do Intune para obter acesso seguro aos arquivos, aos aplicativos e ao email corporativo ou de estudante.

Normalmente, as organizações exigem que você registre seu dispositivo antes de poder acessar dados proprietários. Depois que o dispositivo é registrado, ele se torna *gerenciado*. Sua organização pode atribuir políticas e aplicativos ao dispositivo por meio de um provedor de MDM (gerenciamento de dispositivo móvel), como o Intune. Para obter acesso contínuo às informações corporativas ou de estudante no seu dispositivo, você precisa configurá-lo de acordo com as configurações da política de sua organização.  

Este artigo descreve como usar o aplicativo Portal da Empresa do Intune para macOS para registrar, configurar e manter seu dispositivo a fim de atender aos requisitos organizacionais.  


## <a name="what-to-expect-from-the-company-portal-app"></a>O que esperar do aplicativo Portal da Empresa

Durante a configuração inicial, o aplicativo Portal da Empresa exige que você entre e se autentique com sua organização. Portal da Empresa, em seguida, o informará sobre as configurações de dispositivo que você precisa configurar para atender aos requisitos da sua organização. Por exemplo, as organizações geralmente definem os requisitos de mínimo e máximo de caracteres de senha que você deverá atender.    

Depois de registrar seu dispositivo, Portal da Empresa sempre verificará se o dispositivo está protegido de acordo com os requisitos da sua organização. Por exemplo, se você instalar um aplicativo de uma fonte não confiável, Portal da Empresa irá alertá-lo e poderá restringir o acesso aos recursos da sua organização. As políticas de proteção de aplicativo como essa são comuns. Para restabelecer o acesso, você provavelmente precisará desinstalar o aplicativo não confiável. 

Se, após o registro, sua organização impuser um novo requisito de segurança, como a autenticação multifator, o Portal da Empresa emitirá uma notificação. Você terá a oportunidade de ajustar as configurações para que possa continuar a trabalhar usando seu dispositivo.  

Para saber mais sobre o registro, confira [O que acontece quando eu instalo o aplicativo Portal da Empresa e registro meu dispositivo?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-macos-device-managed"></a>Faça com que seu dispositivo macOS seja gerenciado  
Use as etapas a seguir para registrar seu dispositivo macOS com sua organização. Seu dispositivo deve estar executando o macOS 10,12 ou posterior.   

> [!NOTE]
> Durante esse processo, você pode ser solicitado a permitir que Portal da Empresa use informações confidenciais armazenadas em seu conjunto de chaves. Esses prompts fazem parte da segurança da Apple. Quando receber o prompt, digite sua senha de conjunto de chaves de logon e selecione **sempre permitir**. Se você pressionar **Enter** ou **retornar** no teclado, o prompt selecionará **permitir**, o que pode resultar em prompts adicionais.  

### <a name="install-company-portal-app"></a>Instalar o aplicativo do Portal da Empresa  
1. Vá para [registrar meu Mac](https://go.microsoft.com/fwlink/?linkid=853070).  
2. O arquivo Portal da Empresa Installer. pkg será baixado. Abra o instalador e continue as etapas. 
3. Concorde com o contrato de licença do software. 
4. Insira a senha do dispositivo ou a impressão digital registrada para instalar o software.  
5. Abra Portal da Empresa. 

> [!IMPORTANT]
> O Microsoft AutoUpdate pode abrir para atualizar seu software da Microsoft. Depois que todas as atualizações forem instaladas, abra o aplicativo Portal da Empresa. Para obter a melhor experiência de configuração, instale as versões mais recentes do Microsoft AutoUpdate e Portal da Empresa.  


### <a name="enroll-your-mac"></a>Registrar seu Mac  


1. Entre no Portal da Empresa com sua conta corporativa ou de estudante.  
2. Quando o aplicativo for aberto, selecione **Iniciar**.  
3. Examine [o que sua organização pode ou não ver](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) em seu dispositivo registrado. Em seguida, selecione **Continuar**.  
4. Na tela **instalar perfil de gerenciamento** , selecione **baixar perfil**.   

    ![Exemplo de captura de tela de Portal da Empresa, instalar perfil de gerenciamento, realçando o botão "baixar perfil".](./media/install-mgmt-profile-mac-1911.PNG)   
5. As preferências do sistema do seu dispositivo serão abertas. Selecione **instalar** e, em seguida, selecione **instalar** novamente. Se for solicitado, insira a senha do dispositivo.  

    ![Captura de tela de exemplo de preferências do sistema macOS, prompt de instalação, realçando o botão "instalar".](./media/system-preference-install-1911.PNG)  
6. Depois que o perfil for instalado, ele será exibido na lista de perfis em **perfil de gerenciamento.**  

   ![Captura de tela de exemplo de preferências de sistema do macOS, telas de perfis, realçando o perfil de gerenciamento instalado.](./media/system-preference-verify-1911.PNG)   
7. Retornar para Portal da Empresa.   
8. Sua organização pode exigir que você atualize as configurações do dispositivo. Quando você terminar de atualizar as configurações, selecione **verificar configurações**.  

    ![Exemplo de captura de tela de Portal da Empresa, atualizar configurações do dispositivo, realçando o botão "verificar configurações".](./media/update-settings-mac-1911.PNG)  
9. Quando a instalação estiver concluída, selecione **concluído**.  


 ## <a name="troubleshooting-and-feedback"></a>Solução de problemas e comentários   

Se você encontrar problemas durante o registro, acesse **ajuda** > **Enviar relatório de diagnóstico** para relatar o problema aos desenvolvedores de aplicativos da Microsoft. Essas informações são usadas para ajudar a melhorar o aplicativo. Eles também usarão essas informações para ajudar a resolver o problema se o seu pessoal de suporte de ti chegar a ele para obter ajuda.  

Depois de relatar o problema à Microsoft, você pode enviar os detalhes de sua experiência para sua pessoa de suporte de ti. Selecione **detalhes do email**. Digite o que você experimentou no corpo do email. Para localizar o endereço de email da pessoa de suporte, acesse o aplicativo Portal da Empresa > **contato**. Ou verifique o [site Portal da empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
 

Além disso, o Microsoft Intune Portal da Empresa equipe adoraria ouvir seus comentários. Acesse **ajuda** > **enviar comentários** para compartilhar seus pensamentos e ideias.  

## <a name="unverified-profiles"></a>Perfis não verificados  
Quando você exibe os perfis do MDM (gerenciamento de dispositivo móvel) instalados em **Preferências do Sistema** > **Perfis**, alguns perfis podem exibir um status não verificado. Se o perfil de gerenciamento exibe um status verificado, não é necessário se preocupar.  

O perfil de gerenciamento é o que define a conexão de canal do MDM. Contanto que o perfil de gerenciamento seja verificado, quaisquer outros perfis fornecidos ao computador por meio desse canal herdam as características secundárias do perfil de gerenciamento.  

## <a name="updating-the-company-portal-app"></a>Atualizando o aplicativo do Portal da Empresa

A atualização do aplicativo do Portal da Empresa é feita da mesma maneira que qualquer outro aplicativo do Office, por meio do Microsoft AutoUpdate para macOS. Descubra mais sobre [como atualizar aplicativos da Microsoft para macOS](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1).  

## <a name="next-steps"></a>Próximas etapas  
Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  


