---
title: Instalar a Defesa contra ameaças móveis em seu dispositivo móvel
description: Saiba como instalar a defesa contra ameaças móveis em seu dispositivo móvel.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f395a9cedc72a8184cfe3e29d6fcd3117a1473d
ms.sourcegitcommit: 259462591835f3607392aa6b179882dbac830a89
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72980352"
---
# <a name="install-mobile-threat-defense"></a>Instalar Defesa contra Ameaças Móveis   

Como parte dos requisitos de segurança de sua organização, talvez seja necessário instalar um aplicativo de fornecedor de defesa contra ameaças móveis (MTD). Esse tipo de aplicativo detecta e alerta você sobre ameaças em seu dispositivo, como aplicativos suspeitos, redes ou vulnerabilidades do sistema operacional.  

Se você não tiver o aplicativo MTD necessário, você será impedido de entrar em aplicativos protegidos com sua conta corporativa ou de estudante. Neste artigo, você aprenderá [a instalar um aplicativo MTD](set-up-mobile-threat-defense.md#install-app) para ser desbloqueado.  

Há uma variedade de aplicativos de fornecedores do MTD disponíveis para instalação; sua organização lhe permitirá saber qual delas usar. 


## <a name="information-your-organization-can-see"></a>Informações que sua organização pode ver   

Sua organização não pode ver dados, como textos, emails e imagens, em seus aplicativos pessoais. O aplicativo MTD relata informações sobre seus aplicativos, como nome e versão, para sua organização. As informações reais relatadas dependem do fornecedor de MTD que sua empresa usa. Sua organização pode ver:   

* Nome do aplicativo  
* ID do aplicativo: o nome exclusivo que identifica o aplicativo no Google Play.  
* Versão do aplicativo e número curto da versão: os números de versão específicos de um aplicativo.  
* Lote de aplicativo e tamanho dinâmico: a quantidade de espaço que um aplicativo usa em seu dispositivo. 


## <a name="install-app"></a>Instalar aplicativo    
Ao entrar em um aplicativo protegido, você será automaticamente solicitado a instalar um aplicativo MTD. Siga as etapas na tela para concluir a instalação. Use as etapas nesta seção para obter ajuda adicional.  
 
Você também pode ser solicitado a registrar seu dispositivo. O registro é necessário para confirmar sua identidade e conectar sua conta de estudante ou corporativa ao seu dispositivo. Se você não estiver registrado, será automaticamente guiado por meio dessa configuração antes de instalar o aplicativo MTD. Quando chegar à tela **obter acesso** , você pode iniciar as etapas de instalação.  

Para obter mais informações sobre o registro de dispositivo, consulte [registrar seu dispositivo pessoal na rede da sua organização](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network).  

### <a name="ios-setup"></a>instalação do iOS  

1. Na tela **obter acesso** , siga as instruções para instalar o aplicativo MTD exigido pela sua organização.   
2. Volte para a tela **obter acesso** e selecione **abrir**.  
3. O aplicativo MTD solicita permissão para abrir Microsoft Authenticator. Selecione **Abrir**. 
4. Selecione sua conta corporativa para entrar. 
5. Aguarde enquanto o aplicativo MTD examina seu dispositivo em busca de ameaças à segurança. 
6. Retorne ao aplicativo escolar ou de trabalho que você estava tentando acessar originalmente. Neste ponto, sua organização pode solicitar que você configure outros requisitos de segurança de aplicativo, como a criação de um PIN.   
7. Agora você deve ter acesso ao aplicativo. Se você ainda estiver bloqueado:  
    * Na tela **obter acesso** , selecione **verificar novamente**.  
    * Vá para o aplicativo MTD e verifique se há ameaças existentes. Conclua as etapas recomendadas para resolver a ameaça e reobter o acesso.    

### <a name="android-setup"></a>Configuração do Android 

1. Na tela **obter acesso** , siga as instruções para instalar o aplicativo MTD exigido pela sua organização.  
2. Volte para a tela **obter acesso** e selecione **abrir**.  
3. O aplicativo MTD solicita sua permissão para acessar determinadas áreas do seu dispositivo, caso seja necessário. Para que esse aplicativo funcione corretamente, você deve **permitir** o acesso aos contatos. As permissões solicitadas variam em todos os fornecedores de MTD.  
4. Selecione sua conta corporativa para entrar.  
5. Aguarde enquanto o aplicativo MTD examina seu dispositivo em busca de ameaças à segurança.  
6. Retorne ao aplicativo escolar ou de trabalho que você estava tentando acessar originalmente. Neste ponto, sua organização pode solicitar que você configure outros requisitos de segurança de aplicativo, como a criação de um PIN.  
7. Agora você deve ter acesso ao aplicativo. Se você ainda estiver bloqueado:  
    * Na tela **obter acesso** , selecione **verificar novamente**.  
    * Vá para o aplicativo MTD e verifique se há ameaças existentes. Conclua as etapas recomendadas para resolver a ameaça e reobter o acesso.  

### <a name="installation-failed"></a>Falha na instalação  

Se a instalação falhar, contate a pessoa de suporte de ti. Acesse o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para localizar as informações de contato da sua organização.  

Você também pode enviar seus logs de aplicativo para sua pessoa de suporte de ti para fornecer a eles mais contexto sobre a instalação.  
* Usuários do Android: [carregue e envie por email seus logs](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android) de portal da empresa.   

* usuários do dispositivo iOS: [recuperar e enviar seus logs](https://docs.microsoft.com/intune/apps/manage-microsoft-edge#use-microsoft-edge-on-ios-to-access-managed-app-logs) do Microsoft Edge para Ios.  

## <a name="resolve-a-threat"></a>Resolver uma ameaça  
Se uma ameaça exceder o nível de ameaça definido da sua organização, sua organização irá:  
   
* Bloquear acesso: impede que você use os aplicativos protegidos da sua organização enquanto estiver conectado à sua conta corporativa ou de estudante.  
* Apagar dados: exclui seus dados corporativos ou de estudante de um ou mais dos aplicativos protegidos da sua organização.  

Para resolver uma ameaça e reobter o acesso, abra o aplicativo MTD em seu dispositivo. Leia as informações fornecidas para saber como a ameaça pode afetar o dispositivo e como resolvê-lo. Depois de seguir as etapas para resolver a ameaça, volte para o aplicativo MTD e inicie uma nova verificação. Pode levar alguns minutos para restabelecer o acesso à sua organização.  

## <a name="next-steps"></a>Próximas etapas  

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
