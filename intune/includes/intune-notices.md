---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: d907c5256469e86410c9916d117d3e322d43cfc3
ms.sourcegitcommit: 2614d1b08b8a78cd792aebd2ca9848f391df8550
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67812521"
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

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Planejar mudanças: Intune passa a ser compatível com o iOS 11 e posteriores em setembro <!-- 4665342-->
Em setembro, esperamos que o iOS 13 seja lançado pela Apple. O registro do Intune, o Portal da Empresa e o Managed Browser mudarão para ser compatíveis com o iOS 11 e posteriores logo após o lançamento do iOS 13.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Desde que os aplicativos móveis do O365 sejam compatíveis com o iOS 11.0 e posteriores, isso pode não afetar você. Provavelmente você já atualizou seu sistema operacional ou dispositivos. No entanto, se você tiver algum dos dispositivos listados abaixo ou decidir registrar algum deles, saiba que eles não são compatíveis com um sistema operacional posterior ao iOS 10. Esses dispositivos precisarão ser atualizados para um dispositivo compatíveis com o iOS 11 ou posterior:

- iPhone 5
- iPhone 5c
- iPad (4ª geração)

A partir de julho, dispositivos registrados no MDM com iOS 10 e o Portal da Empresa receberão uma solicitação para atualizar seu sistema operacional ou dispositivo. Se você usar APP (Políticas de Proteção de Aplicativo), também poderá definir a configuração de acesso "Exigir o sistema de operacional iOS mínimo (somente aviso)".

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Verifique o relatório do Intune para ver quais dispositivos ou usuários podem ser afetados. Vá para **Dispositivos** > **Todos os dispositivos** e filtre por sistema operacional. É possível adicionar colunas extras para ajudar a identificar quem na sua organização tem dispositivos que executam o iOS 10. Solicite que os usuários finais atualizem seus dispositivos para uma versão de sistema operacional compatível antes de setembro.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Planejar mudanças: Compatibilidade com a versão 8.1.1 e superiores do SDK de Aplicativo do Intune para iOS <!-- 3586942-->
Começando em setembro de 2019, o Intune mudará para ser compatível com aplicativos iOS com o SDK de Aplicativo do Intune 8.1.1 e posterior. Os aplicativos criados com versões do SDK anteriores a 8.1.1 não serão mais compatíveis. Essa alteração entrará em vigor com o lançamento da Apple do iOS 13, que deve ocorrer por volta de setembro e também foi anunciado no MC181399.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Com a Integração de Encapsulamento de Aplicativo ou o SDK de Aplicativo do Intune, você pode proteger dados corporativos de aplicativos e usuários não aprovados por meio da criptografia de dados. O SDK de Aplicativo do Intune para iOS usa as chaves de criptografia de 256 bits por padrão quando a criptografia é habilitada pela APP (Políticas de Proteção de Aplicativo do Intune). Após essa alteração, quaisquer aplicativos iOS em versões do SDK anteriores à 8.1.1, que usam chaves de criptografia de 128 bits, não poderão compartilhar dados com aplicativos integrados ao SDK 8.1.1 ou usando as chaves de 256 bits. Todos os aplicativos do iOS precisarão ter um SDK versão 8.1.1 ou posterior para permitir o compartilhamento de dados protegidos.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Verifique seus aplicativos Microsoft, de terceiros e LOB (linha de negócios). Você deve garantir que todos os seus aplicativos protegidos com a APP do Intune estejam usando o SDK versão 8.1.1 ou posterior.

- Para aplicativos LOB: Pode ser necessário publicar novamente seus aplicativos integrados com o SDK versão 8.1.1 ou posterior. Recomendamos a versão mais recente do SDK. Para obter informações sobre como preparar seus aplicativos LOB para políticas de proteção de aplicativo, confira [Preparar aplicativos de linha de negócios para as políticas de proteção de aplicativos](../apps-prepare-mobile-application-management.md).
- Para aplicativos Microsoft/de terceiros: Certifique-se de que você esteja implantando a versão mais recente desses aplicativos para seus usuários.

Você também deve atualizar sua documentação ou as diretrizes do desenvolvedor, se aplicável, para incluir essa alteração na compatibilidade do SDK.

#### <a name="additional-information"></a>Informações adicionais
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Planejar mudanças: Novas configurações de atualizações do Windows no Intune <!-- 4464404 -->
A partir da versão de agosto, ou 1908, do Intune, estamos adicionando novas “configurações de prazo” que podem ser definidas como alternativa à opção “Permitir que o usuário reinicie (reinício estabelecido)”. Planejamos desabilitar as configurações de reinício estabelecido na interface do usuário na atualização de setembro, ou 1909, e removê-las completamente do console no final de outubro. 

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Se você gerencia dispositivos do Windows 10 em seu ambiente: 
- Com a atualização de agosto, ou 1908, do Intune, você verá novas configurações de prazo no console, além das configurações de reinício usadas anteriormente.
- Quando tanto as configurações antigas quanto as novas estão configuradas, os valores das configurações de prazo substituirão os de reinício estabelecido.
- As configurações de prazo substituirão a opção “Permitir que o usuário reinicie (reinício estabelecido) na atualização 1910 do console.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Comece a usar as configurações de prazo na versão 1908, configurando-as com os valores desejados. Depois de definir isso, você poderá optar pela configuração de reinício estabelecido como “Não configurado” para se preparar para sua remoção do console em outubro.

Atualize sua documentação e todos os scripts de automação, se necessário. 

Manteremos você atualizado e postaremos um lembrete na Central de mensagens antes da remoção das configurações de reinício estabelecido.
