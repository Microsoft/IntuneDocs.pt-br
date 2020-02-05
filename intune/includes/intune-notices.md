---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 6064fb657454106a8a7213e0bbbcecdcef765857
ms.sourcegitcommit: c7c6be3833d9a63d43f31d598b555b49b33cf5cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76966344"
---
Esses avisos fornecem informações importantes que podem ajudar você a se preparar para os recursos e as alterações futuras do Intune.

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Foi atualizada a instrução de suporte do aplicativo móvel "Adobe Acrobat Reader for Intune"<!--5746776-->
Compartilhamos no MC188653 no final de agosto, que o aplicativo móvel Adobe Acrobat Reader para Intune estava atingindo o fim da vida útil em 1º de dezembro de 2019 e que a Adobe planejava dar suporte às políticas de proteção de aplicativos do Intune no aplicativo principal Acrobat Reader. Desde então, recebemos comentários dos clientes de que precisávamos dar mais tempo para continuar a permitir que os administradores de TI direcionem e os usuários finais comecem a usar o Adobe Acrobat Reader para Intune. Devido ao alto uso do Adobe Acrobat Reader para Intune em dispositivos de usuário final e sua importância em cenários empresariais, queremos garantir que todas as experiências atendam às necessidades de proteção do aplicativo da sua organização. 

Embora ainda seja recomendável direcionar o aplicativo móvel geral do Acrobat Reader em suas políticas, já que o aplicativo móvel do Acrobat Reader oferece suporte às políticas de proteção de aplicativos e integrou o SDK do Intune, o aplicativo Adobe Acrobat Reader para Intune continuará a ter suporte até 31 de março de 2020. 

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Você está recebendo esta mensagem porque nosso relatório indica que uma ou mais políticas em sua organização estão direcionadas ao aplicativo Adobe Acrobat Reader para Intune e/ou você pode ter recebido nossa comunicação de EOL anterior. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Informe os usuários finais e o suporte técnico sobre essa alteração. Você pode usar a [funcionalidade de informações de suporte do Portal da empresa](../apps/company-portal-app.md#support-information) para estabelecer um canal de perguntas relacionadas ao Intune.

#### <a name="additional-information"></a>Informações adicionais
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="end-support-for-windows-phone-81--3544909--"></a>Fim do suporte para o Windows Phone 8.1<!--3544909-->
O suporte principal da Microsoft para o Windows Phone 8.1 foi encerrado em julho de 2017, e o suporte estendido terminou em junho de 2019. O aplicativo Portal da Empresa para Windows Phone 8.1 está no modo de manutenção desde outubro de 2017. O Microsoft Intune encerrará o suporte em 20 de fevereiro de 2020 para o Windows Phone 8.1.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Após 20 de fevereiro de 2020, esses dispositivos não receberão atualizações de segurança, e não será possível registrar nenhum dispositivo novo. Os dispositivos Windows Phone 8.1 existentes permanecerão registrados (política, aplicativos e relatórios), mas não haverá suporte para a solução de problemas de um registro existente após essa data, pois muitos componentes, como certificados de terceiros, já encerraram o suporte para a plataforma. O Intune desativará o teste de compatibilidade com o Intune e o Windows Phone 8.1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Confira o relatório do Intune para ver quais dispositivos ou usuários podem ser afetados. Acesse Dispositivos > Todos os dispositivos e filtre por sistema operacional. É possível adicionar colunas extras para ajudar a identificar quem na sua organização tem dispositivos que executam o Windows Phone 8.1. Solicite que os usuários finais atualizem os dispositivos deles para uma versão de sistema operacional com suporte.


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Tomada de ação: use o Microsoft Edge para sua experiência de navegação protegida no Intune<!--5728447-->
Conforme compartilhado durante todo o ano passado, o Microsoft Edge Mobile é compatível com o mesmo conjunto de recursos de gerenciamento que o Managed Browser, oferecendo uma experiência de usuário final muito aprimorada. No intuito de proporcionar as experiências robustas oferecidas no Microsoft Edge, o Intune Managed Browser será desativado. A partir de 27 de janeiro de 2020, o Intune não dará mais suporte ao Intune Managed Browser.  

#### <a name="how-does-this-affect-me"></a>Como isso me afeta? 
A partir de 1º de fevereiro de 2020, o Intune Managed Browser não estará mais disponível na Google Play Store nem na App Store do iOS. Nesse momento, você ainda poderá direcionar novas políticas de proteção de aplicativo para o Intune Managed Browser, embora os novos usuários não possam baixar o aplicativo Intune Managed Browser. Além disso, no iOS, os novos clipes da Web enviados para o dispositivo inscrito no MDM serão abertos no Microsoft Edge, e não no Intune Managed Browser.  

Em 31 de março de 2020, o Intune Managed Browser será removido do console do Azure. Isso significa que não será mais possível criar novas políticas para o Intune Managed Browser. Se houver políticas existentes do Intune Managed Browser em vigor, elas não serão afetadas. O Intune Managed Browser aparecerá no console como um aplicativo LOB sem ícone, e as políticas existentes serão mostradas como ainda sendo direcionadas para o aplicativo. Nesse momento, também removeremos a opção de redirecionar o conteúdo da Web para o Intune Managed Browser na seção de Proteção de Dados das Políticas de proteção do aplicativo.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração? 
Recomendamos a execução proativa das seguintes etapas para garantir uma transição tranquila do Intune Managed Browser para o Microsoft Edge: 

1. Direcione o Microsoft Edge para iOS e Android com a política de proteção de aplicativos (também conhecida como MAM) e as definições de configuração do aplicativo. As políticas do Intune Managed Browser para Microsoft Edge podem ser reutilizadas com o direcionamento delas para o Microsoft Edge.  
2. Verifique se a configuração da política de proteção de aplicativo "Restringir a transferência de conteúdo da Web com outros aplicativos" de todos os aplicativos protegidos por MAM em seu ambiente está definida como "Navegadores gerenciados por política". 
3. Direcione todos os que estiverem protegidos por MAM com o conjunto gerenciado de configuração de aplicativo "com.microsoft.intune.useEdge" definido como true. A partir do próximo mês, com o lançamento da versão 1911, será possível realizar as etapas 2 e 3 simplesmente definindo a configuração "Restringir a transferência de conteúdo da Web com outros aplicativos" para que o "Microsoft Edge" seja selecionado na seção Proteção de dados de suas políticas de proteção de aplicativo. 

Vem aí o suporte para clipes da Web no iOS e no Android. Quando esse suporte for lançado, será necessário fazer o redirecionamento dos clipes da Web pré-existentes para garantir que eles sejam abertos no Microsoft Edge em vez do Managed Browser. 

#### <a name="additional-information"></a>Informações adicionais
Consulte nossos documentos sobre o [uso do Microsoft Edge com as políticas de proteção de aplicativo](../apps/manage-microsoft-edge.md) para obter mais informações ou confira nossa [postagem no blog de suporte](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="end-of-support-for-legacy-pc-management"></a>Fim do suporte ao gerenciamento de computador herdado

O suporte ao gerenciamento de computador herdado será encerrado em 15 de outubro de 2020. Atualize os dispositivos para o Windows 10 e registre-os novamente como dispositivos MDM (Gerenciamento de Dispositivo Móvel) para mantê-los gerenciados pelo Intune.

[Saiba mais](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Redução do suporte para o administrador de dispositivos Android 
O administrador de dispositivos Android (às vezes chamado de gerenciamento Android "herdado" e lançado com o Android 2.2) é uma maneira de gerenciar dispositivos Android. No entanto, a funcionalidade de gerenciamento aprimorada já está disponível com o [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (lançado com o Android 5.0). Em um esforço para migrar para um gerenciamento de dispositivo moderno, mais avançado e mais seguro, o Google tem reduzido o suporte do administrador de dispositivos em novos lançamentos do Android.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Com essas alterações realizadas pelo Google, os usuários do Intune serão afetados das seguintes maneiras:  
- O Intune só poderá fornecer suporte completo para os dispositivos Android gerenciados pelo administrador de dispositivo que executam o Android 10 e posterior até o segundo trimestre de 2020. Os dispositivos gerenciados pelo administrador de dispositivo que executam o Android 10 ou posterior após essa data não poderão ser totalmente gerenciados. Em particular, os dispositivos afetados não receberão novos requisitos de senha.
    - Os dispositivos Samsung Knox não serão afetados nesse período, porque o suporte estendido é fornecido por meio da integração do Intune à plataforma Knox. Isso possibilita mais tempo para planejar a transição do gerenciamento de administradores de dispositivo.    
- Os dispositivos Android gerenciados pelo administrador de dispositivos que permanecerem em versões anteriores ao Android 10 não serão afetados e poderão continuar sendo totalmente gerenciados com o administrador de dispositivos.    
- Para todos os dispositivos que executam o Android 10 ou posterior, o Google restringiu a capacidade dos agentes de gerenciamento de administradores de dispositivos, como o Portal da Empresa, de acessarem as informações do identificador do dispositivo. Essa restrição afetará os seguintes recursos do Intune após a atualização de um dispositivo para o Android 10 ou posterior:  
    - O controle de acesso à rede para VPN não funcionará mais.   
    - Identificar dispositivos como propriedade corporativa com um IMEI ou número de série não marcará automaticamente os dispositivos como propriedade corporativa.  
    - O IMEI e o número de série não estarão mais visíveis para os administradores de TI no Intune. 
        > [!NOTE]
        > Isso só afetará dispositivos gerenciados pelo administrador de dispositivos no Android 10 e posterior e não afetará dispositivos gerenciados, como o Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Para evitar a redução da funcionalidade no terceiro trimestre de 2020, recomendamos o seguinte:
- Não integre novos dispositivos ao gerenciamento de administradores de dispositivos.
- Se for esperado que um dispositivo receba uma atualização para o Android 10, migre-o do gerenciamento de administradores de dispositivos para o gerenciamento do Android Enterprise e/ou de políticas de proteção de aplicativo.

#### <a name="additional-information"></a>Informações adicionais
- [Diretrizes do Google para a migração do administrador de dispositivos para o Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Documentação do Google sobre o plano para substituir a API do administrador de dispositivos](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Planejar mudanças: O SDK de Aplicativo do Intune e as políticas de proteção de aplicativo para Android estão sendo migrados para oferecer suporte ao Android 5.0 e posteriores em uma versão futura <!--4911065 -->
O Intune será migrado para oferecer suporte ao Android 5.x (Lollipop) e posteriores em uma versão futura. Atualize todos os aplicativos encapsulados com o SDK de Aplicativo do Intune mais recente e atualize seus dispositivos.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Caso você não esteja usando nem planeje usar o SDK ou Aplicativo para Android, essa alteração não afetará você. Se você estiver usando o SDK de Aplicativo do Intune, atualize para a versão mais recente e atualize também seus dispositivos para o Android 5.x e posterior. Se você não fizer a atualização, os aplicativos não receberão atualizações, e a qualidade da experiência diminuirá ao longo do tempo.

Veja abaixo uma lista de dispositivos comuns registrados no Intune que executam o Android versão 4. x. Se você tiver um destes dispositivos, siga as etapas apropriadas para garantir que ele ofereça suporte à versão 5.0 ou posterior do Android ou que seja substituído por um dispositivo com suporte à versão 5.0 ou posterior do Android. Esta lista não está completa com todos os dispositivos que precisam ser avaliados:

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

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7---3042987---"></a>Planejar mudança para o Intune: Aproximação do fim do suporte do Windows 7<!-- 3042987 -->
Após a publicação da mensagem MC148476 em setembro de 2018 e novamente na MC176794 de março de 2019, o Windows 7 encerrará o suporte estendido em 14 de janeiro de 2020. Nesse momento, o Intune desativará o suporte para dispositivos que executam o Windows 7, para que possamos concentrar nosso investimento no suporte de tecnologias mais recentes e em fornecer novas experiências ao usuário final. Após essa data, a assistência técnica e as atualizações automáticas que ajudam a proteger seu PC com Windows 7 não estarão mais disponíveis por meio do Intune. A Microsoft recomenda enfaticamente que você mude para o Windows 10 antes de janeiro de 2020, para evitar um cenário no qual você precise de um serviço ou suporte que não esteja mais disponível. Leia mais sobre o [ciclo de vida de suporte do Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Você está recebendo esta mensagem porque está gerenciando computadores com o Windows 7 usando o agente de software para computador herdado do Intune. Como falta menos de um ano para o fim do suporte estendido do Windows 7, recomendamos enfaticamente que sua organização comece a atualizar para o Windows 10 assim que possível.  

Os recursos de gerenciamento de computadores estão integrados diretamente no sistema operacional Windows 10, e você não precisa mais instalar um agente de cliente, como o software cliente do Intune para Windows 7. Desde o Windows 8.1, a Microsoft usa a arquitetura de MDM (Gerenciamento de Dispositivo Móvel) para provisionar, configurar, atualizar e gerenciar computadores com Windows. Depois de configurar o Intune, você pode simplificar o registro do Windows ao [registrar computadores com Windows 10 no Intune](..\windows-enroll.md) pelo canal MDM. Recomendamos o uso dessa solução de gerenciamento de MDM "sem agente" para gerenciar seus computadores com Windows 10.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Incentivamos sua organização a considerar imediatamente este plano de ação:

- Planeje e atualize a frota de Windows 7 para o Windows 10 antes de 14 de janeiro de 2020.
- Explore o [suporte de implantação do Windows 10](https://docs.microsoft.com/windows/deployment/) para saber mais sobre como atualizar sua frota existente de computadores com Windows 7 para o Windows 10.
- Confira a oferta da [Garantia de Aplicativo da Área de Trabalho](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) por meio do FastTrack, que ajudará na promessa de compatibilidade de aplicativos da Microsoft.
- Migre os dispositivos herdados e existentes gerenciados pelo cliente de software do Intune para a solução recomendada pela Microsoft a fim de gerenciar o Windows 10 usando o gerenciamento MDM. Registre todos os novos computadores com Windows 10 com o gerenciamento do MDM para Intune no portal do Azure.

Para obter mais informações, confira a [postagem no blog aqui](https://aka.ms/Windows7_Intune).


