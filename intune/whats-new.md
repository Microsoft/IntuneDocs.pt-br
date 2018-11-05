---
title: O que há de novo no Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Conheça as novidades do portal do Intune no Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 800d044860a8a264facdeb49f1f59526ee53acdd
ms.sourcegitcommit: 7a649a5995600fb91817643e20a5565caedbb8f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50149114"
---
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Conheça as novidades de cada semana do Microsoft Intune. Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md). Alguns recursos podem ser implantados ao longo de várias semanas e podem não estar disponíveis para todos os clientes na primeira semana.

> [!Note]
> Para obter informações sobre a nova funcionalidade no MDM (gerenciamento de dispositivo móvel) híbrido, confira a [página de Novidades sobre o MDM híbrido](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->     
## <a name="week-of-october-22-2018"></a>Semana de 22 de outubro de 2018

### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Remover um perfil de email de um dispositivo, mesmo quando há apenas um perfil de email <!-- 1818139 -->
Anteriormente, não era possível remover um perfil de email de um dispositivo *quando* ele era o único perfil de email. Com essa atualização, esse comportamento foi alterado. Agora, você pode remover um perfil de email, mesmo que ele seja o único perfil de email no dispositivo. Confira [Adicionar configurações de email em dispositivos usando o Intune](email-settings-configure.md) para obter detalhes.

### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Remover certificados PKCS e SCEP de seus dispositivos <!-- 3218390 -->
Em alguns cenários, os certificados PKCS e SCEP permaneciam nos dispositivos, mesmo quando uma política era removida de um grupo, quando uma configuração ou implantação de conformidade era excluída ou quando um administrador atualizava um perfil de SCEP ou de PKCS existente. Essa atualização alterou esse comportamento. Há alguns cenários em que os certificados PKCS e SCEP são removidos dos dispositivos e alguns cenários em que eles permanecem no dispositivo. Confira [Remove SCEP and PKCS certificates in Microsoft Intune](remove-certificates.md) (Remover certificados SCEP e PKCS no Microsoft Intune) para conhecer esses cenários.

### <a name="powershell-module-for-intune--preview-available----wnready-951068---"></a>Módulo do PowerShell para Intune – Versão prévia disponível <!-- wnready 951068 -->
Um novo módulo do PowerShell, que dá suporte para a API do Intune por meio do Microsoft Graph, agora está disponível em versão prévia no [GitHub]( https://aka.ms/intunepowershell). Para obter detalhes de como usar esse módulo, confira o LEIAME nesse local. 

## <a name="week-of-october-15-2018"></a>Semana de 15 de outubro de 2018

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Solicitação de PIN ao alterar impressões digitais ou Face ID em um dispositivo iOS <!-- 2637704  -->
Os usuários agora são solicitados a inserir um PIN após fazerem alterações biométricas em seu dispositivo iOS. Isso inclui alterações em impressões digitais ou Face ID registradas. O tempo da solicitação depende da configuração do tempo limite em *Verificar novamente os requisitos de acesso após (minutos)*.  Quando não há um PIN definido, o usuário é solicitado a definir um. 
 
Esse recurso está disponível apenas para iOS e requer a participação de aplicativos que integram o SDK do aplicativo Intune para iOS, versão 9.0.1 ou posterior. A integração do SDK é necessária para que o comportamento possa ser aplicado aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. Alguns aplicativos que participam incluem WXP, Outlook, Managed Browser e Yammer.


## <a name="week-of-october-1-2018"></a>Semana de 1 de outubro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Acessar as propriedades de perfil-chave usando o aplicativo de portal da empresa <!-- 772203 -->
Os usuários finais já podem acessar as propriedades e ações da conta de chave de acesso, como redefinição de senha, do aplicativo Portal da Empresa. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Teclados de terceiros podem ser bloqueados por configurações de APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune podem bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivo. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>O acesso à conta de usuário de aplicativos do Intune em dispositivos Android e iOS gerenciados <!-- 1248496 -->
Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Política de configuração de aplicativo do Outlook para iOS e Android <!--1828527 -->
Agora você pode criar uma política de configuração de aplicativo do Outlook para iOS e Android para usuários locais que aproveitam a autenticação Básica com o protocolo ActiveSync. Outras configurações serão adicionadas à medida que forem habilitadas no Outlook para iOS e Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Extensões de arquivo de aplicativos de LOB (linha de negócios) do Windows <!-- 1884873 -->
As extensões de arquivo para aplicativos de LOB do Windows agora incluem *.msi*, *.appx*, *.appxbundle*, *.msix* e *.msixbundle*. Você pode adicionar um aplicativo no Microsoft Intune, selecionando **Aplicativos clientes** > **Aplicativos** > **Adicionar**. O painel **Adicionar aplicativo** é exibido permitindo que você selecione o **Tipo de aplicativo**. Para aplicativos de LOB do Windows, selecione aplicativo de **Linha de negócios** como o tipo de aplicativo, selecione o **Arquivo de pacote do aplicativo** e, em seguida, insira um arquivo de instalação com a extensão apropriada.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Implantação do aplicativo do Windows 10 usando o Intune <!-- 2309001 -->
Criado com base no suporte existente para aplicativos LOB (linha de negócios) e aplicativos Microsoft Store para Empresas, os administradores podem usar o Intune para implantar a maioria dos aplicativos existentes de sua organização nos usuários finais em dispositivos Windows 10. Os administradores podem adicionar, instalar e desinstalar aplicativos para usuários do Windows 10 em diversos formatos, como MSIs, Setup.exe ou MSP. O Intune avaliará as regras de requisitos antes de baixar e instalar, notificar os usuários finais do status ou dos requisitos de reinicialização usando a Central de Ações do Windows 10. Essa funcionalidade desbloqueará efetivamente organizações interessadas em deslocar essa carga de trabalho para o Intune e a nuvem. No momento, este recurso está em versão prévia pública e esperamos adicionar novas funcionalidades significativas a ele durante os próximos meses. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Dispositivo do usuário final e menu de contexto do aplicativo <!-- 2771453 -->
Os usuários finais agora podem usar o menu de contexto no dispositivo e aplicativos para disparar ações comuns, como renomear um dispositivo ou verificar a conformidade. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Atalhos de teclado do Portal da Empresa do Windows <!-- 2771518 -->
Os usuários finais agora poderão disparar ações de aplicativo e do dispositivo no Portal da Empresa do Windows usando atalhos de teclado (aceleradores).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Criar sufixos DNS em perfis de configuração de VPN em dispositivos que executam o Windows 10<!-- 1333668 -->
Quando você cria um perfil de configuração do dispositivo VPN (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **plataforma Windows 10 ou posterior** > O tipo de perfil **VPN**), insere algumas configurações de DNS. Com essa atualização, também é possível inserir vários **sufixos DNS** no Intune. Ao usar sufixos DNS, você pode procurar um recurso de rede usando o nome curto dele em vez do nome de domínio totalmente qualificado (FQDN). Essa atualização também permite alterar a ordem dos sufixos DNS no Intune.
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md#dns-settings) lista as configurações DNS atuais.
Aplica-se a: dispositivos Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Suporte para VPN sempre ativado em perfis de trabalho do Android <!-- 1333705 -->
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

Aplica-se a: Windows 10 e posterior e iOS, com suporte a Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Bloquear remotamente dispositivos não compatíveis <!-- 2064495 -->
Quando um dispositivo não for compatível, será possível criar uma ação na política de conformidade que bloqueia o dispositivo remotamente. Em Intune > **Conformidade do dispositivo**, crie uma nova política ou selecione uma política de conformidade existente > **Propriedades**. Selecione **Ações em caso de não conformidade** > **Adicionar** e opte por bloquear remotamente o dispositivo.
Com suporte em: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 e posterior 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Melhorias no perfil de quiosque em Windows 10 e posterior no Portal do Azure <!-- 2748224 -->
Essa atualização inclui as seguintes melhorias no perfil de configuração do dispositivo Windows 10 Kiosk (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Versão prévia do Quiosque** para o tipo de perfil): 
- Atualmente, você pode criar vários perfis de quiosque no mesmo dispositivo. Com essa atualização, o Intune dará suporte somente a um perfil de quiosque por dispositivo. Se você ainda precisar de vários perfis de quiosque em um único dispositivo, poderá usar um URI personalizado.
- Em um perfil de **Quiosque de vários aplicativos**, é possível selecionar o tamanho do bloco de aplicativos e a ordem do **layout do menu Iniciar** na grade de aplicativos. Se você preferir mais personalização, poderá fazer o upload de um arquivo XML.
- As configurações do navegador de quiosque serão movidas para as configurações de **Quiosque**. Atualmente, as configurações de **Navegador da Web de quiosque** têm sua categoria própria no Portal do Azure.
Aplica-se ao Windows 10 e posteriores




### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Aplicar perfil do Autopilot a dispositivos Windows 10 registrados que ainda não estiverem registrados no Autopilot <!-- 1558983 -->
É possível aplicar perfis do Autopilot a dispositivos Windows 10 registrados que ainda não estiverem registrados no Autopilot. No perfil do Autopilot, escolha a opção **Converter todos os dispositivos de destino em Autopilot** para registrar automaticamente dispositivos não Autopilot no serviço de implantação do Autopilot. Aguarde 48 horas para que o registro seja processado. Quando o registro do dispositivo é cancelado e redefinido, o Autopilot o provisiona.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Criar e atribuir vários perfis de Página de Status de Registro para grupos do Azure AD <!-- 2526564 -->
Agora é possível [criar e atribuir](windows-enrollment-status.md) vários perfis de Página de status de registro a grupos do Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migração do Programa de registro de dispositivos para o Apple Business Manager no Intune <!--2748613-->
O ABM (Apple Business Manager) funciona no Intune, e você pode atualizar sua conta do DEP (Programa de registro de dispositivos) para o ABM. O processo no Intune é o mesmo. Para atualizar sua conta da Apple do DEP para o ABM, vá para [ https://support.apple.com/en-us/HT208817 ]( https://support.apple.com/en-us/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Guias de status de alerta e registro na página de visão geral de registro do dispositivo <!--2748656-->
Alertas e falhas de registro agora são exibidos em guias separadas na página de visão geral de registro do dispositivo.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Restringir aplicativos e bloquear o acesso a recursos corporativos em dispositivos Android <!-- 2451462  -->  
Na **Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android**  >  **Segurança do sistema**, há uma nova configuração na seção *Segurança do dispositivo*, chamada **Aplicativos restritos**. A configuração **Aplicativos restritos** usará uma política de conformidade para bloquear o acesso a recursos corporativos se determinados aplicativos forem instalados no dispositivo. O dispositivo é considerado não compatível até que os aplicativos restritos sejam removidos dele.
Aplica-se a: 
- Android




## <a name="week-of-september-24-2018"></a>Semana de 24 de setembro de 2018

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centro de Administração do Gerenciamento de Dispositivo do Microsoft 365 <!-- 3078424 -->
Uma das promessas do Microsoft 365 é a administração simplificada e, com o passar dos anos, nós integramos os serviços de back-end do Microsoft 365 para fornecer cenários de ponta a ponta, como acesso condicional ao Intune e ao Microsoft Azure AD. O novo [Centro de Administração do Microsoft 365](http://devicemanagement.microsoft.com) é o lugar para consolidar, simplificar e integrar a experiência de administração. O workspace do especialista para Gerenciamento de Dispositivos fornece acesso fácil a todos os dispositivos e informações de gerenciamento de aplicativos e as tarefas que sua organização precisa. Esperamos que ele se torne o workspace de nuvem primária para as equipes de computação do usuário final corporativo.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Compatível com mais ACs (autoridades de certificação) de terceiros <!-- 3093107 -->
Usando o protocolo SCEP, agora você poderá emitir novos certificados e renovar certificados em dispositivos móveis usando Windows, iOS, Android e macOS.

### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>O Intune muda para dar suporte ao iOS 10 e posterior <!-- 2454656 -->  
Agora o registro do Intune, o Portal da Empresa e o navegador gerenciado dão suporte a dispositivos iOS que executam o iOS 10 e posterior. Para verificar se há dispositivos ou usuários afetados em sua organização, vá para o Intune no portal do Azure > **Dispositivos** > **Todos os dispositivos**. Filtre por sistema operacional e clique em **Colunas** para exibir os detalhes da versão do sistema operacional. Solicite que os usuários atualizem seus dispositivos para uma versão do sistema operacional com suporte.  

Se você tiver algum dos dispositivos listados abaixo ou desejar registrar algum deles, esteja ciente de que eles são compatíveis somente com o iOS 9 e versões anteriores.  Para continuar acessando o Portal da Empresa do Intune, atualize esses dispositivos para dispositivos que dão suporte ao iOS 10 ou posteriores:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3ª geração) 
* iPad Mini (1ª geração)  

## <a name="week-of-september-17-2018"></a>Semana de 17 de setembro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Remover a duplicação dos blocos de status de proteção de aplicativo <!-- 3083391 -->
Os blocos **Status do usuário para iOS** e **Status do usuário para Android** existiam nas páginas **Aplicativos Cliente – Visão geral** e **Aplicativos Cliente – Status de proteção do aplicativo**. Os blocos de status foram removidos da página **Aplicativos Cliente – Visão geral** para evitar a duplicação. 

## <a name="week-of-august-27-2018"></a>Semana de 27 de agosto de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Suporte de túnel de pacote para perfis VPN por aplicativo iOS para tipos de conexão personalizados e do Pulse Secure <!-- 1520957 -->
Ao usar um perfil VPN para cada aplicativo iOS, você pode escolher usar o túnel de camada de aplicativo (proxy de aplicativo) ou o túnel no nível do pacote (túnel de pacote). Essas opções estão disponíveis com os seguintes tipos de conexão:
- VPN personalizado
- Pulse Secure. Se você não tiver certeza de qual valor usar, confira a documentação do seu provedor VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Atraso quando as atualizações de software do iOS são mostradas no dispositivo <!-- 1949583 -->
Em Intune > **Atualizações de Software** > **Atualizar políticas do iOS**, você pode configurar os dias e horários em que não deseja que sejam instaladas atualizações nos dispositivos. Em uma atualização futura, você poderá atrasar quando uma atualização de software é mostrada visivelmente no dispositivo, de 1 a 90 dias. 
[Configurar políticas de atualização do iOS no Microsoft Intune](software-updates-ios.md) lista as configurações atuais.

#### <a name="office-365-proplus-version----2213968---"></a>Versão do Office 365 ProPlus <!-- 2213968 -->
Ao atribuir os aplicativos do Office 365 ProPlus a dispositivos Windows 10 usando o Intune, você poderá selecionar a versão do Office. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos** > **Adicionar Aplicativo**. Em seguida, selecione **Office 365 ProPlus Suite (Windows 10)** na lista suspensa **Tipo**. Selecione **Configurações do Pacote de Aplicativos** para exibir a folha associada. Defina o **Canal de Atualização** para um valor, como **Mensal**. Opcionalmente, remova outras versões do Office (msi) dos dispositivos de usuário final, selecionando **Sim**. Selecione **Específico** para instalar uma versão específica do Office para o canal selecionado em dispositivos de usuário final. Neste ponto, você pode selecionar a **Versão específica** do Office a ser usada. As versões disponíveis serão alteradas ao longo do tempo. Portanto, quando você cria uma nova implantação, as versões disponíveis podem ser mais recentes, e determinadas versões mais antigas podem não estar disponíveis. As implantações atuais continuarão a implantar a versão mais antiga, mas a lista de versões será atualizada continuamente por canal. Para mais informações, confira [Visão geral dos canais de atualização do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Suporte para registrar configuração de DNS para VPN do Windows 10 <!-- 2282852 -->
Com essa atualização, você pode configurar perfis VPN do Windows 10 para registrar dinamicamente os endereços IP atribuídos à interface VPN com o DNS interno, sem precisar usar perfis personalizados.
Para obter informações sobre as configurações de perfil VPN disponíveis, confira [Configurações de VPN do Windows 10](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>O instalador do Portal da Empresa do macOS agora inclui o número de versão no nome do arquivo instalador <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759-wnready---"></a>Atualizações automáticas de aplicativo iOS <!-- 2729759 wnready -->
As atualizações automáticas do aplicativo funcionam para aplicativos licenciados para o dispositivo e para o usuário no iOS versão 11.0 e posteriores.




### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>O Windows Hello será direcionado a usuários e dispositivos <!-- 1106609 -->
Quando você cria uma política do [Windows Hello para Empresas](windows-hello.md), ela se aplica a todos os usuários da organização (abrange o locatário). Com esta atualização, a política também pode ser aplicada a usuários ou dispositivos específicos usando uma política de configuração do dispositivo (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Proteção de Identidade** > **Windows Hello para Empresas**).
No Intune no portal do Azure, as configurações e definições do Windows Hello agora existem tanto em **Registro do dispositivo** quanto em **Configuração do dispositivo**. O **Registro de dispositivos** é direcionado a toda a organização (abrange o locatário) e dá suporte ao Windows Autopilot (OOBE). A **Configuração do dispositivo** é direcionada a usuários e dispositivos usando uma política que é aplicada durante o check-in.
Esse recurso aplica-se a:  
- Windows 10 e posterior
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Zscaler é uma conexão disponível para perfis VPN no iOS <!-- 1769858 -->
Quando você cria um perfil de configuração do dispositivo VPN no iOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** plataforma > Tipo de perfil **VPN**), há vários tipos de conexão, incluindo Cisco, Citrix e outros. Essa atualização adiciona o Zscaler como um tipo de conexão. 
[Configurações de VPN para dispositivos que executam o iOS](vpn-settings-ios.md) lista os tipos de conexão disponíveis.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Modo FIPS para perfis de Wi-Fi da empresa para Windows 10 <!-- 1879077 -->
Agora você pode habilitar o modo FIPS (padrão FIPS) para perfis de Wi-Fi da empresa para Windows 10 no portal do Azure do Intune. Verifique se o modo FIPS está habilitado na sua infraestrutura de Wi-Fi ao habilitá-lo em seus perfis de Wi-Fi.
[Configurações de Wi-Fi para dispositivos Windows 10 e posteriores no Intune](wi-fi-settings-windows.md) mostra como criar um perfil de Wi-Fi.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Controlar o modo S em dispositivos Windows 10 e posteriores – versão prévia pública <!-- 1958649 -->
Com essa atualização de recurso, você pode criar um perfil de configuração do dispositivo que tira um dispositivo Windows 10 do modo S ou impede que os usuários tirem o dispositivo do modo S. Esse recurso está no Intune > **Configuração do dispositivo** > **Perfis** >  **Windows 10 e posteriores** > **Atualização de edição e alternância de modo**.
[Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) (Introdução ao Windows 10 no modo S) fornece mais informações sobre o modo S.
Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pacote de configuração do Windows Defender ATP adicionado automaticamente ao perfil de configuração <!-- 2144658 -->
Ao usar a [Proteção Avançada contra Ameaças e integrar](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) dispositivos no Intune, você teve que baixar um pacote de configuração e adicioná-lo ao seu perfil de configuração. Com essa atualização, o Intune obtém automaticamente o pacote da Central de Segurança do Windows Defender e adiciona-o ao seu perfil.
Aplica-se ao Windows 10 e posteriores.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Exigir que os usuários se conectem durante a instalação do dispositivo <!--2311457-->
Agora você pode definir perfis de dispositivo para exigir que o dispositivo se conecte a uma rede antes de continuar, após a página Rede, durante a instalação do Windows 10. Embora esse recurso esteja na versão prévia, um Windows Insider build 1809 ou posterior é necessário para usar essa configuração.
Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Restringir aplicativos e bloquear o acesso aos recursos da empresa em dispositivos iOS e Android Enterprise <!-- 2451462 -->
Em **Conformidade de dispositivos** > **Políticas** > **Criar política** > **iOS** > **Segurança do Sistema**, há uma nova configuração **Aplicativos restritos**. Essa nova configuração usa uma política de conformidade para bloquear o acesso aos recursos da empresa quando determinados aplicativos estão instalados no dispositivo. O dispositivo é considerado não compatível até que os aplicativos restritos sejam removidos dele.
Aplica-se a: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Atualizações modernas de suporte a VPN para iOS <!-- 2459928, 1819876, and 2650856 -->
Essa atualização adiciona suporte aos seguintes clientes VPN do iOS: 
- F5 Access (versão 3.0.1 e posterior)
- SSO da Citrix
- GlobalProtect da Palo Alto Networks versão 5.0 e posterior Também nessa atualização:
- O tipo de conexão do **F5 Access** existente foi renomeado para **F5 Access Herdado** para iOS.
- O tipo de conexão **GlobalProtect da Palo Alto Networks** existente foi renomeado para **GlobalProtect da Palo Alto Networks (herdado)** para iOS.
Os perfis existentes com esses tipos de conexão continuam a funcionar com seus respectivos clientes VPN herdados. Se você estiver usando o Cisco AnyConnect Herdado, o F5 Access Herdado, a VPN da Citrix ou o GlobalProtect da Palo Alto Networks versão 4.1 e anteriores com o iOS, passe a usar os novos aplicativos. Faça isso assim que possível para garantir que o acesso VPN esteja disponível para dispositivos iOS após a atualização para o iOS 12.
Para obter mais informações sobre perfis VPN e o iOS 12, confira o [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806) (Blog da equipe de suporte do Microsoft Intune).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Exportar políticas de conformidade do Portal Clássico do Azure para recriar essas políticas no portal do Azure do Intune <!-- 2469637 -->
As políticas de conformidade criadas no Portal Clássico do Azure serão preteridas. Você pode examinar e excluir as políticas de conformidade existentes, no entanto, você não pode atualizá-las. Se você precisar migrar políticas de conformidade para o portal do Azure do Intune atual, exporte as políticas como um arquivo separado por vírgula (arquivo *.csv*). Em seguida, use os detalhes no arquivo para recriar essas políticas no portal do Azure do Intune.

> [!IMPORTANT]
> Quando o Portal Clássico do Azure for desativado, você não poderá mais acessar ou exibir suas políticas de conformidade. Portanto, exporte as políticas e recrie-as no portal do Azure antes que o Portal Clássico do Azure seja desativado.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile – novo parceiro de Defesa contra Ameaças Móveis <!-- 22662717 -->
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pela Better Mobile, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Bloquear o Portal da Empresa no modo de aplicativo único até a conexão do usuário <!--1067692 --> 
Caso você autentique um usuário por meio do Portal da Empresa e não pelo Assistente de Configuração durante o registro no DEP, haverá a opção de executar o Portal da Empresa no modo de aplicativo único. Essa opção bloqueia o dispositivo imediatamente depois que o Assistente de Configuração é concluído para que o usuário precise entrar para acessar o dispositivo. Esse processo garante que a integração do dispositivo seja concluída e ele não fique órfão em um estado sem nenhum usuário vinculado.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Atribuir um usuário e nome amigável a um dispositivo do Autopilot <!--1346521 -->
Agora você pode [atribuir um usuário a um único dispositivo do Autopilot](enrollment-autopilot.md). Os administradores também poderão atribuir nomes amigáveis para saudar o usuário durante a configuração do dispositivo com o Autopilot.
Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Usar licenças de dispositivo VPP para pré-provisionar o Portal da Empresa durante o registro no DEP <!-- 1608345 -->
Agora você pode usar licenças de dispositivo do VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante os registros no DEP (Programa de registro de dispositivos). Para fazer isso, quando você [criar ou editar um perfil de registro](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), especifique o token VPP que deseja usar para instalar o Portal da Empresa. Verifique se o token não expira e se você tem licenças suficientes para o aplicativo de Portal da Empresa. Caso o token for expirar ou for executado sem licenças, o Intune enviará por push o Portal da Empresa da App Store (uma ID da Apple será solicitada).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Confirmação necessária para excluir o token do VPP que está sendo usado para o pré-provisionamento do Portal da Empresa <!-- 2237634 -->
Agora será necessária uma confirmação para excluir um token do VPP (Volume Purchase Program) se ele estiver sendo usado para pré-provisionar o Portal da Empresa durante o registro no DEP.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Bloquear registros de dispositivos Windows pessoais <!-- 1849498 -->
Você pode [bloquear o registro de dispositivos pessoais do Windows](enrollment-restrictions-set.md#set-device-type-restrictions) no [gerenciamento de dispositivo móvel](windows-enroll.md) no Intune. Os dispositivos registrados com o [agente Intune PC](manage-windows-pcs-with-microsoft-intune.md) não podem ser bloqueados com esse recurso. Esse recurso será implantado nas próximas semanas, portanto, talvez você não o veja imediatamente na interface do usuário.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Especificar os padrões de nome de computador em um perfil do Autopilot <!--1849855-->
Você pode [especificar um modelo de nome do computador](enrollment-autopilot.md#create-an-autopilot-deployment-profile) para gerar e definir o [nome do computador](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) durante o registro do Autopilot. Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Ocultar as opções de alteração de conta na página de entrada e na página de erro de domínio da empresa <!--1901669 --> para os perfis do Windows Autopilot
Há [novas opções de perfil do Windows Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile) para os administradores ocultarem as opções de alteração de conta nas páginas de entrada e de erro de domínio da empresa. Para ocultar essas opções, é necessário configurar uma Identidade Visual da Empresa no Azure Active Directory. Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).



### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="delete-jamf-devices----2653306--"></a>Excluir dispositivos do Jamf <!-- 2653306-->
Você pode excluir os dispositivos gerenciados pelo JAMF, acessando **Dispositivos** > escolha o dispositivo JAMF > **Excluir**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Alterar a terminologia para "desativar" e "apagar" <!-- 2175759 -->
Para ficar consistente com a API do Graph, os termos a seguir foram alterados na documentação e na interface do usuário do Intune:
- **Remover dados da empresa** será alterado para "desativar"
- **Redefinição de fábrica** será alterado para **apagar**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Caixa de diálogo de confirmação se administrador tentar excluir o MDM Push Certificate <!-- 297909500-->
Se alguém tentar excluir um Apple MDM Push Certificate, uma caixa de diálogo de confirmação exibirá o número de dispositivos iOS e macOS relacionados. Se o certificado for excluído, esses dispositivos precisarão ser registrados novamente.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Configurações de segurança adicionais para o Windows Installer <!-- 2282430 -->
Você pode permitir que os usuários controlem as instalações de aplicativos. Se habilitadas, as instalações que, de outra forma, poderiam ser interrompidas devido a uma violação de segurança teriam permissão para continuar. Você pode direcionar o Windows Installer para usar permissões elevadas quando ele instalar algum programa em um sistema. Além disso, você pode habilitar itens de WIP (Proteção de Informações do Windows) a serem indexados e os metadados sobre eles armazenados em um local não criptografado. Quando a política é desabilitada, os itens protegidos pela WIP não são indexados e não aparecem nos resultados na Cortana ou no Explorador de Arquivos. A funcionalidade para essas opções está desabilitada por padrão. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968 -->
Nós adicionamos novos recursos ao site Portal da Empresa, com base nos comentários dos clientes. Você usufruirá de uma melhoria significativa nas funcionalidades existentes e na usabilidade dos seus dispositivos. As áreas do site, como detalhes do dispositivo, comentários e suporte e visão geral do dispositivo, receberam um design novo, moderno e responsivo. Você também verá:

- Fluxos de trabalho simplificados em todas as plataformas de dispositivo
- Fluxos de identificação e registro de dispositivo aprimorados
- Mensagens de erro mais úteis
- Linguagem mais amigável, menos jargão técnico
- Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos
- Maior acessibilidade para todos os usuários  

A [documentação do site Portal da Empresa do Intune](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) foi atualizada para refletir essas alterações. Para ver um exemplo das melhorias do aplicativo, confira [Atualizações da interface do usuário para aplicativos de usuário final do Intune](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Detecção avançada de jailbreak em relatórios de conformidade<!-- 2198738 -->
Os estados da configuração de detecção avançada de jailbreak agora aparecem em todos os relatórios de conformidade no console do administrador.

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-for-policies---1081974---"></a>Marcas de escopo para políticas <!--1081974 -->
Você pode [criar marcas de escopo](scope-tags.md) para limitar o acesso aos recursos do Intune. Adicione uma marca de escopo a uma atribuição de função e, em seguida, adicione a marca de escopo a um perfil de configuração. A função só terá acesso a recursos com perfis de configuração que tenham marcas de escopo correspondentes (ou nenhuma marca de escopo).

## <a name="week-of-august-14-2018"></a>Semana de 14 de agosto de 2018

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>suporte do macOS para o Programa de Registro de Dispositivo da Apple <!-- 747651 -->
O Intune agora dá suporte ao registro de dispositivos macOS no DEP (Programa de Registro de Dispositivos) da Apple. Para obter mais informações, veja [Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos da Apple](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>Semana de 23 de julho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Suporte para aplicativo de LOB (linha de negócios) do macOS <!-- 1895847 -->
O Microsoft Intune permite que aplicativos de LOB para macOS sejam implantados como **Obrigatório** ou **Disponível com registro**. Os usuários finais podem obter aplicativos implantados como **Disponível** usando o Portal da Empresa para macOS ou o [site do Portal da Empresa](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Suporte de aplicativo nativo do iOS para o modo de quiosque <!-- 2051098 -->
Além dos Aplicativos da Loja e dos Aplicativos Gerenciados, agora você pode selecionar um Aplicativo Nativo (por exemplo, o Safari) que é executado no modo de quiosque em um dispositivo iOS.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Editar suas implantações de aplicativo do Office 365 Pro Plus <!-- 2150145 -->
Como administrador do Microsoft Intune, você tem maior capacidade para editar suas implantações de aplicativo do Office 365 Pro Plus. Além disso, não é mais necessário excluir as implantações para alterar uma das propriedades do pacote. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Aplicativos**. Na lista de aplicativos, selecione o Pacote Office 365 Pro Plus.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>A atualização do SDK do Aplicativo do Intune para Android já está disponível <!-- 2744271-->

Uma versão atualizada do SDK do Aplicativo do Intune está disponível para fornecer suporte aos lançamentos da plataforma Android. Se você é um desenvolvedor de aplicativos e usa o SDK do Intune para Android, instale a versão atualizada do SDK do Aplicativo do Intune para garantir que a funcionalidade do Intune nos aplicativos Android continue viável, como esperado nos dispositivos da plataforma Android. Esta versão do SDK do Aplicativo do Intune fornece um plug-in interno que executa as atualizações do SDK. Não é necessário reescrever códigos existentes que estejam integrados. Para saber mais, confira [SDK do Intune para Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Se estiver usando o estilo de notificação anterior do Intune, recomendamos usar o ícone de porta-arquivos. Para saber mais sobre identidade visual, confira [este repositório do GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Usar S/MIME para criptografar e assinar vários dispositivos de um usuário  <!-- 1333642 -->
Essa atualização inclui uma criptografia de email S/MIME usando um novo perfil de certificado importado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > selecionar a plataforma > tipo de perfil **Certificado PKCS importado**). No Intune, você pode importar certificados no formato PFX. Em seguida, o Intune pode fornecer os mesmos certificados para vários dispositivos registrados por um único usuário. Isso também inclui:

- O perfil de email do iOS nativo permite habilitar a criptografia S/MIME usando certificados importados no formato PFX.
- O aplicativo de email nativo em dispositivos Windows Phone 10 usam automaticamente o certificado S/MIME.
- Os certificados privados podem ser entregues em várias plataformas. Porém, nem todos os aplicativos de email são compatíveis com S/MIME.
- Em outras plataformas, talvez você precise configurar manualmente o aplicativo de email para habilitar o S/MIME.  
- Os aplicativos de email compatíveis com a criptografia S/MIME podem manipular a recuperação de certificados para criptografia de email S/MIME de uma maneira com a qual o MDM não é compatível, como a leitura do repositório de certificados do editor.

Compatível com: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Criar política de conformidade do dispositivo usando as configurações do Firewall em dispositivos macOS <!-- 1497640 -->
Quando você cria uma política de conformidade do macOS (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Plataforma: macOS** > **Segurança do sistema**), há algumas novas configurações de **Firewall** disponíveis: 

- **Firewall**: configure como conexões de entrada são tratadas em seu ambiente.
- **Conexões de entrada**: **Bloquear** todas as conexões de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Essa configuração também bloqueia todos os serviços de compartilhamento.
- **Modo Furtivo**: **Habilite** o modo furtivo para impedir que o dispositivo responda a solicitações de investigação. O dispositivo continua a responder a solicitações de entrada para aplicativos autorizados.

Aplica-se a: macOS 10.12 e posteriores

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Novo perfil de configuração de dispositivo de Wi-Fi para Windows 10 e posterior <!-- 1879077 -->
No momento, você pode importar e exportar perfis de Wi-Fi usando arquivos XML. Com essa atualização, você pode criar um perfil de configuração de dispositivo de Wi-Fi diretamente no Intune, como em algumas outras plataformas.

Para criar o perfil, abra **Configuração do dispositivo** > **Perfis** > **Criar Perfil** > **Windows 10 e posteriores** > **Wi-Fi**. 

Aplica-se ao Windows 10 e posteriores.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Quiosque – obsoleto, está esmaecido e não pode ser alterado <!-- 2149998 -->
O [Recurso de quiosque](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** > **Restrições do dispositivo**) está obsoleto e foi substituído por [Configurações de quiosque para o Windows 10 e posterior](kiosk-settings.md). Com essa atualização, o recurso **Quiosque – obsoleto** fica esmaecido e a interface do usuário não pode ser alterada nem atualizada. 

Para habilitar o modo de quiosque, confira [Configurações de quiosque para Windows 10 e posteriores](kiosk-settings.md).

Aplica-se ao Windows 10 e posteriores, Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>APIs para usar autoridades de certificação de terceiros <!-- 2184013 -->
Nesta atualização, há uma API Java que permite a integração das autoridades de certificação de terceiros ao Intune e ao SCEP. Assim, os usuários poderão adicionar o certificado SCEP a um perfil e aplicá-lo aos dispositivos usando o MDM.

Atualmente, o Intune permite [Solicitações SCEP usando serviços de certificados do Active Directory](certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Alternar para mostrar ou não mostrar o botão Encerrar Sessão em um navegador de quiosque <!-- 2455253 -->
Agora você pode configurar se os navegadores de Quiosque mostram ou não o botão Encerrar Sessão. Veja o controle em **Configuração do dispositivo** > **Quiosque (versão prévia)** > **Navegador da Web de quiosque**. Se estiver habilitado, quando um usuário clicar no botão, o aplicativo solicitará uma confirmação para encerrar a sessão. Quando confirmado, o navegador limpa todos os dados de navegação e navega novamente para a URL padrão.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Criar um perfil de configuração de celular do eSIM <!-- 2564077 -->
Em **Configuração do dispositivo**, você pode criar um perfil de celular eSIM. É possível importar um arquivo contendo os códigos de ativação de celular fornecidos pela operadora do dispositivo móvel. Em seguida, você pode implantar esses perfis nos dispositivos Windows 10 habilitados para eSIM LTE, como o Surface Pro LTE e outros dispositivos compatíveis com eSIM.

Verifique se seus [dispositivos são compatíveis com perfis de eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Aplica-se ao Windows 10 e posteriores. 




### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Marcar automaticamente os dispositivos Android registrados usando o Registro de Dispositivo Móvel do Samsung Knox como "corporativo". <!-- 2404851 -->
Por padrão, agora os dispositivos Android registrados usando o Registro de Dispositivo Móvel do Samsung Knox são marcados como **corporativos** em **Propriedade do Dispositivo**. Você não precisa identificar manualmente os dispositivos corporativos usando o IMEI nem os números de série antes de se registrar usando o Registro de Dispositivo Móvel do Knox.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Excluir em massa os dispositivos na folha de dispositivos <!-- 1793693 -->

Agora você pode excluir vários dispositivos ao mesmo tempo na folha Dispositivos. Escolha **Dispositivos** > **Todos os dispositivos** > selecione os dispositivos que deseja excluir > **Excluir**. Para dispositivos que não podem ser excluídos, um alerta será exibido.

## <a name="week-of-july-16-2018"></a>Semana de 16 de julho de 2018  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Mais oportunidades de sincronização no aplicativo do Portal da Empresa para o Windows  
O aplicativo do Portal da Empresa para Windows agora permite que você inicie uma sincronização diretamente na barra de tarefas do Windows e no menu Iniciar. Esse recurso é especialmente útil se a única tarefa é sincronizar dispositivos e obter acesso a recursos corporativos. Para acessar o novo recurso, clique com o botão direito do mouse no ícone do Portal da Empresa fixado na barra de tarefas ou no menu Iniciar. Nas opções de menu (também conhecidas como lista de atalhos), selecione **Sincronizar este dispositivo**. O Portal da Empresa será aberto na página **Configurações** e iniciará a sincronização. Para ver a nova funcionalidade, confira [Novidades da interface do usuário](whats-new-app-ui.md).   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Novas experiências de navegação no aplicativo do Portal da Empresa para o Windows  

Agora, ao navegar ou pesquisar aplicativos no aplicativo do Portal da Empresa para o Windows, você pode alternar entre a exibição **Blocos** existente e a exibição **Detalhes** recém-adicionada. A nova exibição lista detalhes do aplicativo, como nome, fornecedor, data de publicação e status da instalação.  

A exibição **Instalados** da página **Aplicativos** permite que você veja detalhes sobre as instalações de aplicativos concluídas e em andamento. Para ver a aparência da nova exibição, confira [Novidades da interface do usuário](whats-new-app-ui.md).  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Melhoria na experiência do aplicativo do Portal da Empresa para os gerentes de registros de dispositivo  
Quando um DEM (gerenciador de registros de dispositivo) entrar no aplicativo do Portal da Empresa para Windows, agora o aplicativo listará apenas o dispositivo em execução atual do DEM. Essa melhoria reduzirá os tempos limite que ocorriam quando o aplicativo tentava mostrar todos os dispositivos registrados pelo DEM.  


## <a name="week-of-july-9-2018"></a>Semana de 9 de julho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquear acesso do aplicativo com base em modelos e fornecedores de dispositivos não aprovados <!-- 1425689 ! -->
O administrador de TI do Intune pode impor uma lista especificada de fabricantes Android e/ou modelos de iOS por meio das Políticas de Proteção de Aplicativo do Intune. O administrador de TI pode fornecer uma lista separada por ponto e vírgula de fabricantes para políticas do Android e de modelos de dispositivos para políticas do iOS. As Políticas de Proteção de Aplicativo do Intune servem apenas para Android e iOS. Há duas ações separadas que podem ser executadas nessa lista especificada:
- Um bloqueio de acesso do aplicativo em dispositivos que não estão especificados.
- Ou uma limpeza seletiva de dados corporativos em dispositivos que não estão especificados. 

O usuário não conseguirá acessar o aplicativo direcionado se os requisitos por meio da política não forem atendidos. Com base nas configurações, o usuário pode ser bloqueado ou passar por uma limpeza seletiva dos dados corporativos no aplicativo. Em dispositivos iOS, esse recurso exige a participação de aplicativos (tais como WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune para que esse recurso seja imposto aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. No Android, esse recurso exige a versão mais recente do Portal da Empresa. 

Em dispositivos de usuário final, o cliente do Intune executará uma ação com base em uma correspondência simples das cadeias de caracteres especificadas na folha do Intune para Políticas de Proteção de Aplicativo. Isso depende totalmente do valor informado pelo dispositivo. Por isso, o administrador de TI é incentivado a garantir que o comportamento desejado seja preciso. Isso pode ser feito testando essa configuração com base em vários fabricantes e modelos de dispositivo direcionados a um grupo de usuários pequeno. No Microsoft Intune, selecione **Aplicativos clientes** > **Políticas de proteção de aplicativo** para exibir e adicionar as políticas de proteção de aplicativo. Para obter mais informações sobre as políticas de proteção de aplicativo, consulte [Quais são as políticas de proteção de aplicativo](app-protection-policy.md) e [Apagar dados seletivamente usando ações de acesso da política de Proteção de Aplicativo no Intune](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Acesso ao build de pré-lançamento do Portal da Empresa do macOS <!-- 1734766 -->
Usando o Microsoft AutoUpdate, você pode inscrever-se para receber os builds antecipadamente ao ingressar no Programa Insider. A inscrição permite que você use o Portal da Empresa atualizado antes que ele esteja disponível para seus usuários finais. Para obter mais informações, veja o [Blog do Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## <a name="week-of-july-2-2018"></a>Semana de 2 de julho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Monitorar o status de configuração de aplicativo do iOS por dispositivo <!-- 880037 -->
Como administrador do Microsoft Intune, você pode monitorar o status de configuração de aplicativo do iOS para cada dispositivo gerenciado. No **Microsoft Intune**, no portal do Azure, selecione **Dispositivos** > **Todos os dispositivos**. Na lista de dispositivos gerenciados, selecione um dispositivo específico para exibir uma folha para o dispositivo. Na folha do dispositivo, selecione **Configuração de aplicativo**.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Ações de acesso para políticas de proteção de aplicativo <!-- 1483510 -->
Você pode configurar políticas de proteção de aplicativo para apagar, bloquear ou avisar explicitamente os dispositivos não compatíveis. A ação *apagar* remove os dados corporativos de um dispositivo. Se ocorrer uma limpeza, o usuário do dispositivo receberá uma notificação sobre o motivo dela e as etapas de remediação. Para algumas configurações, como a versão mínima do sistema operacional, você poderá aplicar várias ações, como bloquear e apagar. Observe que essas ações são disparadas quando o aplicativo é iniciado.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Apagamento seletivo de dados de aplicativo da organização <!-- 1507030 -->
Agora os administradores podem configurar um apagamento seletivo de dados da organização como uma nova ação quando as condições de configurações de Acesso APP (Políticas de Proteção do Aplicativo) não forem atendidas.  Esse recurso ajuda os administradores a proteger e remover automaticamente dados confidenciais de empresa de aplicativos com base em critérios previamente configurados.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Revogar um aplicativo iOS adquirido por meio do VPP <!-- 1777384 -->
Como administrador do Microsoft Intune, você pode revogar as licenças para um aplicativo iOS selecionado adquirido por meio do VPP (programa de compra de volume). Você pode notificar os usuários quando um aplicativo licenciado pelo usuário não estiver mais atribuído a eles. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. A contagem de licenças recuperadas será refletida no nó **Aplicativos Licenciados** na carga de trabalho de **Aplicativo** do Intune. Para obter mais informações relacionadas a aplicativos VPP iOS, veja [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Atualizações nas mensagens que indicam a não conformidade no aplicativo do Portal da Empresa <!-- 1832222 -->
Revisamos as mensagens que são exibidas para os usuários de dispositivos quando um dispositivo está fora de conformidade. As mensagens mantêm seus significados originais, mas foram atualizadas com uma linguagem mais amigável e menos técnica. Também atualizamos os links para as etapas de correção e a documentação para mantê-los atualizados.
Os seguintes textos anterior e posterior são um exemplo das melhorias no sistema de mensagens que você verá:
- **Antes**: *Este dispositivo não contatou o serviço Intune no período especificado exigido pelo administrador de TI. Para resolver esse problema, abra o aplicativo do Portal da Empresa em seu dispositivo e clique no botão Verificar Conformidade.*
- **Depois**: *Seu dispositivo não faz check-in na organização há algum tempo. Para restabelecer a conexão, abra o aplicativo do Portal da Empresa no dispositivo e toque em Verificar Configurações no dispositivo.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>Revogar a licença de aplicativo VPP iOS <!-- 1863797 -->
Como administrador, você pode recuperar uma licença de aplicativo de VPP iOS atribuída a um usuário ou dispositivo. Desinstalar um aplicativo VPP iOS também permitirá que você recupere a licença do aplicativo. Antes de desinstalar o aplicativo, o usuário ou o dispositivo precisa ser removido do grupo ao qual o aplicativo é direcionado. A remoção do usuário ou dispositivo do grupo evita a reinstalação do aplicativo. Depois de concluir essas etapas, você pode optar por atribuir a licença do aplicativo a outro usuário ou dispositivo. Para obter mais informações sobre licenças de aplicativo VPP iOS, consulte [Gerenciar aplicativos adquiridos por volume do iOS no Microsoft Intune](vpp-apps-ios.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Selecione as categorias de dispositivo usando as configurações de Acesso Corporativo ou de Estudante <!-- 1058963 eenotready --> 
Se você tiver habilitado o [mapeamento do grupo de dispositivos](https://docs.microsoft.com/intune/device-group-mapping), os usuários no Windows 10 passarão a receber uma solicitação para selecionar uma categoria de dispositivo após o registro por meio do botão **Conectar** em **Configurações** > **Contas** > **Acesso corporativo ou de estudante**. 

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

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Suporte para perfis de VPN GlobalProtect da Palo Alto Networks <!-- 1333680 ! -->
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

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nova configuração de idioma/região ao configurar o OOBE para Autopilot <!-- 1821766 -->
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

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>Desinstale a versão mais recente das atualizações de software do Windows 10 <!-- 1732948 -->
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
O navegador Microsoft Edge para dispositivos móveis (iOS e Android) agora é compatível com as políticas de proteção de aplicativo do Microsoft Intune. Os usuários de dispositivos iOS e Android que entrarem com suas contas corporativas do Azure AD no aplicativo Edge estarão protegidos pelo Intune. Em dispositivos iOS, a política **Exigir navegador gerenciado para conteúdo da Web** permitirá aos usuários abrir links no Microsoft Edge quando ele for gerenciado.

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
O Microsoft Intune oferecerá a capacidade de instalar aplicativos de LOB macOS do Portal do Azure. Você poderá adicionar um aplicativo de LOB macOS ao Intune depois de ele ter sido previamente processado pela ferramenta disponível no GitHub. No portal do Azure, escolha **Aplicativos clientes** na folha **Intune**. Na folha **Aplicativos clientes**, escolha **Aplicativos** > **Adicionar**. Na folha **Adicionar Aplicativo**, selecione **Aplicativo de linha de negócios**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Grupos Todos os Usuários e Todos os Dispositivos internos para atribuição de aplicativo de perfil de trabalho do Android Enterprise <!-- 1813073 -->
É possível aproveitar os grupos internos **Todos os Usuários** e **Todos os Dispositivos** para a atribuição de aplicativos de perfil de trabalho do Android Enterprise. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>O Intune reinstalará os aplicativos necessários que são desinstalados pelos usuários <!-- 1947010 -->
Se um usuário final desinstalar um aplicativo obrigatório, o Intune reinstalará automaticamente o aplicativo em até 24 horas, em vez de aguardar o ciclo de reavaliação de 7 dias.

### <a name="device-configuration"></a>Configuração do dispositivo

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>A lista de status e gráfico de perfil do dispositivo mostra todos os dispositivos em um grupo <!-- 1449153 -->
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

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Mostrar as informações sobre a chamada no perfil pessoal – Perfil de trabalho do Android Enterprise <!--1098984 -->
Ao usar um perfil pessoal em um dispositivo, os usuários finais poderão não ver os detalhes das informações sobre a chamada de um contato de trabalho. 

Com essa atualização, há uma nova configuração em **Android Enterprise** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
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
  - **Inicialização segura com DMS (Acesso direto à memória)**: ativa a VBS com inicialização segura e acesso direto à memória. A proteção de DMA exige suporte de hardware e é habilitada somente em dispositivos configurados corretamente. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Use um nome de entidade personalizado no certificado SCEP <!-- 2064190 -->
Você pode usar o nome comum **OnPremisesSamAccountName** em uma entidade personalizada em um perfil de certificado SCEP. Por exemplo, você pode usar `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Bloquear câmera e capturas de tela nos perfis de trabalho do Android Enterprise <!-- 1098977 -->
Duas novas propriedades estão disponíveis para bloqueio quando você configurar as restrições de dispositivo para dispositivos Android: 
- Câmera: bloqueia o acesso a todas as câmeras no dispositivo
- Captura de tela: bloqueia a captura de tela e também impede que o conteúdo seja mostrado em dispositivos de exibição que não tenham uma saída de vídeo segura

Se aplica a perfis de trabalho do Android Enterprise.


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Novas etapas de registro para usuários em dispositivos com macOS High Sierra 10.13.2+ <!--1734567 -->
O macOS High Sierra 10.13.2 introduziu o conceito de registro do MDM "Aprovado pelo Usuário". As inscrições aprovadas permitem que o Intune gerencie algumas configurações sensíveis de segurança. Para obter mais informações, consulte a documentação de suporte da Apple aqui: https://support.apple.com/HT208019.

Dispositivos registrados usando o Portal da Empresa macOS são considerados "Não Aprovados pelo Usuário", a menos que o usuário final abra as Preferências do Sistema e dê manualmente sua aprovação. Para esse fim, o Portal da Empresa macOS agora direciona os usuários em macOS 10.13.2 e acima e aprovar manualmente o registro no final do processo de registro. O console do administrador do Intune relatará se um dispositivo registrado for aprovado pelo usuário.



### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>A Proteção Avançada contra Ameaças (ATP) e o Intune estão totalmente integrados <!-- 1629303 -->

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
O aplicativo do Portal da Empresa do Intune para Windows 10 foi atualizado com a [exibição de navegação do Fluent Design System](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). No lado do aplicativo, você verá uma lista estática e vertical de todas as páginas de nível superior. Clique em qualquer link para exibir e alternar rapidamente entre as páginas. Esta é a primeira de várias atualizações que você verá como parte de nosso esforço contínuo de criar uma experiência mais adaptável, intuitiva e familiar no Intune. Para ver a aparência atualizada, vá para [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Semana de 16 de abril de 2018

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Usar o cliente do Cisco AnyConnect para iOS <!-- 1333708 -->

Quando você cria um novo perfil de VPN para iOS, agora há duas opções: **Cisco AnyConnect** e **Cisco Legacy AnyConnect**. Os perfis do Cisco AnyConnect 4.0.7x são compatíveis com o 4.0.7x e versões mais recentes. Os perfis existentes de VPN do Cisco AnyConnect do iOS são rotulados como **Cisco Legacy AnyConnect** e continuarão a funcionar com o Cisco AnyConnect 4.0.5x e versões anteriores, como fazem atualmente.

> [!NOTE]
> Essa alteração se aplica apenas ao iOS. Continuará existindo apenas uma opção do Cisco AnyConnect para os perfis de trabalho do Android Enterprise, Android e plataformas do macOS.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Os dispositivos macOS registrados em Jamf já podem se registrar no Intune <!-- 2370684 -->

As versões 1.3 e 1.4 do portal da empresa do macOS não registraram com êxito os dispositivos Jamf no Intune. A versão 1.4.2 do portal do macOS corrige esse problema.


## <a name="week-of-april-9-2018"></a>Semana de 9 de abril de 2018  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Experiência de ajuda atualizada no aplicativo Portal da Empresa para Android <!-- 1631531 -->

Nós atualizamos a experiência da ajuda no aplicativo Portal da Empresa para Android com base nas práticas recomendadas para a plataforma Android. Agora, quando os usuários encontram um problema no aplicativo, eles poderão tocar em **Menu** > **Ajuda** e:
- Faça o upload dos de diagnóstico para a Microsoft.
- Envie um email que descreva a ID do problema e do incidente para um profissional de suporte da empresa.  

Para conferir a experiência de ajuda atualizada, acesse [Enviar logs usando o email](/intune-user-help/send-logs-to-your-it-admin-by-email-android) e [Enviar erros à Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Novo gráfico de tendência de falha de registro e tabela de motivos de falhas<!-- 1471783 -->

Na página Visão Geral do Registro, você poderá exibir a tendência de falhas de registro e as cinco principais causas de falhas. Ao clicar no gráfico ou na tabela, você poderá fazer uma busca detalhada nos detalhes para encontrar recomendações de solução de problemas e sugestões de correção.

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
Agora você pode usar a APP (Proteção de Política do Aplicativo) do Intune e o AC (Acesso Condicional) para proteger o acesso a dados do Exchange no Local com o Outlook Mobile. Para adicionar ou modificar uma política de proteção de aplicativo no portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Políticas de proteção de aplicativo**. Antes de usar esse recurso, verifique se você atende aos [requisitos do Outlook para iOS e Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="notices"></a>Avisos

### <a name="plan-for-change-intune-will-move-to-support-macos-1012-and-higher-in-december---2970975--"></a>Programe-se para a mudança: o Intune mudará para oferecer compatibilidade com o macOS 10.12 e posterior em dezembro <!--2970975--> 

A Apple acaba de lançar o macOS 10.14. Posteriormente, o Intune mudará para oferecer compatibilidade com o macOS 10.12 e posterior em dezembro de 2018. 

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?

A partir de dezembro, os usuários finais em dispositivos com macOS 10.11 e versões anteriores não poderão usar o Portal da Empresa para registrar-se no Intune. Eles precisarão atualizar os dispositivos para o macOS 10.12 ou posterior e o aplicativo do Portal da Empresa para a versão mais recente para continuar a receber suporte e novos recursos. 

Atualmente, o macOS 10.12 e versões posteriores são compatíveis com: 
- MacBook (fim de 2009 ou mais recente). 
- iMac (fim de 2009 ou mais recente)
- MacBook Air (fim de 2010 ou mais recente).  
- MacBook Pro (fim de 2010 ou mais recente). 
- Mac Mini (fim de 2010 ou mais recente). 
- Mac Pro (fim de 2010 ou mais recente). 

Depois de dezembro, os usuários finais que têm dispositivos diferentes dos listados acima não poderão acessar a versão mais recente do aplicativo do Portal da Empresa para macOS. Os dispositivos registrados no momento que executam versões incompatíveis anteriores ao macOS 10.12 continuarão a ser gerenciados e listados no Console de Administração do Intune.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?

- Solicite que os usuários finais atualizem os dispositivos deles para uma versão de sistema operacional compatível antes de dezembro de 2018. 
- Verifique os relatórios do Intune no console do Intune no Azure para ver quais dispositivos ou usuários serão afetados. Acesse Dispositivos > Todos os dispositivos e filtre por sistema operacional. É possível adicionar colunas extras para ajudar a identificar quem na sua organização tem dispositivos que executam o macOS 10.11. 
- Se você estiver usando o MDM (gerenciamento de dispositivo móvel), acesse Ativos e Conformidade > Dispositivos no console do Configuration Manager, clique com o botão direito do mouse nas colunas para adicionar as colunas de Sistema Operacional e Versão do Cliente e ordene por sistema operacional. Observe que o MDM híbrido foi preterido, e você precisa mudar para o Intune no Azure o mais breve possível. 
 
#### <a name="additional-information"></a>Informações adicionais
Para obter mais informações, confira [Registrar seu dispositivo macOS no Intune com o aplicativo Portal da Empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).
 

### <a name="plan-for-change-new-intune-support-experience-for-premier-customers"></a>Plano de mudança: experiência de suporte do Intune para clientes do Premier 
Como um cliente do Premier da Microsoft, atualmente você pode usar o portal do Microsoft Premier Online (MPO) (premier.microsoft.com) e o Intune no Azure (portal.azure.com) para criar solicitações de suporte do Intune. A partir de 3 de dezembro de 2018, para continuar aprimorando a experiência de suporte do Premier, você poderá criar solicitações de suporte apenas no Intune no Azure.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Após 3 de dezembro, não será possível criar solicitações de suporte no MPO.  Ao tentar fazer isso, você verá um prompt que não poderá ignorar, para ser redirecionado ao Intune no Azure. Lá, é possível criar uma solicitação de suporte que será encaminhada ao Suporte da Microsoft dedicado ao Intune para diagnosticar e resolver o problema de maneira oportuna. As solicitações de suporte criadas no portal do MPO não podem ser exibidas no Portal do Azure, portanto, interrompa a criação de solicitações de suporte no MPO.  

Se você usa o gerenciamento de dispositivo móvel híbrido (MDM híbrido) ou o cogerenciamento, pode continuar a usar o MPO para criar solicitações de suporte para o ConfigMgr, mas usar o Portal do Azure para criar solicitações de suporte do Intune. Como lembrete, o MDM híbrido é preterido, e você deve planejar a migração para o Intune no Azure assim que possível. Para obter mais informações, confira [Migrar do Gerenciamento de Dispositivo Móvel Híbrido para o Intune no Azure](https://aka.ms/hybrid_notification).

Observe que apenas os usuários com funções de Administrador Global, de Administrador de Serviços do Intune e de Administrador de Suporte de Serviço podem criar tíquetes de suporte no portal do Azure.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
- Pare de usar o MPO e use o Intune no Azure para criar e gerenciar todas as suas solicitações de suporte do Intune.  
- Notifique a assistência técnica e atualize a documentação, se necessário.
- Se houver usuários sem funções de Administrador global ou Administrador de serviços do Intune criando solicitações de suporte no MPO, atribua a eles a função de Administrador de suporte ao serviço no Azure Active Directory, para que eles possam continuar a criar tíquetes de suporte no Portal do Azure.
- Para obter mais informações e links úteis, clique em Informações Adicionais.

#### <a name="additional-information"></a>Informações adicionais
Para saber mais, confira a [postagem no blog da equipe de suporte do Microsoft Intune](https://aka.ms/IntuneSupport_MPO_to_Azure).


### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Executar ação: atualize as configurações de senha de política de conformidade ou de restrição do dispositivo Android no Intune
O Intune removerá o tipo de senha "dispositivo padrão" disponível para dispositivos Android 4.4 superiores. Devido às diferenças em plataformas Android e dispositivos padrão, essa política geralmente é tratada como opcional pelo dispositivo. Para esclarecer dúvidas sobre quando essa configuração é aplicada no Android, removeremos essa configuração da interface do usuário em uma versão futura. 
#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
- Se sua intenção é exigir uma senha nos dispositivos, é recomendável que, em vez de usar "dispositivo padrão", você edite seus perfis da plataforma Android para articular claramente o tipo de senha necessário.
- Se sua intenção é permitir que o usuário final decida se deve criar uma senha, selecione o botão "Não configurado". Quando removermos essa configuração da interface do usuário, você deverá escolher um valor diferente de "Dispositivo padrão" na próxima edição do perfil se a configuração ainda estiver definida.
O que preciso fazer para me preparar para essa alteração?
Examine as configurações de senha em suas políticas de conformidade e restrição de dispositivo Android e Android enterprise. Elas são listadas na Segurança do sistema para Políticas de conformidade e em Senha do dispositivo ou Configurações de perfil de trabalho para Restrições de dispositivo. Informações adicionais têm um link para obter mais detalhes e capturas de tela para os quais essas configurações são definidas.
#### <a name="additional-information"></a>Informações adicionais
https://aka.ms/PasswordSettings 

### <a name="plan-for-change-change-password-at-next-auth-added-to-intune---1873216---"></a>Plano de alteração: opção Alterar Senha na Próxima Autenticação adicionada ao Intune<!-- 1873216 -->
Na versão do serviço de setembro, o Intune planeja integrar a configuração recém-lançada da Apple **Alterar Senha na Próxima Autenticação** aos dispositivos que executam o macOS versões 10.13 e mais recentes. Antes dessa configuração, os provedores de MDM não podiam verificar se a senha do dispositivo foi alterada para ficar em conformidade. As políticas de configuração e conformidade do Intune somente validam que na próxima vez que a senha do dispositivo for alterada, ele será marcado como em conformidade. Quando esse novo recurso da Apple for adicionado, os usuários do macOS receberão uma solicitação para atualizar a senha, mesmo que ela esteja em conformidade.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Isso afeta ambientes que têm uma política de dispositivo macOS e que usam o Intune ou um MDM híbrido. Agora que a Apple tem essa configuração **Alterar Senha na Nova Autenticação**, o Intune pode forçar os usuários a atualizarem a senha quando uma política de senha é enviada por push. Se você bloquear os recursos da empresa até que o dispositivo seja marcado como em conformidade, os usuários finais poderão ser impedidos de acessar os recursos da empresa, como email ou sites do SharePoint, até que redefinam a senha. No futuro, todas as atualizações das políticas de senha de configuração e conformidade forçarão os usuários de destino a atualizarem suas senhas.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Informe o Suporte Técnico. Caso você não queira impor essa política do dispositivo macOS, recomendamos que você cancele a atribuição ou exclua a política do macOS existente. Uma pesquisa com clientes sugere que a maioria deles não é afetada por essa alteração. A maioria dos usuários finais atualiza a senha depois de receber uma solicitação para registrar com uma senha ou redefine a senha para permanecer em conformidade.

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Plano para alteração: migração do Intune para o TLS 1.2
A partir de 31 de outubro de 2018, o Intune dará suporte ao protocolo TLS versão 1.2 a fim de fornecer criptografia de ponta, para garantir que nosso serviço seja mais seguro por padrão e para se alinhar com outros serviços da Microsoft, como o Microsoft Office 365. O Office anunciou essa alteração no MC128929.

O Portal da Empresa também mudará para ser compatível com o TLS 1.2 em 31 de outubro de 2018.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A partir de 31 de outubro de 2018, o Intune deixará de dar suporte ao protocolo TLS versões 1.0 ou 1.1. Todas as combinações de cliente-servidor e navegador-servidor devem usar o TLS versão 1.2 para garantir uma conexão sem problemas com o Intune. Observe que essa alteração afetará os dispositivos de usuários finais que não são mais compatíveis com o Intune, mas que ainda recebem a política por meio do Intune e que não podem usar o TLS versão 1.2. Isso inclui dispositivos como aqueles que executam o Android 4.3 e anterior. Para obter uma lista dos dispositivos e navegadores afetados, confira Informações adicionais abaixo.

Após 31 de outubro de 2018, caso você tenha um problema relacionado ao uso de uma versão antiga do TLS, precisará atualizar para o TLS 1.2 ou para um dispositivo que dê suporte ao TLS 1.2 como parte da resolução.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Recomendamos que você remova de forma proativa as dependências do TLS 1.0 e 1.1 dos ambientes e desabilite o TLS 1.0 e 1.1 no nível do sistema operacional sempre que possível. Comece a planejar hoje mesmo sua migração para o TLS 1.2. Confira a postagem no blog de suporte abaixo para obter a lista de dispositivos que não são compatíveis com o Intune hoje, mas que ainda podem receber a política e que não poderão se comunicar usando o TLS versão 1.2. Talvez você precise notificar os usuários finais de que eles perderão o acesso aos recursos corporativos.

**Informações adicionais**: [migração do Intune para o TLS 1.2 para criptografia](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Planeje a mudança: use o Intune no Azure agora para o gerenciamento MDM<!-- 1227338 -->
Há mais de um ano, foi anunciada [a visualização pública do Intune no Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) e, após seis meses, a [Disponibilidade geral da nova experiência de administração](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) para o Intune. No dia 31 de agosto de 2018, o MDM (gerenciamento de dispositivo móvel) será desabilitado no console do Silverlight clássico para os clientes que usam o Intune autônomo. Nesse caso, você poderá usar o [Intune no Azure](https://aka.ms/Intune_on_Azure) para atender às suas necessidades de MDM. Se você ainda estiver usando o console clássico do MDM, deixe de usá-lo e familiarize-se com o Intune no Azure. Não esperamos que haja nenhum impacto para o usuário final com essa alteração. O gerenciamento de computador clássico permanecerá no Silverlight. Saiba mais sobre essa alteração e como ela o afetará clicando [aqui](https://aka.ms/Intune_on_Azure_mdm).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->
A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Vamos manter nosso [blog de suporte do Intune](https://aka.ms/compportalats) com detalhes.



## <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/cloud-platform/roadmap)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
