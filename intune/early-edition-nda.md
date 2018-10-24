---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72585982cd27962981f581a99f0ea361642df0ee
ms.sourcegitcommit: ba0699cc351954960b222223c60c4ecd50edc829
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49652131"
---
# <a name="the-early-edition-for-microsoft-intune---october-2018"></a>A edição antecipada do Microsoft Intune – Outubro de 2018

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

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Usar configurações recomendadas pela Microsoft com linhas de base de segurança <!-- 2055484 -->
O Intune integra-se a outros serviços que têm foco na segurança, incluindo o Windows Defender ATP e o Office 365 ATP. Os clientes estão solicitando uma estratégia comum e um conjunto coeso de fluxos de trabalho de segurança de ponta a ponta entre os serviços do Microsoft 365. Nossa meta é alinhar estratégias para criar soluções que façam a ponte entre operações de segurança e tarefas comuns do administrador. No Intune, nosso objetivo é atingir essa meta publicando um conjunto de "Linhas de base de segurança" recomendadas pela Microsoft (**Intune** > **Linhas de base de segurança**).  Um administrador poderá criar políticas de segurança diretamente com base nessas linhas de base e implantá-las para seus usuários. Eles também poderão personalizar as recomendações de melhores práticas para atender às necessidades de sua organização. O Intune garante que os dispositivos estejam em conformidade com essas linhas de base e notifica os administradores de usuários ou dispositivos que não estão em conformidade.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices----1048100---"></a>Suporte de piloto automático para dispositivos ingressados no Azure Active Directory híbrido <!-- 1048100 -->
Será possível configurar dispositivos ingressados no Azure Active Directory híbrido usando o Autopilot. Os dispositivos devem ser ingressados na rede da sua organização para usar o recurso Autopilot híbrido.

### <a name="scope-tags-for-apps---1081941---"></a>Marcas de escopo para aplicativos <!--1081941 -->
Você poderá criar marcas de escopo para limitar o acesso aos recursos do Intune. Adicione uma marca de escopo a uma atribuição de função e, em seguida, adicione a marca de escopo a um perfil de configuração. A função só terá acesso a recursos com perfis de configuração que tenham marcas de escopo correspondentes (ou nenhuma marca de escopo).
Para criar uma marca de escopo, escolha **Funções do Intune** > **Escopo (Marcas)** > **Criar**.
Para adicionar uma marca de escopo a uma atribuição de função, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de Política e Perfil** > **Atribuições** > **Escopo (Marcas)**.
Para adicionar uma marca de escopo a um perfil de configuração, escolha **Configuração do dispositivo** > **Perfis** > escolha um perfil > **Propriedades** > **Escopo (Marcas)**.

### <a name="tenant-health-dashboard----1124854---"></a>Painel de Integridade do Locatário <!-- 1124854 -->
A página Status do Locatário no Intune fornecerá informações de status do locatário em um único lugar. A página está dividida em quatro seções:  
- **Detalhes do locatário**: contém informações, como sua Autoridade de MDM, o total de dispositivos registrados no seu locatário e contagens de suas licenças. Esta seção também fornece a versão de serviço atual do seu locatário.
- **Status do conector**: contém informações para conectores configurados, como o VPP da Apple, Windows Store para Empresas e conectores de certificado. Com base em seu estado atual, os conectores são sinalizados como *Íntegro*, *Aviso* ou *Não íntegro*.
- **Integridade do serviço do Intune**: contém incidentes interrupções ativos do seu locatário. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office ([https://portal.office.com](https://portal.office.com)).
- **Notícias sobre o Intune**: contém mensagens ativas para seu locatário, que inclui itens como notificações de que seu locatário recebeu os recursos mais recentes do Intune. As informações desta seção são recuperadas diretamente do Centro de Mensagens do Office ([https://portal.office.com](https://portal.office.com)).

### <a name="enrollment-abandonment-report----1382924---"></a>Relatório de abandono de registro <!-- 1382924 -->
Um novo relatório que fornece detalhes sobre registros abandonados estará disponível em **Registro de dispositivo** > **Monitorar**.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Políticas de WIP implantadas sem o registro do usuário <!-- 1434452 -->
Políticas de WIP (Proteção de Informações do Windows) poderão ser implantadas sem que os usuários do MDM registrem seu dispositivo Windows 10. Essa configuração permite que as empresas protejam seus documentos corporativos com base na configuração do WIP, enquanto permitem que o usuário mantenha o gerenciamento dos seus próprios dispositivos Windows. Depois que os documentos forem protegidos com uma política de WIP, os dados protegidos poderão ser apagados seletivamente por um administrador do Intune. Selecionando o usuário e o dispositivo, e enviando uma solicitação de apagamento, todos os dados protegidos por meio da política de WIP ficarão inutilizáveis. No Intune no portal do Azure, selecione **Aplicativo móvel** > **Apagamento seletivo do aplicativo**.


### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Adicionar imagem de marca personalizada para o aplicativo do Portal da Empresa <!-- 1916266 -->
Como administrador do Microsoft Intune, você poderá fazer upload de uma imagem de marca personalizada que será exibida como uma imagem de tela de fundo na página do perfil do usuário no aplicativo do Portal da Empresa. Para obter mais informações sobre como configurar o aplicativo do Portal da Empresa, confira [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](company-portal-app.md).

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Agrupar dispositivos registrados no Windows Autopilot por ID de correlação <!-- 2075110 -->
O Intune dará suporte ao agrupamento de dispositivos Windows por uma ID de correlação quando registrado usando o [Autopilot para dispositivos existentes](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) por meio do Configuration Manager. A ID de correlação é um parâmetro do arquivo de configuração do Autopilot. O Intune definirá automaticamente o [atributo do dispositivo do Azure AD enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) para que ele seja igual a "OfflineAutopilotprofile-\<ID de correlação\>". Isso permite que os grupos dinâmicos arbitrários do Azure AD sejam criados com base na ID de correlação por meio do atributo enrollmentprofileName para registros offline do Autopilot. 


### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Suporte para OAuth iOS 12 em perfis de email do iOS <!--2155106 -->
Perfis de email do iOS do Intune darão suporte ao OAuth iOS 12. Para ver esse recurso, escolha **Intune** > **Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **OAuth**. Se essa configuração for ativada, duas coisas acontecerão:
1. Os dispositivos já direcionados receberão um novo perfil.
2. Os usuários finais deverão inserir suas credenciais novamente.

### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nova configuração padrão "Tipo de senha obrigatória" para Android, Android Enterprise<!-- 2649963 -->
Quando você criar uma nova política de conformidade (**Intune** > **Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android** ou **Android Enterprise** para Plataforma > Segurança do Sistema), o valor padrão para **Tipo de senha obrigatória** será alterado: Padrão atual: Padrão do dispositivo Novo padrão: pelo menos numérico Aplica-se a: Android, Android Enterprise

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Atribuir perfis do Autopilot ao grupo virtual Todos os dispositivos <!--2715522 -->
Será possível atribuir perfis do Autopilot ao grupo virtual Todos os dispositivos. Para fazer isso, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > escolha um perfil > **Atribuições** > em **Atribuir a**, escolha **Todos os dispositivos**.

### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Recurso Novos termos de uso do Azure Active Directory <!-- 2870393 -->
O Azure Active Directory terá um recurso de termos de uso que você pode usar em vez dos termos e condições existentes do Intune. O recurso de termos de uso do Azure AD oferece mais flexibilidade sobre quais termos mostrar e quando mostrá-los, melhor suporte à localização, mais controle em como os termos são renderizados e melhor geração de relatórios. O recurso de termos de uso do Azure AD requer o Azure Active Directory Premium P1, que também faz parte do pacote Enterprise Mobility + Security E3.


### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>O Intune manterá o idioma localizado do Office ao atualizá-lo nos computadores dos usuários finais <!-- 2971030 -->
Quando o Intune instalar o Office nos computadores do seu usuário final, os usuários finais obterão automaticamente os mesmos pacotes de idioma que eles tinham com as instalações anteriores do .MSI Office. 

<!-- 1809 start -->  

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Configurações de transferência de dados de aplicativo do Intune em dispositivos iOS de MDM registrados <!-- 2244713 -->
Você poderá separar o controle de configurações de transferência de dados de aplicativo do Intune em dispositivos iOS de MDM registrados da especificação de identidade do usuário registrado. Os administradores que não estiverem usando o IntuneMAMUPN não observarão uma alteração de comportamento. Quando essa funcionalidade estiver disponível, os administradores que estiverem usando o IntuneMAMUPN para controlar o comportamento de transferência de dados em dispositivos registrados deverão revisar as novas configurações e atualizar as configurações de aplicativo conforme necessário.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Usar uma chave pré-compartilhada em um perfil de Wi-Fi do Windows 10 <!-- 2662938 -->
Você poderá usar uma chave pré-compartilhada (PSK) com o protocolo de segurança WPA/WPA2-Personal para autenticar um perfil de configuração de Wi-Fi no Windows 10.
No momento, é preciso importar um perfil de Wi-Fi ou criar um perfil personalizado para usar uma chave pré-compartilhada. [Configurações de Wi-Fi no Windows 10](wi-fi-settings-windows.md) lista as configurações atuais. 

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações de APP (Política de Proteção de Aplicativo) do aplicativo para dados Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>A frequência de sincronização de dispositivos Autopilot passa a ser a cada 12 horas <!-- 2753673 -->
Os dispositivos Autopilot serão sincronizados a cada 12 horas, não mais a cada 24 horas.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>As atualizações na página de aterrissagem do Intune e renomeação de nó <!--2867309 -->
As atualizações na página de aterrissagem do Intune incluirão novos e alterados blocos de monitoramento e gráficos para melhor visualização dos dados. O nó **Aplicativos móveis** será alterado para **Aplicativos cliente**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Maior acesso do usuário final usando o aplicativo do Portal da Empresa <!-- 772203 -->
Os usuários finais poderão acessar ações de conta principal, como a redefinição de senha e o perfil do AAD, pelo aplicativo de Portal da Empresa.  

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

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Melhoria na experiência do aplicativo Portal da Empresa para os usuários gerentes de registros de dispositivo <!-- 675800 -->
Quando um DEM (gerente de registros de dispositivo) entra no aplicativo Portal da Empresa para Windows, o aplicativo lista apenas o dispositivo em execução atual do DEM. Essa melhoria reduz os tempos limite que ocorriam anteriormente quando o aplicativo tentava carregar todos os dispositivos registrados pelo DEM.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Conferir a conformidade do Configuration Manager <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O Configuration Manager envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token do VPP ou de licença do Portal da Empresa quase acabando <!-- 2237572 -->
Se você usar o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem quase acabando.

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Teclados de terceiros podem ser bloqueados por configurações de APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune poderão bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivos. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

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



