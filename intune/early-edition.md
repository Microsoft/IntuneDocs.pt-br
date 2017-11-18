---
title: "Edição antecipada"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f7cc595655950ef1bf2586e939b6f02e270e7afc
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>A edição antecipada do Microsoft Intune – Novembro de 2017

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


### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **integrado** tornará mais fácil para você criar e atribuir os aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Suporte para logon único para iOS <!-- 1333645 -->  
Você poderá usar o Logon Único para usuários do iOS. Os aplicativos iOS que são codificados para exigir credenciais do usuário no conteúdo do Logon Único são compatíveis com essa atualização de configuração de conteúdo. Você também pode usar o UPN e a ID de Dispositivo do Intune para configurar o Nome da entidade e o Realm.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API do inventário de aplicativos iOS 11 para detecção de ameaças móveis <!-- 1391759 -->
O Intune coleta informações do inventário de aplicativos em dispositivos pessoais e corporativos e as disponibiliza para provedores de Detecção de Ameaça Móvel (MTD) para efetuar o fetch, como Lookout for Work. Você poderá coletar o inventário de aplicativos dos usuários de dispositivos iOS 11+.

**Inventário de aplicativos**  
Inventários de dispositivos pessoais e corporativos iOS 11+ são enviados para o provedor de serviços de MTD. Os dados de inventário de aplicativos incluem:

 - ID do aplicativo
 - Versão de Aplicativo
 - Versão Curta do Aplicativo
 - Nome do Aplicativo
 - Tamanho do Pacote do Aplicativo
 - Tamanho Dinâmico do Aplicativo
 - O Aplicativo é validado ou não
 - O Aplicativo é gerenciado ou não

### <a name="audit-updates----1412961---"></a>Atualizações de auditoria <!-- 1412961 -->  
A auditoria do Intune fornece um registro das operações de alteração relacionadas ao Intune.  Todas as operações de criação, atualização, exclusão e de tarefa remota são capturadas e mantidas por um ano.  O portal do Azure fornece uma exibição dos últimos 30 dias de dados de auditoria em cada carga de trabalho e pode ser filtrado.  Uma API do Graph correspondente permite a recuperação dos dados de auditoria armazenados para o último ano. 

A auditoria é encontrada no grupo **MONITOR**. Há um item de menu de **Logs de Auditoria** para cada carga de trabalho.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocolo de texto permitido em Aplicativos gerenciados <!-- 1414050  -->
Aplicativos gerenciados pelo SDK do Aplicativo do Intune poderão enviar mensagens SMS.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Reiniciar remotamente o dispositivo iOS (somente supervisionado) <!-- 1424595 -->
Você poderá disparar um dispositivo iOS 10.3+ supervisionado para reiniciar usando uma ação do dispositivo. Para obter mais informações sobre como usar a ação de reinício de dispositivo, consulte [Reiniciar remotamente dispositivos com o Intune](device-restart.md).

> [!Note]  
> Este comando requer um dispositivo supervisionado e o direito de acesso de **Bloqueio de Dispositivo**. O dispositivo é reiniciado imediatamente. Dispositivos iOS protegidos por senha não serão reconectados a uma rede Wi-Fi após a reinicialização; Após a reinicialização, é possível que eles não se comuniquem com o servidor.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Bloquear dispositivos macOS gerenciados remotamente com o Intune <!-- 1437691 -->
Você poderá bloquear um dispositivo macOS perdido e definir um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

Para obter mais informações, consulte [Bloquear dispositivos gerenciados remotamente com o Intune](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Configurações de frequência do relatório da Proteção Avançada contra Ameaças do Windows Defender <!--- 1455974  --->
O serviço de Proteção Avançada contra Ameaças (WDATP) do Windows Defender permite que os administradores gerenciem a frequência dos relatórios para dispositivos gerenciados. Com a nova opção de **Agilizar a frequência de relatórios de telemetria**, o WDATP coleta dados e avalia os riscos com mais frequência. O padrão para relatórios otimiza a velocidade e o desempenho. Aumentar a frequência de emissão de relatórios pode ser importante para dispositivos de alto risco. Essa configuração pode ser encontrada no perfil **Windows Defender ATP** nas **Configurações do dispositivo**.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>A resolução de conflitos de atribuição foi alterada para aplicativos da iOS store <!-- 1480316 -->
Os usuários finais podem perceber alguma alteração na disponibilidade de aplicativos iOS store. No momento, um aplicativo que foi atribuído a dois grupos com um conflito entre **Necessário e Disponível** e **Não Aplicável**, é resolvido para **Necessário e Disponível**. Com a alteração, um aplicativo com este conflito é resolvido para **Não Aplicável**.

A alteração elimina a confusão quando um aplicativo é atribuído a vários grupos com propósitos de aplicativo diferentes.

Se você gostaria de ter seu aplicativo disponível no Portal do Operador de informações e no Portal da Empresa antes do lançamento do serviço em novembro, você tem duas opções:

1. Remover a atribuição **Não Aplicável** de seu grupo.
2. Criar um novo grupo que não inclui membros com a finalidade **Necessário e Disponível** atribuída e atribuir esse grupo como **Não Aplicável**.

Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

> [!Note]
> Após o lançamento você não poderá exibir ou modificar atribuições de aplicativo de Gerenciamento de Dispositivo Móvel (MDM) no console do Intune clássico. No entanto, você pode usar o console do Azure ou a API do Graph Intune para fazer atribuições de seu aplicativo.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Gerenciar dispositivos Android for Work independentemente dos dispositivos Android <!-- 1490731 -->
O Intune oferecerá suporte ao gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

Por padrão, as configurações de dispositivos Android for Work serão as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.
 
Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

Ao trabalhar com as novas configurações, considere o seguinte:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Se você nunca integrou o registro de Android for Work antes
A plataforma Android for Work está bloqueada nas restrições de Tipo de Dispositivo padrão. Após integrar o recurso, você poderá permitir que dispositivos se registrem com Android for Work. Para fazer isso, altere o padrão ou crie uma nova restrição de Tipo de Dispositivo para substituir a restrição padrão de Tipo de Dispositivo.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Se você tiver integrado o registro de Android for Work
Se você já tiver integrado antes, sua situação dependerá da configuração que escolher:

| Setting | Status de Android for Work na Restrição de Tipo de Dispositivo padrão | Anotações |
| --- | --- | --- |
| **Gerenciar todos os dispositivos como Android** | Bloqueado | Todos os dispositivos Android devem se registrar sem o Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work** | Permitido | Todos os dispositivos que oferecem suporte ao Android for Work devem ser registrados com Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work somente para os usuários nestes grupos** | Bloqueado | Uma política de Restrição de Tipo de Dispositivo separada foi criada para substituir o padrão. Essa política define os grupos que você selecionou anteriormente para permitir o registro Android for Work. Usuários dentro dos grupos selecionados ainda poderão registrar seus dispositivos Android for Work. Todos os outros usuários são impedidos de se registrar com o Android for Work. |

Em todos os casos, a norma pretendida é preservada. Nenhuma ação é necessária de sua parte para manter a permissão global ou por grupo do Android for Work em seu ambiente.

Essas alterações começarão a distribuição com a atualização de novembro, mas podem levar tempo para serem executadas em sua conta. Você receberá uma notificação de confirmação no portal do Office 365 quando essas alterações entrarem em vigor para a sua conta.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Suporte para vários conectores do Serviço de Registro de Dispositivo de Rede (NDES) <!-- 1528104 -->
O NDES permite a execução de dispositivos móveis sem credenciais de domínio para obter certificados baseados no protocolo SCEP. Com essa atualização, vários conectores NDES terão suporte.

### <a name="new-scep-profile-details-supported----1559808---"></a>Novos detalhes do perfil de SCEP com suporte <!-- 1559808 -->
Os administradores poderão definir configurações adicionais ao criar um perfil de SCEP em plataformas Android, Windows, iOS e macOS.  Os administradores podem definir o IMEI, o número ou o nome comum incluindo email no formato de nome do assunto.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurar um PIN de aplicativo iOS <!-- 1586774 -->
Em breve, você poderá exigir um PIN para aplicativos iOS determinados. Você pode configurar o requisito e a data de vencimento do PIN em dias por meio do portal do Azure. Quando necessário, um usuário deverá definir e usar um novo PIN antes de receber o acesso a um aplicativo iOS. Apenas os aplicativos iOS que têm a proteção de aplicativo habilitada com o SDK de Aplicativo do Intune oferecerão suporte a esse recurso.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Manter dados durante uma redefinição de fábrica <!-- 1588489 -->
Estamos adicionando o suporte a uma nova funcionalidade de redefinição de Fábrica do Windows. Agora, os administradores puderem especificar se o registro de dispositivo e outros dados fornecidos serão mantidos em um dispositivo após uma redefinição de fábrica. 
 
Os seguintes dados são mantidos após a redefinição de fábrica:
- Contas do usuário associadas ao dispositivo
- Estado do computador (ingresso no domínio, AADJ)
- Registro do MDM
- Aplicativos instalados pelo OEM (aplicativos do Win32 e da loja)
- Perfil de usuário
- Dados do usuário de fora do perfil do usuário
- Logon automático do usuário
 
Os dados a seguir não são preservados:
- Arquivos do usuário
- Aplicativos instalados pelo usuário (aplicativos do Win32 e da loja)
- Configurações do dispositivo não padrão 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>O status de instalação do aplicativo agora informa um gráfico de barras <!-- 1249446 -->  
O relatório de **Status de instalação do aplicativo** acessível para cada aplicativo por meio da lista de **Aplicativos** na carga de trabalho de **Aplicativos móveis** em breve serão renderizados como um gráfico de barras.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Adicionar "Encontrar meu iPhone" para dispositivos pessoais <!--1427287-->
Você poderá exibir se os dispositivos iOS têm o Bloqueio de Ativação ativado. Esse recurso podia ser encontrado anteriormente no portal clássico do Intune.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrições de registro atribuídas pelo grupo <!-- 747598 -->
Como um administrador do Intune, você poderá criar restrições personalizadas de registro de Tipo de Dispositivo e de Limite do Dispositivo para grupos de usuários.
 
O Portal do Azure do Intune permite criar até 25 instâncias de cada tipo de restrição que podem ser atribuídas a grupos de usuários. Restrições atribuídas a grupos substituem as restrições padrão.
 
Todas as instâncias de um tipo de restrição são mantidas em uma lista estritamente ordenada. Essa ordem define um valor de prioridade para resolução de conflitos. Um usuário afetado por mais de uma instância de restrição é restringido apenas pela instância com o valor de prioridade mais elevado. Você pode alterar a prioridade de uma determinada instância arrastando-a para uma posição diferente na lista. 
 
Essa funcionalidade será lançada com a migração das configurações de Android for Work no menu de registro do Android for Work para o menu de Restrições de Registro. Como esta migração pode levar vários dias, sua conta pode ser atualizada para outras partes do lançamento de novembro antes que você veja uma atribuição de grupo habilitada para Restrições de Registro.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Atribuições de anel de atualização do Windows 10 são exibidas <!-- 1621837 -->
Quando estiver **solucionando problemas,** para o usuário que estiver sendo exibido, você poderá ver todas as atribuições de anéis de atualização do Windows 10.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Solucionar problemas de registro  <!--- 746324 --->  
O espaço de trabalho da Solução de Problemas mostrará problemas de registro do usuário. Os detalhes sobre o problema e as etapas de correção sugeridas podem ajudar os administradores e os operadores de suporte técnico a solucionar problemas. Determinados problemas de registro não são capturados e alguns erros podem não ter as sugestões de correção.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672(archived), 1119689 -->  
Você poderá criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Suporte do Android for Work no Lookout <!-- 1087312 -->   
O conector do Intune com o Lookout dará suporte a dispositivos Android for Work ao usar o aplicativo Lookout for Work. Você pode implantar o aplicativo Lookout dentro ou fora do contêiner.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Proteção de Aplicativo do Intune e Ferramentas de Desenvolvimento do Citrix MDX <!-- 709185 -->
Você pode gerenciar dispositivos e aplicativos com uma combinação do Citrix XenMobile MDX e o Microsoft Intune. Isso permite que você gerencie aplicativos com políticas de proteção de aplicativo do Intune usando a tecnologia de mVPN da Citrix.

Você pode localizar um repositório de códigos que contém a Ferramenta de Encapsulamento de Aplicativo do Intune e o SDK de Aplicativo do Intune para iOS e Android, integrando com a tecnologia mVPN da Citrix MDX.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->   
Você pode ter várias funções de CAS (Servidor de Acesso de Cliente) para o Exchange Connector local. Por exemplo, se o CAS principal falhar, o Exchange Connector recebe uma consulta para voltar a outros CASs. Esse recurso garante que o serviço não seja interrompido.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pacote de gerenciamento do System Center Operations Manager para Exchange Connector <!-- 885457 -->   
O pacote de gerenciamento do System Center Operations Manager para o Exchange Connector estará disponível para ajudá-lo a analisar os logs do Exchange Connector. Esse pacote de gerenciamento oferece diferentes maneiras de monitorar o Intune quando você precisar solucionar problemas.





## <a name="intune-apps"></a>Aplicativos do Intune

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ajudando seus usuários com o aplicativo de Portal da Empresa para Android <!---1573324, 1573150, 1558616, 1564878--->
O aplicativo de Portal da Empresa para Android está adicionando instruções para os usuários finais para ajudá-los a compreender e, quando possível, resolver automaticamente novos casos de uso. 

- Uma nova mensagem será exibida que explica que foi implantada uma política de conformidade para criptografia, mas o [fabricante do dispositivo não está criptografando o dispositivo](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) de acordo com as [diretrizes recomendadas do Google] (https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, booliano).
- Os usuários finais serão direcionados para o (portal do Azure Active Directory) [https://account.activedirectory.windowsazure.com/r/#/profile] para remover um dispositivo se tiverem atingido o número máximo de dispositivos que eles têm permissão para adicionar. 
- Os usuários finais devem seguir as etapas para ajudá-los a [corrigir erros de ativação em dispositivos Samsung KNOX](https://go.microsoft.com/fwlink/?linkid=859718) ou [desligar o modo de economia de energia](/intune-user-help/power-saving-mode-android). Se nenhuma dessas soluções resolver o problema, fornecemos uma explicação de como [enviar logs para a Microsoft](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nova ação “Resolver” disponível para dispositivos Android <!---1583480--->
O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android atualmente dá suporte a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [criptografia do dispositivo](/intune-user-help/encrypt-your-device-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirecionando usuários do macOS para nosso novo aplicativo do Portal da Empresa <!--1380728-->   
Quando um usuário final fizer o logon no site do Portal da Empresa para registrar seu dispositivo macOS, ele será direcionado a baixar o novo aplicativo do Portal da Empresa para macOS a fim de concluir o processo. Isso ocorre em dispositivos macOS usando OS X El Capitan 10.11 ou superior. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->
Os aplicativos da empresa que foram disponibilizados com ou sem a inscrição no aplicativo Portal da Empresa Android podem ser instalados sem uma solicitação de inscrição.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Suporte do Intune Managed Browser para iOS e Android <!-- 1374196 -->
A partir de outubro de 2017, o aplicativo do Intune Managed Browser no aplicativo do Android oferecerá suporte apenas a dispositivos que executam o Android 4.4 e versões posteriores. O aplicativo Intune Managed Browser no iOS oferecerá suporte apenas a dispositivos que executam o iOS 9.0 e versões posteriores. Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."




## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.




### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
