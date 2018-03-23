---
title: Maneiras comuns de usar o Microsoft Intune
description: Saiba mais sobre as seis tarefas mais comuns que o Microsoft Intune pode ajudá-lo a gerenciar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b3010695c6562bab845d271775693f23daf99184
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="common-ways-to-use-microsoft-intune"></a>Maneiras comuns de usar o Microsoft Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Antes de se envolver em tarefas de implementação, é importante alinhar os participantes da mobilidade corporativa da sua empresa em relação às metas de negócios.  Isso é importante se você for iniciante em mobilidade corporativa ou estiver migrando de outro produto.  

As necessidades em torno da mobilidade corporativa estão evoluindo dinamicamente e a abordagem da Microsoft para lidar com isso, às vezes, é diferente de outras soluções no mercado. A melhor maneira de alinhar suas metas de negócios é expressá-las em termos dos cenários que você deseja habilitar para seus funcionários, parceiros e o departamento de TI.  

Abaixo, temos breves apresentações dos seis cenários mais comuns que se baseiam no Intune, acompanhadas de links para obter mais informações sobre como planejar e implantar cada um deles.

>[!NOTE]
>Quer saber como a equipe de TI da Microsoft usa o Intune para dar à Microsoft acesso aos recursos corporativos em seus dispositivos móveis enquanto também mantêm os dados corporativos protegidos? [Leia este estudo de caso técnico](https://www.microsoft.com/itshowcase/Article/Content/588) para ver em detalhes como o a equipe de TI da Microsoft utiliza o Intune e outros serviços para gerenciar identidades, dispositivos e aplicativos e dados.  

>[!IMPORTANT]
>Queremos garantir que os dispositivos móveis estejam atualizados considerando os recentes ataques de malware "Trident" em dispositivos iOS. Por isso, publicamos uma postagem de blog chamada [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (Garantindo que os dispositivos móveis estejam atualizados usando o Microsoft Intune). Ela fornece informações sobre as diferentes maneiras como o Intune pode ajudar a manter seus dispositivos seguros e atualizados.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Proteger seus dados e emails locais para que eles possam ser acessados com segurança por dispositivos móveis
A maioria das estratégias de mobilidade corporativa começam com um plano para habilitar o acesso seguro ao email para funcionários com dispositivos móveis que se conectam à Internet. Muitas organizações ainda têm dados e servidores de aplicativos locais, como o Microsoft Exchange, que são hospedados em sua rede corporativa.


O Intune e o Microsoft EMS (Enterprise Mobility + Security) fornecem uma [solução de acesso condicional](conditional-access.md) ([portal Clássico](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) integrada de forma exclusiva para o Exchange Server, que garante que nenhum aplicativo móvel pode acessar emails até que o dispositivo seja registrado no Intune. É possível fazer tudo isso sem implantar outro computador de gateway no limite da rede corporativa.

O Intune também dá suporte à habilitação do acesso a aplicativos móveis que precisam de acesso seguro aos dados locais, como servidores de aplicativos de linha de negócios. Isso normalmente é feito usando [certificados gerenciados pelo Intune](certificates-configure.md) ([portal Clássico](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)) para o controle de acesso, combinado com um gateway de VPN padrão ou proxy no perímetro, como o Proxy de Aplicativo do Microsoft Azure Active Directory. 

Nesses casos, a única maneira de acessar os dados corporativos é registrar o dispositivo no gerenciamento. Após os dispositivos serem registrados, o sistema de gerenciamento garante que eles sejam compatíveis com suas políticas antes que possam acessar dados corporativos. Além disso, a [Ferramenta de Disposição do Aplicativo e o SKD do Aplicativo](apps-prepare-mobile-application-management.md) do Intune podem ajudar a conter os dados acessados dentro de seu aplicativo de linha de negócios, de modo que ele não possa transmitir dados corporativos para serviços ou aplicativos de consumidor.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Proteger seus dados e emails do Office 365 para que eles possam ser acessados com segurança por dispositivos móveis
Proteger dados corporativos no Office 365 (email, documentos, mensagens instantâneas, contatos) não poderia ser mais fácil para você ou perfeita para seus usuários.


O Intune e o Microsoft Enterprise Mobility + Security fornecem uma solução de acesso condicional integrada exclusivamente que garante que nenhum usuário, aplicativo ou dispositivo pode acessar dados do Office 365, a menos que eles atendam aos requisitos de conformidade da empresa ([autenticação multifator](/intune-classic/deploy-use/multi-factor-authentication-azure-active-directory) executada, registrado no Intune, usando o aplicativo gerenciado, versão do sistema operacional com suporte, PIN do dispositivo, perfil de risco do usuário baixo etc.).


Os aplicativos móveis do Office nas respectivas lojas de aplicativos estão prontos para uso, com políticas de confinamento de dados que você pode configurar por meio do Intune. Isso permite que você impeça que os dados sejam compartilhados com aplicativos (por exemplo, aplicativos de email nativos) e locais de armazenamento (por exemplo, o Dropbox) que não são gerenciados pelo departamento de TI. Toda essa funcionalidade é incorporada ao Office 365 e EMS. Você não precisa implantar uma infraestrutura adicional para obter esse valor.

Uma prática comum de implantação do Office 365 é exigir que os dispositivos se registrem no gerenciamento caso eles precisem ser totalmente configurados com configurações de aplicativos corporativos, certificados, Wi-Fi ou VPN, o que é comum para dispositivos corporativos.  


No entanto, se o usuário apenas precisar acessar documentos e emails corporativos, o que é geralmente o caso para dispositivos pessoais, você poderá solicitar que ele use os aplicativos móveis do Office (aos quais você aplicou as [políticas de proteção de aplicativo](app-protection-policies.md)) ([Portal Clássico](/intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune)) e ignore completamente o registro do dispositivo.  



De qualquer forma, os dados do Office 365 serão protegidos pelas políticas que você definiu.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>Oferecer um programa do tipo traga seu próprio dispositivo para todos os funcionários
O BYOD (traga seu próprio dispositivo) continua crescendo em termos de popularidade entre as organizações como um meio para reduzir as despesas de hardware ou aumentar as opções de produtividade móvel para os funcionários. Praticamente todos têm um telefone pessoal hoje em dia, então por que colocar outro no seu bolso? O principal desafio sempre foi convencer os funcionários a registrar seu dispositivo pessoal no gerenciamento, uma vez que eles têm receio de que seu departamento de TI poderá ver e fazer com seus dispositivos.  

Quando o registro de dispositivo não é uma opção viável, o Intune oferece uma abordagem alternativa de BYOD de apenas [gerenciar os aplicativos que contêm dados corporativos](app-protection-policies.md) ([portal Clássico](/intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune)). O Intune protege os dados corporativos mesmo se o aplicativo em questão acessa dados corporativos e pessoais, como no caso de aplicativos móveis do Office.  

Como administrador, você pode exigir que os usuários acessem o Office 365 dos aplicativos móveis do Office e configurem os aplicativos com políticas que mantenham os dados protegidos (como criptografá-los, protegê-los com PIN, etc.). Essas políticas de proteção de aplicativos impedem a perda de dados de aplicativos e locais de armazenamento não gerenciados, dentro ou fora desses aplicativos. Por exemplo, as políticas impedem que um usuário copie texto de um perfil de email corporativo para um perfil de email de consumidor mesmo se os dois perfis estiverem configurados no Outlook Mobile. Configurações semelhantes podem ser implantadas em outros serviços e aplicativos necessários para os usuários de BYOD.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-employees"></a>Fornecer telefones corporativos para seus funcionários
A maioria dos funcionários é móvel hoje em dia, tornando a produtividade em dispositivos móveis fundamental para a competitividade. Esses funcionários precisam de acesso contínuo a todos os aplicativos e dados corporativos, a qualquer momento, independentemente de onde estiverem. Você precisa garantir que os dados corporativos estejam seguros e os custos administrativos sejam baixos.  

O Intune oferece [soluções de gerenciamento e provisionamento em massa](device-enrollment.md) ([Portal Clássico](/intune-classic/deploy-use/manage-corporate-owned-devices)) que são integradas com as principais plataformas de gerenciamento de dispositivos corporativos do mercado atualmente, incluindo o Programa de registro de dispositivos da Apple e a plataforma de segurança móvel do Samsung Knox. A criação centralizada das configurações de dispositivo com o Intune ajuda a tornar o provisionamento de dispositivos corporativos algo que pode ser altamente automatizado.  

Imagine: entregar a um funcionário uma caixa de iPhone fechada. O funcionário o liga e é guiado por um fluxo de instalação da empresa, no qual ele deve se autenticar. O iPhone está configurado perfeitamente com as [políticas de segurança](device-profiles.md) ([portal Clássico](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)).

Em seguida, o funcionário inicia o aplicativo de Portal da Empresa do Intune para acessar os aplicativos corporativos opcionais disponíveis para ele.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-employees"></a>Fornecer tablets compartilhados de uso limitado para seus funcionários
Os funcionários estão usando cada vez mais as tecnologias móveis. Por exemplo, tablets compartilhados agora são usados comumente por funcionários de lojas varejistas.  Quer sejam usados para processar uma venda ou verificar o estoque instantaneamente, os tablets ajudam a criar excelentes interações com o cliente.

A simplicidade da experiência do usuário é fundamental nesse caso. Por esse motivo, os tablets geralmente são entregues para os funcionários em um modo de uso limitado, de modo que um único aplicativo de linha de negócios é a única coisa com a qual o funcionário pode interagir. O Intune permite que você provisione, proteja e gerencie em massa e de forma centralizada esses dispositivos [iOS e Android](device-profiles.md) compartilhados ([portal Clássico](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)) que podem ser configurados para serem executados nesse modo de uso limitado.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Habilitar os funcionários para acessar o Office 365 de forma segura de um quiosque público não gerenciado
Às vezes, seus funcionários precisam usar dispositivos, aplicativos ou navegadores que você não pode gerenciar, como os computadores públicos em feiras de negócios e lobbies de hotel.

Você deve permitir que seus funcionários acessem o email corporativo deles? Com o Intune e o Microsoft Enterprise Mobility + Security, a resposta pode ser simplesmente “não”, [limitando o acesso a email aos dispositivos que são gerenciados pela sua organização](conditional-access.md) ([portal Clássico](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)). Isso garante que seu funcionário com autenticação forte não deixe dados corporativos em um computador não confiável acidentalmente.
