---
title: Edição antecipada - Microsoft Intune
titlesuffix: ''
description: Edição antecipada do Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/09/2019
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
ms.openlocfilehash: 0efc84da6a9efb594600b9ca33aa5eb7622c8101
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203426"
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

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implantação de aplicativos online licenciados da Microsoft Store para Empresas <!-- 1672660  -->
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

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>O SDK de Aplicativo do Intune oferece suporte a chaves de criptografia de 256 bits <!-- 1832174 -->
O SDK de Aplicativo do Intune para Android usa as chaves de criptografia de 256 bits quando a criptografia está habilitada por Políticas de Proteção de Aplicativo. O SDK continua a fornecer suporte a chaves de 128 bits para compatibilidade com o conteúdo e aplicativos que usam versões mais antigas do SDK.


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


### <a name="additional-settings-for-outlook----3301182---"></a>Configurações adicionais para o Outlook <!-- 3301182 -->
Agora você poderá definir configurações adicionais para o Outlook para iOS e Android usando o Intune.  As configurações incluem as seguintes:
- Permitir o uso somente de contas corporativas ou de estudante no Outlook no iOS e no Android
- Implantar a autenticação moderna para o Office 365 e a autenticação moderna híbrida para contas locais
- Usar `SAMAccountName` para o campo de nome de usuário no perfil de email quando a autenticação Básica for selecionada
- Permitir que os contatos sejam salvos
- Configurar MailTips de destinatários externos
- Configurar **Caixa de Entrada Destaques**
- Exigir biometria para acessar o Outlook para iOS 
- Bloquear imagens externas

> [!NOTE]
> Se estiver usando políticas de Proteção de Aplicativo do Intune para gerenciar o acesso de identidades corporativas, considere a possibilidade de não habilitar a opção **Exigir biometria**. Para obter mais informações, confira **Exigir credenciais corporativas para acesso** para [Requisitos de acesso do iOS](app-protection-policy-settings-ios.md#access-settings) e [Requisitos de acesso do Android](app-protection-policy-settings-android.md#access-settings).

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Os modelos administrativos estão em versão prévia pública e mudaram para o perfil de configuração próprio <!-- 3322847 -->
Os modelos administrativos no Intune (**Configuração do dispositivo** > **Modelos administrativos**) estão em versão prévia privada. Com esta atualização: Modelos administrativos incluem aproximadamente 300 configurações que podem ser gerenciadas no Intune. Anteriormente, essas configurações só existiam no editor de política de grupo.
Os modelos administrativos estão disponíveis na versão prévia pública. Os modelos administrativos estão mudando de **Configuração do dispositivo** > **Modelos administrativos** para **Configuração do dispositivo** > **Perfis** >**Criar perfil** > em **Plataforma**, escolha **Windows 10 e posterior**, em **Tipo de perfil**, escolha **Modelos administrativos**.
A criação de relatórios está habilitada. Aplica-se a: Windows 10 e posterior

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Modo Escuro do Portal da Empresa do Intune no macOS <!-- 3300524 -->
O Portal da Empresa do Intune no macOS agora dá suporte ao Modo Escuro para macOS. Quando você habilitar o Modo Escuro em um dispositivo macOS 10.14 ou superior, o Portal da Empresa ajustará sua aparência de acordo com as cores para refletir o modo.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Usar configurações recomendadas pela Microsoft com linhas de base de segurança <!-- 2055484 -->
O Intune integra-se a outros serviços que têm foco na segurança, incluindo o Windows Defender ATP e o Office 365 ATP. Os clientes estão solicitando uma estratégia comum e um conjunto coeso de fluxos de trabalho de segurança de ponta a ponta entre os serviços do Microsoft 365. Nossa meta é alinhar estratégias para criar soluções que façam a ponte entre operações de segurança e tarefas comuns do administrador. No Intune, nosso objetivo é atingir essa meta publicando um conjunto de "Linhas de base de segurança" recomendadas pela Microsoft (**Intune** > **Linhas de base de segurança**).  Um administrador poderá criar políticas de segurança diretamente com base nessas linhas de base e implantá-las para seus usuários. Eles também poderão personalizar as recomendações de melhores práticas para atender às necessidades de sua organização. O Intune garante que os dispositivos estejam em conformidade com essas linhas de base e notifica os administradores de usuários ou dispositivos que não estão em conformidade.

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



<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Conferir a conformidade do Configuration Manager <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o System Center Configuration Manager (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O Configuration Manager envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do Configuration Manager retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores



## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.



