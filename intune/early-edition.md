---
title: "Edição antecipada"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 12f4a09fe10ec792abe8183369a21f53c23f5d1a
ms.sourcegitcommit: 53d272defd2ec061dfdfdae3668d1b676c8aa7c6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>A edição antecipada do Microsoft Intune – janeiro de 2018

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

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Resolução facilitada de problemas de conformidade para o aplicativo do Portal da Empresa para Windows 10 <!--676546 -->

Os usuários finais com dispositivos com Windows poderão tocar no motivo da não conformidade no aplicativo do Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema.

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nova opção de autenticação de usuário para registro em massa da Apple <!-- 747625 -->
O Intune dará a você a opção para autenticar dispositivos usando o aplicativo do Portal da Empresa para os seguintes métodos de registro:

- Programa de Registro do Dispositivo da Apple
- Apple School Manager
- Registro do Apple Configurator

Com a opção do Portal da Empresa, a autenticação multifator do Azure Active Directory pode ser imposta sem bloquear esses métodos de registro.

Com a opção do Portal da Empresa, o Intune ignora a autenticação do usuário no Assistente de Configuração do iOS para registro de afinidade de usuário. Isso significa que o dispositivo e registrado inicialmente como um dispositivo sem usuário e, portanto, não receberá as configurações ou políticas dos grupos de usuários. Receberá apenas as configurações e políticas dos grupos de dispositivos. No entanto, o Intune instalará automaticamente o aplicativo do Portal da Empresa no dispositivo. O primeiro usuário a iniciar e entrar no aplicativo do Portal da Empresa será associado ao dispositivo no Intune. Nesse momento, o usuário receberá as configurações e políticas de seus grupos de usuários. A associação do usuário não pode ser alterada sem um novo registro.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 -->
O Intune dará suporte para o registro de dispositivos de até 100 contas diferentes do DEP (Programa de registro de dispositivos) da Apple ou do Apple School Manager. Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>Selecione as categorias de dispositivo usando as configurações de Acesso Corporativo ou de Estudante <!-- 1058963 eeready -->
Se você tiver habilitado o [mapeamento do grupo de dispositivos](https://docs.microsoft.com/en-us/intune/device-group-mapping), os usuários no Windows 10 receberão uma solicitação para selecionar uma categoria de dispositivo após o registro por meio do botão **Conectar** em **Configurações** > **Contas** > **Acesso corporativo ou de estudante** ou durante a configuração inicial pelo usuário.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Direcionamento de políticas de conformidade para dispositivos em grupos de dispositivo <!--1307012 -->

Você poderá direcionar políticas de conformidade para usuários em grupos de usuários. Você poderá direcionar políticas de conformidade para dispositivos em grupos de dispositivos.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos <!-- 1406920 -->

Durante a atribuição do aplicativo e após a seleção de um tipo de atribuição, você poderá selecionar os grupos a serem incluídos, bem como os grupos para exclusão.

### <a name="remote-erase-command-support----1438084---"></a>Suporte ao comando "Erase" remoto <!-- 1438084 -->

Os administradores poderão emitir um comando Erase remotamente.

> [!IMPORTANT]
> O comando erase não pode ser revertido e deve ser usado com cuidado.

O comando erase remove todos os dados, incluindo o sistema operacional, de um dispositivo. Também remove o dispositivo do gerenciamento do Intune. Nenhum aviso é emitido para o usuário, e a remoção ocorre imediatamente após a emissão do comando.

Você poderá configurar um PIN de recuperação com seis dígitos. Este PIN pode ser usado para desbloquear o dispositivo apagado e, nesse momento, a reinstalação do sistema operacional começará. Após o início da remoção, o PIN aparecerá em uma barra de status na folha de visão geral do dispositivo no Intune. O PIN permanecerá enquanto a remoção estiver em andamento. Após a conclusão da remoção, o dispositivo desaparecerá totalmente do gerenciamento do Intune. Anote o PIN de recuperação para que a pessoa que estiver restaurando o dispositivo possa usá-lo.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dados criptografados de WIP (Proteção de Informações do Windows) nos resultados da pesquisa do Windows <!-- 1469193 -->

Uma nova configuração na política de WIP (Proteção de Informações do Windows) permitirá que você controle se os dados criptografados por WIP estarão incluídos nos resultados da pesquisa do Windows.

### <a name="website-learning-mode----1631908---"></a>Modo de Aprendizado do Site <!-- 1631908 -->

Intune apresentará uma extensão do modo de Aprendizado do WIP (Proteção de Informações do Windows). Além de exibir informações sobre aplicativos habilitados para WIP, você poderá exibir um resumo dos dispositivos que compartilharam dados de trabalho com sites. Com essas informações, é possível determinar quais sites devem ser adicionados às políticas de WIP de grupo e de usuário.

### <a name="updates-to-compliance-emails---1637547---"></a>Atualizações nos emails de conformidade <!--1637547 -->

Quando um email é enviado para informar sobre um dispositivo sem conformidade, os detalhes sobre o dispositivo sem conformidade serão incluídos. O artigo a seguir será atualizado para indicar esse fato: [Automatizar ações para não conformidade](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>As Políticas de Acesso Condicional para o Intune só estão disponíveis no Portal do Azure <!-- 1737088 1634311 -->
Simplificaremos o local no qual você configura e gerencia o acesso condicional. Você configurará e gerenciará suas políticas no [Portal do Azure](https://portal.azure.com) em **Azure Active Directory** > **Acesso Condicional**. Para sua conveniência, você também poderá acessar essa folha do Intune no Portal do Azure em **Intune** > **Acesso Condicional**.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertas para tokens expirados e tokens que expirarão em breve<!-- 1639263 -->
A página de visão geral mostrará alertas para tokens expirados e tokens que expirarão em breve. Ao clicar em um alerta de um único token, você será levado até a página de detalhes do token.  Se você clicar no alerta com vários tokens, será levado até uma lista com todos os tokens e seu status. Os administradores devem renovar seus tokens antes da data de expiração.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impressão remota em uma rede segura <!-- 1709994  -->
As soluções de impressão móvel sem fio do PrinterOn permitirão aos usuários imprimir remotamente de qualquer lugar, e a qualquer momento, em uma rede segura. O PrinterOn será integrado ao SDK do Aplicativo do Intune para iOS e Android. Você poderá direcionar políticas de proteção de aplicativo para esse aplicativo por meio da folha **Políticas de proteção do aplicativo** do Intune no console do administrador. Os usuários finais poderão baixar o aplicativo "PrinterOn para Microsoft" através da Play Store ou iTunes para uso no ecossistema do Intune.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Aprovar o aplicativo do Portal da Empresa para Android for Work <!--1797090 -->
Se sua organização usa o Android for Work, você precisará aprovar manualmente o aplicativo do Portal da Empresa para Android, para que ele continue recebendo atualizações automáticas da loja Google Play gerenciada.

### <a name="faceid-on-ios-devices----1807377---"></a>FaceID em dispositivos iOS <!-- 1807377 -->
Agora, as políticas de proteção de aplicativo do Intune permitem uma configuração que controla o FaceID em dispositivos iOS. Essa configuração é para dispositivos que permitem a funcionalidade FaceID (atualmente, somente no iPhone X). Essa configuração é separada dos controles TouchID permitidos no momento. As organizações têm a capacidade de escolher se desejam confiar no FaceID como um prompt de PIN válido como uma alternativa aos controles TouchID.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>API do Microsoft Graph para Intune – Disponibilidade Geral <!-- 1833289 -->
As APIs do Intune no Microsoft Graph fornecerão acesso programático aos dados e métodos para automatização de ações administrativas para o serviço do Intune.  Com a **Disponibilidade Geral** dessas APIs, clientes, parceiros e desenvolvedores poderão aproveitar as APIs para integração com soluções internas ou comerciais relacionadas ao suporte, ou que exigem o suporte, do Intune ou de outros serviços da Microsoft disponíveis por meio do Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Revogação de aplicativos do Programa de Compra por Volume do iOS <!-- 820863 -->
Para um determinado dispositivo que tem um ou mais aplicativos VPP (Programa de Compra por Volume) do iOS, você poderá revogar a licença do aplicativo com base no dispositivo associada ao dispositivo. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. Para saber mais, confira [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Revogar licenças para um token de Programa de Compra por Volume do iOS<!-- 820870 -->
Você poderá revogar a licença de todos os aplicativos VPP (Programa de Compra por Volume) do iOS para um determinado Token de VPP.

### <a name="new-ios-device-action------1244701---"></a>Nova ação do dispositivo iOS <!-- 1244701 -->
Você pode desligar os dispositivos supervisionados com o iOS 10.3. Essa ação desliga o dispositivo imediatamente sem avisar o usuário final. A ação **Desligar (somente supervisionado)** pode ser encontrada nas propriedades do dispositivo quando você seleciona um dispositivo na carga de trabalho **Dispositivo**.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Agora, o Intune fornece a operação de Movimentação da Conta <!-- 1573558, 1579830 -->
A **Movimentação da Conta** migra um locatário da ASU (Unidade de Escala do Azure) para outra. A **Movimentação da Conta** pode ser usada para os cenários iniciados pelo cliente, quando você liga para a equipe de suporte do Intune solicitando-a, e também pode ser um cenário controlado pela Microsoft, no qual a Microsoft precisa fazer ajustes no serviço no back-end. Durante a **Movimentação da Conta**, o locatário entra no modo somente leitura (ROM). As operações de serviço como inscrever, renomear dispositivos, atualizar status de conformidade falharão durante o período de ROM.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **integrado** tornará mais fácil para você criar e atribuir os aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.


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


### <a name="configure-an-ios-app-pin----1586774---"></a>Configurar um PIN de aplicativo iOS <!-- 1586774 -->
Em breve, você poderá exigir um PIN para aplicativos iOS determinados. Você pode configurar o requisito e a data de vencimento do PIN em dias por meio do portal do Azure. Quando necessário, um usuário deverá definir e usar um novo PIN antes de receber o acesso a um aplicativo iOS. Apenas os aplicativos iOS que têm a proteção de aplicativo habilitada com o SDK de Aplicativo do Intune oferecerão suporte a esse recurso.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!--1412866-->

Será lançada uma atualização principal da experiência do usuário para o aplicativo Portal da Empresa para iOS. A atualização apresentará uma reformulação visual completa, incluindo uma aparência modernizada com melhorias de acessibilidade e usabilidade. Todas as funcionalidades atuais do Portal da Empresa para iOS serão mantidas.

Estamos oferecendo uma versão de pré-lançamento do aplicativo Portal da Empresa para iOS atualizado por meio do programa Apple TestFlight para que você use e forneça comentários. Inscreva-se em https://aka.ms/intune_ios_cp_testflight para obter acesso ao TestFlight. 

![imagens chamativas do novo aplicativo portal da empresa para ios](./media/ios-cp-app-redesign-1801-teaser.png)


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672(archived), 1119689 -->  
Você poderá criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Proteção de Aplicativo do Intune e Ferramentas de Desenvolvimento do Citrix MDX <!-- 709185 -->
Você pode gerenciar dispositivos e aplicativos com uma combinação do Citrix XenMobile MDX e o Microsoft Intune. Isso permite que você gerencie aplicativos com políticas de proteção de aplicativo do Intune usando a tecnologia de mVPN da Citrix.

Você pode localizar um repositório de códigos que contém a Ferramenta de Encapsulamento de Aplicativo do Intune e o SDK de Aplicativo do Intune para iOS e Android, integrando com a tecnologia mVPN da Citrix MDX.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirecionando usuários do macOS para nosso novo aplicativo do Portal da Empresa <!--1380728-->   
Quando um usuário final fizer o logon no site do Portal da Empresa para registrar seu dispositivo macOS, ele será direcionado a baixar o novo aplicativo do Portal da Empresa para macOS a fim de concluir o processo. Isso ocorre em dispositivos macOS usando OS X El Capitan 10.11 ou superior. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Suporte do Intune Managed Browser para iOS e Android <!-- 1374196 -->
A partir de outubro de 2017, o aplicativo do Intune Managed Browser no aplicativo do Android oferecerá suporte apenas a dispositivos que executam o Android 4.4 e versões posteriores. O aplicativo Intune Managed Browser no iOS oferecerá suporte apenas a dispositivos que executam o iOS 9.0 e versões posteriores. Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Mensagem de erro melhorada para quando um usuário atinge o número máximo de dispositivos que podem ser registrados <!-- 1270370 -->
Em vez de uma mensagem de erro genérica, os usuários finais com dispositivos Android recebem uma mensagem de erro amigável e acionável: "Você registrou o número máximo de dispositivos permitidos por seu administrador de TI. Remova um dispositivo registrado ou obtenha ajuda do administrador de TI."




## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.




### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
