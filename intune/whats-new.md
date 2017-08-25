---
title: Novidades do Microsoft Intune
titleSuffix: Intune on Azure
description: "Conheça as novidades do portal do Intune no Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f28ce989b5907f7e7474543c364508424dc0c9cf
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Conheça as novidades de cada semana do Microsoft Intune. Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md).

> [!Note]
> Muitos desses recursos acabarão tendo suporte em implantações híbridas com o Configuration Manager. Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Intune apps
-->   


## <a name="week-of-august-21-2017"></a>Semana de 21 de agosto de 2017
### <a name="app-management"></a>Gerenciamento de aplicativos
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nova experiência conectada para usuários do Portal da Empresa para Android e para usuários da Política de Proteção de Aplicativo <!-- 621669 -->

Agora, os usuários finais podem procurar aplicativos, gerenciar dispositivos e exibir informações de contato de TI usando o aplicativo Portal da Empresa para Android sem registrar seus dispositivos Android. Além disso, se um usuário final já usa um aplicativo protegido pelas Políticas de Proteção de Aplicativo do Intune, ele não recebe mais uma solicitação para registrar o dispositivo ao iniciar o Portal da Empresa para Android.

## <a name="week-of-july-31-2017"></a>Semana de 31 de julho de 2017
### <a name="device-enrollment"></a>Registro de dispositivo  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restringir a restrição de registro de dispositivo Android e iOS por versão do sistema operacional  <!--- 1333256,  1245463 --->
O Intune agora dá suporte à restrição do registro de iOS e Android por número de versão do sistema operacional. Agora, em **Restrição de Tipo de Dispositivo**, o administrador de TI pode definir uma configuração de plataforma para restringir o registro entre os valores mínimo e máximo do sistema operacional. As versões do sistema operacional Android devem ser especificadas como Major.Minor.Build.Rev, em que Minor, Build e Rev são opcionais. Versões do iOS devem ser especificadas como Major.Minor.Build, em que Minor e Build são opcionais. Saiba mais sobre as [restrições de registro de dispositivo](enrollment-restrictions-set.md).

>[!NOTE]
>Não restringe o registro por meio dos programas de registro da Apple ou do Apple Configurator.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Restringir o registro de dispositivos de pessoais Android, iOS e macOS  <!--- 1333272,  1333275, 1245709 --->
O Intune pode restringir o registro de dispositivos pessoais colocando em uma lista de permissões os números IMEI dos dispositivos corporativos. Agora, o Intune expandiu essa funcionalidade para iOS, Android e macOS usando os números de série do dispositivo. Ao carregar os números de série para o Intune, você pode pré-declarar os dispositivos como corporativos. Usando as restrições de registro, você pode bloquear dispositivos pessoais (BYOD), permitindo somente o registro de dispositivos corporativos. Saiba mais sobre as [restrições de registro de dispositivo](enrollment-restrictions-set.md).

Para importar os números de série, acesse **Registro de dispositivo** > **Identificadores de dispositivo corporativo**, clique em **Adicionar** e, em seguida, carregue um arquivo .CSV (sem cabeçalho, duas colunas de número de série e detalhes como números IMEI).  Para restringir os dispositivos pessoais, acesse **Registro de dispositivo** > **Restrições de registro**. Em **Restrições de tipo de dispositivo**, selecione o **Padrão** e, em seguida, escolha **Configurações da Plataforma**. Você pode **Permitir** ou **Bloquear** dispositivos pessoais para iOS, Android e macOS. 


### <a name="device-management"></a>Gerenciamento de dispositivo   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nova ação de dispositivo para forçar os dispositivos a sincronizarem com o Intune <!-- 711369 -->
Nessa versão, adicionamos uma nova ação de dispositivo que força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.
Para ver mais detalhes, consulte [Sincronizar o dispositivo](device-sync.md)

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível <!-- 777100 -->
Uma nova política está disponível no espaço de trabalho Atualizações de software, em que você pode forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Para obter detalhes, consulte [Configurar políticas de atualização do iOS](/intune/software-updates-ios)

#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – Novo parceiro de Defesa contra Ameaças Móveis  <!-- 954651, 1172027 -->
É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional baseado na avaliação de risco realizada pelo Checkpoint SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Como a integração com o Intune funciona?
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Checkpoint SandBlast Mobile. É possível configurar políticas de acesso condicional de EMS com base na avaliação de risco do Checkpoint SandBlast Mobile habilitada por meio das políticas de conformidade de dispositivo do Intune. Você pode permitir ou bloquear o acesso de dispositivos sem conformidade aos recursos corporativos com base em ameaças detectadas.


### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Implantar um aplicativo como ele está disponível na Microsoft Store para Empresas <!-- 748101 -->
Com essa versão, os administradores agora podem atribuir o Microsoft Store para Empresas como ele está disponível. Quando definido como disponível, os usuários finais podem instalar o aplicativo do site ou do aplicativo do Portal da Empresa sem serem redirecionados para a Microsoft Store.


### <a name="intune-apps"></a>Aplicativos do Intune  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 1-->
Fizemos várias atualizações na interface do usuário do [site Portal da Empresa](https://portal.manage.microsoft.com) para aprimorar a experiência do usuário final.

- __Aprimoramentos para blocos de aplicativos__: os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente com base na cor dominante do ícone (caso seja possível detectá-la). Quando aplicável, essa tela de fundo substituirá a borda cinza que era visível anteriormente em blocos de aplicativos.

    O site do Portal da Empresa exibe ícones grandes sempre que possível em uma versão futura. É recomendável que os administradores de TI publiquem aplicativos usando ícones de alta resolução com um tamanho mínimo de 120x120 pixels. 

- __Alterações de navegação__: os itens da barra de navegação foram movidos para o menu hambúrguer na parte superior esquerda. A página Categorias foi removida. Os usuários agora podem filtrar o conteúdo por categoria durante a navegação.

- __Atualizações para os Aplicativos em Destaque__: adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque da página inicial.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Suporte para iBooks no site do Portal da Empresa <!--1231841-->
Adicionamos uma página dedicada ao site do Portal da Empresa que permite aos usuários procurar e baixar iBooks. 

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Detalhes adicionais da solução de problemas de suporte técnico <!---  Applies to 1263399, 1326964, 1341642 --->
 
O Intune atualizou a exibição de solução de problemas e aprimorou as informações que ele fornece aos administradores e à equipe de suporte técnico. Agora, é exibida uma tabela **Atribuições** que resume todas as atribuições do usuário com base em associação a um grupo. Essa lista inclui:
- Aplicativos móveis
- Políticas de conformidade
- Perfis de configuração
 
Além disso, a tabela **Dispositivos** agora inclui as colunas **Tipo de ingresso no Azure AD** e **Em conformidade com o Azure AD**. Para obter mais informações, consulte [ajudar os usuários a solucionar problemas](help-desk-operators.md).

### <a name="reporting"></a>Relatórios

#### <a name="intune-data-warehouse-public-preview"></a>Intune Data Warehouse (Visualização Pública)

O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do locatário. É possível acessar os dados usando um arquivo do Power BI (PBIX), um link OData compatível com várias ferramentas de análise ou interagindo com a API REST. Para obter mais informações, consulte [Usar o Intune Data Warehouse](reports-nav-create-intune-reports.md).

## <a name="week-of-july-23rd-2017"></a>Semana de 23 de julho de 2017

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modos claro e escuros disponíveis para o aplicativo de Portal da Empresa para Windows 10 <!---676547--->
Os usuários finais poderão personalizar o modo de cores para o aplicativo de Portal da Empresa para Windows 10. O usuário poderá fazer a alteração na seção Configurações do aplicativo de Portal da Empresa. A alteração será exibida depois que o usuário reiniciar o aplicativo. Para Windows 10 versão 1607 e posteriores, o modo de aplicativo padrão será o da configuração do sistema. Para Windows 10 versão 1511 e anteriores, o modo de aplicativo padrão será o da configuração do sistema.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Habilitar que os usuários finais marquem seu grupo de dispositivos no aplicativo de Portal da Empresa para Windows 10 <!---807046-->
Os usuários finais agora podem selecionar a grupo seu dispositivo pertence marcando-o diretamente de no aplicativo de Portal da Empresa para Windows 10.




## <a name="notices"></a>Avisos

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Endereços IP atualizados para o Intune <!-- 1175274 -->
Uma [lista atualizada de nomes DNS e endereços IP](/intune/network-bandwidth-use) está disponível para as configurações de proxy do firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Usar o Azure Active Directory para o acesso condicional <!-- 967947 -->
O acesso condicional está disponível na seção Azure Active Directory do console do Azure e fornece uma estrutura mais avançada e flexível para definir políticas para aplicativos na nuvem como o Office 365 Exchange Online e o SharePoint Online.  Use a folha **Acesso condicional no Azure Active Directory** para configurar políticas em vez do console clássico do Intune. As políticas existentes no console clássico do Intune precisam ser recriadas no console do Azure. Para obter mais informações, consulte [Criar políticas de acesso condicional do Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência, caso sua conta existente não possa acessar o portal do Azure.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Funções de administração que estão sendo substituídas no Portal do Azure
As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure. Após a migração para o portal do Azure, você precisará reatribuir essas novas funções de administração aos administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>O que está por vir

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!---1164477--->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 2-->
__Atualizações de Aplicativos em destaque__  
Adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque na página inicial. Você pode ver a aparência dessas alterações na página [novidades na interface do usuário do aplicativo](whats-new-app-ui.md).


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fim do suporte para Android 4.3 e inferior <!---1171127, 1326920 --->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Os dispositivos que não forem atualizados até o início de outubro não poderão mais acessar o Portal da Empresa ou esses aplicativos. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.


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
