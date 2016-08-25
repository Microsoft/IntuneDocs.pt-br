---
title: Maneiras comuns de usar o Intune | Microsoft Intune
description: Lista seis das tarefas mais comuns nas quais o Intune ajuda
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 76d0d9c620000864a4a554600985ba351c18d359
ms.openlocfilehash: e9315040972df39c543a1e99d197a64cf280b7ff


---

# Maneiras comuns de usar o Intune

Antes de se envolver em tarefas de implementação, é importante alinhar os participantes de mobilidade corporativa da sua empresa em relação às metas de negócios.  Isso é importante se você for novato em mobilidade corporativa ou estiver migrando de outro produto.  As necessidades em torno de mobilidade corporativa estão evoluindo dinamicamente e as abordagens da Microsoft para lidar com essas necessidades, às vezes, podem ser diferentes de outras soluções no mercado.  A melhor maneira de alinhar em relação às metas de negócios expressar o que você deseja realizar em termos dos cenários que você deseja habilitar para seus funcionários, parceiros e TI.  Abaixo estão introduções curtas para os seis cenários mais comuns que se baseiam no Intune, acompanhadas com links para obter mais informações sobre como planejar e implantar cada um deles.

>[!NOTE]
>Você deseja saber como a equipe de TI da Microsoft utiliza o Intune para permitir que os funcionários da Microsoft acessem recursos corporativos em seus dispositivos móveis enquanto também mantêm os dados corporativos protegidos? [Leia este estudo de caso técnico](https://www.microsoft.com/itshowcase/Article/Content/588) para ver em detalhes como o a equipe de TI da Microsoft utiliza o Intune e outros serviços para gerenciar identidades, dispositivos e aplicativos e dados.  

## Protegendo seus dados e emails locais para que eles possam ser acessados com segurança pelos dispositivos móveis
A maioria das estratégias de mobilidade corporativa começam com um plano para habilitar o acesso seguro ao email para funcionários com dispositivos móveis na Internet. Muitas organizações ainda têm dados locais e servidores de aplicativos, como o Microsoft Exchange, hospedados em sua rede corporativa. O Intune e o EMS (Enterprise Mobility Suite) oferecem uma [solução de acesso condicional](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) integrada exclusivamente para o Exchange Server que garante que nenhum aplicativo móvel poderá acessar o email até que o dispositivo seja registrado no Intune, tudo sem implantar outro computador de gateway na borda da sua rede corporativa!

Além do email, o Intune dá suporte à habilitação do acesso a aplicativos móveis que precisam de acesso seguro aos dados locais, como um servidor de aplicativo de linha de negócios.  Isso geralmente é feito usando [certificados gerenciados pelo Intune](/en-us/intune/deploy-use/secure-resource-access-with-certificate-profiles) para o controle de acesso combinado com um gateway de VPN padrão ou o proxy no perímetro, como o Proxy de Aplicativo do Microsoft Azure AD.  Nesses casos, a única maneira de acessar os dados corporativos é registrar o dispositivo no gerenciamento.  Depois de registrado, o sistema de gerenciamento garante que os dispositivos que acessam dados corporativos são compatíveis com suas políticas.  Além disso, a [Ferramenta de Disposição do Aplicativo e o SKD do Aplicativo](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) do Intune podem ser usadas para ajudar a conter os dados acessados dentro de seu aplicativo de linha de negócios, portanto, ele não pode passar dados corporativos para serviços ou aplicativos de consumidor.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Protegendo seus dados e emails do Office 365 para que eles possam ser acessados com segurança pelos dispositivos móveis
Proteger dados corporativos no Office 365 (email, documentos, mensagens instantâneas, contatos) não poderia ser mais fácil para você ou perfeita para seus usuários. O Intune e o Enterprise Mobility Suite fornecem uma solução de acesso condicional integrada exclusivamente que garante que nenhum usuário, aplicativo ou dispositivo possa acessar dados do Office 365, a menos que eles atendam aos requisitos de conformidade da empresa ([autenticação multifator](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication) executada, registrado no Intune, usando o aplicativo gerenciado, versão do sistema operacional com suporte, PIN do dispositivo, perfil de risco do usuário baixo etc.). Os aplicativos móveis do Office em seus respectivos repositórios do aplicativo estão prontos para serem usados com políticas de contenção de dados que podem ser configuradas por meio do Intune, permitindo que você impeça que os dados sejam compartilhados com os aplicativos (por exemplo, o aplicativo de email nativo) e locais de armazenamento (por exemplo, Dropbox) que não são gerenciados pela equipe de TI.  Toda essa funcionalidade é incorporada ao Office 365 e EMS.  Você não precisa implantar uma infraestrutura adicional para obter esse valor.

Uma prática de implantação comum do Office 365 é exigir que os dispositivos se registrem no gerenciamento, caso eles precisem ser totalmente provisionados com configurações de aplicativos/certificados/Wi-Fi/VPN corporativas, que geralmente é o caso para dispositivos corporativos.  No entanto, se o usuário simplesmente precisa acessar documentos e o email corporativo, que é geralmente o caso para dispositivos pessoais, o usuário precisa usar os aplicativos móveis do Office (aos quais você [aplicou políticas de contenção de dados](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune)) e ignorar completamente o registro do dispositivo!  De qualquer forma, os dados do Office 365 serão protegidos pelas políticas que você definiu.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## Ofereça um programa “BYOD” (traga seu próprio dispositivo) para todos os funcionários
O BYOD continua a crescer em termos de popularidade entre organizações como um meio para reduzir as despesas de hardware ou aumentar as opções de produtividade móvel para os funcionários. Praticamente todos têm um telefone pessoal hoje em dia, então por que colocar outro no seu bolso? O principal desafio sempre foi convencer os funcionários a registrar seu dispositivo pessoal no gerenciamento, uma vez que eles têm receio de que seu departamento de TI poderá ver e fazer com seus dispositivos.  

Quando o registro de dispositivo não é uma opção viável, o Intune oferece uma abordagem alternativa de BYOD de simplesmente [gerenciar os aplicativos que contêm dados corporativos](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune).  O Intune protege os dados corporativos mesmo se o aplicativo em questão acessa dados corporativos e pessoais, como no caso de aplicativos móveis do Office.  Como administrador, você pode exigir que os usuários acessem o Office 365 dos aplicativos móveis do Office e configurem os aplicativos com políticas que mantêm os dados protegidos (criptografados, protegidos por PIN, etc.).  Essas políticas impedem a perda de dados para aplicativos e locais de armazenamento não gerenciados, dentro ou fora desses aplicativos.  Por exemplo, as políticas impedirão que um usuário copie o texto de um perfil de email corporativo para um perfil de email de consumidor mesmo se os dois perfis estiverem configurados no Outlook Mobile.  Configurações semelhantes podem ser implantadas para outros serviços e aplicativos necessários para os usuários de BYOD.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Emitir telefones corporativos para seus funcionários de informações
A maioria dos funcionários de informações é móvel hoje em dia, tornando a produtividade em dispositivos móveis fundamental para sermos competitivos.  Esses funcionários precisam de acesso contínuo a todos os aplicativos e dados corporativos, a qualquer momento, independentemente de onde estiverem.  Você precisa garantir que os dados corporativos estejam seguros e os custos administrativos sejam baixos.  

O Intune oferece [soluções de gerenciamento e provisionamento em massa](/intune/deploy-use/manage-corporate-owned-devices) que estão integradas com as principais plataformas de gerenciamento de dispositivos corporativos no mercado atualmente, incluindo o Programa de Registro de Dispositivo Apple e a plataforma de segurança móvel Samsung KNOX.  A criação centralizada das configurações de dispositivo com o Intune torna o provisionamento de dispositivos corporativos algo que pode ser altamente automatizado.  

Imagine: entregar a um funcionário uma caixa de iPhone fechada. O funcionário o liga e é guiado por um fluxo de instalação da empresa, no qual ele deve se autenticar. O iPhone é configurado perfeitamente com [políticas de segurança](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (criptografia de disco rígido, PIN do dispositivo etc.), perfis de [email/Wi-Fi/VPN/certificado](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) e um conjunto de linha de base de [aplicativos](/intune/deploy-use/add-apps). Em seguida, o funcionário inicia o aplicativo de Portal da Empresa Intune para acessar aplicativos corporativos opcionais disponíveis para ele.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Emitir tablets compartilhados de uso limitado para seus funcionários
Os funcionários estão cada vez mais fazendo uso de tecnologias móveis.  Por exemplo, tablets compartilhados agora são comuns para os funcionários de lojas varejistas.  Quer sejam usados para processar uma venda ou verificar o estoque instantaneamente, os tablets ajudam a criar excelentes interações com o cliente.  A simplicidade da experiência do usuário é fundamental nesse caso.  Por esse motivo, os tablets geralmente são entregues para os funcionários em um modo de uso limitado, de modo que um único aplicativo de linha de negócios é a única coisa com a qual o funcionário pode interagir.  O Intune permite que você provisione, proteja e gerencie centralmente em massa esses tablets [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings) e [Android](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) compartilhados que podem ser configurados para funcionar nesse modo de uso limitado.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Habilitar os funcionários para acessar o Office 365 de forma segura de um quiosque público não gerenciado
Às vezes, seus funcionários precisam usar dispositivos, aplicativos ou navegadores que você não pode gerenciar, como os computadores públicos em feiras de negócios e lobbies de hotel. Você deve permitir que seus funcionários acessem o email corporativo deles? Com o Intune e o Enterprise Mobility Suite, <!--you have choices. The--> a resposta pode ser simplesmente "não" [limitando o acesso do email aos dispositivos que são gerenciados pela sua organização](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  Isso garantirá que seus funcionários com autenticação forte não deixarão acidentalmente dados corporativos em um computador não confiável.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Jul16_HO4-->


