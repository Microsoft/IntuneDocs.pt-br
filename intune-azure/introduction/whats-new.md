---
title: "Novidades da visualização do Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Descubra as novidades da visualização do Intune Azure"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: f209429bbafe50530e90bbaf133f780f448a8c57
ms.contentlocale: pt-br
ms.lasthandoff: 05/10/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Novidades da versão prévia do Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Conforme o andamento da versão prévia pública e à medida que mais recursos forem adicionados, nós os apresentaremos aqui.

> [!Note]
> Estamos distribuindo as alterações listadas nesta página para visualização do portal do Azure. No entanto, as alterações podem não estar disponíveis imediatamente devido a como o serviço do Intune é atualizado.  Vários componentes do serviço devem ser atualizados em sequência antes dos novos recursos do portal ficarem disponíveis. Procure essas alterações na distribuição posterior deste mês.

## <a name="april-2017"></a>Abril de 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Suporte para gerenciamento do aplicativo Sala de Aula da Apple

Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads. Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.
Para obter detalhes, confira [Definir as configurações de educação do iOS](../configure-devices/how-to-configure-ios-edu-settings.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->

Agora, os aplicativos Android na Play Store que oferecem suporte a opções de configuração gerenciada podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nova política de Android para PINs complexos <!-- 722069 -->

Agora, você pode definir um tipo de [senha](../configure-devices/device-restrictions-for-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Suporte adicional para dispositivos Android for Work

- **Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 -->

  Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 -->

  Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

Para saber mais, confira [Restrições de dispositivo para Android for Work](../configure-devices/device-restrictions-for-afw.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->

Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](../manage-apps/ios-lob-app.md) (arquivos .ipa) e [Android](../manage-apps/android-lob-app.md) (arquivos .apk) a usuários ou dispositivos.

###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 -->

- **Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](../configure-devices/home-screen-settings-for-ios.md). Essa política altera o layout da tela inicial, mas não implanta nenhum aplicativo que você especificou que não esteja instalado.

- **Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](../configure-devices/air-print-settings-for-ios-and-macos.md) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](../configure-devices/airplay-settings-for-ios-devices.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão. Para saber mais, confira [Ações do dispositivo disponíveis](../manage-devices/what-is.md#available-device-actions)


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->

Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](../configure-devices/app-notification-settings-for-ios.md) para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->

Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](../configure-devices/device-restrictions-for-ios.md#autonomous-single-app-mode-supervised-only). Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->

Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](../configure-devices/device-restrictions-for-ios.md#domains):

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 -->

Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->

Agora você pode [sincronizar os livros](../manage-apps/ios-vpp-apps.md) que adquiriu da loja Apple de programas de aquisição com base em volume com o Intune e atribuí-los aos usuários.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gerenciamento de vários usuários para dispositivos Samsung KNOX Standard <!-- 971988 -->

Agora há suporte para dispositivos que executam o Samsung KNOX Standard para o [gerenciamento de vários usuários](../enroll-devices/enroll-android-and-knox-standard-devices.md) pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->

Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](../configure-devices/device-restrictions-for-windows-10.md), como suporte adicional ao navegador Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->

Adicionamos suporte para o [gerenciamento de vários usuários](../enroll-devices/enroll-windows-devices.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Começar do zero para PCs com Windows 10<!-- 1004830 -->

Agora há uma [nova ação de dispositivo para começar do zero](../manage-devices/what-is.md#available-device-actions) disponível em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->

Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](../configure-devices/how-to-configure-windows-10-edition-upgrade.md) para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->

Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](../enroll-devices/bulk-enroll-windows.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte no momento para cenários de autoatendimento e de Portal da Empresa.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 -->

Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal de solução de problemas de suporte técnico <!-- 907448 -->

O novo [portal de solução de problemas](../manage-users/help-desk.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

## <a name="march-2017"></a>Março de 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Suporte para o Modo Perdido do iOS<!--431695-->

Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**. Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.

O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido. Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.

O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](../manage-devices/what-is.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->

Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### <a name="actions-for-non-compliance---730266--"></a>Medidas para não conformidade <!--730266-->

**Ações de não conformidade** é um novo recurso das políticas de conformidade que permite tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->

Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](../manage-apps/add-apps.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->

Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="new-compliance-reports---846671--"></a>Novos relatórios de conformidade <!--846671-->

Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários. Você pode exibir informações sobre

- Estado de conformidade geral de dispositivos
- Estado de conformidade para uma configuração individual
- Estado de conformidade para uma política individual

Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as diretivas que afetam esse dispositivo.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->

Para contas do Intune criadas depois de janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho de registrar dispositivos na Versão Prévia do Portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


## <a name="february-2017"></a>Fevereiro de 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Exibir todas as ações em dispositivos gerenciados <!--677150-->
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](https://docs.microsoft.com../manage-devices/what-is.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](../manage-apps/add-apps.md).

### <a name="display-device-categories---814654--"></a>Exibir categorias de dispositivos <!--814654-->
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](../manage-apps/add-apps.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Definir as configurações do Windows Update para Empresas <!--776716-->

O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10. Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](../configure-devices/how-to-configure-windows-update-for-business.md).

## <a name="january-2017"></a>Janeiro de 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748823-->
Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa. Consulte [O que é o gerenciamento de aplicativo](../manage-apps/what-is-app-management.md).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Resolva o problema em que os dispositivos iOS estão inativos ou o console de administração não pode se comunicar com eles
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](../enroll-devices/troubleshoot-device-enrollment.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Dezembro de 2016 (versão inicial)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integração de gerenciamento de despesas de telecomunicações na visualização pública do portal do Azure<!--747605-->
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Implantar e gerenciar aplicativos de um repositório para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos LOB (linha de negócios) para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos adquiridos de volume para dispositivos iOS e Windows
- Implantar e gerenciar aplicativos Web para dispositivos Android, iOS e Windows
- Perfis de configuração do aplicativo gerenciado por iOS
- Configurar políticas de proteção de aplicativo e implantar aplicativos de linha de negócios em dispositivos que não são registrados com o Intune
- Perfis VPN, VPN por aplicativo, Wi-Fi, email e perfis de certificado
- Políticas de conformidade
- Acesso condicional para Azure AD
- Acesso condicional para Exchange Local
- Registro de dispositivo
- Controle de acesso baseado em função

## <a name="deprecated-features-in-the-azure-portal"></a>Recursos preteridos no Portal do Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Suporte para examinar de linha por linha dos identificadores de hardware
O Portal do Azure não dá suporte à analise de linha por linha de identificadores de hardware para números IMEI e números de série da Apple. No console do Intune clássico, você pode importar detalhes de um arquivo valores separados por vírgulas (.csv) e substituir os detalhes existentes pelos identificadores de hardware individuais. O Portal do Azure apresenta uma única opção simplificada que automaticamente substitui detalhes para todos os identificadores de hardware ou ignora detalhes novos para identificadores existentes.

#### <a name="how-this-affects-you"></a>Como isso afeta você
No Portal do Azure, você não poderá decidir, linha por linha, os dispositivos de identidade de equipamentos de móveis internacional (IMEI) para atualizar. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### <a name="how-to-get-ready-for-this-change"></a>Como se preparar para essa alteração
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Suporte para o padrão perfis de registro de dispositivo corporativo em Apple DEP
O Portal do Azure não dá suporte para o perfil de registro de dispositivo corporativo "padrão" para números de série do dispositivo do DEP (Programa de registro de dispositivos) da Apple. Essa funcionalidade, disponível no console do Intune clássico, está sendo descontinuada para impedir que os perfis atribuídos acidentalmente. No Portal do Azure, os números de série sincronizados com base em uma conta de DEP da Apple inicialmente não terá nenhum perfil de registro de dispositivo corporativo atribuído.

#### <a name="how-this-affects-you"></a>Como isso afeta você
No Portal do Azure, você não poderá definir uma política de perfil padrão em todos os dispositivos da Apple. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### <a name="how-to-get-ready-for-this-change"></a>Como se preparar para essa alteração
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.

