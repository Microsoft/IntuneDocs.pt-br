---
title: Novidades do Microsoft Intune nos meses anteriores
titlesuffix: 
description: "Veja comunicados mais antigos da página de novidades do Intune"
keywords: 
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ba6262c1126a421f2e2ca0e5085796c11df8d9a
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Novidades do Microsoft Intune – meses anteriores

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="october-2017"></a>Outubro de 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>O número de versão do aplicativo de linha de negócios Android e iOS é visível <!-- 1380712 -->

Aplicativos no Intune agora exibem o número de versão para aplicativos de linha de negócios iOS e Android. O número é exibido no portal do Azure na lista de aplicativos e na folha de visão geral do aplicativo. Os usuários finais podem ver o número do aplicativo no aplicativo do Portal da Empresa e no portal da web.

__Número de versão completo__ O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800)

O número de versão completa tem dois componentes:

 - **Versão**  
   O número de versão é o número de versão legível do aplicativo. Isso é usado pelos usuários finais para identificar versões diferentes do aplicativo.

 - **Número de build**  
    O número de build é um número interno que pode ser usado na detecção do aplicativo e para gerenciar o aplicativo de forma programática. O número de build se refere a uma iteração do aplicativo que referencia alterações no código.

Saiba mais sobre os números de versão e desenvolvimento de aplicativos de linha de negócios em [Introdução ao SDK de Aplicativo do Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integração do gerenciamento de dispositivos e aplicativos <!-- 677972 -->   
Agora que o gerenciamento de dispositivo móvel do Intune (MDM) e o gerenciamento de aplicativo móvel (MAM) são ambos acessíveis do portal do Azure, o Intune começou integrar a experiência de administração de TI em torno do gerenciamento de aplicativo e dispositivo. Essas alterações têm o objetivo de simplificar seu dispositivo e a experiência de gerenciamento de aplicativo.

Saiba mais sobre as alterações de MDM e MAM anunciadas no [blog da equipe de suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Novos alertas de registro para dispositivos Apple <!-- 1471790 -->
A página de visão geral de registro mostrará alertas úteis para administradores de TI sobre o gerenciamento de dispositivos Apple. Os alertas serão exibido na página Visão geral de quando o certificado de push de MDM da Apple estiver expirando ou já tiver expirado; quando o token do Programa de Registro de Dispositivos estiver expirando ou já tiver expirado; e quando houver dispositivos não atribuídos no Programa de Registro de Dispositivo.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Substituição do token de suporte para a configuração de aplicativo sem registro de dispositivo <!-- 1080364 -->

Você pode usar tokens de valores dinâmicos nas configurações de aplicativo para aplicativos em dispositivos que não estão registrados. Para obter mais informações, consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Atualizações para o aplicativo Portal da Empresa para Windows 10 <!--1299474-->
A página Configurações no aplicativo Portal da Empresa para Windows 10 foi atualizada para tornar as configurações e as ações de usuário pretendidas mais consistentes em todas as configurações. Ela também foi atualizada para corresponder ao layout de outros aplicativos do Windows. Encontre imagens de antes/depois na página [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para dispositivos com Windows 10 <!--1337920-->
Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para Windows 10. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela **Sobre**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Solicitações de comentários para o aplicativo Portal da Empresa para Android <!--1165249-->
O aplicativo Portal da Empresa para Android agora solicita comentários do usuário final. Estes comentários são enviados diretamente para a Microsoft e fornecem aos usuários finais uma oportunidade de avaliar o aplicativo na loja pública do Google Play. Os comentários não são obrigatórios, e podem ser ignorados facilmente para que os usuários possam continuar usando o aplicativo.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ajudando seus usuários com o aplicativo de Portal da Empresa para Android <!-- 1573324, 1573150, 1558616, 1564878 -->

O aplicativo de Portal da Empresa para Android adicionou instruções para os usuários finais a fim de ajudá-los a compreender e, quando possível, resolver automaticamente novos casos de uso.
- Os usuários finais serão direcionados para o [Portal do Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) para remover um dispositivo se tiverem atingido o número máximo de dispositivos que eles têm permissão para adicionar.
- Os usuários finais recebem etapas a serem seguidas para ajudá-los a [corrigir erros de ativação em dispositivos Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) ou a [desligar o modo de economia de energia](/intune-user-help/power-saving-mode-android). Se nenhuma dessas soluções resolver o problema, fornecemos uma explicação de como [enviar logs para a Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nova ação “Resolver” disponível para dispositivos Android <!-- 1583480 -->

O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android atualmente dá suporte a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indicador de progresso de configuração do dispositivo no Portal da Empresa para Android <!-- 1565657 -->
O aplicativo Portal da Empresa para Android mostra um indicador de progresso de configuração do dispositivo quando o usuário estiver inscrevendo seu dispositivo. O indicador mostra novos status, começando com "Configurando seu dispositivo...", depois "Registrando seu dispositivo..." e "Concluindo o registro de seu dispositivo...", em seguida, "Concluindo a configuração de seu dispositivo...".

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Suporte à autenticação baseada em certificado no Portal da Empresa para iOS <!--1029830-->
Adicionamos suporte para autenticação baseada em certificado (CBA) no aplicativo do Portal da Empresa para iOS. Os usuários com CBA inserem seus nomes de usuário, em seguida, tocam no link "Entrar com um certificado". O CBA já é compatível com os aplicativos do Portal da Empresa para Android e Windows. Você pode obter mais informações na página [entrar no aplicativo do Portal da Empresa](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->

Os aplicativos da empresa que foram disponibilizados com ou sem o registro no aplicativo do Portal da Empresa Android agora podem ser instalados sem um aviso de registro.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Suporte ao programa Windows AutoPilot Deployment no Microsoft Intune  <!-- 747617  -->
Agora você pode usar o Microsoft Intune com o programa Windows AutoPilot Deployment para capacitar os usuários a provisionarem dispositivos corporativos sem envolver TI. Você pode personalizar a OOBE (configuração inicial pelo usuário) e orientar os usuários a ingressarem seus dispositivos no Azure AD e a se registrarem no Intune. Trabalhando juntos, o Microsoft Intune e o Windows AutoPilot eliminam a necessidade de implantar, manter e gerenciar imagens do sistema operacional. Para obter detalhes, consulte [Enroll Windows devices using Windows AutoPilot Deployment Program](https://docs.microsoft.com/intune/enrollment-autopilot) (Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment).

### <a name="quick-start-for-device-enrollment-----1425655---"></a>Início rápido para o registro de dispositivo  <!-- 1425655 --> 
O início rápido agora está disponível para o **Registro de dispositivo** e fornece uma tabela de referências para gerenciamento de plataformas e a configuração do processo de registro. Uma breve descrição de cada item e links para a documentação com instruções passo a passo fornece uma documentação útil para simplificar a introdução.

### <a name="device-categorization----1427491---"></a>Categorização de dispositivo <!-- 1427491 -->
O gráfico de plataforma de dispositivos registrados da folha **Dispositivos > Visão geral** organiza os dispositivos pela plataforma, incluindo Windows Mobile, Windows, macOS, iOS e Android.  Os dispositivos que executam outros sistemas operacionais são agrupados em "Outros".  Isso inclui dispositivos fabricados pela Blackberry, NOKIA e outras.  

Para saber quais dispositivos são afetados em seu locatário, escolha **Gerenciar > Todos os dispositivos** e, em seguida, use **Filtrar** para limitar o campo **SO**.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Novo parceiro de Defesa contra Ameaças Móveis   <!-- 954681 -->  
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Zimperium, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como funciona a integração com o Intune
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Zimperium. Você pode configurar políticas de acesso condicional de EMS com base na avaliação de risco do Zimperium habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade a recursos corporativos com base em ameaças detectadas.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10  <!--- 978575, 1308849, -->  
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Suporte remoto para dispositivos Windows e Windows Mobile   <!-- 1070473 -->  
O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, que permite dar assistência remota a usuários que executam dispositivos Windows e Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Verificar dispositivos com o Windows Defender <!-- 1280988  1280990   -->
Agora você pode executar uma **Verificação rápida**, uma **Verificação completa** e **Atualizar assinaturas** com o Windows Defender Antivírus em dispositivos Windows 10 gerenciados. Na folha de visão geral do dispositivo, escolha a ação a ser executada no dispositivo. Você precisará confirmar a ação antes de o comando ser enviado ao dispositivo. 

**Verificação rápida**: uma verificação rápida examina os locais onde o malware registra-se para começar, como as chaves do Registro e pastas de inicialização conhecidas do Windows. Uma verificação rápida demora cerca de cinco minutos. Combinada com a configuração **Proteção sempre em tempo real**, que examina os arquivos quando eles são abertos, fechados e sempre que um usuário navega até uma pasta, uma verificação rápida ajuda a fornecer proteção contra malware que pode estar no sistema ou no kernel. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Verificação completa**: uma verificação completa pode ser útil em dispositivos que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa, e é útil para executar verificações sob demanda. A verificação completa pode demorar uma hora. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Atualizar assinaturas**: o comando para atualizar assinatura atualiza as definições e assinaturas de malware do Windows Defender. Isso ajuda a garantir o que Windows Defender Antivírus seja eficaz na detecção de malware. Esse recurso destina-se somente a dispositivos com Windows 10, com conectividade de internet pendente no dispositivo. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>O botão Habilitar/Desabilitar foi removido da página Autoridade de certificação do Intune do Portal do Azure do Intune  <!-- 1400455 -->
 Estamos eliminando uma etapa extra da configuração do Certificate Connector no Intune. No momento, você pode baixar o Certificate Connector e habilitá-lo no console do Intune. No entanto, se você desabilitar o conector no console do Intune, o conector continuará a emitir certificados.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A partir de outubro, o botão Habilitar/Desabilitar não aparecerá mais na página Autoridade de certificação no Portal do Azure. A funcionalidade do conector permanece a mesma. Os certificados ainda são implantados nos dispositivos registrados no Intune. Você ainda pode baixar e instalar o Certificate Connector. Para interromper a emissão de certificados, agora você pode desinstalar o Certificate Connector em vez de desabilitá-lo.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se o Certificate Connector já estiver desabilitado, você deverá desinstalá-lo.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10 Team   <!--- 1308838 -->
Nesta versão, foram adicionadas várias novas configurações ao perfil de restrição de dispositivo do Windows 10 Team para ajudar a controlar dispositivos do Surface Hub.

Para saber mais sobre esse perfil, veja [Configurações de restrição de dispositivo do Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Impedir que os usuários de dispositivos com Android alterem a data e a hora de seus dispositivos <!-- 1333292 -->
Use uma [política de dispositivo personalizada do Android](custom-settings-android.md) para impedir que os usuários de dispositivos com Android alterem a data e a hora do dispositivo.

Para fazer isso, configure uma política personalizada do Android com o URI de configuração ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Defina isso como **TRUE** e, em seguida, atribua-o aos grupos necessários.

### <a name="bitlocker-device-configuration----1397398---"></a>Configuração de dispositivo do BitLocker <!-- 1397398 -->
A seção **Criptografia do Windows > Configurações Base** inclui uma nova configuração **Aviso para criptografia de outro disco** que permite que você desabilite o [prompt de aviso](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) para a criptografia de outro disco que possa estar em uso no dispositivo do usuário.  A mensagem de aviso exige o consentimento do usuário final antes de instalar o BitLocker no dispositivo e bloqueia a instalação do BitLocker até receber a confirmação do usuário final.  A nova configuração desabilita o aviso ao usuário final.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Os aplicativos do Volume Purchase Program for Business agora serão sincronizadas ao seu locatário do Intune <!-- 800882 -->  
Os desenvolvedores de terceiros podem distribuir aplicativos de forma privada para membros autorizados do VPP (Volume Purchase Program) for Business especificados no iTunes Connect. Esses membros do VPP for Business podem entrar na App Store do Volume Purchase Programa e adquirir seus aplicativos.

Com esta versão, os aplicativos do VPP for Business comprados pelo usuário final passarão a ser sincronizados com seus locatários do Intune.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Selecione o país da loja da Apple para sincronização de aplicativos VPP<!-- 1332311 -->  
Você pode configurar o país da loja do VPP (Programa de Compra por Volume) ao carregar seu token de VPP. O Intune sincroniza aplicativos VPP para todas as localidades da loja VPP especificada de um país.

> [!NOTE]  
> Atualmente, o Intune sincroniza apenas aplicativos VPP da loja VPP que correspondem à localidade do Intune na qual o locatário do Intune foi criado.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquear a ação de copiar e colar entre perfis de trabalho e pessoais no Android for Work <!-- 1098994 -->
Com esta versão, é possível configurar o perfil de trabalho para Android for Work para bloquear a ação de copiar e colar entre aplicativos pessoais e de trabalho. Encontre essa nova configuração no perfil **Restrições de dispositivo** para a plataforma **Android for Work** em **Configurações de perfil de trabalho**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Criar aplicativos iOS limitados a Apple App Stores regionais específicas <!-- 1281692 -->
Você poderá especificar a localidade do país durante a criação de um aplicativo gerenciado da Apple App Store.

> [!Note]  
> No momento, você só pode criar aplicativos gerenciados da Apple App Store que estão presentes na loja dos Estados Unidos.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Atualizar usuário VPP do iOS e os aplicativos de dispositivo licenciados <!-- 1305564 -->  
Você poderá configurar o token de VPP do iOS para atualizar todos os aplicativos comprados para esse token por meio do serviço Intune. O Intune detectará as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará automaticamente ao dispositivo quando o dispositivo fizer check-in.

Para obter as etapas para definir um token do VPP e habilitar as atualizações automáticas, consulte [Como gerenciar aplicativos iOS comprados por meio de um Volume Purchase Program com o Microsoft Intune] (/intune/vpp-aplicativos-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->
Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Examinar a conformidade da política para anéis de atualização do Windows 10 <!-- 1067886 -->
Você poderá examinar um relatório da política de seus grupos de atualização do Windows 10 em Atualizações de software > Por estado de implantação do grupo de atualização. O relatório da política inclui o status da implantação para os anéis de atualização que você configurou. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** está disponível no espaço de trabalho **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Exibir as atribuições de política de proteção do aplicativo para solução de problemas <!--  1475003 -->
Nesta versão futura, a opção de **Política de proteção do aplicativo** será adicionada à lista suspensa **Atribuições** disponível na folha de solução de problemas. Agora você pode selecionar as políticas de proteção do aplicativo para ver as políticas de proteção de aplicativo atribuídas aos usuários selecionados.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Melhorias no fluxo de trabalho de configuração de dispositivo no Portal da Empresa <!--1490692-->
Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para Android. A linguagem é mais fácil de usar e mais específica para sua empresa e combinamos as telas sempre que possível. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Melhor orientação sobre a solicitação de acesso aos contatos em dispositivos Android <!--1484985-->

O aplicativo de Portal da Empresa para Android normalmente exige que o usuário final aceite a permissão de Contatos. Se um usuário final recusar esse acesso, ele verá uma notificação no aplicativo que o alerta para conceder a permissão para acesso condicional. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Correção de inicialização segura para Android <!--1490712-->

Os usuários finais com dispositivos Android poderão tocar no motivo da não conformidade no aplicativo do Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Notificações por push adicionais para usuários finais no aplicativo Portal da Empresa para Android Oreo <!--1475932-->

Os usuários finais verão notificações adicionais para indicar a eles quando o aplicativo Portal da Empresa para Android Oreo estiver executando tarefas em segundo plano, como recuperação de políticas do serviço Intune. Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas em seu dispositivo. Isso faz parte da [otimização geral da interface do usuário do Portal da Empresa](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) para o aplicativo Portal da Empresa para Android Oreo. 

Há mais otimizações para novos elementos de interface do usuário que estão habilitados no Android Oreo.  Os usuários finais verão notificações adicionais que indicarão a eles quando o Portal da Empresa estiver executando tarefas em segundo plano, tais como recuperação das políticas do serviço Intune.  Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas no dispositivo deles.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho<!-- 1485783 -->

Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. 

Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->

A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Bloquear o registro de dispositivo Samsung Knox sem suporte <!-- 1490695 -->

O aplicativo Portal da Empresa tenta registrar apenas os dispositivos Samsung Knox com suporte. Para evitar erros de ativação de Knox que impedem o registro do MDM, o registro do dispositivo será tentado somente se ele aparecer na [lista de dispositivos publicada pela Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Os dispositivos Samsung podem ter números de modelo que oferecem suporte a Knox, enquanto outros não. Verifique a compatibilidade com KNOX com o revendedor do dispositivo antes de adquirir e implantar. Você pode encontrar a lista completa de dispositivos verificados nas [configurações de política do Android e Samsung Knox Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Fim do suporte para Android 4.3 e inferior <!-- 1171126, 1326920 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informar aos usuários finais quais informações de dispositivo podem ser vistas em dispositivo registrados <!--1165314-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo em todos os aplicativos Portal da Empresa. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente do artigo [Quais informações sua empresa pode ver?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Isso será distribuído em todos os aplicativos de Portal da Empresa em um futuro próximo. Anunciamos isso para iOS em [setembro](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).

## <a name="september-2017"></a>Setembro de 2017

### <a name="intune-supports-ios-11---1428975--"></a>O Intune dá suporte ao iOS 11 <!--1428975-->
O Intune dá suporte ao iOS 11. Isso foi anunciado anteriormente no [blog de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!-- 1164477 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->
O aplicativo Portal da Empresa para Windows 10 permite que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para iOS <!--739894-->

Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para iOS. Isso permitirá que os usuários obtenham mais informações sobre privacidade diretamente a partir desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela Sobre.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Permitir que os usuários finais acessem o aplicativo de Portal da Empresa para Android sem registro <!---1169910--->

Em breve, os usuários finais não precisarão registrar seu dispositivo para acessar o aplicativo de Portal da Empresa para Android. Os usuários finais em organizações que estão usando as Políticas de Proteção de Aplicativo deixarão de receber solicitações para registrar seu dispositivo quando abrirem o aplicativo de Portal da Empresa. Os usuários finais também poderão instalar aplicativos do Portal da Empresa sem registrar o dispositivo. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Frases mais fáceis de entender para o aplicativo Portal da Empresa para Android <!---1396349--->  

O processo de inscrição para o aplicativo Portal da Empresa para Android foi simplificado com o novo texto a fim de facilitar a inscrição dos usuários. Se você tiver a documentação de inscrição personalizada, atualize-o para refletir as novas telas. Você pode encontrar as imagens de amostra na nossa página [Atualizações da interface do usuário para aplicativos de usuário final do Intune](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Aplicativo Portal da Empresa do Windows 10 adicionado à política de permissão da Proteção de Informações do Windows <!-- 677129 -->

O aplicativo Portal da Empresa do Windows 10 foi atualizado para dar suporte à WIP (Proteção de Informações do Windows). O aplicativo pode ser adicionado à política de permissão do WIP. Com essa alteração, o aplicativo não precisa mais ser adicionado à lista **Isento**.


## <a name="august-2017"></a>Agosto de 2017

### <a name="improvements-to-device-overview----1404453---"></a>Melhorias na visão geral de dispositivos <!-- 1404453 -->  
Com as melhorias, agora a visão geral de dispositivos exibe os dispositivos registrados, mas exclui os dispositivos gerenciados pelo Exchange ActiveSync. Os dispositivos do Exchange ActiveSync não têm as mesmas opções de gerenciamento que os dispositivos registrados. Para exibir o número de dispositivos registrados e o número de dispositivos registrados por plataforma no Intune, no portal do Azure, acesse **Dispositivos** > **Visão geral**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Melhorias no inventário de dispositivos coletado pelo Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
Nesta versão, fizemos as seguintes melhorias nas informações de inventário coletadas para cada um dos dispositivos que você gerencia:
 
-   Para dispositivos Android, agora você pode adicionar uma coluna no inventário de dispositivos que mostra o nível de patch mais recente para cada dispositivo. Adicione a coluna **Nível de patch de segurança** à sua lista de dispositivos para ver essa informação.
-   Ao filtrar a exibição de dispositivos, agora você pode filtrar os dispositivos pela data de registro. Por exemplo, você pode exibir somente os dispositivos que foram registrados após uma data especificada.
-   Fizemos melhorias no filtro usado pelo item **Última data de check-in**.
-   Na lista de dispositivos, agora você pode exibir o número de telefone dos dispositivos corporativos.
Além disso, você pode usar o painel de filtro para pesquisar dispositivos por número de telefone.
 
Para obter mais detalhes sobre o inventário de dispositivos, consulte [Como exibir o inventário de dispositivo do Intune](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Suporte a acesso condicional para dispositivos macOS 
<!-- 720172 -->
Agora você pode definir uma política de acesso condicional que requer que os dispositivos Mac sejam registrados no Intune e estejam em conformidade com as políticas de conformidade de dispositivo. Por exemplo, os usuários podem baixar o aplicativo de Portal da Empresa Intune para macOS e registrar seus dispositivos Mac no Intune. O Intune avaliar se o dispositivo Mac está em conformidade ou não com requisitos como PIN, criptografia, versão do sistema operacional e integridade do sistema.

- Saiba mais sobre [suporte a acesso condicional para dispositivos macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>O aplicativo Portal da Empresa para macOS está em visualização pública <!---1484796--->
O aplicativo Portal da Empresa para macOS agora está disponível como parte da visualização pública para acesso condicional no Enterprise Mobility + Security. Essa versão é compatível com macOS 10.11 e superior. Obtenha-a em [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Novas configurações de restrição de dispositivo para Windows 10    
<!--1063965, 1308850  -->
Nesta versão, adicionamos novas configurações no [perfil de restrição de dispositivo Windows 10](/intune/device-restrictions-windows-10) nas seguintes categorias:

-   Windows Defender SmartScreen
-   Loja de aplicativos

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Atualizações no perfil de dispositivo de Endpoint Protection do Windows 10 para configurações do BitLocker
<!--1459533 -->    
Nesta versão, fizemos as seguintes melhorias no modo de funcionamento das configurações do BitLocker em um perfil de dispositivo de Endpoint Protection do Windows 10:
 
Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **BitLocker com chip do TPM não compatível**, anteriormente, quando você selecionava **Bloquear**, na verdade, o BitLocker era permitido. Agora isso foi corrigido para bloquear o BitLocker quando essa opção está selecionada.
Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **Agente de recuperação de dados baseada em certificado**, agora você pode bloquear explicitamente o agente de recuperação de dados baseada em certificado. No entanto, por padrão, o agente é permitido.
Em **Configurações de unidade de dados fixa do BitLocker**, na configuração **Agente de recuperação de dados**, agora você pode bloquear explicitamente o agente de recuperação de dados.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nova experiência conectada para usuários do Portal da Empresa para Android e para usuários da Política de Proteção de Aplicativo <!-- 621669 -->
Os usuários finais agora podem procurar aplicativos, gerenciar dispositivos e exibir as informações de contato de TI usando o aplicativo Portal da Empresa Android sem inscrever os respectivos dispositivos Android. Além disso, se um usuário final já usa um aplicativo protegido pelas Políticas de Proteção de Aplicativo do Intune, ele não recebe mais uma solicitação para registrar o dispositivo ao iniciar o Portal da Empresa para Android.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nova configuração no aplicativo Portal da Empresa para Android para ativar/desativar a otimização de bateria <!--1405990-->
A página **Configurações** no aplicativo Portal da Empresa para Android tem uma nova configuração que permite que os usuários desliguem facilmente a otimização da bateria para os aplicativos Portal da Empresa e Microsoft Authenticator. O nome do aplicativo mostrado na configuração variará dependendo de qual aplicativo gerencia a conta de trabalho. É recomendável que os usuários desliguem a otimização da bateria para melhorar o desempenho dos aplicativos de trabalho que sincronizam dados e emails. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Suporte a várias identidades do OneNote para iOS <!-- 1234281 -->
Os usuários finais agora podem usar contas diferentes (trabalho e pessoal) com o Microsoft OneNote para iOS. As políticas de proteção de aplicativo podem ser aplicadas aos dados corporativos em blocos de anotações de trabalho sem afetar os blocos de anotações pessoais. Por exemplo, uma política pode permitir que um usuário localize informações em blocos de anotações de trabalho, mas impedirá que o usuário copie e cole dados corporativos do bloco de anotações de trabalho para um bloco de anotações pessoal.
 
- Saiba mais sobre os aplicativos que dão suporte à [proteção de aplicativo e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Novas configurações para permitir e bloquear aplicativos em dispositivos Samsung Knox Standard
<!-- 1305423 822899-->  
Nessa versão, estamos adicionando novas [configurações de restrições de dispositivo](device-restrictions-android.md) que permitem especificar as seguintes listas de aplicativo:
 
- Aplicativos que os usuários têm permissão para instalar
- Aplicativos que os usuários são impedidos de executar
- Aplicativos que ficam ocultados do usuário no dispositivo
 
Você pode especificar o aplicativo por URL, nome de pacote ou na lista de aplicativos gerenciados.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link da nova interface do usuário da política de acesso condicional com base no aplicativo do Azure AD no Intune
<!-- 1016201 -->
Agora os administradores de TI podem definir políticas condicionais com base no aplicativo por meio da nova interface do usuário de política de acesso condicional na carga de trabalho do Azure AD. O acesso condicional com base no aplicativo na seção Proteção de Aplicativo do Intune no Portal do Azure por enquanto continuará lá e a implementação será feita em conjunto. Também há um link de conveniência para a nova interface do usuário da política de acesso condicional na carga de trabalho do Intune.

- Saiba mais sobre o [acesso condicional com base no aplicativo no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## <a name="july-2017"></a>Julho de 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restringir a restrição de registro de dispositivo Android e iOS por versão do sistema operacional  <!--- 1333256,  1245463 --->
O Intune agora dá suporte à restrição do registro de iOS e Android por número de versão do sistema operacional. Agora, em **Restrição de Tipo de Dispositivo**, o administrador de TI pode definir uma configuração de plataforma para restringir o registro entre os valores mínimo e máximo do sistema operacional. As versões do sistema operacional Android devem ser especificadas como Major.Minor.Build.Rev, em que Minor, Build e Rev são opcionais. Versões do iOS devem ser especificadas como Major.Minor.Build, em que Minor e Build são opcionais. Saiba mais sobre as [restrições de registro de dispositivo](enrollment-restrictions-set.md).

>[!NOTE]
>Não restringe o registro por meio dos programas de registro da Apple ou do Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Restringir o registro de dispositivos de pessoais Android, iOS e macOS  <!--- 1333272,  1333275, 1245709 --->
O Intune pode restringir o registro de dispositivos pessoais colocando em uma lista de permissões os números IMEI dos dispositivos corporativos. Agora, o Intune expandiu essa funcionalidade para iOS, Android e macOS usando os números de série do dispositivo. Ao carregar os números de série para o Intune, você pode pré-declarar os dispositivos como corporativos. Usando as restrições de registro, você pode bloquear dispositivos pessoais (BYOD), permitindo somente o registro de dispositivos corporativos. Saiba mais sobre as [restrições de registro de dispositivo](enrollment-restrictions-set.md).

Para importar os números de série, acesse **Registro de dispositivo** > **Identificadores de dispositivo corporativo**, clique em **Adicionar** e, em seguida, carregue um arquivo .CSV (sem cabeçalho, duas colunas de número de série e detalhes como números IMEI).  Para restringir os dispositivos pessoais, acesse **Registro de dispositivo** > **Restrições de registro**. Em **Restrições de tipo de dispositivo**, selecione o **Padrão** e, em seguida, escolha **Configurações da Plataforma**. Você pode **Permitir** ou **Bloquear** dispositivos pessoais para iOS, Android e macOS. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nova ação de dispositivo para forçar os dispositivos a sincronizarem com o Intune <!-- 711369 -->
Nessa versão, adicionamos uma nova ação de dispositivo que força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.
Para ver mais detalhes, consulte [Sincronizar o dispositivo](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível <!-- 777100 -->
Uma nova política está disponível no espaço de trabalho Atualizações de software, em que você pode forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Para obter detalhes, consulte [Configurar políticas de atualização do iOS](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – Novo parceiro de Defesa contra Ameaças Móveis  <!-- 954651, 1172027 -->
É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional baseado na avaliação de risco realizada pelo Checkpoint SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como a integração com o Intune funciona?
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Checkpoint SandBlast Mobile. É possível configurar políticas de acesso condicional de EMS com base na avaliação de risco do Checkpoint SandBlast Mobile habilitada por meio das políticas de conformidade de dispositivo do Intune. Você pode permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base nas ameaças detectadas.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Implantar um aplicativo como ele está disponível na Microsoft Store para Empresas <!-- 748101 -->
Com essa versão, os administradores agora podem atribuir o Microsoft Store para Empresas como ele está disponível. Quando definido como disponível, os usuários finais podem instalar o aplicativo do site ou do aplicativo do Portal da Empresa sem serem redirecionados para a Microsoft Store.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 1-->
Fizemos várias atualizações na interface do usuário do [site Portal da Empresa](https://portal.manage.microsoft.com) para aprimorar a experiência do usuário final.

- __Aprimoramentos para blocos de aplicativos__: os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente com base na cor dominante do ícone (caso seja possível detectá-la). Quando aplicável, essa tela de fundo substituirá a borda cinza que era visível anteriormente em blocos de aplicativos.

    O site do Portal da Empresa exibe ícones grandes sempre que possível em uma versão futura. É recomendável que os administradores de TI publiquem aplicativos usando ícones de alta resolução com um tamanho mínimo de 120x120 pixels. 

- __Alterações de navegação__: os itens da barra de navegação foram movidos para o menu hambúrguer na parte superior esquerda. A página Categorias foi removida. Os usuários agora podem filtrar o conteúdo por categoria durante a navegação.

- __Atualizações para os Aplicativos em Destaque__: adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque da página inicial.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Suporte para iBooks no site do Portal da Empresa <!--1231841-->
Adicionamos uma página dedicada ao site do Portal da Empresa que permite aos usuários procurar e baixar iBooks. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Detalhes adicionais da solução de problemas de suporte técnico <!---  Applies to 1263399, 1326964, 1341642 --->
O Intune atualizou a exibição de solução de problemas e aprimorou as informações que ele fornece aos administradores e à equipe de suporte técnico. Agora, é exibida uma tabela **Atribuições** que resume todas as atribuições do usuário com base em associação a um grupo. Essa lista inclui:
- Aplicativos móveis
- Políticas de conformidade
- Perfis de configuração
 
Além disso, a tabela **Dispositivos** agora inclui as colunas **Tipo de ingresso no Azure AD** e **Em conformidade com o Azure AD**. Para obter mais informações, consulte [ajudar os usuários a solucionar problemas](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune Data Warehouse (Visualização Pública)
O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do locatário. É possível acessar os dados usando um arquivo do Power BI (PBIX), um link OData compatível com várias ferramentas de análise ou interagindo com a API REST. Para obter mais informações, consulte [Usar o Intune Data Warehouse](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modos claro e escuros disponíveis para o aplicativo de Portal da Empresa para Windows 10 <!---676547--->
Os usuários finais poderão personalizar o modo de cores para o aplicativo de Portal da Empresa para Windows 10. O usuário poderá fazer a alteração na seção Configurações do aplicativo de Portal da Empresa. A alteração será exibida depois que o usuário reiniciar o aplicativo. Para Windows 10 versão 1607 e posteriores, o modo de aplicativo padrão será o da configuração do sistema. Para Windows 10 versão 1511 e anteriores, o modo de aplicativo padrão será o da configuração do sistema.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Habilitar que os usuários finais marquem seu grupo de dispositivos no aplicativo de Portal da Empresa para Windows 10 <!---807046-->
Os usuários finais agora podem selecionar a grupo seu dispositivo pertence marcando-o diretamente de no aplicativo de Portal da Empresa para Windows 10.



## <a name="june-2017"></a>Junho de 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Novo acesso de administração baseada em funções para administradores do Intune   <!-- 1099990 -->  
Uma nova função de administrador de acesso condicional está sendo adicionada para exibir, criar, modificar e excluir políticas de Acesso Condicional do Azure AD. Anteriormente, somente os administradores globais e os administradores de segurança tinham essa permissão. Os administradores do Intune podem receber essa permissão de função para ter acesso às políticas de acesso condicional.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Marcar dispositivos de propriedade corporativa com o número de série <!-- 1215070 -->  
O Intune agora dá suporte ao upload dos números de série de iOS, macOS e Android como Identificadores de Dispositivo Corporativo. No momento, não é possível usar números de série para bloquear o registro de dispositivos pessoais, pois os números de série não são verificados durante o registro. O bloqueio de dispositivos pessoais pelo número de série será liberado em breve.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Novas ações remotas para dispositivos iOS <!-- 854689 -->
Neste lançamento, adicionamos duas novas ações remotas para dispositivos iPad compartilhados, que gerenciam o aplicativo Classroom da Apple:

-   [Fazer logoff do usuário atual](device-logout-user.md) – Faz logoff do usuário atual de um dispositivo iOS escolhido.
-   [Remover usuário](device-remove-user.md) – Exclui um usuário escolhido do cache local de um dispositivo iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Suporte para iPads compartilhados com o aplicativo Sala de aula do iOS <!-- 1044681 -->
Nessa versão, expandimos o suporte do gerenciamento do aplicativo Classroom iOS para incluir os alunos que fazem logon em iPads compartilhados usando suas IDs da Apple gerenciadas.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Alterações para aplicativos internos do Microsoft Intune <!-- 1332306 -->
Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.
No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos. Você pode continuar a atribuir esses aplicativos conforme necessário.
Planejamos adicionar em um lançamento posterior, um método mais fácil para selecionar e atribuir aplicativos internos no Portal do Azure.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Instalação mais fácil de aplicativos do Office 365 <!--- 1121362 --->
O novo tipo de aplicativo do **Office 365 ProPlus** facilitará a atribuição de aplicativos do Office 365 ProPlus 2016 aos dispositivos gerenciados que executam a versão mais recente do Windows 10. Além disso, você também poderá instalar o Microsoft Project e o Microsoft Visio se tiver licenças para eles. Os aplicativos que você desejar serão agrupados e aparecerão como um aplicativo na lista de aplicativos no console do Intune.
Para obter mais informações, consulte [Como adicionar aplicativos do Office 365 para Windows 10](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Suporte para aplicativos offline da Microsoft Store para Empresas <!--- 777044 --->
Aplicativos offline comprados na Microsoft Store para Empresas agora serão sincronizados com o Portal do Azure. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>O Microsoft Teams agora faz parte da lista de AC baseada em aplicativos de aplicativos aprovados   <!-- 1257019 -->
O aplicativo Microsoft Teams para iOS e Android fará parte dos aplicativos aprovados para as políticas de acesso condicional baseado em aplicativos do Exchange e do SharePoint Online. O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários que usam o acesso condicional baseado em aplicativos.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Navegador gerenciado e integração de proxy de aplicativo <!-- 1287310 -->
O Navegador Gerenciado do Intune agora pode ser integrado ao serviço de Proxy de aplicativo do Azure AD para permitir que os usuários acessem os sites da Web internos, mesmo quando estão trabalhando remotamente. Os usuários do navegador simplesmente inserem a URL normalmente e o Managed Browser encaminha a solicitação através do gateway Web do proxy de aplicativo. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Novas definições de configuração de aplicativo para o Intune Managed Browser <!-- 682951 -->
Nesta versão, adicionamos configurações adicionais para o aplicativo Intune Managed Browser para iOS e Android. Agora você pode usar uma política de configuração de aplicativo para configurar a página inicial padrão e os indicadores do navegador.
Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Configurações do BitLocker para Windows 10  <!-- 951707 -->
Agora você pode definir as configurações do BitLocker para dispositivos Windows 10 usando um novo perfil de dispositivo do Intune. Por exemplo, você pode exigir que os dispositivos sejam criptografados e também definir outras configurações que são aplicadas quando o BitLocker é ativado.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Nesta versão, adicionamos novas configurações para o perfil de restrição de dispositivo do Windows 10 nas seguintes categorias:

-  Windows Defender
-  Celular e conectividade
-  Experiência na tela bloqueada
-  Privacidade
-  Pesquisar
-  Destaque do Windows
-  Navegador de borda

Para obter mais informações sobre as configurações do Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>O aplicativo de Portal da Empresa para Android agora tem uma nova experiência do usuário final para as Políticas de Proteção do Aplicativo <!--1305217-->
Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**. A intenção é impedir que os usuários finais passem desnecessariamente pelo processo de inscrição quando eles só precisam acessar os aplicativos que dão suporte a Políticas de Proteção do Aplicativo, um recurso de gerenciamento de aplicativo móvel do Intune. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569-->
De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo. Esta ação remove o dispositivo do gerenciamento do Intune para que o aplicativo possa ser removido do dispositivo pelo usuário. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) e na [documentação do usuário final do Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505-->
O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703). Isso reduzirá o problema de atraso das instalações de aplicativos durante o estado de "Sincronização Pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938--->
O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados. A nova experiência fornece instruções passo a passo que guiam o usuário pelo processo de inscrição no Azure Active Directory (exigido para recursos de Acesso Condicional) e inscrição de MDM (exigido para os recursos de gerenciamento de dispositivo). A experiência guiada estará acessível na home page do Portal da Empresa. Os usuários podem continuar a usar o aplicativo se não concluírem o registro e inscrição, mas enfrentarão uma funcionalidade limitada.

Esta atualização só fica visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Os consoles de administrador do Microsoft Intune e do Acesso Condicional estão disponíveis
Anunciamos a disponibilidade geral do novo Intune nos consoles de administrador do Portal do Azure e do Acesso Condicional. Por meio do Intune no Portal do Azure, agora você pode gerenciar todas as funcionalidades MAM e MDM do Intune em uma única experiência de administrador consolidada e aproveitar o agrupamento e direcionamento do Azure AD. O acesso condicional no Azure reúne funcionalidades avançadas no Azure AD e no Intune em um único console unificado. Além disso, de uma experiência administrativa, a migração para a plataforma Azure permite o uso de navegadores modernos.

O Intune agora está visível sem o rótulo **versão prévia** no Portal do Azure em portal.azure.com.

No momento, nenhuma ação é necessária para os clientes existentes, a menos que você tenha recebido uma de uma série de mensagens no centro de mensagens solicitando uma ação de sua parte para que possamos migrar seus grupos. Talvez você também tenha recebido um aviso do centro de mensagens informando que a migração está levando mais tempo devido a bugs no nosso lado. Continuaremos trabalhando incessantemente para migrar os clientes afetados.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS
Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS
Os usuários de dispositivos iOS poderão ver nosso novo seletor de conta ao entrarem no Portal da Empresa, caso usem suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft. Para saber mais, veja [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

## <a name="may-2017"></a>Maio de 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950-->
Agora você pode alterar a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. No console do Configuration Manager, [altere a autoridade de MDM](/sccm/mdm/deploy-use/change-mdm-authority) em Definir como Configuration Manager (híbrido), como Microsoft Intune (autônomo) ou vice-versa.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notificação aprimorada para PINs de inicialização do Samsung Knox <!--1087143-->
Quando os usuários finais precisarem definir um PIN de inicialização em dispositivos Samsung Knox para ficarem em conformidade com a criptografia, a notificação exibida para eles os levará para o local exato no aplicativo de Configurações quando a notificação for tocada.  Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Suporte para o ASM (Apple School Manager) com iPad compartilhado <!-- 748864, 770395-->

O Intune agora dá suporte ao uso do ASM (Apple School Manager) no lugar do Programa de registro de dispositivos da Apple para fornecer o registro pronto para uso de dispositivos iOS. A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS). Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> A configuração de iPads Compartilhados para trabalhar com o aplicativo Sala de aula exige configurações de Educação do iOS no Azure que ainda não estão disponíveis.  Essa funcionalidade será adicionada em breve.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Fornecer assistência remota para dispositivos Android usando o TeamViewer <!-- 675418 -->

O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android. Para obter mais informações, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Novas condições de políticas de proteção de aplicativo para MAM <!-- 679864 -->

Agora você pode definir um requisito para o MAM sem os usuários do registro, que impõe as seguintes políticas:

- Versão mínima do aplicativo
- Versão mínima do sistema operacional
- Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)

Esse recurso está disponível no Android e no iOS. O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune. No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK. O usuário não poderá acessar o aplicativo direcionado se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos três diferentes níveis mencionados acima. Neste ponto, o usuário poderá remover sua conta (para aplicativos de várias identidades), fechar o aplicativo ou atualizar a versão do sistema operacional ou do aplicativo.

Defina também outras configurações para fornecer uma notificação sem bloqueio que recomenda uma atualização do sistema operacional ou do aplicativo. Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.

Para obter mais informações, consulte [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md) e [Configurações da política de proteção de aplicativo do Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Definir as configurações de aplicativo para o Android for Work <!-- 621621 -->
Alguns aplicativos Android da loja dão suporte a opções de configuração gerenciada que permitem a um administrador de TI controlar como um aplicativo é executado no perfil de trabalho. Com o Intune, agora você pode exibir as configurações com suporte em um aplicativo e defini-las no Portal do azure com um designer de configuração ou um editor de JSON. Para obter mais informações, consulte [Usar configurações de aplicativo para o Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nova funcionalidade de configuração de aplicativo para MAM sem registro <!-- 677969 -->
Agora você pode criar políticas de configuração de aplicativo por meio do MAM sem um canal de registro. Esse recurso é equivalente às políticas de configuração de aplicativo disponíveis na configuração de aplicativo do MDM (gerenciamento de dispositivo móvel). Para obter um exemplo de configuração de aplicativo que usa o MAM sem registro, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Configurar listas de permissões e bloqueios de URLs para o Managed Browser <!-- 682960 -->
Agora você pode configurar uma lista de permissões e bloqueios de domínios e URLs para o Intune Managed Browser usando definições de configuração de aplicativo no portal do Azure. Essas configurações podem ser definidas independentemente de estarem sendo usadas em um dispositivo gerenciado ou não gerenciado. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Exibição de assistência técnica da política de proteção de aplicativo <!-- 1069473 -->
Os usuários da assistência técnica de TI agora podem verificar o status da licença do usuário e o status dos aplicativos da política de proteção de aplicativo atribuídos aos usuários na folha Solução de Problemas. Para obter detalhes, consulte [Solução de problemas](./help-desk-operators.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Controlar visitas ao site em dispositivos iOS <!-- 723832 -->
Agora você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois seguintes métodos:

- Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.

- Permita que apenas sites especificado sejam acessados pelo navegador Safari. Para cada site que você especificar são criados indicadores no Safari.

Para obter mais informações, consulte [Configurações de filtro de conteúdo da Web para dispositivos iOS](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 -->
Para aplicativos implantados em perfis de trabalho de dispositivos Android for Work, agora é possível configurar o estado de permissões em aplicativos individuais.  Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.  Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone. Esse recurso permite definir permissões em nome do usuário final.  É possível configurar permissões para a) negar automaticamente sem notificar o usuário; b) aprovar automaticamente sem notificar o usuário ou c) solicitar que o usuário aceite ou recuse. Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definir PIN específico do aplicativo para dispositivos Android for Work <!-- 728976, 1102534 -->
Dispositivos Android 7.0 e superior com um perfil de trabalho gerenciados como um dispositivo Android for Work possibilitam ao administrador definir uma política de senha que se aplica somente aos aplicativos no perfil de trabalho.  As opções incluem:

- Definir apenas uma política de senha em todo o dispositivo – essa é a senha que o usuário deve usar para desbloquear seu dispositivo inteiro.
- Definir apenas uma política de senha de perfil de trabalho – os usuários deverão inserir uma senha sempre que um aplicativo for aberto no perfil de trabalho.
- Definir uma política de dispositivo e de perfil de trabalho – o administrador de TI tem a opção de definir uma política de senha de dispositivo e uma política de senha de perfil de trabalho em diferentes níveis (por exemplo, um PIN de quatro dígitos para desbloquear o dispositivo, mas um PIN de seis dígitos para abrir um aplicativo de trabalho).

Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Isso está disponível somente no Android 7.0 e superior.  Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Novas configurações para dispositivos Windows 10 <!-- 978585 -->
Adicionamos novas [configurações de restrição de dispositivos Windows](device-restrictions-windows-10.md) que controlam recursos como vídeos sem fio, descoberta de dispositivo, alternância de tarefas e mensagens de erro do cartão SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Atualizações da configuração de certificado <!-- 918991 and 823198 -->
Ao criar um perfil de certificado SCEP, em **Formato do nome da entidade**, a opção **Personalizado** está disponível para dispositivos iOS, Android e Windows. Antes dessa atualização, o campo **Personalizado** estava disponível apenas para dispositivos iOS. Para obter mais informações, consulte [Como criar um perfil de certificado SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Ao criar um perfil de certificado PKCS, em **Nome alternativo da entidade**, o **Atributo personalizado do Azure AD** está disponível. A opção **Departamento** fica disponível quando você seleciona **Atributo personalizado do Azure AD**. Para saber mais, veja [Como criar um perfil de certificado PKCS](certficates-pfx-configure.md#create-a-device-configuration-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Configurar vários aplicativos que podem ser executados quando um dispositivo Android está no modo de quiosque <!-- 662059 -->
Anteriormente, quando um dispositivo Android estava no modo de quiosque, era possível configurar apenas um aplicativo que tinha permissão para ser executado. Agora é possível configurar vários aplicativos usando a ID do aplicativo, a URL da loja ou selecionando um aplicativo Android já gerenciado. Para obter mais informações, consulte [Configurações do modo de quiosque](device-restrictions-android.md#kiosk).



## <a name="april-2017"></a>Abril de 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Suporte para gerenciamento do aplicativo Sala de Aula da Apple
Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads. Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.
Para obter detalhes, confira [Definir as configurações de educação do iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->
Agora, os aplicativos Android na Play Store, que são compatíveis com opções de configuração gerenciada, podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nova política de Android para PINs complexos <!-- 722069 -->
Agora, você pode definir um tipo de [senha](device-restrictions-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Suporte adicional para dispositivos Android for Work
- **Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 -->

  Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 -->

  Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

Para saber mais, confira [Restrições de dispositivo para Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->
Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](lob-apps-ios.md) (arquivos .ipa) e [Android](lob-apps-android.md) (arquivos .apk) a usuários ou dispositivos.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](home-screen-settings-ios.md). Essa política altera o layout da Tela inicial, mas não implanta nenhum aplicativo.

- **Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](air-print-settings-ios-macos.md) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](airplay-settings-ios.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão. Para obter mais informações, consulte [Ativar o modo perdido em dispositivos iOS](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->
Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](app-notification-settings-ios.md) para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->
Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->
Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](device-restrictions-ios.md#domains):

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 -->
Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->
Agora você pode [sincronizar os livros](vpp-apps-ios.md) adquiridos na loja de programa adquirido por volume da Apple com o Intune e atribuí-los aos usuários.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gerenciamento de vários usuários para dispositivos Samsung Knox Standard <!-- 971988 -->
Agora há suporte para dispositivos que executam o Samsung Knox Standard para o [gerenciamento de vários usuários](android-enroll.md) pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e obtêm as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->
Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](device-restrictions-windows-10.md), como suporte adicional ao navegador Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->
Adicionamos suporte para o [gerenciamento de vários usuários](windows-enroll.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Começar do zero para PCs com Windows 10<!-- 1004830 -->
Agora há uma [nova ação de dispositivo para começar do zero](device-fresh-start.md) disponível em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->
Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](edition-upgrade-configure-windows-10.md) para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->
Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para o logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte para cenários de autoatendimento e de Portal da Empresa no momento.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 -->
Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal de solução de problemas de suporte técnico <!-- 907448 -->
O novo [portal de solução de problemas](help-desk-operators.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

## <a name="march-2017"></a>Março de 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Suporte para o Modo Perdido do iOS<!--431695-->
Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**. Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.

O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido. Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.

O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](device-management.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->
Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->
Agora você pode atribuir aplicativos de linhas de negócios da loja para os usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="new-compliance-reports---846671--"></a>Novos relatórios de conformidade <!--846671-->
Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários. Você pode exibir informações sobre

- Estado de conformidade geral de dispositivos
- Estado de conformidade para uma configuração individual
- Estado de conformidade para uma política individual

Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as políticas que afetam esse dispositivo.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal do Azure. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


## <a name="february-2017"></a>Fevereiro de 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Exibir todas as ações em dispositivos gerenciados <!--677150-->
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Exibir categorias de dispositivos <!--814654-->
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Definir as configurações do Windows Update para Empresas <!--776716-->

O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10. Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](windows-update-for-business-configure.md).
