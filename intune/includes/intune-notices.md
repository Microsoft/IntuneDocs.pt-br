---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 8db05399c4a880d72d24cde885976309bf9a4fa7
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74549351"
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
Após 20 de fevereiro de 2020, esses dispositivos não receberão atualizações de segurança, e não será possível registrar nenhum dispositivo novo. Os dispositivos Windows Phone 8.1 existentes permanecerão registrados (política, aplicativos, relatórios), mas não haverá suporte para a solução de problemas de um registro existente após essa data porque muitos componentes, como certificados de terceiros, já encerraram o suporte para a plataforma. O Intune desativará o teste de compatibilidade com o Intune e o Windows Phone 8.1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Confira o relatório do Intune para ver quais dispositivos ou usuários podem ser afetados. Acesse Dispositivos > Todos os dispositivos e filtre por sistema operacional. É possível adicionar colunas extras para ajudar a identificar quem na sua organização tem dispositivos que executam o Windows Phone 8.1. Solicite que os usuários finais atualizem os dispositivos deles para uma versão de sistema operacional com suporte.

### <a name="update-your-intune-outlook-app-protection-policies-app--2576686--"></a>Atualizar suas políticas de proteção de Aplicativo do Outlook do Intune (aplicativo)<!--2576686-->
Talvez seja necessário executar uma ação se você recebeu o MC195618 em seu Centro de Mensagens. Como compartilhado nas IDs de recurso de roteiro do Microsoft 365: 56325 e 56326, o Intune e o Outlook para iOS e Android estão lançando um suporte para limitar dados confidenciais em notificações por email e lembretes de calendário. Como resultado desses aprimoramentos, o Outlook para iOS e Android removerá o suporte para várias chaves de configuração de aplicativo de proteção de dados que você está aproveitando atualmente para gerenciar notificações.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Embora os novos recursos não tenham sido enviados, quando isso ocorrer, as seguintes chaves de configuração do aplicativo não funcionarão mais no Outlook para iOS e Android:
- com.microsoft.outlook.Mail.NotificationsEnabled
- com.microsoft.outlook.Mail.NotificationsEnabled.UserChangeAllowed
- com.microsoft.outlook.Calendar.NotificationsEnabled
- com.microsoft.outlook.Calendar.NotificationsEnabled.UserChangeAllowed

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Recomendamos que você defina a configuração de proteção de dados da Política de Proteção de Aplicativo do Intune de "Notificações de dados da organização" com um valor de "Bloquear dados da organização" em preparação para esse novo recurso. A partir de 16 de dezembro de 2019, o Outlook para iOS e Android honrará a configuração de proteção de dados de "Notificações de dados da organização" e não dará mais suporte às chaves mencionadas anteriormente. Definir essa nova configuração garantirá que os dados confidenciais não sejam vazados quando as chaves de configuração acima não tiverem mais suporte. Além disso, o Outlook fornece granularidade adicional quando a configuração de proteção de dados de "Notificações de dados da organização" é definida como "Bloquear dados da organização" com uma definição de configuração de aplicativo adicional, "Notificações de calendário". A combinação das configurações da Política de Proteção de Aplicativo e essa definição de configuração de aplicativo limita as informações confidenciais nas notificações por email, enquanto expõe informações confidenciais nas notificações de calendário, para que os usuários possam acessar suas reuniões olhando rapidamente a notificação ou o centro de notificações.

#### <a name="additional-information"></a>Informações adicionais
Confira mais informações sobre configurações do aplicativo e do Outlook em:
- [Configurações de política de proteção de aplicativo, Android](../apps/app-protection-policy-settings-android.md)
- [Configurações de política de proteção de aplicativo, iOS](../apps/app-protection-policy-settings-ios.md)
- [Implantar definições de configuração de aplicativos no Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune)


### <a name="intune-plan-for-change-windows-10-version-1703-company-portal-moving-out-of-support--5026679--"></a>Planejamento do Intune para a mudança: encerramento de suporte da versão 1703 do Portal da Empresa do Windows 10<!--5026679-->
A versão 1703 do Windows 10, também conhecido como Windows 10, RS2, saiu de serviço em 8 de outubro de 2019 para as edições Enterprise e EDU. A partir de 26 de dezembro de 2019, o Intune encerrará o suporte para o respectivo aplicativo do Portal da Empresa do RS2/RS1.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Daqui para a frente, você não verá novos recursos na versão específica do aplicativo Portal da Empresa, mas seguiremos dando suporte a ela até 26 de dezembro de 2019, o que inclui o fornecimento de todas as atualizações de segurança necessárias para o aplicativo Portal da Empresa. No entanto, como a versão 1703 do Windows 10 não receberá atualizações de segurança após sair de serviço, é altamente recomendável que você atualize seus dispositivos Windows para uma versão mais recente do Windows, e confirme que está usando o aplicativo Portal da Empresa mais recente para continuar a obter novos recursos e funcionalidades adicionais.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
As etapas executadas dependerão de como seu ambiente está configurado. No entanto, de forma geral, você deve identificar os dispositivos que têm a versão mais antiga do sistema operacional e/ou do Portal da Empresa e atualizá-los. Para configurar os anéis de atualização do Windows 10, faça logon no Intune – > Atualizações de software – anéis de atualização do Windows 10. A versão mais recente do Portal da Empresa é a 10.3.5601.0. Direcione seus usuários para baixá-la na Microsoft Store e ficarem em dia com as versões futuras. O Intune também pode ser usado para instalar a versão mais recente em seus dispositivos Windows por meio da [Microsoft Store para Empresas](https://docs.microsoft.com/intune/windows-store-for-business).

#### <a name="additional-information"></a>Informações adicionais
[Adicionar manualmente o aplicativo do Portal da Empresa ao Windows 10 usando o Microsoft Intune](https://docs.microsoft.com/intune/store-apps-company-portal-app)


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

Vem aí o suporte para clipes da Web no iOS e no Android. Quando esse suporte for lançado, será preciso fazer o redirecionamento dos clipes da Web pré-existentes para garantir que eles sejam abertos no Microsoft Edge, e não no Managed Browser. 

#### <a name="additional-information"></a>Informações adicionais
Acesse mais informações em nossos documentos sobre o [uso do Microsoft Edge com as políticas de proteção de aplicativo](../apps/manage-microsoft-edge.md) ou confira a nossa [postagem no blog de suporte](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).

### <a name="plan-for-change-updated-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--5198878--"></a>Planejar mudanças: experiência atualizada ao registrar dispositivos dedicados do Android Enterprise no Intune.<!--5198878-->
Com o lançamento da versão de novembro ou 1911 do Intune, adicionamos o suporte para a implantação de certificados de dispositivos SCEP em dispositivos Android Enterprise dedicados para habilitar o acesso baseado em certificado a perfis de Wi-Fi. Essa alteração também envolve algumas alterações secundárias no fluxo ao registrar dispositivos Android Enterprise dedicados.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Se você gerenciar dispositivos Android Enterprise dedicados em seu ambiente, começará a ver algumas alterações distribuídas em novembro.

- Para novos registros de dispositivos Android Enterprise dedicados: os usuários finais verão um conjunto diferente de etapas nos dispositivos durante o registro. O registro ainda começará da mesma forma de hoje (com um identificador QR, NFC, Zero-Touch ou de dispositivo), mas, após a versão do serviço de novembro, haverá uma etapa obrigatória de instalação de aplicativo.
- Para dispositivos Android existentes registrados como dispositivos dedicados: o Intune começará a instalar automaticamente o aplicativo Microsoft Intune nos dispositivos a partir do início de novembro. Você não precisa realizar nenhuma ação. O aplicativo será baixado e instalado automaticamente nos dispositivos. 

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você deve planejar a atualização das diretrizes do usuário final e informar a assistência técnica sobre essa alteração. Clique em Informações adicionais para obter mais detalhes e capturas de tela. Atualizaremos nossa página de Novidades quando a alteração começar a ser implantada.

#### <a name="additional-information"></a>Informações adicionais
[https://aka.ms/Dedicated_devices_enrollment](https://aka.ms/Dedicated_devices_enrollment)

### <a name="end-of-support-for-legacy-pc-management"></a>Fim do suporte ao gerenciamento de computador herdado

O suporte ao gerenciamento de computador herdado será encerrado em 15 de outubro de 2020. Atualize os dispositivos para o Windows 10 e registre-os novamente como dispositivos MDM (Gerenciamento de Dispositivo Móvel) para mantê-los gerenciados pelo Intune.

[Saiba mais](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Redução do suporte para o administrador de dispositivos Android 
O administrador de dispositivos Android (às vezes chamado de gerenciamento Android "herdado" e lançado com o Android 2.2) é uma maneira de gerenciar dispositivos Android. No entanto, a funcionalidade de gerenciamento aprimorada já está disponível com o [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (lançado com o Android 5.0). Em um esforço para migrar para um gerenciamento de dispositivo moderno, mais avançado e mais seguro, o Google tem reduzido o suporte do administrador de dispositivos em novos lançamentos do Android.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Com essas alterações realizadas pelo Google, os usuários do Intune serão afetados das seguintes maneiras:  
- O Intune só poderá fornecer suporte para dispositivos Android gerenciados pelo administrador de dispositivos que executa o Android 10 e posterior (também conhecido como Android Q) até o verão de 2020. É nessa data que a próxima versão principal do Android deverá ser lançada.   
- Dispositivos gerenciados pelo administrador de dispositivos que executarem o Android 10 ou posterior após o verão 2020 não poderão ser totalmente gerenciados.       
- Os dispositivos Android gerenciados pelo administrador de dispositivos que permanecerem em versões anteriores ao Android 10 não serão afetados e poderão continuar sendo totalmente gerenciados com o administrador de dispositivos.    
- Para todos os dispositivos que executam o Android 10 ou posterior, o Google restringiu a capacidade dos agentes de gerenciamento de administradores de dispositivos, como o Portal da Empresa, de acessarem as informações do identificador do dispositivo. Essa restrição afetará os seguintes recursos do Intune após uma atualização do dispositivo para o Android 10 ou posterior:  
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
- Migre os dispositivos gerenciados existentes de cliente de software do Intune herdados para a solução recomendada pela Microsoft para gerenciar o Windows 10 com o gerenciamento do MDM. Registre todos os novos computadores com Windows 10 com o gerenciamento do MDM para Intune no portal do Azure.

Confira a [postagem no blog aqui](https://aka.ms/Windows7_Intune) para saber mais.


