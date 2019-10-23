---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 9965c6e85173ea9958182be43b6c93d9578d534f
ms.sourcegitcommit: c2e62f1ebdf75599c8e544287123c602f0f15f2b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72749361"
---
Esses avisos fornecem informações importantes que podem ajudar você a se preparar para os recursos e as alterações futuras do Intune.

### <a name="end-of-support-for-legacy-pc-management"></a>Fim do suporte ao gerenciamento de computador herdado

O suporte ao gerenciamento de computador herdado será encerrado em 15 de outubro de 2020. Atualize os dispositivos para o Windows 10 e registre-os novamente como dispositivos MDM para mantê-los gerenciados pelo Intune.

[Saiba mais](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Redução do suporte para o administrador de dispositivos Android 
O administrador de dispositivos Android (às vezes chamado de gerenciamento Android "herdado" e lançado com o Android 2.2) é uma maneira de gerenciar dispositivos Android. No entanto, a funcionalidade de gerenciamento aprimorada já está disponível com o [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (lançado com o Android 5.0). Em um esforço para migrar para um gerenciamento de dispositivo moderno, mais avançado e mais seguro, o Google tem reduzido o suporte do administrador de dispositivos em novos lançamentos do Android.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Com essas alterações realizadas pelo Google, os usuários do Intune serão afetados das seguintes maneiras:  
- O Intune só poderá fornecer suporte para dispositivos Android gerenciados pelo administrador de dispositivos que executa o Android 10 e posterior (também conhecido como Android Q) até o verão de 2020. É nessa data que a próxima versão principal do Android deverá ser lançada.   
- Dispositivos gerenciados pelo administrador de dispositivos que executarem o Android 10 ou posterior após o verão 2020 não poderão ser totalmente gerenciados.       
- Os dispositivos Android gerenciados pelo administrador de dispositivos que permanecerem em versões anteriores ao Android 10 não serão afetados e poderão continuar sendo totalmente gerenciados com o administrador de dispositivos.    
- Para todos os dispositivos que executam o Android 10 ou posterior, o Google restringiu a capacidade dos agentes de gerenciamento de administradores de dispositivos, como o Portal da Empresa, de acessarem as informações do identificador do dispositivo. Isso afetará os seguintes recursos do Intune após uma atualização do dispositivo para o Android 10 ou posterior:  
    - O controle de acesso à rede para VPN não funcionará mais.   
    - Identificar dispositivos como propriedade corporativa com um IMEI ou número de série não marcará automaticamente os dispositivos como propriedade corporativa.  
    - O IMEI e o número de série não estarão mais visíveis para os administradores de TI no Intune. 
        > [!NOTE]
        > Isso só afetará dispositivos gerenciados pelo administrador de dispositivos no Android 10 e posterior e não afetará dispositivos gerenciados, como o Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Para evitar a redução da funcionalidade no verão de 2020, recomendamos o seguinte:
- Não integre novos dispositivos ao gerenciamento de administradores de dispositivos.
- Se for esperado que um dispositivo receba uma atualização para o Android 10, migre-o do gerenciamento de administradores de dispositivos para o gerenciamento do Android Enterprise e/ou de políticas de proteção de aplicativo.

#### <a name="additional-information"></a>Informações adicionais
- [Diretrizes do Google para a migração do administrador de dispositivos para o Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Documentação do Google sobre o plano para substituir a API do administrador de dispositivos](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Atualize o aplicativo Portal da Empresa para Android para a versão mais recente <!--4536963-->
Periodicamente, o Intune lança atualizações para o aplicativo Portal da Empresa para Android. Em novembro de 2018, lançamos uma atualização do Portal da Empresa, que incluiu um comutador de back-end para preparar para a alteração do Google da plataforma de notificação existente do FCM (Firebase Cloud Messaging) do Google. Quando o Google desativar a plataforma de notificação existente e migrar para o FCM, os usuários finais precisarão atualizar o aplicativo Portal da Empresa pelo menos até novembro de 2018 para continuar a se comunicar com a Google Play Store.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Nossa telemetria indica que você tem dispositivos com uma versão do Portal da Empresa anterior à 5.0.4269.0. Caso essa versão ou a posterior do aplicativo do Portal da Empresa não esteja instalada, pode ser que ações de dispositivo iniciadas por um profissional de TI, como limpar, redefinir senha, instalações de aplicativos disponíveis e necessárias e registrar certificados, não funcionem como o esperado. Se os dispositivos estiverem registrados no MDM do Intune, você poderá ver os usuários e as versões do Portal da Empresa acessando Aplicativos cliente — Aplicativos descobertos. Selecionar versões anteriores do aplicativo do Portal da Empresa permitirá que você veja quais usuários finais têm os dispositivos que ainda não atualizaram o aplicativo do Portal da Empresa.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Peça aos usuários finais de dispositivos Android que não fizeram a atualização para atualizar o aplicativo do Portal da Empresa por meio do Google Play. Notifique o suporte técnico caso um usuário não tenha mantido a atualização automática do aplicativo Portal da Empresa. Confira o link nas *Informações adicionais* para saber mais sobre a plataforma do FCM do Google e a alteração.

#### <a name="additional-information"></a>Informações adicionais
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-full-screen-experience-coming-to-intune---4593669--"></a>Nova experiência de tela inteira em breve no Intune <!--4593669-->
Estamos lançando experiências atualizadas do Intune para criar e editar a interface do usuário no portal do Azure. Essa nova experiência simplificará os fluxos de trabalho existentes, usando um formato de estilo de assistente condensado dentro de uma folha. Essa atualização eliminará a "expansão da folha" ou fluxos de criação e edição que exijam que você faça drill down em jornadas de folha profundas. Atualizaremos também os fluxos de trabalho de criação para incluir atribuições (exceto atribuição de aplicativo).

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A experiência de tela inteira será implantada no Intune, em portal.azure.com e devicemanagement.microsoft.com, durante os próximos meses. Essa atualização na interface do usuário não afetará a funcionalidade dos perfis e das políticas existentes, mas a aparência do fluxo de trabalho mudará ligeiramente. Por exemplo, ao criar novas políticas, você poderá definir algumas atribuições como parte desse fluxo, em vez de fazer isso após a criação da política. Confira a postagem no blog em *Informações adicionais* para ver capturas de tela com a nova aparência no console.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você não precisa fazer nada, mas é possível atualizar as diretrizes para profissionais de TI, caso necessário. Atualizaremos nossa documentação no portal do Azure, à medida que lançarmos essa experiência em várias folhas do Intune.

#### <a name="additional-information"></a>Informações adicionais 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-october---4911065---"></a>Planejar mudanças: O SDK de Aplicativo do Intune as políticas de proteção de aplicativo para Android estão sendo migrados para oferecer suporte ao Android 5.0 e posterior em outubro <!--4911065 -->
O Intune será migrado para oferecer suporte ao Android 5.x (Lollipop) e posterior em outubro. Atualize todos os aplicativos encapsulados com o SDK de Aplicativo do Intune mais recente e atualize seus dispositivos.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Caso você não esteja usando nem planeje usar o SDK ou Aplicativo para Android, essa alteração não afetará você. Se você estiver usando o SDK de Aplicativo do Intune, atualize para a versão mais recente e atualize também seus dispositivos para o Android 5.x e posterior. Se você não fizer a atualização, os aplicativos não receberão atualizações e a qualidade da experiência diminuirá ao longo do tempo.

Veja abaixo uma lista de dispositivos comuns registrados no Intune que executam o Android versão 4. x. Se você tiver um destes dispositivos, siga as etapas apropriadas para garantir que ele ofereça suporte à versão 5.0 ou posterior do Android ou que seja substituído por um dispositivo com suporte à versão 5.0 ou posterior do Android. Esta lista não abrange todos os dispositivos que precisam ser avaliados:

- Samsung SM-T561  
- Samsung SM-T365
- Samsung GT-I9195
- Samsung SM-G800F
- Samsung SM-G357FZ
- Motorola XT1080
- Samsung GT-I9305
- Samsung SM-T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Encapsule seus aplicativos com o SDK de Aplicativo do Intune mais recente. Você também pode definir a configuração de inicialização condicional "Exigir versão mínima do sistema operacional (somente aviso)" para notificar os usuários finais sobre dispositivos pessoais que serão atualizados.

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7----3042987---"></a>Planejar mudança para o Intune: Aproximação do fim do suporte do Windows 7 <!-- 3042987 -->
Após a publicação da mensagem MC148476 em setembro de 2018 e novamente na MC176794 de março de 2019, o Windows 7 encerrará o suporte estendido em 14 de janeiro de 2020. Nesse momento, o Intune desativará o suporte para dispositivos que executam o Windows 7, para que possamos concentrar nosso investimento no suporte de tecnologias mais recentes e em fornecer novas experiências ao usuário final. Após essa data, a assistência técnica e as atualizações automáticas que ajudam a proteger seu PC com Windows 7 não estarão mais disponíveis por meio do Intune. A Microsoft recomenda enfaticamente que você mude para o Windows 10 antes de janeiro de 2020, para evitar um cenário no qual você precise de um serviço ou suporte que não esteja mais disponível. Leia mais sobre o [ciclo de vida de suporte do Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Você está recebendo esta mensagem porque está gerenciando computadores com o Windows 7 usando o agente de software para computador herdado do Intune. Como falta menos de um ano para o fim do suporte estendido do Windows 7, recomendamos enfaticamente que sua organização comece a atualizar para o Windows 10 assim que possível.  

Os recursos de gerenciamento de computadores estão integrados diretamente no sistema operacional Windows 10, e você não precisa mais instalar um agente de cliente, como o software cliente do Intune para Windows 7. Desde o Windows 8.1, a Microsoft usa a arquitetura de MDM (Gerenciamento de Dispositivo Móvel) para provisionar, configurar, atualizar e gerenciar computadores com Windows. Depois de configurar o Intune, você pode simplificar o registro do Windows ao [registrar computadores com Windows 10 no Intune](..\windows-enroll.md) pelo canal MDM. Recomendamos o uso dessa solução de gerenciamento de MDM "sem agente" para gerenciar seus computadores com Windows 10.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Incentivamos sua organização a considerar imediatamente este plano de ação:

- Planeje e atualize a frota de Windows 7 para o Windows 10 antes de 14 de janeiro de 2020.
- Explore o [suporte de implantação do Windows 10](https://docs.microsoft.com/windows/deployment/) para saber mais sobre como atualizar sua frota existente de computadores com Windows 7 para o Windows 10.
- Confira a oferta da [Garantia de Aplicativo da Área de Trabalho](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) por meio do FastTrack, que ajudará na promessa de compatibilidade de aplicativos da Microsoft.
- Migre os dispositivos gerenciados existentes de cliente de software do Intune herdados para a solução recomendada pela Microsoft para gerenciar o Windows 10 com o gerenciamento do MDM. Registre todos os novos computadores com Windows 10 com o gerenciamento do MDM para Intune no portal do Azure.

Confira a [postagem no blog aqui](https://aka.ms/Windows7_Intune) para saber mais.
