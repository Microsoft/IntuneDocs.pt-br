---
title: Novidades do Microsoft Intune
titlesuffix: Azure portal
description: "Conheça as novidades do portal do Intune no Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bc322567505506f63e2eb002fd330fc151bc70d
ms.sourcegitcommit: 6004fe51e3cee6fb34514ed0d56e20587ecafeb4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Conheça as novidades de cada semana do Microsoft Intune. Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md).

> [!Note]
> Muitos desses recursos acabarão tendo suporte em implantações híbridas com o Configuration Manager. Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-october-2-2017"></a>Semana de 2 de outubro de 2017

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Melhorias no fluxo de trabalho de configuração de dispositivo no Portal da Empresa <!--1490692-->
Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para Android. A linguagem é mais fácil de usar e mais específica para sua empresa e combinamos as telas sempre que possível. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Melhor orientação sobre a solicitação de acesso aos contatos em dispositivos Android <!--1484985-->

O aplicativo de Portal da Empresa para Android normalmente exige que o usuário final aceite a permissão de Contatos. Se um usuário final recusar esse acesso, ele verá uma notificação no aplicativo que o alerta para conceder a permissão para acesso condicional. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Correção de inicialização segura para Android <!--1490712-->

Os usuários finais com dispositivos Android poderão tocar no motivo da não conformidade no aplicativo do Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Notificações por push adicionais para usuários finais no aplicativo Portal da Empresa para Android Oreo <!--1475932-->

Os usuários finais verão notificações adicionais para indicar a eles quando o aplicativo Portal da Empresa para Android Oreo estiver executando tarefas em segundo plano, como recuperação de políticas do serviço Intune. Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas em seu dispositivo. Isso faz parte da [otimização geral da interface do usuário do Portal da Empresa](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) para o aplicativo Portal da Empresa para Android Oreo. 

Há mais otimizações para novos elementos de interface do usuário que estão habilitados no Android Oreo.  Os usuários finais verão notificações adicionais que indicarão a eles quando o Portal da Empresa estiver executando tarefas em segundo plano, tais como recuperação das políticas do serviço Intune.  Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas no dispositivo deles.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho<!---1485783--->

Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. 

Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->

A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Bloquear o registro de dispositivo Samsung Knox sem suporte <!--- 1490695 --->

O aplicativo Portal da Empresa tenta registrar apenas os dispositivos Samsung Knox com suporte. Para evitar erros de ativação de KNOX que impedem o registro do MDM, o registro do dispositivo será tentado somente se ele aparecer na [lista de dispositivos publicada pela Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Dispositivos Samsung podem ter números de modelo que oferecem suporte a KNOX, enquanto outros não. Verifique a compatibilidade com KNOX com o revendedor do dispositivo antes de adquirir e implantar. Você pode encontrar a lista completa de dispositivos verificados nas [configurações de política do Android e Samsung KNOX Standard](/intune-classic/android-policy-settings-in-microsoft-intune.md#supported-samsung-knox-standard-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Fim do suporte para Android 4.3 e inferior <!---1171126, 1326920 --->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informar aos usuários finais quais informações de dispositivo podem ser vistas em dispositivo registrados <!--1165314-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo em todos os aplicativos Portal da Empresa. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente do artigo [Quais informações sua empresa pode ver?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Isso será distribuído em todos os aplicativos de Portal da Empresa em um futuro próximo. Anunciamos isso para iOS em [setembro](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017). 


## <a name="week-of-september-25-2017"></a>Semana de 25 de setembro de 2017

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="intune-supports-ios-11---1428975--"></a>O Intune dá suporte ao iOS 11 <!--1428975-->
O Intune dá suporte ao iOS 11. Isso foi anunciado anteriormente no [blog de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!---1164477--->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. 

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->

O aplicativo Portal da Empresa para Windows 10 permite que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.

## <a name="week-of-september-11-2017"></a>Semana de 11 de setembro de 2017

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para iOS <!--739894-->

Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para iOS. Isso permitirá que os usuários obtenham mais informações sobre privacidade diretamente a partir desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela Sobre.

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Permitir que os usuários finais acessem o aplicativo de Portal da Empresa para Android sem registro <!---1169910--->

Em breve, os usuários finais não precisarão registrar seu dispositivo para acessar o aplicativo de Portal da Empresa para Android. Os usuários finais em organizações que estão usando as Políticas de Proteção de Aplicativo deixarão de receber solicitações para registrar seu dispositivo quando abrirem o aplicativo de Portal da Empresa. Os usuários finais também poderão instalar aplicativos do Portal da Empresa sem registrar o dispositivo. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Frases mais fáceis de entender para o aplicativo Portal da Empresa para Android <!---1396349--->  

O processo de inscrição para o aplicativo Portal da Empresa para Android foi simplificado com o novo texto a fim de facilitar a inscrição dos usuários. Se você tiver a documentação de inscrição personalizada, atualize-o para refletir as novas telas. Você pode encontrar as imagens de amostra na nossa página [Atualizações da interface do usuário para aplicativos de usuário final do Intune](whats-new-app-ui.md#week-of-september-11-2017).

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Aplicativo Portal da Empresa do Windows 10 adicionado à política de permissão da Proteção de Informações do Windows <!-- 677129 -->

O aplicativo Portal da Empresa do Windows 10 foi atualizado para dar suporte à WIP (Proteção de Informações do Windows). O aplicativo pode ser adicionado à política de permissão do WIP. Com essa alteração, o aplicativo não precisa mais ser adicionado à lista **Isento**.


## <a name="week-of-august-21-2017"></a>Semana de 21 de agosto de 2017

### <a name="device-enrollment"></a>Registro de dispositivo
#### <a name="improvements-to-device-overview----1404453---"></a>Melhorias na visão geral de dispositivos <!-- 1404453 -->  
Com as melhorias, agora a visão geral de dispositivos exibe os dispositivos registrados, mas exclui os dispositivos gerenciados pelo Exchange ActiveSync. Os dispositivos do Exchange ActiveSync não têm as mesmas opções de gerenciamento que os dispositivos registrados. Para exibir o número de dispositivos registrados e o número de dispositivos registrados por plataforma no Intune, no portal do Azure, acesse **Dispositivos** > **Visão geral**.

### <a name="device-management"></a>Gerenciamento de dispositivo
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Melhorias no inventário de dispositivos coletado pelo Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
Nesta versão, fizemos as seguintes melhorias nas informações de inventário coletadas para cada um dos dispositivos que você gerencia:
 
-   Para dispositivos Android, agora você pode adicionar uma coluna no inventário de dispositivos que mostra o nível de patch mais recente para cada dispositivo. Adicione a coluna **Nível de patch de segurança** à sua lista de dispositivos para ver essa informação.
-   Ao filtrar a exibição de dispositivos, agora você pode filtrar os dispositivos pela data de registro. Por exemplo, você pode exibir somente os dispositivos que foram registrados após uma data especificada.
-   Fizemos melhorias no filtro usado pelo item **Última data de check-in**.
-   Na lista de dispositivos, agora você pode exibir o número de telefone dos dispositivos corporativos.
Além disso, você pode usar o painel de filtro para pesquisar dispositivos por número de telefone.
 
Para obter mais detalhes sobre o inventário de dispositivos, consulte [Como exibir o inventário de dispositivo do Intune](device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>Suporte a acesso condicional para dispositivos macOS 
<!-- 720172 -->
Agora você pode definir uma política de acesso condicional que requer que os dispositivos Mac sejam registrados no Intune e estejam em conformidade com as políticas de conformidade de dispositivo. Por exemplo, os usuários podem baixar o aplicativo de Portal da Empresa Intune para macOS e registrar seus dispositivos Mac no Intune. O Intune avaliar se o dispositivo Mac está em conformidade ou não com requisitos como PIN, criptografia, versão do sistema operacional e integridade do sistema.

- Saiba mais sobre [suporte a acesso condicional para dispositivos macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>O aplicativo Portal da Empresa para macOS está em visualização pública <!---1484796--->
O aplicativo Portal da Empresa para macOS agora está disponível como parte da visualização pública para acesso condicional no Enterprise Mobility + Security. Essa versão é compatível com macOS 10.11 e superior. Obtenha-a em [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Novas configurações de restrição de dispositivo para Windows 10    
<!--1063965, 1308850  -->
Nesta versão, adicionamos novas configurações no [perfil de restrição de dispositivo Windows 10](/intune/device-restrictions-windows-10) nas seguintes categorias:

-   Windows Defender SmartScreen
-   Loja de aplicativos

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Atualizações no perfil de dispositivo de Endpoint Protection do Windows 10 para configurações do BitLocker
<!--1459533 -->    
Nesta versão, fizemos as seguintes melhorias no modo de funcionamento das configurações do BitLocker em um perfil de dispositivo de Endpoint Protection do Windows 10:
 
Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **BitLocker com chip do TPM não compatível**, anteriormente, quando você selecionava **Bloquear**, na verdade, o BitLocker era permitido. Agora isso foi corrigido para bloquear o BitLocker quando essa opção está selecionada.
Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **Agente de recuperação de dados baseada em certificado**, agora você pode bloquear explicitamente o agente de recuperação de dados baseada em certificado. No entanto, por padrão, o agente é permitido.
Em **Configurações de unidade de dados fixa do BitLocker**, na configuração **Agente de recuperação de dados**, agora você pode bloquear explicitamente o agente de recuperação de dados.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).


### <a name="app-management"></a>Gerenciamento de aplicativos
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nova experiência conectada para usuários do Portal da Empresa para Android e para usuários da Política de Proteção de Aplicativo <!-- 621669 -->
Os usuários finais agora podem procurar aplicativos, gerenciar dispositivos e exibir as informações de contato de TI usando o aplicativo Portal da Empresa Android sem inscrever os respectivos dispositivos Android. Além disso, se um usuário final já usa um aplicativo protegido pelas Políticas de Proteção de Aplicativo do Intune, ele não recebe mais uma solicitação para registrar o dispositivo ao iniciar o Portal da Empresa para Android.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nova configuração no aplicativo Portal da Empresa para Android para ativar/desativar a otimização de bateria <!--1405990-->
A página **Configurações** no aplicativo Portal da Empresa para Android tem uma nova configuração que permite que os usuários desliguem facilmente a otimização da bateria para os aplicativos Portal da Empresa e Microsoft Authenticator. O nome do aplicativo mostrado na configuração variará dependendo de qual aplicativo gerencia a conta de trabalho. É recomendável que os usuários desliguem a otimização da bateria para melhorar o desempenho dos aplicativos de trabalho que sincronizam dados e emails. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Suporte a várias identidades do OneNote para iOS <!-- 1234281 -->
Os usuários finais agora podem usar contas diferentes (trabalho e pessoal) com o Microsoft OneNote para iOS. As políticas de proteção de aplicativo podem ser aplicadas aos dados corporativos em blocos de anotações de trabalho sem afetar os blocos de anotações pessoais. Por exemplo, uma política pode permitir que um usuário localize informações em blocos de anotações de trabalho, mas impedirá que o usuário copie e cole dados corporativos do bloco de anotações de trabalho para um bloco de anotações pessoal.
 
- Saiba mais sobre os aplicativos que dão suporte à [proteção de aplicativo e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Novas configurações para permitir e bloquear aplicativos em dispositivos Samsung KNOX Standard
<!-- 1305423 822899-->  
Nessa versão, estamos adicionando novas [configurações de restrições de dispositivo](device-restrictions-android.md) que permitem especificar as seguintes listas de aplicativo:
 
- Aplicativos que os usuários têm permissão para instalar
- Aplicativos que os usuários são impedidos de executar
- Aplicativos que ficam ocultados do usuário no dispositivo
 
Você pode especificar o aplicativo por URL, nome de pacote ou na lista de aplicativos gerenciados.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link da nova interface do usuário da política de acesso condicional com base no aplicativo do Azure AD no Intune
<!-- 1016201 -->
Agora os administradores de TI podem definir políticas condicionais com base no aplicativo por meio da nova interface do usuário de política de acesso condicional na carga de trabalho do Azure AD. O acesso condicional com base no aplicativo na seção Proteção de Aplicativo do Intune no Portal do Azure por enquanto continuará lá e a implementação será feita em conjunto. Também há um link de conveniência para a nova interface do usuário da política de acesso condicional na carga de trabalho do Intune.

- Saiba mais sobre o [acesso condicional com base no aplicativo no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).


## <a name="notices"></a>Avisos

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Endereços IP atualizados para o Intune <!-- 1175274 -->
Uma [lista atualizada de nomes DNS e endereços IP](/intune/network-bandwidth-use) está disponível para as configurações de proxy do firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Usar o Azure Active Directory para o acesso condicional <!-- 967947 -->
O acesso condicional está disponível na seção Azure Active Directory do Portal do Azure e fornece uma estrutura mais avançada e flexível para definir políticas para aplicativos na nuvem como o Office 365 Exchange Online e o SharePoint Online.  Use a folha **Acesso condicional no Azure Active Directory** para configurar políticas em vez do console do Intune. As políticas existentes no console do Intune precisam ser recriadas no Portal do Azure. Para obter mais informações, consulte [Criar políticas de acesso condicional do Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal Clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência, caso sua conta existente não possa acessar o portal do Azure.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Funções de administração que estão sendo substituídas no Portal do Azure
As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure. Após a migração para o portal do Azure, você precisará reatribuir essas novas funções de administração aos administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>O que está por vir

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>O aplicativo Mail do iOS 11 dará suporte ao OAuth <!---1196951--->
O acesso condicional com o Intune dá suporte a uma autenticação mais segura em dispositivos iOS com o OAuth. Para dar suporte a ela, agora haverá um fluxo diferente no aplicativo Portal da Empresa para iOS, a fim de possibilitar uma autenticação mais segura. Quando os usuários finais tentarem entrar em uma nova conta do Exchange no aplicativo Mail, eles verão um prompt de exibição da Web. Após o registro no Intune, os usuários verão um aviso para permitir que o aplicativo Mail nativo acesse um certificado. A maioria dos usuários finais não verá mais nenhum email em quarentena. As contas de email existentes continuarão usando o protocolo de autenticação básica. Portanto, esses usuários ainda receberão emails em quarentena. Essa experiência de entrada para usuários finais é semelhante à de aplicativos móveis do Office.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 2-->
__Atualizações de Aplicativos em destaque__  
Adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque na página inicial. Você pode ver a aparência dessas alterações na página [novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Lembrete de suporte à plataforma: o suporte base do Windows Phone 8.1 terminou em 11 de julho de 2017
<!-- 1327781 -->
Em 11 de julho de 2017, o suporte base à plataforma Windows Phone 8.1 chegou ao fim. O suporte a computadores Windows 8.1 não foi afetado.

Não há nenhum impacto imediato para qualquer dispositivo Windows Phone 8.1 que é gerenciado pelo serviço do Intune. Dispositivos registrados continuarão a funcionar e todas as políticas, configurações e aplicativos continuarão a funcionar como esperado. Observe que não há nenhuma melhoria voltada para a plataforma Windows Phone 8.1 no Serviço do Intune e para o aplicativo de Portal da Empresa do Windows Phone 8.1.

É recomendável que você atualize os dispositivos Windows Phone 8.1 qualificados para Windows 10 Mobile assim que possível. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Alterações no suporte para o aplicativo do Portal da Empresa iOS do Intune  <!-- 1164474  -->
Em breve, haverá uma nova versão do aplicativo do Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 9.0 ou posterior. A versão do Portal da Empresa que dá suporte ao iOS 8 ainda estará disponível por um breve período. No entanto, nós também damos suporte ao iOS 9.0 e posterior, portanto, se você também usa aplicativos iOS habilitados para MAM, faça com que seus usuários finais atualizem para o sistema operacional mais recente. 

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Estamos informando isso com antecedência, mesmo que não tenhamos datas específicas, para que você tenha tempo de planejar. Verifique se seus usuários atualizaram para o iOS 9 ou superior e, quando o aplicativo do Portal da Empresa for lançado, solicite que eles atualizem esse aplicativo.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Recomendamos que os usuários atualizem para o iOS 9.0 ou posterior para que eles aproveitem os novos recursos do Intune.  Incentive os usuários a instalarem a nova versão do Portal da Empresa e aproveitar os novos recursos que ele oferece.

Acesse o Intune no Portal do Azure e exiba Dispositivos > Todos os Dispositivos e filtre por versão do iOS para ver os dispositivos atuais com os sistemas operacionais anteriores ao iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->
A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS.

Disponibilizamos uma versão do aplicativo Portal da Empresa para iOS por meio do programa TestFlight da Apple, que impõe os novos requisitos de ATS. Se quiser experimentá-lo a fim de testar a conformidade com a ATS, envie um email para <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> informando seu nome e sobrenome, endereço de email e nome da empresa. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
