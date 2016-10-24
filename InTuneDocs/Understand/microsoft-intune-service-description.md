---
title: "Descrição do Serviço | Microsoft Intune"
description: "O Intune é um serviço baseado em nuvem que ajuda você a gerenciar computadores Windows e dispositivos móveis iOS, Mac OS X, Android e Windows."
keywords: 
author: Nbigman
ms.author: nbigman
manager: angrobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: cacamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a7cced90c482498b5f5af424165f8dcf77b79b75
ms.openlocfilehash: e3694f80d6148abbce004bb0c7143bf394b313d9


---

# Descrição do serviço do Microsoft Intune

O Microsoft Intune é um serviço baseado em nuvem que ajuda você a gerenciar computadores Windows e dispositivos móveis, iOS, Mac OS X, Android e Windows. O Intune também ajuda a proteger dados e aplicativos corporativos. Você pode usar o Intune sozinho ou integrá-lo ao System Center Configuration Manager para estender suas funcionalidades de gerenciamento. 

A Microsoft oferece o benefício do Intune Onboarding para serviços qualificados em planos qualificados. O benefício do Onboarding permite que você trabalhe remotamente com especialistas da Microsoft para deixar seu ambiente do Intune pronto para uso. Para saber mais, consulte [Descrição do Benefício do Microsoft Intune Onboarding](http://go.microsoft.com/fwlink/?LinkId=619281).

É possível começar a usar o Intune com uma versão de avaliação gratuita por 30 dias, que inclui 100 licenças para usuários. Para iniciar sua avaliação gratuita, [clique aqui para visitar a página de inscrição do Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/). Se a sua empresa tiver um contrato corporativo ou um contrato de licenciamento por volume equivalente, entre em contato com o seu representante Microsoft para configurar sua avaliação gratuita.

> [!NOTE]
> Se a sua organização tem uma conta corporativa ou de estudante do Microsoft Online Services e é provável que você continue com essa assinatura do Intune em produção depois que o período de avaliação terminar, clique na opção **Entrar** nessa página e faça a autenticação usando a conta de administrador global da sua organização. Esta ação assegurará seus links de avaliação do Intune para sua conta do trabalho ou da escola.

Para ver uma lista de configurações que você pode definir em dispositivos móveis, consulte:

-   [Recursos de gerenciamento de dispositivos registrados do Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

-   [MDM (gerenciamento de dispositivo móvel) híbrido com o System Center Configuration Manager e o Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) 

Para obter informações sobre o System Center Configuration Manager, consulte a [Documentação do System Center Configuration Manager](https://technet.microsoft.com/library/mt346023.aspx).

## Entenda como as atualizações de serviço do Intune afetam você
Como o Intune é um serviço online, a Microsoft pode atualizá-lo regularmente.

Use as informações neste tópico para ajudá-lo a entender a frequência dessas atualizações de serviço e a notificação antecipada que fornecemos quando uma atualização puder afetar seu uso do serviço.

Para aprender sobre as mudanças no serviço do Intune, consulte [O que há de novo no Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune). O [Blog do Microsoft Intune](http://blogs.technet.com/b/microsoftintune/) também aborda as alterações no serviço e fornece dicas úteis para que você possa obter o máximo do Intune. 

Atualizações do serviço importantes também serão comunicadas no Centro de Mensagens do [portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx). Se você instalar o complemento [aplicativo móvel de administração do Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), você poderá receber notificações em seu dispositivo móvel.

> [!NOTE]
> Você pode monitorar a integridade do serviço Intune no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx). Escolha **Integridade do Serviço** no painel esquerdo.  

Aqui estão os tipos de avisos que a Microsoft fornece sobre o serviço do Intune:
-   Para ajudar a planejar alterações no serviço, notificaremos pelo menos 30 a 90 dias antes da atualização de serviço, dependendo do impacto da alteração. Isso acontecerá usando canais de comunicação dentro do produto, como alertas do quadro de avisos. Essas alterações podem incluir:
* Atualizações que podem ter impacto sobre normas ou sobre a conformidade
* Alterações na experiência do usuário, interface do usuário e fluxos de trabalho
* APIs novas ou alteradas – notificando que você precisará testar para garantir a compatibilidade com versões anteriores de aplicativos personalizados
* Alterações em requisitos de sistema, por exemplo, a versão mínima necessária do navegador
* Quaisquer atualizações que exigem providências para habilitar o recurso ou para evitar a interrupção de serviço para o recurso.
-   A Microsoft fornece informações sobre novos recursos, novas funcionalidades e aprimoramentos em funcionalidades existentes em nossa atualização mensal do serviço. Em geral, a Microsoft lança atualizações de serviço em meados de cada mês. As atualizações são descritas em [What's new in Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune) (Novidades do Microsoft Intune).
-   No caso de desativação do serviço do Intune, você seria notificado com 12 meses de antecedência.

## Escolha a solução de gerenciamento que é ideal para você
Você pode configurar o Intune de várias formas para gerenciar e ajudar a proteger os dispositivos móveis e computadores da sua empresa (chamados de **dispositivos** neste documento).

-   **Configuração autônoma do Intune.** Use o console de administração baseado na Web do Intune para gerenciar dispositivos na sua organização. O Intune pode ser usado sem nenhuma infraestrutura de TI local, mas se usar o Intune com os Serviços de Domínio do Active Directory, você poderá usar contas de usuário de domínio que você gerencia com os Serviços de Domínio com Intune.

-   **Intune com System Center Configuration Manager.** Use o console de gerenciamento do Configuration Manager para gerenciar computadores e dispositivos móveis na sua empresa. Essa configuração pode ajudá-lo a gerenciar todos os dispositivos da sua empresa por meio de um único console, o Console de Admin do Configuration Manager. O Configuration Manager é compatível com inúmeros dispositivos móveis, servidores e computadores. Para obter mais informações, consulte [Gerenciamento de dispositivo móvel (MDM) híbrido com o System Center Configuration Manager e o Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx).  Para obter mais ajuda para decidir qual abordagem é adequada para você, veja [Choose between Microsoft Intune standalone and hybrid mobile device management with Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx) (Escolher entre gerenciamento de dispositivo móvel do Microsoft Intune autônomo ou híbrido com o Configuration Manager). 


## Saiba mais sobre o Intune
Use estes recursos para saber mais sobre o Intune:

-   O [Microsoft Intune Trust Center](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) fornece informações sobre as práticas de segurança, privacidade e conformidade do Intune e descreve algumas das certificações do Intune.

-   [Recursos de gerenciamento de dispositivos registrados do Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

### Consulte também
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Biblioteca de documentação do System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[Novidades do Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Sep16_HO4-->


