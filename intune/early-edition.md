---
title: "Edição antecipada"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0ac0d1fd2f618339f847201f333d3f32561ca6b1
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>A edição antecipada do Microsoft Intune – setembro de 2017

A **edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não compartilhe essas informações fora da empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
>As seguintes alterações estão em desenvolvimento para o Intune. Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

<!--

## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
   
-->

  

## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure


### <a name="google-play-protect-support-on-android----908720----"></a>Suporte para Google Play Protect no Android <!-- 908720  -->  
Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. O Intune oferecerá suporte aos recursos do Google Play Protect, incluindo atestado remoto do SafetyNet.  Os administradores podem definir requisitos de política de conformidade que exigem a configuração e a integridade do Google Play Protect. A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play.  O acesso condicional pode impedir que os usuários acessem recursos corporativos, se um dispositivo não for compatível com os requisitos do Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Impedir que os usuários de dispositivos com Android alterem a data e a hora de seus dispositivos <!-- 1333292 -->
Use uma [política de dispositivo personalizada do Android](custom-settings-android.md) para impedir que os usuários de dispositivos com Android alterem a data e a hora do dispositivo.
Para fazer isso, configure uma política personalizada do Android com o URI de configuração ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Defina isso como **TRUE** e, em seguida, atribua-o aos grupos necessários.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Exibir as atribuições de política de proteção do aplicativo para solução de problemas <!--  1475003 -->
Nesta versão futura, a opção de **Política de proteção do aplicativo** será adicionada à lista suspensa **Atribuições** disponível na folha de solução de problemas. Agora você pode selecionar as políticas de proteção do aplicativo para ver as políticas de proteção de aplicativo atribuídas aos usuários selecionados.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Criar aplicativos iOS limitados a Apple App Stores regionais específicas <!-- 1281692 -->
Você poderá especificar a localidade do país durante a criação de um aplicativo gerenciado da Apple App Store.

> [!NOTE]  
> No momento, você só pode criar aplicativos gerenciados da Apple App Store que estão presentes na loja dos Estados Unidos.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Selecione o país da loja da Apple para sincronização de aplicativos VPP<!-- 1332311 -->  
Você pode configurar o país da loja do VPP (Programa de Compra por Volume) ao carregar seu token de VPP. O Intune sincroniza aplicativos VPP para todas as localidades da loja VPP especificada de um país.

> [!NOTE]  
> Atualmente, o Intune sincroniza apenas aplicativos VPP da loja VPP que correspondem à localidade do Intune na qual o locatário do Intune foi criado.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Atualizar usuário VPP do iOS e os aplicativos de dispositivo licenciados <!-- 1305564 -->  
Você poderá configurar o token de VPP do iOS para atualizar todos os aplicativos comprados para esse token por meio do serviço Intune. O Intune detectará as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará automaticamente ao dispositivo quando o dispositivo fizer check-in.

### <a name="ios-11-support----1428975---"></a>Suporte para iOS 11 <!-- 1428975 -->
Quando for lançado pela Apple, o Intune oferecerá suporte ao iOS 11.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 1308838  -->
Nesta versão, estamos adicionando várias configurações novas para o perfil de restrição de dispositivo do Windows 10 Team para ajudar você a controlar dispositivos do Surface Hub.
Para saber mais sobre esse perfil, veja [Configurações de restrição de dispositivo do Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672, 1119689 -->  
Você poderá criar uma política de atualização de edição do Windows 10 que atualiza dispositivos com Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Examinar a conformidade da política para anéis de atualização do Windows 10 <!-- 1352223 -->  
Você poderá examinar um relatório da política para seus anéis de atualização do Windows 10 em **Atualizações de software** > **Por estado de implantação do anel de atualização**. O relatório da política inclui o status da implantação para os anéis de atualização que você configurou. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Aplicativo Portal da Empresa do Windows 10 adicionado à política de permissão da Proteção de Informações do Windows <!-- 677129 -->  
O aplicativo Portal da Empresa do Windows 10 será atualizado para dar suporte à WIP (Proteção de Informações do Windows). O aplicativo pode ser adicionado à política de permissão do WIP. Com essa alteração, o aplicativo não precisa mais ser adicionado à lista **Isento**. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Suporte remoto para Windows e dispositivos com Windows Mobile <!-- 1070473 -->    
O Intune poderá usar o software [TeamViewer](https://www.teamviewer.com), adquirido separadamente, para que você possa dar assistência remota a usuários que estão utilizando dispositivos com Windows e Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Verificar dispositivos com o Windows Defender <!-- 1280988  1280990   -->
Você poderá executar uma **Verificação rápida**, **Verificação completa** e **Atualizar assinaturas** com o Windows Defender Antivírus em dispositivos com Windows 10 gerenciados. Na folha de visão geral do dispositivo, escolha a ação a ser executada no dispositivo. Você precisará confirmar a ação antes de o comando ser enviado ao dispositivo. 

**Verificação rápida**: uma verificação rápida examina os locais onde o malware registra-se para começar, como as chaves do Registro e pastas de inicialização conhecidas do Windows. Uma verificação rápida demora cerca de cinco minutos. Combinada com a configuração **Proteção sempre em tempo real**, que examina os arquivos quando eles são abertos, fechados e sempre que um usuário navega até uma pasta, uma verificação rápida ajuda a fornecer proteção contra malware que pode estar no sistema ou no kernel. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Verificação completa**: uma verificação completa pode ser útil em dispositivos que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa, e é útil para executar verificações sob demanda. A verificação completa pode demorar uma hora. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Atualizar assinaturas**: o comando para atualizar assinatura atualiza as definições e assinaturas de malware do Windows Defender. Isso ajuda a garantir o que Windows Defender Antivírus seja eficaz na detecção de malware. Esse recurso destina-se somente a dispositivos com Windows 10, com conectividade de internet pendente no dispositivo. 

### <a name="bitlocker-device-configuration----1397398---"></a>Configuração de dispositivo do BitLocker <!-- 1397398 -->  
**Criptografia Windows > Configurações de Base** incluirá uma nova configuração **Aviso para criptografia de outro disco** que permite que você desabilite o [prompt de aviso](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) para criptografia de outro disco que pode estar em uso no dispositivo do usuário.  A mensagem de aviso exige o consentimento do usuário final antes de configurar o BitLocker no dispositivo e bloqueia a instalação do BitLocker até receber a confirmação do usuário final.  A nova configuração desabilita o aviso do usuário final.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->
A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquear a ação de copiar e colar entre perfis de trabalho e pessoais no Android for Work <!-- 1098994 -->   
Com esta versão, é possível configurar o perfil de trabalho para Android for Work para bloquear a ação de copiar e colar entre aplicativos pessoais e de trabalho. Encontre essa nova configuração no perfil **Restrições de dispositivo** para a plataforma **Android for Work** em **Configurações de perfil de trabalho**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho<!---1485783--->
Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Suplementos do MAM do Intune e Outlook para Android <!-- 1450688 -->
Em algumas semanas, a equipe do Office anunciará suplementos para o Outlook no Android. O conjunto de recursos desse suplemento já existe no Outlook no Windows, iOS, Web e Mac. Como os suplementos são gerenciados pelo Exchange, os usuários poderão copiar e compartilhar dados e mensagens entre o Outlook e aplicativos de suplementos não gerenciados, a menos que o acesso aos suplementos seja desativado pelo administrador do Exchange. 

Para gerenciar permissões de acesso do usuário aos suplementos, trabalhe com o administrador do Exchange para garantir que as políticas de proteção de dados de MAM se aplicam aos suplementos.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Se as políticas do Exchange já estiverem definidas para impedir o sideload ou a instalação de suplementos, não haverá a necessidade de continuar a leitura. Suas políticas de MAM serão aplicadas conforme o esperado. Se, no entanto, você tiver configurado as políticas de MAM para restringir operações de recortar, copiar e colar no Outlook no Android, e não tiver definido sua política de suplemento do Exchange, saiba que, por padrão, os usuários poderão instalar suplementos para o Outlook. Esses suplementos podem acessar o corpo e o assunto da mensagem, além de outras propriedades da mensagem. Você pode desativar a capacidade do usuário final de instalar suplementos fazendo com que o Administrador do Exchange remova as funções "Meus Aplicativos do Marketplace" e "Meus Aplicativos Personalizados". Para obter mais detalhes, veja o link de informações adicionais compartilhado abaixo.

Observe que a alteração da configuração no Exchange será aplicada no Outlook no Windows, iOS, Web, Mac e móvel. 

#### <a name="what-do-i-need-to-do"></a>O que eu preciso fazer?
Revise hoje suas políticas do Exchange. Informe sua equipe de TI e de suporte técnico. Entre em contato com nossa equipe de suporte se tiver perguntas ou dúvidas específicas. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->
Você poderá criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associa coleções de usuário e de entidades do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>Ações para não conformidade <!--730266-->     
*Ações de não conformidade* são um novo recurso das políticas de conformidade que permitem tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** estará disponível no espaço de trabalho **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10
<!--- 978575, 1308849, -->
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Suporte do Android for Work no Lookout <!-- 1087312 -->   
O conector do Intune com o Lookout dará suporte a dispositivos Android for Work ao usar o aplicativo Lookout for Work. Você pode implantar o aplicativo Lookout dentro ou fora do contêiner.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Proteção de Aplicativo do Intune e Ferramentas de Desenvolvimento do Citrix MDX <!-- 709185 -->
Você pode gerenciar dispositivos e aplicativos com uma combinação do Citrix XenMobile MDX e o Microsoft Intune. Isso permite que você gerencie aplicativos com políticas de proteção de aplicativo do Intune usando a tecnologia de mVPN da Citrix.

Você pode localizar um repositório de códigos que contém a Ferramenta de Encapsulamento de Aplicativo do Intune e o SDK de Aplicativo do Intune para iOS e Android, integrando com a tecnologia mVPN da Citrix MDX.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Novo parceiro de Defesa contra Ameaças Móveis   <!-- 954681 -->
Agora, é possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Zimperium, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como a integração com o Intune funciona?
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Zimperium. Você pode configurar políticas de acesso condicional de EMS com base na avaliação de risco do Zimperium habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade a recursos corporativos com base em ameaças detectadas.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Link da nova interface do usuário da política de acesso condicional do Azure AD do Intune <!-- 1016201 -->
Os administradores de TI podem definir políticas condicionais com base no aplicativo por meio da nova interface do usuário de política de acesso condicional na carga de trabalho do Azure AD. As políticas de acesso condicional com base no aplicativo que estão na seção Proteção de Aplicativo do Intune no Azure permanecem lá por enquanto e são impostas lado a lado. Também haverá um link de conveniência para a nova política de acesso condicional da interface do usuário no Azure AD da carga de trabalho do Intune.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->   
Você pode ter várias funções de CAS (Servidor de Acesso de Cliente) para o Exchange Connector local. Por exemplo, se o CAS principal falhar, o Exchange Connector recebe uma consulta para voltar a outros CASs. Esse recurso garante que o serviço não seja interrompido.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pacote de gerenciamento do System Center Operations Manager para Exchange Connector <!-- 885457 -->   
O pacote de gerenciamento do System Center Operations Manager para o Exchange Connector estará disponível para ajudá-lo a analisar os logs do Exchange Connector. Esse pacote de gerenciamento oferece diferentes maneiras de monitorar o Intune quando você precisar solucionar problemas.

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!---1164477--->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos.  

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fim do suporte para Android 4.3 e inferior <!---1171127, 1326920 --->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Os dispositivos que não forem atualizados até o início de outubro não poderão mais acessar o Portal da Empresa ou esses aplicativos. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e a qualidade da sua experiência decairá ao longo do tempo.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Lembrete de suporte de plataforma: o suporte base do Windows Phone 8.1 terminará em 11 de julho de 2017 <!-- 1327781 -->  
Em 11 de julho de 2017, a plataforma Windows Phone 8.1 chegará ao fim do suporte base. O suporte da versão Windows 8.1 de computador não é afetado.

Não há nenhum impacto imediato para qualquer dispositivo Windows Phone 8.1 que é gerenciado pelo serviço do Intune. Os dispositivos registrados continuam a funcionar e todas as políticas, configurações e aplicativos continuarão a funcionar como esperado. Observe que não há nenhuma melhoria voltada para a plataforma Windows Phone 8.1 no Serviço do Intune e para o aplicativo de Portal da Empresa do Windows Phone 8.1.

É recomendável fazer upgrade dos dispositivos Windows Phone 8.1 qualificados para Windows 10 Mobile assim que possível. 





## <a name="intune-apps"></a>Aplicativos do Intune
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->
O aplicativo Portal da Empresa para Windows 10 permitirá que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->
Os aplicativos da empresa que foram disponibilizados com ou sem a inscrição no aplicativo Portal da Empresa Android podem ser instalados sem uma solicitação de inscrição.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>O Portal da Empresa do iOS exibe ícones grandes <!-- 1454593 -->
Estamos corrigindo um problema conhecido com o modo como o Portal da Empresa do iOS exibe ícones no bloco do aplicativo. Se você carregar ícones de aplicativo com 120 x 120 pixels ou maiores, eles serão exibidos no [site Portal da Empresa] (https://portal.manage.microsoft.com) e nas páginas de aplicativos do Portal da Empresa do iOS com o tamanho total do bloco de aplicativo.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Frases mais fáceis de entender para o aplicativo Portal da Empresa para Android <!---1396349--->    
O processo de inscrição para o aplicativo Portal da Empresa para Android foi simplificado com o novo texto a fim de facilitar a inscrição dos usuários. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Suporte do Intune Managed Browser para iOS e Android <!---1374196--->
A partir de outubro de 2017, o aplicativo do Intune Managed Browser no aplicativo do Android oferecerá suporte apenas a dispositivos que executam o Android 4.4 e versões posteriores. O aplicativo Intune Managed Browser no iOS oferecerá suporte apenas a dispositivos que executam o iOS 9.0 e versões posteriores. Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Permitir que os usuários finais acessem o aplicativo de Portal da Empresa para Android sem registro <!---1169910--->  
Em breve, os usuários finais não precisarão registrar seu dispositivo para acessar o aplicativo de Portal da Empresa para Android. Os usuários finais em organizações que estão usando as Políticas de Proteção de Aplicativo deixarão de receber solicitações para registrar seu dispositivo quando abrirem o aplicativo de Portal da Empresa. Os usuários finais também poderão instalar aplicativos do Portal da Empresa sem registrar o dispositivo. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para iOS <!--739894-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para iOS. Isso permite aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela Sobre.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>As páginas de detalhes de aplicativos exibem novas informações para dispositivos Android <!--1287476-->
A página de detalhes de aplicativos do aplicativo Portal da Empresa para Android exibirá as categorias de aplicativo que o administrador de TI tiver definido para esse aplicativo.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>As caixas de diálogo MAM (Gerenciamento de Aplicativos Móveis) do Intune agora têm uma interface moderna <!-- 1199015 -->
As caixas de diálogo MAM (Gerenciamento de Aplicativos Móveis) do Intune foram atualizadas para a aparência moderna. As caixas de diálogo funcionam da mesma maneira como no estilo anterior.

Em dispositivos Android modernos, as caixas de diálogo de erro ou notificação exibidas pelo Intune agora mostrarão a aparência moderna.



## <a name="notices"></a>Avisos
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->   
A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planejar mudanças: o Intune está mudando a experiência do Portal do Parceiro <!-- 1050016 -->
Vamos remover a página do Parceiro do Microsoft Intune em manage.microsoft.com, a partir da atualização do serviço em meados de maio de 2017.  

Se você for um administrador de parceiro, não será mais possível exibir conteúdo e tomar medidas em nome de seus clientes na página de Parceiro do Microsoft Intune. Em vez disso, deverá entrar em um dos outros Portais de Parceiro da Microsoft.

O [Microsoft Partner Center](https://partnercenter.microsoft.com/) e o [Centro de administração do parceiro do Office 365](https://portal.office.com/) permitem entrar nas contas de clientes que você gerencia. Avançando como parceiro, use um desse sites para gerenciar os clientes.



### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
