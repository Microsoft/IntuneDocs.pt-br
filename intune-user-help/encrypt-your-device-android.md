---
title: Criptografar dispositivo Android para o Intune | Microsoft Docs
description: Etapas para ativar a criptografia de dispositivo Android quando exigido pelo Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2965d6a017d92bd4535a29a2257c0cac5e6deaf
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506354"
---
# <a name="encrypting-your-android-device"></a>Criptografar o dispositivo Android

A criptografia de dispositivo protege seus arquivos e pastas contra o acesso não autorizado se o dispositivo for perdido ou roubado. Depois de ativar a criptografia de dispositivo, somente indivíduos com a senha ou o PIN correto poderão entrar no seu dispositivo. 

Antes de poder acessar os recursos de estudante ou de trabalho, sua organização pode exigir que você criptografe seu dispositivo Android. Alguns dispositivos Android mais recentes são criptografados por padrão, prontos para uso.  

## <a name="turn-on-encryption"></a>Ativar criptografia

Se Portal da Empresa ou o aplicativo Microsoft Intune solicitar que você criptografe seu dispositivo, conclua as etapas a seguir. 

> [!Note]
> Determinados dispositivos Android da Huawei, da vivo e do OPPO não podem ser criptografados. Saiba mais [aqui](your-device-appears-encrypted-but-cp-says-otherwise-android.md).  

1. Defina um bloqueio de tela do dispositivo.  
    a. Acesse **Configurações** > **Tela de bloqueio e segurança** > **Tipo de bloqueio de tela**.  
    b. Selecione **PIN**, **senha**ou **padrão**.  
    c. Siga as instruções na tela para configurar o bloqueio de tela.  

2. Volte para **tela de bloqueio e segurança** e selecione **inicialização segura**.
3. Escolha **exigir PIN quando o dispositivo ligar** > **OK**.
4. Insira seu PIN para confirmar e criptografar seu dispositivo.
5. Abra o Portal da Empresa ou Microsoft Intune aplicativo.
    * Usuários do Portal da Empresa: selecione seu dispositivo e toque em **Verificar as configurações do dispositivo**. 
    * Microsoft Intune usuários: você precisará aguardar até que a página seja atualizada, mas quando ela for, seu status de criptografia deverá mudar para compatível.  

Dispositivos que executam o Android 4,4 e anterior podem não ter a opção de **inicialização segura** . Nesse caso, conclua as etapas a seguir para criptografar seu dispositivo.

1. Vá para **configurações** > **segurança** > **criptografar dispositivo**. Os rótulos na tela variam de acordo com os dispositivos Android. Se você não vir a opção **criptografar dispositivo** , faça check-in:
    * **Armazenamento** > **criptografia de armazenamento**
    * **Armazenamento** > **tela de bloqueio e segurança** > **outras configurações de segurança** 

2. Siga as instruções na tela. Durante a criptografia, seu dispositivo pode reiniciar várias vezes.
3. Abra o Portal da Empresa ou Microsoft Intune aplicativo.
    * Usuários do Portal da Empresa: selecione seu dispositivo e toque em **Verificar as configurações do dispositivo**.  
    * Microsoft Intune usuários: você precisará aguardar até que a página seja atualizada, mas quando ela for, seu status de criptografia deverá mudar para compatível.

## <a name="troubleshoot"></a>Solucionar problemas  
**Problema**: você já criptografou seu dispositivo e

- O botão de criptografia está desabilitado.
- Uma mensagem dizendo que você ainda precisa criptografá-lo é exibida.
- Você recebe erros ao tentar usar o Portal da Empresa ou Microsoft Intune aplicativo.

**Ações recomendadas**

- Verifique se o dispositivo está carregado e conectado.  
- Verifique se você definiu um PIN ou uma senha no dispositivo.  

Ainda precisa de ajuda? Entre em contato com o suporte de sua empresa (consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obter as informações de contato) ou escreva para a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">equipe de Android da Microsoft</a>.  
