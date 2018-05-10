---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b003fde011fd3a727c7c7a163fedb1dae6779425
ms.sourcegitcommit: 407191a92ef356a3d196b6f9959b9b033190ca2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>A Edição Antecipada do Microsoft Intune – abril de 2018

A **edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não compartilhe essas informações fora da empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
>As seguintes alterações estão em desenvolvimento para o Intune. Para obter mais informações sobre os novos recursos híbridos, confira a [página Novidades sobre híbridos](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1804 start -->

### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Mostrar a identificação do chamador no perfil pessoal - Android for Work <!--1098984 -->
Ao usar um perfil particular em um dispositivo, os usuários finais não poderão ver os detalhes da identificação do chamador de um contato de trabalho. 

Com essa atualização, há uma nova configuração em **Android for Work** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
- Exibir a identificação do chamador do contato de trabalho no perfil pessoal

Quando habilitado (não configurado), os detalhes de contato comercial do chamador são exibidos no perfil pessoal. Quando bloqueado, o número de contato comercial do chamador é exibido no perfil pessoal. 

Aplica-se a: dispositivos Android de perfil de trabalho no sistema operacional Android v6.0 e mais recentes

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Novas configurações do Windows Defender Credential Guard adicionadas às configurações de proteção de ponto de extremidade <!--1102252 --><!--from 1802-->

As novas configurações do [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) serão adicionadas à **Configuração do dispositivo** > **Perfis** > **Proteção de ponto de extremidade**. As configurações a seguir serão adicionadas:

- Nível de Segurança da Plataforma: especifique se o Nível de Segurança da Plataforma está habilitado na próxima reinicialização. A segurança baseada em virtualização requer a Inicialização Segura. A segurança baseada em virtualização pode, opcionalmente, ser habilitada com o uso de proteções de DMA (acesso direto à memória). Proteções de DMA exigem suporte de hardware e serão habilitadas somente em dispositivos configurados corretamente.
- Segurança baseada em virtualização: especifique se a segurança baseada em virtualização será habilitada na próxima reinicialização.
- Windows Defender Credential Guard: ative o Credential Guard com a segurança baseada em virtualização para ajudar a proteger as credenciais na próxima reinicialização quando o Nível de Segurança de Plataforma com Inicialização Segura e a Segurança Baseada em Virtualização estiverem habilitadas. As opções disponíveis incluem **Desabilitada**, **Habilitada com o bloqueio UEFI**, **Habilitada sem bloqueio** e **Não configurada**.
  - A opção "Desabilitada" desativará o Credential Guard remotamente se ele estiver habilitado com a opção "Habilitada sem bloqueio".

  - A opção "Habilitada com o bloqueio UEFI" garante que o Credential Guard não possa ser desabilitado com a chave do Registro ou usando a Política de Grupo. Para desabilitar o Credential Guard após usar essa configuração, você precisa definir a Política de Grupo como "Desabilitada" e remover a funcionalidade de segurança em cada computador, com um usuário presente fisicamente, para limpar a configuração persistente na UEFI. Enquanto a configuração da UEFI persistir, o Credential Guard estará habilitado.

  - A opção "Habilitada sem bloqueio" permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, pelo menos, o Windows 10 (versão 1511).

  - A opção "Não configurada" deixa a configuração de política indefinida. A Política de Grupo não grava a configuração de política no Registro e, por isso, não tem impacto sobre computadores ou usuários. Se houver uma configuração atual no registro, ela não será modificada.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Suporte de senha para o PIN de MAM no Android<!-- 1438086 -->

Os administradores do Intune poderão definir um requisito de inicialização do aplicativo para impor uma senha, em vez de um PIN numérico de MAM. Se configurado, o usuário será obrigado a definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. O Intune é compatível com senha de maneira semelhante ao PIN numérico existente, sendo capaz de definir um tamanho mínimo, permitindo caracteres e sequências repetidos por meio do console do administrador. Este recurso requer a versão mais recente do Portal da Empresa no Android. Esse recurso já está disponível para iOS.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Bloquear capturas de tela e a câmera no Android for Work <!-- 1098977 eeready-->
Duas novas propriedades estarão disponíveis para bloqueio quando você configurar as restrições de dispositivo para dispositivos Android: 
- Câmera: bloqueia o acesso a todas as câmeras no dispositivo
- Captura de tela: bloqueia a captura de tela e também impede que o conteúdo seja mostrado em dispositivos de exibição que não tenham uma saída de vídeo segura

Aplica-se a Android for Work.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Suporte para aplicativo de LOB (linha de negócios) do macOS <!-- 1473977 -->
O Microsoft Intune oferecerá a capacidade de instalar aplicativos de LOB macOS do Portal do Azure. Você poderá adicionar um aplicativo de LOB macOS ao Intune depois de ele ter sido previamente processado pela ferramenta disponível no GitHub. No Portal do Azure, escolha **Aplicativos móveis** na folha **Intune**. Na folha **Aplicativos móveis**, escolha **Aplicativos** > **Adicionar**. Na folha **Adicionar Aplicativo**, selecione **Aplicativo de linha de negócios**. 

### <a name="support-for-user-less-devices----1637553---"></a>Suporte para dispositivos sem usuário <!-- 1637553 -->
O Intune será compatível com a capacidade de avaliar a conformidade em um dispositivo sem usuário, como o Microsoft Surface Hub. A política de conformidade pode ter como destino dispositivos específicos. Assim, a conformidade (e a não conformidade) pode ser determinada para dispositivos que não tenham um usuário associado.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Adições às configurações das opções de segurança do dispositivo local <!-- 1403702 -->
Você poderá definir as configurações adicionais de Opções de Segurança de Dispositivo Local para dispositivos Windows 10. Configurações adicionais estarão disponíveis nas áreas de Cliente de Rede da Microsoft, Servidor de Rede Microsoft, Acesso e segurança de rede e Logon interativo. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Requer a instalação de perfis de políticas, aplicativos, certificado e rede <!-- 1553555 -->
Os administradores poderão impedir que usuários finais acessem a área de trabalho do Windows 10 RS4 até que o Intune instale políticas, aplicativos e perfis de certificado e de rede durante o provisionamento de dispositivos AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estarão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de remoção de dispositivo**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Impedir aplicativos e experiências de consumidor em dispositivos Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Você poderá impedir a instalação de aplicativos e experiências de consumidor nos seus dispositivos Windows 10 Enterprise RS4 AutoPilot. Para ver esse recurso, vá para **Intune** > **Registro de dispositivo** > **Registro do Windows** > **Perfis do Windows AutoPilot** > **Criar Novo** > **Configurações de registro**. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>A Proteção Avançada contra Ameaças é integrada ao Intune <!-- 1629303 -->
[ATP (Proteção Avançada contra Ameaças)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) mostra o nível de risco de dispositivos Windows 10. Quando o Intune avalia dispositivos Windows 10 para fins de conformidade, a pontuação de risco ATP é incluída nessa avaliação. Você pode usar ATP com acesso condicional para ajudar a proteger a sua rede.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Novas etapas de registro para usuários em dispositivos com macOS High Sierra 10.13.2+ <!--1734567 -->
O macOS High Sierra 10.13.2 introduziu o conceito de registro do MDM "Aprovado pelo Usuário". No futuro, inscrições aprovadas permitirão que o Intune gerencie algumas configurações sensíveis de segurança. Para obter mais informações, consulte a documentação de suporte da Apple aqui: https://support.apple.com/HT208019.

Dispositivos registrados usando o Portal da Empresa macOS serão considerados "Não Aprovados pelo Usuário", a menos que o usuário final abra as Preferências do Sistema e dê manualmente sua aprovação. Para esse fim, o Portal da Empresa macOS agora direciona os usuários em macOS 10.13.2 e acima e aprovar manualmente o registro no final do processo de registro. O console do administrador do Intune relatará se um dispositivo registrado for aprovado pelo usuário.

### <a name="delete-autopilot-devices----1713650---"></a>Excluir dispositivos AutoPilot <!-- 1713650 -->
Os administradores do Intune poderão excluir dispositivos AutoPilot.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Grupos Todos os Usuários e Todos os Dispositivos internos para atribuição de aplicativo AFW (Android for Work) <!-- 1813073 -->
Você poderá aproveitar os grupos **Todos os Usuários** e **Todos os Dispositivos** internos para uma atribuição de aplicativo AFW. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).

### <a name="improved-device-deletion-experience---1832333---"></a>Experiência de exclusão do dispositivo aprimorada <!--1832333 -->
Você não precisará mais remover dados da empresa nem fazer uma redefinição de fábrica do dispositivo antes de excluir um dispositivo do Intune.

Para ver a nova experiência, entre no Intune e selecione **Dispositivos** > **Todos os Dispositivos** > nome do dispositivo > **Excluir**.

 Se você ainda quiser apagar/desativar a confirmação, poderá usar a rota de ciclo de vida do dispositivo padrão emitindo **Remover dados da empresa** e **Redefinição de Fábrica** antes de **Excluir**. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Perfis do AutoPilot passando para grupo direcionado a <!-- 1877935 -->
No momento, perfis de implantação do AutoPilot podem ser atribuídos a dispositivos selecionados. Até o final de abril, é assim que você atribuirá estes perfis:
- Criar grupos (Azure AD) contendo dispositivos AutoPilot
- Atribua os perfis desejados a um grupo do Azure AD. O perfil AutoPilot agora será atribuído a dispositivos AutoPilot naquele grupo.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Tocar sons no iOS quando no modo Perdido <!-- 1629303 -->
Quando dispositivos iOS supervisionados estiverem no [modo Perdido](device-lost-mode.md) do MDM (gerenciamento de dispositivo móvel), você poderá tocar um som (**Dispositivos** > **Todos os dispositivos** > selecione um dispositivo iOS > **Visão geral** > **Mais**). O som continua sendo reproduzido até o dispositivo ser removido do modo perdido ou um usuário desabilitar o som no dispositivo. Aplica-se a dispositivos iOS 9.3 e mais recentes.

### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune reinstalará os aplicativos necessários que são desinstalados por usuários <!-- 1947010 -->
Se um usuário final desinstalar um aplicativo necessário, o Intune reinstalará automaticamente o aplicativo dentro de 24 horas em vez de aguardar o ciclo de reavaliação de 7 dias.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Use um nome de entidade personalizado no certificado SCEP <!-- 2064190 -->
Você poderá usar o nome comum **OnPremisesSamAccountName** em uma entidade personalizada em um perfil de certificado SCEP. Por exemplo, você pode usar `CN={OnPremisesSamAccountName})`.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Enviar relatórios de diagnóstico no aplicativo de Portal da Empresa para macOS <!-- 2216677 -->
O aplicativo Portal da Empresa para dispositivos macOS será atualizado para melhorar a como os usuários relatam erros relacionados ao Intune. No aplicativo Portal da Empresa, seus funcionários poderão:
- Carregue relatórios de diagnóstico diretamente para a equipe de desenvolvedores Microsoft.
- Envie por email uma ID de incidente à equipe de suporte de TI da sua empresa.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On para Windows 10 <!--1333666 -->

No momento, [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) pode ser usado em dispositivos Windows 10 usando um perfil de VPN (rede virtual privada) personalizado criado usando o OMA-URI.

Com essa atualização, os administradores poderão habilitar Always On para perfis de VPN do Windows 10 diretamente no Intune no Portal do Azure. Perfis de VPN Always On conectam-se automaticamente quando:

- Os usuários fazem logon em seus dispositivos
- A rede no dispositivo muda
- A tela do dispositivo é ativada novamente depois de ser desligada

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Mensagens de erro aprimoradas para falha no upload do Apple MDM Push Certificate <!-- 2172331 -->

A mensagem de erro explicará que a mesma ID da Apple deve ser usada durante a renovação de um certificado existente do MDM.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>A lista de status e gráfico de perfil do dispositivo mostra todos os dispositivos em um grupo <!-- 1449153 eeready -->
Quando você configura um perfil de dispositivo (**Configuração do dispositivo** > **Perfis**), escolha o perfil do dispositivo, como iOS. Você pode atribuir esse perfil a um grupo que inclua dispositivos iOS e dispositivos não iOS. A contagem de gráfico mostra que o perfil é aplicado a dispositivos iOS *e* não iOS (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral**). Quando você seleciona o gráfico na guia **Visão geral**, o **Status do dispositivo** lista todos os dispositivos no grupo, em vez de apenas os dispositivos iOS. 

Com essa atualização, o gráfico (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral**) mostrará apenas a contagem para o perfil de dispositivo específico. Por exemplo, se o perfil do dispositivo de configuração se aplicar a dispositivos iOS, o gráfico listará somente a contagem de dispositivos iOS. Selecionar o gráfico e abrir o **Status do dispositivo** lista apenas os dispositivos iOS.

Enquanto essa atualização está sendo feita, o gráfico do usuário é removido temporariamente. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Suporte ao Multiple Exchange Connector <!-- 2070451 -->

Você não fica mais limitado a um Microsoft Intune Exchange Connector por locatário. O Intune dá suporte a vários Exchange Connectors para que você possa configurar o acesso condicional do Intune com diversas organizações do Exchange local.

Com um conector do Exchange local do Intune, você pode gerenciar o acesso ao dispositivo para suas caixas de entrada do Exchange local com base em se um dispositivo é registrado no Intune e está em conformidade com as políticas de conformidade de dispositivo do Intune. Para configurar um conector, baixe o conector do Exchange local do Portal do Azure no Intune e instale-o em um servidor na sua organização do Exchange. No painel do Microsoft Intune, escolha **Acesso local** e, em **Configuração**, selecione **Conector do Exchange ActiveSync**. Baixe o conector local do Exchange local e instale-o em um servidor na sua organização do Exchange. Agora que não há mais o limite de um conector do Exchange por locatário, se você tiver organizações do Exchange adicionais, siga este mesmo processo para baixar e instalar um conector para cada organização do Exchange adicional.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Suporte futuro para novo cliente Cisco AnyConnect para iOS <!-- 1333708 -->

Os novos perfis de VPN criados para Cisco AnyConnect para iOS funcionam com o Cisco AnyConnect 4.0.7x e superior. Perfis existentes de VPN do Cisco AnyConnect do iOS serão rotulado como **Cisco Legacy AnyConnect** e continuarão a funcionar com o Cisco AnyConnect 4.0.5x como fazem atualmente.

> [!NOTE]
> Essa mudança afeta apenas o iOS. Continuará existindo apenas uma opção de Cisco AnyConnect para Android, Android for Work e macOS.

#### <a name="more-information"></a>Mais informações

Você precisa criar um novo perfil de VPN do Cisco AnyConnect do iOS para dar suporte ao novo aplicativo, pois o novo aplicativo Cisco AnyConnect e o aplicativo Cisco Legacy AnyConnect são aplicativos separados. Se você estiver gerenciando o cliente AnyConnect em seu ambiente, também será necessário implantar o aplicativo Cisco AnyConnect. Para concluir uma atualização, você também precisa excluir o perfil de VPN do Cisco Legacy AnyConnect e remover o aplicativo Cisco Legacy AnyConnect.

Integração de NAC (Controle de Acesso à Rede) não funcionará para o novo cliente AnyConnect na versão inicial. Estamos trabalhando com a Cisco para fornecer integração a NAC em uma futura versão do Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Capacidade de implantar aplicativos LOB (aplicativo de linha de negócios) necessários para Todos os usuários em dispositivos do Windows 10 Desktop <!-- 1627835 RS4 -->
Os clientes poderão implantar os aplicativos de linha de negócios do Windows 10 necessários que deverão ser instalados em contextos de dispositivo. Isso permitirá que esses aplicativos estejam disponíveis para todos os usuários no dispositivo. Isso se aplica somente a dispositivos Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Registro do Portal da Empresa melhorado <!-- 1874230-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior poderão concluir a primeira etapa de registro sem sair do aplicativo.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Atualizando a experiência de Ajuda e Comentários no aplicativo Portal da Empresa para Android <!--1631531 -->

Atualizaremos a experiência de Ajuda e de Comentários no aplicativo Portal da Empresa para Android a fim de alinhá-lo com as práticas recomendadas para aplicativos Android. Estaremos atualizando o aplicativo Portal da Empresa para Android nos próximos meses para dividir o item de menu **Ajuda e Comentários** nos itens **Ajuda** e **Enviar comentários** separados. A página **Ajuda** conterá com uma seção de **Perguntas Frequentes** e um botão **Suporte por Email** para instruir os usuários finais a carregar logs para a Microsoft e enviar email para o suporte da empresa descrevendo o problema. **Enviar Comentários** guiará o usuário por um envio de comentários padrão da Microsoft, que solicitará ao usuário escolher entre “Gosto de algo”, “ Não gosto de algo” ou “Tenho uma ideia”.

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Novas configurações de impressora para perfis de educação <!-- 1308900 -->

Para perfis de educação, novas configurações estarão disponíveis na categoria **Impressoras**: **Impressoras**, **Impressora padrão**, **Adicionar novas impressoras**.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.




## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.


### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


