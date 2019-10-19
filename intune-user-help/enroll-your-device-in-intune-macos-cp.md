---
title: Registrar seu dispositivo macOS no Intune com o Portal da Empresa | Microsoft Docs
description: Descreve como registrar um dispositivo macOS no Intune com o aplicativo Portal da Empresa
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ee725d118353e18924858569ac861992d19f839a
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506190"
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Registrar seu dispositivo macOS no Intune com o aplicativo Portal da Empresa

Registre seu dispositivo macOS no aplicativo Portal da Empresa do Intune para obter acesso seguro ao email, aos arquivos e aos aplicativos da organização.

As organizações geralmente exigem que seu dispositivo se torne gerenciado antes que você possa acessar dados proprietários por meio dele. Depois que um dispositivo se torna gerenciado, as organizações podem enviar por push políticas e aplicativos ao dispositivo por meio do provedor de gerenciamento de dispositivo móvel. Para obter acesso contínuo às suas informações corporativas ou de estudante no dispositivo, você precisa configurá-lo de acordo com as configurações da política.  

Este artigo descreve como o aplicativo Portal da Empresa do Intune para macOS ajuda você a registrar, configurar e manter seu dispositivo para atender aos requisitos organizacionais.  
</br>
> [!VIDEO https://www.youtube.com/embed/Pa2pfhwq_yk?rel=0]

## <a name="what-to-expect-from-the-company-portal-app"></a>O que esperar do aplicativo Portal da Empresa

Durante a instalação inicial, o aplicativo requer que você se autentique na organização. Em seguida, ele informa sobre as configurações do dispositivo que você deve fazer. Por exemplo, as organizações geralmente definem os requisitos de mínimo e máximo de caracteres de senha que você deverá atender.    

Depois que o dispositivo for registrado, o aplicativo Portal da Empresa continuará a verificar se o dispositivo está protegido. Se você instalar um aplicativo de uma fonte não confiável, por exemplo, o aplicativo o alertará e, às vezes, revogará o acesso aos dados da empresa. As políticas de proteção de aplicativo como essa são comuns nas organizações e, geralmente, exigem que você desinstale os aplicativos não confiáveis para que possa recuperar o acesso.

Se, após o registro, sua organização impuser um novo requisito de segurança, como a autenticação multifator, o aplicativo Portal da Empresa emitirá uma notificação. Você terá a oportunidade de ajustar as configurações para que possa continuar a trabalhar usando seu dispositivo.  

Para saber mais sobre o registro, confira [O que acontece quando eu instalo o aplicativo Portal da Empresa e registro meu dispositivo?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-device-managed"></a>Fazer com que o dispositivo seja gerenciado  
Use as etapas a seguir para registrar dispositivos macOS que executam o macOS 10,12 e posterior.   


1. Para acessar o site Portal da Empresa, abra uma nova janela no __Safari__ e acesse https://portal.manage.microsoft.com.  

2. Entre no site Portal da Empresa com sua conta corporativa ou de estudante.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. No canto superior esquerdo da página, clique em **Menus** > **Dispositivos**.  

4. A página __Dispositivos__ mostrará uma lista dos dispositivos gerenciados ou uma faixa. O conteúdo exibido depende da presença de um dispositivo gerenciado. 
    * Para adicionar um dispositivo que não está listado, selecione a faixa com informa **Toque aqui para informar qual dispositivo você está usando ou adicionar um novo dispositivo.**
    * Se você não tiver nenhum dispositivo, a faixa informará: **Você não tem nenhum dispositivo gerenciado. Adicione este ao tocar aqui.** Clique na faixa para adicionar seu dispositivo.  

     ![Uma captura de tela da página Dispositivos, com um quadrado vermelho em torno da opção de faixa para realçar onde clicar.](./media/CP-enroll-MACOS-1808.png)  
5. Conclua a etapa abaixo que corresponde à mensagem exibida atualmente no Portal da Empresa.  
    * Se você estiver adicionando um dispositivo pela primeira vez, será solicitado que você baixe o aplicativo Portal da Empresa em seu dispositivo. Clique em **Baixar** para continuar.  

         ![Captura de tela de exemplo da tela do prompt para baixar o aplicativo Portal da Empresa do macOS. O usuário tem a opção de clicar no botão azul de Download na parte inferior esquerda do prompt ou o botão cinza Cancelar na parte inferior direita.](./media/CP-enroll-download-macOS-1808.png)  

    * Se já houver um dispositivo macOS gerenciado, você receberá um prompt com uma lista de seus dispositivos macOS gerenciados no momento. Selecione **Meu dispositivo não está listado aqui** > **Baixar** para baixar o aplicativo Portal da Empresa no dispositivo que você está adicionando.  

         ![Captura de tela de exemplo da tela do prompt para baixar o aplicativo Portal da Empresa do macOS. O usuário tem a opção de selecionar *Meu dispositivo não está listado aqui* ou um dispositivo específico no meio da página. Um botão azul de Download é exibido na parte inferior esquerda do prompt e um botão cinza Cancelar é exibido na parte inferior direita](./media/cp-mac-os-device-isnt-here-1808.png)  

6. O dispositivo verificará se o arquivo de instalação **CompanyPortal.pkg** pode ser aberto com segurança. Depois que essa verificação for concluída, abra o instalador e conclua a instalação.  

7. Quando o instalador terminar, acesse a **Barra inicial** e abra **Portal da Empresa**.  

8. Seu dispositivo macOS solicitará que você confirme se você deseja abrir o aplicativo Portal da Empresa. Clique em **Abrir**.  

   > [!TIP]
   > O Intune precisa de acesso ao seu computador para certificar-se de que o dispositivo é seguro o suficiente para acessar recursos da sua organização. Se o computador se recusar a abrir o aplicativo Portal da Empresa [desabilite o Gatekeeper](https://support.apple.com/HT202491). Em seguida, abra o aplicativo.

9. A primeira tela exibida no aplicativo Portal da Empresa solicita que você **Entre**. Use a mesma conta corporativa ou de estudante que você usou para entrar no site Portal da Empresa.

10. O Portal da Empresa confirma as informações da conta e exibe os status **Registro de Dispositivo** e **Conformidade do Dispositivo**. Triângulos amarelos realçam as ações que você precisa executar para proteger seu dispositivo macOS corporativo ou de estudante. Clique em **Iniciar** para começar o registro. 

11. Se solicitado, digite suas informações de entrada do seu computador.  

Pode levar alguns minutos para registrar seu dispositivo no gerenciamento. Durante esse tempo, você pode usar seu dispositivo para outras coisas. Uma mensagem será exibida quando a Instalação do Acesso à Empresa for concluída para informá-lo que ela já terminou.  

## <a name="unverified-profiles"></a>Perfis não verificados
Quando você exibe os perfis do MDM (gerenciamento de dispositivo móvel) instalados para seu dispositivo macOS, alguns perfis podem exibir um status **Não verificado**. Desde que o **Perfil de gerenciamento** exiba um status **Verificado**, não é necessário se preocupar.  

O perfil de gerenciamento é o que define a conexão de canal do MDM. Contanto que o perfil de gerenciamento seja verificado, quaisquer outros perfis entregues ao computador, por meio desse canal, herdam as características secundárias do perfil de gerenciamento.

Além disso, como esses outros perfis não exigem verificações individuais, eles são gerados mais rapidamente e entregues aos dispositivos. 

## <a name="updating-the-company-portal-app"></a>Atualizando o aplicativo do Portal da Empresa

Atualizar o aplicativo do Portal da Empresa é feito da mesma maneira que qualquer outro aplicativo do Office, por meio do Microsoft AutoUpdate for Mac. Descubra mais sobre [como atualizar aplicativos da Microsoft para macOS aqui](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1).  

## <a name="next-steps"></a>Próximas etapas  
Precisa de ajuda adicional? Faça check-in com o suporte da sua empresa. Você pode encontrar as informações de contato deles no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  


