---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 62028232e4d6c9ab20a05480811978234ed0a3c1
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---may-2018"></a>A Edição Antecipada do Microsoft Intune – maio de 2018

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

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Suporte para perfis de VPN GlobalProtect da Palo Alto Networks <!-- 1333680 eeready ! -->

Com essa atualização, você pode escolher o GlobalProtect da Palo Alto Networks como um tipo de conexão VPN para perfis VPN no Intune (**Configuração do dispositivo** > **Perfis**  >  **Criar perfil** > **Tipo de perfil** > **VPN**). Nesta versão, há suporte para as seguintes plataformas: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Definir a conformidade de acordo com a localização do dispositivo <!-- 851881 ! -->
Em algumas situações, convém restringir o acesso aos recursos corporativos a uma localização específica, definida por uma conexão de rede. Você poderá criar uma política de conformidade (**Conformidade do dispositivo** > **Locais**) com base no endereço IP do dispositivo. Se o dispositivo sair do intervalo de IP, ele não poderá mais acessar os recursos corporativos.

Aplica-se a: dispositivos Android 6.0 e superiores, com o aplicativo Portal da Empresa atualizado

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Solução aprimorada de problemas de instalação do aplicativo <!-- 928990 -->
Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. Estamos enviando uma Visualização Pública dos nossos recursos de Solução de Problemas de Aplicativo. Você observará um novo nó em cada dispositivo individual com o nome **Aplicativos Gerenciados**. Ele lista os aplicativos que foram entregues por meio do MDM do Intune. Dentro do nó, você verá uma lista dos estados de instalação do aplicativo. Se você selecionar um aplicativo individual, verá o modo de exibição de solução de problemas desse aplicativo específico. Na exibição de solução de problemas, você verá o ciclo de vida completo do aplicativo, por exemplo, quando o aplicativo foi criado, modificado, direcionado e entregue a um dispositivo. Além disso, se a instalação do aplicativo não for bem-sucedida, você receberá o código de erro e uma mensagem útil sobre a causa do erro. 

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquear acesso do aplicativo com base em modelos e fornecedores de dispositivos não aprovados <!-- 1425689 ! -->
O administrador de TI do Intune será capaz de impor uma lista especificada de fabricantes Android e/ou modelos de iOS por meio das Políticas de Proteção de Aplicativo do Intune. O administrador de TI pode fornecer uma lista separada por ponto e vírgula de fabricantes para políticas do Android e de modelos de dispositivos para políticas do iOS. As Políticas de Proteção de Aplicativo do Intune servem apenas para Android e iOS. Haverá duas ações diferentes que podem ser executadas nessa lista especificada:
- Um bloqueio de acesso do aplicativo em dispositivos que não estão especificados.
- Ou uma limpeza seletiva de dados corporativos em dispositivos que não estão especificados. 

O usuário não conseguirá acessar o aplicativo direcionado se os requisitos por meio da política não forem atendidos. Com base nas configurações, o usuário pode ser bloqueado ou passar por uma limpeza seletiva dos dados corporativos no aplicativo. Em dispositivos iOS, esse recurso exige a participação de aplicativos (por exemplo, WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune para as configurações de versão mínima serem impostas aos aplicativos direcionados. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. No Android, esse recurso exige a versão mais recente do Portal da Empresa.

Em dispositivos de usuário final, o cliente do Intune executaria uma ação com base em uma correspondência simples das cadeias de caracteres especificadas na folha do Intune para Políticas de Proteção de Aplicativo. Isso depende totalmente do valor informado pelo dispositivo. Por isso, o administrador de TI é incentivado a garantir que o comportamento desejado seja preciso. Isso pode ser feito testando essa configuração com base em vários fabricantes e modelos de dispositivo direcionados a um grupo de usuários pequeno. No Microsoft Intune, selecione **Aplicativos Móveis** > **Políticas de proteção de aplicativo** para exibir e adicionar as políticas de proteção de aplicativo. Para saber mais sobre políticas de proteção de aplicativo, confira [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Habilitar o modo de quiosque em dispositivos com Windows 10 <!-- 1560072 ! -->
Em dispositivos com Windows 10, você pode criar um perfil de configuração e habilitar o modo de quiosque (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** > **Restrições do Dispositivo** > **Quiosque**). Nesta atualização, a configuração **Quiosque (visualização)** é renomeada para **Quiosque (obsoleto)**. **Quiosque (obsoleto)** não é mais recomendado para uso, mas continuará a funcionar até a atualização de julho. **Quiosque (obsoleto)** é substituído pelo novo tipo de perfil **Quiosque** (**Criar perfil** > **Windows 10** > **Quiosque (versão prévia)**), que conterá as configurações de quiosques no Windows 10 RS4 e versões posteriores.

Aplica-se ao Windows 10 e posteriores.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Recuperar a AUMID (ID de modelo de usuário do aplicativo associado) para aplicativos da Microsoft Store para Empresas no modo de quiosque <!-- 1560077 ! -->
O Intune poderá recuperar as AUMIDs (IDs de modelo de usuário do aplicativo) para aplicativos WSfB (Microsoft Store para Empresas) a fim de melhorar a configuração do perfil de quiosque.

Para saber mais sobre aplicativos da Microsoft Store para Empresas, confira [Gerenciar aplicativos da Microsoft Store para Empresas](windows-store-for-business.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Ações de acesso para políticas de proteção de aplicativo <!-- 1483510 EEready -->
Logo, você poderá configurar políticas de proteção de aplicativo para apagar, bloquear ou avisar explicitamente os dispositivos não compatíveis. A ação mais recente, *apagar*, remove os dados corporativos de um dispositivo. Se ocorrer uma limpeza, o usuário do dispositivo receberá uma notificação sobre o motivo da limpeza e etapas de remediação. Para algumas configurações, como a versão mínima do sistema operacional, você poderá aplicar várias ações, como bloquear e apagar.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Novas informações de inventário para dispositivos com Windows <!-- 1333569 eeready -->

Para dispositivos com Windows, as seguintes informações de inventário estarão disponíveis por dispositivo na guia **Hardware** (**Grupos** > **Todos os dispositivos móveis** > **Dispositivos** > escolha o dispositivo do usuário > **Exibir Propriedades** > **Hardware**):
- TPM
- Integração com antivírus
- AntiSpyware
- Firewall
- UAC
- Bateria
- Nome do domínio

Para saber mais sobre como esses dados são recuperados pelo CSP, confira as entradas de DeviceGuard no artigo [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp).

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune e o navegador Microsoft Edge <!-- 1818969 -->
O navegador Microsoft Edge para dispositivos móveis (iOS e Android) agora dá suporte a políticas de proteção de aplicativos do Intune. Os usuários que entrarem com suas contas corporativas do Azure AD no aplicativo Edge estarão protegidos pelo Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nova configuração de idioma/região ao configurar o OOBE para Autopilot <!-- 1821766 -->
Uma nova definição de configuração estará disponível para definição do idioma e da região para perfis do Autopilot durante a configuração inicial pelo usuário.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nova configuração para o teclado do dispositivo <!-- 1821768 -->
Uma nova configuração estará disponível para definição do teclado para perfis do Autopilot durante a configuração inicial pelo usuário.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Use o TeamViewer para compartilhar a tela de dispositivos iOS e MacOS <!-- 1985547 -->
No momento, você pode usar o TeamViewer para administrar remotamente [dispositivos Android e Windows gerenciados pelo Intune](device-profile-android-teamviewer.md).

Os administradores poderão se conectar ao TeamViewer e iniciar uma sessão de compartilhamento de tela com dispositivos iOS e macOS. Usuários do iPhone, iPad e macOS podem compartilhar suas telas ao vivo com qualquer desktop ou dispositivo móvel. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>O gráfico de perfil do dispositivo do usuário está de volta <!-- 2160133 -->
Durante o aprimoramento das contagens numéricas exibidas no gráfico de perfil do dispositivo (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral** ), o gráfico de usuário gráfico foi temporariamente removido.

Com essa atualização, o gráfico de usuário está de volta, e é exibido no Portal do Azure.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Atribua todos os usuários e dispositivos como grupos de escopo <!-- 2196803 -->
Você poderá atribuir todos os usuários e dispositivos aos grupos de escopo.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Perfis do AutoPilot passando para grupo direcionado a <!-- 1877935 -->
No momento, perfis de implantação do AutoPilot podem ser atribuídos a dispositivos selecionados. Após o lançamento desse recurso, você fará o seguinte para atribuir esses perfis:
- Criar grupos (Azure AD) contendo dispositivos AutoPilot
- Atribua os perfis desejados a um grupo do Azure AD. O perfil AutoPilot agora será atribuído a dispositivos AutoPilot naquele grupo.

### <a name="management-name-field-will-be-editable----1875989---"></a>O campo Nome de gerenciamento poderá ser editado <!-- 1875989 -->
Você poderá editar o campo de nome de gerenciamento na folha **Propriedades** de um dispositivo. Para editar esse campo, escolha **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo > **Propriedades**. Use o campo de nome de gerenciamento para identificar exclusivamente um dispositivo.

<!-- 1804 start -->


### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Adições às configurações das opções de segurança do dispositivo local <!-- 1403702 -->
Você poderá definir as configurações adicionais de Opções de Segurança de Dispositivo Local para dispositivos Windows 10. Configurações adicionais estarão disponíveis nas áreas de Cliente de Rede da Microsoft, Servidor de Rede Microsoft, Acesso e segurança de rede e Logon interativo. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Requer a instalação de perfis de políticas, aplicativos, certificado e rede <!-- 1553555 -->
Os administradores poderão impedir que usuários finais acessem a área de trabalho do Windows 10 RS4 até que o Intune instale políticas, aplicativos e perfis de certificado e de rede durante o provisionamento de dispositivos AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estarão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de remoção de dispositivo**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Impedir aplicativos e experiências de consumidor em dispositivos Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Você poderá impedir a instalação de aplicativos e experiências de consumidor nos seus dispositivos Windows 10 Enterprise RS4 AutoPilot. Para ver esse recurso, vá para **Intune** > **Registro de dispositivo** > **Registro do Windows** > **Perfis do Windows AutoPilot** > **Criar Novo** > **Configurações de registro**. 

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

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
