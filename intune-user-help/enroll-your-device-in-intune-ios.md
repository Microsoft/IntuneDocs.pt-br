---
title: Configurar o acesso aos recursos de sua empresa | Microsoft Docs
description: Descreve como fazer seu dispositivo iOS ser gerenciado pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 51492c1a8d7e32ab7dbdd5d896e7726c877d62d5
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43149576"
---
# <a name="set-up-access-to-your-company-resources"></a>Configurar o acesso aos recursos de sua empresa

Registre seu dispositivo iOS no aplicativo Portal da Empresa do Intune para obter acesso seguro ao email, aos arquivos e aos aplicativos da organização.

As organizações geralmente exigem que seu dispositivo se torne gerenciado antes que você possa acessar dados proprietários por meio dele. Depois que um dispositivo se torna gerenciado, as organizações podem enviar por push políticas e aplicativos ao dispositivo por meio do provedor de gerenciamento de dispositivo móvel. 

Para obter acesso contínuo às suas informações corporativas ou de estudante no dispositivo, você precisa configurá-lo de acordo com as configurações da política. Este artigo descreve como o aplicativo Portal da Empresa do Intune para iOS ajuda você a registrar, configurar e manter seu dispositivo para atender aos requisitos organizacionais.

> [!NOTE]
> Se você está tentando acessar o email da empresa no aplicativo Mail, provavelmente você recebeu uma solicitação para gerenciar seu dispositivo para mantê-lo seguro. Siga as instruções abaixo para obter acesso ao seu email e a outros recursos da empresa em seu dispositivo iOS.

## <a name="what-to-expect-from-the-company-portal-app"></a>O que esperar do aplicativo Portal da Empresa

### <a name="security"></a>Segurança 
Durante a instalação inicial, o aplicativo requer que você se autentique na organização. Em seguida, ele informa sobre as configurações do dispositivo que você deve fazer. Por exemplo, as organizações geralmente definem os requisitos de mínimo e máximo de caracteres de senha que você deverá atender.    

### <a name="protection"></a>Proteção
Depois que o dispositivo for registrado, o aplicativo Portal da Empresa continuará a verificar se o dispositivo está protegido. Se você instalar um aplicativo de uma fonte não confiável, por exemplo, o aplicativo o alertará e, às vezes, revogará o acesso aos dados da empresa. As políticas de proteção de aplicativo como essa são comuns nas organizações e, geralmente, exigem que você desinstale os aplicativos não confiáveis para que possa recuperar o acesso.

### <a name="setting-notifications"></a>Definindo notificações
Se, após o registro, sua organização impuser um novo requisito de segurança, como a autenticação multifator, o aplicativo Portal da Empresa emitirá uma notificação. Você terá a oportunidade de ajustar as configurações para que possa continuar a trabalhar usando seu dispositivo.  

Para saber mais sobre o registro, confira [O que acontece quando eu instalo o aplicativo Portal da Empresa e registro meu dispositivo?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md). 

## <a name="before-you-start"></a>Antes de começar

- Depois de começar, conclua o processo inteiro. Se você pausar por mais do que alguns minutos, a instalação poderá ser encerrada e exigir que você comece novamente.  
    - Se esse processo falhar, retorne ao aplicativo Portal da Empresa e tente novamente.  
- Verifique se o Wi-Fi está funcionando e se o Safari funciona no dispositivo.
- Baixe e instale o [aplicativo do Portal da Empresa do Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Usar o aplicativo Portal da Empresa para configurar o acesso aos recursos da empresa

|O que você vê|Explicação|
|---|---|
|![Tela de entrada do Portal da Empresa, com o botão "Entrar" na parte inferior.](./media/ios-01-cp-enroll-1802.png)|Abra o aplicativo Portal da Empresa e toque em **Entrar**.|
|![Prompt de entrada do Azure AD.](./media/ios-02-cp-enroll-1802.png)|Insira seu endereço de email corporativo e toque em **Avançar**.|
|![Solicitação de senha do Azure AD.](./media/ios-03-cp-enroll-1802.png)|Insira sua senha e toque em **Entrar**.|
|![Tela inicial do carregamento de recursos da empresa.](./media/ios-04-cp-enroll-1802.png)|Espere até que essa tela seja carregada.|
|![Página de Termos e Condições.](./media/ios-05-cp-enroll-1802.png)|Leia e **Aceite tudo** dos Termos e Condições.|
|![Tela Configurar acesso da empresa. Tanto o gerenciamento quanto as configurações necessitam de resolução no momento.](./media/ios-06-cp-enroll-1802.png)|Toque em **Iniciar** para iniciar o processo que permitirá ao seu dispositivo acessar os recursos da empresa. Se você não puder fazer isso agora, poderá **Adiar** o processo, mas você não poderá obter emails, documentos e muito mais.|
|![Tela O que minha empresa pode ver.](./media/ios-07-cp-enroll-1802.png)|**Saiba mais** sobre o que sua empresa pode ver tocando no link na parte inferior. Se não quiser, toque em **Continuar**.|
|![Tela O que vem a seguir.](./media/ios-08-cp-enroll-1802.png)|Esta tela explica o que está acontecendo na configuração. Você dedicará um tempo ao Safari, ao aplicativo Configurações e ao aplicativo Portal da Empresa para concluir esse processo. Toque em **Continuar**.|
|![Carregando a tela após tocar em Próximo em O que vem a seguir.](./media/ios-09-cp-enroll-1802.png)|Espere até que essa tela seja carregada.|
|![Alternou para o Safari para a inscrição.](./media/ios-7-cp-enroll-1711.png)|Você é enviado ao Safari para obter informações de gerenciamento para o seu dispositivo.|
|![Solicitação do sistema para abertura do aplicativo Ajustes.](./media/ios-8-cp-enroll-1711.png)|Toque em **Permitir** para abrir o aplicativo Ajustes e baixar o arquivo de configuração. Instale isso para permitir que sua empresa gerencie informações corporativas em seu dispositivo.|
|![O perfil abre as configurações do dispositivo.](./media/ios-9-cp-enroll-1711.png)|Toque em **Instalar**.|
|![Instalando a caixa de diálogo modal do perfil na parte inferior da tela.](./media/ios-10-cp-enroll-1711.png)|Toque em **Instalar**.|
|![Tela de carregamento O perfil está sendo instalado.](./media/ios-11-cp-enroll-1711.png)|Espere até que essa tela seja carregada.|
|![Tela de aviso de gerenciamento de perfil.](./media/ios-12-cp-enroll-1711.png)|Este aviso, escrito pela Apple, fala mais sobre os tipos de ações que podem ser realizadas em um dispositivo sob gerenciamento. Saiba mais sobre [quais informações sua empresa pode ver](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![Solicitação do sistema sobre a confiança no gerenciamento remoto.](./media/ios-13-cp-enroll-1711.png)|Toque em **Confiar** para permitir que sua empresa gerencie informações corporativas e configurações em seu dispositivo.|
|![Tela de carregamento Concluindo a instalação do perfil.](./media/ios-14-cp-enroll-1711.png)|Espere até que essa tela seja carregada.|
|![Tela Perfil instalado.](./media/ios-15-cp-enroll-1711.png)|Seu perfil está instalado, e as informações corporativas e configurações do seu dispositivo estão muito próximas de serem gerenciadas.|
|![Alternou para o Safari para a inscrição.](./media/ios-16-cp-enroll-1711.png)|Você é enviado de volta ao Safari para terminar de receber informações de gerenciamento para o seu dispositivo. |
|![Solicitação do sistema para abrir o portal da empresa.](./media/ios-17-cp-enroll-1711.png)|Toque em **Abrir**.|
|![Tela Carregando recursos da empresa.](./media/ios-21-cp-enroll-1802.png)|Espere até que essa tela seja carregada.|
|![Selecione a categoria de dispositivo no aplicativo portal da empresa.](./media/ios-22-cp-enroll-1802.png)|Escolha a melhor categoria para seu dispositivo. Geralmente, isso tem a ver com quem é proprietário do dispositivo, ou sua localização frequente.|
|![Categoria selecionada.](./media/ios-23-cp-enroll-1802.png)||
|![Gerenciamento de dispositivo bem-sucedido; agora é necessário atualizar as configurações.](./media/ios-24-cp-enroll-1802.png)|Seu dispositivo está sendo gerenciado. Provavelmente, ainda há configurações que sua empresa precisa atualizar, como o tamanho da senha. Clique em **Continuar** para prosseguir.|
|![Confirmação das configurações do dispositivo.](./media/ios-25-cp-enroll-1802.png)|O Portal da Empresa verificará se as configurações precisam ser atualizadas.|
|![Verificação das configurações concluída, com uma versão incorreta do sistema operacional](./media/ios-26-cp-enroll-1802.png)|O Portal da Empresa fornecerá instruções sobre como você pode corrigir quaisquer problemas com as configurações. Ao terminar de corrigir os problemas, toque em **Verificar Configurações**.|
|![Tela de carregamento Confirmação das configurações do dispositivo](./media/ios-27-cp-enroll-1802.png)|O dispositivo verificará se as configurações estão seguras o suficiente para acessar os recursos da empresa.|
|![Inscrição bem-sucedida e configurações atualizadas](./media/ios-28-cp-enroll-1802.png)|Parabéns! Agora, seu dispositivo está registrado no Intune.|

> [!Note]
> Talvez ainda haja mais algumas etapas para concluir antes que o dispositivo esteja totalmente gerenciado. Saiba mais sobre como [registrar seu dispositivo usando o gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se sua organização estiver usando o Programa de registro de dispositivos da Apple, descubra mais [aqui](enroll-your-device-dep-ios.md).

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
