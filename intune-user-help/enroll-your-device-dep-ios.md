---
title: Registre no gerenciamento o dispositivo iOS fornecido pela organização. | Microsoft Docs
description: Descreve como registrar no Intune um dispositivo iOS que foi comprado e fornecido pela sua organização
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f4e7d87e-56d1-43e4-8e88-2f62cf0999e2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e5ce83d20958f3ba4c818e49b0c226e07851d03
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506233"
---
# <a name="enroll-your-organization-provided-ios-device-in-management"></a>Registrar no gerenciamento o dispositivo iOS fornecido pela organização

Saiba como fazer com que o novo dispositivo iOS seja gerenciado no Intune.  

Os dispositivos iOS que são fornecidos pela escola ou empresa costumam ser pré-configurados antes de serem entregues a você. Sua organização enviará essas configurações pré-definidas ao dispositivo depois que você o ligar e entrar pela primeira vez. Depois de concluir a configuração do dispositivo, você terá acesso aos recursos corporativos ou de estudante.  

Para começar a configuração, ligue o dispositivo e entre com suas credenciais corporativas ou de estudante. O restante deste artigo descreve as etapas e telas que você verá ao percorrer o Assistente de Instalação.

## <a name="what-is-apple-dep"></a>O que é o DEP da Apple?

É possível que sua organização tenha comprado os dispositivos por meio do chamado *DEP (Programa de registro de dispositivos) da Apple*. O DEP da Apple permite que as organizações comprem grandes quantidades de dispositivos iOS ou macOS. As organizações podem então configurar e gerenciar esses dispositivos com seu provedor de gerenciamento de dispositivo móvel preferido, como o Intune. Se você é um administrador e deseja obter mais informações sobre o DEP da Apple, veja [Registrar dispositivos iOS automaticamente no Programa de registro de dispositivos da Apple](/intune/enrollment/device-enrollment-program-enroll-ios).

## <a name="set-up-your-ios-device"></a>Configurar seu dispositivo iOS

Se você estiver usando seu próprio dispositivo iOS e não um fornecido pela empresa, siga as etapas para [dispositivos pessoais e do tipo “traga seu próprio dispositivo”](enroll-your-device-in-intune-ios.md).  

1. Ligue seu dispositivo iOS.
2. Depois de selecionar o **Idioma**, conecte o dispositivo ao Wi-Fi.
3. Na tela **Configurar dispositivo iOS**, escolha se você deseja:
   - **Configurar como novo dispositivo**
   - **Restaurar do backup do iCloud**
   - **Restaurar do backup do iTunes**

4. Depois de você ter se conectado ao Wi-Fi, a tela **Configuração** será exibida. Isso informará que **[Sua empresa] configurará automaticamente seu dispositivo.**

   **A configuração permite à [Sua empresa] gerenciar este dispositivo por conexão sem fio. Um administrador pode ajudar você a configurar contas de email e de rede, instalar e configurar aplicativos e gerenciar configurações remotamente. Um administrador pode desabilitar recursos, instalar e remover aplicativos, monitorar e restringir o tráfego de Internet e apagar remotamente este dispositivo.**

   **A configuração é fornecida pela: Equipe do iOS da [Sua empresa] [endereço]**

5. Faça logon com sua ID da Apple. Fazer logon permite instalar o aplicativo do Portal da Empresa e instalar o perfil de gerenciamento que permitirá à sua empresa conceder a você acesso aos recursos, como email e aplicativos.
6. Concorde com os **termos e condições** e decida se deseja enviar informações de diagnóstico para a Apple.
7. Depois de concluir o registro, o dispositivo pode solicitar que você realize mais ações. Algumas dessas etapas podem inserir sua senha para acesso de email ou configurar uma senha.

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
