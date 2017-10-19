---
title: Seu dispositivo Android parece estar criptografado
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: be68e330c2bd2800ea68fd83845b71e3b257e785
ms.sourcegitcommit: 751587b1c6ed15877152d770772748e042c1e3ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Seu dispositivo Android parece estar criptografado, mas o Portal da Empresa informa o contrário

Ao criptografar um dispositivo, você está codificando as informações nele usando uma chave secreta conhecida apenas por você. Isso impede que pessoas não autorizadas o acessem. Muitas organizações requerem que seus usuários criptografem seus dispositivos Android antes que possam acessar os arquivos da empresa, o email ou os dados.

## <a name="common-issues"></a>Problemas comuns

As versões mais recentes do Android, particularmente a partir da v7.0, exigem uma senha de inicialização para garantir que o dispositivo está totalmente criptografado. Outros fabricantes de dispositivos têm descrições e locais diferentes para a senha de inicialização. Na maioria das vezes, essa configuração é conhecida como "Inicialização Segura". 

## <a name="solutions"></a>Soluções

### <a name="add-a-startup-pin"></a>Adicionar um PIN de inicialização

Alguns dispositivos Android exigirão que você crie um PIN de inicialização para assegurar que o dispositivo esteja seguro. Há várias versões do Android de vários fabricantes diferentes. Você pode tentar corrigir esse problema encontrando um local no aplicativo de configurações para habilitar essa opção. Por exemplo, no Samsung Galaxy S7, você habilita a Inicialização Segura acessando **Configurações** > **Tela de Bloqueio e Segurança** > **Inicialização Segura**.  

### <a name="downgrade-your-version-of-android"></a>Fazer o downgrade de sua versão do Android

Se o dispositivo oferecer a opção para fazer downgrade para o Android 6.0 e posterior, faça isso. Haverá um risco de perda de dados se você tentar fazer downgrade de seu dispositivo. Caso contrário, recomendamos contatar o suporte de sua empresa para resolver esse problema. É possível obter informações de contato do suporte de sua empresa no [site do Portal da Empresa](https://portal.manage.microsoft.com).

### <a name="encrypt-the-entire-device"></a>Criptografar todo o dispositivo

Alguns dispositivos terão a opção de criptografar todo o dispositivo ou somente o espaço usado. Escolha a opção para criptografar todo o dispositivo em vez de "somente o espaço usado". Se você já tiver criptografado somente o espaço usado:

1. [Remova o dispositivo do Portal da Empresa](unenroll-your-device-from-intune-android.md)
2. Descriptografar o espaço usado
3. Criptografar todo o dispositivo
4. Registrar o dispositivo novamente

## <a name="specific-manufacturer-issues"></a>Problemas de fabricante específicos

Alguns dispositivos Android na versão 7.0 e posterior criptografam dados de maneiras não consistentes com determinados padrões da plataforma Android. Esses dispositivos podem parecer criptografados mesmo quando eles são totalmente novos. O Intune reconhece que os métodos de criptografia desses dispositivos colocam as informações do dispositivo em risco. Esse risco deriva primariamente de usuários malintencionados que têm acesso físico ao dispositivo.

> [!Note]
> A Microsoft trabalha com os fabricantes para solucionar problemas encontrados durante o teste ou relatados pelos usuários. Atualizaremos este artigo sempre que novas informações estiverem disponíveis. 

## <a name="known-devices"></a>Dispositivos conhecidos

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Dispositivos conhecidos que podem ser atualizados para corrigir esse problema

Se você tiver um dos dispositivos a seguir, poderá ter esse problema caso não tenha atualizado seu dispositivo para a versão mais recente do Android. Instale as atualizações para esses dispositivos acessando **Configurações** > **Atualização**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Dispositivos conhecidos que não podem ser atualizados no momento para corrigir esse problema

Não é possível resolver esse problema para os dispositivos abaixo. Talvez você precise usar um dispositivo diferente para acessar recursos da empresa. 

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Smartphones Xiaomi Mi](https://xiaomi-mi.com/mi-smartphones/)
