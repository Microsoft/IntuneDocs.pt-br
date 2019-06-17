---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/31/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7c14568a0581220cf5941984645bd0b9044e00c1
ms.sourcegitcommit: cb76efd3db60a422a65478ebce83d3aea7b5eeed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66749950"
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

Conheça as novidades de cada semana do Microsoft Intune. Encontre também [próximas alterações](in-development.md), [notificações importantes](#notices) e informações sobre [versões anteriores](whats-new-archive.md). 

> [!Note]
> Alguns recursos podem ser implantados ao longo de várias semanas e podem não estar disponíveis para todos os clientes na primeira semana.

**Feed RSS**: Receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-may-27-2019"></a>Semana de 27 de maio de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Relatórios para aplicativos potencialmente prejudiciais em dispositivos Android <!-- 4223162 -->
Agora, o Intune fornece informações adicionais de relatórios sobre aplicativos potencialmente prejudiciais em dispositivos Android. 

## <a name="week-of-may-20-2019"></a>Semana de 20 de maio de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="windows-company-portal-app----3316993---"></a>Aplicativo do Portal da Empresa para Windows <!-- 3316993 -->
O aplicativo do Portal da Empresa do Windows agora terá uma nova página rotulada **Dispositivos**. A página **Dispositivos** mostrará aos usuários finais todos os seus dispositivos registrados. Os usuários verão essa alteração no Portal da Empresa quando usarem a versão 10.3.4291.0 e posterior. Para obter informações sobre como configurar o Portal da Empresa, confira [Como configurar o aplicativo Portal da Empresa do Microsoft Intune](company-portal-app.md).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Nome do atributo OrderID do dispositivo Autopilot alterado para Marcação de Grupo <!-- 4659453 -->

Para torná-lo mais intuitivo, o nome do atributo **OrderID** em dispositivos do Autopilot foi alterado para **Marcação de Grupo**. Ao usar CSVs para carregar informações do dispositivo do Autopilot, você precisa usar Marcação de Grupo como o cabeçalho de coluna, não OrderID.  

## <a name="week-of-may-13-2019"></a>Semana de 13 de maio de 2019 

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359-idready-wnready--"></a>Método de autenticação de atualização das políticas do Intune e instalação do aplicativo Portal da Empresa  <!-- 1927359 idready wnready-->
Em dispositivos já registrados por meio do Assistente de Instalação com um dos métodos de registro de dispositivo corporativo da Apple, o Intune não oferecerá mais o suporte do Portal da Empresa quando for instalado manualmente pelos usuários finais da loja de aplicativos. Essa alteração só é relevante quando você autentica com o Assistente de Configuração da Apple durante o registro. Além disso, essa alteração afeta apenas dispositivos iOS registrados via:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Programa de registro de dispositivos (DEP) da Apple

Se os usuários instalarem o aplicativo Portal da Empresa pela loja de aplicativos e tentarem registrar esses dispositivos por meio do aplicativo, receberão um erro. Esses dispositivos só devem usar o Portal da Empresa quando ele for enviado por push, automaticamente, pelo Intune durante o registro. Os perfis de registro no Intune, no portal do Azure, serão atualizados para que você possa especificar como os dispositivos são autenticados, e se o usuário recebe o aplicativo Portal da Empresa. Se você quiser que os usuários de dispositivos DEP tenham o Portal da Empresa, especifique suas preferências em um perfil de registro. 

Além disso, a tela **Identificar seu dispositivo** no Portal da Empresa do iOS está sendo removida. Portanto, os administradores que desejem habilitar o acesso condicional ou implantar aplicativos da empresa devem atualizar o perfil de registro de DEP. Esse requisito aplica-se somente se o registro de DEP for autenticado com o Assistente de Configuração. Nesse caso, você deve efetuar push do Portal da Empresa para o dispositivo. Para fazer isso, escolha **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Propriedades** > defina **Instalar o Portal da Empresa** para **Sim**.

Para instalar o Portal da Empresa em dispositivos DEP já registrados, acesse Intune > Aplicativos Cliente, e envie-o como um aplicativo gerenciado com políticas de configuração de aplicativo. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Configurar o modo como os usuários finais atualizam um aplicativo de linha de negócios (LOB) usando uma política de proteção de aplicativo <!-- 3568384 -->
Agora é possível configurar onde os usuários finais podem obter uma versão atualizada de um aplicativo de linha de negócios (LOB). Os usuários finais verão esse recurso na caixa de diálogo de inicialização condicional **Versão mínima do aplicativo**, que solicitará que os usuários finais atualizem para uma versão mínima do aplicativo de linha de negócios. Forneça esses detalhes de atualização como parte de sua política de proteção de aplicativo de linha de negócios (APP). Este recurso está disponível para iOS e Android. No iOS, esse recurso requer que o aplicativo seja integrado (ou encapsulado usando a ferramenta de encapsulamento) ao SDK do Intune para iOS v. 10.0.7 ou versão posterior. No Android, esse recurso exige a versão mais recente do Portal da Empresa. Para configurar o modo como um usuário final atualiza um aplicativo de linha de negócios, o aplicativo precisa que uma política de configuração de aplicativo gerenciado seja enviada a ele com a chave, `com.microsoft.intune.myappstore`. O valor enviado define de qual repositório o usuário final baixará o aplicativo. Se o aplicativo for implantado por meio do Portal da Empresa, o valor deverá ser `CompanyPortal`. Para qualquer outro repositório, você deverá inserir uma URL completa.

#### <a name="intune-management-extension-powershell-scripts-----3734186-idready---"></a>Scripts do PowerShell da extensão de gerenciamento do Intune  <!-- 3734186 idready -->
A execução de scripts do PowerShell pode ser configurada com privilégios de administrador do usuário no dispositivo. Saiba mais em [Usar scripts do PowerShell em dispositivos Windows 10 no Intune](intune-management-extension.md) e [Gerenciamento de Aplicativos Win32](apps-win32-app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Gerenciamento de aplicativos do Android Enterprise <!-- 4459905 -->
Para facilitar a configuração e o uso do gerenciamento de Android Enterprise pelos administradores de TI, o Intune adicionará automaticamente quatro aplicativos comuns relacionados ao Android Enterprise ao console do administrador do Intune. Os quatro aplicativos do Android Enterprise são os seguintes:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – usado para cenários totalmente gerenciados pelo Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – ajuda a entrar em suas contas se usar a verificação de dois fatores.
- **[Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – usado para cenários de perfil de trabalho das Políticas de Proteção do Aplicativo (APP) e do Android Enterprise.
- [Tela inicial gerenciada](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – usado para cenários dedicados/quiosques do Android Enterprise.

Antes, os administradores de TI precisavam encontrar e aprovar manualmente esses aplicativos na [Google Play Store gerenciada](https://play.google.com/store/apps) como parte da configuração. Essa alteração remove essas etapas que eram manuais para tornar mais fácil e rápido para os clientes usarem o gerenciamento do Android Enterprise.

Os administradores verão esses quatro aplicativos adicionados automaticamente à lista de aplicativos do Intune no momento em que conectarem pela primeira vez o locatário do Intune ao Google Play gerenciado. Confira mais informações em [Conectar sua conta do Intune à sua conta gerenciada do Google Play](connect-intune-android-enterprise.md). Para locatários que já conectaram o próprio locatário ou que já usam o Android Enterprise, não há nada que os administradores precisem fazer. Esses quatro aplicativos aparecerão automaticamente dentro de sete dias após a conclusão da implantação do serviço em maio de 2019.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Conector do Certificado PFX atualizado do Microsoft Intune  <!-- 1533038 -->
Lançamos uma atualização para o [Conector do Certificado PFX para o Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors) que resolve um problema em que os certificados PFX existentes continuam a ser reprocessados, o que faz com que o conector pare de processar novas solicitações.

####  <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Tarefas de segurança do Intune para Defender ATP (em versão prévia pública)     <!-- 3208597 -->
Na versão prévia pública, você pode usar o Intune para gerenciar [tarefas de segurança para a ATP (Proteção Avançada contra Ameaças) do Microsoft Defender](atp-manage-vulnerabilities.md). Essa integração com a ATP adiciona uma abordagem baseada em riscos para detectar, priorizar e corrigir vulnerabilidades e configurações incorretas do ponto de extremidade, enquanto reduz o tempo entre a descoberta e a mitigação.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671   idstaged-->
Muitos dispositivos Windows 10 e posteriores têm chipsets TPM (Trusted Platform Module). Esta atualização inclui uma nova configuração de conformidade que verifica a versão do chip TPM no dispositivo. 

O artigo [Configurações de política de conformidade do Windows 10 e posteriores](compliance-policy-create-windows.md#device-security) descreve esta configuração.

Aplica-se a: Windows 10 e posterior

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Impedir que usuários finais alterem o ponto de acesso pessoal e desabilitem o registro em log do servidor Siri em dispositivos iOS <!-- 4097904   -->  
Crie um perfil de restrições de dispositivo no dispositivo iOS (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações que você poderá configurar:

- **Aplicativos internos**: registro em log no lado do servidor para os comandos da Siri
- **Sem fio**: modificação do usuário do Ponto de acesso pessoal (somente supervisionado)

Para ver essas configurações, vá para [Configurações de aplicativo interno para iOS](device-restrictions-ios.md#built-in-apps) e [Configurações sem fio para iOS](device-restrictions-ios.md#wireless).

Aplica-se a: iOS 12.2 e posteriores

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Novas configurações de restrição de dispositivo do aplicativo Sala de aula para dispositivos macOS <!-- 4097905   --> 
Crie perfis de configuração de dispositivo para dispositivos macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Essa atualização inclui novas configurações do aplicativo Sala de aula, a opção de bloquear capturas de tela e a opção de desabilitar a Biblioteca de Fotos do iCloud.

Para ver as configurações atuais, vá para [Configurações do dispositivo macOS para permitir ou restringir recursos usando o Intune](device-restrictions-macos.md).

Aplica-se a: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>A senha do iOS para acessar a configuração da loja de aplicativos foi renomeada<!-- 4557891  -->
A configuração **Senha para acessar a loja de aplicativos** foi renomeada para **Exigir a senha do iTunes para todas as compras** (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma> **Restrições do Dispositivo** para o tipo de perfil > **Loja de Aplicativos, Exibição de Documentos, Jogos**).

Para ver as configurações disponíveis, acesse a configuração do iOS [Loja de Aplicativos, Exibição de Documentos, Jogos](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Aplica-se a: iOS

####  <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Linha de base da Proteção Avançada contra Ameaças do Microsoft Defender (versão prévia)  <!--  3754134 -->
Adicionamos uma versão prévia da linha de base de segurança para as configurações da [Proteção Avançada contra Ameaças do Microsoft Defender](security-baseline-settings-defender-atp.md). Esta linha de base está disponível quando seu ambiente atende aos pré-requisitos para usar a [Proteção Avançada contra Ameaças do Microsoft Defender](advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>A página Status do Registro do Windows (ESP) já está amplamente disponível <!-- 3605348 -->
A página Status do Registro saiu da versão prévia. Para saber mais, consulte [Configurar uma página de status de registro](windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Atualização da interface de usuário do Intune – Criação de perfil de registro do Autopilot  <!-- 4593669 -->
A interface do usuário para a criação de um perfil de registro do Autopilot foi atualizada para alinhar-se aos estilos de interface do usuário do Azure. Saiba mais em [Criar um perfil de registro do Autopilot](https://docs.microsoft.com/intune/enrollment-autopilot#create-an-autopilot-deployment-profile). A partir de agora cenários adicionais do Intune serão atualizados para esse novo estilo de interface do usuário.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Habilitar Autopilot Reset para todos os dispositivos do Windows <!-- 4225665 -->
Agora o Autopilot Reset funciona em todos os dispositivos Windows, mesmo aqueles não configurados para usar a página de Status de registro. Se uma página de Status de registro não tiver sido configurada para o dispositivo durante o registro inicial do dispositivo, o dispositivo será direcionado para a área de trabalho depois do login. Ele pode levar até oito horas para sincronizar e aparecer como em conformidade no Intune. Saiba mais em [Redefinir dispositivos com o Windows Autopilot Reset remoto](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>O formato exato do IMEI não é obrigatório ao pesquisar por Todos os dispositivos <!--30407680 -->
Você não precisa incluir espaços em números IMEI ao pesquisar **Todos os dispositivos**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Excluir um dispositivo no portal da Apple será refletido no portal do Intune <!--2489996 -->
Se um dispositivo for excluído do Programa de registro de dispositivos da Apple ou dos portais do Apple Business Manager, o dispositivo será excluído automaticamente do Intune durante a próxima sincronização.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>A Página de status de registro agora acompanha aplicativos Win32 <!-- 2714451 -->
Isso se aplica somente a dispositivos que executam o Windows 10 versão 1903 e superior. Para saber mais, consulte [Configurar uma página de status de registro](windows-enrollment-status.md).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Redefinir e apagar dispositivos em massa usando a API do Graph <!-- 3295288 -->
Você agora pode redefinir e apagar até 100 dispositivos em massa, usando a API do Graph.


### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>O relatório de criptografia saiu da versão prévia pública   <!-- 4587546      -->
O [relatório para BitLocker e criptografia de dispositivo](encryption-monitor.md) já está amplamente disponível e não faz mais parte da versão prévia pública. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Assinatura e configurações de biometria do Outlook para dispositivos iOS e Android <!-- 4050557 -->
Agora você pode especificar se a assinatura padrão está habilitada no Outlook em dispositivos iOS e Android. Além disso, pode permitir que os usuários alterem a configuração biométrica do Outlook no iOS.

## <a name="week-of-may-6-2019"></a>Semana de 6 de maio de 2019 

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Suporte do NAC (Controle de Acesso à Rede) do F5 Access para dispositivos iOS <!-- 4500808 -->

O F5 lançou uma atualização para BIG-IP 13 que permite funcionalidade NAC no F5 Access em iOS no Intune. Para usar esse recurso:

- Atualize o BIG-IP para a atualização 13.1.1.5. O BIG-IP 14 não é compatível.
- Integre o BIG-IP com o Intune para NAC. As etapas em [Visão geral: como configurar o APM para verificações de situação do dispositivo com sistemas de gerenciamento de ponto de extremidade](https://support.f5.com/kb/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
- Verifique a configuração **Habilitar NAC (controle de acesso de rede)** no perfil de VPN no Intune.

Para ver a configuração disponível, vá para [Definir configurações de VPN em dispositivos iOS](vpn-settings-ios.md).

Aplica-se a: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Conector do Certificado PFX atualizado do Microsoft Intune <!-- doc-vso 1521237  -->  
Lançamos uma atualização para o [conector de certificado PFX para o Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors) que reduz o intervalo de sondagem de 5 minutos para 30 segundos.

## <a name="week-of-april-22-2019"></a>Semana de 22 de abril de 2019

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Usar o Gerenciador de Conformidade para criar avaliações para o Microsoft Intune<!-- 4404750 -->

O [Gerenciador de Conformidade](https://servicetrust.microsoft.com/ComplianceManager) (o link abre outro site da Microsoft) é uma ferramenta de avaliação de risco baseada em fluxo de trabalho no Portal de Confiança do Serviço da Microsoft. Ele permite que você acompanhe, atribua e verifique as atividades de conformidade regulatória de sua organização relacionadas aos serviços da Microsoft. Crie sua própria avaliação de conformidade com o Office 365, o Azure, o Dynamics, os Serviços Profissionais e o Intune. O Intune tem duas avaliações disponíveis – FFIEC e RGPD.

O Gerenciador de Conformidade ajuda você a concentrar seus esforços com o detalhamento dos controles – controles gerenciados pela Microsoft e controles gerenciados por sua organização. Conclua as avaliações e, em seguida, exporte-as e imprima-as.

A conformidade com [FFIEC (Federal Financial Institutions Examination Council)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (o link abre outro site da Microsoft) é um conjunto de padrões de bancos online emitido pelo FFIEC. É a avaliação mais solicitada para instituições financeiras que usam o Intune. Ela interpreta como o Intune ajuda a atender às diretrizes de segurança cibernética do FFIEC relacionadas a cargas de trabalho de nuvem pública. A avaliação do FFIEC do Intune é a segunda avaliação do FFIEC no Gerenciador de Conformidade.

No exemplo a seguir, você poderá ver o detalhamento dos controles do FFIEC. A Microsoft aborda 64 controles. Você é responsável pelos 12 controles restantes.

![Confira uma avaliação de exemplo do Intune para o FFIEC, incluindo as ações do cliente e as ações da Microsoft](./media/intune-ffiec-assessment-status.png)

O [RGPD (Regulamento Geral sobre a Proteção de Dados)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (o link abre outro site da Microsoft) é uma lei da UE (União Europeia) que ajuda a proteger os direitos de indivíduos e seus dados. O RGPD é a avaliação mais solicitada para ajudar a cumprir as regulamentações referentes à privacidade. 

No exemplo a seguir, você verá o detalhamento dos controles do RGPD. A Microsoft aborda 49 controles. Você é responsável pelos 66 controles restantes.

![Confira uma avaliação de exemplo do Intune para o RGPD, incluindo as ações do cliente e as ações da Microsoft](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Semana de 15 de abril de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Criptografia OpenSSL para políticas de proteção de aplicativo do Android <!-- 3747362 -->
A APP (Política de Proteção de Aplicativo) do Intune em dispositivos Android agora usa uma biblioteca de criptografia OpenSSL em conformidade com o FIPS 140-2. Para obter mais informações, confira a seção [criptografia](app-protection-policy-settings-android.md#encryption) de [Configurações da política de proteção de aplicativo do Android no Microsoft Intune](app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Habilitar dependências de aplicativo Win32 <!-- 2617348  -->
Como administrador, você pode exigir que outros aplicativos sejam instalados como dependências antes da instalação do aplicativo Win32. Especificamente, o dispositivo precisa instalar os aplicativos dependentes antes de instalar o aplicativo Win32. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar** para exibir a folha **Adicionar aplicativo**. Selecione **Aplicativo do Windows (Win32)** como o **Tipo de aplicativo**. Depois de adicionar o aplicativo, selecione **Dependências** para adicionar os aplicativos dependentes que precisam ser instalados para que o aplicativo Win32 possa ser instalado. Para obter mais informações, confira [Intune autônomo – gerenciamento de aplicativos Win32](apps-win32-app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Informações de instalação de versão do aplicativo para aplicativos da Microsoft Store para Empresas <!-- 3537391   -->
Os relatórios de instalação de aplicativo incluem informações de versão do aplicativo para aplicativos da Microsoft Store para Empresas. No Intune, selecione **Aplicativos cliente** > **Aplicativos**. Selecione um **aplicativo da Microsoft Store para Empresas** e, em seguida, selecione **Status de instalação do dispositivo** na seção **Monitorar**.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Adições às regras de requisitos de aplicativos Win32 <!-- 3676883   -->
Você pode criar regras de requisitos baseadas em scripts do PowerShell, valores do Registro e informações do sistema de arquivos. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Em seguida, selecione **Aplicativo do Windows (Win32)** como o **Tipo de aplicativo** na folha **Adicionar aplicativo**.  Selecione **Requisitos** > **Adicionar** para configurar regras de requisitos adicionais. Em seguida, selecione **Tipo de arquivo**, **Registro** ou **Script** como o **Tipo de requisito**. Para obter mais informações, confira [Gerenciamento de aplicativos Win32](apps-win32-app-management.md).

 #### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Configurar os aplicativos Win32 para serem instalados em dispositivos ingressados no Azure AD registrados no Intune <!-- 3695227  -->
Você pode atribuir os aplicativos Win32 para serem instalados em dispositivos ingressados no Azure AD registrados no Intune. Para obter mais informações sobre aplicativos Win32 no Intune, confira [Gerenciamento de aplicativos Win32](apps-win32-app-management.md).

#### <a name="device-overview-shows-primary-user---794259----"></a>A página Visão geral do dispositivo mostra o usuário primário <!--794259  -->
A página Visão geral do dispositivo mostrará o usuário primário, também chamado de usuário UDA (afinidade de dispositivo de usuário). Para ver o usuário primário de um dispositivo, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo. O usuário primário será exibido próximo à parte superior da página **Visão Geral**.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Relatórios adicionais de aplicativos do Google Play Gerenciado para dispositivos de perfil de trabalho do Android Enterprise <!-- 4105925  -->
Para aplicativos do Google Play Gerenciado implantados em dispositivos de perfil de trabalho do Android Enterprise, você pode exibir o número de versão específico do aplicativo instalado em um dispositivo. Isso se aplica somente aos aplicativos obrigatórios.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>Teclados de terceiros para iOS <!-- 4111843   -->
O suporte da APP (política de proteção de aplicativo) do Intune à configuração **Teclados de Terceiros** do iOS será encerrado devido a uma alteração da plataforma iOS. Você não poderá definir essa configuração no Console de Administração do Intune e ela não será imposta no cliente no SDK do Aplicativo do Intune.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Definir as configurações de logon e controlar as opções de reinicialização em dispositivos macOS <!-- 1210083  -->
Em dispositivos macOS, você pode criar um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **macOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). Essa atualização inclui novas configurações de janela de logon, como exibição de uma faixa personalizada, escolher como os usuários se conectam, mostrar ou ocultar as configurações de energia, entre outros.

Para ver essas configurações, acesse [Configurações de recurso de dispositivo macOS](macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Configurar o Wi-Fi em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo em execução no modo de quiosque de vários aplicativos <!--3041940  -->
Habilite as configurações em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo durante a execução como um dispositivo dedicado no modo de quiosque de vários aplicativos. Nessa atualização, você pode permitir que os usuários configurem e se conectem a redes Wi-Fi (**Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo, Restrições de dispositivo** para o tipo de perfil > **Dispositivos dedicados** > **Modo de quiosque**: **Vários aplicativos** > **Configuração de Wi-Fi**). 

Para ver todas as configurações que você pode configurar, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md).

Aplica-se a: Dispositivos dedicados Android Enterprise em execução no modo de quiosque de vários aplicativos


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Configurar o Bluetooth e o emparelhamento em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo em execução no modo de quiosque de vários aplicativos <!-- 3041941  -->
Habilite as configurações em dispositivos dedicados Android Enterprise, Proprietário do Dispositivo durante a execução como um dispositivo dedicado no modo de quiosque de vários aplicativos. Nessa atualização, você pode permitir que os usuários finais habilitem o Bluetooth e emparelhem dispositivos via Bluetooth (**Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo, Restrições de dispositivo** para o tipo de perfil > **Dispositivos dedicados** > **Modo de quiosque**: **Vários aplicativos** > **Configuração do Bluetooth**). 

Para ver todas as configurações que você pode configurar, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md).

Aplica-se a: Dispositivos dedicados Android Enterprise em execução no modo de quiosque de vários aplicativos

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Criar e usar perfis de configuração de dispositivo do OEMConfig no Intune <!-- 3305883  -->
Nessa atualização, o Intune dá suporte à configuração de dispositivos Android Enterprise com o OEMConfig. Especificamente, você pode criar um perfil de configuração do dispositivo e aplicar as configurações a dispositivos Android Enterprise usando o OEMConfig (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma).

No momento, há suporte para OEMs conforme o OEM. Se um aplicativo OEMConfig desejado não estiver disponível na lista de aplicativos OEMConfig, contate `IntuneOEMConfig@microsoft.com`.

Para saber mais sobre esse recurso, acesse [Usar e gerenciar dispositivos Android Enterprise com o OEMConfig no Microsoft Intune](android-oem-configuration-overview.md).

Aplica-se a: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Notificações do Windows Update  <!-- 3316758, 3316782  -->
Adicionamos duas *Configurações da experiência do usuário* às configurações de grupo do Windows Update que você pode gerenciar no console do Intune. Agora você pode:
- Bloquear ou permitir que os usuários [verifiquem se há atualizações do Windows](windows-update-settings.md#block-user-from-scanning-for-windows-updates).
- Gerenciar o [nível de notificação do Windows Update](windows-update-settings.md#windows-update-notification-level) visto pelos usuários.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Novas configurações de restrição de dispositivo para dispositivos Android Enterprise, Proprietário do Dispositivo <!-- 3574254  -->
Em dispositivos Android Enterprise, você pode criar um perfil de restrição de dispositivo para permitir ou restringir recursos, definir regras de senha, entre outros (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **Android Enterprise** para a plataforma > **Somente proprietário do dispositivo > Restrições de dispositivo** para o tipo de perfil). 

Essa atualização inclui novas configurações de senha, permite o acesso completo aos aplicativos na Google Play Store para dispositivos totalmente gerenciados, entre outros. Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md). 

Aplica-se a: Dispositivos Android Enterprise totalmente gerenciados

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671 -->

Esse recurso está atrasado e deve ser lançado posteriormente.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Atualização das alterações de interface do usuário para o navegador Microsoft Edge em dispositivos Windows 10 e posterior <!-- 3775833   -->
Ao criar um perfil de configuração do dispositivo, você pode permitir ou restringir recursos do Microsoft Edge em dispositivos Windows 10 e posterior (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Restrições de dispositivo** para o tipo de perfil > **Navegador Microsoft Edge**). Nessa atualização, as configurações do Microsoft Edge são mais descritivas e mais fáceis de entender. 

Para ver esses recursos, acesse [Configurações de restrição de dispositivo do navegador Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

Aplica-se a: Windows 10 e posterior

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Suporte expandido para dispositivos Android Enterprise totalmente gerenciados (versão prévia)  <!--   3903241, 3903244, 3903246   -->
Ainda em uma versão prévia pública, expandimos nosso suporte de dispositivos Android Enterprise totalmente gerenciados ([anunciado pela primeira vez em janeiro de 2019](whats-new.md#week-of-january-14-2019)) para incluir o seguinte: 

- Em dispositivos totalmente gerenciados e dedicados, você pode criar [políticas de conformidade](compliance-policy-create-android-for-work.md) para incluir regras de senha e requisitos de sistema operacional (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android Enterprise** para a plataforma > **Proprietário do dispositivo** para o tipo de perfil). 

  Em dispositivos dedicados, o dispositivo pode ser mostrado como **Sem conformidade**. O acesso condicional não está disponível em dispositivos dedicados. Lembre-se de concluir todas as tarefas ou ações para colocar os dispositivos dedicados em conformidade com as políticas atribuídas.

- [Acesso condicional](conditional-access.md) – as políticas de acesso condicional que se aplicam ao Android também se aplicam aos dispositivos Android Enterprise totalmente gerenciados. Os usuários agora podem registrar seus dispositivos totalmente gerenciados no Azure Active Directory usando o **aplicativo do Microsoft Intune**. Em seguida, veja e resolva os problemas de conformidade para acessar recursos organizacionais.

- Novo aplicativo de usuário final (aplicativo do Microsoft Intune) – há um novo aplicativo de usuário final para dispositivos Android totalmente gerenciados chamado **Microsoft Intune**. Esse novo aplicativo é leve e moderno e fornece uma funcionalmente semelhante à do aplicativo do Portal da Empresa, mas para dispositivos totalmente gerenciados. Para saber mais, confira [Aplicativo do Microsoft Intune no Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Para configurar dispositivos totalmente gerenciados do Android, acesse **Registro de dispositivo** > **Registro do Android** > **Dispositivos corporativos totalmente gerenciados**. O suporte para dispositivos Android totalmente gerenciados permanece em versão prévia e alguns recursos do Intune podem não estar totalmente funcionais.  

Para saber mais sobre essa versão prévia, confira nosso blog [Microsoft Intune – Versão Prévia 2 para dispositivos Android Enterprise totalmente gerenciados](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470--wnstaged--"></a>Configurar o perfil para ignorar algumas telas durante a execução do Assistente de Configuração <!-- 2276470  wnstaged-->
Ao criar um perfil de registro do macOS, você poderá configurá-lo para ignorar uma das seguintes telas quando um usuário percorrer o Assistente de Configuração:
- Aparência
- Tom de Exibição
- iCloudStorage Se você editar um perfil ou criar um novo, as telas ignoradas selecionadas precisarão ser sincronizadas com o servidor MDM da Apple.  Os usuários podem emitir uma sincronização manual dos dispositivos, para que não haja atraso na aplicação das alterações de perfil.
Saiba mais em [Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos ou o Apple School Manager](device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Nomeação de dispositivo em massa ao registrar dispositivos iOS corporativos<!--3566569  -->
Ao usar um dos métodos de registro corporativo da Apple (DEP/ABM/ASM), você pode definir um formato de nome de dispositivo para nomear automaticamente os dispositivos iOS de entrada. Especifique um formato que inclua o tipo de dispositivo e o número de série no modelo. Para fazer isso, escolha **Intune** > **Registro de dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > **Selecionar um token** >**Criar perfil** > **Formato de nomeação de dispositivo**. Você pode editar os perfis existentes, mas somente os dispositivos recém-sincronizados terão o nome aplicado.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Atualização da mensagem de tempo limite padrão na Página de Status de Registro <!-- 3959331 -->
Atualizamos a mensagem de tempo limite padrão que os usuários veem quando o ESP (Página de Status de Registro) excede o valor de tempo limite especificado no perfil do ESP. A nova mensagem padrão é o que os usuários veem e ajuda-os a entender as próximas ações a serem executadas com sua implantação do ESP.  

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Desativar dispositivos sem conformidade  <!-- 1827291   -->
Esse recurso foi adiado e está planejado para uma versão futura.


### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Alterações do Intune Data Warehouse V1.0 que refletem novamente a versão beta <!-- 4403765 -->
Quando a V1.0 foi introduzida pela primeira vez em 1808, ela tinha algumas diferenças da API beta. Em 1903, essas alterações serão refletidas novamente para a versão beta da API. Se você tem relatórios importantes que usam a versão beta da API, recomendamos expressamente alternar esses relatórios para a V1.0 a fim de evitar alterações da falha. Para obter mais informações, confira [Log de alterações da API do Intune Data Warehouse](reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorar o status da linha de base de segurança (versão prévia pública) <!-- 3082047 --> 
Adicionamos uma [exibição por categoria](security-baselines-monitor.md#per-category-view) ao monitoramento das linhas de base de segurança. (As linhas de base de segurança permanecem em versão prévia). A exibição por categoria exibe cada categoria da linha de base juntamente com o percentual de dispositivos que se enquadram em cada grupo de status dessa categoria. Agora você pode ver quantos dispositivos não correspondem às categorias individuais, estão configurados incorretamente ou não são aplicáveis.

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Marcas de escopo para tokens VPP da Apple <!--2371886  -->
Agora você pode adicionar marcas de escopo a tokens VPP da Apple. Somente os usuários atribuídos com a mesma marca de escopo terão acesso ao token VPP da Apple com essa marca. Os aplicativos e os livros eletrônicos VPP adquiridos com esse token herdam as marcas de escopo. Para obter mais informações sobre marcas de escopo, confira [Usar o RBAC e marcas de escopo](scope-tags.md).







## <a name="week-of-april-1-2019"></a>Semana de 1º de abril de 2019

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Atualização dos conectores de certificado  <!-- ICM 113304612 -->
Lançamos atualizações para o [Intune Certificate Connector e o Conector de Certificado PFX para o Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors). As novas versões corrigem vários problemas conhecidos.  

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!-- 2536024 -->
A página inicial do aplicativo do Portal da Empresa para dispositivos iOS foi reformulada. Com essa alteração, a página inicial seguirá melhor os padrões de interface do usuário do iOS e também fornecerá detectabilidade aprimorada para aplicativos e livros eletrônicos.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Alterações no registro do Portal da Empresa para usuários de dispositivos iOS 12 <!--3448635 -->  
As telas e as etapas de registro do Portal da Empresa para iOS foram atualizadas para se alinharem com as alterações de registro do MDM lançadas no Apple iOS 12.2. O fluxo de trabalho atualizado solicita o seguinte aos usuários:  

* permitir que o Safari abra o site do Portal da Empresa e baixe o perfil de gerenciamento antes de retornar ao aplicativo do Portal da Empresa.  
* abrir o aplicativo de Configurações para instalar o perfil de gerenciamento em seus dispositivos.
* retornar ao aplicativo do Portal da Empresa para concluir o registro.  

Para ver as etapas e as telas de registro atualizadas, confira [Registrar dispositivo iOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>Semana de 25 de março de 2019

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Suporte para o aplicativo de Conformidade do Power BI na folha do Data Warehouse no Microsoft Intune <!-- 4260871 -->
Anteriormente, o link **Baixar arquivo do Power BI** na folha **Intune Data Warehouse** baixava um relatório do Intune Data Warehouse (arquivo .pbix). Esse relatório foi substituído pelo aplicativo de Conformidade do Power BI. O aplicativo de Conformidade do Power BI não exigirá carregamento nem instalação especiais. Ele será aberto diretamente no portal online do Power BI e exibirá dados especificamente para seu locatário do Intune com base em suas credenciais. No Intune, selecione o link **Configurar o Intune Data Warehouse** no lado direito da folha do Intune. Em seguida, clique em **Obter o Aplicativo do Power BI**. Para obter mais informações, confira [Conectar-se ao Data Warehouse com o Power BI](reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>Semana de 18 de março de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Implantar o Microsoft Visio e o Microsoft Project <!-- 3725386  -->
Agora você pode implantar o Microsoft Visio Pro para Office 365 e o Microsoft Project Online Desktop Client como aplicativos independentes em dispositivos Windows 10 usando o Microsoft Intune, caso você tenha licenças para esses aplicativos. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar** para exibir a folha **Adicionar aplicativo**. Na folha **Adicionar aplicativo**, selecione **Windows 10** como o **Tipo de aplicativo**. Em seguida, selecione **Configurar Pacote de Aplicativos** para selecionar os aplicativos a serem instalados. Para obter mais informações sobre os aplicativos do Office 365 para dispositivos Windows 10, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Alteração no nome de produto do Microsoft Visio Pro para Office 365 <!-- 3593653  -->
O **Microsoft Visio Pro para Office 365** agora será conhecido como **Microsoft Visio Online Plano 2**.  Para obter mais informações sobre o Microsoft Visio, confira [Visio Online Plano 2](https://products.office.com/visio/visio-online-plan-2). Para obter mais informações sobre os aplicativos do Office 365 para dispositivos Windows 10, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Configuração do limite de caracteres da APP (Política de Proteção de Aplicativo) do Intune <!-- 3291302  -->
Os administradores do Intune podem especificar uma exceção para a configuração de política **Restringir recortar, copiar e colar com outros aplicativos** da APP do Intune.  Como administrador, você pode especificar o número de caracteres que podem ser recortados ou copiados de um aplicativo gerenciado. Essa configuração permitirá o compartilhamento do número especificado de caracteres com qualquer aplicativo, independentemente da configuração "Restringir recortar, copiar e colar com outros aplicativos". Observe que a versão do aplicativo do Portal da Empresa do Intune para Android exige a versão 5.0.4364.0 ou posterior. Para obter mais informações, confira [Proteção de dados do iOS](app-protection-policy-settings-ios.md#data-protection), [Proteção de dados do Android](app-protection-policy-settings-android.md#data-protection) e [Examinar os logs de proteção de aplicativo cliente](app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>XML do ODT (Ferramenta de Implantação do Office) para implantação do Office ProPlus <!-- 3192477   -->
Você poderá fornecer o XML do ODT (Ferramenta de Implantação do Office) ao criar uma instância do Office Pro Plus no console de administração do Intune. Isso permitirá uma maior capacidade de personalização, caso as opções existentes de interface do usuário do Intune não atendam às suas necessidades. Para obter mais informações, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365) e [Opções de configuração para a Ferramenta de Implantação do Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente <!-- 1429026  -->
No aplicativo do Portal da Empresa do Windows, os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente com base na cor dominante do ícone (caso seja possível detectá-la). Quando aplicável, essa tela de fundo substituirá a borda cinza que era visível anteriormente em blocos de aplicativo. Os usuários verão essa alteração em versões do Portal da Empresa mais recentes que 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Instalar os aplicativos disponíveis usando o aplicativo do Portal da Empresa após o registro em massa do Windows <!-- 2751523   -->
Os dispositivos Windows registrados no Intune com o [registro em massa do Windows](windows-bulk-enroll.md) (pacotes de provisionamento) poderão usar o aplicativo do Portal da Empresa para instalar os aplicativos disponíveis. Para obter mais informações sobre o aplicativo do Portal da Empresa, confira [Adicionar manualmente o Portal da Empresa do Windows 10](store-apps-company-portal-app.md) e [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](company-portal-app.md).

> [!Note]
> Esse recurso ainda não foi totalmente implantado para todos os clientes. Se você não consegue usar o Portal da Empresa em dispositivos registrados em massa, talvez precise aguardar a distribuição dessa alteração para sua conta.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>O aplicativo Microsoft Teams pode ser selecionado como parte do pacote de aplicativos do Office <!-- 3828932  -->
O aplicativo Microsoft Teams pode ser incluído ou excluído como parte da instalação do pacote de aplicativos do Office Pro Plus. Esse recurso funciona no Office Pro Plus número de build 16.0.11328.20116 e posterior. O usuário precisa sair do dispositivo e, em seguida, entrar nele para concluir a instalação. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Selecione um dos tipos de aplicativo **Pacote do Office 365** e, em seguida, selecione **Configurar Pacote de Aplicativos**.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Iniciar automaticamente um aplicativo quando vários aplicativos estão em execução no modo de quiosque em dispositivos Windows 10 e posterior <!-- 2351390 -->

Em dispositivos Windows 10 e posterior, você pode executar um dispositivo no modo de quiosque e executar muitos aplicativos. Nessa atualização, há uma configuração de **Inicialização Automática** (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Quiosque** para o tipo de perfil > **Quiosque de vários aplicativos**). Use essa configuração para iniciar automaticamente um aplicativo quando o usuário entrar no dispositivo.

Para ver uma lista e uma descrição de todas as configurações de quiosque, confira [Configurações de dispositivos Windows 10 e posterior para execução como um quiosque no Intune](kiosk-settings-windows.md).

Aplica-se a: Windows 10 e posterior

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Os logs operacionais também mostram detalhes sobre os dispositivos sem conformidade <!-- 4063755  -->
Durante o roteamento de logs do Intune para recursos do Azure Monitor, você também pode rotear os logs operacionais. Nessa atualização, os logs operacionais também fornecem informações sobre os dispositivos sem conformidade. 

Para obter mais informações sobre esse recurso, confira [Enviar dados de log para o armazenamento, os hubs de eventos ou a análise de logs no Intune](review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Rotear logs para o Azure Monitor em mais cargas de trabalho do Intune <!-- 3804627 -->
No Intune, você pode rotear logs de auditoria e operacionais para os hubs de eventos, o armazenamento e a análise de logs no Azure Monitor (**Intune** > **Monitoramento** > **Configurações de diagnóstico**). Nessa atualização, você pode rotear esses logs em mais cargas de trabalho do Intune, incluindo conformidade, configurações, aplicativos cliente, entre outros. 

Para saber mais sobre os logs de roteamento para o Azure Monitor, confira [Enviar dados de log para o armazenamento, os hubs de eventos ou a análise de logs](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Criar e usar extensões de mobilidade em dispositivos Android Zebra no Intune <!-- 3305880   -->
Nessa atualização, o Intune dá suporte à configuração de dispositivos Android Zebra. Especificamente, você pode criar um perfil de configuração do dispositivo e aplicar as configurações a dispositivos Android Zebra usando perfis MX (extensões de mobilidade) gerados pelo StageNow (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android** para a plataforma > **Perfil MX (somente Zebra)** para o tipo de perfil).

Para obter mais informações sobre esse recurso, confira [Usar e gerenciar dispositivos Zebra com extensões de mobilidade no Intune](android-zebra-mx-overview.md).

Aplica-se a: Android

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Relatório de criptografia para dispositivos Windows 10 (em versão prévia pública)<!-- 2351538 -->  
Use o novo [Relatório de criptografia (versão prévia)](encryption-monitor.md) para exibir detalhes sobre o status da criptografia de seus dispositivos Windows 10. Os detalhes disponíveis incluem uma versão TPM de dispositivos, preparação e status de criptografia, relatório de erros, entre outros.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Acessar as chaves de recuperação do BitLocker no portal do Intune (em versão prévia pública) <!-- 2351547   -->  
Agora você pode usar o Intune para [exibir detalhes](encryption-monitor.md) sobre a ID de Chave e as chaves de recuperação do BitLocker no Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Suporte do Microsoft Edge para cenários do Intune em dispositivos iOS e Android <!-- 3411007 -->
O Microsoft Edge dará suporte a todos os mesmos cenários de gerenciamento do Intune Managed Browser com a adição de melhorias na experiência do usuário final. Os recursos empresariais do Microsoft Edge que são habilitados por políticas do Intune incluem identidade dupla, integração de política de proteção de aplicativo, integração de proxy de aplicativo do Azure e Favoritos e atalhos de página inicial gerenciados. Para obter mais informações, confira o [suporte do Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>O Exchange Online e o Intune Connector preterem o suporte para dispositivos somente do EAS <!--3105122  -->
O console do Intune não dá mais suporte à exibição e ao gerenciamento de dispositivos somente do EAS conectados ao Exchange Online com o Intune Connector. Em vez disso, você tem as seguintes opções:
- Registrar dispositivos no Gerenciamento de Dispositivo Móvel (MDM)
- Usar políticas de Proteção de Aplicativo do Intune para gerenciar seus dispositivos
- Usar controles do Exchange, conforme descrito em [Clientes e celulares no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Pesquisar a página Todos os dispositivos em busca de um dispositivo exato usando o [nome] <!--4254930 -->
Agora você pode pesquisar um nome de dispositivo exato. Acesse **Intune** > **Dispositivos** > **Todos os dispositivos** > na caixa de pesquisa e coloque o nome do dispositivo entre {} para pesquisar uma correspondência exata. Por exemplo, **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Suporte para conectores adicionais na página Status do Locatário <!-- 3617202  -->
A [página Status do Locatário](tenant-status.md) agora exibe informações de status para conectores adicionais, incluindo *Windows Defender ATP* (Proteção Avançada contra Ameaças) e outros conectores de Defesa contra Ameaças Móveis.

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Como permitir acesso somente leitura do Intune a apenas algumas funções do Azure Active Directory <!-- 3637917  -->
O acesso somente leitura do Intune foi permitido às funções do Azure AD a seguir. As permissões concedidas com funções do Azure AD substituem as permissões concedidas com o RBAC (controle de acesso baseado em função) do Intune.

Acesso somente leitura aos dados de auditoria do Intune:

- Administrador de conformidade
- Administrador de dados de conformidade

Acesso somente leitura a todos os dados do Intune:

- Administrador de Segurança
- Operador de segurança
- Leitor de segurança

Para obter mais informações, confira [Controle de acesso baseado em função](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Marcas de escopo para perfis de provisionamento de aplicativo do iOS <!--2934430   -->
Você pode adicionar uma marca de escopo a um perfil de provisionamento de aplicativo do iOS, de modo que somente as pessoas com funções que também receberam essa marca de escopo tenham acesso ao perfil de provisionamento de aplicativo do iOS. Para obter mais informações, confira [Usar o RBAC e marcas de escopo](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Marcas de escopo para políticas de configuração de aplicativos <!--2371891   -->
Você pode adicionar uma marca de escopo a uma política de configuração de aplicativos, de modo que somente as pessoas com funções que também receberam essa marca de escopo tenham acesso à política de configuração de aplicativos. A política de configuração de aplicativos só pode ser direcionada ou associada a aplicativos que receberam a mesma marca de escopo. Para obter mais informações, confira [Usar o RBAC e marcas de escopo](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Suporte do Microsoft Edge para cenários do Intune em dispositivos iOS e Android <!-- 3411007 -->
O Microsoft Edge dará suporte a todos os mesmos cenários de gerenciamento do Intune Managed Browser com a adição de melhorias na experiência do usuário final. Os recursos empresariais do Microsoft Edge que são habilitados por políticas do Intune incluem identidade dupla, integração de política de proteção de aplicativo, integração de proxy de aplicativo do Azure e Favoritos e atalhos de página inicial gerenciados. Para obter mais informações, confira o [suporte do Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>Semana de 25 de fevereiro de 2019

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="intune-powershell-module----951068----"></a>Módulo do PowerShell do Intune <!-- 951068  -->
O módulo do PowerShell do Intune, que fornece suporte para a API do Intune por meio do Microsoft Graph, agora está disponível na [Galeria do Microsoft PowerShell](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Detalhes sobre como usar este módulo](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Exemplos de cenários de uso deste módulo](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Suporte aprimorado para a Otimização de Entrega  <!--3183757  -->
Expandimos o suporte no Intune para configurar a Otimização de Entrega. Agora você pode configurar uma lista expandida de [configurações de Otimização de Entrega](delivery-optimization-settings.md) e direcioná-la a seus dispositivos diretamente no console do Intune.


## <a name="week-of-february-18-2019"></a>Semana de 18 de fevereiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>O Intune aproveitará as APIs do Google Play Protect em dispositivos Android <!-- 2577355   -->
Alguns administradores de TI se deparam com um cenário de BYOD, em que os usuários finais podem acabar efetuando rooting ou desbloqueio por jailbreak dos respectivos dispositivos móveis. Esse comportamento, embora às vezes não mal-intencionado, resulta em um desvio de muitas políticas do Intune que são definidas para proteger os dados da organização em dispositivos de usuário final. Assim, o Intune fornece detecção de root e jailbreak para dispositivos registrados e não registrados. Com esta versão, o Intune agora aproveitará as APIs do Google Play Protect para adicionar a nossas verificações de detecção de root existentes para dispositivos não registrados. Embora o Google não compartilhe as verificações de detecção de root que ocorrem na íntegra, esperamos que essas APIs detectem os usuários que realizaram rooting de seus dispositivos por qualquer motivo, desde personalização de dispositivo até possibilidade de obtenção das atualizações mais recentes do sistema operacional em dispositivos mais antigos. Esses usuários podem então ser impedidos de acessar dados corporativos e suas contas corporativas podem ser apagadas de seus aplicativos habilitados para política. Para o valor adicional, o administrador de TI agora tem várias atualizações de geração de relatórios na folha da Proteção de Aplicativo do Intune – o relatório "Usuários sinalizados" mostrará quais usuários são detectados por meio do verificação de API do SafetyNet da Google Play Protect, o relatório "Aplicativos potencialmente prejudiciais" mostrará quais aplicativos são detectados por meio da verificação de API da Verificação de Aplicativos do Google. Este recurso está disponível no Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informações do aplicativo Win32 disponíveis na folha Solução de Problemas <!-- 2617342   -->
Agora você pode coletar arquivos de log de falha para uma instalação de aplicativo Win32 na folha **Solução de Problemas** do aplicativo do Intune. Para obter mais informações sobre solução de problemas de instalação do aplicativo, confira [Solução de problemas de instalação do aplicativo](troubleshoot-app-install.md) e [Solução de problemas de aplicativos Win32](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Detalhes do status do aplicativo para aplicativos iOS <!-- 3761235   -->
Há novas mensagens de erro de instalação de aplicativo relacionadas ao seguinte:
- Falha em aplicativos VPP durante a instalação no iPad compartilhado
- Falha quando o repositório do aplicativo é desabilitado
- Falha ao localizar a licença do VPP para o aplicativo
- Falha ao instalar aplicativos do sistema com o provedor de MDM
- Falha ao instalar aplicativos quando o dispositivo está no modo perdido ou modo de quiosque
- Falha ao instalar o aplicativo quando o usuário não está conectado à App Store

No Intune, selecione **Aplicativos cliente** > **Aplicativos** > "Nome do aplicativo" > **Status de instalação do dispositivo**. Novas mensagens de erro estarão disponíveis na coluna **Detalhes do status**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Nova tela Categorias de aplicativo no aplicativo do Portal da Empresa para Windows 10<!-- 3834780  -->
Uma nova tela chamada **Categorias de aplicativo** foi adicionada para melhorar a experiência de navegação e de seleção do aplicativo no Portal da Empresa para Windows 10. Agora os usuários verão os aplicativos classificados em categorias como **Em destaque**, **Educação** e **Produtividade**. Essa alteração é exibida nas versões do Portal da Empresa 10.3.3451.0 e posteriores. Para exibir a nova tela, confira [Novidades da interface do usuário do aplicativo](https://docs.microsoft.com/intune/whats-new-app-ui). Para obter mais informações sobre os aplicativos no Portal da Empresa, confira [Instalar e compartilhar aplicativos em seu dispositivo](/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Aplicativo de Conformidade do Power BI <!-- 1455231 doc-work-item -->
Acesse o Intune Data Warehouse no Power BI Online usando o aplicativo [Conformidade do Intune (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Com esse aplicativo do Power BI, agora você pode acessar e compartilhar relatórios pré-criados sem nenhuma configuração e sem sair do navegador da Web. Para obter mais informações, confira [Log de alterações – aplicativo de Conformidade do Power BI](reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>Os scripts do PowerShell podem ser executados em um host de 64 bits em dispositivos de 64 bits <!-- 1862675   -->
Quando você adiciona um script do PowerShell a um perfil de configuração do dispositivo, o script é executado sempre em 32 bits, mesmo em sistemas operacionais de 64 bits. Com essa atualização, um administrador pode executar o script em um host do PowerShell de 64 bits em dispositivos de 64 bits (**Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar** > **Configurar** > **Executar o script no host do PowerShell de 64 bits**).

Para obter mais detalhes sobre como usar o PowerShell, veja [scripts do PowerShell no Intune](intune-management-extension.md).

Aplica-se a: Windows 10 e posterior

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>Os usuários do macOS deverão atualizar suas senhas <!-- 1873216 -->
O Intune impõe a configuração **ChangeAtNextAuth** em dispositivos macOS. Essa configuração afeta os usuários finais e os dispositivos que têm políticas de senha de conformidade ou perfis de senha de restrição de dispositivo. Os usuários finais deverão atualizar suas senhas uma vez. Esse prompt ocorre sempre que um usuário executa pela primeira vez uma tarefa que exige autenticação, como a entrada no dispositivo. Os usuários também podem precisar atualizar suas senhas ao realizar tarefas que exigem privilégios administrativos, como solicitação de acesso ao conjunto de chaves. 

As alterações na política de senha novas ou existentes pelo administrador solicitam que os usuários finais atualizem suas senhas novamente.

Aplica-se a:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-----2340521----"></a>Atribuir certificados SCEP a um dispositivo macOS sem usuário  <!-- 2340521  -->
Você pode atribuir certificados do protocolo SCEP usando atributos do dispositivo a dispositivos macOS, incluindo dispositivos sem afinidade de usuário, e associar o perfil de certificado a perfis de VPN ou Wi-Fi. Isso expande o suporte que já temos para [atribuir certificados SCEP a dispositivos com e sem afinidade de usuário](certificates-scep-configure.md#create-a-scep-certificate-profile) que executam o Windows, o iOS e o Android.  Essa atualização adiciona a opção de selecionar um tipo de Certificado do *Dispositivo* quando você configura um perfil de certificado SCEP para o macOS.

Aplica-se a: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Atualização da interface do usuário de acesso condicional do Intune   <!-- 2432313   -->
Fizemos melhorias na interface do usuário para acesso condicional no console do Intune. Como por exemplo:
-  Substituição da folha *Acesso condicional* do Intune pela folha do Azure Active Directory. Isso garante que você terá acesso à variedade completa de definições e configurações de [acesso condicional](conditional-access.md) (que continua sendo uma tecnologia do Azure AD) no console do Intune. 
- Renomeamos a folha *Acesso local* para *Acesso ao Exchange* e relocamos a configuração *Conector de serviço do Exchange* para essa folha renomeada.  Essa alteração consolida o local em que você [configura e monitora os detalhes relacionados ao Exchange Online e localmente](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Os aplicativos do navegador de quiosque e do navegador Microsoft Edge podem ser executados em dispositivos Windows 10 no modo de quiosque <!-- 2935135   -->
Você pode usar dispositivos Windows 10 no modo de quiosque para executar um ou muitos aplicativos. Esta atualização inclui várias alterações para usar aplicativos de navegador no modo de quiosque, incluindo:

- Adicionar o navegador Microsoft Edge ou o navegador de quiosque para serem executados como aplicativos no dispositivo de quiosque (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **Windows 10 e posterior** para a plataforma > **Quiosque** para tipo de perfil).
- Novos recursos e novas configurações estão disponíveis para permissão ou restrição (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **Windows 10 e posterior** para a plataforma > **Restrições de dispositivo** para o tipo de perfil), incluindo:

  - Navegador Microsoft Edge:
  - Usar o modo de quiosque do Microsoft Edge
  - Atualizar o navegador após tempo ocioso

 - Favoritos e pesquisa:
  - Permitir alterações no mecanismo de pesquisa

Para obter uma lista dessas configurações, confira:

- [Configurações de dispositivos com Windows 10 (e posterior) para execução como um quiosque](kiosk-settings-windows.md)
- [Restrições de dispositivo do navegador Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Favoritos e restrições de dispositivo de pesquisa](device-restrictions-windows-10.md##favorites-and-search)

Aplica-se a: Windows 10 e posterior

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Novas configurações de restrição de dispositivo para dispositivos iOS e macOS <!-- 3448774   -->
Você pode restringir algumas configurações e recursos em dispositivos que executam o iOS e macOS (**Configuração do dispositivo** > **Perfis** > **Novo perfil**  >  **iOS** ou **macOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil). Essa atualização adiciona mais recursos e configurações que você pode controlar, incluindo o tempo da tela de configuração, a alteração das configurações do eSIM e planos do celular, entre outros, em dispositivos iOS. Além disso, o atraso da visibilidade do usuário das atualizações de software e o bloqueio do cache de conteúdo em dispositivos macOS. 

Para ver os recursos e as configurações que você pode restringir, confira:

- [Configurações de restrição de dispositivo iOS](device-restrictions-ios.md)
- [Configurações de restrição de dispositivo macOS](device-restrictions-macos.md)

Aplica-se a:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Os dispositivos de "quiosque" agora são chamados "dispositivos Dedicados" em dispositivos Android Enterprise <!-- 3598402   -->
Para alinhamento com a terminologia do Android, o **quiosque** foi alterado para **dispositivos dedicados** em dispositivos Android Enterprise (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise para a plataforma > **Somente Proprietário do Dispositivo** > **Restrições de dispositivo** > **Dispositivos dedicados**).

Para ver as configurações disponíveis, acesse [Configurações do dispositivo para permitir ou restringir recursos](device-restrictions-android-for-work.md#dedicated-device-settings).

Aplica-se a:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>As configurações do iOS Safari e Atrasando a visibilidade das atualizações de software pelo usuário estão sendo movidas para a interface do usuário do Intune <!-- 3640850, 3803313   -->
Para dispositivos iOS, você pode definir as configurações do Safari e configurar as Atualizações de Software. Nesta atualização, essas configurações estão sendo movidas para diferentes partes da interface do usuário do Intune:

- As configurações do Safari foram movidas da opção **Safari** (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil) para **[Aplicativos Internos](device-restrictions-ios.md#built-in-apps)** .
- A configuração **Atrasando a visibilidade das atualizações de software pelo usuário para dispositivos iOS supervisionados** (**Atualizações de software** > **Atualizar as políticas para iOS**) está sendo movida para **Restrições de dispositivo** >  **[Geral](device-restrictions-ios.md#general)** .  Para obter detalhes sobre o impacto das políticas existentes, confira [Atualizações de software do iOS](software-updates-ios.md#configure-the-policy). 

Para obter uma lista das configurações, confira:

- [Restrições de dispositivo iOS](device-restrictions-ios.md) 
- [Atualizações de software do iOS](software-updates-ios.md)

Esse recurso aplica-se a: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>A configuração Habilitando restrições nas configurações do dispositivo é renomeada para Tempo de Tela em dispositivos iOS <!-- 3699164   -->
Você pode configurar a **Habilitar restrições nas configurações do dispositivo** em dispositivos iOS supervisionados (**Configuração do dispositivo** > **Perfis** > **Novo perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para tipo de perfil > **Geral**). Nesta atualização, essa configuração é renomeada para **Tempo de Tela (somente supervisionado)** . 

O comportamento é o mesmo. Especificamente: 

- iOS 11.4.1 e versões anteriores: **Bloquear** impede que os usuários finais definam suas próprias restrições nas configurações do dispositivo. 
- iOS 12.0 e versões posteriores: **Bloquear** impede que os usuários finais configurem seu próprio **Tempo de Tela** nas configurações do dispositivo, incluindo restrições de privacidade e de conteúdo. Dispositivos atualizados para o iOS 12.0 não exibirão mais a guia de restrições nas configurações do dispositivo. Essas configurações estão no **Tempo de Tela**. 

Para obter uma lista das configurações, confira [Restrições de dispositivo iOS](device-restrictions-ios.md#general).

Aplica-se a: 
- iOS


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Renomear um dispositivo Windows registrado <!-- 1911112  -->
Agora você pode renomear um dispositivo Windows 10 registrado (RS4 ou posterior). Para fazê-lo, escolha **Intune** > **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Renomear dispositivo**. No momento, esse recurso não dá suporte à renomeação de dispositivos Windows do Azure AD híbrido.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Atribuir automaticamente marcas de escopo aos recursos criados por um administrador com esse escopo <!-- 3173823  -->
Quando um administrador cria um recurso, todas as marcas de escopo atribuídas ao administrador serão atribuídas automaticamente a esse novo recurso.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>O relatório de registro com falha é movido para a folha Registro de Dispositivo <!-- 3560202  -->
O relatório **Registros com falha** foi movido para a seção **Monitorar** da folha **Registro de dispositivo**. Duas novas colunas (Método de Registro e Versão do Sistema Operacional) foram adicionadas.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Relatório de abandono do Portal da Empresa renomeado para Registros de usuário incompletos <!--3815076 eemiss -->
O relatório **Abandono do Portal da Empresa** foi renomeado para **Registros de usuário incompletos**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Semana de 4 de fevereiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Modo Escuro do Portal da Empresa do Intune macOS <!-- 3300524  -->
O Portal da Empresa do Intune no macOS agora dá suporte ao Modo Escuro para macOS. Quando você habilitar o Modo Escuro em um dispositivo macOS 10.14 ou superior, o Portal da Empresa ajustará sua aparência de acordo com as cores para refletir o modo.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>Semana de 21 de janeiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Notificações do sistema para aplicativos Win32 <!-- 3136566   -->
Você pode suprimir a exibição de notificações do sistema ao usuário final de acordo com a atribuição de aplicativo. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > selecione o aplicativo > **Atribuições** > **Incluir Grupos**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Atualização da interface do usuário de políticas de proteção de aplicativo do Intune <!-- 3251427  -->
Alteramos os rótulos das configurações e dos botões da proteção de aplicativo do Intune, a fim de facilitar a compreensão. Entre as alterações estão:  
- Mudamos os controles de **sim** / **não** para, principalmente, **bloquear** / **permitir** e **desabilitar** / **habilitar**. Os rótulos também foram atualizados.  
- As configurações foram reformatadas, portanto, a configuração e seu rótulo estão lado a lado no controle, fornecendo uma navegação melhor.   

As configurações padrão e o número de configurações permanecem iguais, mas essa alteração permite que o usuário entenda, navegue e utilize as configurações mais facilmente para aplicar as políticas de proteção de aplicativo específicas. Para saber mais, confira [Configurações do iOS](app-protection-policy-settings-ios.md) e [Configurações do Android](app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Configurações adicionais para o Outlook <!-- 3301182  -->
Agora você pode definir as seguintes configurações adicionais para o Outlook para iOS e Android usando o Intune:

- Permitir o uso somente de contas corporativas ou de estudante no Outlook no iOS e no Android
- Implantar a autenticação moderna para o Office 365 e a autenticação moderna híbrida para contas locais
- Usar `SAMAccountName` para o campo de nome de usuário no perfil de email quando a autenticação Básica for selecionada
- Permitir que os contatos sejam salvos
- Configurar MailTips de destinatários externos
- Configurar **Caixa de Entrada Destaques**
- Exigir biometria para acessar o Outlook para iOS
- Bloquear imagens externas

> [!NOTE]
> Se estiver usando políticas de Proteção de Aplicativo do Intune para gerenciar o acesso de identidades corporativas, considere a possibilidade de não habilitar a opção **Exigir biometria**. Para saber mais, confira **Exigir credenciais corporativas para acesso** para [Configurações de acesso do iOS](app-protection-policy-settings-ios.md#access-requirements) e [Configurações de acesso do Android](app-protection-policy-settings-android.md#access-requirements).

Para obter mais informações, confira [Definições de configuração do Microsoft Outlook](app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Excluir aplicativos Android Enterprise <!-- 1352553 -->
Você pode excluir aplicativos do Google Play Gerenciado no Microsoft Intune. Para excluir um aplicativo do Google Play Gerenciado, abra o Microsoft Intune no portal do Azure e selecione **Aplicativos do cliente** > **Aplicativos**. Na lista de aplicativos, selecione as reticências (...) à direita do aplicativo do Google Play Gerenciado e, em seguida, selecione **Excluir** na lista exibida. Quando você exclui um aplicativo do Google Play gerenciado na lista de aplicativos, o aplicativo do Google Play gerenciado torna-se para aprovação automaticamente.

#### <a name="managed-google-play-app-type----1352580---"></a>Tipo de aplicativo do Google Play Gerenciado <!-- 1352580 -->
O tipo de aplicativo **Google Play gerenciado** permitirá que você adicione especificamente [aplicativos do Google Play gerenciado](https://play.google.com/work/search?q=microsoft&c=apps) ao Intune. Como administrador do Intune, agora você pode navegar, pesquisar, aprovar, sincronizar e atribuir aplicativos aprovados do Google Play Gerenciado no Intune.  Não é mais necessário navegar até o console do Google Play Gerenciado separadamente, nem autenticar novamente.  No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo**, selecione **Google Play Gerenciado** como o tipo de aplicativo.

### <a name="default-android-pin-keyboard----3802457---"></a>Teclado padrão de PIN do Android <!-- 3802457 -->
Para usuários finais que definiram um PIN de APP (Política de Proteção de Aplicativo) do Intune em seus dispositivos Android com o tipo PIN "Numérico", agora será exibido o teclado Android padrão em vez da interface do usuário de teclado Android fixa que foi criada anteriormente. Essa alteração foi feita para ser consistente ao usar teclados padrão no Android e iOS, para os tipos PIN "Numérico" e/ou "Senha". Para obter mais informações sobre as configurações de acesso do usuário final no Android, tais como o PIN do aplicativo, veja [requisitos de acesso do Android](app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Usar as configurações recomendadas pela Microsoft com linhas de base de segurança (versão prévia pública) <!-- 2055484   -->

O Intune integra-se a outros serviços que têm foco na segurança, incluindo o Windows Defender ATP e o Office 365 ATP. Os clientes estão solicitando uma estratégia comum e um conjunto coeso de fluxos de trabalho de segurança de ponta a ponta entre os serviços do Microsoft 365. Nossa meta é alinhar estratégias para criar soluções que façam a ponte entre operações de segurança e tarefas comuns do administrador. No Intune, nosso objetivo é atingir essa meta publicando um conjunto de "Linhas de base de segurança" recomendadas pela Microsoft (**Intune** > **Linhas de base de segurança**).  Um administrador pode criar políticas de segurança diretamente dessas linhas de base e, depois, implantá-las para seus usuários. Também é possível personalizar as recomendações de melhores práticas para atender às necessidades da sua organização. O Intune garante que os dispositivos estejam em conformidade com essas linhas de base e notifica os administradores de usuários ou dispositivos que não estão em conformidade.

Esse recurso está em versão prévia pública, portanto, todos os perfis criados agora não serão movidos para modelos de linhas de base de segurança que estejam em GA (disponibilidade geral). Você não deve planejar usar esses modelos de versão prévia em seu ambiente de produção.

Para saber mais sobre linhas de base de segurança, veja [Criar uma linha de base de segurança do Windows 10 no Intune](security-baselines-monitor.md).

Esse recurso aplica-se a: Windows 10 e posterior

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Aqueles que não são administradores podem habilitar o BitLocker em dispositivos Windows 10 ingressados no Azure AD<!-- 2147379   -->
Ao habilitar as configurações do BitLocker em dispositivos com Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Endpoint Protection** para o tipo de perfil > **Criptografia do Windows**), você adiciona as configurações do BitLocker. 

Esta atualização inclui uma nova configuração de BitLocker para permitir que os usuários padrão (não administradores) habilitem a criptografia. 

Para ver essas configurações, acesse [Configurações do Endpoint Protection para Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Verificar a conformidade do Configuration Manager <!-- 2192052  eepublished  -->
Essa atualização inclui uma nova configuração de conformidade do System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10 e posterior** > **Conformidade do Configuration Manager**). O Configuration Manager envia sinais para a conformidade do Intune. Com essa configuração, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

[Conformidade do Configuration Manager](compliance-policy-create-windows.md#configuration-manager-compliance) descreve essa configuração.

Aplica-se a: Windows 10 e posterior

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Personalizar o papel de parede em dispositivos iOS supervisionados usando um perfil de configuração do dispositivo <!-- 2809324   -->
Ao criar um perfil de configuração do dispositivo para dispositivos iOS, você poderá personalizar alguns recursos (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Recursos do dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações de **Papel de parede** que permitem a um administrador usar uma imagem .png, .jpg ou .jpeg na tela inicial ou na tela de bloqueio. Essas configurações de papel de parede se aplicam somente a dispositivos supervisionados. 

Para obter uma lista com essas configurações, veja [Configurações de recurso em dispositivo iOS](ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>O quiosque do Windows 10 está em disponibilidade geral <!-- 3594661  -->
Nesta atualização, o recurso de Quiosque em dispositivos com Windows 10 e posteriores já está disponível (GA). Para ver todas as configurações que você pode adicionar e definir, consulte [Configurações de quiosque para Windows 10 (e posterior)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>O Compartilhamento de Contatos via Bluetooth foi removido de Restrições de Dispositivo > Proprietário do Dispositivo Android Enterprise <!-- 3598396   -->
Quando você cria um perfil de restrições de dispositivo para dispositivos Android Enterprise, há uma configuração **Compartilhamento de Contatos via Bluetooth**. Nesta atualização, a configuração **Compartilhamento de Contatos via Bluetooth** foi removida (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Restrições de Dispositivo > Proprietário do dispositivo** para o tipo de perfil > **Geral**). 

Não há suporte para a configuração **Compartilhamento de Contatos via Bluetooth** no gerenciamento do Proprietário do Dispositivo Android Enterprise. Portanto, quando essa configuração for removida, ela não afetará nenhum dispositivo ou locatário, mesmo se ela estiver habilitada e configurada no ambiente.

Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md).

Aplica-se a: Proprietário do Dispositivo Android Enterprise

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Suporte de apagamento seletivo para dispositivos WIP sem registro <!-- 1434452 -->
O WIP-WE (Proteção de Informações do Windows sem registro) permite que os clientes protejam seus dados corporativos em dispositivos Windows 10 sem a necessidade de registro MDM completo. Depois que os documentos forem protegidos com uma política de WIP-WE, os dados protegidos poderão ser apagados seletivamente por um administrador do Intune. Se o usuário e o dispositivo forem selecionados e uma solicitação de apagamento for enviada, todos os dados protegidos por meio da política de WIP-WE ficarão inutilizáveis. No Intune no portal do Azure, selecione **Aplicativo móvel** > **Apagamento seletivo do aplicativo**.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Novos logs operacionais e capacidade de enviar logs para serviços do Azure Monitor <!-- 3762211  -->
O Intune tem log de auditoria interno que rastreia os eventos à medida que as alterações são feitas. Esta atualização inclui novos recursos de registro em log, incluindo: 
- Logs operacionais (versão prévia) que mostram detalhes sobre os usuários e dispositivos registrados, incluindo tentativas com falha e sucesso.
- Os logs de auditoria e operacional podem ser enviados ao Azure Monitor, incluindo contas de armazenamento, hubs de eventos e log analytics. Esses serviços permitem que você armazene, use análises como Splunk e QRadar e obtenha visualizações de seus dados de log.

[Enviar dados de log para o armazenamento, hubs de eventos ou log analytics no Intune](review-logs-using-azure-monitor.md) fornece mais informações sobre esse recurso.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Ignorar mais telas do Assistente de Configuração em um dispositivo iOS DEP <!-- 2687509  -->
Além das telas que você pode ignorar no momento, você poderá definir dispositivos iOS DEP para ignorar as seguintes telas no Assistente de Configuração quando um usuário registrar o dispositivo: Exiba tom, Privacidade, Migração do Android, botão Página Inicial, iMessage e FaceTime, Integração, Migração de Inspeção, Aparência, Hora na Tela, Atualização de Software, Configuração do SIM.
Para escolher quais telas ignorar, acesse **Registro do dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Propriedades** > **Personalização do Assistente de Configuração** > escolha **Ocultar** para as telas que você deseja ignorar > **OK**.
Se você cria um perfil novo ou edita um perfil, as telas ignoradas selecionadas precisam ser sincronizadas com o servidor MDM da Apple. Os usuários podem emitir uma sincronização manual dos dispositivos, para que não haja atraso na aplicação das alterações de perfil.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Implantação do aplicativo APP-WE do Android Enterprise <!-- 1171203 -->
Para dispositivos Android em um cenário de implantação APP-WE (Política de proteção de aplicativo sem registro), é possível usar o Google Play gerenciado para implantar aplicativos da loja e aplicativos de LOB para os usuários. Especificamente, é possível fornecer aos usuários finais uma experiência de catálogo e instalação de aplicativos que não exige mais que eles afrouxem a postura de segurança de seus dispositivos ao permitir instalações de fontes desconhecidas. Além disso, esse cenário de implantação fornece uma experiência aprimorada ao usuário final.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>Semana de 14 de janeiro de 2019

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Versão prévia do suporte para dispositivos Android corporativos totalmente gerenciados <!-- 1574342  -->
O Intune agora dá suporte total a dispositivos Android totalmente gerenciados, um cenário de "proprietário do dispositivo" de propriedade corporativa no qual os dispositivos são gerenciados de modo estrito pelo departamento de TI e são afiliados a usuários individuais. Isso permite aos administradores gerenciar todo o dispositivo, impor uma extensa variedade de controles de política não disponíveis aos perfis de trabalho e restringe a instalação de aplicativos por parte dos usuários apenas à Google Play gerenciada. Para obter mais informações, confira [Configurar o registro de dispositivos Android totalmente gerenciados no Intune](android-fully-managed-enroll.md) e [Registrar seus dispositivos dedicados ou dispositivos totalmente gerenciados](android-dedicated-devices-fully-managed-enroll.md).  Observe que esse recurso está em versão prévia. Algumas funcionalidades do Intune, como certificados, conformidade e Acesso Condicional, não estão atualmente disponíveis em dispositivos de usuário Android totalmente gerenciados.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>Semana de 7 de janeiro de 2019

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="intune-app-pin----2298397---"></a>PIN do aplicativo do Intune <!-- 2298397 -->
Como administrador de TI, você pode configurar o número de dias que um usuário final pode aguardar até que o PIN do aplicativo Intune precise ser alterado. A nova configuração é *Redefinição de PIN após o número de dias* e será disponibilizada no portal do Azure pela seleção de **Intune** > **Aplicativos cliente** > **Políticas de proteção do aplicativo** > **Criar Política** > **Configurações** > **Requisitos de acesso**. Disponível para dispositivos [iOS](app-protection-policy-settings-ios.md) e [Android](app-protection-policy-settings-android.md), esse recurso dá suporte a um valor inteiro positivo.


#### <a name="intune-device-reporting-fields----2748738---"></a>Campos de relatório de dispositivo do Intune <!-- 2748738 -->
O Intune fornece campos adicionais de relatório do dispositivo, incluindo ID de Registro do Aplicativo, fabricante do Android, modelo e versão do patch de segurança, bem como modelo do iOS. No Intune, esses campos estão disponíveis pela seleção de **Aplicativos cliente** > **Status de proteção do aplicativo** e escolha de **Relatório de Proteção do Aplicativo: iOS, Android**. Além disso, esses parâmetros ajudam a configurar a lista **Permissão** para o fabricante do dispositivo (Android), a lista **Permissão** para o modelo do dispositivo (Android e iOS) e a configuração de versão mínima do patch de segurança do Android. 


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Os modelos administrativos estão em versão prévia pública e passaram a ter seu próprio perfil de configuração <!-- 3322847 -->

Atualmente, os modelos administrativos no Intune (**Configuração do dispositivo** > **Modelos administrativos**) estão em versão prévia pública. Com esta atualização:

- Os modelos administrativos incluem aproximadamente 300 configurações que podem ser gerenciadas no Intune. Anteriormente, essas configurações só existiam no editor de política de grupo.
- Os modelos administrativos estão disponíveis na versão prévia pública.
- Os modelos administrativos estão sendo transferidos de **Configuração do dispositivo** > **Modelos administrativos** para **Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma**, escolha **Windows 10 e posterior**, em **Tipo de perfil**, escolha **Modelos administrativos**.
- O relatório está habilitado

Para ler mais sobre esse recurso, acesse [Modelos do Windows 10 para definir as configurações da Política de Grupo](administrative-templates-windows.md).

Aplica-se a: Windows 10 e posterior

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Usar o S/MIME para criptografar e assinar vários dispositivos para um usuário  <!-- 1333642 -->
Essa atualização inclui uma criptografia de email S/MIME usando um novo perfil de certificado importado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > selecionar a plataforma > tipo de perfil **Certificado PKCS importado**). No Intune, você pode importar certificados no formato PFX. Em seguida, o Intune pode fornecer os mesmos certificados para vários dispositivos registrados por um único usuário. Isso também inclui:
- O perfil de email do iOS nativo permite habilitar a criptografia S/MIME usando certificados importados no formato PFX.
- O aplicativo de email nativo em dispositivos Windows Phone 10 usam automaticamente o certificado S/MIME.
- Os certificados privados podem ser entregues em várias plataformas. Porém, nem todos os aplicativos de email são compatíveis com S/MIME.
- Em outras plataformas, talvez você precise configurar manualmente o aplicativo de email para habilitar o S/MIME.  
- Os aplicativos de email compatíveis com a criptografia S/MIME podem manipular a recuperação de certificados para criptografia de email S/MIME de uma maneira com a qual o MDM não é compatível, como a leitura do repositório de certificados do editor.
Para obter mais informações sobre esse recurso, confira [Visão geral do S/MIME para assinar e criptografar emails](certificates-s-mime-encryption-sign.md).
Com suporte em: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Novas opções para se conectar automaticamente e persistir as regras ao usar configurações de DNS em dispositivos Windows 10 e posterior <!-- 1333665, 2999078 -->
Em dispositivos Windows 10 e posterior, é possível criar um perfil de configuração de VPN que inclua uma lista de servidores DNS para resolver domínios, por exemplo, contoso.com. Essa atualização inclui novas configurações de resolução de nomes (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **Windows 10 e posterior** para a plataforma > escolha **VPN** para o tipo de perfil > **Configurações de DNS** >**Adicionar**): 
- **Conectar automaticamente**: Quando essa opção está **Habilitada**, o dispositivo se conecta automaticamente à VPN quando um dispositivo entra em contato com um domínio inserido por você, por exemplo, contoso.com.
- **Persistente**: Por padrão, todas as regras de NRPT (Tabela de Políticas de Resolução de Nomes) estão ativas, desde que o dispositivo esteja conectado usando esse perfil de VPN. Quando essa configuração está **Habilitada** em uma regra de NRPT, a regra permanece ativa no dispositivo, mesmo quando a VPN desconectar. A regra permanece até que o perfil de VPN seja removido ou até que a regra seja removida manualmente, o que pode ser feito com o PowerShell.
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md) descreve as configurações. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Usar a detecção de rede confiável para perfis de VPN em dispositivos Windows 10 <!-- 1500165 -->
Ao usar a detecção de rede confiável, é possível impedir que os perfis de VPN criem automaticamente uma conexão VPN quando o usuário já está em uma rede confiável. Com essa atualização, é possível adicionar sufixos DNS para habilitar a detecção de rede confiável em dispositivos que executam o Windows 10 e posterior (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **VPN** para o tipo de perfil).
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md) lista as configurações de VPN atuais.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Gerenciar dispositivos Windows Holographic for Business usados por vários usuários <!-- 1907917, 1063203 -->
No momento, é possível definir as configurações de computador compartilhado em dispositivos Windows 10 e Windows Holographic for Business usando uma configuração personalizada de OMA-URI. Com essa atualização, um novo perfil é adicionado para definir as configurações de dispositivo compartilhado (**Configuração do dispositivo** > **Perfis** > **Criar Perfil** > **Windows 10 e posterior** > **Dispositivo multiusuário compartilhado**).
Para saber mais sobre esse recurso, acesse [Configurações do Intune para gerenciar dispositivos compartilhados](shared-user-device-settings.md).
Aplica-se a: Windows 10 e posteriores, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Novas configurações de Atualização do Windows 10 <!--2626030  2512994  -->
Para os [Grupos de Atualização do Windows 10](windows-update-for-business-configure.md), é possível configurar:
- **Comportamento de atualização automática** – use uma nova opção, *Redefinir para padrão*, para restaurar as configurações originais de atualização automática em um computador Windows 10 em computadores que executam a *Atualização de outubro de 2018*
- **Impedir que o usuário pause as atualizações do Windows** – defina uma nova configuração de atualizações de Software para impedir ou permitir que os usuários pausem uma instalação de atualização nas *Configurações* de seus computadores. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>Os perfis de email do iOS podem usar assinatura e criptografia S/MIME <!-- 2662949 -->
É possível criar um perfil de email que inclua configurações diferentes. Essa atualização inclui configurações de S/MIME que podem ser usadas para assinar e criptografar comunicações por email em dispositivos iOS (**Configurações do dispositivo** > **Perfis** > **Criar perfil** > escolha **iOS** para a plataforma > **Email** para o tipo de perfil).
[Definições de configuração de email do iOS](email-settings-ios.md) lista as configurações.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Algumas configurações do BitLocker dão suporte à edição Windows 10 Pro<!-- 2727036 -->
É possível criar um perfil de configuração que defina as configurações do Endpoint Protection em dispositivos Windows 10, incluindo o BitLocker. Essa atualização adiciona suporte à edição Windows 10 Professional em algumas configurações do BitLocker. Para ver essas configurações de proteção, acesse [Configurações do Endpoint Protection do Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>A configuração de dispositivo compartilhado foi renomeada para Mensagem da Tela de Bloqueio em dispositivos iOS no portal do Azure<!-- 2809362 -->
Ao criar um perfil de configuração para dispositivos iOS, é possível adicionar definições de **Configuração de Dispositivo Compartilhado** para mostrar um texto específico na tela de bloqueio. Essa atualização inclui as seguintes alterações: 
- A **Configuração de Dispositivo Compartilhado** no portal do Azure foi renomeada para "Mensagem na Tela de Bloqueio (apenas supervisionada)" (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **iOS** para a plataforma > escolha **Recursos do dispositivo** para o tipo de perfil > **Mensagem na Tela de Bloqueio**).
- Ao adicionar mensagens da tela de bloqueio, é possível inserir um número de série, um nome de dispositivo ou outro valor específico do dispositivo como variável em **Informações da tag do ativo** e **Nota de rodapé da tela de bloqueio**. Por exemplo, é possível inserir `Device name: {{devicename}}` ou `Serial number is {{serialnumber}}` usando colchetes. [Tokens de iOS](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) lista os tokens disponíveis que podem ser usados.
[Configurações para exibir mensagens na tela de bloqueio](shared-device-settings-ios.md) lista as configurações.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Novas configurações de restrição de dispositivo da App Store, Exibição de Documentos, Jogos adicionadas a dispositivos iOS <!-- 2827760-->
Em **Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil > **App Store, Exibição de Documentos, Jogos**, as seguintes configurações são adicionadas: Permitir que aplicativos gerenciados gravem contatos em contas de contatos não gerenciadas Permitir que aplicativos não gerenciados leiam contas de contatos gerenciadas Para ver essas configurações, acesse [Restrições de dispositivo do iOS](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Novas configurações de notificação, dicas e keyguard para dispositivos de proprietário de dispositivo Android Enterprise <!-- 3201839 3201843 -->
Esta atualização inclui vários recursos novos em dispositivos com Android Enterprise durante a execução como proprietário do dispositivo. Para usar esses recursos, acesse **Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma**, escolha **Android Enterprise** > em **Tipo de perfil**, escolha **Somente proprietário do dispositivo** > **Restrições do Dispositivo**.

Os novos recursos incluem: 

- Desabilitar a exibição de notificações do sistema, incluindo chamadas recebidas, alertas do sistema, erros de sistema e muito mais.
- Sugestão de ignorar os tutoriais iniciais e as dicas para aplicativos abertos pela primeira vez.
- Desabilitar as configurações avançadas de keyguard, como câmera, notificações, impressão digital para desbloqueio e muito mais.


Para ver as configurações, acesse [Configurações de restrição de dispositivo empresarial Android](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Os dispositivos de proprietário de dispositivo Android Enterprise podem usar conexões VPN Always On <!-- 3202194 -->
Nesta atualização, é possível usar as conexões VPN Sempre Ativa em dispositivos com Android Enterprise. As conexões VPN sempre ativadas permanecem conectadas ou são reconectadas imediatamente quando o usuário desbloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. Você também pode colocar a conexão em modo de "bloqueio", o que bloqueia todo o tráfego até que a conexão VPN seja ativada.
É possível habilitar a VPN Sempre Ativa em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Restrições de dispositivo** para Somente Proprietário do Dispositivo > **Conectividade**. Para ver as configurações, acesse [Configurações de restrição de dispositivo empresarial Android](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nova configuração para encerrar processos no Gerenciador de Tarefas em dispositivos Windows 10 <!-- 3285177 --> 
Esta atualização inclui uma nova configuração para encerrar processos usando o Gerenciador de Tarefas em dispositivos com Windows 10. Usando um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma** , escolha **Windows 10** > no **Tipo de perfil**, escolha **Restrições de dispositivo** > **Geral**), é possível permitir ou impedir essa configuração.
Para ver essas configurações, acesse [Configurações de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md).
Aplica-se a: Windows 10 e posterior


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Mensagens mais detalhadas sobre a falha de restrição de registro <!-- 3111564 -->
Mensagens de erro mais detalhadas estão disponíveis quando as restrições de registro não são atendidas. Para ver essas mensagens, acesse **Intune** > **Solucionar problemas** e verifique a tabela Falhas de registro. Para obter mais informações, confira a [lista de falhas de registro](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="tenant-status-dashboard-----1124854---"></a>Painel Status do Locatário  <!-- 1124854 -->
A nova [página Status do Locatário](tenant-status.md) fornece uma localização única em que você pode exibir o status e os detalhes relacionados de seu locatário.  O painel é dividido em quatro áreas:
- **Detalhes do Locatário** – exibe informações que incluem o nome do Locatário e a localização, a Autoridade de MDM, o total dos dispositivos registrados no locatário e contagens de licenças. Essa seção também lista a versão de serviço atual do locatário.
- **Status do Conector** – exibe informações sobre os conectores disponíveis configurados e também pode listar aqueles que ainda não foram habilitados.  
   Com base no estado atual de cada conector, eles são sinalizados como Íntegros, Aviso ou Não Íntegros. Selecione um conector para examiná-lo e exibir detalhes ou configurar informações adicionais para ele.
-  **Integridade do Serviço Intune** – exibe detalhes sobre incidentes ativos ou interrupções do locatário. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office.
-  **Notícias do Intune** – exibe as mensagens ativas do locatário. As mensagens incluem itens como notificações quando seu locatário receber os últimos recursos do Intune.  As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nova experiência de ajuda e suporte no Portal da Empresa para Windows 10 <!-- 1488939-->
A nova página Ajuda e suporte do Portal da Empresa ajuda os usuários a solucionar problemas e solicitar ajuda para problemas de acesso e de aplicativo. Na nova página, eles podem enviar por email detalhes do log de diagnóstico e de erro e encontrar os detalhes da Assistência Técnica de sua organização. Eles também encontrarão uma seção de perguntas frequentes com links para a documentação relevante do Intune. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nova experiência de Ajuda e Suporte do Intune   <!-- #3307080 -->
Estamos distribuindo a nova experiência de Ajuda e Suporte a todos os locatários nos próximos dias. Essa nova experiência está disponível para o Intune e pode ser acessada ao usar as folhas do Intune no [portal do Azure](https://portal.azure.com/).
A nova experiência permite que você descreva seu problema em suas próprias palavras e receba informações de solução de problemas e conteúdo de correção baseado na Web. Essas soluções são oferecidas por meio de um algoritmo de aprendizado de máquina baseado em regras, orientado por consultas de usuário. Além das diretrizes específicas do problema, você usa o novo fluxo de trabalho de criação de caso para abrir um caso de suporte por email ou telefone. Essa nova experiência substitui a experiência anterior de Ajuda e Suporte de um conjunto estático de opções pré-selecionadas com base na área do console em que você está quando abre a Ajuda e Suporte. Para obter mais informações, confira [Como obter suporte para o Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-for-apps----1081941---"></a>Marcas de escopo para aplicativos <!-- 1081941 -->
Você pode criar marcas de escopo para limitar o acesso para funções e aplicativos. Você pode adicionar uma tag de escopo a um aplicativo para que somente as pessoas com as funções também atribuídas a essa tag de escopo tenham acesso ao aplicativo. Atualmente, os aplicativos adicionados ao Intune pela Google Play gerenciado ou a partir de aplicativos adquiridos usando o VPP (Volume Purchase Program) da Apple não podem receber marcas de escopo (está planejado o suporte futuro). Para obter mais informações, confira [Usar marcas de escopo para filtrar políticas](scope-tags.md).

<!-- ########################## -->
## <a name="week-of-december-10-2018"></a>Semana de 10 de dezembro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="updates-for-application-transport-security----748318---"></a>Atualizações de Segurança do Transporte de Aplicativo <!-- 748318 -->

O Microsoft Intune dá suporte para o protocolo TLS 1.2 e versões posteriores para fornecer a melhor criptografia, garantir que o Intune esteja mais seguro por padrão e alinhar-se a outros serviços da Microsoft, como o Microsoft Office 365. Para atender a esse requisito, os portais da empresa para iOS e macOS imporão requisitos atualizados de ATS (Segurança do Transporte de Aplicativo) da Apple que também exigem TLS 1.2 e versões posteriores. O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS e macOS. Para saber mais, confira o [blog de suporte do Intune](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>O SDK de Aplicativo do Intune dará suporte a chaves de criptografia de 256 bits <!-- 1832174 -->
Agora o SDK do Aplicativo Intune para Android usa as chaves de criptografia de 256 bits quando a criptografia é habilitada por Políticas de Proteção de Aplicativo. O SDK continua a fornecer suporte a chaves de 128 bits para compatibilidade com o conteúdo e aplicativos que usam versões mais antigas do SDK.

### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>É necessário ter a versão 4.5.0 da Atualização Automática da Microsoft para dispositivos macOS <!-- 3503442 -->
Para continuar recebendo atualizações para o Portal da Empresa e outros aplicativos do Office, os dispositivos macOS gerenciados pelo Intune devem atualizar para a Atualização Automática da Microsoft 4.5.0. Talvez os usuários já tenham essa versão para seus aplicativos do Office.

### <a name="intune-requires-macos-1012-or-later----2827778---"></a>O Intune exige o macOS 10.12 ou posterior <!-- 2827778 -->
Agora, o Intune exige o macOS 10.12 ou posterior. Dispositivos que usam versões anteriores do macOS não podem usar o Portal da Empresa para se inscrever no Intune. Para receber assistência do suporte e os novos recursos, os usuários precisarão atualizar seus dispositivos para o macOS 10.12 ou superior, e atualizar o aplicativo Portal da Empresa para a versão mais recente.

<!-- ########################## -->
## <a name="week-of-november-26-2018"></a>Semana de 26 de novembro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Como desinstalar aplicativos em dispositivos iOS supervisionados corporativos <!-- 1281677 -->

Você pode remover qualquer aplicativo em dispositivos iOS corporativos supervisionados. Você pode remover qualquer aplicativo definindo como destino grupos de usuários ou dispositivos com um tipo de atribuição de **Desinstalação**. Para dispositivos iOS não supervisionados ou pessoais, você continuará podendo remover apenas os aplicativos instalados usando o Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Como baixar conteúdo de aplicativos Win32 do Intune <!-- 2617320 -->
Os clientes com Windows 10 RS3 e superior baixarão o conteúdo do aplicativo Intune Win32 usando um componente de Otimização de Entrega no cliente do Windows 10. A otimização de entrega fornece o recurso de ponto a ponto ativada por padrão. Atualmente, a otimização de entrega pode ser configurada pela política de grupo. Para saber mais, consulte [Otimização de entrega para Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Dispositivo de usuário final e menu de conteúdo do aplicativo <!-- 2771453 -->
Os usuários finais agora podem usar o menu de contexto no dispositivo e nos aplicativos para acionar ações comuns, como renomear um dispositivo ou verificar a conformidade.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Definir a tela de fundo personalizada no aplicativo Tela Inicial Gerenciada  <!-- 3041945 -->
Vamos adicionar uma configuração que permite personalizar a aparência da tela de fundo do aplicativo Tela Inicial Gerenciada em dispositivos Android Enterprise de vários aplicativos em modo de quiosque.  Para configurar a **tela de fundo da URL Personalizada**, vá para o Intune no portal do Azure > Configuração do dispositivo. Selecione um perfil de configuração do dispositivo atual ou crie um novo para editar suas configurações de quiosque.
Para ver as configurações de quiosque, consulte [Restrições de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Salvar e aplicar atribuição de política de proteção de aplicativo <!-- 3104570 -->
Agora, você tem mais controle sobre suas [atribuições de política de proteção de aplicativo](app-protection-policies.md#deploy-a-policy-to-users). Ao selecionar *Atribuições* para definir ou editar as atribuições de uma política, você deve **Salvar** sua configuração antes de aplicar a alteração. Use **Descartar** para limpar todas as alterações feitas sem salvá-las nas listas de inclusão ou exclusão.  Ao exigir Salvar ou Descartar, apenas os usuários desejados receberão uma política de proteção do aplicativo.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Novas configurações do navegador Microsoft Edge para Windows 10 e posterior <!-- 3174639 -->
Essa atualização inclui novas configurações para ajudar a controlar e gerenciar o navegador Microsoft Edge em seus dispositivos. Para obter uma lista dessas configurações, consulte [Restrição de dispositivo para Windows 10 (e mais recentes)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Novo suporte a aplicativos com políticas de proteção de aplicativo <!-- 3330037 -->
Agora, você pode gerenciar os seguintes aplicativos com as [políticas de proteção de aplicativo do Intune](app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Use as políticas de proteção de aplicativo para proteger dados corporativos e controlar a transferência de dados para esses aplicativos, como outros aplicativos gerenciados pela política do Intune. Observação: Se o Flow ainda não estiver visível no console, adicione-o criando ou editando políticas de proteção do aplicativo. Para fazer isso, use a opção **+ Mais aplicativos** e especifique a *ID do Aplicativo* do Flow no campo de entrada. No Android, use *com.microsoft.flow* e para iOS use *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>Os números de build e de versão do iOS e do macOS são mostrados <!-- 1892471 -->
Em **Conformidade do dispositivo** > **Conformidade do dispositivo**, as versões do sistema operacional iOS e macOS são mostradas e estão disponíveis para uso em políticas de conformidade. Essa atualização inclui o número de build, configurável em ambas as plataformas.
Quando são lançadas atualizações de segurança, a Apple normalmente mantém o número de versão no estado em que se encontra, mas atualiza o número de build. Ao usar o número de build em uma política de conformidade, você pode verificar facilmente se uma atualização de vulnerabilidade está instalada.
Para usar esse recurso, consulte as políticas de conformidade para [iOS](compliance-policy-create-ios.md#device-health) e [macOS](compliance-policy-create-mac-os.md#device-properties).

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Os grupos de atualização estão sendo substituídos por configurações de Otimização de Entrega para o Windows 10 e posterior <!-- 2753807 -->
Otimização de entrega é um novo perfil de configuração para o Windows 10 e versões posteriores. Esse recurso fornece uma experiência mais simplificada para fornecer atualizações de software para dispositivos em sua organização. Essa atualização também ajuda você a fornecer as configurações em anéis de atualização novos e existentes usando um perfil de configuração.
Para configurar um perfil de configuração de otimização de entrega, consulte [Configurações de otimização de entrega do Windows 10 (e versões mais recentes)](delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Novas configurações de restrição de dispositivo adicionadas para dispositivos iOS e macOS <!-- 2827760 -->
Esta atualização inclui novas configurações para dispositivos iOS e macOS lançados com o iOS 12:

**Configurações do iOS**: 
- Geral: Bloquear remoção de aplicativo (somente supervisionada)
- Geral: Bloquear modo restrito de USB (somente supervisionada)
- Geral: Forçar de data e hora automáticas (somente supervisionada)
- Contrasenha: Bloquear preenchimento automático de senha (somente supervisionada)
- Contrasenha: Bloquear solicitações de proximidade de senha (somente supervisionada)
- Contrasenha: Bloquear compartilhamento de senha (somente supervisionada)

**Configurações do macOS**: 
- Contrasenha: Bloquear o preenchimento automático de senha
- Contrasenha: Bloquear solicitações de proximidade de senha
- Contrasenha: Bloquear compartilhamento de senha

Para saber mais sobre essas configurações, consulte as configurações de restrição de dispositivos [iOS](device-restrictions-ios.md) e [macOS](device-restrictions-macos.md).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Aplicativos selecionados acompanhados na Página de Status de Registro<!-- 2531007 -->
Você pode escolher quais aplicativos são rastreados na página de status de registro. Até que esses aplicativos sejam instalados, o usuário não pode usar o dispositivo. Para saber mais, consulte [Configurar uma página de status de registro](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Pesquisar o dispositivo do Autopilot pelo número de série <!--2595788 -->
Agora, você pode pesquisar dispositivos do Autopilot pelo número de série. Para fazer isso, escolha **Registro de dispositivo** > **Registro do Windows** > **Dispositivos** > digite um número de série na caixa **Pesquisar por número de série** > pressione Enter.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Acompanhar a instalação do Office ProPlus <!--2620217 -->
Os usuários podem acompanhar o progresso da instalação do [Office ProPlus](apps-add-office365.md) usando a [Página de Status de Registro](windows-enrollment-status.md). Para saber mais, consulte [Configurar uma página de status de registro](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token VPP ou de licença do Portal da Empresa <!-- 2237572 -->
Se você estiver usando o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem acabando.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Suporte do Programa de registro de dispositivos do macOS para contas do Apple School Manager <!--3006133 -->
Agora o Intune oferece suporte ao uso do Programa de registro de dispositivos em dispositivos macOS para contas do Apple School Manager.  Para saber mais, consulte [Registrar automaticamente dispositivos macOS com o Apple School Manager ou o Programa de registro de dispositivos](device-enrollment-program-enroll-macos.md).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Novo SKU de assinatura de dispositivo do Intune <!--3312071-->
Para ajudar a reduzir o custo de dispositivos de gerenciamento nas empresas, um novo SKU de assinatura com base em dispositivo agora está disponível. Este SKU de dispositivo do Intune é licenciado por dispositivo mensalmente. O preço varia de acordo com o programa de licenciamento. Ele está disponível diretamente no Centro de administração do Microsoft 365 e pelo EA ([Contrato Enterprise](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2)), MPSA ([Contrato de Produtos e Serviços Microsoft](https://www.microsoft.com/licensing/mpsa/default)), [Contratos Microsoft Open](https://partner.microsoft.com/licensing/licensing-agreements) e CSP ([Provedor de Soluções na Nuvem](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453)).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Pausar temporariamente o modo de quiosque em dispositivos Android para fazer alterações <!-- 3041935 -->
Ao usar dispositivos Android no modo de quiosque de vários aplicativos, um administrador de TI talvez precise fazer alterações ao dispositivo. Essa atualização inclui novas configurações de quiosque de vários aplicativos que possibilitam que um Administrador de TI pause temporariamente o modo de quiosque usando um PIN e obtenha acesso a todo o dispositivo.
Para ver as configurações de quiosque, consulte [Restrições de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Habilitar o botão de página inicial virtual em dispositivos de quiosque Android Enterprise  <!-- 3042021 -->
Uma nova configuração permitirá que os usuários toquem em um botão de tecla no dispositivo para alternar entre o aplicativo Tela Inicial Gerenciada e outros aplicativos atribuídos no dispositivo de quiosque de vários aplicativos. Essa configuração é particularmente útil em cenários em que o aplicativo de quiosque do usuário não responde adequadamente ao botão "Voltar". Você poderá definir essa configuração para dispositivos Android de uso único e corporativos. Para habilitar ou desabilitar o **botão de Página inicial virtual**, vá para o Intune no portal do Azure > Configuração do dispositivo. Selecione um perfil de configuração do dispositivo atual ou crie um novo para editar suas configurações de quiosque.
Para ver as configurações de quiosque, consulte [Restrições de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).

<!-- ########################## -->
## <a name="week-of-november-12-2018"></a>Semana de 12 de novembro de 2018

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Suporte do NAC (Controle de Acesso à Rede) do Citrix SSO para iOS <!-- 3259404 -->

A Citrix lançou uma atualização para o Citrix Gateway para permitir o Controle de Acesso de Rede (NAC) do Citrix SSO para iOS no Intune. Você pode optar por incluir uma ID de dispositivo em um perfil da VPN no Intune e, em seguida, enviar esse perfil por push para dispositivos iOS. Você precisará instalar a atualização mais recente do Citrix Gateway para usar essa funcionalidade.

[Definir configurações da VPN em dispositivos iOS](vpn-settings-ios.md#base-vpn-settings) fornece mais informações sobre como usar o NAC, incluindo alguns requisitos adicionais. 

<!-- ########################## -->
## <a name="week-of-november-5-2018"></a>Semana de 5 de novembro de 2018

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Suporte para OAuth do iOS 12 em perfis de email do iOS <!--2155106 -->

Perfis de email do iOS do Intune oferecem suporte ao OAuth (Open Authorization) do iOS 12. Para ver esse recurso, crie um novo perfil (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Email** para tipo de perfil), ou atualize um perfil de email do iOS existente. Caso habilite o OAuth em um perfil que já esteja implantado para os usuários, os usuários serão solicitados a autenticar novamente e baixar seus emails de novo.

Os [perfis de email do iOS](email-settings-ios.md) têm mais informações sobre como usar o OAuth em um perfil de email.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Suporte do Autopilot para dispositivos ingressados no Azure Active Directory híbrido (versão prévia) <!-- 1048100-->
Você agora pode configurar dispositivos ingressados no Azure Active Directory híbrido usando o Autopilot. Os dispositivos devem ser ingressados na rede da sua organização para usar o recurso Autopilot híbrido. Para obter mais informações, confira [Implantar dispositivos ingressados no Azure AD híbrido usando o Intune e o Windows Autopilot](windows-autopilot-hybrid.md).
Esse recurso será implantando em toda a base de usuários nos próximos dias. Portanto, você não poderá seguir estas etapas até que ela seja distribuída para a sua conta.

<!-- ########################## -->
## <a name="week-of-october-29-2018"></a>Semana de 29 de outubro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Exigir PIN não biométrico após um tempo limite especificado <!-- 1506985 -->
Ao exigir um PIN não biométrico após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos clientes** > **Políticas de proteção de aplicativos** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas. Para obter informações sobre as configurações de acesso, confira [Configurações do iOS](app-protection-policy-settings-ios.md#access-requirements) e [Configurações do Android](app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Configurações de transferência de dados da APP do Intune em dispositivos iOS registrados no MDM <!-- 2244713 -->
Você pode separar o controle de configurações de transferência de dados do Aplicativo do Intune em dispositivos registrados no MDM do iOS da especificação de identidade do usuário registrado, também conhecida como nome UPN. Os administradores que não estiverem usando o IntuneMAMUPN não observarão uma alteração de comportamento. Quando essa funcionalidade estiver disponível, os administradores que estiverem usando o IntuneMAMUPN para controlar o comportamento de transferência de dados em dispositivos registrados deverão revisar as novas configurações e atualizar as configurações de aplicativo conforme necessário.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplicativos Win32 do Windows 10 <!-- 2617325 -->
Você pode configurar seus aplicativos do Win32 a serem instalados no contexto de usuário para usuários individuais, em vez de instalar o aplicativo para todos os usuários do dispositivo.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplicativos Win32 do Windows e scripts do PowerShell <!-- 2617330 -->
Os usuários finais não precisam mais fazer logon no dispositivo para instalar aplicativos do Win32 ou executar scripts do PowerShell. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Solução de problemas de instalação de aplicativos cliente <!-- 1363711 -->
Você pode solucionar problemas de sucesso da instalação de aplicativos cliente examinando a coluna rotulada **Instalação do aplicativo** na folha **Solucionar problemas**. Para exibir a folha **Solucionar problemas**, no portal do Intune, selecione **Solucionar problemas** em **Ajuda e suporte**.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Suporte para controle de acesso à rede em clientes VPN do iOS <!-- 1333693 -->
Com essa atualização, há uma nova configuração para habilitar o NAC (Controle de Acesso à Rede) quando você cria um perfil de configuração de VPN para Cisco AnyConnect, F5 Access e Citrix SSO para iOS. Essa configuração permite que a ID de NAC do dispositivo seja incluída no perfil de VPN. Atualmente, não existe nenhum cliente VPN nem solução de parceiro NAC que dê suporte a essa nova ID de NAC, mas manteremos você informado por meio de nossa [postagem no blog de suporte](ttps://aka.ms/iOS12_and_vpn) quando houver.

Para usar o NAC, você precisará:
1. Optar por permitir que o Intune inclua as identificações de dispositivo em perfis de VPN
2. Atualizar o seu software/firmware de provedor NAC usando as diretrizes diretamente do seu provedor NAC

Para obter informações sobre essa configuração em um perfil VPN do iOS, confira [Adicionar configurações de VPN a dispositivos iOS no Microsoft Intune](vpn-settings-ios.md). Para obter mais informações sobre o controle de acesso de rede, confira [Integração de NAC (controle de acesso à rede) com o Intune](network-access-control-integrate.md). 

Aplica-se a: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Remover um perfil de email de um dispositivo, mesmo quando há apenas um email perfil <!-- 1818139 -->
Anteriormente, não era possível remover um perfil de email de um dispositivo *quando* ele era o único perfil de email. Com essa atualização, esse comportamento foi alterado. Agora, você pode remover um perfil de email, mesmo que ele seja o único perfil de email no dispositivo. Confira [Adicionar configurações de email em dispositivos usando o Intune](email-settings-configure.md) para obter detalhes.

#### <a name="powershell-scripts-and-aad----2309469---"></a>Scripts do PowerShell e AAD <!-- 2309469 -->
Scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nova configuração padrão "Tipo de senha obrigatória" para Android, Android Enterprise<!-- 2649963 -->
Quando você cria uma nova política de conformidade (**Intune** > **Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android** ou **Android Enterprise** para a Plataforma > Segurança do Sistema), o valor padrão para **Tipo de senha necessário** muda:

De: O dispositivo assume o padrão: Ao menos numérico

Aplica-se a: Android, Android Enterprise

Para ver essas configurações, vá para [Android](compliance-policy-create-android.md) e [Android Enterprise](compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Usar uma chave pré-compartilhada em um perfil de Wi-Fi do Windows 10 <!-- 2662938 -->
Com essa atualização, você pode usar uma chave pré-compartilhada (PSK) com o protocolo de segurança WPA/WPA2-Personal para autenticar um perfil de configuração de Wi-Fi no Windows 10. Você também pode especificar a configuração de custo para uma rede limitada para dispositivos com a atualização de outubro de 2018 do Windows 10.

No momento, é preciso importar um perfil de Wi-Fi ou criar um perfil personalizado para usar uma chave pré-compartilhada. [Configurações de Wi-Fi no Windows 10](wi-fi-settings-windows.md) lista as configurações atuais. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Remover certificados PKCS e SCEP de seus dispositivos <!-- 3218390 -->
Em alguns cenários, os certificados PKCS e SCEP permaneciam nos dispositivos, mesmo quando uma política era removida de um grupo, quando uma configuração ou implantação de conformidade era excluída ou quando um administrador atualizava um perfil de SCEP ou de PKCS existente. Essa atualização alterou esse comportamento. Há alguns cenários em que os certificados PKCS e SCEP são removidos dos dispositivos e alguns cenários em que eles permanecem no dispositivo. Confira [Remove SCEP and PKCS certificates in Microsoft Intune](remove-certificates.md) (Remover certificados SCEP e PKCS no Microsoft Intune) para conhecer esses cenários.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Usar o Gatekeeper em dispositivos macOS para conformidade <!-- 2504381 -->
Esta atualização inclui o Gatekeeper para macOS avaliar dispositivos quanto à conformidade. Para definir a propriedade de Gatekeeper, escolha [Adicionar uma política de conformidade do dispositivo para dispositivos macOS](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="enrollment-abandonment-report----1382924---"></a>Relatório de abandono de registro <!-- 1382924 -->
Um novo relatório que fornece detalhes sobre registros abandonados está disponível em **Registro de dispositivo** > **Monitorar**. Para obter mais informações, confira [Relatório de abandono do portal da empresa](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Novo recurso de termos de uso do Azure Active Directory <!-- 2870393 -->
O Azure Active Directory tem um recurso de termos de uso que você pode usar em vez dos termos e condições existentes do Intune. O recurso de termos de uso do Azure AD oferece mais flexibilidade sobre quais termos mostrar e quando mostrá-los, melhor suporte à localização, mais controle em como os termos são renderizados e melhor geração de relatórios. O recurso de termos de uso do Azure AD requer o Azure Active Directory Premium P1, que também faz parte do pacote Enterprise Mobility + Security E3. Para obter mais informações, confira o [artigo Gerenciar seus termos e condições da sua empresa para acesso do usuário](terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Suporte ao modo de Proprietário do Dispositivo Android <!--3188762-->
Para o Registro Móvel do Samsung Knox, o Intune agora dá suporte ao registro de dispositivos para o modo de Proprietário de Dispositivo Android do gerenciamento. Os usuários em redes de celular ou Wi-Fi podem inscrever seus dispositivos com apenas alguns toques ao o ligarem pela primeira vez. Para saber mais, confira [Inscrever automaticamente os dispositivos Android usando o Knox Mobile Enrollment da Samsung](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Gerenciamento de dispositivos
#### <a name="new-settings-for-software-updates------1907869---"></a>Novas configurações de atualizações de software   <!-- 1907869 -->  
- Agora, você pode configurar algumas notificações para alertar os usuários finais sobre reinicializações exigidas para concluir a instalação das atualizações de software mais recentes.   
- Agora, você pode configurar um prompt de aviso de reinicialização para reinicializações que ocorrem fora do horário de trabalho, o que dá suporte a cenários de BYOD.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Agrupar dispositivos registrados no Windows Autopilot por ID de correlação <!-- 2075110 -->
O Intune agora dá suporte ao agrupamento de dispositivos Windows por uma ID de correlação quando registrado usando o [Autopilot para dispositivos existentes](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) por meio do Configuration Manager. A ID de correlação é um parâmetro do arquivo de configuração do Autopilot. O Intune definirá automaticamente o [atributo do dispositivo do Azure AD enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) para que ele seja igual a "OfflineAutopilotprofile-<correlator ID>". Isso permite que os grupos dinâmicos arbitrários do Azure AD sejam criados com base na ID de correlação por meio do atributo enrollmentprofileName para registros offline do Autopilot. Para obter mais informações, confira [Windows Autopilot para dispositivos existentes](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Políticas de proteção de aplicativo do Intune <!-- 2984657 -->
As políticas de Proteção de Aplicativo do Intune permitem que você defina várias configurações de proteção de dados para aplicativos protegidos do Intune, como Microsoft Word e Microsoft Outlook. Alteramos a aparência dessas configurações para [iOS](app-protection-policy-settings-ios.md) e [Android](app-protection-policy-settings-android.md) para tornar mais fácil encontrar as configurações individuais. Há três categorias de configurações de política:
- **Realocação de dados** – esse grupo inclui os controles DLP (prevenção de perda dados), como restrições de cortar, copiar, colar e salvar-como. Essas configurações determinam como os usuários interagem com os dados nos aplicativos.
- **Requisitos de acesso** – esse grupo contém as opções de PIN por aplicativo que determinam como o usuário final acessa os aplicativos em um contexto de trabalho.  
- **Inicialização condicional** – esse grupo contém configurações como configurações de sistema operacional mínimo, jailbreak e detecção de dispositivos com raiz e períodos de cortesia offline.  
  
A funcionalidade das configurações não muda, mas será mais fácil encontrá-la quando você trabalhar na política de fluxo de criação.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>O Intune dará suporte a um tamanho máximo de pacote de 8 GB para aplicativos LOB <!-- 1727158 -->
O Intune aumentou o tamanho máximo do pacote para 8 GB para aplicativos de LOB (linha de negócios). Para obter mais informações, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Adicionar imagem de marca personalizada ao aplicativo do Portal da Empresa <!-- 1916266 -->
Como administrador do Microsoft Intune, você poderá fazer upload de uma imagem de marca personalizada que será exibida como uma imagem de tela de fundo na página do perfil do usuário no aplicativo do Portal da Empresa iOS. Para obter mais informações sobre como configurar o aplicativo do Portal da Empresa, confira [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>O Intune manterá o idioma localizado do Office ao atualizar o Office nos computadores dos usuários finais <!-- 2971030 -->
Quando o Intune instalar o Office nos computadores do seu usuário final, os usuários finais obterão automaticamente os mesmos pacotes de idioma que eles tinham com as instalações anteriores do .MSI Office. Para obter mais informações, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nova experiência de suporte do Intune no portal de Gerenciamento de Dispositivo do Microsoft 365 <!-- 3076965 -->
Estamos desenvolvendo uma nova experiência de Ajuda e Suporte para o Intune no [Portal de Gerenciamento de Dispositivo do Microsoft 365]( http://devicemanagement.microsoft.com). A nova experiência permite que você descreva seu problema em suas próprias palavras e receba informações de solução de problemas e conteúdo de correção baseado na Web. Essas soluções são oferecidas por meio de um algoritmo de aprendizado de máquina baseado em regras, orientado por consultas de usuário.  

Além das orientações específicas do problema, você também pode usar o novo fluxo de trabalho de criação do caso para abrir um caso de suporte por email ou telefone.  

Para clientes que fazem parte da implementação, essa nova experiência substitui a experiência de Ajuda e Suporte atual de um conjunto estático de opções pré-selecionadas com base na área do console em que você está quando você abre a Ajuda e Suporte.  

*Esta nova experiência de Ajuda e Suporte está sendo distribuída a alguns, mas não todos, os locatários e está disponível no Portal de Gerenciamento de Dispositivo. Os participantes dessa nova experiência são selecionados aleatoriamente entre os locatários do Intune disponíveis. Novos locatários serão adicionados à medida que expandirmos a distribuição.*  

Para obter mais informações, confira [Experiência de Ajuda e Suporte](get-support.md#help-and-support-experience) em Como obter suporte para o Microsoft Intune.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Módulo do PowerShell para Intune – Versão prévia disponível <!-- 951068 -->
Um novo módulo do PowerShell, que dá suporte para a API do Intune por meio do Microsoft Graph, agora está disponível em versão prévia no [GitHub]( https://aka.ms/intunepowershell). Para obter detalhes de como usar esse módulo, confira o LEIAME nesse local. 


<!-- ########################## -->
## <a name="week-of-october-15-2018"></a>Semana de 15 de outubro de 2018

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Solicitação de PIN ao alterar impressões digitais ou identificação de rosto em um dispositivo iOS  <!-- 2637704  -->
Os usuários agora são solicitados a inserir um PIN após fazerem alterações biométricas em seu dispositivo iOS. Isso inclui alterações em impressões digitais ou Face ID registradas. O tempo da solicitação depende da configuração do tempo limite em *Verificar novamente os requisitos de acesso após (minutos)* .  Quando não há um PIN definido, o usuário é solicitado a definir um. 
 
Esse recurso está disponível apenas para iOS e requer a participação de aplicativos que integram o SDK do aplicativo Intune para iOS, versão 9.0.1 ou posterior. A integração do SDK é necessária para que o comportamento possa ser aplicado aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. Alguns aplicativos que participam incluem WXP, Outlook, Managed Browser e Yammer.


<!-- ########################## -->
## <a name="week-of-october-1-2018"></a>Semana de 1 de outubro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Acesso a propriedades-chave do perfil usando o aplicativo do portal da empresa <!-- 772203 -->
Os usuários finais já podem acessar as propriedades e ações da conta de chave de acesso, como redefinição de senha, do aplicativo Portal da Empresa. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Os teclados de terceiros podem ser bloqueados por configurações da APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune podem bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivo. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Acesso à conta de usuário de aplicativos do Intune em dispositivos Android e iOS gerenciados <!-- 1248496 -->
Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Política de configuração de aplicativos do Outlook para iOS e Android <!--1828527 -->
Agora você pode criar uma política de configuração de aplicativo do Outlook para iOS e Android para usuários locais que aproveitam a autenticação Básica com o protocolo ActiveSync. Outras configurações serão adicionadas à medida que forem habilitadas no Outlook para iOS e Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Extensões de arquivo de aplicativos LOB (linha de negócios) do Windows <!-- 1884873 -->
As extensões de arquivo para aplicativos LOB do Windows agora incluirão *.msi*, *.appx*, *.appxbundle*, *.msix* e *.msixbundle*. Você pode adicionar um aplicativo no Microsoft Intune, selecionando **Aplicativos clientes** > **Aplicativos** > **Adicionar**. O painel **Adicionar aplicativo** é exibido permitindo que você selecione o **Tipo de aplicativo**. Para aplicativos de LOB do Windows, selecione aplicativo de **Linha de negócios** como o tipo de aplicativo, selecione o **Arquivo de pacote do aplicativo** e, em seguida, insira um arquivo de instalação com a extensão apropriada.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Implantação do aplicativo do Windows 10 usando o Intune <!-- 2309001 -->
Criado com base no suporte existente para aplicativos LOB (linha de negócios) e aplicativos Microsoft Store para Empresas, os administradores podem usar o Intune para implantar a maioria dos aplicativos existentes de sua organização nos usuários finais em dispositivos Windows 10. Os administradores podem adicionar, instalar e desinstalar aplicativos para usuários do Windows 10 em diversos formatos, como MSIs, Setup.exe ou MSP. O Intune avaliará as regras de requisitos antes de baixar e instalar, notificar os usuários finais do status ou dos requisitos de reinicialização usando a Central de Ações do Windows 10. Essa funcionalidade desbloqueará efetivamente organizações interessadas em deslocar essa carga de trabalho para o Intune e a nuvem. No momento, este recurso está em versão prévia pública e esperamos adicionar novas funcionalidades significativas a ele durante os próximos meses. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações da APP (Política de Proteção de Aplicativo) para dados da Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Dispositivo de usuário final e menu de conteúdo do aplicativo <!-- 2771453 -->
Os usuários finais agora podem usar o menu de contexto no dispositivo e aplicativos para disparar ações comuns, como renomear um dispositivo ou verificar a conformidade. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Atalhos de teclado do Portal da Empresa do Windows <!-- 2771518 -->
Os usuários finais agora poderão disparar ações de aplicativo e do dispositivo no Portal da Empresa do Windows usando atalhos de teclado (aceleradores).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Criar sufixos DNS em perfis de configuração de VPN em dispositivos que executam o Windows 10<!-- 1333668 -->
Quando você cria um perfil de configuração do dispositivo VPN (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **plataforma Windows 10 ou posterior** > O tipo de perfil **VPN**), insere algumas configurações de DNS. Com essa atualização, também é possível inserir vários **sufixos DNS** no Intune. Ao usar sufixos DNS, você pode procurar um recurso de rede usando o nome curto dele em vez do nome de domínio totalmente qualificado (FQDN). Essa atualização também permite alterar a ordem dos sufixos DNS no Intune.
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md#dns-settings) lista as configurações DNS atuais.
Aplica-se a: Dispositivos com Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Suporte para VPN Always On em perfis de trabalho do Android Enterprise <!-- 1333705 -->
Nesta atualização, é possível usar as conexões VPN Always On em dispositivos Android empresariais com perfis de trabalho gerenciados. As conexões VPN sempre ativadas permanecem conectadas ou são reconectadas imediatamente quando o usuário desbloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. Você também pode colocar a conexão em modo de "bloqueio", o que bloqueia todo o tráfego até que a conexão VPN seja ativada.
É possível habilitar a VPN Always On na **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android enterprise** para configurações da plataforma > **Restrições de dispositivo** > **Conectividade**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Emitir certificados SCEP para dispositivos sem usuário <!-- 1744554 -->
Atualmente, os certificados são emitidos para usuários. Com essa atualização, os certificados SCEP podem ser emitidos para dispositivos, incluindo dispositivos sem usuário, como quiosques (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Certificado SCEP** para perfil). Outras atualizações incluem:
- A propriedade **Assunto** em um perfil SCEP agora é uma caixa de texto personalizada e pode incluir novas variáveis. 
- A propriedade **Nome alternativo da entidade (SAN)** em um perfil SCEP agora é um formato de tabela e pode incluir novas variáveis. Na tabela, um administrador pode adicionar um atributo e preencher o valor em uma caixa de texto personalizada. A SAN será compatível com os seguintes atributos: 
  - DNS
  - Endereço de email
  - UPN

  Essas novas variáveis podem ser adicionadas com texto estático em uma caixa de texto de valor personalizada. Por exemplo, o atributo DNS pode ser adicionado como `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Os símbolos de chaves, ponto e vírgula e barra vertical “ { } ; | ” não funcionarão no texto estático da SAN. Apenas uma das novas variáveis de certificado do dispositivo a serem aceitas para `Subject` ou `Subject alternative name` devem ser colocadas entre chaves. 

Novas variáveis de certificado do dispositivo:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` funciona somente para dispositivos Windows e unidos ao domínio. 
>  -  Ao especificar propriedades do dispositivo, como IMEI, número de série e nome de domínio totalmente qualificado no assunto ou SAN para um certificado de dispositivo, esteja ciente de que essas propriedades podem ser falsificadas por uma pessoa com acesso ao dispositivo. 

[Criar um perfil de certificado SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) lista as variáveis atuais ao criar um perfil de configuração de SCEP. 

Aplica-se a: Windows 10 e posterior e iOS, com suporte para Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Bloquear remotamente dispositivos sem conformidade <!-- 2064495 -->
Quando um dispositivo não for compatível, será possível criar uma ação na política de conformidade que bloqueia o dispositivo remotamente. Em Intune > **Conformidade do dispositivo**, crie uma nova política ou selecione uma política de conformidade existente > **Propriedades**. Selecione **Ações em caso de não conformidade** > **Adicionar** e opte por bloquear remotamente o dispositivo.
Com suporte em: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 e posterior 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Melhorias no perfil de quiosque do Windows 10 e posterior no portal do Azure <!-- 2748224 -->
Essa atualização inclui as seguintes melhorias no perfil de configuração do dispositivo Windows 10 Kiosk (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Versão prévia do Quiosque** para o tipo de perfil): 
- Atualmente, você pode criar vários perfis de quiosque no mesmo dispositivo. Com essa atualização, o Intune dará suporte somente a um perfil de quiosque por dispositivo. Se você ainda precisar de vários perfis de quiosque em um único dispositivo, poderá usar um URI personalizado.
- Em um perfil de **Quiosque de vários aplicativos**, é possível selecionar o tamanho do bloco de aplicativos e a ordem do **layout do menu Iniciar** na grade de aplicativos. Se você preferir mais personalização, poderá fazer o upload de um arquivo XML.
- As configurações do navegador de quiosque serão movidas para as configurações de **Quiosque**. Atualmente, as configurações de **Navegador da Web de quiosque** têm sua categoria própria no Portal do Azure.
Aplica-se a: Windows 10 e posterior




### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Aplicar perfil do Autopilot a dispositivos Windows 10 registrados que ainda não estão registrados no Autopilot <!-- 1558983 -->
É possível aplicar perfis do Autopilot a dispositivos Windows 10 registrados que ainda não estiverem registrados no Autopilot. No perfil do Autopilot, escolha a opção **Converter todos os dispositivos de destino em Autopilot** para registrar automaticamente dispositivos não Autopilot no serviço de implantação do Autopilot. Aguarde 48 horas para que o registro seja processado. Quando o registro do dispositivo é cancelado e redefinido, o Autopilot o provisiona.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Criar e atribuir vários perfis de Página de Status de Registro a grupos do Azure AD <!-- 2526564 -->
Agora é possível [criar e atribuir](windows-enrollment-status.md) vários perfis de Página de status de registro a grupos do Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migração do Programa de registro de dispositivos para o Apple Business Manager no Intune <!--2748613-->
O ABM (Apple Business Manager) funciona no Intune, e você pode atualizar sua conta do DEP (Programa de registro de dispositivos) para o ABM. O processo no Intune é o mesmo. Para atualizar sua conta da Apple do DEP para o ABM, vá para [ https://support.apple.com/HT208817 ]( https://support.apple.com/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Guias de status de alerta e registro na página Visão geral do registro de dispositivos <!--2748656-->
Alertas e falhas de registro agora são exibidos em guias separadas na página de visão geral de registro do dispositivo.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Restringir aplicativos e bloquear o acesso a recursos da empresa em dispositivos Android <!-- 2451462  -->  
Na **Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android**  >  **Segurança do sistema**, há uma nova configuração na seção *Segurança do dispositivo*, chamada **Aplicativos restritos**. A configuração **Aplicativos restritos** usará uma política de conformidade para bloquear o acesso a recursos corporativos se determinados aplicativos forem instalados no dispositivo. O dispositivo é considerado não compatível até que os aplicativos restritos sejam removidos dele.
Aplica-se a: 
- Android

<!-- ########################### -->
## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]
