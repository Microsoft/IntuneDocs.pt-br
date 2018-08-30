---
title: Registrar o dispositivo macOS de propriedade de sua empresa ou fornecido por ela no gerenciamento | Microsoft Docs
description: Descreve como registrar um dispositivo macOS no Intune que foi comprado e fornecido pela sua organização.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 272a82f7d3d62d117fa5506ccf446b3169ff514f
ms.sourcegitcommit: bb56ada81e6d4950f130415918c4acc455bb52dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43016220"
---
# <a name="get-your-company-owned-macos-device-managed"></a>Tornar o dispositivo macOS de propriedade da sua empresa gerenciado

Saiba como tornar um novo dispositivo macOS gerenciado automaticamente no Intune.

Dispositivos de propriedade da escola e da empresa geralmente são pré-configurados antes de você os receber. Sua organização envia as configurações predefinidas para seu dispositivo quando você o liga e entra pela primeira vez. Depois de concluir a configuração do seu dispositivo, você terá acesso a recursos corporativos ou de estudante. 

Para começar a configuração de gerenciamento, ligue seu dispositivo e entre com suas credenciais corporativas ou de estudante. O restante deste artigo descreve as etapas e telas que você verá ao percorrer o Assistente de Instalação.   

## <a name="what-is-apple-dep"></a>O que é o DEP da Apple?
Se você tem um dispositivo de propriedade da empresa, talvez ele tenha sido adquirido pelo DEP (Programa de Registro de Dispositivos) da Apple. Algumas organizações compram grandes quantidades de dispositivos iOS ou macOS por meio do DEP da Apple. As organizações podem então configurar e gerenciar dispositivos dentro de seu provedor de gerenciamento de dispositivo móvel preferido, como o Intune. Se você é um administrador e deseja obter mais informações sobre o DEP da Apple, veja [Registrar dispositivos macOS automaticamente com o Programa de Registro de Dispositivos da Apple](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="set-up-your-macos-device"></a>Configurar seu dispositivo macOS  
Conclua as etapas a seguir para registrar seu dispositivo macOS no gerenciamento. Se você estiver usando seu próprio dispositivo, em vez de um dispositivo da empresa, siga as etapas para [dispositivos pessoais e do tipo “traga seu próprio dispositivo”](enroll-your-device-in-intune-macos-cp.md).  

1. Ligue seu dispositivo macOS. 
2. Escolha seu **Idioma** e clique em **Continuar**.  

   ![Captura da tela de Boas-vindas do assistente de instalação de dispositivo macOS, mostrando uma lista de idiomas dentre os quais escolher.](./media/macos-dep-welcome-1808.png)   
3. Escolha um layout de teclado. A lista mostra uma ou mais opções com base em seu idioma selecionado. Para ver todas as opções de layout, independentemente de seu idioma selecionado, clique em **Mostrar Tudo**. Quando terminar, clique em **Continuar**.  

   ![Captura de tela da tela de Layout do Teclado do Assistente de Instalação de dispositivo macOS, mostrando uma lista de idiomas do teclado dentre os quais selecionar, uma opção de Mostrar Tudo desmarcada e um botão Voltar e Continuar.](./media/macos-dep-keyboard-1808.png)  
4. Selecione sua rede Wi-Fi. Você deve ter uma conexão de Internet para continuar a instalação. Se sua rede não for exibida ou se você precisar se conectar usando uma rede com fio, clique em **Outras Opções de Rede**. Quando terminar, clique em **Continuar**.  

   ![Captura de tela de Selecionar sua Rede Wi-Fi do Assistente de Instalação do dispositivo macOS, mostrando uma lista de redes disponíveis para sua escolha. Também mostra um botão de Outras Opções de Rede, o botão Voltar e o botão Continuar.](./media/macos-dep-wifi-1808.png)  
5. Depois que você está conectado ao Wi-Fi, a tela **Gerenciamento Remoto** é exibida. O gerenciamento remoto permite que o administrador da organização configure remotamente seu dispositivo com redes, configurações, aplicativos e contas requeridos pela empresa. Antes de prosseguir, leia a documentação para entender como seu dispositivo é gerenciado. Em seguida, clique em **Continuar**.  

   ![Captura de tela de Gerenciamento Remoto do Assistente de Instalação de dispositivo macOS, com texto explicando o gerenciamento remoto e um link para a documentação para obter mais informações. Também mostra um botão Voltar e o botão Continuar.](./media/macos-dep-remote-management-1-1808.png)  
6. Quando solicitado, entre com sua conta corporativa ou de estudante. Após a autenticação, seu dispositivo instalará um perfil de gerenciamento. O perfil configura e permite seu acesso aos recursos da sua organização.  
7. Leia mais sobre o ícone de dados e privacidade da Apple para conseguir identificar mais tarde quando as informações pessoais estão sendo coletadas. Em seguida, clique em **Continuar**.  

   ![Captura de tela de Dados e Privacidade do Assistente de Instalação do dispositivo macOS, mostrando uma ilustração de duas pessoas apertando as mãos e, em seguida, descrevendo o uso feito pela Apple de informações pessoais. Também mostra um botão Voltar e o botão Continuar.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Depois que o dispositivo é registrado, você pode ter etapas adicionais para concluir. As etapas que você vê dependem de como sua organização personalizou a experiência de instalação. Ele pode exigir que você:
    * Entre em uma conta da Apple
    * Concorde com os termos e condições
    * Exclua uma conta do computador
    * Realize uma instalação expressa
    * Configure seu Mac  
## <a name="get-the-company-portal-app"></a>Obtenha o aplicativo Portal da Empresa      
Vá para a App Store para obter o aplicativo de Portal da Empresa do Intune em seu dispositivo. O aplicativo permite que você monitore, sincronize, adicione e remove seu dispositivo do gerenciamento e que instale aplicativos.

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
