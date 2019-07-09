---
title: Criptografe o dispositivo do Intune | Microsoft Docs
description: Etapas para ativar a criptografia de dispositivo Android quando exigidos pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfc17c60412a1cfe90693216caa69ada3d2d2c9a
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67545252"
---
# <a name="encrypting-your-android-device"></a>Criptografar o dispositivo Android

Criptografia do dispositivo protege seus arquivos e pastas contra acesso não autorizado se o dispositivo for perdido ou roubado. Depois de ativar a criptografia do dispositivo, somente os indivíduos com o pin ou senha correta será capazes de entrar seu dispositivo. 

Antes de poder acessar os recursos de trabalho ou de estudante, sua organização pode exigir que você criptografe seu dispositivo Android. Alguns dispositivos Android mais recentes são criptografados por padrão, out-of-the-box.  

## <a name="turn-on-encryption"></a>Ativar a criptografia

Se o Portal da empresa ou o aplicativo do Microsoft Intune solicitará que você criptografe seu dispositivo, conclua as etapas a seguir. 

> [!Note]
> Alguns dispositivos Android do Huawei, Vivo e OPPO não podem ser criptografados. Saiba mais [aqui](your-device-appears-encrypted-but-cp-says-otherwise-android.md).  

1. Defina um bloqueio de tela do dispositivo.  
    a. Acesse **Configurações** > **Tela de bloqueio e segurança** > **Tipo de bloqueio de tela**.  
    b. Selecione a **PIN**, **senha**, ou **padrão**.  
    c. Siga as instruções na tela para configurar seu bloqueio de tela.  

2. Volte para **tela de bloqueio e segurança** e selecione **Secure startup**.
3. Escolher **exigir PIN quando o dispositivo liga** > **Okey**.
4. Insira seu PIN para confirmar e criptografar seu dispositivo.
5. Abra o aplicativo Portal da empresa ou o Microsoft Intune.
    * Usuários do Portal da Empresa: selecione seu dispositivo e toque em **Verificar as configurações do dispositivo**. 
    * Os usuários do Microsoft Intune: você terá de esperar até que as atualizações de página, mas quando isso acontecer, seu status de criptografia deve alterar a conformidade.  

Dispositivos que executam o Android 4.4 e versões anteriores não podem ter o **inicialização segura** opção. Nesse caso, conclua as seguintes etapas para criptografar seu dispositivo.

1. Vá para **as configurações** > **segurança** > **criptografar dispositivo**. Na tela rótulos variam entre os dispositivos Android. Se você não vir as **criptografar dispositivo** opção, faça check-in:
    * **Armazenamento** > **criptografia de armazenamento**
    * **Armazenamento** > **tela de bloqueio e segurança** > **outras configurações de segurança** 

2. Siga as instruções na tela. Durante a criptografia, seu dispositivo pode reiniciar várias vezes.
3. Abra o aplicativo Portal da empresa ou o Microsoft Intune.
    * Usuários do Portal da Empresa: selecione seu dispositivo e toque em **Verificar as configurações do dispositivo**.  
    * Os usuários do Microsoft Intune: você terá de esperar até que as atualizações de página, mas quando isso acontecer, seu status de criptografia deve alterar a conformidade.

## <a name="troubleshoot"></a>Solucionar problemas  
**Problema**: você já tiver criptografado o seu dispositivo e

- O botão de criptografia está desabilitado.
- Uma mensagem dizendo que você ainda precisa criptografá-lo é exibida.
- Você obtiver erros ao tentar usar o aplicativo de Portal da empresa ou o Microsoft Intune.

**Ações recomendadas**

- Verifique se o dispositivo está carregado e conectado.  
- Verifique se você definiu um PIN ou uma senha no dispositivo.  

Ainda precisa de ajuda? Entre em contato com o suporte de sua empresa (consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obter as informações de contato) ou escreva para a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">equipe de Android da Microsoft</a>.  
