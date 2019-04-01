---
title: incluir arquivo
description: incluir arquivo
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 073115d33f9a4f22fe3706ef15860c2a8d8a68ee
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675486"
---
Esses avisos fornecem importantes de informações que podem ajudar você a se preparar para recursos e alterações futuras do Intune. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Alteração no fluxo de trabalho do registro com o Portal da empresa do Intune em dispositivos iOS corporativos autenticando com o Assistente de instalação <!-- 1927359 -->
Há uma alteração futura no fluxo de trabalho para o registro de dispositivos iOS por meio de um dos métodos de registro de dispositivo corporativo da Apple - Configurator da Apple, gerente de negócios da Apple, Apple School Manager ou o Apple dispositivo registro programa (DEP), ao usar o programa de instalação Assistente para autenticação. Essa alteração se aplica somente a dispositivos registrados com afinidade do usuário.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Quando essa alteração for distribuída em ~~março~~ abril, os perfis de registro no Intune no portal do Azure serão atualizados para que você possa especificar como os dispositivos são autenticados e se o usuário recebe o aplicativo Portal da Empresa. Haverá um fluxo de trabalho aperfeiçoado para registrar dispositivos iOS por meio dos métodos listados acima. 

- Quando registrar novos dispositivos e autenticar com o Assistente de instalação, você poderá escolher se deseja ou não implantar automaticamente o aplicativo Portal da empresa. Os usuários finais não verão a tela de "Identifique seu dispositivo" e a tela de "Confirmar seu dispositivo" no fluxo de registro.  
- Em dispositivos já registrados por meio do Assistente de instalação por meio de um dos métodos de registro de dispositivo corporativo da Apple, é necessário tomar providências para habilitar o acesso condicional. Você precisará configurar uma política de configuração de aplicativo com um xml específico para enviar por push o Portal da empresa para esses dispositivos. Orientações para fazer isso estão na postagem do blog no link de informações adicionais. Se você optar por enviar por push o Portal da empresa dessa maneira, os usuários finais não verão a tela de "Identifique seu dispositivo" e a tela de "Confirmar seu dispositivo" no fluxo de registro. 
- Depois que essa alteração é distribuída, se você ainda não implantou o Portal da empresa com o perfil de configuração de aplicativo mencionados acima e se vai armazenar o aplicativo de Portal da empresa do aplicativo, que ele possa entrar de download de usuários finais, mas eles receberá uma mensagem de erro. Eles não poderão usar o aplicativo para acesso condicional. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se você planeja usar o fluxo de trabalho modificado, você desejará atualizar suas diretrizes do usuário final para indicar que:

- Os usuários finais não verá mais as duas telas mencionadas acima no fluxo de registro. 
- Eles serão necessário entrar no Portal da empresa quando ele é implantado automaticamente e não baixá-lo da loja de aplicativos. 

Você pode optar por criar uma política de configuração de aplicativo agora, se necessário, em preparação para essa alteração. Quando esse novo fluxo de trabalho for distribuída, você verá os perfis de registro atualizado no console do. Também você será informado de que essa distribuição por meio do Centro de mensagens. Depois disso, você precisará executar a ação para que os usuários finais podem registrar por meio do DEP por meio da autenticação com o Assistente de instalação e você pode usar o Portal da empresa para acesso condicional.

Consulte nosso blog de suporte a postagem no link de informações adicionais para obter mais detalhes sobre essa alteração.

#### <a name="additional-information"></a>Informações adicionais 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Plano para alteração: atualização de experiência do usuário para o aplicativo Portal da Empresa do Intune para iOS
Estamos felizes em compartilhar que o Intune em breve lançará uma grande atualização de experiência do usuário para o aplicativo de Portal da Empresa para iOS. A atualização apresentará uma reformulação visual da home page, com filtros avançados e acesso mais rápido a aplicativos e livros.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Essa atualização da experiência do usuário manterá a funcionalidade atual do Portal da Empresa do iOS e introduzirá:
- Uma home page com aparência nativa do iOS 
- Recursos de filtragem em listagens de conteúdo e pesquisa, incluindo a capacidade de filtrar por tipo de conteúdo (aplicativos ou livros eletrônicos) e por disponibilidade (gerenciamento de dispositivo obrigatório ou disponível sem registro)
- Capacidade de pesquisar livros eletrônicos
- Histórico de pesquisa para aplicativos e livros eletrônicos

Se fizer parte do programa TestFlight da Apple, você será notificado sobre a versão de pré-lançamento do aplicativo Portal da Empresa do Intune iOS atualizado quando ele estiver disponível. Se você não faz parte do programa TestFlight da Apple, não é tarde demais para se registrar. O registro permite que você use o aplicativo do Portal da Empresa atualizado antes que ele esteja disponível para seus usuários finais. Você também pode fornecer seus comentários diretamente para a equipe do Intune.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>O que posso fazer para me preparar para essa alteração?
Você não precisa tomar nenhuma providência; essas alterações serão lançadas em uma versão futura do aplicativo do Portal da Empresa do iOS. 

#### <a name="additional-information"></a>Informações adicionais
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)

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

### <a name="plan-for-change-upcoming-fix-for-windows-10-email-profiles-in-intune---3904031--"></a>Plano para mudança: correção futura para perfis de email do Windows 10 no Intune <!--3904031-->
Estamos atualizando a maneira como o Intune grava email perfis para Windows 10 de abril de atualização para o serviço do Intune para corrigir um bug, bem como para garantir que seus perfis de email continuem a funcionar em futuras versões do Windows 10. Não há ação que você precisa realizar depois que essa correção é implantada.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Essa alteração afeta você, se você usar perfis de email do Windows 10 com
- O cliente de email nativo em áreas de trabalho do Windows 10 ou
- O cliente de email do Outlook no Windows 10 Mobile

Isso afeta os dois clientes de gerenciamento de dispositivo móvel (MDM) do Intune autônomo e híbrido.

Depois que distribui a atualização de abril, você precisará recriar esses perfis no console do Intune (no console do administrador do Configuration Manager se você estiver usando o MDM híbrido).

Se você não tomar uma providência, aqui está o que você verá para perfis criados antes da atualização de abril:

- Os perfis de email existentes aparecerão no estado de erro no console do Intune ou do console de administração do Configuration Manager, mas os usuários finais ainda terá acesso ao email. No entanto, após uma atualização subsequente do Windows for distribuída, esses perfis não funcionará. Os usuários finais em dispositivos de destino com esses perfis perderão o acesso ao email.
- As edições feitas a esses perfis depois de abril não será refletida em dispositivos de destino.
- Apagamento seletivo não funcionará para remover esses perfis, mesmo após a correção é distribuída em abril.

Se você agir e crie novamente os perfis de email, os usuários finais terão percorrer etapas semelhantes àquelas quando um perfil de email é implantado pela primeira vez. Seu email será impedido de sincronização até que ele aceite a atualização que aplica o novo perfil.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Você precisará agir somente depois que a correção é distribuída com a atualização de abril. Entraremos em contato para você por meio do Centro de mensagens quando essa alteração for lançada, para que você possa começar recriar os perfis no Intune.

Se você usar perfis de email do Windows 10 no Intune, você precisará executar as seguintes etapas:

1. Capturar configurações de perfil existentes do Windows 10
2. Cancelar a atribuição de e/ou excluir perfis existentes
3. Criar novos perfis usando as configurações capturadas e atribuir novos perfis aos mesmos grupos

Você precisa notificar os usuários finais e avise a assistência técnica dessa alteração. Consulte a postagem do blog de suporte em informações adicionais para detalhes do erro e instruções para recriar esses perfis.

#### <a name="additional-information"></a>Informações adicionais
https://aka.ms/Win10EmailProfiles

