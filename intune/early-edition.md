---
title: "Edição antecipada"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1ea734e83cfab3fff22c775764ac9814012d52b6
ms.sourcegitcommit: 70dc0aaad51b447e173b663d1092d993dc81ffdd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>A edição antecipada do Microsoft Intune – dezembro de 2017

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

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Revogação de aplicativos do Programa de Compra por Volume do iOS <!-- 820863 -->
Para um determinado dispositivo que tem um ou mais aplicativos VPP (Programa de Compra por Volume) do iOS, você poderá revogar a licença do aplicativo com base no dispositivo associada ao dispositivo. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. Para saber mais, confira [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Revogar licenças para um token de Programa de Compra por Volume do iOS<!-- 820870 -->
Você poderá revogar a licença de todos os aplicativos VPP (Programa de Compra por Volume) do iOS para um determinado Token de VPP.

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Excluir um token de Programa de Compra por Volume do iOS <!-- 820879 -->
Você poderá excluir o token VPP (Programa de Compra por Volume) do iOS usando o console. Isso pode ser necessário quando houver instâncias duplicadas de um token VPP.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Relatório de verificação de dispositivo NAC (Controle de Acesso de Rede) <!-- 1232250 -->
Antes dessa alteração, os administradores de TI não conseguiam determinar no lado do Intune se um dispositivo gerenciado por NAC estava ou não se comunicando com sua solução NAC. Quando um dispositivo gerenciado por NAC não está se comunicando com sua solução NAC, o dispositivo é considerado não compatível pela solução NAC e, portanto, é bloqueado pela própria solução NAC e, subsequentemente, é bloqueado pelas políticas de acesso condicional que dependem do estado de conformidade do dispositivo.

Com essa alteração, os administradores de TI podem ver quais dispositivos gerenciados por NAC se comunicaram ou não com êxito com a solução NAC. Essa nova funcionalidade é composta por duas novas funções de monitoramentos, localizadas na Carga de trabalho de conformidade do dispositivo no Intune. Veja abaixo as estatísticas:
- **Média de chamadas do NAC na última hora**
- **Última solicitação de entrada de NAC (data/hora)**

### <a name="new-ios-device-action------1244701---"></a>Nova ação do dispositivo iOS <!-- 1244701 -->
Você pode desligar os dispositivos supervisionados com o iOS 10.3. Essa ação desliga o dispositivo imediatamente sem avisar o usuário final. A ação **Desligar (somente supervisionado)** pode ser encontrada nas propriedades do dispositivo quando você seleciona um dispositivo na carga de trabalho **Dispositivo**.

### <a name="palo-alto-vpn-now-supported----1333680-eeready---"></a>Agora há suporte para a VPN Palo Alto <!-- 1333680 eeready -->
A lista **Tipo de conexão** incluirá a VPN Palo Alto quando você configurar sua VPN base.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>Suporte a vários conectores para manipulação de certificado SCEP e PFX <!-- 1361755 eeready -->
Os clientes que usam o conector NDES local para fornecer certificados a dispositivos conseguirão configurar vários conectores em um único locatário.

Essa nova capacidade dá suporte ao seguinte cenário:

- **Alta disponibilidade**

    Cada conector NDES efetua o pull de solicitações de certificado do Intune.  Se um conector NDES ficar offline, o outro conector poderá continuar processando solicitações.

### <a name="new-automatic-redeployment-setting----1469168---"></a>Nova configuração automática de reimplantação <!-- 1469168 -->
Essa configuração permite que usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **CTRL + Win + R** na tela de bloqueio do dispositivo. O dispositivo será reconfigurado automaticamente e inscrito novamente no gerenciamento.

Essa configuração pode ser encontrada em Windows 10 -> Restrições de dispositivo -> Geral -> Reimplantação automática.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalar aplicativos do Office em dispositivos macOS <!-- 1494311 -->
Você poderá instalar aplicativos do Office em dispositivos macOS. Esse novo tipo de aplicativo permitirá que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Esses aplicativos também são fornecidos com o MAU (Microsoft AutoUpdater), para ajudar a manter seus aplicativos seguros e atualizados.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Conta de recurso do Surface Hub com suporte <!-- 1566442 eeready -->
Uma nova ação de dispositivo será adicionada para que os administradores possam definir e atualizar a conta do recurso associada a um Surface Hub.

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

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Agora, o Intune fornece a operação de Movimentação da Conta <!-- 1573558, 1579830 -->
A **Movimentação da Conta** migra um locatário da ASU (Unidade de Escala do Azure) para outra. A **Movimentação da Conta** pode ser usada para os cenários iniciados pelo cliente, quando você liga para a equipe de suporte do Intune solicitando-a, e também pode ser um cenário controlado pela Microsoft, no qual a Microsoft precisa fazer ajustes no serviço no back-end. Durante a **Movimentação da Conta**, o locatário entra no modo somente leitura (ROM). As operações de serviço como inscrever, renomear dispositivos, atualizar status de conformidade falharão durante o período de ROM.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Novas definições do perfil de configuração de dispositivo da WDSC (Central de Segurança do Windows Defender) <!-- 1335507 -->
O Intune adiciona uma nova seção de configurações de perfil de configuração de dispositivo sob a Proteção de ponto de extremidade chamada **Central de Segurança do Windows Defender**. Os administradores de TI podem configurar quais pilares do aplicativo Central de Segurança do Windows Defender os usuários finais podem acessar. Se um administrador de TI ocultar um pilar no aplicativo Central de Segurança do Windows Defender, todas as notificações relacionadas ao pilar oculto não serão exibidas no dispositivo do usuário.

Estes são os pilares que os administradores podem ocultar nas configurações do perfil de configuração de dispositivo da Central de Segurança do Windows Defender:
- Proteção contra vírus e ameaças
- Desempenho e integridade do dispositivo
- Proteções de firewall e rede
- Controle de aplicativo e navegador
- Opções da família

Os administradores de TI também podem personalizar quais notificações os usuários recebem. Por exemplo, você pode configurar se os usuários recebem todas as notificações geradas por pilares visíveis na WDSC, ou apenas as notificações críticas. As notificações não críticas incluem resumos periódicos de atividades do Windows Defender Antivírus e notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas. Além disso, você também pode personalizar o conteúdo da própria notificação, por exemplo, você pode fornecer informações de contato da TI para incorporar as notificações que aparecem nos dispositivos dos usuários.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **integrado** tornará mais fácil para você criar e atribuir os aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Suporte para logon único para iOS <!-- 1333645 -->  
Você poderá usar o Logon Único para usuários do iOS. Os aplicativos iOS que são codificados para exigir credenciais do usuário no conteúdo do Logon Único são compatíveis com essa atualização de configuração de conteúdo. Você também pode usar o UPN e a ID de Dispositivo do Intune para configurar o Nome da entidade e o Realm.

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocolo de texto permitido em Aplicativos gerenciados <!-- 1414050  -->
Aplicativos gerenciados pelo SDK do Aplicativo do Intune poderão enviar mensagens SMS.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Bloquear dispositivos macOS gerenciados remotamente com o Intune <!-- 1437691 -->
Você poderá bloquear um dispositivo macOS perdido e definir um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

Para obter mais informações, consulte [Bloquear dispositivos gerenciados remotamente com o Intune](device-remote-lock.md).


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

| Configuração | Status de Android for Work na Restrição de Tipo de Dispositivo padrão | Anotações |
| --- | --- | --- |
| **Gerenciar todos os dispositivos como Android** | Bloqueado | Todos os dispositivos Android devem se registrar sem o Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work** | Permitido | Todos os dispositivos que oferecem suporte ao Android for Work devem ser registrados com Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work somente para os usuários nestes grupos** | Bloqueado | Uma política de Restrição de Tipo de Dispositivo separada foi criada para substituir o padrão. Essa política define os grupos que você selecionou anteriormente para permitir o registro Android for Work. Usuários dentro dos grupos selecionados ainda poderão registrar seus dispositivos Android for Work. Todos os outros usuários são impedidos de se registrar com o Android for Work. |

Em todos os casos, a norma pretendida é preservada. Nenhuma ação é necessária de sua parte para manter a permissão global ou por grupo do Android for Work em seu ambiente.

Essas alterações começarão a distribuição com a atualização de novembro, mas podem levar tempo para serem executadas em sua conta. Você receberá uma notificação de confirmação no portal do Office 365 quando essas alterações entrarem em vigor para a sua conta.


### <a name="configure-an-ios-app-pin----1586774---"></a>Configurar um PIN de aplicativo iOS <!-- 1586774 -->
Em breve, você poderá exigir um PIN para aplicativos iOS determinados. Você pode configurar o requisito e a data de vencimento do PIN em dias por meio do portal do Azure. Quando necessário, um usuário deverá definir e usar um novo PIN antes de receber o acesso a um aplicativo iOS. Apenas os aplicativos iOS que têm a proteção de aplicativo habilitada com o SDK de Aplicativo do Intune oferecerão suporte a esse recurso.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Adicionar "Encontrar meu iPhone" para dispositivos pessoais <!--1427287-->
Você poderá exibir se os dispositivos iOS têm o Bloqueio de Ativação ativado. Esse recurso podia ser encontrado anteriormente no portal clássico do Intune.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.


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
O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android oferece suporte atualmente a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [criptografia do dispositivo](/intune-user-help/encrypt-your-device-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android), e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




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
