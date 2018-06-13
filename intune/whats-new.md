---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/04/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: f1f6cac720e753e78bbabe091ce1c68cc58b7917
ms.sourcegitcommit: 21b08737c3366b81b0f3b981b29008563f63f036
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34758143"
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Conheça as novidades de cada semana do Microsoft Intune. Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md). Alguns recursos podem ser implantados ao longo de várias semanas e podem não estar disponíveis para todos os clientes na primeira semana.

> [!Note]
> Para obter informações sobre a nova funcionalidade no MDM (gerenciamento de dispositivo móvel) híbrido, confira a [página de Novidades sobre o MDM híbrido](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
### App management
### Device enrollment
### Device management
### Device configuration
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   

## <a name="week-of-june-4-2018"></a>Semana de 4 de junho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Recuperar a AUMID (ID de modelo de usuário do aplicativo associado) para aplicativos da Microsoft Store para Empresas no modo de quiosque <!-- 1560077 ! -->
O Intune agora pode recuperar as AUMIDs (IDs de modelo de usuário do aplicativo) para aplicativos WSfB (Microsoft Store para Empresas) para melhorar a configuração do perfil de quiosque.

Para saber mais sobre aplicativos da Microsoft Store para Empresas, confira [Gerenciar aplicativos da Microsoft Store para Empresas](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Nova página da identidade visual do Portal da Empresa <!-- 1916370 -->
A página de identidade visual do Portal da Empresa tem um novo layout, mensagens e dicas de ferramenta.


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Suporte para perfis de VPN GlobalProtect da Palo Alto Networks <!-- 1333680 eeready ! -->
Com essa atualização, você pode escolher o GlobalProtect da Palo Alto Networks como um tipo de conexão VPN para perfis VPN no Intune (**Configuração do dispositivo** > **Perfis**  >  **Criar perfil** > **Tipo de perfil** > **VPN**). Nesta versão, há suporte para as seguintes plataformas: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Adições às configurações das opções de segurança do dispositivo local <!-- 1403702 -->
Agora você pode definir as configurações adicionais de Opções de Segurança de Dispositivo Local para dispositivos Windows 10. Configurações adicionais estão disponíveis nas áreas de Cliente de Rede da Microsoft, Servidor de Rede Microsoft, Acesso e segurança de rede e Logon interativo. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Habilitar o modo de quiosque em dispositivos com Windows 10 <!-- 1560072 ! -->
Em dispositivos com Windows 10, você pode criar um perfil de configuração e habilitar o modo de quiosque (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** > **Restrições do Dispositivo** > **Quiosque**). Nesta atualização, a configuração **Quiosque (visualização)** é renomeada para **Quiosque (obsoleto)**. **Quiosque (obsoleto)** não é mais recomendado para uso, mas continuará a funcionar até a atualização de julho. **Quiosque (obsoleto)** é substituído pelo novo tipo de perfil **Quiosque** (**Criar perfil** > **Windows 10** > **Quiosque (versão prévia)**), que conterá as configurações de quiosques no Windows 10 RS4 e versões posteriores.

Aplica-se ao Windows 10 e posteriores.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>O gráfico de perfil do dispositivo do usuário está de volta <!-- 2160133 -->
Durante o aprimoramento das contagens numéricas exibidas no gráfico de perfil do dispositivo (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral** ), o gráfico de usuário gráfico foi temporariamente removido.

Com essa atualização, o gráfico de usuário está de volta, e é exibido no Portal do Azure.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118-wnready---"></a>Suporte para registro do Windows Autopilot sem autenticação de usuário <!-- 1165118 wnready -->
O Intune agora é compatível com registro do Windows Autopilot sem autenticação de usuário. Essa é uma nova opção no perfil de implantação do Windows Autopilot, "Modo de Implantação do Autopilot" definido como "Autoimplantando".  O dispositivo deve estar executando o Windows 10 build 1803 ou posterior e ter um TPM 2.0 para autorizar esse tipo de registro. Como nenhuma autenticação de usuário é necessária, você só deve atribuir essa opção a dispositivos sobre os quais você tenha controle físico.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766-eeready---"></a>Nova configuração de idioma/região ao configurar o OOBE para Autopilot <!-- 1821766 eeready -->
Uma nova definição de configuração está disponível para definição do idioma e da região para perfis do Autopilot durante a Experiência de Configuração Inicial. Para ver a nova configuração, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > **Criar perfil** > **Modo de implantação** = **Autoimplantação** > **Padrões configurados**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nova configuração para o teclado do dispositivo <!-- 1821768 -->
Uma nova configuração estará disponível para definição do teclado para perfis do Autopilot durante a configuração inicial pelo usuário. Para ver a nova configuração, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > **Criar perfil** > **Modo de implantação** = **Autoimplantação** > **Padrões configurados**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Perfis do AutoPilot passando para grupo direcionado a <!-- 1877935 -->
Os perfis de implantação do AutoPilot podem ser atribuídos a grupos do Azure AD que contém dispositivos do AutoPilot.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="set-compliance-by-device-location----851881----"></a>Definir a conformidade de acordo com a localização do dispositivo <!-- 851881 ! -->
Em algumas situações, convém restringir o acesso aos recursos corporativos a uma localização específica, definida por uma conexão de rede. Agora você pode criar uma política de conformidade (**Conformidade do dispositivo** > **Locais**) com base no endereço IP do dispositivo. Se o dispositivo sair do intervalo de IP, ele não poderá mais acessar os recursos corporativos.

Aplica-se a: dispositivos Android 6.0 e superiores, com o aplicativo Portal da Empresa atualizado

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Impedir aplicativos e experiências de consumidor em dispositivos Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Você poderá impedir a instalação de aplicativos e experiências de consumidor nos seus dispositivos Windows 10 Enterprise RS4 AutoPilot. Para ver esse recurso, acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Plataforma** = **Windows 10 ou posterior** > **Tipo de perfil** = **Restrições do dispositivo** > **Configurar** > **Windows Spotlight** > **Recursos do consumidor**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948-eeready---"></a>Desinstale a versão mais recente das atualizações de software do Windows 10 <!-- 1732948 eeready -->
Caso você descubra um problema de quebra em seus computadores Windows 10, poderá optar por desinstalar a atualização (reverter) a atualização de recurso mais recente ou a atualização de qualidade mais recente. Desinstalar uma atualização de recurso ou qualidade só está disponível para o canal de serviço que o dispositivo se encontra. Ao desinstalar, uma política é disparada para restaurar a atualização anterior em seus computadores Windows 10. Para atualizações de recursos, especificamente, você pode limitar o tempo entre 2 e 60 dias em que uma desinstalação da versão mais recente pode ser aplicada. Para definir opções de desinstalação de atualização de software, selecione **Atualizações de software** na folha do **Microsoft Intune** no portal do Azure. Em seguida, selecione **Anéis de Atualização do Windows 10** na folha **Atualizações de software**. Em seguida, você pode escolher a opção **Desinstalar** na seção **Visão Geral**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Pesquisar IMEI e número de série de todos os dispositivos <!-- 1793685 -->
Agora você pode pesquisar IMEI e números de série na folha Todos os dispositivos (email, UPN, nome do dispositivo e nome de gerenciamento ainda estão disponíveis). No Intune, escolha **Dispositivos** > **Todos os dispositivos** > Insira sua pesquisa na caixa de pesquisa.

#### <a name="management-name-field-will-be-editable----1875989---"></a>O campo Nome de gerenciamento poderá ser editado <!-- 1875989 -->
Você agora pode editar o campo de nome de gerenciamento na folha **Propriedades** de um dispositivo. Para editar esse campo, escolha **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo > **Propriedades**. Use o campo de nome de gerenciamento para identificar exclusivamente um dispositivo.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Novo filtro Todos os dispositivos: categoria de dispositivo <!-- 1878520 -->
Agora você pode filtrar a lista **Todos os dispositivos** por categoria de dispositivo. Para fazer isso, escolha **Dispositivos** > **Todos os dispositivos** > **Filtrar** > **Categoria de dispositivo**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Use o TeamViewer para compartilhar a tela de dispositivos iOS e MacOS <!-- 1985547 -->
Os administradores agora podem se conectar ao [TeamViewer](device-profile-android-teamviewer.md) e iniciar uma sessão de compartilhamento de tela com dispositivos iOS e macOS. Usuários do iPhone, iPad e macOS podem compartilhar suas telas ao vivo com qualquer desktop ou dispositivo móvel. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Suporte ao Multiple Exchange Connector <!-- 2070451 -->
Você não fica mais limitado a um Microsoft Intune Exchange Connector por locatário. O Intune agora é compatível com vários conectores do Exchange para que você possa configurar o acesso condicional do Intune com diversas organizações do Exchange locais.

Com um conector do Exchange local do Intune, você pode gerenciar o acesso ao dispositivo para suas caixas de entrada do Exchange local com base em se um dispositivo é registrado no Intune e está em conformidade com as políticas de conformidade de dispositivo do Intune. Para configurar um conector, baixe o conector do Exchange local do Portal do Azure no Intune e instale-o em um servidor na sua organização do Exchange. No painel do Microsoft Intune, escolha **Acesso local** e, em **Configuração**, selecione **Conector do Exchange ActiveSync**. Baixe o conector local do Exchange local e instale-o em um servidor na sua organização do Exchange. Agora que não há mais o limite de um conector do Exchange por locatário, se você tiver organizações do Exchange adicionais, siga este mesmo processo para baixar e instalar um conector para cada organização do Exchange adicional.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Detalhes do novo hardware do dispositivo: CCID <!-- 2156657 -->
As informações de CCID (Dispositivo de Interface de Cartão de Chip) agora estão incluídas para cada dispositivo. Para vê-las, selecione **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**> marque **Detalhes da rede**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Atribua todos os usuários e dispositivos como grupos de escopo <!-- 2196803 -->
Você agora pode atribuir todos os dispositivos e todos os usuários e todos os dispositivos aos grupos no escopo. Para fazer isso, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de política e perfil** > **Atribuições** > escolher uma atribuição > **Escopo (grupos)**.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806-wnready--"></a>Informações de UDID agora estão incluídas para dispositivos iOS e macOS <!-- 2219806 wnready-->
Para ver o UDID (Identificador Exclusivo de Dispositivo) para dispositivos iOS e macOS, acesse **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**. O UDID só está disponível para dispositivos corporativos, conforme definido em **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Propriedades** > **Propriedade do dispositivo**.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Solução aprimorada de problemas de instalação do aplicativo <!-- 928990 -->
Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. Estamos enviando uma Visualização Pública dos nossos recursos de Solução de Problemas de Aplicativo. Você observará um novo nó em cada dispositivo individual com o nome **Aplicativos Gerenciados**. Ele lista os aplicativos que foram entregues por meio do MDM do Intune. Dentro do nó, você verá uma lista dos estados de instalação do aplicativo. Se você selecionar um aplicativo individual, verá o modo de exibição de solução de problemas desse aplicativo específico. Na exibição de solução de problemas, você verá o ciclo de vida completo do aplicativo, por exemplo, quando o aplicativo foi criado, modificado, direcionado e entregue a um dispositivo. Além disso, se a instalação do aplicativo não for bem-sucedida, você receberá o código de erro e uma mensagem útil sobre a causa do erro. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Políticas de proteção de aplicativo do Intune e Microsoft Edge <!-- 1818968 -->
O navegador Microsoft Edge para dispositivos móveis (iOS e Android) agora é compatível com as políticas de proteção de aplicativo do Microsoft Intune. Os usuários de dispositivos iOS e Android que entrarem com suas contas corporativas do Azure AD no aplicativo Microsoft Edge estarão protegidos pelo Intune. Em dispositivos iOS, a política **Exigir navegador gerenciado para conteúdo da Web** permitirá aos usuários abrir links no Microsoft Edge quando ele for gerenciado.

## <a name="week-of-may-14-2018"></a>Semana de 14 de maio de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Requer a instalação de perfis de políticas, aplicativos, certificado e rede <!-- 1553555 -->

Os administradores podem impedir que usuários finais acessem a área de trabalho do Windows 10 RS4 até que o Intune instale políticas, aplicativos e perfis de certificado e de rede durante o provisionamento de dispositivos AutoPilot. Para obter mais informações, consulte [Configurar uma página de status de registro](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Configurar políticas de proteção do aplicativo <!-- 2144597 Part 2 -->

No portal do Azure, em vez de acessar a folha do serviço de Proteção de Aplicativo do Intune, vá apenas até o Intune. Agora, há apenas uma localização para políticas de proteção de aplicativo no Intune. Observe que todas as suas políticas de proteção de aplicativo estão na folha **Aplicativo móvel** no Intune em **Políticas de proteção de aplicativo**. Essa integração ajuda a simplificar a administração do gerenciamento de nuvem. Lembre-se de que todas as políticas de proteção do aplicativo já estão no Intune e você pode modificar qualquer uma das políticas configuradas anteriormente. As políticas de APP (Proteção de Política de Aplicativo) e de CA (Acesso Condicional) do Intune estão agora em **Acesso condicional**, que pode ser encontrado na seção **Gerenciar** na folha **Microsoft Intune** ou na seção **Segurança** na folha **Azure Active Directory**. Para obter mais informações sobre como modificar políticas de acesso condicional, consulte [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Para obter mais informações, consulte [Quais são as políticas de proteção do aplicativo?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>Semana de 7 de maio de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Suporte à inscrição no Samsung Knox Mobile <!--1112863-->

Ao usar o Intune com a inscrição no Samsung Knox Mobile (KME), você pode inscrever vários dispositivos Android corporativos. Os usuários em redes de celular ou Wi-Fi podem inscrever seus dispositivos com apenas alguns toques ao o ligarem pela primeira vez. Ao usar o Aplicativo de Implantação do Knox, os dispositivos podem ser inscritos usando Bluetooth ou NFC. Para saber mais, confira [Inscrever automaticamente os dispositivos Android usando o Knox Mobile Enrollment da Samsung](android-samsung-knox-mobile-enroll.md).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Solicitar ajuda no Portal de Empresa para Windows 10 <!-- 1874137 -->

Agora, o Portal da Empresa para Windows 10 envia logs de aplicativo diretamente à Microsoft quando o usuário inicia o fluxo de trabalho para obter ajuda com um problema. Isso facilitará a solução de problemas enviados para a Microsoft.

## <a name="week-of-april-23-2018"></a>Semana de 23 de abril de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Suporte de senha para o PIN de MAM no Android<!-- 1438086 -->

Os administradores do Intune podem definir um requisito de inicialização do aplicativo para impor uma senha, em vez de um PIN numérico de MAM. Se configurado, o usuário precisa definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. O Intune é compatível com senha de maneira semelhante ao PIN numérico existente, sendo capaz de definir um tamanho mínimo, permitindo caracteres e sequências repetidos por meio do console do administrador. Este recurso requer a versão mais recente do Portal da Empresa no Android. Esse recurso já está disponível para iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Suporte para aplicativo de LOB (linha de negócios) do macOS <!-- 1473977 -->
O Microsoft Intune oferecerá a capacidade de instalar aplicativos de LOB macOS do Portal do Azure. Você poderá adicionar um aplicativo de LOB macOS ao Intune depois de ele ter sido previamente processado pela ferramenta disponível no GitHub. No Portal do Azure, escolha **Aplicativos móveis** na folha **Intune**. Na folha **Aplicativos móveis**, escolha **Aplicativos** > **Adicionar**. Na folha **Adicionar Aplicativo**, selecione **Aplicativo de linha de negócios**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Grupos Todos os Usuários e Todos os Dispositivos internos para atribuição de aplicativo AFW (Android for Work) <!-- 1813073 -->
Você pode aproveitar os grupos **Todos os Usuários** e **Todos os Dispositivos** internos em uma atribuição de aplicativo AFW. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>O Intune reinstalará os aplicativos necessários que são desinstalados pelos usuários <!-- 1947010 -->
Se um usuário final desinstalar um aplicativo necessário, o Intune reinstalará automaticamente o aplicativo dentro de 24 horas em vez de aguardar o ciclo de reavaliação de 7 dias.

### <a name="device-configuration"></a>Configuração do dispositivo

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>A lista de status e gráfico de perfil do dispositivo mostra todos os dispositivos em um grupo <!-- 1449153 eeready -->
Quando você configura um perfil de dispositivo (**Configuração do dispositivo** > **Perfis**), escolha o perfil do dispositivo, como iOS. Você pode atribuir esse perfil a um grupo que inclua dispositivos iOS e dispositivos não iOS. A contagem de gráfico mostra que o perfil é aplicado a dispositivos iOS *e* não iOS (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral**). Quando você seleciona o gráfico na guia **Visão geral**, o **Status do dispositivo** lista todos os dispositivos no grupo, em vez de apenas os dispositivos iOS. 

Com essa atualização, o gráfico (**Configuração do dispositivo** > **Perfis** > Selecione um perfil existente > **Visão geral**) mostrará apenas a contagem para o perfil de dispositivo específico. Por exemplo, se o perfil do dispositivo de configuração se aplicar a dispositivos iOS, o gráfico listará somente a contagem de dispositivos iOS. Selecionar o gráfico e abrir o **Status do dispositivo** lista apenas os dispositivos iOS.

Enquanto essa atualização está sendo feita, o gráfico do usuário é removido temporariamente. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On para Windows 10 <!--1333666 -->

No momento, [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) pode ser usado em dispositivos Windows 10 usando um perfil de VPN (rede virtual privada) personalizado criado usando o OMA-URI.

Com essa atualização, os administradores podem habilitar o Always On para perfis de VPN do Windows 10 diretamente no Intune no Portal do Azure. Perfis de VPN Always On conectam-se automaticamente quando:

- Os usuários fazem logon em seus dispositivos
- A rede no dispositivo muda
- A tela do dispositivo é ativada novamente depois de ser desligada

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Novas configurações de impressora para perfis de educação <!-- 1308900 -->

Para perfis de educação, novas configurações estão disponíveis na categoria **Impressoras**: **Impressoras**, **Impressora padrão**, **Adicionar novas impressoras**.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Mostrar as informações sobre a chamada no perfil pessoal – Android for Work <!--1098984 -->
Ao usar um perfil particular em um dispositivo, os usuários finais não poderão ver os detalhes das informações sobre a chamada de um contato de trabalho. 

Com essa atualização, há uma nova configuração em **Android for Work** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
- Exibir a identificação do chamador do contato de trabalho no perfil pessoal

Quando esta opção está habilitada (não configurada), os detalhes de contato comercial do chamador são exibidos no perfil pessoal. Quando bloqueada, o número de contato comercial do chamador não é exibido no perfil pessoal. 

Aplicável a: dispositivos Android de perfil de trabalho no sistema operacional Android v6.0 e mais recentes

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Novas configurações do Windows Defender Credential Guard adicionadas às configurações de proteção de ponto de extremidade <!--1102252 --><!--from 1802 and 1804-->

Com essa atualização, o [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Configuração do dispositivo** > **Perfis** > **Proteção do ponto de extremidade**) inclui as seguintes configurações: 

- **Windows Defender Credential Guard**: ativa a proteção de credenciais com segurança baseada em virtualização. Habilitar este recurso ajuda a proteger as credenciais na próxima reinicialização quando as opções **Nível de segurança de plataforma com a inicialização segura** e **Segurança baseada em virtualização** estiverem habilitadas. As opções incluem:
  - **Desabilitada**: se o Credential Guard tiver sido ativado anteriormente com a opção **Habilitado sem bloqueio**, então, ele desativará o Credential Guard remotamente.

  - **Habilitada com o bloqueio UEFI**: garante que o Credential Guard não possa ser desabilitado com a chave do Registro ou usando a Política de Grupo. Para desabilitar a Proteção de Credenciais depois de usar essa configuração, você deve definir a Política de Grupo como "Desabilitada". Em seguida, remova a funcionalidade de segurança de cada computador, com um usuário fisicamente presente. Essas etapas limpam a configuração mantida no UEFI. Enquanto a configuração da UEFI for mantida, o Credential Guard estará habilitado.

  - **Habilitada sem bloqueio**: permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, pelo menos, o Windows 10 (versão 1511).

As seguintes tecnologias dependentes são habilitadas automaticamente ao configurar o Credential Guard: 

  - **Habilitar a VBS (segurança baseada em virtualização)**: ativa a VBS (segurança baseada em virtualização) na próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para fornecer suporte aos serviços de segurança e exige a Inicialização Segura.
  - **Inicialização segura com DMS (Acesso direto à memória)**: ativa a VBS com inicialização segura e acesso direto à memória. As proteções de DMA exigem suporte de hardware e serão habilitadas somente em dispositivos configurados adequadamente. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Use um nome de entidade personalizado no certificado SCEP <!-- 2064190 -->
Você pode usar o nome comum **OnPremisesSamAccountName** em uma entidade personalizada em um perfil de certificado SCEP. Por exemplo, você pode usar `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Bloquear capturas de tela e a câmera no Android for Work <!-- 1098977 eeready-->
Duas novas propriedades estão disponíveis para bloqueio quando você configurar as restrições de dispositivo para dispositivos Android: 
- Câmera: bloqueia o acesso a todas as câmeras no dispositivo
- Captura de tela: bloqueia a captura de tela e também impede que o conteúdo seja mostrado em dispositivos de exibição que não tenham uma saída de vídeo segura

Aplica-se a Android for Work.


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Novas etapas de registro para usuários em dispositivos com macOS High Sierra 10.13.2+ <!--1734567 -->
O macOS High Sierra 10.13.2 introduziu o conceito de registro do MDM "Aprovado pelo Usuário". As inscrições aprovadas permitem que o Intune gerencie algumas configurações sensíveis de segurança. Para obter mais informações, consulte a documentação de suporte da Apple aqui: https://support.apple.com/HT208019.

Dispositivos registrados usando o Portal da Empresa macOS são considerados "Não Aprovados pelo Usuário", a menos que o usuário final abra as Preferências do Sistema e dê manualmente sua aprovação. Para esse fim, o Portal da Empresa macOS agora direciona os usuários em macOS 10.13.2 e acima e aprovar manualmente o registro no final do processo de registro. O console do administrador do Intune relatará se um dispositivo registrado for aprovado pelo usuário.



### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>A Proteção Avançada contra Ameaças (ATP) e o Intune estão totalmente integrados <!-- EEready 1629303 -->

[ATP (Proteção Avançada contra Ameaças)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) mostra o nível de risco de dispositivos Windows 10. Na Central de Segurança do Windows Defender (portal da ATP), você pode criar uma conexão ao Microsoft Intune. Depois de criada, uma política de conformidade do Intune é usada para determinar um nível de ameaça aceitável. Se o nível de ameaça for excedido, uma política de acesso condicional do Azure Active Directory (AD) poderá bloquear o acesso a aplicativos diferentes na organização.

Esse recurso permite que a ATP examine arquivos, detecte ameaças e relate qualquer risco em seus dispositivos Windows 10.

Veja [Habilitar a ATP com acesso condicional no Intune](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Suporte para dispositivos sem usuário <!-- 1637553 -->
O Intune é compatível com a capacidade de avaliar a conformidade em um dispositivo sem usuário, como o Microsoft Surface Hub. A política de conformidade pode ter como destino dispositivos específicos. Assim, a conformidade (e a não conformidade) pode ser determinada para dispositivos que não tenham um usuário associado.

#### <a name="delete-autopilot-devices----1713650---"></a>Excluir dispositivos AutoPilot <!-- 1713650 -->
Os administradores do Intune podem [excluir dispositivos do AutoPilot](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Experiência de exclusão do dispositivo aprimorada <!--1832333 -->
Você não precisa mais remover dados da empresa, nem fazer uma redefinição de fábrica do dispositivo antes de [excluir um dispositivo do Intune](devices-wipe.md#delete-devices-from-the-intune-portal).

Para ver a nova experiência, entre no Intune e selecione **Dispositivos** > **Todos os Dispositivos** > nome do dispositivo > **Excluir**.

Se você ainda quiser apagar/desativar a confirmação, poderá usar a rota de ciclo de vida do dispositivo padrão emitindo **Remover dados da empresa** e **Redefinição de Fábrica** antes de **Excluir**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Tocar sons no iOS quando no modo Perdido <!-- 1947769 -->
Quando dispositivos iOS supervisionados estiverem no [modo Perdido](device-lost-mode.md) do MDM (gerenciamento de dispositivo móvel), você poderá [tocar um som](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Dispositivos** > **Todos os dispositivos** > Selecione um dispositivo iOS > **Visão geral** > **Mais**). O som continua sendo reproduzido até o dispositivo ser removido do Modo perdido ou um usuário desabilitar o som no dispositivo. Aplica-se a dispositivos iOS 9.3 e mais recentes.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Bloquear ou permitir os resultados da Web em pesquisas feitas em um dispositivo do Intune <!--1972804-->

Os administradores agora podem bloquear os resultados da Web de pesquisas feitas em um dispositivo.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Mensagens de erro aprimoradas para falha no upload do Apple MDM Push Certificate <!-- 2172331 -->

A mensagem de erro explica que a mesma ID da Apple deve ser usada durante a renovação de um certificado existente do MDM.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Teste o Portal da Empresa para macOS em máquinas virtuais <!-- 2216679 -->

Publicamos as orientações para ajudar os administradores de TI a testar o aplicativo do Portal da Empresa para macOS em máquinas virtuais no Parallels Desktop e no VMware Fusion. Saiba mais em [Registrar máquinas macOS virtuais para teste](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### <a name="user-interface"></a>Interface do usuário

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Blocos de dispositivo aprimorados no Portal da Empresa do Windows 10 <!--2213364 -->

Os blocos foram atualizados para serem mais acessíveis aos usuários com visão subnormal e para apresentarem um desempenho melhorado nas ferramentas de leitura de tela.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Enviar relatórios de diagnóstico no aplicativo de Portal da Empresa para macOS <!-- 2216677 -->
O aplicativo do Portal da Empresa para dispositivos macOS foi atualizado para melhorar o modo como os usuários relatam erros relacionados ao Intune. No aplicativo Portal da Empresa, seus funcionários podem:

- Carrega relatórios de diagnóstico diretamente para a equipe de desenvolvedores Microsoft.
- Envie por email uma ID de incidente à equipe de suporte de TI da sua empresa.

Para obter mais informações, consulte [Enviar erros para o macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>O Intune se adapta ao Fluent Design System no aplicativo do Portal da Empresa para o Windows 10 <!-- 1195010 WNready -->
O aplicativo do Portal da Empresa do Intune para Windows 10 foi atualizado com a [exibição de navegação do Fluent Design System](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). No lado do aplicativo, você verá uma lista estática e vertical de todas as páginas de nível superior. Clique em qualquer link para exibir e alternar rapidamente entre as páginas. Esta é a primeira de várias atualizações que você verá como parte de nosso esforço contínuo de criar uma experiência mais adaptável, intuitiva e familiar no Intune. Para ver a aparência atualizada, vá para [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Semana de 16 de abril de 2018

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Usar o cliente do Cisco AnyConnect para iOS <!-- EEready 1333708 -->

Quando você cria um novo perfil de VPN para iOS, agora há duas opções: **Cisco AnyConnect** e **Cisco Legacy AnyConnect**. Os perfis do Cisco AnyConnect 4.0.7x são compatíveis com o 4.0.7x e versões mais recentes. Os perfis existentes de VPN do Cisco AnyConnect do iOS são rotulados como **Cisco Legacy AnyConnect** e continuarão a funcionar com o Cisco AnyConnect 4.0.5x e versões anteriores, como fazem atualmente.

> [!NOTE]
> Essa alteração se aplica apenas ao iOS. Continuará existindo apenas uma opção do Cisco AnyConnect para plataformas do Android, Android for Work e macOS.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Os dispositivos macOS registrados em Jamf já podem se registrar no Intune <!-- 2370684 -->

As versões 1.3 e 1.4 do portal da empresa do macOS não registraram com êxito os dispositivos Jamf no Intune. A versão 1.4.2 do portal do macOS corrige esse problema.


## <a name="week-of-april-9-2018"></a>Semana de 9 de abril de 2018

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Experiência de ajuda atualizada no aplicativo Portal da Empresa para Android <!-- 1631531 -->

Nós atualizamos a experiência da ajuda no aplicativo Portal da Empresa para Android com base nas práticas recomendadas para a plataforma Android. Agora, quando os usuários encontram um problema no aplicativo, eles poderão tocar em **Menu** > **Ajuda** e:
- Faça o upload dos de diagnóstico para a Microsoft.
- Envie um email que descreva a ID do problema e do incidente para um profissional de suporte da empresa.  

Para conferir a experiência de ajuda atualizada, acesse [Enviar logs usando o email](/intune-user-help/send-logs-to-your-it-admin-by-email-android) e [Enviar erros à Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Novo gráfico de tendência de falha de registro e tabela de motivos de falhas<!-- 1471783 -->

Na página Visão Geral do Registro, você poderá exibir a tendência de falhas de registro e as cinco principais causas de falhas. Ao clicar no gráfico ou na tabela, você poderá analisar os detalhes para encontrar solução de correção e dicas de solução de problemas.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Atualizar o local no qual configurar as políticas de proteção do aplicativo <!-- 2144597 -->

No Portal do Azure no serviço do Microsoft Intune, vamos temporariamente redirecioná-lo da folha de serviço **Proteção de Aplicativo do Intune** para a folha **Aplicativo móvel**. Observe que todas as suas políticas de proteção de aplicativo já estão na folha de **Aplicativo Móvel** do Intune, em configuração do aplicativo. Em vez de acessar a Proteção de Aplicativo do Intune, basta acessar o Intune. Em abril de 2018, interromperemos o redirecionamento e removeremos totalmente a folha de serviço da **Proteção de Aplicativo do Intune**, para que haja apenas um local para as políticas de proteção de aplicativos no Intune. 

**Como isso me afeta?**
Essa alteração afeta os clientes do Intune autônomo e os clientes do híbrido (Intune com o Configuration Manager). Essa integração ajudará a simplificar a administração do gerenciamento da nuvem.

**O que preciso fazer para me preparar para essa alteração?**
Marque o **Intune** como um favorito, em vez da folha de serviço da **Proteção de Aplicativo do Intune** e familiarize-se com o fluxo de trabalho da política de proteção de Aplicativo na folha de aplicativo **Móvel** no Intune. Você será redirecionado por um breve período e, em seguida, removeremos a folha **Proteção de Aplicativo**. Lembre-se de que todas as políticas de proteção do aplicativo já estão no Intune e você pode modificar qualquer uma das suas políticas de acesso condicional. Para obter mais informações sobre como modificar políticas de acesso condicional, consulte [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Para obter mais informações, consulte [Quais são as políticas de proteção do aplicativo?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>Semana de 2 de abril de 2018

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!--1412866 -->
Lançamos uma atualização principal da experiência do usuário para o aplicativo Portal da Empresa para iOS. A atualização apresenta um novo design visual completo que inclui uma aparência modernizada. Mantivemos a funcionalidade do aplicativo, mas aumentamos sua usabilidade e acessibilidade.  

Você também verá:
- Suporte para iPhone X.
- Mais rapidez na inicialização do aplicativo e no carregamento de respostas para economizar tempo para os usuários.
- Barras de progresso adicionais para fornecer aos usuários as informações de status mais atualizadas.
- Melhorias às maneiras como os usuários carregam logs, portanto, se algo der errado, será mais fácil relatar.  

Para ver a aparência atualizada, vá para [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

#### <a name="protect-on-premise-exchange-data-using-intune-app-and-ca----1056954---"></a>Proteger dados do Exchange locais usando o aplicativo do Intune e a AC <!-- 1056954 -->
Agora você pode usar o APP (Proteção de Política do Aplicativo) do Intune e o AC (Acesso Condicional) para proteger o acesso a dados locais do Exchange com o Outlook Mobile. Para adicionar ou modificar uma política de proteção do aplicativo no Portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Políticas de proteção do aplicativo**. Antes de usar esse recurso, verifique se você atende aos [requisitos do Outlook para iOS e Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="week-of-march-26-2018"></a>Semana de 26 de março de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Alertas para a expiração de aplicativos de LOB (linha de negócios) do iOS para Microsoft Intune <!-- 748789 -->

No Portal do Azure, o Intune o alertará sobre aplicativos de linha de negócios iOS que estão prestes a expirar. Após carregar uma nova versão do aplicativo de linha de negócios iOS, o Intune remove a notificação de expiração da lista de aplicativos. Esta notificação de expiração somente ficará ativa para aplicativos de linha de negócios iOS recém-carregados. Um aviso aparecerá 30 dias antes da expiração do perfil de provisionamento de aplicativo do iOS LOB. Quando expirar, o alerta mudará para Expirado.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Personalize os temas do Portal da Empresa com códigos hexadecimais <!--1049561 -->

Você pode personalizar a cor do tema nos aplicativos do Portal da Empresa usando códigos hexadecimais. Ao inserir o código hexadecimal, o Intune determina a cor do texto que oferece o maior nível de contraste entre a cor do texto e a cor da tela de fundo. É possível visualizar a cor do texto e o logotipo da empresa em relação à cor em **Aplicativos móveis** > **Portal da Empresa**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos para Android Enterprise <!-- 1813081 -->

Android Enterprise (anteriormente conhecido como Android for Work) é compatível com a inclusão e a exclusão de grupos, mas não com grupos internos de **Todos os Usuários** e **Todos os Dispositivos** pré-criados. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Novos aprimoramentos de segurança no serviço do Intune <!-- 1637539 -->   

Apresentamos uma alternância do Intune no Azure que os clientes autônomos do Intune podem usar para tratar os dispositivos sem qualquer política atribuída como **Em conformidade** (recurso de segurança desligado) ou tratar esses dispositivos como **Não em conformidade** (recurso de segurança ligado). Isso garantirá acesso aos recursos somente após a avaliação de conformidade do dispositivo.

Esse recurso afeta você de maneira diferente dependendo se você já tem políticas de conformidade atribuídas ou não.

- Se você for uma conta nova ou existente e não tiver nenhuma política de conformidade atribuída aos seus dispositivos, a alternância será definida automaticamente como **Em conformidade**. O recurso está desligado como uma configuração padrão no console. Não há nenhum impacto ao usuário final.
- Se você for uma conta existente e tiver qualquer dispositivo com uma política de conformidade atribuída, a alternância será definida automaticamente como **Não em conformidade**. O recurso está ligado como uma configuração padrão conforme a atualização de março é implantada.

Se você usar políticas de conformidade com CA (Acesso Condicional) e o recurso estiver ativado, os dispositivos que não tiverem pelo menos uma política de conformidade atribuída agora serão bloqueados pelo CA. Os usuários finais associados a esses dispositivos, que anteriormente tinham permissão de acesso ao email, perderão o acesso, a menos que você atribua pelo menos uma política de conformidade a todos os dispositivos.   

Observe que, embora o status de alternância padrão seja exibido na interface do usuário imediatamente com as atualizações do serviço do Intune feitas em março, esse status de alternância não é imposto imediatamente. Alterações feitas à alternância não terá impacto sobre a conformidade do dispositivo até habilitarmos sua conta para ter uma alternância operando. Você será informado por meio do Centro de Mensagens quando terminamos de habilitar sua conta. Isso pode levar alguns dias depois que o serviço do Intune for atualizado para março.

**Informações adicionais**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Detecção de jailbreak avançada <!-- 846515 -->

A detecção de jailbreak avançada é uma nova configuração de conformidade que melhora a maneira como o Intune avalia os dispositivos desbloqueados por jailbreak. A configuração faz o dispositivo realizar check-in com o Intune com mais frequência, o que utiliza os serviços de localização do dispositivo e afeta o uso da bateria.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Redefina senhas de dispositivos Android O <!-- 1238299 -->
Você poderá redefinir senhas para dispositivos com Android 8.0 registrados com perfis de Trabalho. Quando você envia uma solicitação de "Redefinir senha" a um dispositivo Android 8.0, ele define uma nova senha de desbloqueio de dispositivo ou um desafio de perfil gerenciado para o usuário atual. A senha ou o desafio é enviado e entra em vigor imediatamente.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Direcionamento de políticas de conformidade para dispositivos em grupos de dispositivo <!--1307012 -->

Você pode direcionar políticas de conformidade para usuários em grupos de usuários. Com essa atualização, você pode direcionar políticas de conformidade para dispositivos em grupos de dispositivo. Dispositivos de destino como parte de grupos de dispositivos não receberão as ações de conformidade.

#### <a name="new-management-name-column----1333586---"></a>Coluna Novo nome de gerenciamento <!-- 1333586 -->
 Uma nova coluna chamada **Nome de gerenciamento** está disponível na folha de dispositivos. Este é um nome não editável gerado automaticamente atribuído por dispositivo, com base na seguinte fórmula:
- Nome padrão para todos os dispositivos: <username><em><devicetype></em><enrollmenttimestamp>
- Para dispositivos adicionados em massa: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Esta é uma coluna opcional na folha de dispositivos. Ele não está disponível por padrão e você poderá acessá-lo apenas por meio do seletor de colunas. O nome do dispositivo não é afetado por essa nova coluna.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Os dispositivos iOS solicitam um PIN a cada 15 minutos <!--1550837 -->
Depois que uma política de conformidade ou de configuração for aplicada a um dispositivo iOS, os usuários serão solicitados a definir um PIN a cada 15 minutos. Os usuários são notificados continuamente até que um PIN seja definido.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Agendar suas atualizações automáticas <!--1805514 -->
Com o Intune, você controla como instalar atualizações automáticas usando as [configurações do Grupo de Atualização do Windows](windows-update-for-business-configure.md). Com essa atualização, você pode agendar atualizações recorrentes, incluindo semana, dia e hora.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Use o nome totalmente diferenciado como assunto para o certificado SCEP <!--2221763 -->
Quando você cria um perfil de certificado SCEP, você inserir o Nome do assunto. Com essa atualização, você pode usar o nome totalmente diferenciado como a entidade. Para **Nome do assunto**, selecione **Personalizado** e, em seguida, digite `CN={{OnPrem_Distinguished_Name}}`. Para usar a variável `{{OnPrem_Distinguished_Name}}`, sincronize o atributo de usuário `onpremisesdistingishedname` usando o [Azure AD (Active Directory) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) com seu Azure AD.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Habilitar compartilhamento de contatos por Bluetooth – Android for Work <!--1098983 -->
Por padrão, o Android impede que contatos no perfil de trabalho sejam sincronizados com dispositivos Bluetooth. Como resultado, os contatos do perfil de trabalho não são exibidos nas informações sobre a chamada para dispositivos Bluetooth.

Com essa atualização, há uma nova configuração em **Android for Work** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
- Compartilhamento de contatos por Bluetooth

O administrador do Intune pode configurar essas configurações para habilitar o compartilhamento. Isso é útil ao emparelhar um dispositivo com um dispositivo Bluetooth baseado em carro que exibe as informações sobre a chamada para uso não assistido. Quando habilitados, os contatos de perfil de trabalho são exibidos. Quando não habilitados, os contatos de perfil de trabalho não serão exibidos.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Configurar o Gatekeeper para controlar a origem do download do aplicativo macOS <!-- 1690459 -->

Você pode configurar o Gatekeeper para proteger os dispositivos de aplicativos, controlando de que local os aplicativos podem ser baixados. Você pode configurar as seguintes fontes de download: **Mac App Store**, **Mac App Store e desenvolvedores identificados** ou **De qualquer lugar**. Você também pode configurar se os usuários podem instalar um aplicativo usando CTRL + clique para substituir esses controles do Gatekeeper.

Essas configurações podem ser encontradas em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Configurar o firewall do aplicativo Mac <!-- 1690461 -->

Você pode configurar o firewall do aplicativo Mac. Você pode usar isso para controlar as conexões por aplicativo, em vez de por porta. Isso facilita obter os benefícios da proteção de firewall e ajuda a impedir que aplicativos indesejáveis assumam o controle de portas de rede abertas para aplicativos legítimos.

Esse recurso pode ser encontrado em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

Depois de habilitar a configuração de Firewall, você pode configurar o firewall usando duas estratégias:

- Bloquear todas as conexões de entrada

   É possível bloquear todas as conexões de entrada para os dispositivos de destino. Se você optar por fazer isso, as conexões de entrada serão bloqueadas para todos os aplicativos.

- Permitir ou bloquear aplicativos específicos

   Você pode permitir ou bloquear que aplicativos específicos recebam conexões de entrada. Você também pode habilitar o modo furtivo para impedir respostas para as solicitações de sondagem.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Códigos de erro e mensagens detalhados <!-- 1376342 -->

Em sua configuração de dispositivo, há códigos de erro e mensagens de erro mais detalhados disponíveis para visualização. Esse relatório aprimorado mostra as configurações, o estado dessas configurações e os detalhes sobre como solucionar problemas.

##### <a name="more-information"></a>Mais informações

- Bloquear todas as conexões de entrada

   Isso impede que todos os serviços de compartilhamento (como Compartilhamento de arquivos e Compartilhamento de tela) recebam conexões de entrada. Os serviços do sistema que ainda têm permissão para receber conexões de entrada são:
  - configd – implementa DHCP e outros serviços de configuração de rede
  - mDNSResponder – implementa o Bonjour
  - racoon – implementa IPsec

    Para usar os serviços de compartilhamento, verifique se **Conexões de entrada** está definido como **Não configurado** (não **Bloqueado**).

- Modo furtivo

   Habilite esta opção para impedir que o computador responda às solicitações de sondagem. O computador ainda responde a solicitações de entrada para aplicativos autorizados. Solicitações inesperadas, como o ICMP (ping), são ignoradas.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Desabilitar verificações na reinicialização do dispositivo <!--1805490 -->
O Intune fornece controle para [gerenciar atualizações de software](windows-update-for-business-configure.md). Com essa atualização, a propriedade <strong>Reiniciar verificações</strong> está disponível e habilitada por padrão. Para ignorar as verificações típicas que ocorrem quando você reinicia um dispositivo (como usuários ativos, níveis de bateria e assim por diante), selecione <strong>Ignorar</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Novos canais do Windows 10 Insider Preview disponíveis para anéis de implantação <!-- 1746293 -->
Agora você tem a opção de selecionar os seguintes canais de serviço do Windows 10 Insider Preview ao criar um anel de implantação do Windows 10:
- Build do Windows Insider &#8208; rápido
- Build do Windows Insider &#8208; lento
- Liberar build do Windows Insider 

Para obter mais informações sobre esses canais, consulte [Gerenciar builds do Insider Preview](https://insider.windows.com/en-us/for-business-organization-admin/).   
Para obter mais informações sobre como criar canais de implantação no Intune, consulte [Gerenciar atualizações de software no Intune](windows-update-for-business-configure.md).

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Registro do Portal da Empresa melhorado <!-- 1874230 eeready-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior agora podem concluir a primeira etapa de registro sem sair do aplicativo.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>Agora o HoloLens e o Surface Hub são exibidos nas listas de dispositivos <!--1725868 -->
Adicionamos suporte para mostrar dispositivos HoloLens e Surface Hub registrados no Intune no aplicativo Portal da Empresa para Android.

#### <a name="custom-book-categories-for-volume-purchase-progream-vpp-ebooks----1488911---"></a>Categorias de livro personalizadas para livros eletrônicos do VPP (Volume Purchase Program) <!-- 1488911 -->
Você pode criar categorias de livros eletrônicos personalizadas e atribuir livros eletrônicos do VPP a essas categorias personalizadas. Os usuários finais poderão ver as categorias de livro eletrônico recém-criadas e os livros atribuídos às categorias. Para obter mais informações, consulte [Gerenciar aplicativos e livros comprados por volume com o Microsoft Intune](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Mudanças de suporte para a opção de comentários do aplicativo Portal da Empresa para Windows <!-- 2070166 -->
A partir de 30 de abril de 2018, a opção **Enviar Comentários** no aplicativo Portal da Empresa para Windows funcionará apenas em dispositivos que executam a Atualização de Aniversário do Windows 10 (1607) e posterior. Não há mais suporte para a opção de enviar comentários ao usar o aplicativo Portal da Empresa para Windows com:  
- Windows 10, versão 1507  
- Windows 10, versão 1511  
- Windows Phone 8.1 

Se o seu dispositivo estiver executando no Windows 10 RS1 ou posterior, baixe a versão mais recente do aplicativo Portal da Empresa do Windows na Store. Se você estiver executando uma versão sem suporte, continue a enviar comentários por meio destes canais: 
- Aplicativo Hub de Comentários no Windows 10
- Email WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Novas configurações do Windows Defender Application Guard <!-- 1631890 -->

- **Habilitar aceleração de elementos gráficos**: os administradores poderão habilitar um processador de gráficos virtual para o Windows Defender Application Guard. Essa configuração permite que a CPU descarregue a renderização de gráficos no vGPU. Isso pode melhorar o desempenho ao trabalhar com sites com uso intenso de gráficos ou ao assistir a vídeos dentro do contêiner.

- **SaveFilestoHost**: os administradores poderão permitir que arquivos sejam passados do Microsoft Edge em execução no contêiner para o sistema de arquivos do host. Ativar essa configuração permite que os usuários baixem arquivos do Microsoft Edge no contêiner para o sistema de arquivos do host.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Políticas de proteção MAM definidas como destino com base no estado de gerenciamento <!-- 1665993 -->
Você pode ter como destino políticas de MAM com base no estado de gerenciamento do dispositivo:
- **Dispositivos Android** – você poderá ter como destino dispositivos não gerenciados, dispositivos gerenciados pelo Intune e Perfis do Android Enterprise gerenciados pelo Intune (anteriormente Android for Work).
- **Dispositivos iOS** – você poderá ter como destino dispositivos não gerenciados (somente MAM) ou dispositivos gerenciados pelo Intune.

    > [!NOTE]
    > - O suporte do iOS para essa funcionalidade será implantado em abril de 2018.

Para obter mais informações, consulte [Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Melhorias à linguagem no aplicativo Portal da Empresa para Windows <!-- 1683758 -->
Melhoramos a linguagem no Portal da Empresa para Windows 10 para ser mais amigável e específica para sua empresa. Para ver algumas amostras de imagens do que já fizemos, consulte [novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Novas adições aos nossos documentos sobre privacidade do usuário <!-- 1440709 -->
Como parte dos nossos esforços para dar aos usuários finais mais controle sobre seus dados e privacidade, publicamos as atualizações aos documentos que explicam como exibir e remover dados armazenados localmente usando os aplicativos do Portal da Empresa. Você pode encontrar essas atualizações no:

- **Android**: [como cancelar o registro do dispositivo Android do Intune](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, se o usuário tiver recusado os termos de uso**: [remova seu gerenciamento de dispositivo se tiver recusado os "Termos de Uso"](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [remova seu dispositivo iOS do Intune](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [remova seu dispositivo Windows do Intune](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>Semana de 19 de março de 2018

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Exportar todos os dispositivos para arquivos CSV no IE, no Edge ou no Chrome <!-- 2258071 -->
Em **Dispositivos** > **Todos os Dispositivos**, você pode **Exportar** os dispositivos para uma lista formatada em CSV. Os usuários do IE (Internet Explorer) com >10.000 dispositivos podem exportar com êxito seus dispositivos para vários arquivos. Cada arquivo tem até 10.000 dispositivos.

Os usuários do Edge e do Chrome com > 30.000 dispositivos podem exportar com êxito seus dispositivos para vários arquivos. Cada arquivo tem até 30.000 dispositivos.

[Gerenciar dispositivos](device-management.md) fornece mais detalhes sobre o que você pode fazer com os dispositivos que gerencia.

## <a name="week-of-march-12-2018"></a>Semana de 12 de março de 2018

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o aplicativo Intune Managed Browser e dar suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->

Usando o Azure AD (Azure Active Directory), agora você pode restringir o acesso a sites em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure. Para obter mais informações, consulte [Controles de acesso no acesso condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aplicativo Portal da empresa para atualizações visuais do Android <!--976944 -->

Atualizamos o aplicativo Portal da Empresa para Android para seguir as diretrizes do [Design de Material](https://material.io/) do Android. É possível ver as imagens dos novos ícones no artigo [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Novas configurações do Windows Defender Exploit Guard <!-- 1631893 -->

Seis novas configurações de <strong>Redução da Superfície de Ataque</strong> e funcionalidades expandidas de <strong>Acesso controlado a pastas: proteção de pasta</strong> agora estão disponíveis. Essas configurações podem ser encontradas em: Configuração do dispositivo\Perfis\
Criar perfil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Proteção avançada contra ransomware|Habilitado, Auditoria, Não configurado|Usar proteção agressiva contra ransomware.|
|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows|Habilitado, Auditoria, Não configurado|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows (lsass.exe).|
|Criação de processo de comandos WMI e PSExec|Bloquear, Auditoria, Não configurado|Bloquear criações de processo provenientes de comandos PSExec e WMI.|
|Processos não assinados e não confiáveis executados de um USB|Bloquear, Auditoria, Não configurado|Bloquear processos não assinados e não confiáveis executados de um USB.|
|Arquivos executáveis que não atendem um critério de prevalência, idade ou lista confiável|Bloquear, Auditoria, Não configurado|Bloquear a execução de arquivos executáveis a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.|

#### <a name="controlled-folder-access"></a>Acesso controlado à pasta

|              Nome da configuração               |                                                              Opções de configuração                                                              | Descrição |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Proteção de pasta (já implementada) | Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> <strong>Novo</strong><br>Bloquear modificação de disco, Auditar modificação de disco |             |

Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: impedir que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

## <a name="week-of-february-19-2018"></a>Semana de 19 de fevereiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 -->

Agora o Intune é compatível com o registro de dispositivos de até 100 contas diferentes do [DEP (Programa de registro de dispositivos) da Apple](device-enrollment-program-enroll-ios.md) ou do [Apple School Manager](apple-school-manager-set-up-ios.md). Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Consultar as restrições de registro por usuário <!-- 1634444 eeready wnready -->
Agora, na folha **Solucionar Problemas**, é possível ver as [restrições de registro](enrollment-restrictions-set.md) que estão em vigor para cada usuário ao selecionar **Restrições de registro** na lista **Atribuições**.

### <a name="device-management"></a>Gerenciamento de dispositivos
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Relatórios de status de ameaça e status da integridade do Windows Defender <!--854704 -->

Compreender o status da integridade e das ameaças do Windows Defender é essencial para gerenciar computadores Windows.  Com essa atualização, o Intune adiciona novos relatórios e ações ao status e à integridade do agente do Windows Defender. Usando um relatório de acúmulo de status na [carga de trabalho de Conformidade do Dispositivo](compliance-policy-monitor.md), você pode ver os dispositivos que precisam de:
- atualização de assinatura
- Reiniciar
- intervenção manual
- verificação completa
- outros estados de agente que requerem intervenção

Um relatório de análise para cada categoria de status lista os computadores individuais que precisam de atenção ou aqueles cujo estado relatado é **Limpo**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Novas configurações de privacidade para restrições de dispositivo <!--1308926 -->
Agora [duas novas configurações de privacidade](device-restrictions-windows-10.md#privacy) estão disponíveis para dispositivos:
- **Publicar as atividades do usuário**: defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas.
- **Apenas atividades locais**: defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Novas configurações para o navegador Microsoft Edge <!--1469166 -->
Agora há [duas novas configurações](device-restrictions-windows-10.md#edge-browser) disponíveis para dispositivos com o navegador Edge: **Caminho para o arquivo de favoritos** e **Alterações aos Favoritos**.

### <a name="app-management"></a>Gerenciamento de aplicativos
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Exceções de protocolo para aplicativos <!--1035509 -->

Agora você pode criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune para abrir aplicativos não gerenciados específicos. Esses aplicativos devem ser confiáveis para a TI. Exceto pelas exceções que você cria, a transferência de dados ainda fica restrita a aplicativos gerenciados pelo Intune quando sua política de transferência de dados estiver definida como **somente aplicativos gerenciados**. É possível criar as restrições usando protocolos (iOS) ou pacotes (Android).

Por exemplo, é possível adicionar o pacote do Webex como uma exceção à política de transferência de dados de MAM. Isso permitirá que links do Webex em uma mensagem de email gerenciada do Outlook sejam abertos diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados. Para obter mais informações, consulte [Exceções à política transferência de dados para aplicativos](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dados criptografados de WIP (Proteção de Informações do Windows) nos resultados da pesquisa do Windows <!-- 1469193 -->
Uma configuração na política de WIP (Proteção de Informações do Windows) agora permite que você controle se os dados criptografados por WIP são incluídos nos resultados da pesquisa do Windows. Defina essa opção da política de proteção de aplicativo por meio da seleção de **Permitir que o indexador do Windows Search pesquise itens criptografados** nas **Configurações avançadas** da política de Proteção de Informações do Windows. A política de proteção do aplicativo deve ser definida para a plataforma *Windows 10* e a política de aplicativo **Estado do registro** deve ser definida como **Com registro**. Para obter mais informações, consulte [Permitir que o indexador do Windows Search pesquise itens criptografados](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Configurando um aplicativo móvel do MSI com autoatualização <!-- 1740840 -->
Você pode configurar um aplicativo móvel do MSI com atualização automática conhecido para ignorar o processo de verificação de versão. Essa funcionalidade é útil para evitar entrar em uma condição de corrida. Por exemplo, esse tipo de condição de corrida poderá ocorrer se o aplicativo que está sendo automaticamente atualizado pelo desenvolvedor também for atualizado pelo Intune. As duas atualizações podem tentar impor uma versão do aplicativo em um cliente do Windows, o que poderia criar um conflito. Para esses aplicativos do MSI atualizados automaticamente, você pode configurar a opção **Ignorar a versão do aplicativo** na folha **Informações do aplicativo**. Quando essa configuração é definida como **Sim**, Microsoft Intune ignora a versão do aplicativo instalada no cliente do Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Conjuntos relacionados de licenças de aplicativo compatíveis com o Intune <!-- 1864117 -->
Agora o Intune no Portal do Azure é compatível com conjuntos relacionados de licenças de aplicativo como um único item de aplicativo na interface do usuário. Além disso, qualquer aplicativo licenciado offline sincronizado da Microsoft Store para Empresas será consolidado em uma única entrada de aplicativo e qualquer detalhe de implantação dos pacotes individuais será migrado para essa única entrada. Para exibir conjuntos relacionados de licenças de aplicativo no Portal do Azure, selecione **Licenças de aplicativo** na folha **Aplicativos móveis**.

### <a name="device-configuration"></a>Configuração do dispositivo
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Extensões de arquivo da WIP (Proteção de Informações do Windows) para criptografia automática <!-- 1463582 -->
Uma configuração na política da WIP (Proteção de Informações do Windows) agora permite que você especifique quais extensões de arquivo são criptografadas automaticamente ao copiar de um compartilhamento de SMB (protocolo SMB) dentro do limite corporativo, como definido na política da WIP.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Definir as configurações de conta do recurso para Surface Hubs

Você já pode definir remotamente configurações de conta do recurso para Surface Hubs.

A conta do recurso é usada por um Surface Hub para autenticar no Skype/Exchange a fim de ingressar em uma reunião.
Você poderá criar uma conta do recurso exclusiva para que o Surface Hub possa aparecer na reunião como aparece na sala de conferência.
Por exemplo, uma conta do recurso como **Sala de conferência B41/6233**.

> [!NOTE]
> - Se deixar os campos em branco, você substituirá os atributos configurados anteriormente no dispositivo.
>
> - As propriedades de conta do recurso podem ser alteradas dinamicamente no Surface Hub. Por exemplo, se a rotação de senha estiver ativada. Portanto, é possível que os valores no console do Azure levem algum tempo para refletir a realidade do dispositivo.
>
>   Para entender o que está configurado atualmente no Surface Hub, os dados da conta do recurso podem ser incluídas no inventário de hardware (que já tem um intervalo de sete dias) ou como propriedades somente leitura. Para aumentar a precisão após a ação remota ter ocorrido, você pode obter o estado dos parâmetros imediatamente após a execução da ação para atualizar a conta/parâmetros no Surface Hub.


##### <a name="attack-surface-reduction"></a>Redução da superfície de ataque


|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Execução de conteúdo executável protegido por senha no email|Bloquear, Auditoria, Não configurado|Impedir que arquivos executáveis protegidos por senha baixados por email sejam executados.|
|Proteção avançada contra ransomware|Habilitado, Auditoria, Não configurado|Usar proteção agressiva contra ransomware.|
|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows|Habilitado, Auditoria, Não configurado|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows (lsass.exe).|
|Criação de processo de comandos WMI e PSExec|Bloquear, Auditoria, Não configurado|Bloquear criações de processo provenientes de comandos PSExec e WMI.|
|Processos não assinados e não confiáveis executados de um USB|Bloquear, Auditoria, Não configurado|Bloquear processos não assinados e não confiáveis executados de um USB.|
|Arquivos executáveis que não atendem um critério de prevalência, idade ou lista confiável|Bloquear, Auditoria, Não configurado|Bloquear a execução de arquivos executáveis a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.|

##### <a name="controlled-folder-access"></a>Acesso controlado à pasta

|              Nome da configuração               |                                                              Opções de configuração                                                              | Descrição |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Proteção de pasta (já implementada) | Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> <strong>Novo</strong><br>Bloquear modificação de disco, Auditar modificação de disco |             |

Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: impedir que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Acréscimos às configurações de Segurança do sistema para políticas de conformidade do Windows 10 e posteriores <!--1704133-->

Acréscimos às configurações de conformidade do Windows 10 já estão disponíveis, incluindo a necessidade de um Firewall e do Windows Defender Antivírus.


### <a name="role-based-access-control"></a>Controle de acesso baseado em função
### <a name="intune-apps"></a>Aplicativos do Intune
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Suporte para aplicativos offline da Microsoft Store para Empresas <!--1222672-->
Aplicativos offline comprados na Microsoft Store para Empresas agora estão sincronizados com o Portal do Azure. Você pode implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Impedir que os usuários finais adicionem ou removam contas manualmente no perfil de trabalho <!-- 1728700 -->

Agora, ao implantar o aplicativo Gmail em um perfil Android for Work, você pode impedir que usuários finais adicionem ou removam contas manualmente no perfil de trabalho, usando a configuração **Adicionar e remover contas** no perfil de restrições de dispositivo do Android for Work.

## <a name="week-of-february-5-2018"></a>Semana de 5 de fevereiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nova opção de autenticação de usuário para registro em massa da Apple <!-- 747625 eeready -->

> [!NOTE]
> Os novos locatários veem essa opção imediatamente. Para locatários existentes, esse recurso será distribuído durante o mês de abril. Até essa implantação estar concluída, talvez você não tenha acesso aos novos recursos.

Agora o Intune oferece a opção para autenticar dispositivos usando o aplicativo Portal da Empresa para os seguintes métodos de registro:

- Programa de Registro do Dispositivo da Apple
- Apple School Manager
- Registro do Apple Configurator

Com a opção do Portal da Empresa, a autenticação multifator do Azure Active Directory pode ser imposta sem bloquear esses métodos de registro.

Com a opção do Portal da Empresa, o Intune ignora a autenticação do usuário no Assistente de Configuração do iOS para registro de afinidade de usuário. Isso significa que o dispositivo é registrado inicialmente como um dispositivo sem usuário e, portanto, não recebe as configurações ou políticas de grupos de usuários. Ele recebe apenas as configurações e políticas de grupos de dispositivos. No entanto, o Intune instalará automaticamente o aplicativo do Portal da Empresa no dispositivo. O primeiro usuário a iniciar e entrar no aplicativo do Portal da Empresa será associado ao dispositivo no Intune. Nesse momento, o usuário receberá as configurações e políticas de seus grupos de usuários. A associação do usuário não pode ser alterada sem um novo registro.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager<!-- 747685 eeready -->

Agora o Intune é compatível com o registro de dispositivos de até 100 contas diferentes do DEP (Programa de registro de dispositivos) da Apple ou do Apple School Manager. Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impressão remota em uma rede segura <!-- 1709994  -->
As soluções de impressão móvel sem fio do PrinterOn permitirão aos usuários imprimir remotamente de qualquer lugar, e a qualquer momento, em uma rede segura. O PrinterOn será integrado ao SDK do Aplicativo do Intune para iOS e Android. Você poderá direcionar políticas de proteção de aplicativo para esse aplicativo por meio da folha **Políticas de proteção do aplicativo** do Intune no console do administrador. Os usuários finais poderão baixar o aplicativo "PrinterOn para Microsoft" através da Play Store ou iTunes para uso no ecossistema do Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Suporte do Portal da Empresa para macOS para registros que usam o Gerenciador de Registros do Dispositivo <!-- 1352411 -->

Agora os usuários podem fazer registro no Portal da Empresa para macOS usando o Gerenciador de Registros do Dispositivo.

## <a name="week-of-january-29-2018"></a>Semana de 29 de janeiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertas para tokens expirados e tokens que expirarão em breve<!-- 1639263 -->
A página de visão geral agora mostra alertas para tokens expirados e tokens que expirarão em breve. Ao clicar em um alerta de um único token, você será levado até a página de detalhes do token.  Se você clicar no alerta com vários tokens, será levado até uma lista com todos os tokens e seu status. Os administradores devem renovar seus tokens antes da data de expiração.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Suporte ao comando "Erase" remoto para dispositivos macOS <!-- 1438084 -->

Os administradores podem emitir um comando Erase remotamente para dispositivos macOS.

> [!IMPORTANT]
> O comando erase não pode ser revertido e deve ser usado com cuidado.

O comando erase remove todos os dados, incluindo o sistema operacional, de um dispositivo. Também remove o dispositivo do gerenciamento do Intune. Nenhum aviso é emitido para o usuário, e a remoção ocorre imediatamente após a emissão do comando.

Você deve configurar um PIN de recuperação de seis dígitos. Este PIN pode ser usado para desbloquear o dispositivo apagado e, nesse momento, a reinstalação do sistema operacional começará. Após o início da remoção, o PIN aparecerá em uma barra de status na folha de visão geral do dispositivo no Intune. O PIN permanecerá enquanto a remoção estiver em andamento. Após a conclusão da remoção, o dispositivo desaparecerá totalmente do gerenciamento do Intune. Anote o PIN de recuperação para que a pessoa que estiver restaurando o dispositivo possa usá-lo.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Revogar licenças para um token de Programa de Compra por Volume do iOS<!-- 820870 -->
Você pode revogar a licença de todos os aplicativos do VPP (Apple Volume Purchase Program) do iOS para um determinado Token de VPP.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Revogação de aplicativos do Programa de Compra por Volume do iOS <!-- 820863 -->
Para um determinado dispositivo que tem um ou mais aplicativos do VPP (Apple Volume Purchase Program) do iOS, você pode revogar a licença do aplicativo com base no dispositivo associada ao dispositivo. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. Para saber mais, confira [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **Interno** facilita a criação e atribuição de aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos <!-- 1406920 -->

Durante a atribuição de aplicativo e após a seleção de um tipo de atribuição, você pode selecionar os grupos a serem incluídos e os grupos a serem excluídos.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Você pode atribuir uma política de configuração de aplicativo para grupos por meio da inclusão e exclusão de atribuições <!-- 1480316 -->

Você pode atribuir uma política de configuração de aplicativo a um grupo de usuários e dispositivos usando uma combinação de atribuições de inclusão e exclusão. As atribuições de podem ser escolhidas como uma seleção personalizada de grupos ou como um grupo virtual. Um grupo virtual pode incluir **Todos os usuários**, **Todos os dispositivos** ou **Todos os Usuários + Todos os Dispositivos**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10 <!-- 903672(archived), 1119689 -->  
Você pode criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>As Políticas de Acesso Condicional para o Intune só estão disponíveis no Portal do Azure <!-- 1737088 1634311 -->

Começando por esta versão, você deve configurar e gerenciar suas políticas de Acesso Condicional no [Portal do Azure](https://portal.azure.com), em **Azure Active Directory** > **Acesso Condicional** . Para sua conveniência, você também pode acessar essa folha do Intune no portal do Azure em **Intune** > **Acesso Condicional**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Atualizações nos emails de conformidade <!--1637547 -->

Quando um email é enviado para informar sobre um dispositivo não compatível, os detalhes sobre esse dispositivo são incluídos.


## <a name="week-of-january-22-2018"></a>Semana de 22 de janeiro de 2018

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nova funcionalidade para a ação "Resolver" para dispositivos Android <!--1583480-->

O aplicativo Portal da Empresa para Android está expandindo a ação "Resolver" para **Atualizar configurações do dispositivo** a fim de resolver [problemas de criptografia de dispositivo](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Bloqueio remoto disponível no aplicativo de Portal da Empresa para Windows 10 <!--676506-->
Agora, os usuários finais podem bloquear remotamente seus dispositivos do aplicativo do Portal da Empresa para Windows 10. Isso não será exibido para o dispositivo local que ele estiver usando ativamente.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Resolução facilitada de problemas de conformidade para o aplicativo do Portal da Empresa para Windows 10 <!--676546-->
Os usuários finais com dispositivos Windows poderão tocar no motivo da não conformidade no aplicativo Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema.

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

O Intune é compatível com gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

Por padrão, as configurações de dispositivos Android for Work são as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.

Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

Ao trabalhar com as novas configurações, considere os seguintes pontos:

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

O relatório **Status da instalação do aplicativo**, acessível para cada aplicativo por meio da lista **Aplicativo** na carga de trabalho **Aplicativos móveis**, agora contém uma contagem de **Instalação pendente** de Usuários e Dispositivos.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API do inventário de aplicativos iOS 11 para detecção de ameaças móveis <!-- 1391759 -->

O Intune coleta informações do inventário de aplicativos de dispositivos pessoais e corporativos e as disponibiliza para provedores de MTD (Detecção de Ameaça Móvel) para efetuar fetch, como Lookout for Work. É possível coletar um inventário de aplicativos dos usuários de dispositivos iOS 11+.

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
Novos processos e ferramentas já estão disponíveis para mover os usuários e seus dispositivos do MDM híbrido para o Intune no Portal do Azure, permitindo que você realize as seguintes tarefas:
- Copiar perfis e políticas do console do Configuration Manager para o Intune no portal do Azure
- Mover um subconjunto de usuários ao Intune no portal do Azure enquanto mantém o restante no MDM híbrido
- Migrar os dispositivos para o Intune no portal do Azure sem necessidade de registrá-los novamente

Consulte os detalhes em [Migrar usuários e dispositivos do MDM híbrido para o Intune autônomo](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->
Após o Exchange Connector criar uma conexão com o Exchange usando o CAS especificado, o conector terá a capacidade de descobrir outros CASs. Se o CAS primário ficar não disponível, o conector realizará o failover em outro CAS, se houver um disponível, até que o CAS primário fique disponível. Para obter detalhes, confira [Suporte de alta disponibilidade do Exchange Connector local](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

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

Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. Agora o Intune é compatível com os recursos do Google Play Protect, incluindo atestado remoto do SafetyNet. Os administradores podem definir requisitos de política de conformidade que exigem que o Google Play Protect esteja configurado e íntegro.
A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play. Se um dispositivo não for compatível com os requisitos do Google Play Protect, o acesso condicional poderá impedir que os usuários acessem recursos corporativos.

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
O pacote de gerenciamento do SCOM (System Center Operations Manager) para o conector do Exchange está disponível para ajudar você a analisar os logs do conector do Exchange. Com esse recurso, você terá diferentes maneiras de monitorar o serviço quando houver necessidade de solucionar problemas.

## <a name="week-of-november-6-2017"></a>Semana de 6 de novembro de 2017

### <a name="device-enrollment"></a>Registro de dispositivo
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogerenciamento para dispositivos Windows 10  <!-- 1243445 -->
O cogerenciamento é uma solução que fornece uma ponte do gerenciamento tradicional para o moderno e um caminho para fazer a transição usando uma abordagem em fases. Na sua base, o cogerenciamento é uma solução na qual os dispositivos Windows 10 são gerenciados simultaneamente pelo Configuration Manager e pelo Microsoft Intune, e também podem ser ingressados no AD (Active Directory) e no Azure AD (Azure Active Directory).  Essa configuração lhe fornece um caminho para modernizar ao longo do tempo, no ritmo que seja adequado para sua organização se você não puder mover tudo de uma só vez.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Restringir o registro do Windows por versão do sistema operacional <!-- 245498 -->
Como administrador do Intune, agora é possível especificar uma versão mínima e uma máxima do Windows 10 para registros de dispositivo. É possível definir essas restrições na folha **Configurações de Plataforma**.

Agora o Intune continuará dando suporte ao registro de computadores e telefones Windows 8.1. Contudo, apenas versões do Windows 10 podem ser definidas com limites mínimo e máximo. Para permitir o registro de dispositivos 8.1, deixe o limite mínimo vazio.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alertas para dispositivos não atribuídos do Windows AutoPilot <!-- 1631236 -->
Um novo alerta está disponível para dispositivos não atribuídos do Windows AutoPilot na página **Microsoft Intune** > **Registro de Dispositivo** > **Visão geral**. Este alerta mostra quantos dispositivos do programa AutoPilot não têm perfis de implantação do AutoPilot atribuídos. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows AutoPilot e informações detalhadas sobre eles. Para obter mais informações, consulte [Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Botão Atualizar para a Lista de dispositivos    <!-- 1333581 -->
Como a Lista de dispositivos não é atualizada automaticamente, é possível usar o novo botão Atualizar para atualizar os dispositivos exibidos na lista.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Suporte para AC (Autoridade de Certificação) da Nuvem Symantec  <!-- 1333638 -->    
O Intune agora é compatível com a AC da Nuvem Symantec, que permite que o Conector de Certificado do Intune emita certificados PKCS da AC da Nuvem Symantec para dispositivos gerenciados pelo Intune. Se você já está usando o Conector de Certificado do Intune com a AC (Autoridade de Certificação) da Microsoft, é possível usar a configuração do Conector de Certificado do Intune existente para adicionar a compatibilidade com a AC da Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Novos itens adicionados ao inventário de aplicativos   <!--1404455 -->
Os novos itens a seguir já estão disponíveis para o [inventário realizado por dispositivos registrados](device-inventory.md):

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
Os administradores podem definir sites como "confiáveis" ou "corporativos" usando um fluxo de trabalho da Proteção de Informações do Windows ou o novo perfil "Limite de rede" nas configurações do dispositivo. Caso sejam exibidos com o Microsoft Edge, os sites que não estão listados no limite de rede confiável de um dispositivo Windows 10 de 64 bits serão abertos em um navegador de um computador virtual do Hyper-V.

O Application Guard pode ser encontrado nos perfis de configuração do dispositivo, no perfil "Endpoint Protection". A partir daí, os administradores podem configurar a interação entre o navegador virtualizado e o computador host, sites não confiáveis e sites confiáveis e dados de armazenamento gerados no navegador virtualizado. Para usar o Application Guard em um dispositivo, um limite de rede deve estar configurado primeiro. É importante definir somente um limite de rede para um dispositivo.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>O Windows Defender Application Control no Windows 10 Enterprise fornece modo para confiar somente em aplicativos autorizados <!-- 1031096 -->    
Com milhares de novos arquivos mal-intencionados criados diariamente, usar a detecção baseada em assinatura de antivírus para combater o malware poderá deixar de fornecer uma defesa adequada contra novos ataques. Ao usar o Windows Defender Application Control no Windows 10 Enterprise, é possível alterar a configuração do dispositivo de um modo no qual os aplicativos sejam confiáveis, a menos que sejam bloqueados por um antivírus ou outra solução de segurança, para um modo no qual o sistema operacional confie somente em aplicativos autorizados por sua empresa. Atribua confiança a aplicativos no Windows Defender Application Control.

Com o Intune, é possível configurar políticas de controle de aplicativo no modo "somente auditoria" ou no modo de imposição. Os aplicativos não são bloqueados durante a execução no modo “somente auditoria”. O modo "somente auditoria" registra todos os eventos em logs do cliente local. Também é possível configurar se somente componentes do Windows e aplicativos da Microsoft Store podem ser executados ou se aplicativos adicionais com boa reputação, conforme definido pelo Intelligent Security Graph, podem ser executados.

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
Um novo perfil de configuração de dispositivo chamado **Limite de rede** pode ser encontrado com seus outros perfis de configuração de dispositivo. Use esse perfil para definir os recursos online que você deseja que sejam considerados corporativos e confiáveis. Você deve definir um limite de rede para um dispositivo *antes* que os recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows, possam ser usados no dispositivo. É importante definir somente um limite de rede para cada dispositivo.

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

**Extensão de tempo limite para verificação de arquivo pela nuvem**  

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

O fluxo de trabalho de configuração de dispositivo foi melhorado no aplicativo Portal da Empresa para iOS. A linguagem é mais fácil de usar e combinamos as telas sempre que possível. A linguagem é mais específica à sua empresa ao usar o nome da empresa em todo o texto de configuração. Veja esse fluxo de trabalho atualizado na  [página de novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entidade de usuário contém dados mais recentes do usuário no modelo de dados do Data Warehouse <!-- 1544273 -->
A primeira versão do modelo de dados do Intune Data Warehouse continha somente dados históricos recentes do Intune. Os criadores de relatório não podiam capturar o estado atual de um usuário. Nesta atualização, a **Entidade do usuário** é preenchida com os dados mais recentes do usuário.


## <a name="notices"></a>Avisos

### <a name="plan-for-change-new-windows-10-setting-for-kiosk-configuration-in-intune----1560072---"></a>Plano para mudança: nova configuração do Windows 10 para a configuração de Quiosque no Intune <!-- 1560072 -->
Estamos alterando como e em que local você pode configurar as áreas de trabalho do Windows 10 1709 e posteriores (RS3 e posteriores) no Portal do Azure do Intune.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta? 
Nossos registros indicam que você está usando o Windows 10 > Restrições de dispositivo > Configuração de quiosque (versão prévia). Isso será renomeado em maio como o Windows 10 > Restrições de Dispositivo > Quiosque (obsoleto) na interface do usuário para indicar que o uso não é mais recomendado. Porém, ele continuará a funcionar até a atualização de julho do Intune. Em seguida, ele se tornará obsoleto no back-end e deixará de funcionar. Como alternativa, estamos lançando um novo Perfil de configuração de dispositivo em maio: Windows 10 > Quiosque, que contém as definições para configurar Quiosques no Windows 10 RS4 e versões posteriores.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?  
Quando o Intune liberar a atualização de serviço no final de maio, compartilharemos instruções para testar e verificar se você é capaz de migrar sua configuração de Quiosque do Windows 10 RS3 para o Windows 10 RS4. Use estas instruções para configurar seus dispositivos como quiosques usando o novo perfil de configuração de dispositivo para quiosques.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Essa alteração afeta os clientes do Intune autônomo e os clientes do híbrido (Intune com o Configuration Manager). Essa integração ajudará a simplificar a administração do gerenciamento da nuvem. Agora, você terá apenas uma folha para acessar no Azure – a folha do Intune – a fim de gerenciar grupos, políticas, aplicativos e qualquer outro gerenciamento de dispositivo móvel.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Marque o Intune como um favorito em vez da folha de serviço da Proteção de Aplicativo do Intune e familiarize-se com o fluxo de trabalho da Política de proteção de aplicativo, na folha Aplicativo Móvel do Intune. Você será redirecionado por um breve período de tempo e, em seguida, a folha da Proteção de Aplicativo será removida. Lembre-se de que todas as políticas de Proteção do aplicativo já estão no Intune e você pode modificar qualquer uma das políticas de acesso condicional seguindo esta documentação: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Informações adicionais**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Plano para Alteração: alterações no suporte para o SDK de Aplicativo do Microsoft Intune para o plug-in do Cordova
O Intune terminará o suporte para o [Plug-in do Cordova do SDK de Aplicativo do Microsoft Intune](app-sdk-cordova.md) em 1 de maio de 2018. Em vez desse plug-in, é recomendável que você use a Ferramenta de Disposição do Aplicativo do Intune para preparar seus aplicativos com base em Cordova para gerenciamento e disponibilidade do Intune. Quando essa alteração entrar em vigor, o SDK de Aplicativo do Microsoft Intune para o plug-in do Cordova não será mais mantido nem receberá atualizações. Os desenvolvedores de aplicativos não poderão usar esse plug-in. O Intune planeja continuar a dar suporte a aplicativos criados com o Cordova. No entanto, todos os aplicativos criados com o SDK de Aplicativo do Microsoft Intune para o plug-in do Cordova terá funcionalidade reduzida no Intune. Depois de encapsular com a Ferramenta de Disposição do Aplicativo do Intune, os aplicativos poderão ser implantados para usuários finais conforme de costume. Para aplicativos Android baseados no Cordova que são lançados na Google Play Store:
- As credenciais dos usuários finais serão solicitadas a fim de receberem a política do Intune na primeira inicialização.
- Os aplicativos devem ser liberados na loja de aplicativos destinada a usuários do Intune, por exemplo "Aplicativo Contoso para Intune".

Para obter mais informações sobre a Ferramenta de Disposição do Aplicativo, consulte [Ferramenta de Disposição do Aplicativo para iOS](app-wrapper-prepare-ios.md) e [Ferramenta de Disposição do Aplicativo para Android](app-wrapper-prepare-android.md). Em caso de problemas ou de dúvidas, contate [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com).

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Planeje a mudança: use o Intune no Azure agora para o gerenciamento MDM<!-- 1227338 -->
Há mais de um ano, foi anunciada [a visualização pública do Intune no Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) e, após seis meses, a [Disponibilidade geral da nova experiência de administração](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) para o Intune. No dia 31 de agosto de 2018, o MDM (gerenciamento de dispositivo móvel) será desabilitado no console do Silverlight clássico para os clientes que usam o Intune autônomo. Nesse caso, você poderá usar o [Intune no Azure](https://aka.ms/Intune_on_Azure) para atender às suas necessidades de MDM. Se você ainda estiver usando o console clássico do MDM, deixe de usá-lo e familiarize-se com o Intune no Azure. Não esperamos que haja nenhum impacto para o usuário final com essa alteração. O gerenciamento de computador clássico permanecerá no Silverlight. Saiba mais sobre essa alteração e como ela o afetará clicando [aqui](https://aka.ms/Intune_on_Azure_mdm).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal Clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. Caso sua conta existente não possa acessar o Portal do Azure, é altamente recomendável criar uma conta de avaliação para testar a nova experiência.

## <a name="whats-coming"></a>O que está por vir

### <a name="local-device-security-option-settings----1251887---"></a>Configurações de opção de segurança do dispositivo local <!-- 1251887 -->
Você poderá habilitar configurações de segurança em dispositivos Windows 10 usando as novas configurações de Opção de segurança do dispositivo Local. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968-->

Estamos introduzindo uma nova experiência de site de Portal da Empresa em abril, com atualizações da interface do usuário, fluxos de trabalho simplificados e aprimoramentos de acessibilidade. Isso incluirá aprimoramentos voltados ao cliente como compartilhamento de aplicativos e melhor desempenho geral para levar a você uma experiência mais simples.
Adicionamos alguns recursos novos com base nos comentários de clientes como você, que aprimorarão significativamente a funcionalidade e a usabilidade existentes:

-   Aprimoramentos da interface do usuário em todo o site
-   Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos

Não é necessário tomar nenhuma medida para se preparar para essa mudança. Informaremos você quando o site atualizado do Portal da Empresa estiver disponível. No entanto, você pode eventualmente precisar atualizar os documentos do usuário final com capturas de tela atualizadas. Observe que talvez seja necessário, também, atualizar a documentação do aplicativo de Portal da Empresa no iOS, uma vez que o site habilita a seção **Aplicativos** do aplicativo iOS. É possível ver uma imagem de exemplo para isso na página [novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->
A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Vamos manter nosso [blog de suporte do Intune](https://aka.ms/compportalats) com detalhes.



## <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/cloud-platform/roadmap)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
