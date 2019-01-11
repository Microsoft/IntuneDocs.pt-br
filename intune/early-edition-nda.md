---
title: Edição antecipada - Microsoft Intune
titlesuffix: ''
description: Edição antecipada do Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 94125ced318f304e5b2bdc8f09472280fc05b08a
ms.sourcegitcommit: 662afec5e87639a7f541bb89700cc0fec5037bb0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2019
ms.locfileid: "54069346"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>A edição antecipada do Microsoft Intune – janeiro de 2019

> [!Note]
> Notificação de NDA: As seguintes alterações estão em desenvolvimento para o Intune. Essas informações são compartilhadas nos termos do NDA de forma muito limitada. Não poste nenhuma dessas informações em mídia social nem em sites públicos, como Twitter, UserVoice, Reddit e assim por diante. 

A **edição antecipada** fornece uma lista de recursos, compartilhados nos termos do NDA, que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não tweet, poste no UserVoice nem compartilhe de nenhuma outra forma essas informações fora de sua empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Aplicativos do Android Enterprise <!-- 1352553  -->
Você poderá excluir aplicativos do Google Play gerenciado do Microsoft Intune. Para excluir um aplicativo do Google Play gerenciado, você abrirá o Microsoft Intune no portal do Azure e selecionará **Aplicativos cliente** > **Aplicativos**. Na lista de aplicativos, você selecionará as reticências (...) à direita do aplicativo do Google Play gerenciado e, em seguida, selecionará **Excluir** na lista exibida. Quando você exclui um aplicativo do Google Play gerenciado na lista de aplicativos, o aplicativo do Google Play gerenciado torna-se para aprovação automaticamente.

### <a name="managed-google-play-app-type----1352580---"></a>Tipo de aplicativo do Google Play gerenciado <!-- 1352580 -->
O tipo de aplicativo **Google Play gerenciado** permitirá que você adicione especificamente [aplicativos do Google Play gerenciado](https://play.google.com/work/search?q=microsoft&c=apps) ao Intune. Como administrador do Intune, agora você poderá navegar, pesquisar, aprovar, sincronizar e atribuir aplicativos aprovados do Google Play gerenciado no Intune. Você não precisará mais navegar para o console do Google Play gerenciado separadamente nem se autenticar novamente. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo**, selecione **Google Play Gerenciado** como o tipo de aplicativo.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Versão prévia do suporte para dispositivos Android corporativos totalmente gerenciados <!-- 1574342  -->
O Intune oferece suporte a dispositivos Android totalmente gerenciados, um cenário de "proprietário do dispositivo" corporativo no qual os dispositivos são gerenciados com rigidez pelo departamento de TI e são afiliados a usuários individuais. Isso permite aos administradores gerenciar todo o dispositivo, impor uma extensa variedade de controles de política não disponíveis aos perfis de trabalho e restringe a instalação de aplicativos por parte dos usuários apenas à Google Play gerenciada. Para configurar dispositivos Android totalmente gerenciados, você acessará **Registro de dispositivo** > **Registro do Android** > **Dispositivos de usuários corporativos totalmente gerenciados**. Observe que esse recurso está em versão prévia. Algumas funcionalidades do Intune, como certificados, conformidade e Acesso Condicional, não estão atualmente disponíveis em dispositivos de usuário Android totalmente gerenciados.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----16726660----"></a>Implantação de aplicativos online licenciados da Microsoft Store para Empresas <!-- 16726660  -->
Você poderá atribuir aplicativos online licenciados obrigatórios da Microsoft Store para Empresas no contexto de dispositivo. A implantação de um aplicativo da Microsoft Store para Empresas dessa maneira permitirá que o aplicativo seja instalado para todos os usuários no dispositivo. Isso é aplicável somente a dispositivos Windows 10 RS4+ desktop. A opção de instalação no contexto de dispositivo está disponível na página Atribuição de aplicativo do Cliente para aplicativos Online Licenciados da MSFB.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Configurar o perfil para ignorar algumas telas durante a execução do Assistente de Configuração <!-- 2276470  -->
Ao criar um perfil de registro do macOS, você poderá configurá-lo para ignorar uma das seguintes telas quando um usuário executar o Assistente de Configuração:
- Migração do Android
- Tom de Exibição
- Privacidade
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Atribuir perfis do Autopilot ao grupo virtual Todos os dispositivos <!--2715522  -->
Será possível atribuir perfis do Autopilot ao grupo virtual Todos os dispositivos. Para fazer isso, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > escolha um perfil > **Atribuições** > em **Atribuir a**, escolha **Todos os dispositivos**. Para obter mais informações sobre os perfis do Autopilot, confira [Registrar dispositivos Windows usando o Windows Autopilot](enrollment-autopilot.md).

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Personalizar o papel de parede em dispositivos iOS supervisionados usando um perfil de configuração do dispositivo <!-- 2809324  -->
Ao criar um perfil de configuração do dispositivo para dispositivos iOS, você poderá permitir e restringir algumas configurações em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil. Essa atualização inclui novas configurações de **Papel de Parede** que permitem a um administrador usar uma imagem .png, .jpg ou .jpeg como papel de parede, visualizar a imagem e impedir que os usuários alterem o papel de parede. As configurações de papel de parede se aplicam somente a dispositivos supervisionados. Para obter uma lista das configurações atuais, confira [Configurações de restrição de dispositivo iOS](device-restrictions-ios.md).

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Notificações do sistema para aplicativos Win32 <!-- 3136566   -->
Você poderá suprimir a exibição de notificações do sistema ao usuário final por atribuição de aplicativo. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > selecione o aplicativo > **Atribuições** > **Incluir Grupos**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>O Compartilhamento de Contatos via Bluetooth é removido de Restrições de Dispositivo > Proprietário do Dispositivo Android Enterprise <!-- 3598396 -->
Quando você cria um perfil de restrições de dispositivo para dispositivos Android Enterprise, há uma configuração **Compartilhamento de Contatos via Bluetooth**. Nesta atualização, a configuração **Compartilhamento de Contatos via Bluetooth** será removida (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para a plataforma > **Restrições de Dispositivo > Proprietário do dispositivo** para o tipo de perfil > **Geral**). 

Não há suporte para a configuração **Compartilhamento de Contatos via Bluetooth** no gerenciamento do Proprietário do Dispositivo Android Enterprise. Portanto, quando essa configuração for removida, ela não afetará nenhum dispositivo ou locatário, mesmo se ela estiver habilitada e configurada no ambiente.

Para ver a lista atual de configurações, acesse [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos](device-restrictions-android-for-work.md).

Aplica-se a: Proprietário do Dispositivo Android Enterprise

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Implantação do aplicativo APP-WE do Android Enterprise <!-- 1171203 -->
Para dispositivos Android em um cenário de implantação APP-WE (Política de proteção de aplicativo sem registro), é possível usar o Google Play gerenciado para implantar aplicativos da loja e aplicativos de LOB para os usuários. Especificamente, o departamento de TI pode fornecer uma experiência de catálogo e instalação de aplicativos que não exige mais dos usuários finais a negligência com relação à postura de segurança de seus dispositivos ao permitir instalações de fontes desconhecidas. Além disso, esse cenário de implantação fornece uma experiência aprimorada ao usuário final.

### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Novas opções para se conectar automaticamente e manter as regras ao usar configurações de DNS em dispositivos com Windows 10 e versões posteriores <!-- 1333665, 2999078 -->
Em dispositivos com Windows 10 e posteriores, é possível criar um perfil de configuração de VPN que inclui uma lista de servidores DNS para resolver domínios, por exemplo, contoso.com. Isso inclui novas configurações de resolução de nome (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **Windows 10 e posterior** para a plataforma > escolha **VPN** para o tipo de perfil > **Configurações de DNS** >**Adicionar**): 

- **Conectar automaticamente**: Quando essa opção está **Habilitada**, o dispositivo se conecta automaticamente à VPN quando um dispositivo entra em contato com um domínio inserido por você, por exemplo, contoso.com.
- **Persistente**: Por padrão, todas as regras de NRPT (Tabela de Políticas de Resolução de Nomes) estão ativas, desde que o dispositivo esteja conectado usando esse perfil de VPN. Quando essa configuração está **Habilitada** em uma regra de NRPT, a regra permanece ativa no dispositivo, mesmo quando a VPN desconectar. A regra permanece até que o perfil de VPN seja removido ou até que a regra seja removida manualmente, o que pode ser feito com o PowerShell.

[Configurações de VPN do Windows 10](vpn-settings-windows-10.md) descreve a lista atual das configurações. 

### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user----1333642-eeready---"></a>Usar S/MIME para criptografar e assinar vários dispositivos para um usuário <!-- 1333642 eeready -->
Criptografia de email S/MIME usando um novo perfil de certificado importado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > selecione a plataforma > tipo de perfil **Certificado PKCS importado**). No Intune, você pode importar certificados no formato PFX. Em seguida, o Intune pode fornecer os mesmos certificados para vários dispositivos registrados por um único usuário. Isso também inclui:

- O perfil de email do iOS nativo permite habilitar a criptografia S/MIME usando certificados importados no formato PFX.
- O aplicativo de email nativo em dispositivos Windows Phone 10 usam automaticamente o certificado S/MIME.
- Os certificados privados podem ser entregues em várias plataformas. Porém, nem todos os aplicativos de email são compatíveis com S/MIME.
- Em outras plataformas, talvez você precise configurar manualmente o aplicativo de email para habilitar o S/MIME.  
- Os aplicativos de email compatíveis com a criptografia S/MIME podem manipular a recuperação de certificados para criptografia de email S/MIME de uma maneira com a qual o MDM não é compatível, como a leitura do repositório de certificados do editor.

Com suporte em: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="help-and-support-page-in-the-windows-company-portal-app----1488939---"></a>Página de Ajuda e Suporte no Aplicativo Portal da Empresa do Windows <!-- 1488939 -->
Uma nova página é adicionada ao aplicativo Portal da Empresa do Windows. A página de ajuda e suporte fornece informações de contato da assistência técnica. Além disso, os usuários finais podem enviar logs do Portal da Empresa, caso tenham problemas. A página também fornece uma seção de perguntas frequentes para ajudar os usuários finais.

### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Usar a detecção de rede confiável para perfis de VPN em dispositivos com Windows 10 <!-- 1500165 -->
Ao usar a detecção de rede confiável, é possível impedir que os perfis de VPN criem automaticamente uma conexão VPN quando o usuário já estiver em uma rede confiável. É possível adicionar sufixos DNS para habilitar a detecção de rede confiável em dispositivos que executam o Windows 10 e posterior (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **VPN** para o tipo de perfil).
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md) lista as configurações de VPN atuais.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>O SDK de Aplicativo do Intune oferece suporte a chaves de criptografia de 256 bits <!-- 1832174 -->
O SDK de Aplicativo do Intune para Android usa as chaves de criptografia de 256 bits quando a criptografia está habilitada por Políticas de Proteção de Aplicativo. O SDK continua a fornecer suporte a chaves de 128 bits para compatibilidade com o conteúdo e aplicativos que usam versões mais antigas do SDK.

### <a name="enabled-shared-pc-settings-in-intune-profile----1907917-1063203---"></a>Configurações de computador compartilhado habilitadas no perfil do Intune <!-- 1907917, 1063203 -->
No momento, é possível definir as configurações de computador compartilhado em dispositivos de área de trabalho do Windows 10 usando uma configuração OMA-URI personalizada. Um novo perfil é adicionado para definir as configurações de Computador compartilhado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** > **Dispositivo multiusuário compartilhado**).

Aplica-se a: Windows 10 e posteriores, Windows Holographic for Business

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Método de autenticação de atualização das políticas do Intune e instalação do aplicativo Portal da Empresa <!-- 1927359 -->
Em dispositivos já registrados por meio do Assistente de Instalação com um dos métodos de registro de dispositivo corporativo da Apple, o Intune não oferecerá mais o suporte do Portal da Empresa quando for instalado manualmente pelos usuários finais da loja de aplicativos. Essa alteração só é relevante quando você autentica com o Assistente de Configuração da Apple durante o registro. Além disso, essa alteração afeta apenas dispositivos iOS registrados via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Programa de registro de dispositivos (DEP) da Apple

Se os usuários instalarem o aplicativo Portal da Empresa pela loja de aplicativos e tentarem registrar esses dispositivos por meio do aplicativo, receberão um erro. Esses dispositivos só devem usar o Portal da Empresa quando ele for enviado por push, automaticamente, pelo Intune durante o registro. Os perfis de registro no Intune, no portal do Azure, serão atualizados para que você possa especificar como os dispositivos são autenticados, e se o usuário recebe o aplicativo Portal da Empresa. Se você quiser que os usuários de dispositivos DEP tenham o Portal da Empresa, especifique suas preferências em um perfil de registro. Além disso, a tela **Identifique o dispositivo** no aplicativo Portal da Empresa logo se tornará obsoleta.  
Para instalar o Portal da Empresa em dispositivos DEP já registrados, acesse Intune > Aplicativos cliente, e envie-o como um aplicativo gerenciado com políticas de configuração de aplicativo. Os detalhes sobre como executar essas etapas serão descritos em documentos futuros.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Aqueles que não são administradores podem habilitar o BitLocker em dispositivos com Windows 10 registrados no Azure AD<!-- 2147379 -->
Ao habilitar as configurações do BitLocker em dispositivos com Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para a plataforma > **Endpoint Protection** para o tipo de perfil > **Criptografia do Windows**), você adiciona as configurações do BitLocker. Esta atualização inclui uma nova configuração de BitLocker para permitir que os usuários padrão (não administradores) habilitem a criptografia. Para ver as configurações atuais, consulte [Configurações de proteção do ponto de extremidade para Windows 10](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-app-pin----2298397---"></a>PIN do aplicativo Intune <!-- 2298397 -->
Como administrador(a) de TI, é possível configurar o número de dias que um usuário final pode esperar até que o PIN do aplicativo Intune precise ser alterado. A nova configuração será disponibilizada no portal do Azure ao selecionar **Intune** > **Aplicativos cliente** > **Políticas de proteção do aplicativo** > **Criar política** > **Configurações** > **Requisitos de acesso**. Esse recurso será disponibilizado em dispositivos Android e iOS. Essa configuração oferece suporte a um valor inteiro positivo.

### <a name="new-windows-10-update-settings----2626030-2512994---"></a>Novas configurações de Atualização do Windows 10 <!-- 2626030 2512994 -->
Para seus Anéis de Atualização do Windows 10, é possível:
- restaurar as configurações originais de atualização automática em computadores com Windows 10 que instalaram a *Atualização de outubro de 2018*
- definir uma nova configuração de atualizações de software para bloquear ou permitir a pausa da instalação da atualização em *Configurações* nos computadores dos usuários. 



### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>Perfis de email do iOS podem usar assinatura e criptografia S/MIME <!-- 2662949 -->
É possível criar um perfil de email que inclui configurações diferentes. Isso inclui configurações de S/MIME que podem ser usadas para assinar e criptografar comunicações por email em dispositivos iOS (**Configurações do dispositivo** > **Perfis** >  **Criar perfil** > escolha **iOS** para a plataforma > **Email** para o tipo de perfil).

[Definições de configuração de email do iOS](email-settings-ios.md) lista as configurações atuais.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509---"></a>Ignorar mais telas do Assistente de Configuração em um dispositivo DEP com iOS <!-- 2687509 -->
Além das telas que você pode pular no momento, você poderá definir dispositivos iOS DEP para ignorar as telas a seguir no Assistente de Configuração, quando um usuário registrar o dispositivo: Exiba tom, Privacidade, Migração do Android, botão Página Inicial, iMessage e FaceTime, Integração, Migração de Inspeção, Aparência, Hora na Tela, Atualização de Software, Configuração do SIM.
Para escolher quais telas ignorar, acesse **Registro do dispositivo** > **Registro da Apple** > **Tokens do programa de registro** > escolha um token > **Perfis** > escolha um perfil > **Propriedades** > **Personalização do Assistente de Configuração** > escolha **Ocultar** para as telas que você deseja ignorar > **OK**.

### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Algumas configurações do BitLocker oferecem suporte à edição Windows 10 Pro<!-- 2727036 -->
É possível criar um perfil de configuração que define as configurações de proteção do ponto de extremidade em dispositivos com Windows 10, incluindo o BitLocker. Isso adiciona suporte ao Windows 10 Professional para algumas configurações do BitLocker. Para ver as configurações atuais do Windows 10, consulte [Configurações de proteção do ponto de extremidade para Windows 10](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-device-reporting-fields----2748738---"></a>Campos de relatório de dispositivo do Intune <!-- 2748738 -->
O Intune fornece campos adicionais de informações sobre o dispositivo, incluindo o fabricante, o modelo e a versão do patch de segurança do Android, bem como o modelo do iOS. No Intune, esses campos estão disponíveis ao selecionar **Aplicativos cliente** > **Status de Proteção do Aplicativo** e **Relatório de proteção do aplicativo: iOS, Android**. Além disso, esses parâmetros ajudam a configurar a lista **Permissão** para o fabricante do dispositivo (Android), a lista **Permissão** para o modelo do dispositivo (Android e iOS) e a configuração de versão mínima do patch de segurança do Android. 

### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal----2809362---"></a>A configuração de dispositivos compartilhados foi renomeada para Mensagem de Tela de Bloqueio para dispositivos iOS no portal do Azure <!-- 2809362 -->
Ao criar um perfil de configuração para dispositivos iOS, é possível adicionar ajustes de **Configuração de Dispositivo Compartilhado** para mostrar um texto específico na tela de bloqueio. Isso inclui estas alterações: 

- A **Configuração de Dispositivo Compartilhado** no portal do Azure foi renomeada para "Mensagem na Tela de Bloqueio (apenas supervisionada)" (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > escolha **iOS** para a plataforma > escolha **Recursos do dispositivo** para o tipo de perfil > **Mensagem na Tela de Bloqueio**).
- Ao adicionar mensagens na tela de bloqueio, é possível inserir um número de série, um nome de dispositivo ou outro valor específico ao dispositivo como variável em **Informações de marca do ativo**. Por exemplo, é possível inserir `Device name: {{device name}}` ou `Serial number is {{serial number}}` usando colchetes. [Tokens de iOS](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) lista os tokens disponíveis que podem ser usados.

[Configurações para exibir mensagens na tela de bloqueio](shared-device-settings-ios.md) lista as configurações atuais.

### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564--"></a>Mensagem mais detalhada sobre a falha de restrição de registro <!-- 3111564-->
Você verá mensagens de erro mais detalhadas quando as restrições de registro não forem atendidas. Para ver essas mensagens, acesse **Intune** > **Solucionar problemas** e verifique a tabela Falhas de registro.

### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Novas configurações de notificação, dicas e keyguard para dispositivos do Android Enterprise<!-- 3201839 3201843 -->
Esta atualização inclui vários recursos novos em dispositivos com Android Enterprise durante a execução como proprietário do dispositivo. Para usar esses recursos, acesse **Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma**, escolha **Android Enterprise** > em **Tipo de perfil**, escolha **Somente proprietário do dispositivo** > **Restrições do Dispositivo**.
Os novos recursos incluem: 
- Desabilitar a exibição de notificações do sistema, incluindo chamadas recebidas, alertas do sistema, erros de sistema e muito mais
- Sugestão de ignorar os tutoriais iniciais e as dicas para aplicativos abertos pela primeira vez
- Desabilitar as configurações avançadas de keyguard, como câmera, notificações, impressão digital para desbloqueio e muito mais

Para ver as configurações atuais, acesse [Configurações de restrição de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).

### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Dispositivos de proprietário com Android Enterprise podem usar conexões VPN Always On <!-- 3202194 -->
Nesta atualização, é possível usar as conexões VPN Sempre Ativa em dispositivos com Android Enterprise. As conexões VPN sempre ativadas permanecem conectadas ou são reconectadas imediatamente quando o usuário desbloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. Você também pode colocar a conexão em modo de "bloqueio", o que bloqueia todo o tráfego até que a conexão VPN seja ativada.
É possível habilitar a VPN Sempre Ativa em **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android Enterprise** para plataforma > **Restrições de dispositivo** para Somente Proprietário do Dispositivo > **Conectividade**. Para ver as configurações atuais, acesse [Configurações de restrição de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).

### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nova configuração para encerrar processos no Gerenciador de Tarefas em dispositivos com Windows 10 <!-- 3285177 --> 
Esta atualização inclui uma nova configuração para encerrar processos usando o Gerenciador de Tarefas em dispositivos com Windows 10. Usando um perfil de configuração do dispositivo (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > em **Plataforma** , escolha **Windows 10** > no **Tipo de perfil**, escolha **Restrições de dispositivo** > **Geral**), é possível permitir ou impedir essa configuração.
Para ver as configurações atuais, acesse [Configurações de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md).
Aplica-se a: Windows 10 e posterior

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Os modelos administrativos estão em versão prévia pública e mudaram para o perfil de configuração próprio <!-- 3322847 -->
Os modelos administrativos no Intune (**Configuração do dispositivo** > **Modelos administrativos**) estão em versão prévia privada. Com esta atualização: Modelos administrativos incluem aproximadamente 300 configurações que podem ser gerenciadas no Intune. Anteriormente, essas configurações só existiam no editor de política de grupo.
Os modelos administrativos estão disponíveis na versão prévia pública. Os modelos administrativos estão mudando de **Configuração do dispositivo** > **Modelos administrativos** para **Configuração do dispositivo** > **Perfis** >**Criar perfil** > em **Plataforma**, escolha **Windows 10 e posterior**, em **Tipo de perfil**, escolha **Modelos administrativos**.
A criação de relatórios está habilitada. Aplica-se a: Windows 10 e posterior

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Modo Escuro do Portal da Empresa do Intune no macOS <!-- 3300524 -->
O Portal da Empresa do Intune no macOS agora dá suporte ao Modo Escuro para macOS. Quando você habilitar o Modo Escuro em um dispositivo macOS 10.14 ou superior, o Portal da Empresa ajustará sua aparência de acordo com as cores para refletir o modo.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Usar configurações recomendadas pela Microsoft com linhas de base de segurança <!-- 2055484 -->
O Intune integra-se a outros serviços que têm foco na segurança, incluindo o Windows Defender ATP e o Office 365 ATP. Os clientes estão solicitando uma estratégia comum e um conjunto coeso de fluxos de trabalho de segurança de ponta a ponta entre os serviços do Microsoft 365. Nossa meta é alinhar estratégias para criar soluções que façam a ponte entre operações de segurança e tarefas comuns do administrador. No Intune, nosso objetivo é atingir essa meta publicando um conjunto de "Linhas de base de segurança" recomendadas pela Microsoft (**Intune** > **Linhas de base de segurança**).  Um administrador poderá criar políticas de segurança diretamente com base nessas linhas de base e implantá-las para seus usuários. Eles também poderão personalizar as recomendações de melhores práticas para atender às necessidades de sua organização. O Intune garante que os dispositivos estejam em conformidade com essas linhas de base e notifica os administradores de usuários ou dispositivos que não estão em conformidade.

### <a name="scope-tags-for-apps---1081941---"></a>Marcas de escopo para aplicativos <!--1081941 -->
Você poderá criar marcas de escopo para limitar o acesso aos recursos do Intune. Adicione uma marca de escopo a uma atribuição de função e, em seguida, adicione a marca de escopo a um perfil de configuração. A função só terá acesso a recursos com perfis de configuração que tenham marcas de escopo correspondentes (ou nenhuma marca de escopo).
Para criar uma marca de escopo, escolha **Funções do Intune** > **Escopo (Marcas)** > **Criar**.
Para adicionar uma marca de escopo a uma atribuição de função, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de Política e Perfil** > **Atribuições** > **Escopo (Marcas)**.
Para adicionar uma marca de escopo a um perfil de configuração, escolha **Configuração do dispositivo** > **Perfis** > escolha um perfil > **Propriedades** > **Escopo (Marcas)**.

### <a name="tenant-health-dashboard----1124854---"></a>Painel de Integridade do Locatário <!-- 1124854 -->
A página Status do Locatário no Intune fornecerá informações de status do locatário em um único lugar. A página está dividida em quatro seções:  
- **Detalhes do locatário**: Contém informações, como sua Autoridade de MDM, o total de dispositivos registrados no seu locatário e contagens de suas licenças. Esta seção também fornece a versão de serviço atual do seu locatário.
- **Status do Conector**: Contém informações para conectores configurados, como o VPP da Apple, Windows Store para Empresas e conectores de certificado. Com base em seu estado atual, os conectores são sinalizados como *Íntegro*, *Aviso* ou *Não íntegro*.
- **Integridade do Serviço do Intune**: Contém incidentes ativos ou interrupções para o seu locatário. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office ([https://portal.office.com](https://portal.office.com)).
- **Notícias sobre o Intune**: Contém mensagens ativas para seu locatário, que inclui itens como notificações de que seu locatário recebeu os recursos mais recentes do Intune. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Políticas de WIP implantadas sem o registro do usuário <!-- 1434452 -->
Políticas de WIP (Proteção de Informações do Windows) poderão ser implantadas sem que os usuários do MDM registrem seu dispositivo Windows 10. Essa configuração permite que as empresas protejam seus documentos corporativos com base na configuração do WIP, enquanto permitem que o usuário mantenha o gerenciamento dos seus próprios dispositivos Windows. Depois que os documentos forem protegidos com uma política de WIP, os dados protegidos poderão ser apagados seletivamente por um administrador do Intune. Selecionando o usuário e o dispositivo, e enviando uma solicitação de apagamento, todos os dados protegidos por meio da política de WIP ficarão inutilizáveis. No Intune no portal do Azure, selecione **Aplicativo móvel** > **Apagamento seletivo do aplicativo**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações de APP (Política de Proteção de Aplicativo) do aplicativo para dados Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token de VPP da Apple usado por outro MDM <!-- 1488946 -->
O Intune detectará e mostrará detalhes se um token do VPP (Apple Volume Purchase Program) estiver sendo usado tanto pelo Intune quanto por outro MDM.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Dispositivos desativados no painel de conformidade de dispositivos <!-- 1981119 -->
Em uma atualização futura, os dispositivos desativados serão removidos do painel de conformidade de dispositivos. Com isso, seus números de conformidade serão alterados.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Alteração no processo de atualização de conectores locais <!-- 2277554 -->
Com base nos comentários dos clientes, a maneira em que as atualizações são feitas nos conectores locais será alterada. Depois que você instalar um conector local inicialmente, as atualizações passarão a ocorrer automaticamente. Essa alteração começará com o novo conector de certificado PFX para Microsoft Intune e, posteriormente, será distribuída a outros tipos de conectores locais. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Conferir a conformidade do Configuration Manager <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O Configuration Manager envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores



## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.



