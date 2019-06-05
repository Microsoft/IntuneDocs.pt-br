---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 1073a38da8a5b2467b1ff8c97b32b93f92e34e4c
ms.sourcegitcommit: f90cba0b2c2672ea733052269bcc372a80772945
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66454137"
---
Esses avisos fornecem informações importantes que podem ajudar você a se preparar para os recursos e as alterações futuras do Intune. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Atualize o aplicativo Portal da Empresa para Android para a versão mais recente <!--4536963-->
Periodicamente o Intune lança atualizações para o aplicativo Portal da Empresa para Android. Em novembro de 2018, lançamos uma atualização do Portal da Empresa, que incluiu um comutador de back-end para preparar para a alteração do Google da plataforma de notificação existente do FCM (Firebase Cloud Messaging) da Google. Quando o Google desativar a plataforma de notificação existente e migrar para o FCM, os usuários finais precisarão atualizar o aplicativo Portal da Empresa pelo menos até novembro de 2018 para continuar a se comunicar com a Google Play Store.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Nossa telemetria indica que você tem dispositivos com uma versão do Portal da Empresa anterior à 5.0.4269.0. Se esta versão ou a posterior do aplicativo Portal da Empresa não estiver instalada, pode ser que ações de dispositivo iniciadas por um profissional de TI, como limpar, redefinir senha, instalações de aplicativos disponíveis e necessárias, e registrar certificados, não funcionem como o esperado. Se os dispositivos estiverem registrado no MDM do Intune, você poderá ver os usuários e as versões do Portal da Empresa acessando os aplicativos do Cliente, aplicativos Descobertos. Selecionar versões anteriores do Portal da Empresa permitirá que você veja quais usuários finais tem os dispositivos que ainda não atualizaram o Portal da Empresa.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Peça aos usuários finais de dispositivos Android que não atualizaram para atualizar o Portal da Empresa por meio do Google Play. Notifique o suporte técnico caso um usuário não tenha mantido a atualização automática do aplicativo Portal da Empresa. Veja o link nas Informações Adicionais para saber mais sobre a plataforma do FCM do Google e a alteração.

#### <a name="additional-information"></a>Informações adicionais
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Nova experiência de tela inteira em breve no Intune <!--4593669-->
Estamos lançando experiências atualizadas do Intune para criar e editar a IU no portal do Azure. Essa nova experiência simplificará os fluxos de trabalho existentes, usando um formato de estilo de assistente condensado dentro de uma folha. Essa atualização eliminará a "expansão da folha" ou fluxos de criação e edição que exijam fazer drill down em jornadas de folha profundas. Atualizaremos também os fluxos de trabalho de criação para incluir Atribuições (exceto atribuição de aplicativo).

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A experiência de tela inteira será implantada no Intune, em portal.azure.com e devicemanagement.microsoft.com, durante os próximos meses. Essa atualização na interface do usuário não afetará a funcionalidade dos perfis e das políticas existentes, mas a aparência do fluxo de trabalho mudará ligeiramente. Por exemplo, ao criar novas políticas, você poderá definir algumas atribuições como parte desse fluxo, em vez de fazer isso após a criação da política. Confira a postagem no blog em "Informações adicionais" para ver capturas de tela com a nova aparência no console.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você não precisa fazer nada, mas é possível atualizar as diretrizes para profissionais de TI, caso necessário. Atualizaremos nossa documentação no portal do Azure, à medida que lançarmos essa experiência em várias folhas do Intune.

#### <a name="additional-information"></a>Informações adicionais 
https://aka.ms/intune_fullscreen
