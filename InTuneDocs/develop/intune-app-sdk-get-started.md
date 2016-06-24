---
# required metadata

title: Introdução ao SDK de Aplicativo do Microsoft Intune | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Introdução ao SDK de Aplicativos do Microsoft Intune

Este Guia de introdução o ajudará a habilitar rapidamente seu aplicativo móvel para o Gerenciamento de aplicativos móveis com o Microsoft Intune. Pode ser útil compreender primeiro os benefícios do SDK de Aplicativo do Intune enumerados na [Visão geral do SDK do Aplicativo do Intune](intune-app-sdk.md).

Este guia aborda as principais etapas necessárias para habilitar o gerenciamento de aplicativos móveis em seu aplicativo com o Microsoft Intune. O SDK de Aplicativos do Intune dá suporte a cenários semelhantes em diferentes plataformas e destina-se a criar uma experiência consistente em todas as plataformas para os administradores de TI. No entanto, existem pequenas diferenças no suporte a determinados recursos devido a limitações da plataforma.

# Guia de introdução

## Registrar-se para o Microsoft Connect

Atualmente, o SDK de Aplicativos do Intune está acessível por meio do Microsoft Connect e requer logon. Para fazer isso, registre-se para uma [Conta da Microsoft](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X) usando seu email corporativo.

O registro ficará com status pendente até que a equipe do Intune analise sua solicitação. O tempo típico de resposta é de 2 a 3 dias úteis. Depois de aprovado, você receberá uma notificação por email com os links para baixar o SDK de Aplicativos do Intune para suas plataformas e todos os guias de relacionados. Você também pode acessar essas guias no site do MSDN.

## Registrar seu aplicativo de armazenamento no Microsoft Intune

**Se seu aplicativo habilitado for interno à sua empresa e não estiver disponível na loja de aplicativos da Apple ou do Google**: não será necessário registrar o aplicativo. Para esses aplicativos internos, o administrador de TI os carregará diretamente no console do Microsoft Intune para implantação, o Intune detectará que o aplicativo foi desenvolvido com o SDK e apresentará ao administrador de TI a opção de aplicar a política de MAM a ele. Você pode ignorar a seção intitulada [Habilitar seu aplicativo móvel iOS ou Android para MAM com o SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Se você for um ISV desenvolvendo um aplicativo que será disponibilizado para os clientes por meio das lojas de aplicativos da Apple ou do Google**: deverá primeiro registrar seu aplicativo no Microsoft Intune e concordar com os termos de registro. Você pode fornecer um link profundo do aplicativo neste momento. Depois, um administrador de TI pode aplicar a política de MAM do Intune ao aplicativo. Até que o registro tenha sido concluído e confirmado pela equipe do Microsoft Intune, o link profundo do aplicativo não terá a opção de aplicar a política de MAM no console do administrador. A Microsoft também mantém um site de parceiros do Microsoft Intune, onde o aplicativo será registrado para que os clientes saibam que ele oferece suporte à política de MAM do Microsoft Intune.

Para iniciar o processo de registro, **analise e assine** o [contrato de parceiro do Microsoft Intune](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Este contrato descreve os termos que sua empresa deve aceitar antes de se tornar um parceiro de aplicativo do Microsoft Intune. Você precisará entrar antes de exibir este documento. Você pode encontrar o contrato do site na guia pesquisas Intune aplicativo SDK Microsoft Connect ou na guia Pesquisas localizada aqui. Também pedimos que você forneça o nome do aplicativo, nome da empresa e o link profundo do seu aplicativo na loja do Google ou iTunes.

![Microsoft Connect](../media/microsoft-connect.png)

Nós usaremos seu endereço de email de registro para confirmar e concluir o recebimento do processo de registro. Além disso, usamos o seu endereço de email de registro para entrar em contato com você caso tenhamos quaisquer dúvidas.

**O que esperar do processo de registro**: depois de ter enviado o formulário, você será contatado pela Microsoft por meio de seu endereço de email de registro para confirmar o recebimento bem-sucedido ou solicitar informações adicionais para concluir o registro. Você também será contatado quando seu aplicativo for registrado com êxito no Microsoft Intune e quando ele estiver em destaque no site de parceiros do Microsoft Intune. Após o recebimento das informações ser confirmado, o link profundo do aplicativo será incluído na próxima atualização mensal do Intune Service. Por exemplo, se as informações de registro forem concluídas em julho, o link profundo do aplicativo terá suporte em meados de agosto. Se o link profundo do aplicativo da loja for alterado no futuro, você precisará registrar novamente o aplicativo. Além disso, informe se você atualizar seu aplicativo com uma nova versão do SDK de Aplicativos do Intune.

**Observação**: todas as informações coletadas no formulário acima e por correspondência por email com a equipe do Intune serão tratadas de acordo com a [Declaração de Privacidade da Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Habilitar seu aplicativo móvel iOS ou Android para MAM com o SDK

Para habilitar seu aplicativo móvel iOS, você precisará do seguinte:

1. **[Intune App SDK for iOS Developer Guide](intune-app-sdk-ios.md)** (Guia do SDK de Aplicativo do Intune para desenvolvedor de iOS): este documento vai orientá-lo passo a passo durante a habilitação do seu aplicativo móvel iOS com o SDK de Aplicativo do Intune. Você pode encontrar este documento na pasta de documentação que você baixou como parte do pacote do SDK de Aplicativos do Intune.
2. **SDK de Aplicativos do Intune para iOS**: como parte do pacote do SDK de Aplicativos do Intune baixado do Microsoft Intune, você encontrará uma pasta assinada "SDK de aplicativo Intune para iOS". Esta pasta tem todo o conteúdo do SDK de Aplicativos do Intune para iOS.

Para habilitar seu aplicativo móvel Android com o SDK de Aplicativos do Intune, você precisará do seguinte:

1. **[Intune App SDK for Android Developer Guide](intune-app-sdk-android.md)** (Guia do desenvolvedor de SDK de Aplicativo do Intune para Android): este documento vai orientá-lo passo a passo durante a habilitação do seu aplicativo móvel Android com o SDK de Aplicativo do Intune. Você pode encontrar este documento na pasta de documentação que você baixou como parte do pacote do SDK de Aplicativos do Intune.
2. **SDK de Aplicativos do Intune para Android**: como parte do pacote do SDK de Aplicativos do Intune baixado do Microsoft Intune, você encontrará uma pasta assinada "SDK de aplicativo Intune para Android". Esta pasta tem todo o conteúdo do SDK de Aplicativos do Intune para Android.

## Desativando a telemetria para seu aplicativo

**SDK de Aplicativo Intune para iOS**: o SDK registra dados de telemetria do SDK sobre eventos de uso por padrão. Esses dados são enviados para o Microsoft Intune.

Se optar por não enviar dados de telemetria do SDK para o Microsoft Intune do seu aplicativo, você **deverá desabilitar** a transmissão de telemetria pelo SDK definindo a propriedade `MAMTelemetryDisabled` para ”SIM” em `IntuneMAMSettings`.

**SDK de aplicativo Intune para Android**: os dados de telemetria do SDK não são registrados por meio do SDK.

## Testar seu aplicativo habilitado para MAM com o Microsoft Intune

Depois de concluir as etapas necessárias para esclarecer (integrar o SDK de Aplicativos do Intune) seu SDK de Aplicativos do Intune do iOS ou Android, você precisará garantir que todas as políticas de gerenciamento de aplicativo estejam habilitadas e funcionando para o usuário final e o administrador de TI. Para testar seu aplicativo habilitado, você precisará do seguinte:

1. **Testando seu aplicativo habilitado para MAM com o Microsoft Intune**: este documento orientará você passo a passo sobre como testar seus aplicativos iOS ou android MAM com o Microsoft Intune. Você pode encontrar este documento na pasta de documentação que você baixou como parte do pacote do SDK de Aplicativos do Intune.
2. **Conta do Microsoft Intune**: para testar seus aplicativos habilitados para MAM com o Microsoft Intune, você precisará de uma conta do Microsoft Intune. Se for um ISV habilitando seus aplicativos iOS ou Android para, você receberá um código de promoção após concluir o registro com o Microsoft Intune, conforme descrito na etapa de registro. O código de promoção permitirá que você se inscreva para uma avaliação de 1 ano de uso estendido Microsoft Intune. Se estiver desenvolvendo um aplicativo de linha de negócios que não será enviado para a loja, você deverá ter acesso ao Microsoft Intune por meio de sua organização. Você pode se inscrever para 1 mês de avaliação gratuita no [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).



<!--HONumber=May16_HO2-->


