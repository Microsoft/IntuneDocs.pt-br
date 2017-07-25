---
title: Seu dispositivo Android parece estar criptografado
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/10/2017
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
ms.openlocfilehash: 370fbcf8bb424030eb7b7dbaba66fa943f08aa42
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Seu dispositivo Android parece estar criptografado, mas o Portal da Empresa informa o contrário

Ao criptografar um dispositivo, você está codificando as informações nele usando uma chave secreta conhecida apenas por você. Isso impede que pessoas não autorizadas o acessem. Muitas organizações requerem que seus usuários criptografem seus dispositivos Android antes que possam acessar os arquivos da empresa, o email ou os dados.

## <a name="common-issues"></a>Problemas comuns

As versões mais recentes do Android, particularmente a partir da v7.0, exigem uma senha de inicialização para garantir que o dispositivo está totalmente criptografado. Outros fabricantes de dispositivos têm descrições e locais diferentes para a senha de inicialização. Na maioria das vezes, essa configuração é conhecida como "Inicialização Segura". 

## <a name="solutions"></a>Soluções

### <a name="add-a-startup-pin"></a>Adicionar um PIN de inicialização

Alguns dispositivos Android exigirão que você crie um PIN de inicialização para assegurar que o dispositivo esteja seguro. Há várias versões do Android de vários fabricantes diferentes. Você pode tentar corrigir esse problema encontrando um local no aplicativo de configurações para habilitar essa opção. Por exemplo, no Samsung Galaxy S7, você habilita a Inicialização Segura acessando **Configurações** > **Tela de Bloqueio e Segurança** > **Inicialização Segura**.  

### <a name="downgrade-your-version-of-android"></a>Fazer o downgrade de sua versão do Android

Se o dispositivo oferecer a opção para fazer downgrade para o Android 6.0 e posterior, faça isso. Haverá um risco de perda de dados se você tentar fazer downgrade de seu dispositivo. Caso contrário, recomendamos contatar o administrador de TI para resolver esse problema. É possível obter informações de contato do administrador de TI no [site do Portal da Empresa](http://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Problemas de fabricante específicos

Alguns dispositivos Android na versão 7.0 e posterior criptografam dados de maneiras não consistentes com determinados padrões da plataforma Android. Esses dispositivos podem parecer criptografados mesmo quando eles são totalmente novos. O Intune reconhece que os métodos de criptografia desses dispositivos colocam as informações do dispositivo em risco. Esse risco deriva primariamente de usuários malintencionados que têm acesso físico ao dispositivo.

> [!Note]
> A Microsoft trabalha com os fabricantes para solucionar problemas encontrados durante o teste ou relatados pelos usuários. Atualizaremos este artigo sempre que novas informações estiverem disponíveis. 

## <a name="known-devices"></a>Dispositivos conhecidos

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Dispositivos conhecidos que podem ser atualizados para corrigir esse problema

Se você tiver um dos dispositivos a seguir, poderá ter esse problema caso não tenha atualizado seu dispositivo para a versão mais recente do Android. Instale as atualizações para esses dispositivos acessando **Configurações** > **Atualização**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Dispositivos conhecidos que não podem ser atualizados no momento para corrigir esse problema

Não é possível resolver esse problema para os dispositivos abaixo. Talvez você precise usar um dispositivo diferente para acessar recursos da empresa. 

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Huawei Mate 9](http://consumer.huawei.com/en/phones/mate9/)
- [Smartphones Xiaomi Mi](https://xiaomi-mi.com/mi-smartphones/)
