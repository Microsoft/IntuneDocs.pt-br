---
# required metadata

title: Guia de avaliação do Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Guia de avaliação do Intune
É fácil e rápido configurar uma avaliação gratuita de 30 dias do Intune para gerenciar seus dispositivos móveis e computadores. Com apenas algumas etapas simples na avaliação, você pode adicionar até 100 usuários e dispositivos, configurar grupos e políticas de conformidade e registrar e gerenciar computadores e dispositivos móveis.

Neste tópico, você aprenderá o básico para obter uma avaliação do Intune em funcionamento e obterá uma visão geral do serviço para poder avaliar os recursos e as funcionalidades do Intune.

Assista a este vídeo de demonstração de cinco minutos para ver como é fácil começar com uma avaliação gratuita do Microsoft Intune e gerenciar seus dispositivos:

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Antes de começar
Antes de começar com o Intune, será necessário o seguinte:

-   Um dispositivo com um navegador da Web habilitado para Silverlight que você pode usar para acessar os sites em que criará contas de usuário do Intune (o **Centro de administração do Office 365**) e no qual gerenciará dispositivos, grupos e políticas (o **console de administração do Intune**)).

-   Um segundo dispositivo com um navegador da Web que você usará para testar como usuários vão registrar e gerenciar seus dispositivos usando o Portal da Empresa. Você também vai testar como os usuários encontram e instalam aplicativos e solicitam ajuda dos administradores. Se você não tiver um segundo dispositivo, poderá usar a configuração “modo de privacidade” no mesmo navegador que usa para a administração do Intune (por exemplo: no Internet Explorer você pode escolher **Ferramentas** &gt; **Navegação InPrivate**).

-   Se você tiver uma conta existente do Microsoft Online Services, precisará das credenciais de administrador para essa conta. Se você não tiver esta conta ou se desejar usar este locatário do Intune somente para fins de avaliação, você não precisará de credenciais de administrador.

-   Se você gerenciar dispositivos iOS ou Windows Phone com a avaliação do Intune, precisará de certificados (ou chaves) e contas para recuperar esses certificados (consulte a tabela a seguir). Dispositivos Android não precisam de nenhum certificado adicional.

    |Plataforma|Requisitos de Certificado|Mais informações|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 e Windows Phone 8 |Nenhum certificado é necessário para usuários do Windows Phone 8.1 que instalam o aplicativo do Portal da Empresa da Loja. Um certificado Symantec é necessário para Windows Phone 8.0 ou para usar o Intune a fim de implantar o aplicativo Portal da Empresa em dispositivos do Windows Phone 8.1.|Estas diretrizes pressupõem que os usuários obtiverem o aplicativo Portal da Empresa pela Loja em um dispositivo Windows Phone 8.1 ou posterior. Para obter informações sobre o suporte ao Windows Phone 8.0, consulte [Set up Windows Phone management with Microsoft Intune (Configurar o gerenciamento do Windows Phone com o Microsoft Intune)](/Intune/DeployUse/set-up-windows-phone-management-with-microsoft-intune).|
    |Dispositivos do Windows 10, Windows RT 8.1, Windows RT ou Windows 8.1|Não existem requisitos de certificado para registrar dispositivos do Windows RT e do Windows.|[Instalar o cliente do PC Windows com o Microsoft Intune](/Intune/DeployUse/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 ou posterior|Obter um certificado de serviço de Notificação por Push da Apple.|Solicitar um certificado do Apple Push Notification Service da Apple, conforme descrito aqui: [Configurar gerenciamento do iOS e Mac com o Microsoft Intune](/Intune/DeployUse/set-up-ios-and-mac-management-with-microsoft-intune).|

## Etapas para realizar uma avaliação de 30 dias do Intune
- [Etapa 1: Entrar ou se inscrever para uma avaliação de 30 dias](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Antes de se inscrever ou entrar no Intune, você deve considerar se deseja entrar usando uma conta existente ou criar uma conta temporária a ser usada apenas para a avaliação de 30 dias do Microsoft Intune.
- [Etapa 2: Adicionar usuários](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Agora que você configurou sua conta, poderá adicionar contas de usuário individuais ao Intune ou adicionar usuários em massa (consulte as instruções nesta seção). Antes de começar, é importante entender como o Intune lida com contas de administrador.
- [Etapa 3: Criar grupos para organizar usuários e dispositivos](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Os grupos no Intune oferecem grande flexibilidade para o gerenciamento de dispositivos e usuários. Você pode configurar grupos para atender as suas necessidades organizacionais (por exemplo, por localização geográfica, departamento ou características de hardware) e usá-los para executar diversas tarefas administrativas em escala, da definição de políticas para um conjunto de usuários à implantação de aplicativos para um conjunto de dispositivos.
- [Etapa 4: Criar políticas e publicar um aplicativo](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos.
- [Etapa 5: Registrar dispositivos móveis e instalar um aplicativo](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve definir a autoridade de gerenciamento de dispositivo móvel, habilitar o gerenciamento de plataformas de dispositivo específicas e registrar seus dispositivos com o aplicativo Portal da Empresa. Em seguida, você pode implantar o aplicativo Microsoft Skype que publicou.
- [Etapa 6: Outras opções e extras](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Escolha como usar alertas, relatórios e outros recursos do Intune para atender às suas necessidades de negócios.
- [Etapa 7: Próximas etapas](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Prepare-se para ir para uma assinatura paga do Intune e aproveitar o benefício "FastTrack Center" do Intune.


### Próximas etapas
É hora de começar a usar sua assinatura de avaliação de 30 dias!

>[!div class="step-by-step"]
[**Inscreva-se para o Intune** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### Consulte também
[Guia de início rápido do Intune](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)


<!--HONumber=May16_HO1-->


