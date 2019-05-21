---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: ffcef5b4d78856709f8563ee1f667ec7e5d993b3
ms.sourcegitcommit: d2e04a38e024b0f5afb0ca202823227de9da3ad1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65732596"
---
Esses avisos fornecem informações importantes que podem ajudar você a se preparar para os recursos e as alterações futuras do Intune. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Alteração no fluxo de trabalho de registro no Portal da Empresa do Intune de dispositivos iOS corporativos com autenticação no Assistente de Configuração <!-- 1927359 -->
Há uma alteração futura no fluxo de trabalho para o registro de dispositivos iOS por meio dos métodos de registro de dispositivo corporativo da Apple, tais como Apple Configurator, Apple Business Manager, Apple School Manager ou o DEP (Programa de registro de dispositivos da Apple), ao usar o Assistente de Configuração para autenticação. Essa alteração se aplica somente a dispositivos registrados com afinidade de usuário.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Quando essa alteração for distribuída, os perfis de registro no Intune no portal do Azure serão atualizados para que você possa especificar como os dispositivos são autenticados e se o usuário recebe o aplicativo Portal da Empresa. Haverá um fluxo de trabalho aperfeiçoado para registrar dispositivos iOS por meio dos métodos listados acima. 

- Ao registrar novos dispositivos e fazer a autenticação no Assistente de Configuração, você poderá escolher se deseja ou não implantar o aplicativo Portal da Empresa automaticamente. Os usuários finais não verão a tela "Identifique seu dispositivo" e a tela "Confirmar seu dispositivo" no fluxo de registro.  
- Em dispositivos já registrados por meio do Assistente de Configuração com um dos métodos de registro de dispositivo corporativo da Apple, você deve tomar providências caso deseje habilitar o Acesso Condicional. Você precisará [configurar uma política de configuração de aplicativo](https://aka.ms/enrollment_setup_assistant) com um xml específico para enviar por push o Portal da Empresa para esses dispositivos.  Se você optar por enviar por push o Portal da Empresa dessa maneira, os usuários finais não verão a tela "Identifique seu dispositivo" e a tela "Confirmar seu dispositivo" no fluxo de registro. 
- Depois que essa alteração for distribuída, se você não tiver implantado o Portal da Empresa com o perfil de configuração do aplicativo mencionado acima, e se os usuários finais baixarem o aplicativo Portal da Empresa na App Store, eles poderão entrar, mas receberão uma mensagem de erro. Eles não conseguirão usar o aplicativo para Acesso Condicional. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se você pretende usar o fluxo de trabalho modificado, convém atualizar suas diretrizes do usuário final para indicar que:

- Os usuários finais não verão mais as duas telas mencionadas acima no fluxo de registro. 
- Será necessário entrar no Portal da Empresa quando ele for implantado automaticamente, e não baixá-lo da loja de aplicativos. 

Agora você pode optar por criar uma política de configuração de aplicativo, se necessário, em preparação para essa alteração. Quando esse novo fluxo de trabalho for distribuído, você verá os perfis de registro atualizados no console. Você também será informado dessa distribuição por meio do Centro de Mensagens. Em seguida, você precisará executar a ação para que os usuários finais possam se registrar pelo DEP por meio da autenticação com o Assistente de Configuração e você possa usar o Portal da Empresa para Acesso Condicional.

#### <a name="additional-information"></a>Informações adicionais 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Atualize o aplicativo Portal da Empresa para Android para a versão mais recente <!--4536963-->
Periodicamente o Intune lança atualizações para o aplicativo Portal da Empresa para Android. Em novembro de 2018, lançamos uma atualização do Portal da Empresa, que incluiu um comutador de back-end para preparar para a alteração do Google da plataforma de notificação existente do FCM (Firebase Cloud Messaging) da Google. Quando o Google desativar a plataforma de notificação existente e migrar para o FCM, os usuários finais precisarão atualizar o aplicativo Portal da Empresa pelo menos até novembro de 2018 para continuar a se comunicar com a Google Play Store.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Nossa telemetria indica que você tem dispositivos com uma versão do Portal da Empresa anterior à 5.0.4269.0. Se esta versão ou a posterior do aplicativo Portal da Empresa não estiver instalada, pode ser que ações de dispositivo iniciadas por um profissional de TI, como limpar, redefinir senha, instalações de aplicativos disponíveis e necessárias, e registrar certificados, não funcionem como o esperado. Se os dispositivos estiverem registrado no MDM do Intune, você poderá ver os usuários e as versões do Portal da Empresa acessando os aplicativos do Cliente, aplicativos Descobertos. Selecionar versões anteriores do Portal da Empresa permitirá que você veja quais usuários finais tem os dispositivos que ainda não atualizaram o Portal da Empresa.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Peça aos usuários finais de dispositivos Android que não atualizaram para atualizar o Portal da Empresa por meio do Google Play. Notifique o suporte técnico caso um usuário não tenha mantido a atualização automática do aplicativo Portal da Empresa. Veja o link nas Informações Adicionais para saber mais sobre a plataforma do FCM do Google e a alteração.

#### <a name="additional-information"></a>Informações adicionais
https://firebase.google.com/docs/cloud-messaging/