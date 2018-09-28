---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/4/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: beee1462c1b6e683287b4d304df386ce525be820
ms.sourcegitcommit: 8fdddb684ecf5eabf071907168413bcd89a2f702
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141621"
---
# <a name="the-early-edition-for-microsoft-intune---september-2018"></a>A edição antecipada do Microsoft Intune – setembro de 2018

> [!Note]
> Notificação sobre o NDA: as alterações a seguir estão em desenvolvimento para o Intune. Essas informações são compartilhadas nos termos do NDA de forma muito limitada. Não poste nenhuma dessas informações em mídia social nem em sites públicos, como Twitter, UserVoice, Reddit e assim por diante. 

A **edição antecipada** fornece uma lista de recursos, compartilhados nos termos do NDA, que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não tweet, poste no UserVoice nem compartilhe de nenhuma outra forma essas informações fora de sua empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1809 start -->

### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices-----1248496----"></a>O acesso à conta de usuário de aplicativos do Intune em dispositivos Android e iOS gerenciados <!-- ! 1248496  -->

Como administrador do Microsoft Intune, você poderá controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. Você poderá limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. 

### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10----1333668---"></a>Criar sufixos DNS em perfis de configuração de VPN em dispositivos que executam o Windows 10 <!-- 1333668 -->
Quando você cria um perfil de configuração do dispositivo VPN (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **plataforma Windows 10 ou posterior** > O tipo de perfil **VPN**), insere algumas configurações de DNS. Você também poderá inserir vários **sufixos DNS** no Intune. Ao usar sufixos DNS, você pode procurar um recurso de rede usando o nome curto dele em vez do nome de domínio totalmente qualificado (FQDN). Essa atualização também permite alterar a ordem dos sufixos DNS no Intune.
[Configurações de VPN do Windows 10](vpn-settings-windows-10.md#dns-settings) lista as configurações DNS atuais.
Aplica-se a: dispositivos Windows 10

### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Suporte para VPN sempre ativado em perfis de trabalho do Android <!-- 1333705 -->
Você poderá usar as conexões VPN sempre ativadas em dispositivos Android corporativos com perfis de trabalho gerenciados. As conexões VPN sempre ativadas permanecem conectadas ou são reconectadas imediatamente quando o usuário desbloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. Você também pode colocar a conexão em modo de "bloqueio", o que bloqueia todo o tráfego até que a conexão VPN seja ativada.
A configuração de VPN Always-on estará em **Configuração do dispositivo** > **Perfis** > **Criar perfil** >  **Android Enterprise** para plataforma > **Restrições de dispositivo** em **Apenas Perfis de Trabalho** para O tipo de perfil > configurações de **Conectividade**. 

### <a name="outlook-for-ios-and-android-app-configuration-policy---1828527---"></a>Política de configuração de aplicativo do Outlook para iOS e Android <!--1828527 -->
Você poderá criar para o iOS uma política de configuração do aplicativo Outlook para iOS e Android. Outras definições de configuração serão adicionadas à medida que forem habilitadas no Outlook para iOS e Android.

### <a name="remotely-lock-noncompliant-devices----2064495---"></a>Bloquear remotamente dispositivos não compatíveis <!-- 2064495 -->
Quando um dispositivo não for compatível, você poderá criar uma ação na política de conformidade que bloqueia o dispositivo remotamente. Em Intune > **Conformidade do dispositivo**, crie uma nova política ou selecione uma política de conformidade existente. Selecione **Ações em caso de não conformidade** > **Adicionar** e opte por bloquear remotamente o dispositivo.
Com suporte em: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 e posterior 

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Configurações de transferência de dados de aplicativo do Intune em dispositivos iOS de MDM registrados <!-- 2244713 -->
Você poderá separar o controle de configurações de transferência de dados de aplicativo do Intune em dispositivos iOS de MDM registrados da especificação de identidade do usuário registrado. Os administradores que não estiverem usando o IntuneMAMUPN não observarão uma alteração de comportamento. Quando essa funcionalidade estiver disponível, os administradores que estiverem usando o IntuneMAMUPN para controlar o comportamento de transferência de dados em dispositivos registrados deverão revisar as novas configurações e atualizar as configurações de aplicativo conforme necessário.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Usar uma chave pré-compartilhada em um perfil de Wi-Fi do Windows 10 <!-- 2662938 -->
Você poderá usar uma chave pré-compartilhada (PSK) com o protocolo de segurança WPA/WPA2-Personal para autenticar um perfil de configuração de Wi-Fi no Windows 10.
No momento, é preciso importar um perfil de Wi-Fi ou criar um perfil personalizado para usar uma chave pré-compartilhada. [Configurações de Wi-Fi no Windows 10](wi-fi-settings-windows.md) lista as configurações atuais. 

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>A frequência de sincronização de dispositivos Autopilot passa a ser a cada 12 horas <!-- 2753673 -->
Os dispositivos Autopilot serão sincronizados a cada 12 horas, não mais a cada 24 horas.

### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Aplicar perfil do Autopilot a dispositivos Windows 10 registrados que ainda não estiverem registrados no Autopilot <!-- 1558983 -->
É possível aplicar perfis do Autopilot a dispositivos Windows 10 registrados que ainda não estiverem registrados no Autopilot. No perfil do Autopilot, escolha a opção **Converter todos os dispositivos de destino em Autopilot** para registrar automaticamente dispositivos não Autopilot no serviço de implantação do Autopilot. Aguarde 48 horas para que o registro seja processado. Quando o registro do dispositivo é cancelado e redefinido, o Autopilot o provisiona. 

### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564--"></a>Criar e atribuir vários perfis de Página de Status de Registro para grupos do Azure AD <!-- 2526564-->
Será possível criar e atribuir vários perfis de Página de Status de Registro para grupos de usuários do Azure AAD.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>As atualizações na página de aterrissagem do Intune e renomeação de nó <!--2867309 -->
As atualizações na página de aterrissagem do Intune incluirão novos e alterados blocos de monitoramento e gráficos para melhor visualização dos dados. O nó **Aplicativos móveis** será alterado para **Aplicativos cliente**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Maior acesso do usuário final usando o aplicativo do Portal da Empresa <!-- 772203 -->
Os usuários finais poderão acessar ações de conta principal, como a redefinição de senha e o perfil do AAD, pelo aplicativo de Portal da Empresa.

### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Emitir certificados SCEP para dispositivos sem usuário <!-- 1744554 -->
Atualmente, os certificados são emitidos para usuários. Será possível emitir certificados SCEP para dispositivos, incluindo dispositivos sem usuário, como quiosques (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Certificado SCEP** para perfil). As outras atualizações incluirão:
- A propriedade **Assunto** em um perfil SCEP agora é uma caixa de texto personalizada e pode incluir novas variáveis. 
- A propriedade **Nome alternativo da entidade (SAN)** em um perfil SCEP agora é um formato de tabela e pode incluir novas variáveis. Na tabela, um administrador pode adicionar um atributo e preencher o valor em uma caixa de texto personalizada. A SAN será compatível com os seguintes atributos: 
  - DNS
  - Endereço de email
  - UPN Essas novas variáveis podem ser adicionadas com texto estático em uma caixa de texto de valor personalizada. Por exemplo, o atributo DNS pode ser adicionado como `DNS = {{AzureADDeviceId}}.domain.com`.
  > [!NOTE]
  > Os símbolos de chaves, ponto e vírgula e barra vertical “ { } ; | ” não funcionarão no texto estático da SAN. Apenas uma das novas variáveis de certificado do dispositivo a serem aceitas para `Subject` ou `Subject alternative name` devem ser colocadas entre chaves. Novas variáveis de certificado do dispositivo:  
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



<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token de VPP da Apple usado por outro MDM <!-- 1488946 -->
O Intune detectará e mostrará detalhes se um token do VPP (Apple Volume Purchase Program) estiver sendo usado tanto pelo Intune quanto por outro MDM.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>O número de versão e o número de build do iOS são mostrados <!-- 1892471 -->
Em **Conformidade de dispositivos** > **Conformidade de dispositivos**, a versão do sistema operacional iOS é mostrada. Em uma atualização futura, o número de build também será mostrado.
Quando são lançadas atualizações de segurança, a Apple normalmente mantém o número de versão no estado em que se encontra, mas atualiza o número de build. Exibindo o número de build, você pode verificar facilmente se uma atualização de vulnerabilidade está instalada.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Dispositivos desativados no painel de conformidade de dispositivos <!-- 1981119 -->
Em uma atualização futura, os dispositivos desativados serão removidos do painel de conformidade de dispositivos. Com isso, seus números de conformidade serão alterados.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Alteração no processo de atualização de conectores locais <!-- 2277554 -->
Com base nos comentários dos clientes, a maneira em que as atualizações são feitas nos conectores locais será alterada. Depois que você instalar um conector local inicialmente, as atualizações passarão a ocorrer automaticamente. Essa alteração começará com o novo conector de certificado PFX para Microsoft Intune e, posteriormente, será distribuída a outros tipos de conectores locais. 

### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224-eeready---"></a>Melhorias no perfil de quiosque em Windows 10 e posterior no Portal do Azure <!-- 2748224 eeready -->
O perfil de configuração de dispositivo quiosque do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Versão prévia do quiosque** para tipo de perfil) receberá melhorias: 
- Atualmente, você pode criar vários perfis de quiosque no mesmo dispositivo. Com essa atualização, o Intune dará suporte somente a um perfil de quiosque por dispositivo. Se você ainda precisar de vários perfis de quiosque em um único dispositivo, poderá usar um URI personalizado.
-Em um perfil de **Quiosque de vários aplicativos**, você pode selecionar o tamanho do bloco de aplicativos e a ordem do **layout do menu Iniciar** na grade de aplicativos. Se você preferir mais personalização, poderá fazer o upload de um arquivo XML.
- As configurações do navegador de quiosque serão movidas para as configurações de **Quiosque**. Atualmente, as configurações de **Navegador da Web de quiosque** têm sua categoria própria no Portal do Azure.
Aplica-se ao Windows 10 e posteriores

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Melhoria na experiência do aplicativo Portal da Empresa para os usuários gerentes de registros de dispositivo <!-- 675800 -->
Quando um DEM (gerente de registros de dispositivo) entra no aplicativo Portal da Empresa para Windows, o aplicativo lista apenas o dispositivo em execução atual do DEM. Essa melhoria reduz os tempos limite que ocorriam anteriormente quando o aplicativo tentava carregar todos os dispositivos registrados pelo DEM.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Conferir a conformidade do Configuration Manager <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O Configuration Manager envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token do VPP ou de licença do Portal da Empresa quase acabando <!-- 2237572 -->
Se você usar o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem quase acabando.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Configurações de segurança adicionais para o Windows Installer <!-- 2282430 -->
Você poderá permitir que os usuários controlem as instalações de aplicativo. Se habilitadas, as instalações que, de outra forma, poderiam ser interrompidas devido a uma violação de segurança teriam permissão para continuar. Você poderá instruir o Windows Installer a usar permissões elevadas quando ele instalar um programa em um sistema. Além disso, você poderá permitir que os itens da WIP (Proteção de Informações do Windows) sejam indexados e os metadados sobre eles, armazenados em um local não criptografado. Quando a política for desabilitada, os itens protegidos pela WIP não serão indexados e não serão exibidos nos resultados da Cortana ou no Explorador de Arquivos. A funcionalidade dessas opções estará desabilitada por padrão. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Teclados de terceiros podem ser bloqueados por configurações de APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune poderão bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivos. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

<!-- 1805 start -->

### <a name="require-non-biometric-after-specified-timeout----1506985---"></a>Exigir PIN não biométrico após um limite de tempo especificado <!-- 1506985 --> 

Ao exigir um PIN não biométrico após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

<!-- 1803 start -->

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Atualizando a experiência de Ajuda e Comentários no aplicativo Portal da Empresa para Android <!--1631531 -->

Atualizaremos as experiências de Ajuda e Comentários no aplicativo Portal da Empresa para Android para alinhá-las às práticas recomendadas para aplicativos Android. Atualizaremos o aplicativo Portal da Empresa para Android nos próximos meses para dividir o item de menu **Ajuda e Comentários** nos itens **Ajuda** e **Enviar Comentário** separados. A página **Ajuda** conterá com uma seção de **Perguntas Frequentes** e um botão **Suporte por Email** para instruir os usuários finais a carregar logs para a Microsoft e enviar email para o suporte da empresa descrevendo o problema. **Enviar Comentários** guiará o usuário por um envio de comentários padrão da Microsoft, que solicitará ao usuário escolher entre “Gosto de algo”, “ Não gosto de algo” ou “Tenho uma ideia”.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.



