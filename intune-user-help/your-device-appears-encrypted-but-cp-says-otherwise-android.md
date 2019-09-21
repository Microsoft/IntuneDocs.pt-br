---
title: Seu dispositivo Android parece estar criptografado | Microsoft Docs
description: Resolver o status de criptografia no aplicativo Portal da Empresa e Microsoft Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ec52069c4c53c464cfe5a1e17718ba6725fd0b5
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167435"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Dispositivo criptografado, mas aplicativos dizem de outra forma

Se Portal da Empresa ou o aplicativo Microsoft Intune dizer que seu dispositivo não está criptografado, mas você tem certeza de que está, tente as etapas neste artigo.  

## <a name="add-a-startup-pin"></a>Adicionar um PIN de inicialização

Alguns dispositivos Android exigirão que você crie um PIN de inicialização para assegurar que o dispositivo esteja seguro. O local dessa configuração estará no aplicativo de **configurações** do seu dispositivo. O nome e o local da configuração podem variar. Por exemplo, no Samsung Galaxy S7, a configuração é conhecida como **inicialização segura**. Para habilitá-lo e criar uma senha, vá para **configurações** > **tela de bloqueio e segurança** > **inicialização segura**.  

## <a name="encrypt-the-entire-device"></a>Criptografar todo o dispositivo

Esta seção se aplica somente ao aplicativo Portal da Empresa. Alguns dispositivos terão a opção de criptografar todo o dispositivo ou somente o espaço usado. Escolha a opção para criptografar o dispositivo inteiro. Se você tiver selecionado criptografar apenas o espaço usado:

1. [Remova esse dispositivo do Portal da Empresa](unenroll-your-device-from-intune-android.md).
2. Descriptografe o espaço usado.  
3. Criptografe todo o dispositivo.  
4. Registrar o dispositivo novamente.  

## <a name="downgrade-your-version-of-android"></a>Fazer o downgrade de sua versão do Android

Esta seção se aplica somente ao aplicativo Portal da Empresa. Se o dispositivo oferecer a opção para fazer downgrade para o Android 6.0 e posterior, faça isso. Haverá um risco de perda de dados se você tentar fazer downgrade de seu dispositivo. Caso contrário, recomendamos contatar o suporte de sua empresa para resolver esse problema. Obtenha as informações de contato do suporte de sua empresa no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="specific-manufacturer-issues"></a>Problemas de fabricante específicos

Alguns dispositivos Android na versão 7.0 e posterior criptografam dados de maneiras não consistentes com determinados padrões da plataforma Android. Esses métodos de criptografia colocam as informações do dispositivo em risco. Como resultado, esses dispositivos não têm suporte.

Para obter uma lista não completa de dispositivos Android com suporte, consulte o artigo [sistemas operacionais e navegadores com suporte no Intune](https://docs.microsoft.com/intune/supported-devices-browsers.md#supported-samsung-knox-standard-devices). Se o dispositivo não estiver listado, consulte o fabricante do dispositivo ou contate a pessoa de suporte.

> [!Note]
> A Microsoft trabalha com os fabricantes para solucionar quaisquer problemas que encontrarmos em testes ou relatados pelos usuários. Atualizaremos este artigo sempre que novas informações estiverem disponíveis.

## <a name="update-devices"></a>Atualizar dispositivos

Se você não atualizou seu dispositivo para a versão mais recente do Android, vá para o aplicativo de **configurações** do dispositivo e selecione **Atualizar**.  

## <a name="next-steps"></a>Próximas etapas

Ainda precisa de ajuda? Entre em contato com o suporte de sua empresa (consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obter as informações de contato) ou escreva para a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">equipe de Android da Microsoft</a>.  
