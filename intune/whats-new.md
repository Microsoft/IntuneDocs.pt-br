---
title: Novidades do Microsoft Intune
titlesuffix: Azure portal
description: "Conheça as novidades do portal do Intune no Azure"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5575d02d0c270e9d22e4b858d8fb00753b60448
ms.sourcegitcommit: 5ecb0d6625e6972cc5ccdca7538f41f4aa8da46a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Conheça as novidades de cada semana do Microsoft Intune. Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md).

> [!Note]
> Para obter informações sobre a nova funcionalidade no MDM (Gerenciamento de Dispositivo Móvel) híbrido, confira nossa [página Novidades híbrida](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-december-11-2017"></a>Semana de 11 de dezembro de 2017

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nova configuração automática de reimplantação <!-- 1469168 -->
Essa configuração de **Reimplantação automática** permite que usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **Ctrl+Win+R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento. Essa configuração pode ser encontrada em Windows 10 > Restrições de dispositivo > Geral > Reimplantação automática. Para obter mais detalhes, confira [Configurações de restrição de dispositivo do Intune para Windows 10](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Suporte para as edições de origem adicionais na política de atualização de edição do Windows 10 <!-- 903672,  1119689 -->
Agora você pode usar a política de atualização de edição do Windows 10 para atualizar de edições adicionais do Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud etc.). Antes desta versão, os caminhos de atualização de edição com suporte eram mais limitados. Para obter detalhes, confira [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Novas definições do perfil de configuração de dispositivo da WDSC (Central de Segurança do Windows Defender) <!-- 1335507 -->

O Intune adiciona uma nova seção de configurações de perfil de configuração de dispositivo sob a Proteção de ponto de extremidade chamada **Central de Segurança do Windows Defender**. Os administradores de TI podem configurar quais pilares do aplicativo Central de Segurança do Windows Defender os usuários finais podem acessar. Se um administrador de TI ocultar um pilar no aplicativo Central de Segurança do Windows Defender, todas as notificações relacionadas ao pilar oculto não serão exibidas no dispositivo do usuário.

Estes são os pilares que os administradores podem ocultar nas configurações do perfil de configuração de dispositivo da Central de Segurança do Windows Defender:
- Proteção contra vírus e ameaças
- Desempenho e integridade do dispositivo
- Proteções de firewall e rede
- Controle de aplicativo e navegador
- Opções da família

Os administradores de TI também podem personalizar quais notificações os usuários recebem. Por exemplo, você pode configurar se os usuários recebem todas as notificações geradas por pilares visíveis na WDSC, ou apenas as notificações críticas. As notificações não críticas incluem resumos periódicos de atividades do Windows Defender Antivírus e notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas. Além disso, você também pode personalizar o conteúdo da própria notificação, por exemplo, você pode fornecer informações de contato da TI para incorporar as notificações que aparecem nos dispositivos dos usuários.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Suporte a vários conectores para manipulação de certificado SCEP e PFX <!-- 1361755 -->

Agora, os clientes que usam o conector NDES local para fornecer certificados a dispositivos podem configurar vários conectores em um único locatário.

Essa nova capacidade dá suporte ao seguinte cenário:

- **Alta disponibilidade**

Cada conector NDES efetua o pull de solicitações de certificado do Intune.  Se um conector NDES ficar offline, o outro conector poderá continuar processando solicitações.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Nome da entidade do cliente pode usar a variável AAD_DEVICE_ID <!-- 1468599 -->

Agora, ao criar um perfil de certificado SCEP no Intune, você pode usar a variável AAD_DEVICE_ID ao compilar o nome de entidade personalizado.   Quando o certificado é solicitado usando esse perfil SCEP, a variável é substituída pela ID do dispositivo AAD do dispositivo que está fazendo a solicitação de certificado.


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Gerenciar dispositivos macOS inscritos em Jamf com o mecanismo de conformidade do dispositivo do Intune <!-- 1592747 -->
Agora, você pode usar Jamf para enviar informações de estado do dispositivo macOS ao Intune, que, em seguida, avaliará a conformidade com as políticas definidas no console do Intune. Com base no estado de conformidade do dispositivo, bem como em outras condições (como local, risco de usuário etc.), o acesso condicional imporá a conformidade para dispositivos macOS que estão acessando aplicativos de nuvem e locais conectados com o Azure AD, incluindo o Office 365. Saiba mais sobre [como configurar a integração com Jamf](conditional-access-integrate-jamf.md) e [impor a conformidade para dispositivos gerenciados por Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nova ação do dispositivo iOS <!-- 1424701 -->

Agora, você pode desligar os dispositivos supervisionados com o iOS 10.3. Essa ação desliga o dispositivo imediatamente sem avisar o usuário final. A ação **Desligar (somente supervisionado)** pode ser encontrada nas propriedades do dispositivo quando você seleciona um dispositivo na carga de trabalho **Dispositivo**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Não permitir alterações de data/hora para dispositivos Samsung Knox<!-- 1468103 -->

Adicionamos um novo recurso que permite o bloqueio de alterações de data e hora em dispositivos Samsung Knox. Encontre isso nos **Perfis de configuração do dispositivo** > **Restrições de dispositivo (Android)** > **Geral**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Conta de recurso do Surface Hub com suporte <!-- 1566442  -->

Uma nova ação de dispositivo foi adicionada para que os administradores possam definir e atualizar a conta do recurso associada a um Surface Hub.

A conta do recurso é usada por um Surface Hub para autenticar com o Skype/Exchange a fim de ingressar em uma reunião. Você pode criar uma conta de recurso exclusiva para que o Surface Hub apareça na reunião como aparece na sala de conferência. Por exemplo, a conta do recurso pode aparecer como *Sala de conferência B41/6233*. A conta do recurso (conhecida como conta de dispositivo) para o Surface Hub normalmente precisa ser configurada para o local da sala de conferência, e quando outros parâmetros de conta de recurso precisam ser alterados.

Quando os administradores querem atualizar a conta do recurso em um dispositivo, eles devem fornecer as credenciais atuais do Active Directory/Azure Active Directory associadas ao dispositivo. Se a rotação de senha estiver ativada para o dispositivo, os administradores deverão acessar o Azure Active Directory para localizar a senha.

> [!NOTE]
> Todos os campos são enviados em um pacote, e substituem todos os campos que foram previamente configurados. Os campos vazios também são substituídos pelos campos existentes.

Veja a seguir as configurações que os administradores podem definir:

- **Conta de recurso**
   - **Usuário do Active Directory**

      Nomededomínio\nomedeusuário ou Nome UPN (UPN): user@domainname.com

   - **Senha**

- **Parâmetros opcionais da conta de recurso** (devem ser definidos usando a conta de recurso especificada)

   - **Período de rotação de senha**

     Certifique-se de que a senha da conta seja atualizada automaticamente pelo Surface Hub toda semana por motivos de segurança. Para configurar os parâmetros após essa habilitação, a conta no Azure Active Directory deve ter a senha redefinida primeiro.

   - **Endereço SIP (protocolo de iniciação de sessão)**

     Usado somente quando a descoberta automática falha.

   - **Email**

     Endereço de email da conta de recurso/do dispositivo.

   - **Exchange Server**

     Exigido somente quando a descoberta automática falha.

   - **Sincronização do calendário**

     Especifica se a sincronização de calendário, e outros serviços de servidor do Exchange, está habilitada. Por exemplo: sincronização de reunião.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalar aplicativos do Office em dispositivos macOS <!-- 1494311 -->
Agora, você pode instalar aplicativos do Office em dispositivos macOS. Esse novo tipo de aplicativo permitirá que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Esses aplicativos também são fornecidos com o MAU (Microsoft AutoUpdate), para ajudar a manter seus aplicativos seguros e atualizados.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Excluir um token de Programa de Compra por Volume do iOS <!-- 820879 -->
Você pode excluir o token do VPP (Programa de Compra por Volume) do iOS usando o console. Isso pode ser necessário quando houver instâncias duplicadas de um token VPP.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="end-user-messaging-for-accounts---1573558-for-1712--"></a>Mensagem do usuário final para contas <!--1573558 for 1712-->

Os usuários do site do Portal da Empresa serão impedidos de executar ações que exigem acesso de gravação em seu locatário. Eles verão a mensagem de erro apropriada explicando que a conta deles está em manutenção. Alterações semelhantes serão disponibilizadas em breve para os aplicativos de Portal da Empresa para Windows, macOS, iOS e Android. Veja esse erro em [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).



### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Uma nova coleção de entidade chamada Usuário Atual é limitada a usuários ativos no momento <!-- 1667026 -->

A coleção de entidades **Usuários** contém todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

Em contraste, a nova coleção de entidade **Usuário Atual** contém apenas os usuários que não foram removidos. A coleção de entidade **Usuário Atual** contém apenas usuários ativos no momento. Para saber mais sobre a coleção de entidade **usuário atual**, veja [Referência para a entidade de usuário atual](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>APIs do Graph atualizadas <!-- 1736360 -->

Nesta versão, atualizamos algumas das APIs do Graph para Intune que estão na versão beta. Confira o [log de alterações mensal da API do Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) para saber mais.


## <a name="week-of-december-4-2017"></a>Semana de 4 de dezembro de 2017

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>O Intune é compatível com aplicativos negados pela WIP (Proteção de Informações da Windows)<!-- 1479103 -->
Você pode especificar aplicativos negados no Intune. Se um aplicativo for negado, ele será impedida de acessar informações corporativas, efetivamente o oposto da lista de aplicativos permitidos. Para obter mais informações, consulte [Lista de negações recomendados para a Proteção de Informações do Windows](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>Semana de 27 de novembro de 2017

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Solucionar problemas de registro  <!-- 746324 -->

Agora o espaço de trabalho **Solução de problemas** mostra problemas de registro do usuário. Os detalhes sobre o problema e as etapas de correção sugeridas podem ajudar os administradores e os operadores de suporte técnico a solucionar problemas. Determinados problemas de registro não são capturados e alguns erros podem não ter as sugestões de correção.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrições de registro atribuídas pelo grupo <!-- 747598 -->

Como administrador do Intune, agora é possível [criar restrições personalizadas de registro de Tipo de dispositivo e de Limite de dispositivos para grupos de usuários](enrollment-restrictions-set.md).

O Portal do Azure do Intune permite criar até 25 instâncias de cada tipo de restrição que podem ser atribuídas a grupos de usuários. Restrições atribuídas a grupos substituem as restrições padrão.

Todas as instâncias de um tipo de restrição são mantidas em uma lista estritamente ordenada. Essa ordem define um valor de prioridade para resolução de conflitos. Um usuário afetado por mais de uma instância de restrição é restringido apenas pela instância com o valor de prioridade mais elevado. Você pode alterar a prioridade de uma determinada instância arrastando-a para uma posição diferente na lista.

Essa funcionalidade será lançada com a migração das configurações de Android for Work no menu de registro do Android for Work para o menu de Restrições de Registro. Como esta migração pode levar vários dias, sua conta pode ser atualizada para outras partes do lançamento de novembro antes que você veja uma atribuição de grupo habilitada para Restrições de Registro.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Suporte para vários conectores do Serviço de Registro de Dispositivo de Rede (NDES) <!-- 1528104 -->

O NDES permite a execução de dispositivos móveis sem credenciais de domínio para obter certificados baseados no protocolo SCEP.
Nesta atualização, há suporte a vários conectores NDES.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gerenciar dispositivos Android for Work independentemente dos dispositivos Android <!-- 1490731 EEready-->

**Observação**: as alterações a seguir começarão a serem distribuídas com a atualização de novembro, mas podem demorar para serem executadas em sua conta. Você receberá uma notificação de confirmação no portal do Office 365 quando essas alterações entrarem em vigor para a sua conta. Após a distribuição, você terá opções de capacidade de gerenciamento adicionais. Não haverá nenhuma alteração na experiência do usuário final durante a distribuição.

O Intune é compatível com gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

Por padrão, as configurações de dispositivos Android for Work são as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.

Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

Ao trabalhar com as novas configurações, considere o seguinte:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Se você nunca integrou o registro de Android for Work antes

A plataforma Android for Work está bloqueada nas restrições de Tipo de Dispositivo padrão. Após integrar o recurso, você poderá permitir que dispositivos se registrem com Android for Work. Para fazer isso, altere o padrão ou crie uma nova restrição de Tipo de Dispositivo para substituir a restrição padrão de Tipo de Dispositivo.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Se você tiver integrado o registro de Android for Work

Se você já tiver integrado antes, sua situação dependerá da configuração que escolher:

| Setting | Status de Android for Work na Restrição de Tipo de Dispositivo padrão | Anotações |
| --- | --- | --- |
| **Gerenciar todos os dispositivos como Android** | Bloqueado | Todos os dispositivos Android devem se registrar sem o Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work** | Permitido | Todos os dispositivos que oferecem suporte ao Android for Work devem ser registrados com Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work somente para os usuários nestes grupos** | Bloqueado | Uma política de Restrição de Tipo de Dispositivo separada foi criada para substituir o padrão. Essa política define os grupos que você selecionou anteriormente para permitir o registro Android for Work. Usuários dentro dos grupos selecionados ainda poderão registrar seus dispositivos Android for Work. Todos os outros usuários são impedidos de se registrar com o Android for Work. |

Em todos os casos, a norma pretendida é preservada. Nenhuma ação é necessária de sua parte para manter a permissão global ou por grupo do Android for Work em seu ambiente.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Relatório de instalação de aplicativos atualizado para incluir o status de Instalação pendente<!-- 1249446 -->  

O relatório **Status de instalação do aplicativo** acessível para cada aplicativo por meio da lista **Aplicativo** na carga de trabalho **Aplicativos móveis** agora contém uma contagem **Instalação pendente** para Usuários e Dispositivos.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API do inventário de aplicativos iOS 11 para detecção de ameaças móveis <!-- 1391759 -->

O Intune coleta informações do inventário de aplicativos em dispositivos pessoais e corporativos e as disponibiliza para provedores de Detecção de Ameaça Móvel (MTD) para efetuar o fetch, como Lookout for Work. É possível coletar um inventário de aplicativos dos usuários de dispositivos iOS 11+.

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


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrar usuários e dispositivos do MDM híbrido para o <!-- 1463747 wnready --> autônomo do Intune
Temos um novo processo e ferramentas para mover os usuários e seus dispositivos do MDM híbrido para o Intune no portal do Azure, o que permite que você faça o seguinte:
- Copiar perfis e políticas do console do Configuration Manager para o Intune no portal do Azure
- Mover um subconjunto de usuários ao Intune no portal do Azure enquanto mantém o restante no MDM híbrido
- Migrar os dispositivos para o Intune no portal do Azure sem necessidade de registrá-los novamente

Consulte os detalhes em [Migrar usuários e dispositivos do MDM híbrido para o Intune autônomo](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->
Após o Exchange Connector criar uma conexão com o Exchange usando o CAS especificado, o conector terá a capacidade de descobrir outros CASs. Se o CAS principal ficar desabilitado, o conector realizará o failover para outro CAS, se houver um disponível, até que o CAS principal fique disponível. Para obter detalhes, confira [Suporte de alta disponibilidade do Exchange Connector local](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Reiniciar remotamente o dispositivo iOS (somente supervisionado) <!-- 1424595 -->

Agora é possível disparar um dispositivo iOS 10.3+ supervisionado para reiniciar usando uma ação do dispositivo. Para obter mais informações sobre como usar a ação de reinício de dispositivo, consulte [Reiniciar remotamente dispositivos com o Intune](device-restart.md).

> [!Note]
> Este comando requer um dispositivo supervisionado e o direito de acesso de **Bloqueio de Dispositivo**. O dispositivo é reiniciado imediatamente. Dispositivos iOS protegidos por senha não serão reconectados a uma rede Wi-Fi após a reinicialização; Após a reinicialização, é possível que eles não se comuniquem com o servidor.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Suporte para logon único para iOS <!-- 1333645 -->  

Você pode usar o Logon Único para usuários do iOS. Os aplicativos iOS que são codificados para exigir credenciais do usuário no conteúdo do Logon Único são compatíveis com essa atualização de configuração de conteúdo. Você também pode usar o UPN e a ID de Dispositivo do Intune para configurar o Nome da entidade e o Realm. Para obter detalhes, consulte [Configurar o Intune para logon único de dispositivo iOS](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Adicionar "Encontrar meu iPhone" para dispositivos pessoais <!--1427287-->
Agora você pode exibir se os dispositivos iOS têm o Bloqueio de Ativação ligado. Esse recurso podia ser encontrado anteriormente no portal clássico do Intune.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Bloquear dispositivos macOS gerenciados remotamente com o Intune <!-- 1437691 -->

É possível bloquear um dispositivo macOS perdido e definir um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

Para obter mais informações, consulte [Bloquear dispositivos gerenciados remotamente com o Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Novos detalhes do perfil de SCEP com suporte <!-- 1559808 -->

Agora os administradores podem definir configurações adicionais ao criar um perfil SCEP em plataformas Windows, iOS, macOS e Android.  Os administradores podem definir o IMEI, o número ou o nome comum incluindo email no formato de nome do assunto.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Manter dados durante uma redefinição de fábrica <!--1588489 -->
Ao restaurar o Windows 10 versão 1709 e posterior para as configurações de fábrica, uma nova funcionalidade estará disponível. Os administradores poderão especificar se o registro de dispositivo e outros dados provisionados serão mantidos em um dispositivo por meio de uma redefinição de fábrica.

Os seguintes dados são mantidos após a redefinição de fábrica:
- Contas do usuário associadas ao dispositivo
- Estado do computador (ingresso no domínio, ingressado no Azure Active Directory)
- Registro do MDM
- Aplicativos instalados pelo OEM (aplicativos do Win32 e da loja)
- Perfil de usuário
- Dados do usuário de fora do perfil do usuário
- Logon automático do usuário

Os dados a seguir não são mantidos:
- Arquivos do usuário
- Aplicativos instalados pelo usuário (aplicativos do Win32 e da loja)
- Configurações do dispositivo não padrão

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>As atribuições de anel de atualização do Windows 10 são exibidas <!-- 1621837 -->
Quando estiver **solucionando problemas** para o usuário que estiver sendo exibido, será possível ver as atribuições de anéis de atualização do Windows 10.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Configurações de frequência do relatório da Proteção Avançada contra Ameaças do Windows Defender <!-- 1455974  -->
O serviço de Proteção Avançada contra Ameaças (WDATP) do Windows Defender permite que os administradores gerenciem a frequência dos relatórios para dispositivos gerenciados. Com a nova opção de **Agilizar a frequência de relatórios de telemetria**, o WDATP coleta dados e avalia os riscos com mais frequência. O padrão para relatórios otimiza a velocidade e o desempenho. Aumentar a frequência de emissão de relatórios pode ser importante para dispositivos de alto risco. Essa configuração pode ser encontrada no perfil **Windows Defender ATP** nas **Configurações do dispositivo**.

#### <a name="audit-updates----1412961---"></a>Atualizações de auditoria <!-- 1412961 -->  
A auditoria do Intune fornece um registro das operações de alteração relacionadas ao Intune.  Todas as operações de criação, atualização, exclusão e de tarefa remota são capturadas e mantidas por um ano.  O portal do Azure fornece uma exibição dos últimos 30 dias de dados de auditoria em cada carga de trabalho e pode ser filtrado.  Uma API do Graph correspondente permite a recuperação dos dados de auditoria armazenados para o último ano.

A auditoria é encontrada no grupo **MONITOR**. Há um item de menu de **Logs de Auditoria** para cada carga de trabalho.




## <a name="week-of-november-20-2017"></a>Semana de 20 de novembro de 2017

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="google-play-protect-support-on-android----908720---"></a>Suporte para Google Play Protect no Android <!-- 908720 -->

Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. O Intune oferecerá suporte aos recursos do Google Play Protect, incluindo atestado remoto do SafetyNet. Os administradores podem definir requisitos de política de conformidade que exigem a configuração e a integridade do Google Play Protect.
A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play. O acesso condicional pode impedir que os usuários acessem recursos corporativos, se um dispositivo não for compatível com os requisitos do Google Play Protect.

- Saiba [Como criar uma política de conformidade do dispositivo para habilitar o Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocolo de texto permitido em Aplicativos gerenciados <!-- 1414050  -->

Aplicativos gerenciados pelo SDK do Aplicativo do Intune podem enviar mensagens SMS.

## <a name="week-of-november-13-2017"></a>Semana de 13 de novembro de 2017

### <a name="intune-apps"></a>Aplicativos do Intune
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>O aplicativo Portal da Empresa para macOS está disponível <!--1541700-->
O Portal da Empresa do Intune no macOS tem uma experiência atualizada, que foi otimizada para exibir corretamente todas as informações e notificações de conformidade que seus usuários precisam para todos os dispositivos inscritos. E, após a implantação do Portal da Empresa do Intune em um dispositivo, o Microsoft AutoUpdate para macOS fornecerá as atualizações. Baixe o novo Portal da Empresa do Intune para macOS fazendo logon no site do Portal da Empresa do Intune em um dispositivo macOS.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Agora, o Microsoft Planner faz parte da lista MAM (gerenciamento de aplicativo móvel) de aplicativos aprovados <!-- 1248473 -->
O aplicativo Microsoft Planner para iOS e Android agora faz parte dos aplicativos aprovados para MAM (gerenciamento de aplicativo móvel). O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários.
- Saiba mais sobre a [lista MAM de aplicativos aprovados](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Frequência de atualização de requisito por VPN por aplicativo em dispositivos iOS <!-- 1547061 -->  
Agora, os administradores podem remover os requisitos de acordo com a VPN do aplicativo para aplicativos em dispositivos iOS; os dispositivos afetados serão após o próximo check-in no Intune, o que geralmente ocorre em 15 minutos.  

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Suporte para o pacote de gerenciamento do System Center Operations Manager para o conector do Exchange <!-- 885457 -->
O pacote de gerenciamento do SCOM (System Center Operations Manager) para o conector do Exchange está disponível para ajudar você a analisar os logs do conector do Exchange. Com isso, você tem diferentes maneiras de monitorar o serviço quando for necessário solucionar problemas.

## <a name="week-of-november-6-2017"></a>Semana de 6 de novembro de 2017

### <a name="device-enrollment"></a>Registro de dispositivo
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogerenciamento para dispositivos Windows 10  <!-- 1243445 -->
O cogerenciamento é uma solução que fornece uma ponte do gerenciamento tradicional para o moderno e um caminho para fazer a transição usando uma abordagem em fases. Na sua base, o cogerenciamento é uma solução na qual os dispositivos Windows 10 são gerenciados simultaneamente pelo Configuration Manager e pelo Microsoft Intune, e também podem ser ingressados no AD (Active Directory) e no Azure AD (Azure Active Directory).  Essa configuração lhe fornece um caminho para modernizar ao longo do tempo, no ritmo que seja adequado para sua organização se você não puder mover tudo de uma só vez.  

#### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nova página de status de registro para registros do Windows 10 <!--1063201-->    
Agora é possível configurar uma mensagem que aparece quando os usuários registram dispositivos Windows 10. Use a **Tela de Status de Registro** para configurar uma mensagem personalizada e um hiperlink para serem exibidos aos usuários finais quando registrarem seus dispositivos Windows 10.  A **Tela de Status de Registro** também oferece aos usuários finais uma visão sobre o andamento das configurações de política que estão sendo aplicadas ao seu dispositivo.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Restringir o registro do Windows por versão do sistema operacional <!-- 245498 -->
Como administrador do Intune, agora é possível especificar uma versão mínima e uma máxima do Windows 10 para registros de dispositivo. É possível definir essas restrições na folha **Configurações de Plataforma**.

Agora o Intune continuará dando suporte ao registro de computadores e telefones Windows 8.1. Contudo, apenas versões do Windows 10 podem ser definidas com limites mínimo e máximo. Para permitir o registro de dispositivos 8.1, deixe o limite mínimo vazio.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alertas para dispositivos não atribuídos do Windows AutoPilot <!-- 1631236 -->
Um novo alerta está disponível para dispositivos não atribuídos do Windows AutoPilot na página **Microsoft Intune** > **Registro de Dispositivo** > **Visão geral**. Este alerta mostra quantos dispositivos do programa AutoPilot não têm perfis de implantação do AutoPilot atribuídos. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows AutoPilot e informações detalhadas sobre eles. Para obter mais informações, consulte [Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Botão Atualizar para a Lista de dispositivos    <!-- 1333581 -->
Como a Lista de dispositivos não é atualizada automaticamente, é possível usar o novo botão Atualizar para atualizar os dispositivos exibidos na lista.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Suporte para AC (Autoridade de Certificação) da Nuvem Symantec  <!-- 1333638 -->    
O Intune agora dá suporte à AC da Nuvem Symantec, que permite que o Conector de Certificado do Intune emita os certificados PKCS da AC da Nuvem Symantec para dispositivos gerenciados pelo Intune. Se você já estiver usando o Conector de Certificado do Intune com a AC (Autoridade de Certificação) da Microsoft, será possível aproveitar a configuração do Conector de Certificado do Intune existente para adicionar o suporte de AC da Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Novos itens adicionados ao inventário de aplicativos   <!--1404455 -->
Nesta versão, adicionamos os seguintes itens novos ao [inventário usado por dispositivos registrados](device-inventory.md):

- Endereço MAC Wi-Fi
- Espaço de armazenamento total
- Espaço livre total
- MEID
- Operadora do assinante


### <a name="app-management"></a>Gerenciamento de aplicativos
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Definir o acesso para aplicativos pelo patch de segurança do Android mínimo no dispositivo<!-- 1278463 -->   
Um administrador pode definir o patch mínimo de segurança do Android que deve ser instalado no dispositivo para obter acesso a um aplicativo gerenciado em uma conta gerenciada.

> [!Note]  
> Este recurso só restringe os patches de segurança lançados pela Google no Android 6.0 + dispositivos.

#### <a name="app-conditional-launch-support----1193313---"></a>Suporte de inicialização condicional do aplicativo <!-- 1193313 -->
Os administradores de TI agora poderão definir um requisito por meio do portal de administração do Azure para impor uma senha em vez de um PIN numérico por meio do gerenciamento de aplicativo móvel (MAM) quando o aplicativo iniciar. Se configurado, o usuário precisa definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. Esta versão do Intune permitirá esse recurso **somente no iOS**. O Intune dá suporte à senha de uma maneira semelhante ao PIN numérico, ele define um comprimento mínimo, permitindo caracteres e sequências repetidas. Esse recurso exige a participação de aplicativos (ou seja, WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune ao código desse recurso em vigor para as configurações de senha a serem impostas aos aplicativos de destino.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>O número de Versão do Aplicativo para linha de negócios no relatório de status de instalação do dispositivo <!-- 1233999 -->
Com esta versão, o relatório de status de instalação do dispositivo exibe o número de versão do aplicativo para aplicativos de linha de negócios para iOS e Android. Você pode usar essas informações para solucionar problemas de seus aplicativos ou para localizar dispositivos que executam versões desatualizadas do aplicativo.


### <a name="device-configuration"></a>Configuração do dispositivo
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Os administradores agora podem definir as configurações de Firewall em um dispositivo usando um perfil de configuração do dispositivo <!-- 951708 -->   
Os administradores podem ativar o firewall para dispositivos e também configurar vários protocolos para redes públicas, privadas e de domínio.  Essas configurações de firewall podem ser encontradas no perfil "Endpoint Protection".

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>O Windows Defender Application Guard ajuda a proteger dispositivos contra sites não confiáveis, conforme definido pela sua organização <!-- 958257 -->   
Os administradores podem definir sites como "confiáveis" ou "corporativos" usando um fluxo de trabalho da Proteção de Informações do Windows ou o novo perfil "Limite de rede" nas configurações do dispositivo. Os sites que não estão listados no limite de rede confiável de um dispositivo Windows 10 de 64 bits, caso sejam exibidos com o Microsoft Edge, serão abertos em um navegador com um computador virtual do Hyper-V.

O Application Guard pode ser encontrado nos perfis de configuração do dispositivo, no perfil "Endpoint Protection". A partir daí, os administradores podem configurar a interação entre o navegador virtualizado e o computador host, sites não confiáveis e sites confiáveis e dados de armazenamento gerados no navegador virtualizado. Para usar o Application Guard em um dispositivo, um limite de rede deve estar configurado primeiro. É importante definir somente um limite de rede para um dispositivo.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>O Windows Defender Application Control no Windows 10 Enterprise fornece modo para confiar somente em aplicativos autorizados <!-- 1031096 -->    
Com milhares de novos arquivos mal-intencionados criados diariamente, usar a detecção baseada em assinatura de antivírus para combater o malware poderá deixar de fornecer uma defesa adequada contra novos ataques. Ao usar o Windows Defender Application Control no Windows 10 Enterprise, é possível alterar a configuração do dispositivo de um modo no qual os aplicativos sejam confiáveis, a menos que sejam bloqueados por um antivírus ou outra solução de segurança, para um modo no qual o sistema operacional confie somente em aplicativos autorizados por sua empresa. Atribua confiança a aplicativos no Windows Defender Application Control.

Com o Intune, é possível configurar políticas de controle de aplicativo no modo "somente auditoria" ou no modo de imposição. Os aplicativos não serão bloqueados durante a execução no modo "somente auditoria". O modo "somente auditoria" registra todos os eventos em logs do cliente local. Também é possível configurar se somente os componentes do Windows e os aplicativos da Windows Store podem ser executados ou se os aplicativos adicionais com boa reputação, conforme definido pelo Intelligent Security Graph, podem ser executados.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>O Windows Defender Exploit Guard é um novo conjunto de recursos de prevenção contra intrusões para o Windows 10 <!-- 1063615 -->   
O Windows Defender Exploit Guard inclui regras personalizadas para reduzir a capacidade de exploração de aplicativos, impede ameaças à macro e ao script, bloqueia automaticamente conexões de rede para endereços IP de baixa reputação e pode proteger dados do ransomware e ameaças desconhecidas. O Windows Defender Exploit Guard consiste nos seguintes componentes:

- A **Redução da Superfície de Ataque (ASR)** fornece regras que permitem impedir ameaças a email, macro e script.
- O **acesso controlado a pastas** bloqueia automaticamente o acesso ao conteúdo de pastas protegidas.
- O **Filtro de Rede** bloqueia a conexão de saída de qualquer aplicativo para IP/domínio de baixa reputação
- O **Exploit Protection** fornece memória, fluxo de controle e restrições de políticas que podem ser usados para proteger um aplicativo contra explorações.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10 <!-- 790537 -->

A extensão de gerenciamento do Intune permite que você carregue scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão complementa as funcionalidades MDM (Gerenciamento de Dispositivo Móvel) do Windows 10 e torna fácil para você passar para um gerenciamento moderno. Para obter detalhes, consulte [Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Novas configurações de restrição de dispositivo para Windows 10      <!-- 1308850 -->
-    Mensagens (somente celular) – Desabilite testes ou mensagens MMS
-    Senha – As configurações para habilitar o FIPS e o uso dos dispositivos secundários Windows Hello para autenticação 
-    Tela – Configurações para ativar ou desativar o dimensionamento do GDI para aplicativos herdados

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Restrições de dispositivo do modo de quiosque do Windows 10 <!-- 1308872 -->   
É possível restringir os usuários do dispositivo Windows 10 ao modo de quiosque, que limita os usuários a um conjunto de aplicativos predefinidos.  Para fazer isso, crie um perfil de restrição de dispositivo Windows 10 e defina as configurações de Quiosque.

O modo de quiosque dá suporte a dois modos: **único aplicativo** (permite que um usuário execute apenas um aplicativo) ou **multiaplicativo** (permite o acesso a um conjunto de aplicativos).  Você define o nome do dispositivo e da conta de usuário, o que determina os aplicativos com suporte).  Quando o usuário está conectado, ele estará limitado aos aplicativos definidos.  Para obter mais informações, consulte [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

O modo de quiosque requer:

- O Intune deve ser a autoridade MDM.
- Os aplicativos já devem estar instalados no dispositivo de destino.
- O dispositivo deve ser [adequadamente provisionado](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Novo perfil de configuração do dispositivo para criar limites de rede <!-- 1311967 -->   
Criamos um perfil de configuração de dispositivo chamado **Limite de rede** que pode ser encontrado com seus outros perfis de configuração de dispositivo. Use esse perfil para definir os recursos online que você deseja que sejam considerados corporativos e confiáveis. Você deve definir um limite de rede para um dispositivo *antes* que os recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows, possam ser usados no dispositivo. É importante definir somente um limite de rede para cada dispositivo.

Você pode definir recursos de nuvem da empresa, intervalos de endereços IP e servidores proxy internos que você deseja que sejam considerados confiáveis. Depois de definido, um limite de rede pode ser consumido por outros recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Duas configurações adicionais para o Windows Defender Antivírus <!-- 1338409 -->  
**Nível de bloqueio de arquivo**

| | |
|---|---|
| Não configurado | **Não Configurado** usa o nível de bloqueio padrão do Windows Defender Antivírus e fornece detecção de alta segurança sem aumentar o risco de detectar arquivos legítimos. |
| Alta | **Alto** se aplica um alto nível de detecção.
| Alta +  | **Alto +** fornece um alto nível com medidas de proteção adicional que podem afetar o desempenho do cliente.
| Tolerância zero  | A **Tolerância zero** bloqueia todos os executáveis desconhecidos. |

Embora seja pouco provável, configurar como **Alto** pode fazer com que alguns arquivos legítimos sejam detectados.
É recomendável definir o nível de bloqueio do Arquivo para padrão, **Não configurado**.

**Extensão de tempo limite para verificação do arquivo pela nuvem**  

| | |
|--|--|
| Número de segundos (0-50) | Especifique o máximo de tempo para o Windows Defender Antivírus bloquear um arquivo enquanto aguarda um resultado da nuvem. O tempo padrão é de 10 segundos: qualquer tempo adicional especificado aqui (até 50 segundos) será adicionado a esses 10 segundos. Na maioria dos casos, a verificação leva muito menos tempo do que o máximo. Estender o tempo permite que a nuvem investigue completamente os arquivos suspeitos. É recomendável que você habilite essa configuração e especifique pelo menos 20 segundos adicionais. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN adicionado a dispositivos Windows 10 <!-- 1512457 -->  
É possível configurar uma VPN Citrix para seus dispositivos Windows 10. É possível escolher a VPN do Citrix na lista *Selecione um tipo de conexão* na folha **VPN da Base** ao configurar a VPN para Windows 10 e posterior.

> [!Note]
> A configuração do Citrix existia para iOS e Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>As conexões Wi-Fi são compatíveis com chaves pré-compartilhadas no iOS <!-- 1550823 -->
Os clientes podem configurar perfis Wi-Fi para usar PSK (chaves pré-compartilhadas) para conexões WPA/WPA2 Personal em dispositivos iOS. Esses perfis são enviados por push para o dispositivo do usuário quando o dispositivo é registrado no Intune.

Quando o perfil tiver sido enviado por push para o dispositivo, a próxima etapa dependerá da configuração do perfil.  Se estiver configurado para se conectar automaticamente, ele se conectará quando a rede for a próxima necessária.  Quando o perfil se conecta manualmente, o usuário deve ativar a conexão manualmente.  

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Acesso aos logs de aplicativos gerenciados para iOS <!-- 1469920 -->
Agora os usuários finais com o Browser gerenciado instalado podem exibir o status de gerenciamento de todos os aplicativos publicados da Microsoft e enviar logs para solucionar problemas dos seus aplicativos iOS gerenciados.

Saiba como habilitar o modo de solução de problemas no Managed Browser em um dispositivo iOS, consulte [How to access to managed app logs using the Managed Browser on iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) (Como acessar logs de aplicativos gerenciados usando o Managed Browser no iOS).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Aprimoramentos no fluxo de trabalho de configuração de dispositivo no Portal da Empresa para iOS na versão 2.9.0 <!-- 1417174 -->

Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para iOS. A linguagem é mais fácil de usar e combinamos as telas sempre que possível. Também tornamos a linguagem mais específica à sua empresa usando o nome da empresa em todo o texto de configuração. Veja esse fluxo de trabalho atualizado na  [página de novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entidade de usuário contém dados mais recentes do usuário no modelo de dados do Data Warehouse <!-- 1544273 -->
A primeira versão do modelo de dados do Intune Data Warehouse continha somente dados históricos recentes do Intune. Os criadores de relatório não podiam capturar o estado atual de um usuário. Nesta atualização, a **Entidade do usuário** é preenchida com os dados mais recentes do usuário.


## <a name="week-of-october-30-2017"></a>Semana de 30 de outubro de 2017

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>O número de versão do aplicativo de linha de negócios Android e iOS é visível <!-- 1380712 -->

Aplicativos no Intune agora exibem o número de versão para aplicativos de linha de negócios iOS e Android. O número é exibido no portal do Azure na lista de aplicativos e na folha de visão geral do aplicativo. Os usuários finais podem ver o número do aplicativo no aplicativo do Portal da Empresa e no portal da web.

__Número de versão completo__ O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800)

O número de versão completa tem dois componentes:

 - **Versão**  
   O número de versão é o número de versão legível do aplicativo. Isso é usado pelos usuários finais para identificar versões diferentes do aplicativo.

 - **Número de build**  
    O número de build é um número interno que pode ser usado na detecção do aplicativo e para gerenciar o aplicativo de forma programática. O número de build se refere a uma iteração do aplicativo que referencia alterações no código.

Saiba mais sobre os números de versão e desenvolvimento de aplicativos de linha de negócios em [Introdução ao SDK de Aplicativo do Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers).

#### <a name="device-and-app-management-integration----677972---"></a>Integração do gerenciamento de dispositivos e aplicativos <!-- 677972 -->   
Agora que o gerenciamento de dispositivo móvel do Intune (MDM) e o gerenciamento de aplicativo móvel (MAM) são ambos acessíveis do portal do Azure, o Intune começou integrar a experiência de administração de TI em torno do gerenciamento de aplicativo e dispositivo. Essas alterações têm o objetivo de simplificar seu dispositivo e a experiência de gerenciamento de aplicativo.

Saiba mais sobre as alterações de MDM e MAM anunciadas no [blog da equipe de suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Novos alertas de registro para dispositivos Apple <!-- 1471790 -->
A página de visão geral de registro mostrará alertas úteis para administradores de TI sobre o gerenciamento de dispositivos Apple. Os alertas serão exibido na página Visão geral de quando o certificado de push de MDM da Apple estiver expirando ou já tiver expirado; quando o token do Programa de Registro de Dispositivos estiver expirando ou já tiver expirado; e quando houver dispositivos não atribuídos no Programa de Registro de Dispositivo.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Substituição do token de suporte para a configuração de aplicativo sem registro de dispositivo <!-- 1080364 -->

Você pode usar tokens de valores dinâmicos nas configurações de aplicativo para aplicativos em dispositivos que não estão registrados. Para obter mais informações, consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Atualizações para o aplicativo Portal da Empresa para Windows 10 <!--1299474-->
A página Configurações no aplicativo Portal da Empresa para Windows 10 foi atualizada para tornar as configurações e as ações de usuário pretendidas mais consistentes em todas as configurações. Ela também foi atualizada para corresponder ao layout de outros aplicativos do Windows. Encontre imagens de antes/depois na página [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para dispositivos com Windows 10 <!--1337920-->
Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para Windows 10. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela **Sobre**.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Solicitações de comentários para o aplicativo Portal da Empresa para Android <!--1165249-->
O aplicativo Portal da Empresa para Android agora solicita comentários do usuário final. Estes comentários são enviados diretamente para a Microsoft e fornecem aos usuários finais uma oportunidade de avaliar o aplicativo na loja pública do Google Play. Os comentários não são obrigatórios, e podem ser ignorados facilmente para que os usuários possam continuar usando o aplicativo.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ajudando seus usuários com o aplicativo de Portal da Empresa para Android <!-- 1573324, 1573150, 1558616, 1564878 -->

O aplicativo de Portal da Empresa para Android adicionou instruções para os usuários finais a fim de ajudá-los a compreender e, quando possível, resolver automaticamente novos casos de uso.
- Os usuários finais serão direcionados para o [Portal do Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) para remover um dispositivo se tiverem atingido o número máximo de dispositivos que eles têm permissão para adicionar.
- Os usuários finais devem seguir as etapas para ajudá-los a [corrigir erros de ativação em dispositivos Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) ou [desligar o modo de economia de energia](/intune-user-help/power-saving-mode-android). Se nenhuma dessas soluções resolver o problema, fornecemos uma explicação de como [enviar logs para a Microsoft](/intune-user-help/send-logs-to-microsoft-android).

#### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nova ação “Resolver” disponível para dispositivos Android <!-- 1583480 -->

O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android atualmente dá suporte a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

#### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indicador de progresso de configuração do dispositivo no Portal da Empresa para Android <!-- 1565657 -->
O aplicativo Portal da Empresa para Android mostra um indicador de progresso de configuração do dispositivo quando o usuário estiver inscrevendo seu dispositivo. O indicador mostra novos status, começando com "Configurando seu dispositivo...", depois "Registrando seu dispositivo..." e "Concluindo o registro de seu dispositivo...", em seguida, "Concluindo a configuração de seu dispositivo...".

## <a name="week-of-october-23-2017"></a>Semana de 23 de outubro de 2017

### <a name="intune-apps"></a>Aplicativos do Intune
#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Suporte à autenticação baseada em certificado no Portal da Empresa para iOS <!--1029830-->
Adicionamos suporte para autenticação baseada em certificado (CBA) no aplicativo do Portal da Empresa para iOS. Os usuários com CBA inserem seus nomes de usuário, em seguida, tocam no link "Entrar com um certificado". O CBA já é compatível com os aplicativos do Portal da Empresa para Android e Windows. Você pode obter mais informações na página [entrar no aplicativo do Portal da Empresa](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->

Os aplicativos da empresa que foram disponibilizados com ou sem o registro no aplicativo do Portal da Empresa Android agora podem ser instalados sem um aviso de registro.

## <a name="week-of-october-16-2017"></a>Semana de 16 de outubro de 2017
### <a name="device-enrollment"></a>Registro de dispositivo
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Suporte ao programa Windows AutoPilot Deployment no Microsoft Intune  <!-- 747617  -->
Agora você pode usar o Microsoft Intune com o programa Windows AutoPilot Deployment para capacitar os usuários a provisionarem dispositivos corporativos sem envolver TI. Você pode personalizar a OOBE (configuração inicial pelo usuário) e orientar os usuários a ingressarem seus dispositivos no Azure AD e a se registrarem no Intune. Trabalhando juntos, o Microsoft Intune e o Windows AutoPilot eliminam a necessidade de implantar, manter e gerenciar imagens do sistema operacional. Para obter detalhes, consulte [Enroll Windows devices using Windows AutoPilot Deployment Program](https://docs.microsoft.com/intune/enrollment-autopilot) (Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Início rápido para o registro de dispositivo  <!-- 1425655 --> 
O início rápido agora está disponível para o **Registro de dispositivo** e fornece uma tabela de referências para gerenciamento de plataformas e a configuração do processo de registro. Uma breve descrição de cada item e links para a documentação com instruções passo a passo fornece uma documentação útil para simplificar a introdução.

#### <a name="device-categorization----1427491---"></a>Categorização de dispositivo <!-- 1427491 -->
O gráfico de plataforma de dispositivos registrados da folha **Dispositivos > Visão geral** organiza os dispositivos pela plataforma, incluindo Windows Mobile, Windows, macOS, iOS e Android.  Os dispositivos que executam outros sistemas operacionais são agrupados em "Outros".  Isso inclui dispositivos fabricados pela Blackberry, NOKIA e outras.  

Para saber quais dispositivos são afetados em seu locatário, escolha **Gerenciar > Todos os dispositivos** e, em seguida, use **Filtrar** para limitar o campo **SO**.

### <a name="device-management"></a>Gerenciamento de dispositivos
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Novo parceiro de Defesa contra Ameaças Móveis   <!-- 954681 -->  
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Zimperium, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Como funciona a integração com o Intune
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Zimperium. Você pode configurar políticas de acesso condicional de EMS com base na avaliação de risco do Zimperium habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade a recursos corporativos com base em ameaças detectadas.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10  <!--- 978575, 1308849, -->  
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Suporte remoto para dispositivos Windows e Windows Mobile   <!-- 1070473 -->  
O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, que permite dar assistência remota a usuários que executam dispositivos Windows e Windows Mobile.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Verificar dispositivos com o Windows Defender <!-- 1280988  1280990   -->
Agora você pode executar uma **Verificação rápida**, uma **Verificação completa** e **Atualizar assinaturas** com o Windows Defender Antivírus em dispositivos Windows 10 gerenciados. Na folha de visão geral do dispositivo, escolha a ação a ser executada no dispositivo. Você precisará confirmar a ação antes de o comando ser enviado ao dispositivo. 

**Verificação rápida**: uma verificação rápida examina os locais onde o malware registra-se para começar, como as chaves do Registro e pastas de inicialização conhecidas do Windows. Uma verificação rápida demora cerca de cinco minutos. Combinada com a configuração **Proteção sempre em tempo real**, que examina os arquivos quando eles são abertos, fechados e sempre que um usuário navega até uma pasta, uma verificação rápida ajuda a fornecer proteção contra malware que pode estar no sistema ou no kernel. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Verificação completa**: uma verificação completa pode ser útil em dispositivos que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa, e é útil para executar verificações sob demanda. A verificação completa pode demorar uma hora. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Atualizar assinaturas**: o comando para atualizar assinatura atualiza as definições e assinaturas de malware do Windows Defender. Isso ajuda a garantir o que Windows Defender Antivírus seja eficaz na detecção de malware. Esse recurso destina-se somente a dispositivos com Windows 10, com conectividade de internet pendente no dispositivo. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>O botão Habilitar/Desabilitar foi removido da página Autoridade de certificação do Intune do Portal do Azure do Intune  <!-- 1400455 -->
 Estamos eliminando uma etapa extra da configuração do Certificate Connector no Intune. No momento, você pode baixar o Certificate Connector e habilitá-lo no console do Intune. No entanto, se você desabilitar o conector no console do Intune, o conector continuará a emitir certificados.

##### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A partir de outubro, o botão Habilitar/Desabilitar não aparecerá mais na página Autoridade de certificação no Portal do Azure. A funcionalidade do conector permanece a mesma. Os certificados ainda são implantados nos dispositivos registrados no Intune. Você ainda pode baixar e instalar o Certificate Connector. Para interromper a emissão de certificados, agora você pode desinstalar o Certificate Connector em vez de desabilitá-lo.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se o Certificate Connector já estiver desabilitado, você deverá desinstalá-lo.

### <a name="device-configuration"></a>Configuração do dispositivo
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10 Team   <!--- 1308838 -->
Nesta versão, foram adicionadas várias novas configurações ao perfil de restrição de dispositivo do Windows 10 Team para ajudar a controlar dispositivos do Surface Hub.

Para saber mais sobre esse perfil, veja [Configurações de restrição de dispositivo do Windows 10 Team](device-restrictions-windows-10-teams.md).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Impedir que os usuários de dispositivos com Android alterem a data e a hora de seus dispositivos <!-- 1333292 -->
Use uma [política de dispositivo personalizada do Android](custom-settings-android.md) para impedir que os usuários de dispositivos com Android alterem a data e a hora do dispositivo.

Para fazer isso, configure uma política personalizada do Android com o URI de configuração ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Defina isso como **TRUE** e, em seguida, atribua-o aos grupos necessários.

#### <a name="bitlocker-device-configuration----1397398---"></a>Configuração de dispositivo do BitLocker <!-- 1397398 -->
A seção **Criptografia do Windows > Configurações Base** inclui uma nova configuração **Aviso para criptografia de outro disco** que permite que você desabilite o [prompt de aviso](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) para a criptografia de outro disco que possa estar em uso no dispositivo do usuário.  A mensagem de aviso exige o consentimento do usuário final antes de configurar o BitLocker no dispositivo e bloqueia a instalação do BitLocker até receber a confirmação do usuário final.  A nova configuração desabilita o aviso do usuário final.


### <a name="app-management"></a>Gerenciamento de aplicativos
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Os aplicativos do Volume Purchase Program for Business agora serão sincronizadas ao seu locatário do Intune <!-- 800882 -->  
Os desenvolvedores de terceiros podem distribuir aplicativos de forma privada para membros autorizados do VPP (Volume Purchase Program) for Business especificados no iTunes Connect. Esses membros do VPP for Business podem entrar na App Store do Volume Purchase Programa e adquirir seus aplicativos.

Com esta versão, os aplicativos do VPP for Business comprados pelo usuário final passarão a ser sincronizados com seus locatários do Intune.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Selecione o país da loja da Apple para sincronização de aplicativos VPP<!-- 1332311 -->  
Você pode configurar o país da loja do VPP (Programa de Compra por Volume) ao carregar seu token de VPP. O Intune sincroniza aplicativos VPP para todas as localidades da loja VPP especificada de um país.

> [!NOTE]  
> Atualmente, o Intune sincroniza apenas aplicativos VPP da loja VPP que correspondem à localidade do Intune na qual o locatário do Intune foi criado.


### <a name="intune-apps"></a>Aplicativos do Intune
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquear a ação de copiar e colar entre perfis de trabalho e pessoais no Android for Work <!-- 1098994 -->
Com esta versão, é possível configurar o perfil de trabalho para Android for Work para bloquear a ação de copiar e colar entre aplicativos pessoais e de trabalho. Encontre essa nova configuração no perfil **Restrições de dispositivo** para a plataforma **Android for Work** em **Configurações de perfil de trabalho**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Criar aplicativos iOS limitados a Apple App Stores regionais específicas <!-- 1281692 -->
Você poderá especificar a localidade do país durante a criação de um aplicativo gerenciado da Apple App Store.

> [!Note]  
> No momento, você só pode criar aplicativos gerenciados da Apple App Store que estão presentes na loja dos Estados Unidos.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Atualizar usuário VPP do iOS e os aplicativos de dispositivo licenciados <!-- 1305564 -->  
Você poderá configurar o token de VPP do iOS para atualizar todos os aplicativos comprados para esse token por meio do serviço Intune. O Intune detectará as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará automaticamente ao dispositivo quando o dispositivo fizer check-in.

Para obter as etapas para definir um token do VPP e habilitar as atualizações automáticas, consulte [Como gerenciar aplicativos iOS comprados por meio de um Volume Purchase Program com o Microsoft Intune] (/intune/vpp-aplicativos-ios).


### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->
Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Examinar a conformidade da política para anéis de atualização do Windows 10 <!-- 1067886 -->
Você poderá examinar um relatório da política de seus grupos de atualização do Windows 10 em Atualizações de software > Por estado de implantação do grupo de atualização. O relatório da política inclui o status da implantação para os anéis de atualização que você configurou. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** está disponível no espaço de trabalho **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Exibir as atribuições de política de proteção do aplicativo para solução de problemas <!--  1475003 -->
Nesta versão futura, a opção de **Política de proteção do aplicativo** será adicionada à lista suspensa **Atribuições** disponível na folha de solução de problemas. Agora você pode selecionar as políticas de proteção do aplicativo para ver as políticas de proteção de aplicativo atribuídas aos usuários selecionados.



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

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho<!-- 1485783 -->

Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. 

Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->

A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Bloquear o registro de dispositivo Samsung Knox sem suporte <!-- 1490695 -->

O aplicativo Portal da Empresa tenta registrar apenas os dispositivos Samsung Knox com suporte. Para evitar erros de ativação de Knox que impedem o registro do MDM, o registro do dispositivo será tentado somente se ele aparecer na [lista de dispositivos publicada pela Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Os dispositivos Samsung podem ter números de modelo que oferecem suporte a Knox, enquanto outros não. Verifique a compatibilidade com KNOX com o revendedor do dispositivo antes de adquirir e implantar. Você pode encontrar a lista completa de dispositivos verificados nas [configurações de política do Android e Samsung Knox Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Fim do suporte para Android 4.3 e inferior <!-- 1171126, 1326920 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informar aos usuários finais quais informações de dispositivo podem ser vistas em dispositivo registrados <!--1165314-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo em todos os aplicativos Portal da Empresa. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente do artigo [Quais informações sua empresa pode ver?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Isso será distribuído em todos os aplicativos de Portal da Empresa em um futuro próximo. Anunciamos isso para iOS em [setembro](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Semana de 25 de setembro de 2017

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="intune-supports-ios-11---1428975--"></a>O Intune dá suporte ao iOS 11 <!--1428975-->
O Intune dá suporte ao iOS 11. Isso foi anunciado anteriormente no [blog de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!-- 1164477 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. 

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->
O aplicativo Portal da Empresa para Windows 10 permite que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.



## <a name="notices"></a>Avisos

### <a name="plan-for-change-easy-assist-end-of-life----1556480---"></a>Planeje-se para a mudança: fim da vida útil do Easy Assist<!-- 1556480 -->
O Intune usa o Microsoft Easy Assist para assistência remota de gerenciamento de PC. Talvez você não saiba que o Microsoft Easy Assist é um componente do Office Live Meeting, um serviço desativado em 31 de dezembro de 2017. Portanto, a oferta do Easy Assist do Intune também chegou ao fim da vida útil em 31 de dezembro de 2017.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gerenciar dispositivos Android for Work independentemente dos dispositivos Android <!-- 1490731 EEready-->    
**Observação**: as alterações a seguir começarão a serem distribuídas com a atualização de novembro, mas podem demorar para serem executadas em sua conta. Você receberá uma notificação de confirmação no portal do Office 365 quando essas alterações entrarem em vigor para a sua conta. Após a distribuição, você terá opções de capacidade de gerenciamento adicionais. Não haverá nenhuma alteração na experiência do usuário final durante a distribuição.

O Intune é compatível com gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

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

### <a name="deprecating-support-for-os-x-mavericks-1010-and-previous-versions-of-macos---1489263-plan-for-change-for-1802--"></a>Substituindo o suporte para OS X Mavericks 10.10 e versões anteriores do macOS <!--1489263, plan for change for 1802-->
Estamos anunciando que começaremos a desativar a inscrição de dispositivos com OS X Yosemite 10.10 e versões anteriores do macOS em fevereiro de 2018. O Intune é compatível com o OS X El Capitan 10.11 e versões mais recentes.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Novo caminho para dispositivos gerenciados na API do Graph <!-- 1586728 -->
Estamos fazendo uma alteração no caminho usado para acessar os dispositivos gerenciados na versão beta da API do Graph. 

| | |
|--|--|
| Caminho atual |  https://graph.microsoft.com/beta/managedDevices |
| Novo caminho | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Os dois caminhos funcionam durante o mês de outubro. Após o lançamento do serviço de outubro, somente o novo caminho funcionará.  Se você estiver usando a API do Graph para acessar os dispositivos gerenciados, atualize e verifique seus scripts e aplicativos com o novo caminho. Para obter outras alterações, verifique o [log mensal de alterações da API do Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal Clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência, caso sua conta existente não possa acessar o portal do Azure.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Funções de administração que estão sendo substituídas no Portal do Azure
As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure. Após a migração para o portal do Azure, você precisará reatribuir essas novas funções de administração aos administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>O que está por vir

### <a name="conditional-access-policies-for-intune-will-only-be-available-from-the-azure-portal-----1737088---"></a>Políticas de Acesso Condicional para o Intune só estarão disponíveis no portal do Azure <!-- 1737088 -->
Estamos simplificando o local em que você configura e gerencia o acesso condicional. No momento, você pode gerenciar o acesso condicional na folha MAM (Proteção de Aplicativo do Intune) e por meio da experiência clássica do Azure AD no [Portal do Microsoft Azure](https://manage.windowsazure.com). A partir de janeiro, você só poderá configurar e gerenciar suas políticas no [portal do Azure](https://portal.azure.com) usando **Azure Active Directory** > **Acesso Condicional**. Para sua conveniência, você também pode acessar essa folha do Intune no portal do Azure em **Intune** > **Acesso Condicional**.

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747--"></a>Gerenciar dispositivos macOS inscritos em Jamf com o mecanismo de conformidade do dispositivo do Intune <!--1592747-->
A partir do início 2018, a Jamf enviará informações de estado do dispositivo macOS ao Intune, que, em seguida, avaliará a conformidade com as políticas definidas no console do Intune. Com base no estado de conformidade do dispositivo, bem como em outras condições (como local, risco de usuário etc.), o acesso condicional imporá a conformidade para dispositivos macOS que estão acessando aplicativos de nuvem e locais conectados com o Azure AD, incluindo o Office 365.

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

## <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
