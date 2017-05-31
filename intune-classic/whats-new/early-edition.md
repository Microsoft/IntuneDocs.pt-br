---
title: "Edição antecipada | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>A Edição Antecipada do Microsoft Intune – maio de 2017

A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
> As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Suporte de logon único do Portal da empresa para iOS com o Outlook para iOS <!--834012-->

Os usuários não precisarão mais entrar no aplicativo do Outlook se estiverem conectados no aplicativo de Portal da empresa para iOS no mesmo dispositivo com a mesma conta. Quando os usuários iniciarem o aplicativo do Outlook, eles poderão selecionar sua conta e se conectar automaticamente. Também estamos trabalhando para adicionar essa funcionalidade para outros aplicativos da Microsoft.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notificação aprimorada para PINs de inicialização do Samsung KNOX<!--1087143-->

Quando os usuários finais precisam definir um PIN de inicialização em dispositivos do Samsung KNOX para se tornarem compatíveis com criptografia, a notificação exibida para os usuários finais os levará para o local exato no aplicativo de configurações quando a notificação é tocada.  Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Promover a versão mais atual do Portal da Empresa para Android <!--1098661-->

Os usuários finais verão uma notificação no aplicativo quando uma nova versão recomendada do aplicativo Portal da Empresa para Android tiver sido liberada na tela de notificações do aplicativo. Essa notificação informará aos usuários que uma "Atualização do Portal da Empresa está disponível". Tocar a notificação abrirá uma página da Web mostrando a lista de lojas de aplicativos disponíveis onde eles podem baixar a versão atualizada. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!-- 676505 -->

O Portal da Empresa para o Windows 10 iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo para dispositivos com a Atualização do Windows 10 para Criadores (1704). Isso reduzirá o problema de paralisação de instalações de aplicativo durante o estado de "Sincronização pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo. 

O Portal da Empresa para o Windows 10 também expõe um botão de atualização para permitir que o usuário atualize o conteúdo no aplicativo sempre que necessário. 

## <a name="notices"></a>Avisos

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->

Para contas do Intune criadas depois de janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho de registrar dispositivos na Versão Prévia do Portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Quais são as novidades para Appx do Intune no Azure <!-- 1000270 -->

Como parte da migração para o Intune no Azure, estamos fazendo três alterações de appx:

1. Adição de um novo tipo de aplicativo appx no console clássico do Intune que somente pode ser implantado em dispositivos registrados MDM.
2. Adaptação do tipo de aplicativo appx existente para ser direcionado somente para computadores gerenciados por meio do agente Intune PC.
3. Conversão de todos os appxs existentes em appxs MDM com a migração.

Isso não afetará nenhuma de suas implantações existentes para dispositivos que são gerenciados por meio do agente Intune PC. No entanto, após a migração, você não poderá implantar esses appxs migrados nos novos dispositivos que são gerenciados por meio do agente Intune PC que não foram anteriormente direcionados.

Após a migração, você precisará recarregar o appx novamente como um appx de PC se quiser fazer novas implantações de PC. Para obter mais informações, consulte [Alterações de appx no Intune no Azure](https://aka.ms/appxchange) no blog da equipe de suporte do Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Visualização pública da nova experiência do administrador do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/intune/what-is-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->

Você poderá configurar os aplicativos Android na Play Store que oferecem suporte a opções de configuração gerenciada.  Esse recurso permite que você exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### <a name="remote-assistance-for-android-devices----675418---"></a>Assistência remota para dispositivos Android <!-- 675418 -->

Intune usará o software [TeamViewer](https://www.teamviewer.com), adquirido separadamente, para que você possa dar assistência remota a usuários que estão utilizando dispositivos Android.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 -->

Para aplicativos implantados para perfis de trabalho de dispositivos Android for Work, você poderá configurar o estado de permissões para aplicativos individuais. Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.  Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone. Esse recurso permitirá que você defina permissões em nome do usuário final.  O administrador pode configurar permissões para

- Negar automaticamente sem notificar o usuário
- Aprovar automaticamente sem notificar o usuário
- Avise o usuário para aceitar ou recusar.

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Definir PIN específico do aplicativo para dispositivos Android for Work <!--728976-->

Você poderá definir uma política de senha que só se aplica a aplicativos no perfil de trabalho para dispositivos Android 7.0 e acima gerenciados como um dispositivo Android for Work.  As opções incluem:

- Definir apenas uma política de senha em todo o dispositivo. Essa é a senha que o usuário final deve usar para desbloquear seu dispositivo inteiro
- Definir apenas uma política de senha de perfil de trabalho. Os usuários finais serão solicitados a digitar uma senha sempre que qualquer aplicativo no perfil de trabalho for aberto.
- Definir uma política de dispositivo e de perfil de trabalho. TI tem a opção de definir uma política de senha de dispositivo e uma política de senha do perfil de trabalho em diferentes níveis (por exemplo, um PIN de 4 dígitos para desbloquear o dispositivo, mas um PIN de 6 dígitos para abrir qualquer aplicativo de trabalho)

>[!NOTE]
> Isso só estará disponível no Android 7.0 e posterior.  Por padrão, o usuário final terá a opção de usar os dois PINs definidos separadamente ou eles podem optar por combinar os dois PINs definidos no mais forte dos dois.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Gerenciar senha e outras configurações do Android for Work <!--1102534-->

Estamos adicionando uma nova política de restrição para dispositivo Android for Work que lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Nova política de filtro de conteúdo da Web para dispositivos iOS <!-- 723832 -->

Você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois métodos a seguir:

  - Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.
  - Permita que apenas sites especificado sejam acessados pelo navegador Safari. Serão criados no Safari indicadores para cada site que você especificar.

### <a name="apple-school-manager-asm-support---748864--"></a>Suporte ao Gestor de Escola da Apple (ASM) <!--748864-->

O Intune dará suporte ao uso do Gestor de Escola da Apple (ASM) no lugar do Programa de Registro do Dispositivo da Apple para fornecer registros prontos de dispositivos iOS. A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS).  

### <a name="shared-ipad-support---770395-1044681---"></a>Suporte a iPad compartilhado <!--770395, 1044681 -->

O Intune oferecerá suporte à configuração do modo de iPad compartilhado no perfil de registro para Programa de Registro do Dispositivo da Apple ou Gestor de Escola da Apple. Essa configuração permite que várias IDs da Apple gerenciadas entrem no mesmo dispositivo.

Também expandiremos o suporte para gerenciar o aplicativo de sala de aula do iOS para incluir os alunos que fazem logon em iPads compartilhados usando a ID da Apple gerenciada.

### <a name="new-windows-device-restriction-settings---978585--"></a>Novas configurações de restrição de dispositivos no Windows <!--978585-->

Estamos adicionando configurações ao perfil de restrição de dispositivo do Windows que controlam os recursos como telas sem fio, descoberta de dispositivos, alternância de tarefas e mensagens de erro do cartão SIM.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Aplicativo Office 365 ProPlus disponível para dispositivos Windows 10 <!--1121362-->

Estamos adicionando o novo tipo de aplicativo Office 365 ProPlus que facilita a atribuição de aplicativos Office 365 ProPlus para dispositivos Windows 10. Além disso, você também poderá instalar o Microsoft Project e o Microsoft Visio, se possuir licenças para eles. Os aplicativos que você deseja serão reunidos e aparecerão como um aplicativo na lista de aplicativos no console do Intune.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Nova lista de permissão/bloqueio para o Managed Browser <!--682960-->

Você poderá configurar a lista de permissão/bloqueio de domínios e URLs para o Managed Browser com as configurações de aplicativo do Intune no Portal do Azure. Isso pode ser configurado para o Managed Browser, não importando se ele está sendo usado em um dispositivo gerenciado ou não.

### <a name="new-app-configuration-capabilities----677969---"></a>Novos recursos de configuração de aplicativo <!-- 677969 -->

Este recurso será equivalente à configuração de aplicativo do gerenciamento do dispositivo móvel (MDM). Ele permite que os administradores apliquem mais valores de configuração de aplicativo do que apenas valores de configuração disponíveis por meio de políticas de proteção de aplicativo no MAM sem canal de registro.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>Novas condições de políticas de proteção de aplicativo para MAM <!--679864-->

Você poderá definir um requisito para MAM sem os usuários do registro por meio do Console de administração que impõe o seguinte:

- Versão mínima do aplicativo
- Versão mínima do sistema operacional
- Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)

Esse recurso estará disponível para Android e iOS. O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune. No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK.

O usuário não poderá acessar o aplicativo de destino se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos 3 diferentes níveis mencionados acima. Neste ponto, o usuário pode tanto remover sua conta (para aplicativos de várias identidades), fechar o aplicativo e/ou atualizar o sistema operacional ou versão do aplicativo para atender ao requisito.

Além disso, você também poderá definir configurações adicionais por meio do Console de administração para fornecer uma notificação sem bloqueio que recomenda um sistema operacional ou atualização do aplicativo. Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950-->

Você poderá alterar sua autoridade MDM sem ter que entrar em contato com o Suporte da Microsoft e sem precisar cancelar o registro e registrar novamente os dispositivos gerenciados existentes. No console do Configuration Manager, você pode alterar sua autoridade MDM do conjunto para o Configuration Manager (híbrido) para o Microsoft Intune (autônomo) ou vice-versa.


### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.

