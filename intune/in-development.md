---
title: No desenvolvimento - Microsoft Intune
titlesuffix: ''
description: Recursos do Microsoft Intune no desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c377a8558b1f318b4ddad735b6368a291e34516
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57756812"
---
# <a name="in-development-for-microsoft-intune---march-2019"></a>No desenvolvimento do Microsoft Intune – março de 2019

Para ajudá-lo em sua preparação e planejamento, esta página listas UI Intune atualiza e recursos que estão em desenvolvimento, mas ainda não foi liberado. Além disso:

- Se prevemos que você precisará agir antes de uma alteração, publicaremos uma postagem complementar do Centro de mensagens do Office.
- Quando um recurso é iniciado em produção, como uma visualização ou em disponibilidade geral, a descrição do recurso moverá desativar esta página e para o [página de novidades](whats-new.md).
- Esta página e o [página de novidades](whats-new.md) são atualizados periodicamente. Volte a ela para verificar se há atualizações adicionais.
- Consulte a [M365 roteiro](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para entregas estratégicas e linhas do tempo.

> [!Note]
> Esses itens refletem a expectativas atuais da Microsoft sobre os recursos do Intune vem em uma versão futura. As datas e os recursos individuais podem ser alteradas. Nem todos os itens no desenvolvimento de tem uma descrição do recurso nesta página.

**RSS feed**: receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`


<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure


<!-- 1903 start-->

### <a name="encryption-report-----2351538---"></a>Relatório de criptografia  <!-- 2351538 -->
Você poderá usar um novo relatório de criptografia para exibir detalhes sobre o status da criptografia de seus dispositivos. Detalhes disponíveis incluirá uma versão TPM de dispositivos, preparação de criptografia e status, relatório de erros e muito mais.  

### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-----2351547----"></a>Chaves de recuperação do BitLocker de acesso do portal do Intune  <!-- 2351547  -->
Estamos adicionando um novo ponto de entrada em dispositivos, onde você pode exibir detalhes do Azure AAD (Active Directory) sobre BitLocker chave ID e chaves de recuperação do BitLocker.

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Marcas de escopo para políticas de configuração de aplicativo <!--2371891 -->
Você poderá adicionar uma marca de escopo a uma política de configuração de aplicativo para que somente pessoas com as funções também atribuídas a essa marca de escopo tenham acesso à política de configuração de aplicativo. A política de configuração de aplicativo só pode ser direcionada a ou associada a aplicativos atribuídos a mesma marca de escopo.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Atribuir perfis do Autopilot ao grupo virtual Todos os dispositivos <!--2715522 -->
Será possível atribuir perfis do Autopilot ao grupo virtual Todos os dispositivos. Para fazer isso, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > escolha um perfil > **Atribuições** > em **Atribuir a**, escolha **Todos os dispositivos**. Para obter mais informações sobre os perfis do Autopilot, confira [Registrar dispositivos Windows usando o Windows Autopilot](enrollment-autopilot.md).

### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523----"></a>Instalar aplicativos disponíveis usando o aplicativo de Portal da empresa após o registro em massa do Windows <!-- 2751523  -->
Dispositivos Windows registrados no Intune usando [registro do Windows em massa](windows-bulk-enroll.md) (pacotes de provisionamento) poderão usar o aplicativo de Portal da empresa para instalar aplicativos disponíveis. Para obter mais informações sobre o aplicativo de Portal da empresa, consulte [adicionar manualmente o Portal da empresa do Windows 10](store-apps-company-portal-app.md) e [como configurar o aplicativo de Portal da empresa do Microsoft Intune](company-portal-app.md).

### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430---"></a>Marcas de escopo para perfis de provisionamento de aplicativo do iOS <!--2934430 -->
Você poderá adicionar uma marca de escopo a um perfil de provisionamento de aplicativo do iOS para que somente pessoas com as funções também atribuídas a essa marca de escopo tenham acesso ao perfil de provisionamento de aplicativo do iOS. 

### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477----"></a>Ferramenta de implantação Office (ODT) XML para implantação do Office ProPlus <!-- 3192477  -->
Você poderá fornecer a ferramenta de implantação do Office (ODT) XML ao criar uma instância do Office Pro Plus no console de administração do Intune. Isso permitirá que o maior capacidade de personalização se as opções de UI Intune existentes não atenderem às suas necessidades. 

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>Bloquear usuários de verificar se há atualizações do Windows    <!-- 3316758    -->
Estamos adicionando um novo Windows anel de atualização definindo o que você pode usar que bloqueará os usuários de verificar se há atualizações do Windows. Essa configuração não estará disponível de dentro do portal, mas pode ser configurada usando a API do Graph do Intune.

### <a name="windows-update-notifications-----3316782---"></a>Notificações de atualização do Windows  <!-- 3316782 -->
Estamos adicionando suporte para as configurações do anel de atualização do Windows para que você possa configurar as notificações de atualização do Windows que os usuários vejam. Essa configuração não estará disponível de dentro do portal, mas pode ser configurada usando a API do Graph do Intune.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Alterações no registro do Portal da empresa para usuários de dispositivos iOS 12 <!--3448635 -->  
Portal da empresa para iOS atualizará as telas de registro do aplicativo e as etapas para se alinhar com as alterações de registro do MDM lançadas no Apple iOS 12.2. O fluxo de trabalho atualizado agora solicitará que os usuários:

- Permitir Safari abrir o site do Portal da empresa (por meio do Safari) e baixar o perfil de gerenciamento antes de retornar ao aplicativo Portal da empresa. 
- Abra o aplicativo de configurações para instalar o perfil de gerenciamento em seu dispositivo.
- Retorne ao aplicativo Portal da empresa para concluir o registro.  

Para obter mais informações sobre como preparar para que essas alterações, consulte o [postagem do Microsoft Tech Community](https://techcommunity.microsoft.com/). Enquanto isso, para dar suporte a novos registros de iOS no Portal da empresa, nós atualizamos as etapas em [registrar o dispositivo de iOS no Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). Essas alterações de docs será dinâmicas após o lançamento da Apple iOS versão 12.2. 

### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202-------"></a>Suporte para conectores adicionais na página de Status do locatário <!-- 3617202     -->
A página de Status do locatário exibirá informações de status para conectores adicionais, incluindo *Windows Defender Advanced Threat Protection* (ATP) e outros conectores de defesa contra ameaças móveis.

### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917---"></a>Intune de conceder acesso de leitura apenas para algumas funções do Active Directory do Azure <!-- 3637917 -->
Podemos vai concedendo que acesso somente às seguintes funções do Azure AD de leitura do Intune. Permissões concedidas com funções do Azure AD substituem as permissões concedidas com controle de acesso baseado em função (RBAC) do Intune.

Somente o acesso de leitura aos dados de auditoria do Intune:

- Administrador de conformidade
- Administrador de dados de conformidade

Acesso somente leitura a todos os dados do Intune:

- Administrador de Segurança
- Operador de segurança
- Leitor de segurança
- Leitor global

### <a name="easier-access-to-diagnostic-settings------3804627-----"></a>Acesso mais fácil a configurações de diagnóstico   <!-- 3804627   -->
Estamos adicionando uma nova opção para o **logs de auditoria** folha em cada em cada carga de trabalho do Log de auditoria no console do Intune que você pode usar para abrir diretamente o *configurações de diagnóstico* página.

### <a name="create-and-use-device-configuration-profiles-on-android-zebra-devices-in-intune----3895244----"></a>Criar e usar perfis de configuração do dispositivo em dispositivos Android Zebra no Intune <!-- 3895244  -->
Intune oferecerá suporte a configurar dispositivos Android Zebra. Especificamente, você poderá: 

- Criar um perfil de configuração do dispositivo e aplicar as configurações para dispositivos Android Zebra usando perfis de extensões de mobilidade (MX) gerados pelo StageNow (**configuração do dispositivo** > **perfis**  >  **Criar perfil** > **Android** para plataforma).

Aplica-se a:  
- Android

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implantação de aplicativos online licenciados da Microsoft Store para Empresas <!-- 1672660  -->
Você poderá atribuir aplicativos online licenciados obrigatórios da Microsoft Store para Empresas no contexto de dispositivo. A implantação de um aplicativo da Microsoft Store para Empresas dessa maneira permitirá que o aplicativo seja instalado para todos os usuários no dispositivo. Isso é aplicável somente a dispositivos Windows 10 RS4+ desktop. A opção de instalação no contexto de dispositivo está disponível na página Atribuição de aplicativo do Cliente para aplicativos Online Licenciados da MSFB.

## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
