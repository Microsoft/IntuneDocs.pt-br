---
title: Resolver as restrições de ponto de acesso definidas no Intune
description: Examine as três mensagens comuns para as políticas de restrição de ponto de acesso do Intune e saiba como resolvê-las
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: aefde274ec7ca925d45dd101ee0ebef1083f7f19
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "55851263"
---
# <a name="resolve-access-point-restrictions"></a>Resolver as restrições de ponto de acesso

As organizações podem restringir os locais dos quais os dispositivos acessam dados corporativos.
Para configurar essas *restrições de ponto de acesso*, eles especificam e definem os locais de rede aprovados.  

Quando você tenta se conectar a uma rede não reconhecida ou não aprovada, pode receber uma ou mais das seguintes mensagens:

* Restrições de ponto de acesso não são configuradas.
* Você não é conectado a uma rede aprovada.
* Ocorreu um erro e não foi possível impor as restrições de ponto de acesso.

 As tabelas abaixo listam cada mensagem, o que ela significa e como acessar seus recursos de trabalho novamente.

## <a name="access-point-restrictions-not-set-up"></a>Restrições de ponto de acesso não configuradas  
| Mensagem no Portal da Empresa | O que essa mensagem significa | O que você deve fazer                                                               
|------------------------|--------------------------|--------------------------|
| **Restrições de ponto de acesso não estão configuradas – restrições de ponto de acesso estão ativas e devem ser configuradas.** | Sua empresa aplicou restrições de ponto de acesso ao seu dispositivo. Essa configuração requer o que aplicativo Portal da Empresa verifique algumas configurações de rede em seu dispositivo. | Toque em **Resolver.** O aplicativo Portal da Empresa verificará para garantir que você está conectado a uma rede da empresa aprovada. |

## <a name="not-connected-to-an-approved-network"></a>Não conectado a uma rede aprovada  

| Mensagem no Portal da Empresa | O que essa mensagem significa | O que você deve fazer                                                                   
|------------------------|-----------------------------------|--------------------------|
| **O dispositivo não está conectado a uma rede aprovada – conectar a uma rede sem fio aprovada.** | Você está conectado a uma rede não aprovada para acesso de trabalho. Enquanto você estiver conectado a essa rede, não poderá acessar email de trabalho, aplicativos e outros recursos corporativos protegidos. | Conecte-se a uma rede aprovada pela empresa. Em seguida, toque em **Resolver** para tentar novamente. |

## <a name="restrictions-couldnt-be-enforced"></a>Não foi possível impor restrições  

| Mensagem no Portal da Empresa | O que essa mensagem significa | O que você deve fazer                                                                      
|------------------------|-----------------------------------|--------------------------|
| **Não foi possível impor restrições de ponto de acesso – o Portal da Empresa encontrou um erro.** | O Intune não pode determinar se você está conectado a uma rede aprovada. Esse erro pode ser resultado de má conectividade de rede, bateria fraca, modo de economia de bateria ou um erro de Portal da Empresa. | Verifique se você tem uma recepção de rede forte. Desligue o modo de economia de bateria e verifique se a vida útil da bateria tem pelo menos 30% restantes. Em seguida, toque em **Resolver** para tentar novamente. 

Ainda precisa de ajuda? Recomendamos que você contate o suporte de sua empresa para obter ajuda. Para obter informações de contato específicas, vá para o [site Portal da Empresa](https://portal.manage.microsoft.com/#HelpDeskDialog).
