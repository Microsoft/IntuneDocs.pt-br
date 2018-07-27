---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/13/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: 1d56312fdf0e81406587caf352feafd745bd4353
ms.sourcegitcommit: 5251a630fb2c7a2e6f86abd84ab887f8eabc1481
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39212062"
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
## <a name="week-of-july-9-2018"></a>Semana de 9 de julho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquear acesso do aplicativo com base em modelos e fornecedores de dispositivos não aprovados <!-- 1425689 ! -->
O administrador de TI do Intune pode impor uma lista especificada de fabricantes Android e/ou modelos de iOS por meio das Políticas de Proteção de Aplicativo do Intune. O administrador de TI pode fornecer uma lista separada por ponto e vírgula de fabricantes para políticas do Android e de modelos de dispositivos para políticas do iOS. As Políticas de Proteção de Aplicativo do Intune servem apenas para Android e iOS. Há duas ações diferentes que podem ser executadas nessa lista especificada:
- Um bloqueio de acesso do aplicativo em dispositivos que não estão especificados.
- Ou uma limpeza seletiva de dados corporativos em dispositivos que não estão especificados. 

O usuário não conseguirá acessar o aplicativo direcionado se os requisitos por meio da política não forem atendidos. Com base nas configurações, o usuário pode ser bloqueado ou passar por uma limpeza seletiva dos dados corporativos no aplicativo. Em dispositivos iOS, esse recurso exige a participação de aplicativos (tais como WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune para que esse recurso seja imposto aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. No Android, esse recurso exige a versão mais recente do Portal da Empresa. 

Em dispositivos de usuário final, o cliente do Intune executará uma ação com base em uma correspondência simples das cadeias de caracteres especificadas na folha do Intune para Políticas de Proteção de Aplicativo. Isso depende totalmente do valor informado pelo dispositivo. Por isso, o administrador de TI é incentivado a garantir que o comportamento desejado seja preciso. Isso pode ser feito testando essa configuração com base em vários fabricantes e modelos de dispositivo direcionados a um grupo de usuários pequeno. No Microsoft Intune, selecione **Aplicativos Móveis** > **Políticas de proteção de aplicativo** para exibir e adicionar as políticas de proteção de aplicativo. Para obter mais informações sobre as políticas de proteção de aplicativo, consulte [Quais são as políticas de proteção de aplicativo](app-protection-policy.md) e [Apagar dados seletivamente usando ações de acesso da política de Proteção de Aplicativo no Intune](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Acesso ao build de pré-lançamento do Portal da Empresa do macOS <!-- 1734766 -->
Usando o Microsoft AutoUpdate, você pode inscrever-se para receber os builds antecipadamente ao ingressar no Programa Insider. A inscrição permite que você use o Portal da Empresa atualizado antes que ele esteja disponível para seus usuários finais. Para obter mais informações, veja o [Blog do Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## <a name="week-of-july-2-2018"></a>Semana de 2 de julho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Configurações de segurança adicionais para o Windows Installer <!-- 2282430 -->
Você pode permitir que os usuários controlem as instalações de aplicativos. Se habilitadas, as instalações que, de outra forma, poderiam ser interrompidas devido a uma violação de segurança teriam permissão para continuar. Você pode direcionar o Windows Installer para usar permissões elevadas quando ele instalar algum programa em um sistema. Além disso, você pode habilitar itens de WIP (Proteção de Informações do Windows) a serem indexados e os metadados sobre eles armazenados em um local não criptografado. Quando a política é desabilitada, os itens protegidos pela WIP não são indexados e não aparecem nos resultados na Cortana ou no Explorador de Arquivos. A funcionalidade para essas opções está desabilitada por padrão. 

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Monitorar o status de configuração de aplicativo do iOS por dispositivo <!-- 880037 -->
Como administrador do Microsoft Intune, você pode monitorar o status de configuração de aplicativo do iOS para cada dispositivo gerenciado. No **Microsoft Intune**, no portal do Azure, selecione **Dispositivos** > **Todos os dispositivos**. Na lista de dispositivos gerenciados, selecione um dispositivo específico para exibir uma folha para o dispositivo. Na folha do dispositivo, selecione **Configuração de aplicativo**.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Ações de acesso para políticas de proteção de aplicativo <!-- 1483510 -->
Você pode configurar políticas de proteção de aplicativo para apagar, bloquear ou avisar explicitamente os dispositivos não compatíveis. A ação *apagar* remove os dados corporativos de um dispositivo. Se ocorrer uma limpeza, o usuário do dispositivo receberá uma notificação sobre o motivo dela e as etapas de remediação. Para algumas configurações, como a versão mínima do sistema operacional, você poderá aplicar várias ações, como bloquear e apagar. Observe que essas ações são disparadas quando o aplicativo é iniciado.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Apagamento seletivo de dados de aplicativo da organização <!-- 1507030 -->
Agora os administradores podem configurar um apagamento seletivo de dados da organização como uma nova ação quando as condições de configurações de Acesso APP (Políticas de Proteção do Aplicativo) não forem atendidas.  Esse recurso ajuda os administradores a proteger e remover automaticamente dados confidenciais de empresa de aplicativos com base em critérios previamente configurados.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Revogar um aplicativo iOS adquirido por meio do VPP <!-- 1777384 -->
Como administrador do Microsoft Intune, você pode revogar as licenças para um aplicativo iOS selecionado adquirido por meio do VPP (programa de compra de volume). Você pode notificar os usuários quando um aplicativo licenciado pelo usuário não estiver mais atribuído a eles. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. A contagem de licenças recuperadas será refletida no nó **Aplicativos Licenciados** na carga de trabalho de **Aplicativo** do Intune. Para obter mais informações relacionadas a aplicativos VPP iOS, veja [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Atualizações nas mensagens que indicam a não conformidade no aplicativo do Portal da Empresa <!-- 1832222 -->
Revisamos as mensagens que são exibidas para os usuários de dispositivos quando um dispositivo está fora de conformidade. As mensagens mantêm seus significados originais, mas foram atualizadas com uma linguagem mais amigável e menos técnica. Também atualizamos os links para etapas de correção e documentação para mantê-los atualizados.
Os seguintes textos anterior e posterior são um exemplo das melhorias no sistema de mensagens que você verá:
- **Antes**: *Este dispositivo não contatou o serviço Intune no período especificado exigido pelo administrador de TI. Para resolver esse problema, abra o aplicativo do Portal da Empresa em seu dispositivo e clique no botão Verificar Conformidade.*
- **Depois**: *Seu dispositivo não faz check-in na organização há algum tempo. Para restabelecer a conexão, abra o aplicativo do Portal da Empresa no dispositivo e toque em Verificar Configurações no dispositivo.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>Revogar a licença de aplicativo VPP iOS <!-- 1863797 -->
Como administrador, você pode recuperar uma licença de aplicativo de VPP iOS atribuída a um usuário ou dispositivo. Desinstalar um aplicativo VPP iOS também permitirá que você recupere a licença do aplicativo. Antes de desinstalar o aplicativo, o usuário ou o dispositivo precisa ser removido do grupo ao qual o aplicativo é direcionado. A remoção do usuário ou dispositivo do grupo evita a reinstalação do aplicativo. Depois de concluir essas etapas, você pode optar por atribuir a licença do aplicativo a outro usuário ou dispositivo. Para obter mais informações sobre licenças de aplicativo VPP iOS, consulte [Gerenciar aplicativos adquiridos por volume do iOS no Microsoft Intune](vpp-apps-ios.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Selecione as categorias de dispositivo usando as configurações de Acesso Corporativo ou de Estudante <!-- 1058963 eenotready --> 
Se você tiver habilitado o [mapeamento do grupo de dispositivos](https://docs.microsoft.com/en-us/intune/device-group-mapping), os usuários no Windows 10 passarão a receber uma solicitação para selecionar uma categoria de dispositivo após o registro por meio do botão **Conectar** em **Configurações** > **Contas** > **Acesso corporativo ou de estudante**. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Usar sAMAccountName como o nome de usuário da conta para perfis de email <!-- 1500307 -->
Você pode usar o **sAMAccountName** local como o nome de usuário da conta para perfis de email para Windows 10, iOS e Android. Você também pode obter o domínio do atributo `domain` ou `ntdomain` no Azure AD (Azure Active Directory). Ou insira um domínio estático personalizado.

Para usar esse recurso, você deve sincronizar o atributo `sAMAccountName` do seu ambiente do Active Directory local com o Azure AD.

Aplica-se a [Andoid](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 e posteriores](email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Ver perfis de configuração do dispositivo em conflito <!-- 1556983 -->
Em **Configuração do Dispositivo**, é mostrada uma lista dos perfis existentes. Com essa atualização, uma nova coluna foi adicionada para fornecer detalhes sobre os perfis que apresentam conflito. Você pode selecionar uma linha em conflito para ver a configuração e o perfil que apresenta o conflito. 

Mais detalhes sobre como [gerenciar perfis de configuração](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Novo status para dispositivos em conformidade do dispositivo <!-- 2308882 -->
Em **Conformidade do dispositivo** > **Políticas** > selecione uma política > **Visão geral**, os seguintes novos estados foram adicionados:
- bem-sucedido
- erro
- conflito
- pendente
- não aplicável Uma imagem que mostra a contagem de dispositivos de uma plataforma diferente também é mostrada. Por exemplo, se você estiver procurando em um perfil do iOS, o novo bloco mostrará a contagem de dispositivos não iOS que também estão atribuídos a esse ele. Veja [Políticas de conformidade do dispositivo](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>A conformidade do dispositivo é compatível com soluções de antivírus de terceiros <!-- 2325484 -->
Quando você cria uma política de conformidade do dispositivo (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Plataforma: Windows 10 e posteriores** > **Configurações** > **Segurança do sistema**), há novas opções de **[Segurança do Dispositivo](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)**: 
- **Antivírus**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antivírus registradas com a Central de Segurança do Windows, como Symantec e Windows Defender. 
- **Software antispyware**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções de software antispyware registradas na Central de Segurança do Windows, como Symantec e Windows Defender. 

Aplica-se ao Windows 10 e posteriores 

### <a name="device-enrollment"></a>Registro de dispositivo

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Dispositivos sem a coluna de perfis na lista de tokens do programa de registro <!-- 1853904 -->
Na lista de tokens do programa de registro, há uma nova coluna que mostra o número de dispositivos sem um perfil atribuído. Isso ajuda os administradores a atribuir perfis a esses dispositivos antes de entregá-los aos usuários. Para ver a nova coluna, vá para **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Alterações de nome do Google para Android for Work e Play for Work <!--842873 -->
O Intune atualizou a terminologia "Android for Work" para refletir as alterações de identidade visual do Google. Os termos "Android for Work" e "Play for Work" não são mais usados. É usada uma terminologia diferente, dependendo do contexto:
- "Empresarial Android" refere-se à pilha de gerenciamento Android moderna geral.
- "Perfil de Trabalho" ou "Proprietário de Perfil" refere-se a dispositivos BYOD gerenciados com perfis de trabalho.
- "Google Play gerenciado" refere-se à loja de aplicativos do Google.

#### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de limpeza do dispositivo**.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Suporte para uso único de propriedade corporativa para dispositivos Android <!-- 1630973 -->

Agora o Intune é compatível com dispositivos com Android altamente gerenciados e bloqueados no estilo quiosque. Isso permite que os administradores bloqueiem ainda mais o uso de um dispositivo para um único aplicativo ou um conjunto pequeno de aplicativos, e impede que os usuários habilitem outros aplicativos ou executem outras ações no dispositivo. Para configurar o quiosque do Android, vá o Intune > **Registro de dispositivo** > **Registro do Android** > **Registros de dispositivo de quiosque e tarefa**. Para obter mais informações, veja [Configurar o registro de dispositivos corporativos de quiosque do Android](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Revisão por linha de identificadores de dispositivo corporativo duplicados carregados <!-- 2203794-->
Ao carregar IDs corporativas, agora o Intune fornece uma lista de todas as duplicatas e dá a opção de substituir ou manter as informações existentes. O relatório será exibido se houver duplicatas depois que você escolher **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar Identificadores**. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Adicione manualmente identificadores de dispositivo corporativo <!-- 2203803 -->
Agora você pode adicionar manualmente IDs de dispositivo corporativo. Escolha **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar**. 

## <a name="week-of-june-25-2018"></a>Semana de 25 de junho de 2018

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – novo parceiro de Defesa contra Ameaças Móveis <!-- 1169249 -->

É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Pradeo, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

## <a name="week-of-june-18-2018"></a>Semana de 18 de junho de 2018

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Suporte móvel do Edge para políticas de proteção de aplicativo do Intune <!-- 1817882 -->

O navegador Microsoft Edge para dispositivos móveis agora dá suporte a políticas de proteção de aplicativo definidas no Intune.

## <a name="week-of-june-11-2018"></a>Semana de 11 de junho de 2018

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Usar o modo FIPS com o conector do Certificado NDES <!-- 1333688 -->
Quando você instala o conector do Certificado NDES em um computador com o modo do padrão FIPS habilitado, a emissão e a revogação de certificados não funcionam conforme esperado. Com essa atualização, o suporte para o FIPS está incluído no conector do Certificado NDES. 

Essa atualização também inclui:

- O conector do Certificado NDES exige o .NET 4.5 Framework, que é automaticamente incluído no Windows Server 2016 e no Windows Server 2012 R2. Anteriormente, o .NET 3.5 Framework era a versão mínima necessária.
- O suporte ao TLS 1.2 é incluído no conector do Certificado NDES. Se o servidor com o conector do Certificado NDES instalado dá suporte ao TLS 1.2, o protocolo TLS 1.2 é usado. Se o servidor não dá suporte ao TLS 1.2, o TLS 1.1 é usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

Para obter mais informações, confira [Configurar e usar certificados SCEP](certificates-scep-configure.md) e [Configurar e usar certificados PKCS](certficates-pfx-configure.md).

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
O Intune agora é compatível com registro do Windows Autopilot sem autenticação de usuário. Essa é uma nova opção no perfil de implantação do Windows Autopilot, "Modo de Implantação do Autopilot" definido como "Autoimplantando".  O dispositivo precisa executar o Windows 10 Insider Preview Build 17672 ou posterior e ter um chip do TPM 2.0 para concluir com êxito esse tipo de registro. Como nenhuma autenticação de usuário é necessária, você só deve atribuir essa opção a dispositivos sobre os quais você tenha controle físico.

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
Para ver o UDID (Identificador Exclusivo de Dispositivo) para dispositivos iOS e macOS, acesse **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**. O UDID só está disponível para dispositivos corporativos (conforme definido em **Dispositivos** > **Todos os dispositivos** > escolher um dispositivo > **Propriedades** > **Propriedade do dispositivo**).

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

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Proteger dados do Exchange no Local usando a APP do Intune e o AC <!-- 1056954 -->
Agora você pode usar a APP (Proteção de Política do Aplicativo) do Intune e o AC (Acesso Condicional) para proteger o acesso a dados do Exchange no Local com o Outlook Mobile. Para adicionar ou modificar uma política de proteção do aplicativo no Portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Políticas de proteção do aplicativo**. Antes de usar esse recurso, verifique se você atende aos [requisitos do Outlook para iOS e Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

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
Agora há [duas novas configurações](device-restrictions-windows-10.md#edge-browser) disponíveis para dispositivos com o navegador Microsoft Edge: **Caminho para o arquivo de favoritos** e **Alterações aos Favoritos**.

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

Agora, os clientes que usam o conector NDES local para fornecer certificados para dispositivos podem configurar vários conectores em um único locatário.

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



## <a name="notices"></a>Avisos

### <a name="plan-for-change-intune-moving-to-support-ios-10-and-later-in-september----2454656---"></a>Plano para mudança: Intune passa dar suporte ao iOS 10 e posteriores em setembro <!-- 2454656 -->
Em setembro, espera-se que a Apple lance o iOS 12. Logo após o lançamento, mudaremos o registro do Intune, o Portal da Empresa e o navegador gerenciado para dar suporte ao iOS 10 e posteriores.  

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?  
Aplicativos móveis do Office 365 são compatíveis com o iOS 10 e posteriores, portanto, talvez você já tenha atualizado o sistema operacional ou os dispositivos. Nesse caso, essa mudança não afeta você.  

No entanto, se você tiver algum dos dispositivos listados abaixo, ou desejar inscrever algum deles, esteja ciente de que eles são compatíveis somente com o iOS 9 e versões anteriores.  Para continuar acessando o Portal da Empresa do Intune, atualize esses dispositivos, até setembro, para dispositivos que dão suporte ao iOS 10 ou posteriores:  

* iPhone 4S  
* iPod Touch  
* iPad 2  
* iPad (3ª geração)  
* iPad Mini (1ª geração)  

A partir de julho, dispositivos registrados no MDM com iOS 9 e o Portal da Empresa receberão uma solicitação para atualizar seu sistema operacional ou dispositivo. Se você usar as políticas de proteção de aplicativo, também poderá definir a configuração de acesso "Exigir o sistema de operacional iOS mínimo (somente aviso)".  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?   
Verifique se há dispositivos ou usuários que são afetados em sua organização. No Intune, no portal do Azure, acesse Dispositivos > Todos os dispositivos e filtre por sistema operacional.  Clique em Colunas para ver detalhes como versão do sistema operacional. Solicite que os usuários atualizem seus dispositivos para uma versão de sistema operacional com suporte antes de setembro.  

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Plano para alteração: migração do Intune para o TLS 1.2
A partir de 31 de outubro de 2018, o Intune dará suporte ao protocolo TLS versão 1.2 a fim de fornecer criptografia de ponta, para garantir que nosso serviço seja mais seguro por padrão e para se alinhar com outros serviços da Microsoft, como o Microsoft Office 365. O Office anunciou essa alteração no MC128929.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A partir de 31 de outubro de 2018, o Intune deixará de dar suporte ao protocolo TLS versões 1.0 ou 1.1. Todas as combinações de cliente-servidor e navegador-servidor devem usar o TLS versão 1.2 para garantir uma conexão sem problemas com o Intune. Observe que essa alteração afetará os dispositivos de usuários finais que não são mais compatíveis com o Intune, mas que ainda recebem a política por meio do Intune e que não podem usar o TLS versão 1.2. Isso inclui dispositivos como aqueles que executam o Android 4.3 e anterior. Para obter uma lista dos dispositivos e navegadores afetados, confira Informações adicionais abaixo.

Após 31 de outubro de 2018, caso você tenha um problema relacionado ao uso de uma versão antiga do TLS, precisará atualizar para o TLS 1.2 ou para um dispositivo que dê suporte ao TLS 1.2 como parte da resolução.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Recomendamos que você remova de forma proativa as dependências do TLS 1.0 e 1.1 dos ambientes e desabilite o TLS 1.0 e 1.1 no nível do sistema operacional sempre que possível. Comece a planejar hoje mesmo sua migração para o TLS 1.2. Confira a postagem no blog de suporte abaixo para obter a lista de dispositivos que não são compatíveis com o Intune hoje, mas que ainda podem receber a política e que não poderão se comunicar usando o TLS versão 1.2. Talvez você precise notificar os usuários finais de que eles perderão o acesso aos recursos corporativos.

**Informações adicionais**: [migração do Intune para o TLS 1.2 para criptografia](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)

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

Estamos introduzindo uma nova experiência de site de Portal da Empresa a partir de agosto, com atualizações da interface do usuário, fluxos de trabalho simplificados e aprimoramentos de acessibilidade. Isso incluirá aprimoramentos voltados ao cliente como compartilhamento de aplicativos e melhor desempenho geral para levar a você uma experiência mais simples.
Adicionamos alguns recursos novos com base nos comentários de clientes como você, que aprimorarão significativamente a funcionalidade e a usabilidade existentes:

* Aprimoramentos da interface do usuário em todo o site
* Capacidade de compartilhar links diretos para aplicativos
* Melhor desempenho para grandes catálogos de aplicativos

Não é necessário tomar nenhuma medida para se preparar para essa mudança. Informaremos você quando o site atualizado do Portal da Empresa estiver disponível. No entanto, você pode eventualmente precisar atualizar os documentos do usuário final com capturas de tela atualizadas. Observe que talvez seja necessário, também, atualizar a documentação do aplicativo de Portal da Empresa no iOS, uma vez que o site habilita a seção **Aplicativos** do aplicativo iOS. É possível ver uma imagem de exemplo para isso na página [novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->
A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Vamos manter nosso [blog de suporte do Intune](https://aka.ms/compportalats) com detalhes.



## <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/cloud-platform/roadmap)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
