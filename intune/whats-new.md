---
title: Novidades do Microsoft Intune
titleSuffix: Intune on Azure
description: "Conheça as novidades do portal do Intune no Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fdda99bfd72c71d36a19449d43bc6cbf6a00babe
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Novidades do Microsoft Intune
<a id="whats-new-in-microsoft-intune" class="xliff"></a>

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
-->   



## Semana de 26 de junho de 2017
<a id="week-of-june-26th-2017" class="xliff"></a>

### Controle de acesso baseado em função
<a id="role-based-access-control" class="xliff"></a>
#### Novo acesso de administração baseada em funções para administradores do Intune   <!-- 1099990 -->
<a id="new-role-based-administration-access-for-intune-admins------1099990---" class="xliff"></a>  
Uma nova função de administrador de acesso condicional está sendo adicionada para exibir, criar, modificar e excluir políticas de Acesso Condicional do Azure AD. Anteriormente, somente os administradores globais e os administradores de segurança tinham essa permissão. Os administradores do Intune podem receber essa permissão de função para ter acesso às políticas de acesso condicional.


### Registro de dispositivo
<a id="device-enrollment" class="xliff"></a>
#### Marcar dispositivos de propriedade corporativa com o número de série <!-- 1215070 -->
<a id="tag-corporate-owned-devices-with-serial-number----1215070---" class="xliff"></a>  
O Intune agora dá suporte ao upload dos números de série de iOS, macOS e Android como Identificadores de Dispositivo Corporativo. No momento, não é possível usar números de série para bloquear o registro de dispositivos pessoais, pois os números de série não são verificados durante o registro. O bloqueio de dispositivos pessoais pelo número de série será liberado em breve.


### Gerenciamento de dispositivos
<a id="device-management" class="xliff"></a>
#### Novas ações remotas para dispositivos iOS <!-- 854689 -->
<a id="new-remote-actions-for-ios-devices----854689---" class="xliff"></a>
Nesta versão, adicionamos duas novas ações de dispositivo remoto para dispositivos iOS:

-   [Fazer logoff do usuário atual](device-logout-user.md) – Faz logoff do usuário atual de um dispositivo iOS escolhido.
-   [Remover usuário](device-remove-user.md) – Exclui um usuário escolhido do cache local de um dispositivo iOS.


Usando essas ações remotas, os administradores podem gerenciar as contas de usuário armazenadas em cache em um iPad compartilhado e também fazer logoff do usuário conectado no dispositivo no momento.

Durante o registro, o administrador determina o número máximo de contas de usuário que podem ser armazenadas em cache em um dispositivo. “Remover usuário” permite que os administradores removam usuários específicos armazenados em cache.

“Fazer logoff do usuário atual” fará logoff do usuário que está conectado ao dispositivo no momento. Essa ação pode ser encontrada na parte superior da folha de visão geral do dispositivo no qual as ações de dispositivo geralmente ficam.

“Remover usuário” excluirá um usuário especificado do cache local do dispositivo. Esta ação pode ser encontrada navegando para “Monitorar” -> “Usuários” -> clique com o botão direito do mouse em um usuário específico na lista. Os dados associados a uma conta de usuário que ainda não foram sincronizados serão perdidos. Além disso, pode levar até 24 horas para a lista de usuários refletir que o usuário foi removido.

#### Suporte para iPads compartilhados com o aplicativo Sala de aula do iOS <!-- 1044681 -->
<a id="support-for-shared-ipads-with-the-ios-classroom-app----1044681---" class="xliff"></a>
Nessa versão, expandimos o suporte do gerenciamento do aplicativo Classroom iOS para incluir os alunos que fazem logon em iPads compartilhados usando suas IDs da Apple gerenciadas.


### Gerenciamento de aplicativos
<a id="app-management" class="xliff"></a>  
#### Suporte para aplicativos offline da Windows Store para Empresas <!--- 777044 --->
<a id="support-for-offline-apps-from-the-windows-store-for-business-----777044----" class="xliff"></a>
Aplicativos offline comprados na Windows Store para Empresas agora serão sincronizados com o Portal do Intune. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

#### O Microsoft Teams agora faz parte da lista de AC baseada em aplicativos de aplicativos aprovados   <!-- 1257019 -->
<a id="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---" class="xliff"></a>

O aplicativo Microsoft Teams para iOS e Android fará parte dos aplicativos aprovados para as políticas de acesso condicional baseado em aplicativos do Exchange e do SharePoint Online. O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários que usam o acesso condicional baseado em aplicativos.

#### Navegador gerenciado e integração de proxy de aplicativo <!-- 1287310 -->
<a id="managed-browser-and-app-proxy-integration----1287310---" class="xliff"></a>
 O Navegador Gerenciado do Intune agora pode ser integrado ao serviço de Proxy de aplicativo do Azure AD para permitir que os usuários acessem os sites da Web internos, mesmo quando estão trabalhando remotamente. Usuários do navegador simplesmente digitam a URL do site como normalmente fariam e o Managed Browser roteia a solicitação através do gateway de Web do proxy de aplicativo. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md).


#### Novas definições de configuração de aplicativo para o Intune Managed Browser <!-- 682951 -->
<a id="new-app-configuration-settings-for-the-intune-managed-browser----682951---" class="xliff"></a>
Nesta versão, adicionamos configurações adicionais para o aplicativo Intune Managed Browser para iOS e Android. Agora você pode usar uma política de configuração de aplicativo para configurar a página inicial padrão e os indicadores do navegador.
Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md)




### Configuração do dispositivo
<a id="device-configuration" class="xliff"></a>  
#### Configurações do BitLocker para Windows 10  <!-- 951707 -->
<a id="bitlocker-settings-for-windows-10-----951707---" class="xliff"></a>
Agora você pode definir as configurações do BitLocker para dispositivos Windows 10 usando um novo perfil de dispositivo do Intune. Por exemplo, você pode exigir que os dispositivos sejam criptografados e também definir outras configurações que são aplicadas quando o BitLocker é ativado.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).

### Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
<a id="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----" class="xliff"></a>

Nesta versão, adicionamos novas configurações para o perfil de restrição de dispositivo do Windows 10 nas seguintes categorias:

 -  Windows Defender
-  Celular e conectividade
-  Experiência na tela bloqueada
-  Privacidade
-  Pesquisar
-  Destaque do Windows
-  Navegador de borda

Para obter mais informações sobre as configurações do Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](device-restrictions-windows-10.md).

## Semana de 12 de junho de 2017
<a id="week-of-june-12-2017" class="xliff"></a>

### O aplicativo de Portal da Empresa para Android agora tem uma nova experiência do usuário final para as Políticas de Proteção do Aplicativo <!--1305217-->
<a id="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--" class="xliff"></a>
Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**. A intenção é impedir que os usuários finais passem pelo processo de registro desnecessariamente quando eles só precisam acessar os aplicativos que dão suporte às Políticas de Proteção de Aplicativo, um recurso de gerenciamento de aplicativos móveis do Intune. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569-->
<a id="new-menu-action-to-easily-remove-company-portal---1164569--" class="xliff"></a>
De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo. Essa ação remove o dispositivo do gerenciamento do Intune, de forma que o aplicativo possa ser removido do dispositivo pelo usuário. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) e na [documentação do usuário final do Android](/intune-user-help/unenroll-your-device-from-intune-android).

### Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505-->
<a id="improvements-to-app-syncing-with-windows-10-creators-update---676505--" class="xliff"></a>

O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703). Isso reduzirá o problema de paralisação de instalações de aplicativo durante o estado de "Sincronização pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938--->
<a id="new-guided-experience-for-windows-10-company-portal----1058938---" class="xliff"></a>

O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados. A nova experiência fornece instruções passo a passo que guiam o usuário pelo registro no Azure Active Directory (necessário para os recursos do Acesso Condicional) e pelo registro do MDM (necessário para os recursos de gerenciamento de dispositivos). A experiência guiada estará acessível na home page do Portal da Empresa. Os usuários poderão continuar usando o aplicativo se não concluírem o registro, mas terão funcionalidade limitada.

Esta atualização só é visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

## Semana de 5 de junho de 2017
<a id="week-of-june-5-2017" class="xliff"></a>

### Os consoles de administrador do Microsoft Intune e do Acesso Condicional estão disponíveis
<a id="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available" class="xliff"></a>

Anunciamos a disponibilidade geral dos novos consoles de administrador do Intune no Azure e do Acesso Condicional. Por meio do Intune no Azure, agora você pode gerenciar todas as funcionalidades MAM e MDM do Intune em uma única experiência de administrador consolidada e aproveitar o agrupamento e direcionamento do Azure AD. O acesso condicional no Azure reúne funcionalidades avançadas no Azure AD e no Intune em um único console unificado. Além disso, de uma experiência administrativa, a migração para a plataforma Azure permite o uso de navegadores modernos.

O Intune agora está visível sem o rótulo **versão prévia** no console do Azure em portal.azure.com.

No momento, nenhuma ação é necessária para os clientes existentes, a menos que você tenha recebido uma de uma série de mensagens no centro de mensagens solicitando uma ação de sua parte para que possamos migrar seus grupos. Talvez você também tenha recebido um aviso do centro de mensagens informando que a migração está levando mais tempo devido a bugs no nosso lado. Continuaremos trabalhando incessantemente para migrar os clientes afetados.

### Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS
<a id="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios" class="xliff"></a>
Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS
<a id="account-picker-now-available-for-the-company-portal-app-for-ios" class="xliff"></a>
Os usuários de dispositivos iOS poderão ver nosso novo seletor de conta ao entrarem no Portal da Empresa, caso usem suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

## Semana de 29 de maio de 2017
<a id="week-of-may-29-2017" class="xliff"></a>

### Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950-->
<a id="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--" class="xliff"></a>

Agora você pode alterar a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. No console do Configuration Manager, [altere a autoridade de MDM](/sccm/mdm/deploy-use/change-mdm-authority) em Definir como Configuration Manager (híbrido), como Microsoft Intune (autônomo) ou vice-versa.


### Notificação aprimorada para PINs de inicialização do Samsung KNOX<!--1087143-->
<a id="improved-notification-for-samsung-knox-startup-pins---1087143--" class="xliff"></a>
Quando os usuários finais precisarem definir um PIN de inicialização em dispositivos Samsung KNOX para ficarem em conformidade com a criptografia, a notificação exibida para eles os levará para o local exato no aplicativo de Configurações quando a notificação for tocada.  Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.


### Registro de dispositivo
<a id="device-enrollment" class="xliff"></a>

#### Suporte para o ASM (Apple School Manager) com iPad compartilhado <!-- 748864, 770395-->
<a id="apple-school-manager-asm-support-with-shared-ipad----748864-770395--" class="xliff"></a>

O Intune agora dá suporte ao uso do ASM (Apple School Manager) no lugar do Programa de registro de dispositivos da Apple para fornecer o registro pronto para uso de dispositivos iOS. A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS). Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> A configuração de iPads Compartilhados para trabalhar com o aplicativo Sala de aula exige configurações de Educação do iOS no Azure que ainda não estão disponíveis.  Essa funcionalidade será adicionada em breve.

### Gerenciamento de dispositivos
<a id="device-management" class="xliff"></a>

#### Fornecer assistência remota para dispositivos Android usando o TeamViewer <!-- 675418 -->
<a id="provide-remote-assistance-to-android-devices-using-teamviewer----675418---" class="xliff"></a>

O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android. Para obter mais informações, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](device-profile-android-teamviewer.md).

### Gerenciamento de aplicativos
<a id="app-management" class="xliff"></a>

#### Novas condições de políticas de proteção de aplicativo para MAM <!-- 679864 -->
<a id="new-app-protection-policies-conditions-for-mam----679864---" class="xliff"></a>

Agora você pode definir um requisito para o MAM sem os usuários do registro, que impõe as seguintes políticas:

- Versão mínima do aplicativo
- Versão mínima do sistema operacional
- Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)

Esse recurso está disponível no Android e no iOS. O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune. No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK. O usuário não poderá acessar o aplicativo direcionado se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos três diferentes níveis mencionados acima. Neste ponto, o usuário poderá remover sua conta (para aplicativos de várias identidades), fechar o aplicativo ou atualizar a versão do sistema operacional ou do aplicativo.

Defina também outras configurações para fornecer uma notificação sem bloqueio que recomenda uma atualização do sistema operacional ou do aplicativo. Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.

Para obter mais informações, consulte [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md) e [Configurações da política de proteção de aplicativo do Android](app-protection-policy-settings-android.md).

#### Definir as configurações de aplicativo para o Android for Work <!-- 621621 -->
<a id="configure-app-configurations-for-android-for-work----621621---" class="xliff"></a>
Alguns aplicativos Android da loja dão suporte a opções de configuração gerenciada que permitem a um administrador de TI controlar como um aplicativo é executado no perfil de trabalho. Com o Intune, agora você pode exibir as configurações com suporte em um aplicativo e defini-las no portal do Intune com um designer de configuração ou um editor de JSON. Para obter mais informações, consulte [Usar configurações de aplicativo para o Android for Work](app-configuration-policies-use-android.md).

#### Nova funcionalidade de configuração de aplicativo para MAM sem registro <!-- 677969 -->
<a id="new-app-configuration-capability-for-mam-without-enrollment----677969---" class="xliff"></a>

Agora você pode criar políticas de configuração de aplicativo por meio do MAM sem um canal de registro. Esse recurso é equivalente às políticas de configuração de aplicativo disponíveis na configuração de aplicativo do MDM (gerenciamento de dispositivo móvel). Para obter um exemplo de configuração de aplicativo que usa o MAM sem registro, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### Configurar listas de permissões e bloqueios de URLs para o Managed Browser <!-- 682960 -->
<a id="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---" class="xliff"></a>

Agora você pode configurar uma lista de permissões e bloqueios de domínios e URLs para o Intune Managed Browser usando definições de configuração de aplicativo no portal do Azure. Essas configurações podem ser definidas independentemente de estarem sendo usadas em um dispositivo gerenciado ou não gerenciado. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### Exibição de assistência técnica da política de proteção de aplicativo <!-- 1069473 -->
<a id="app-protection-policy-helpdesk-view----1069473---" class="xliff"></a>

Os usuários da assistência técnica de TI agora podem verificar o status da licença do usuário e o status dos aplicativos da política de proteção de aplicativo atribuídos aos usuários na folha Solução de Problemas. Para obter detalhes, consulte [Solução de problemas](./help-desk-operators.md).

### Configuração do dispositivo
<a id="device-configuration" class="xliff"></a>

#### Controlar visitas ao site em dispositivos iOS <!-- 723832 -->
<a id="control-website-visits-on-ios-devices----723832---" class="xliff"></a>

Agora você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois seguintes métodos:

- Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.

- Permita que apenas sites especificado sejam acessados pelo navegador Safari. Para cada site que você especificar são criados indicadores no Safari.

Para obter mais informações, consulte [Configurações de filtro de conteúdo da Web para dispositivos iOS](web-content-filter-settings-ios.md).

#### Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 -->
<a id="preconfigure-device-permissions-for-android-for-work-apps----621614---" class="xliff"></a>

Para aplicativos implantados em perfis de trabalho de dispositivos Android for Work, agora é possível configurar o estado de permissões em aplicativos individuais.  Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.  Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone. Esse recurso permite definir permissões em nome do usuário final.  É possível configurar permissões para a) negar automaticamente sem notificar o usuário; b) aprovar automaticamente sem notificar o usuário ou c) solicitar que o usuário aceite ou recuse. Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

#### Definir PIN específico do aplicativo para dispositivos Android for Work <!-- 728976, 1102534 -->
<a id="define-app-specific-pin-for-android-for-work-devices----728976-1102534---" class="xliff"></a>

Dispositivos Android 7.0 e superior com um perfil de trabalho gerenciados como um dispositivo Android for Work possibilitam ao administrador definir uma política de senha que se aplica somente aos aplicativos no perfil de trabalho.  As opções incluem:

- Definir apenas uma política de senha em todo o dispositivo – essa é a senha que o usuário deve usar para desbloquear seu dispositivo inteiro.
 Definir apenas uma política de senha de perfil de trabalho – os usuários deverão inserir uma senha sempre que um aplicativo no perfil de trabalho for aberto.
- Definir uma política de dispositivo e de perfil de trabalho – o administrador de TI tem a opção de definir uma política de senha de dispositivo e uma política de senha de perfil de trabalho em diferentes níveis (por exemplo, um PIN de quatro dígitos para desbloquear o dispositivo, mas um PIN de seis dígitos para abrir um aplicativo de trabalho).

Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Isso está disponível somente no Android 7.0 e superior.  Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.

#### Novas configurações para dispositivos Windows 10 <!-- 978585 -->
<a id="new-settings-for-windows-10-devices----978585---" class="xliff"></a>

Adicionamos novas [configurações de restrição de dispositivos Windows](device-restrictions-windows-10.md) que controlam recursos como vídeos sem fio, descoberta de dispositivo, alternância de tarefas e mensagens de erro do cartão SIM.

#### Atualizações da configuração de certificado <!-- 918991 and 823198 -->
<a id="updates-to-certificate-configuration----918991-and-823198---" class="xliff"></a>

Ao criar um perfil de certificado SCEP, em **Formato do nome da entidade**, a opção **Personalizado** está disponível para dispositivos iOS, Android e Windows. Antes dessa atualização, o campo **Personalizado** estava disponível apenas para dispositivos iOS. Para obter mais informações, consulte [Como criar um perfil de certificado SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Ao criar um perfil de certificado PKCS, em **Nome alternativo da entidade**, o **Atributo personalizado do Azure AD** está disponível. A opção **Departamento** fica disponível quando você seleciona **Atributo personalizado do Azure AD**. Para obter mais informações, consulte [Como criar um perfil de certificado PKCS] (certificates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### Configurar vários aplicativos que podem ser executados quando um dispositivo Android está no modo de quiosque <!-- 662059 -->
<a id="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---" class="xliff"></a>

Anteriormente, quando um dispositivo Android estava no modo de quiosque, era possível configurar apenas um aplicativo que tinha permissão para ser executado. Agora é possível configurar vários aplicativos usando a ID do aplicativo, a URL da loja ou selecionando um aplicativo Android já gerenciado. Para obter mais informações, consulte [Configurações do modo de quiosque](device-restrictions-android.md#kiosk).


## Avisos
<a id="notices" class="xliff"></a>

### Endereços IP atualizados para o Intune <!-- 1175274 -->
<a id="ip-addresses-for-intune-updated----1175274---" class="xliff"></a>

Uma [lista atualizada de nomes DNS e endereços IP](/intune/network-bandwidth-use) está disponível para as configurações de proxy do firewall.

### Usar o Azure Active Directory para o acesso condicional <!-- 967947 -->
<a id="use-azure-active-directory-for-conditional-access----967947---" class="xliff"></a>

O acesso condicional está disponível na seção Azure Active Directory do console do Azure e fornece uma estrutura mais avançada e flexível para definir políticas para aplicativos na nuvem como o Office 365 Exchange Online e o SharePoint Online.  Use a folha **Acesso condicional no Azure Active Directory** para configurar políticas em vez do console clássico do Intune. As políticas existentes no console clássico do Intune precisam ser recriadas no console do Azure. Para obter mais informações, consulte [Criar políticas de acesso condicional do Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### Acesso direto aos cenários de registro da Apple <!--951869-->
<a id="direct-access-to-apple-enrollment-scenarios---951869--" class="xliff"></a>

Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência, caso sua conta existente não possa acessar o portal do Azure.

### Funções de administração que estão sendo substituídas no Portal do Azure
<a id="administration-roles-being-replaced-in-azure-portal" class="xliff"></a>

As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure. Após a migração para o portal do Azure, você precisará reatribuir essas novas funções de administração aos administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune/role-based-access-control).

## O que está por vir
<a id="whats-coming" class="xliff"></a>

### Lembrete de suporte de plataforma: o suporte base do Windows Phone 8.1 terminará em 11 de julho de 2017
<a id="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017" class="xliff"></a>
<!-- 1327781 -->

Em 11 de julho de 2017, a plataforma Windows Phone 8.1 chegará ao fim do suporte base. O suporte da versão Windows 8.1 de computador não é afetado.

Não há nenhum impacto imediato para qualquer dispositivo Windows Phone 8.1 que é gerenciado pelo serviço do Intune. Dispositivos registrados continuarão a funcionar e todas as políticas, configurações e aplicativos continuarão a funcionar como esperado. Observe que não há nenhuma melhoria voltada para a plataforma Windows Phone 8.1 no Serviço do Intune e para o aplicativo de Portal da Empresa do Windows Phone 8.1. 

É recomendável que você atualize os dispositivos Windows Phone 8.1 qualificados para Windows 10 Mobile assim que possível. 

### Alterações no suporte para o aplicativo do Portal da Empresa iOS do Intune  <!-- 1164474  -->
<a id="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----" class="xliff"></a>


Em breve, haverá uma nova versão do aplicativo do Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 9.0 ou posterior. A versão do Portal da Empresa que dá suporte ao iOS 8 ainda estará disponível por um breve período. No entanto, observe que se você também usa aplicativos iOS habilitados para MAM, também damos suporte a iOS 9.0 e posterior, por isso é recomendável verificar se os usuários finais atualizaram para o sistema operacional mais recente. 

#### Como isso me afeta?
<a id="how-does-this-affect-me" class="xliff"></a>
Estamos informando isso com antecedência, mesmo que não tenhamos datas específicas, para que você tenha tempo de planejar. Verifique se os usuários são atualizados para iOS 9 ou superior e, quando o aplicativo do Portal da Empresa for lançado, solicite que os usuários finais atualizem o aplicativo de Portal da Empresa.

#### O que preciso fazer para me preparar para essa alteração?
<a id="what-do-i-need-to-do-to-prepare-for-this-change" class="xliff"></a>

Recomendamos que os usuários atualizem para o iOS 9.0 ou posterior para que eles aproveitem os novos recursos do Intune.  Incentive os usuários a instalarem a nova versão do Portal da Empresa e aproveitar os novos recursos que ele oferece.

Acesse o Intune no Portal do Azure e exiba Dispositivos > Todos os Dispositivos e filtre por versão do iOS para ver os dispositivos atuais com os sistemas operacionais anteriores ao iOS 9.

### Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123-->
<a id="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--" class="xliff"></a>

Anunciamos uma alteração que entrará em vigor nos próximos meses, que visa melhorar a experiência de entrada para os aplicativos do Portal da Empresa do Intune para Android, iOS e Windows. A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração. Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único. Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.

Para ver capturas de tela da experiência de entrada anterior, a nova experiência de entrada com credenciais e a nova experiência de entrada em outro dispositivo, consulte [Novidades da interface do usuário do aplicativo](/intune/whats-new-app-ui).

### Planejar mudanças: o Intune está mudando a experiência do Portal do Parceiro <!-- 1050016 -->
<a id="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---" class="xliff"></a>

Vamos remover a página do Parceiro do Microsoft Intune em manage.microsoft.com, a partir da atualização do serviço em meados de maio de 2017.  

Se você for um administrador de parceiro, não será mais possível exibir conteúdo e tomar medidas em nome de seus clientes na página de Parceiro do Microsoft Intune. Em vez disso, deverá entrar em um dos outros Portais de Parceiro da Microsoft.

O [Microsoft Partner Center](https://partnercenter.microsoft.com/) e o [Centro de administração do parceiro do Office 365](https://portal.office.com/) permitem entrar nas contas de clientes que você gerencia. Avançando como parceiro, use um desse sites para gerenciar os clientes.


### Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->
<a id="apple-to-require-updates-for-application-transport-security---748318--" class="xliff"></a>

A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS.

Disponibilizamos uma versão do aplicativo Portal da Empresa para iOS por meio do programa TestFlight da Apple, que impõe os novos requisitos de ATS. Se quiser experimentá-lo a fim de testar a conformidade com a ATS, envie um email para <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> informando seu nome e sobrenome, endereço de email e nome da empresa. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### Consulte também
<a id="see-also" class="xliff"></a>
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
