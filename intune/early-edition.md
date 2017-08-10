---
title: "Edição antecipada"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 8/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5861c999752bfef05b8a33161d0bf75a6d4daf59
ms.sourcegitcommit: 18cdbdc226f64368de892a8c5cff157c37986c57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="the-early-edition-for-microsoft-intune---august-2017"></a>A edição antecipada do Microsoft Intune – agosto de 2017

A **edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não compartilhe essas informações fora da empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
>As seguintes alterações estão em desenvolvimento para o Intune. Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>Intune no portal do Azure




### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nova ação de dispositivo para forçar os dispositivos a sincronizarem com o Intune <!-- 711369 -->    
Estamos adicionando uma nova ação de dispositivo que força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.

### <a name="actions-for-non-compliance----730266--"></a>Ações para não conformidade <!--730266-->     
*Ações de não conformidade* são um novo recurso das políticas de conformidade que permitem tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.


### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restringir a restrição de registro de dispositivo Android e iOS por versão do sistema operacional  <!--- 1333256,  1245463 --->  
O Intune agora dá suporte à restrição do registro de iOS e Android por número de versão do sistema operacional. Em **Intune** > **Restrições de registro** > **Restrição de Tipo de Dispositivo** > **Padrão** > **Restrições de plataforma**, o administrador de TI poderá definir uma configuração de plataforma para restringir o registro entre os valores mínimo e máximo do sistema operacional. As versões do sistema operacional Android devem ser especificadas como Principal.Secundária.Build.Revisão, em que Secundária, Build e Revisão são opcionais. Versões do iOS devem ser especificadas como Principal.Secundária.Build, em que Build é opcional.

>[!NOTE]
>Essa configuração não restringe o registro por meio de programas de registro da Apple, que incluem o Programa de registro de dispositivos da Apple, o Apple School Manager ou o Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Restringir o registro de dispositivos de pessoais Android, iOS e macOS  <!--- 1333272,  1333275, 1245709 --->
O Intune agora dá suporte à restrição de registro de dispositivos pessoais para iOS, Android e macOS usando números de série do dispositivo. Alguns dispositivos não informam os números de série. Verifique junto aos fabricantes de dispositivos para obter os detalhes. Ao carregar os números de série para o Intune, você pode pré-declarar os dispositivos como corporativos. Usando as restrições de registro, você pode bloquear dispositivos pessoais (BYOD), permitindo somente o registro de dispositivos corporativos.

Para importar os números de série para o portal do Intune, acesse **Registro de dispositivo** > **Identificadores de dispositivo corporativo** e clique em **Adicionar** e, em seguida, carregue um arquivo .CSV. O arquivo não deve conter nenhum cabeçalho e tem duas colunas, uma para número de série e uma para detalhes como números IMEI.  Para restringir os dispositivos pessoais, acesse **Registro de dispositivo** > **Restrições de registro**. Em **Restrições de tipo de dispositivo**, selecione o **Padrão** e, em seguida, escolha **Configurações da Plataforma**. Você pode **Permitir** ou **Bloquear** dispositivos pessoais para iOS, Android e macOS. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível <!-- 777100 -->   
Uma nova política estará disponível no espaço de trabalho Atualizações de software em que você pode forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Você também poderá exibir um novo relatório que lista os dispositivos iOS com as versões mais antigas e um resumo de por que eles estão desatualizados.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** estará disponível no espaço de trabalho **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Novas configurações para permitir e bloquear aplicativos em dispositivos Samsung KNOX Standard  <!-- 822899,  1305423-->   
Estamos adicionando novas [configurações de restrições de dispositivo](device-restrictions-android.md) que permitem especificar as seguintes listas de aplicativo:
  - Aplicativos que os usuários têm permissão para instalar
  - Aplicativos que os usuários são impedidos de executar
  - Aplicativos que ficam ocultados do usuário no dispositivo  

Você pode especificar o aplicativo por URL, nome de pacote ou na lista de aplicativos gerenciados.

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10
<!--- 978575, 1308849, 1308850 -->
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior]( device-restrictions-windows-10.md).

### <a name="new-device-restriction-settings-for-windows-10------1063965---"></a>Novas configurações de restrição de dispositivo para Windows 10 <!-- 1063965 -->
Estamos adicionando novas configurações para o [perfil de restrição de dispositivo do Windows 10](/intune/device-restrictions-windows-10) nas seguintes categorias:
- Windows Defender SmartScreen
- Loja de aplicativos


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

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Suporte a acesso condicional para dispositivos Mac  <!-- 720172 -->   
Em breve você será capaz de definir uma política de acesso condicional que exija que os dispositivos Mac sejam registrados no Intune e estejam em conformidade com as políticas de conformidade do dispositivo. Por exemplo, os usuários podem baixar o aplicativo de Portal da Empresa Intune para macOS e registrar seus dispositivos Mac no Intune. O Intune avaliar se o dispositivo Mac está em conformidade ou não com requisitos como PIN, criptografia, versão do sistema operacional e integridade do sistema.

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!---1164477--->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. Em dezembro, todo o acesso aos recursos da empresa, incluindo ao email, será bloqueado. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fim do suporte para Android 4.3 e inferior <!---1171127, 1326920 --->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes do início de outubro não poderão acessar o Portal da Empresa ou esses aplicativos. Em dezembro, todos os dispositivos registrados passarão por uma desativação forçada, resultando na perda de acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e a qualidade da sua experiência decairá ao longo do tempo.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Lembrete de suporte de plataforma: o suporte base do Windows Phone 8.1 terminará em 11 de julho de 2017 <!-- 1327781 -->  
Em 11 de julho de 2017, a plataforma Windows Phone 8.1 chegará ao fim do suporte base. O suporte da versão Windows 8.1 de computador não é afetado.

Não há nenhum impacto imediato para qualquer dispositivo Windows Phone 8.1 que é gerenciado pelo serviço do Intune. Os dispositivos registrados continuam a funcionar e todas as políticas, configurações e aplicativos continuarão a funcionar como esperado. Observe que não há nenhuma melhoria voltada para a plataforma Windows Phone 8.1 no Serviço do Intune e para o aplicativo de Portal da Empresa do Windows Phone 8.1.

É recomendável fazer upgrade dos dispositivos Windows Phone 8.1 qualificados para Windows 10 Mobile assim que possível. 




## <a name="intune-apps"></a>Aplicativos do Intune

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modos claro e escuros disponíveis para o aplicativo de Portal da Empresa para Windows 10 <!---676547--->
Os usuários finais poderão personalizar o modo de cores para o aplicativo de Portal da Empresa para Windows 10. O usuário poderá fazer a alteração na seção Configurações do aplicativo de Portal da Empresa. A alteração será exibida depois que o usuário reiniciar o aplicativo. Para Windows 10 versão 1607 e posterior, o modo de aplicativo padrão é a da configuração do sistema. Para computadores desktop que executam o Windows 10 versão 1511 e versões anteriores, o modo de aplicativo padrão será o modo claro.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Permitir que os usuários finais acessem o aplicativo de Portal da Empresa para Android sem registro <!---1169910--->  
Em breve, os usuários finais não precisarão registrar seu dispositivo para acessar o aplicativo de Portal da Empresa para Android. Os usuários finais em organizações que estão usando as Políticas de Proteção de Aplicativo deixarão de receber solicitações para registrar seu dispositivo quando abrirem o aplicativo de Portal da Empresa. Os usuários finais também poderão instalar aplicativos do Portal da Empresa sem registrar o dispositivo. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."

### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nova experiência conectada para usuários do Portal da Empresa para Android e para usuários da Política de Proteção de Aplicativo <!-- 621669 -->
Os usuários finais poderão procurar aplicativos, gerenciar dispositivos e exibir informações de contato de TI usando o aplicativo Portal da Empresa para Android sem registrar seus dispositivos Android. Além disso, se um usuário final já usa um aplicativo protegido pelas Políticas de Proteção de Aplicativo do Intune e inicia o Portal da Empresa para Android, o usuário final não recebe mais uma solicitação para registrar o dispositivo. 

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para iOS <!--739894-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para iOS. Isso permite aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela Sobre.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>As páginas de detalhes de aplicativos exibem novas informações para dispositivos Android <!--1287476-->
A página de detalhes de aplicativos do aplicativo Portal da Empresa para Android exibirá as categorias de aplicativo que o administrador de TI tiver definido para esse aplicativo.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>As caixas de diálogo MAM (Gerenciamento de Aplicativos Móveis) do Intune agora têm uma interface moderna <!-- 1199015 -->
As caixas de diálogo MAM (Gerenciamento de Aplicativos Móveis) do Intune foram atualizadas para a aparência moderna. As caixas de diálogo funcionam da mesma maneira como no estilo anterior.

Em dispositivos Android modernos, as caixas de diálogo de erro ou notificação exibidas pelo Intune agora mostrarão a aparência moderna.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nova configuração no aplicativo Portal da Empresa para Android para ativar/desativar a otimização de bateria <!--1405990-->
A página **Configurações** no aplicativo Portal da Empresa para Android terá uma nova configuração que permite que os usuários desliguem facilmente a otimização da bateria para os aplicativos Portal da Empresa e Microsoft Authenticator. O nome do aplicativo mostrado na configuração varia dependendo de qual aplicativo gerencia a conta de trabalho. É recomendável que os usuários desliguem a otimização da bateria para melhorar o desempenho dos aplicativos de trabalho que sincronizam dados e emails. 




## <a name="notices"></a>Avisos

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->   
A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->   
Para contas do Intune criadas depois de janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho de registrar dispositivos na Versão Prévia do Portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planejar mudanças: o Intune está mudando a experiência do Portal do Parceiro <!-- 1050016 -->
Vamos remover a página do Parceiro do Microsoft Intune em manage.microsoft.com, a partir da atualização do serviço em meados de maio de 2017.  

Se você for um administrador de parceiro, não será mais possível exibir conteúdo e tomar medidas em nome de seus clientes na página de Parceiro do Microsoft Intune. Em vez disso, deverá entrar em um dos outros Portais de Parceiro da Microsoft.

O [Microsoft Partner Center](https://partnercenter.microsoft.com/) e o [Centro de administração do parceiro do Office 365](https://portal.office.com/) permitem entrar nas contas de clientes que você gerencia. Avançando como parceiro, use um desse sites para gerenciar os clientes.



### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
