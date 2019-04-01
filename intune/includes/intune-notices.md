---
ms.openlocfilehash: dc86f2c22410236368753acd4dd3b66698037241
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57736843"
---

Esses avisos fornecem importantes de informações que podem ajudar você a se preparar para recursos e alterações futuras do Intune. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Alteração no fluxo de trabalho do registro com o Portal da empresa do Intune em dispositivos iOS corporativos autenticando com o Assistente de instalação <!-- 1927359 -->
Há uma alteração futura no fluxo de trabalho para o registro de dispositivos iOS por meio de um dos métodos de registro de dispositivo corporativo da Apple - Configurator da Apple, gerente de negócios da Apple, Apple School Manager ou o Apple dispositivo registro programa (DEP), ao usar o programa de instalação Assistente para autenticação. Essa alteração se aplica somente a dispositivos registrados com afinidade do usuário.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Quando essa alteração for distribuída em ~~março~~ abril, os perfis de registro no Intune no portal do Azure serão atualizados para que você possa especificar como os dispositivos são autenticados e se o usuário recebe o aplicativo Portal da Empresa. Haverá um fluxo de trabalho aperfeiçoado para registrar dispositivos iOS por meio dos métodos listados acima. Observação:

- Quando registrar novos dispositivos e autenticar com o Assistente de instalação, você poderá escolher se deseja ou não implantar automaticamente o aplicativo Portal da empresa. Os usuários finais não verão a tela de "Identifique seu dispositivo" e a tela de "Confirmar seu dispositivo" no fluxo de registro.  
- Em dispositivos já registrados por meio do Assistente de instalação por meio de um dos métodos de registro de dispositivo corporativo da Apple, é necessário tomar providências para habilitar o acesso condicional. Você precisará configurar uma política de configuração de aplicativo com um xml específico para enviar por push o Portal da empresa para esses dispositivos. Orientações para fazer isso estão na postagem do blog no link de informações adicionais. Se você optar por enviar por push o Portal da empresa dessa maneira, os usuários finais não verão a tela de "Identifique seu dispositivo" e a tela de "Confirmar seu dispositivo" no fluxo de registro. 
- Depois que essa alteração é distribuída, se você ainda não implantou o Portal da empresa com o perfil de configuração de aplicativo mencionados acima e se vai armazenar o aplicativo de Portal da empresa do aplicativo, que vai possam se conectar, de download de usuários finais, mas eles receberá uma mensagem de erro. Eles não poderão usar o aplicativo para acesso condicional. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se você planeja usar o fluxo de trabalho modificado, você desejará atualizar suas diretrizes do usuário final para indicar que:

- Os usuários finais não verá mais as duas telas mencionadas acima no fluxo de registro. 
- Eles serão necessário entrar no Portal da empresa quando ele é implantado automaticamente e não baixá-lo da loja de aplicativos. 

Você pode optar por criar uma política de configuração de aplicativo agora, se necessário, em preparação para essa alteração. Quando esse novo fluxo de trabalho for distribuída, você verá os perfis de registro atualizado no console do. Também você será informado de que essa distribuição por meio do Centro de mensagens. Depois disso, você precisará executar a ação para que os usuários finais podem registrar por meio do DEP por meio da autenticação com o Assistente de instalação e você pode usar o Portal da empresa para acesso condicional.

Consulte nosso blog de suporte a postagem no link de informações adicionais para obter mais detalhes sobre essa alteração.

#### <a name="additional-information"></a>Informações adicionais 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="company-portal-changes-for-ios-122-enrollment-in-intune"></a>Alterações de portal da empresa para iOS 12.2 registro no Intune
Compartilhamos em MC172534 que a Apple anunciou algumas alterações relacionadas ao registro de dispositivos iOS em serviços de MDM (gerenciamento de dispositivo móvel). A alteração provavelmente será vista a versão do iOS chegando em março de 2019, bem como todas as versões futuras do iOS. Estamos fazendo algumas atualizações no Portal da empresa para refletir as alterações da Apple. 
 
#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Se os usuários finais atualizarem seus dispositivos para o iOS 12.2 e acima, sabe que há um fluxo de trabalho modificado e eles devem executar etapas adicionais para concluir o registro no Intune. Após a atualização de março para o Intune, aqui está o que eles farão-  

- Iniciar o processo de registro no aplicativo Portal da empresa para baixar um perfil de gerenciamento
- Vá para Configurações > Geral > perfis e procure uma notificação vermelho
- Selecione o perfil correto e clique para instalar
- Retornar ao Portal da empresa para concluir o registro

Para obter informações detalhadas sobre o fluxo de registro, clique em obter informações adicionais.

A menos que eles estão cancelados e precisam de um novo registro, os dispositivos que já estão registrados e atualizar para o iOS 12.2 e acima não devem ser afetado. A experiência de registro em dispositivos que executam o iOS 12.1 ou anterior não será alterada com essa nova versão pela Apple. Dispositivos registrados por meio de um ou métodos de registro corporativo da Apple (programa de registro de dispositivo Apple School Manager ou o gerente de negócios da Apple) não serão afetados.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você deve planejar atualizar a documentação e as diretrizes do usuário final. Você talvez queira informar a assistência técnica sobre essas alterações. Manteremos você informado por meio de nossa página novidades quando essa alteração for lançada. 

Se você quiser tirar proveito das alterações de Portal da empresa, estamos introduzindo, peça aos usuários finais que atualizar seu dispositivo para a nova versão do iOS após a atualização de março, o Intune de serviço ao Portal da empresa 3.9.0 de versão do aplicativo. é liberado.

Clique em obter informações adicionais para uma postagem de blog de suporte com capturas de tela de visualização das alterações de Portal da empresa.

Informações adicionais [https://aka.ms/CP_changes_iOS12](https://aka.ms/CP_changes_iOS12)

### <a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Plano para mudança: fluxo de trabalho é alterado para o registro do iOS 12 no Intune
A Apple anunciou algumas alterações relacionadas ao registro de dispositivos iOS em serviços de MDM (gerenciamento de dispositivo móvel). A alteração provavelmente será vista a versão da primavera de 2019 do iOS, bem como em todas as versões futuras do iOS.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Se os usuários finais atualizarem seus dispositivos para essa nova versão do iOS 12 na primavera, saiba que há um fluxo de trabalho modificado e que eles precisarão executar etapas adicionais para concluir o registro no Intune. Quando Apple apresenta essas alterações, os usuários finais terá que:

- Iniciar o processo de registro no aplicativo Portal da empresa para baixar um perfil de gerenciamento
- Vá para Configurações > Geral > perfis
- Selecione o perfil correto e clique para instalar
- Retornar ao Portal da empresa para concluir o registro 

Dispositivos que já estiverem registrados e atualizarem para a nova versão do iOS não deverão ser afetados, a menos que eles não estejam registrados e precisem de um novo registro.

A experiência de registro em dispositivos que executam o iOS 12.1 ou anterior não será alterada com essa nova versão pela Apple.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você deve planejar atualizar a documentação e as diretrizes do usuário final. Você talvez queira informar a assistência técnica sobre essas alterações. Manteremos você informado por meio do Centro de Mensagens e da nossa página Novidades quando essa alteração for lançada.

#### <a name="additional-information"></a>Informações adicionais
[Suporte a postagem de blog com capturas de tela e o vídeo do fluxo de registro esperado](https://aka.ms/iOS_enrollment_changes).

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Plano para alteração: atualização de experiência do usuário para o aplicativo Portal da Empresa do Intune para iOS
Estamos felizes em compartilhar que o Intune em breve lançará uma grande atualização de experiência do usuário para o aplicativo de Portal da Empresa para iOS. A atualização apresentará uma reformulação visual da home page, com filtros avançados e acesso mais rápido a aplicativos e livros.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Essa atualização da experiência do usuário manterá a funcionalidade atual do Portal da Empresa do iOS e introduzirá:
- Uma home page com aparência nativa do iOS 
- Recursos de filtragem em listagens de conteúdo e pesquisa, incluindo a capacidade de filtrar por tipo de conteúdo (aplicativos ou livros eletrônicos) e por disponibilidade (gerenciamento de dispositivo obrigatório ou disponível sem registro)
- Capacidade de pesquisar livros eletrônicos
- Histórico de pesquisa para aplicativos e livros eletrônicos

Se fizer parte do programa TestFlight da Apple, você será notificado sobre a versão de pré-lançamento do aplicativo Portal da Empresa do Intune iOS atualizado quando ele estiver disponível. Se você não faz parte do programa TestFlight da Apple, não é tarde demais para se registrar. O registro permite que você use o aplicativo do Portal da Empresa atualizado antes que ele esteja disponível para seus usuários finais. Você pode também fornecer seus comentários diretamente para a equipe do Intune.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você não precisa tomar nenhuma providência; essas alterações serão lançadas em uma versão futura do aplicativo do Portal da Empresa do iOS. 

#### <a name="additional-information"></a>Informações adicionais
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="reminder-removal-of-existing-exchange-online-to-intune-connectors----3105122---"></a>Lembrete: Remoção dos existentes o Exchange Online para conectores do Intune <!-- 3105122 -->
MC165575, compartilhamos que estamos poderia ser removendo o Exchange Online para a funcionalidade do conector do Intune 'Serviço' em uma atualização futura. Com a atualização de fevereiro para o serviço Intune, será desabilitamos o botão configurar novos conectores. Estamos planejando remover todos os existentes Exchange Online para conectores do Intune em março de 2019.
 
#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Você está recebendo esta mensagem porque nossos registros indicam que você pode estar usando a funcionalidade do conector Service to Service em seu ambiente. O conector Service to Service dá suporte ao gerenciamento do Intune para dispositivos somente do Exchange Active Sync para o Exchange Online,e não dá suporte à infraestrutura local. Esse conector, devido à maneira como é exibido no console, parece ser necessário para o Acesso Condicional (CA), quando, na realidade, não é. Você pode ter sido usando esse conector para entender o uso do Exchange Online antes de aplicar o acesso condicional. Essas informações já são fornecidas pelo Centro de administração do Microsoft 365. Aqui, você encontrará fornece relatórios de uso para o Exchange Online incluindo o aplicativo de tipo que está sendo usado para entre 7 e 180 dias. Para obter mais informações, consulte [relatórios do Office 365 no Centro de administração - uso de aplicativos de Email](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage?view=o365-worldwide).  
 
Se você usar esses conectores em seu ambiente, não poderá monitorar ou apagar dispositivos somente do Exchange Active Sync no Intune após a desabilitação dos conectores em fevereiro. Não há nenhum impacto previsto para seus usuários finais durante essa alteração.
 
#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Se você tiver o conector Service to Service configurado e tiver dispositivos somente do Exchange Active Sync, alterne para outros métodos de gerenciamento de dispositivos. Você tem as seguintes opções:

- Registrar dispositivos no Gerenciamento de Dispositivo Móvel (MDM) 
- Usar políticas de Proteção de Aplicativo do Intune para gerenciar seus dispositivos 
- Use os controles do Exchange, conforme descrito [nesta](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) documentação 

#### <a name="additional-information"></a>Informações adicionais  
https://docs.microsoft.com/intune/exchange-service-connector-configure




### <a name="check-your-delay-visibility-of-software-updates-setting-in-intune"></a>Verifique sua configuração de "Atraso a visibilidade de atualizações de Software" no Intune 

Compartilhamos MC171466, foram movendo algumas configurações ao redor no console. Com a atualização de março para o Intune, vamos completamente remover a configuração "Atualizações de visibilidade de atraso de Software" na folha de política de atualização do iOS. Isso não alterará a maneira de aplicam as atualizações de software agendada, mas pode afetar quanto tempo a visibilidade de uma atualização está atrasada para os usuários finais. Talvez você precise tomar uma ação antes do final de março, se você usar essa configuração. 

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Após a atualização de serviço do Intune de fevereiro, você observará que a configuração é exibida em perfis de restrição de dispositivo no console e no iOS atualizar políticas na folha de atualização de Software. Quando você vir essa alteração refletida no console, aqui está o que você talvez precise fazer.

- Para políticas de atualização existentes para iOS: se você tiver personalizado configurado essa configuração como qualquer coisa diferente do padrão de 30 dias e deseja que as configurações existentes para a configuração de visibilidade de atraso continuar a aplicar após o final de março, você precisará criar um novo perfil de restrição de dispositivo iOS. Aqui, a configuração de visibilidade de atraso será necessário ter os mesmos valores da política de atualização do iOS existente e ser direcionada aos mesmos grupos. Após a atualização do serviço de março, você não poderá editar os valores para essa configuração nas políticas de atualização de iOS existente, pois ele não estará visível nesta folha. Em vez disso, você irá configurar essa configuração em novos perfis.
  Se o valor do número de dias que você pode atrasar visibilidade não coincide com em ambos os locais para valores de configuração personalizada, a visibilidade de atraso de configuração não funcionará, e os usuários finais verão a atualização em seus dispositivos, assim que ele está disponível. Isso pode ter um impacto mínimo para a maioria dos clientes, desde que as outras configurações na folha da política de atualização de Software sempre tenham feito precedência sobre essa configuração no console do.
- Para novas políticas de atualização do iOS: se você tentar criar novas políticas na folha de atualizações de Software após a atualização do serviço de fevereiro do Intune, você verá essa configuração esmaecidos. Você verá uma nota no console do redirecionando você para a folha de configuração do dispositivo, se você deseja atrasar a visibilidade das atualizações.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você não precisa tomar uma ação se você não use essa configuração ou não deseja atrasar a visibilidade de atualizações de software para seus usuários finais.

Se você deseja atrasar a visibilidade das atualizações, começar a configurar a configuração no novos perfis na folha de configuração do dispositivo em restrições de dispositivo > geral. Se você tiver essa configuração personalizada configurado no iOS existente, políticas de atualização, crie um novo perfil de restrição de dispositivo equivalente com o mesmo valor para "dias" atrasar a visibilidade das atualizações para seus usuários, depois de fevereiro e antes de março atualização distribui. 

Você talvez queira atualizar suas diretrizes para profissionais de TI e informe o suporte técnico.

Consulte nosso blog de suporte a postar informações adicionais para obter detalhes sobre como configurar essa configuração.

#### <a name="additional-information"></a>Informações adicionais 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)
