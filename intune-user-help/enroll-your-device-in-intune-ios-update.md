---
title: Configurar o acesso aos recursos de sua empresa | Microsoft Docs
description: Descreve como fazer seu dispositivo iOS ser gerenciado pelo Intune
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 6474688a09c4063c55eff07f3cf84ebcb1911c65
ms.sourcegitcommit: c29241a88e67137f0fbc678b9eae1db2b2cded14
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-access-to-your-company-resources"></a>Configurar o acesso aos recursos de sua empresa

Sua empresa tem muitas informações proprietárias, de email, a arquivos, redes e muito mais. Sua empresa está usando o Microsoft Intune para ajudar a proteger essas informações quando você as acessa de seu dispositivo iOS. Isso permite que eles gerenciem esses recursos, mantenha-os mais seguros e de a você a liberdade para usar seu dispositivo preferido para realizar seu trabalho.

> [!NOTE]
> Se você está tentando acessar o email da empresa no aplicativo Mail, provavelmente você recebeu uma solicitação para gerenciar seu dispositivo para mantê-lo seguro. Siga as instruções abaixo para obter acesso ao seu email e a outros recursos da empresa em seu dispositivo iOS.

## <a name="before-you-start"></a>Antes de começar

- Não deixe de concluir todo o processo depois de começar. A pausa por mais de alguns minutos geralmente interrompe o processo e exige reinicialização.
- Se esse processo falhar, será necessário retornar ao aplicativo Portal da Empresa e tentar novamente.
- Verifique se o Wi-Fi está funcionando, e se o Safari funciona em seu dispositivo.
- Baixe e instale o [aplicativo do Portal da Empresa do Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Usar o aplicativo Portal da Empresa para configurar o acesso aos recursos da empresa

|O que você vê|Explicação|
|---|---|
|![Tela de entrada do Portal da Empresa, com o botão "Entrar" na parte inferior.](./media/ios-01-cp-enroll-1802.png)|Abra o aplicativo Portal da Empresa e toque em **Entrar**.|
|![Solicitação de entrada no Azure AD.](./media/ios-02-cp-enroll-1802.png)|Insira seu endereço de email corporativo e toque em **Avançar**.|
|![Solicitação de senha do Azure AD.](./media/ios-03-cp-enroll-1802.png)|Insira sua senha e toque em **Entrar**.|
|![Tela inicial do carregamento de recursos da empresa.](./media/ios-04-cp-enroll-1802.png)|Aguarde carregar.|
|![Página de Termos e Condições.](./media/ios-05-cp-enroll-1802.png)|Leia e **Aceite tudo** dos Termos e Condições.|
|![Tela Configurar acesso da empresa. Tanto o gerenciamento quanto as configurações necessitam de resolução no momento.](./media/ios-06-cp-enroll-1802.png)|Toque em **Iniciar** para iniciar o processo que permitirá ao seu dispositivo acessar os recursos da empresa. Se você não puder fazer isso agora, poderá **Adiar** o processo, mas você não poderá obter emails, documentos e muito mais.|
|![Tela O que minha empresa pode ver.](./media/ios-07-cp-enroll-1802.png)|**Saiba mais** sobre o que sua empresa pode ver tocando no link na parte inferior. Se não quiser, toque em **Continuar**.|
|![Tela O que vem a seguir.](./media/ios-08-cp-enroll-1802.png)|Esta tela explica o que está acontecendo na configuração. Você vai passar um tempo no Safari, no aplicativo Ajustes e no aplicativo Portal da Empresa para concluir esse processo. Toque em **Continuar**.|
|![Carregando a tela após tocar em Próximo em O que vem a seguir.](./media/ios-09-cp-enroll-1802.png)|Aguarde carregar.|
|![Alternou para o Safari para a inscrição.](./media/ios-7-cp-enroll-1711.png)|Você é enviado ao Safari para obter informações de gerenciamento para o seu dispositivo.|
|![Solicitação do sistema para abertura do aplicativo Ajustes.](./media/ios-8-cp-enroll-1711.png)|Toque em **Permitir** para abrir o aplicativo Ajustes e baixar o arquivo de configuração. Instale isso para permitir que sua empresa gerencie informações corporativas em seu dispositivo.|
|![O Perfil é aberto em Ajustes.](./media/ios-9-cp-enroll-1711.png)|Toque em **Instalar**.|
|![Instalando a caixa de diálogo modal do perfil na parte inferior da tela.](./media/ios-10-cp-enroll-1711.png)|Toque em **Instalar**.|
|![Tela de carregamento O perfil está sendo instalado.](./media/ios-11-cp-enroll-1711.png)|Aguarde carregar.|
|![Tela de aviso de gerenciamento de perfil.](./media/ios-12-cp-enroll-1711.png)|Este aviso, escrito pela Apple, fala mais sobre os tipos de ações que podem ser realizadas em um dispositivo sob gerenciamento. Saiba mais sobre [quais informações sua empresa pode ver](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![Solicitação do sistema sobre a confiança no gerenciamento remoto.](./media/ios-13-cp-enroll-1711.png)|Toque em **Confiar** para permitir que sua empresa gerencie informações corporativas e configurações em seu dispositivo.|
|![Tela de carregamento Concluindo a instalação do perfil.](./media/ios-14-cp-enroll-1711.png)|Aguarde carregar.|
|![Tela Perfil instalado.](./media/ios-15-cp-enroll-1711.png)|Seu perfil está instalado, e as informações corporativas e configurações do seu dispositivo estão muito próximas de serem gerenciadas.|
|![Alternou para o Safari para a inscrição.](./media/ios-16-cp-enroll-1711.png)|Você é enviado de volta ao Safari para terminar de receber informações de gerenciamento para o seu dispositivo. |
|![Solicitação do sistema para abrir o portal da empresa.](./media/ios-17-cp-enroll-1711.png)|Toque em **Abrir**.|
|![Tela Carregando recursos da empresa.](./media/ios-21-cp-enroll-1802.png)|Aguarde carregar.|
|![Selecione a categoria de dispositivo no aplicativo portal da empresa.](./media/ios-22-cp-enroll-1802.png)|Escolha a melhor categoria para seu dispositivo. Geralmente, isso tem a ver com quem é proprietário do dispositivo, ou sua localização frequente.|
|![Categoria selecionada.](./media/ios-23-cp-enroll-1802.png)||
|![Gerenciamento de dispositivo bem-sucedido; agora é necessário atualizar as configurações.](./media/ios-24-cp-enroll-1802.png)|Seu dispositivo está sendo gerenciado. Provavelmente, ainda há configurações que sua empresa precisa atualizar, como o tamanho da senha. Clique em **Continuar** para prosseguir.|
|![Confirmação das configurações do dispositivo.](./media/ios-25-cp-enroll-1802.png)|O Portal da Empresa verificará se as configurações precisam ser atualizadas.|
|![Verificação das configurações concluída, com uma versão incorreta do sistema operacional](./media/ios-26-cp-enroll-1802.png)|O Portal da Empresa fornecerá instruções sobre como você pode corrigir quaisquer problemas com as configurações. Ao terminar de corrigir os problemas, toque em **Verificar Configurações**.|
|![Tela de carregamento Confirmação das configurações do dispositivo](./media/ios-27-cp-enroll-1802.png)|O dispositivo verificará se as configurações estão seguras o suficiente para acessar os recursos da empresa.|
|![Inscrição bem-sucedida e configurações atualizadas](./media/ios-28-cp-enroll-1802.png)|Parabéns! Agora, seu dispositivo está registrado no Intune.|

> [!Note]
> Talvez ainda haja mais algumas etapas para concluir antes que o dispositivo esteja totalmente gerenciado. Saiba mais sobre como [registrar seu dispositivo usando o gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se sua organização estiver usando o Programa de registro de dispositivos da Apple, descubra mais [aqui](enroll-your-device-dep-ios.md).

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
