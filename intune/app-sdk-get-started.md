---
title: "Introdução ao SDK de Aplicativos do Microsoft Intune"
description: "Habilite rapidamente seu aplicativo móvel para MAM (gerenciamento de aplicativo móvel) com o Microsoft Intune."
keywords: 
author: mattbriggs
manager: angrobe
ms.author: mabriggs
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0e55246f8f089a998fa4a04fe07e5e54408d8513
ms.sourcegitcommit: f3b8fb8c47fd2c9941ebbe2c047b7d0a093e5a83
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2017
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Introdução ao SDK de Aplicativos do Microsoft Intune

Este guia ajudará você a habilitar rapidamente seu aplicativo móvel para políticas de proteção do aplicativo com o Microsoft Intune. Pode ser útil compreender primeiro os benefícios do SDK de Aplicativo do Intune enumerados na [Visão geral do SDK de Aplicativos do Intune](app-sdk.md).

O SDK do Aplicativo do Intune dá suporte a cenários semelhantes no iOS e Android e destina-se a criar uma experiência consistente em todas as plataformas para os administradores de TI. Porém, há pequenas diferenças no suporte a determinados recursos devido a limitações da plataforma.

## <a name="register-your-store-app-with-microsoft"></a>Registrar seu aplicativo de uma loja de aplicativos no Microsoft

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Caso o aplicativo seja interno à sua organização e não esteja disponível publicamente:

Você *não precisa* registrar seu aplicativo. Para aplicativos de linha de negócios internos, o administrador de TI implantará o aplicativo internamente. O Intune detectará que o aplicativo foi criado com o SDK e permitirá que o administrador de TI aplique a política de proteção do aplicativo a ele. É possível ignorar a seção [Habilitar o aplicativo iOS ou Android para a política de proteção do aplicativo](#enable-your-iOS-or-Android-app-for-app-protection-policy).

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Se o aplicativo for liberado para uma loja pública de aplicativos, como a Apple App Store ou o Google Play:

Primeiro, você _**deve**_ registrar o aplicativo no Microsoft Intune e concordar com os termos de registro. Em seguida, os administradores de TI poderão aplicar a política de proteção do aplicativo ao aplicativo habilitado, que será listado como um parceiro de aplicativos do Intune.

Somente depois que o registro for concluído e confirmado pela equipe do Microsoft Intune os administradores do Intune terão a opção de aplicar a política de proteção do aplicativo ao link profundo do aplicativo. A Microsoft também adicionará seu aplicativo à [página Parceiros do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps). Nessa página, o ícone do aplicativo será exibido para mostrar que ele dá suporte às políticas de proteção do aplicativo do Intune.

Para iniciar o processo de registro, preencha o [Questionário de Parceiro de Aplicativo do Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

Usaremos os endereços de email listados em suas respostas ao questionário para contatá-lo e continuar o processo de registro. Além disso, usamos o seu endereço de email de registro para entrar em contato com você caso tenhamos quaisquer dúvidas.

> [!NOTE]
> Todas as informações coletadas no questionários e por email com a equipe do Microsoft Intune serão tratadas de acordo com a [Política de Privacidade da Microsoft](https://www.microsoft.com/privacystatement/default.aspx).

**O que esperar no processo de registro**:

1. Após enviar o questionário, nós contataremos você pelo endereço de email registrado para confirmar o recebimento ou para solicitar informações adicionais para concluir o registro.

2. Após recebermos de você todas as informações necessárias, enviaremos o Contrato de Parceiro do Aplicativo do Microsoft Intune para você assinar. Este contrato descreve os termos que sua empresa deve aceitar antes de se tornar um parceiro de aplicativo do Microsoft Intune.

3. Você também será notificado quando seu aplicativo for registrado com êxito no serviço do Microsoft Intune e quando ele estiver em destaque no site de [parceiros do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

4. Por fim, o link profundo de seu aplicativo será adicionado à próxima atualização mensal do Serviço do Intune. Por exemplo, se as informações o registro forem concluídas em julho, o link profundo terá suporte em meados de agosto.

Se o link profundo do aplicativo for alterado no futuro, você precisará registrar novamente o aplicativo.

> [!NOTE]
> Além disso, informe se você atualizou o aplicativo com uma nova versão do SDK do Aplicativo do Intune.



## <a name="download-the-sdk-files"></a>Baixar os arquivos do SDK

Os SDKs do Aplicativo do Intune para iOS e Android nativo são hospedados em uma conta do GitHub da Microsoft. Esses repositórios públicos têm os arquivos do SDK para o iOS e Android nativo, respectivamente:

* [SDK de Aplicativo do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK de Aplicativo do Intune para Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Caso o aplicativo seja um aplicativo Xamarin ou Cordova, use essas variantes do SDK:

* [Componente Xamarin do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Plug-in Cordova do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Convém criar uma conta do GitHub que você possa usar para bifurcar e efetuar pull de nosso repositórios. O GitHub permite que os desenvolvedores se comuniquem com nossa equipe de produto, abram questões e recebam respostas rápidas, exibam notas de versão e forneçam comentários à Microsoft. Em caso de dúvidas sobre o GitHub do SDK do Aplicativo do Intune, contate msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>Habilitar o aplicativo iOS ou Android para a política de proteção do aplicativo

Você precisará de um dos seguintes guias do desenvolvedor para ajudá-lo a integrar o SDK do Aplicativo do Intune em seu aplicativo:

* **[Guia do Desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md)**: esse documento fornece um passo a passo para a habilitação do aplicativo iOS nativo com o SDK do Aplicativo do Intune.

* **[Guia do Desenvolvedor do SDK do Aplicativo do Intune para Android](app-sdk-android.md)**: esse documento fornece um passo a passo para a habilitação do aplicativo Android nativo com o SDK do Aplicativo do Intune.

* **[Guia do plug-in Cordova do SDK de Aplicativo do Intune](app-sdk-cordova.md)**: esse documento ajudará você a criar aplicativos iOS e Android usando o Cordova para as políticas de proteção do aplicativo do Intune.

* **[Guia do Componente Xamarin do SDK do Aplicativo do Intune](app-sdk-xamarin.md)**: esse documento ajudará você a criar aplicativos iOS e Android usando o Cordova para as políticas de proteção do aplicativo do Intune.




## <a name="configure-telemetry-for-your-app"></a>Configurando a Telemetria para seu aplicativo

O Microsoft Intune coleta dados sobre estatísticas de uso para seu aplicativo.

* **SDK de Aplicativo Intune para iOS**: o SDK registra dados de telemetria do SDK sobre eventos de uso por padrão. Esses dados são enviados para o Microsoft Intune.

    * Se optar por não enviar dados de telemetria do SDK para o Microsoft Intune do seu aplicativo, você deverá desabilitar a transmissão de telemetria definindo a propriedade `MAMTelemetryDisabled` como ”YES” no dicionário IntuneMAMSettings.


* **SDK do Aplicativo do Intune para Android**: os dados de telemetria não são registrados por meio do SDK.

## <a name="next-steps-after-integration"></a>Próximas etapas após integração

### <a name="test-your-app"></a>Teste seu aplicativo
Depois de concluir as etapas necessárias para integrar seu aplicativo iOS ou Android com o SDK do Aplicativo do Intune, você precisará garantir que todas as políticas de proteção do aplicativo estão habilitadas e funcionando para o usuário e o administrador de TI. Para testar seu aplicativo integrado, você precisará do seguinte:

* **Conta de teste do Microsoft Intune**: para testar seu aplicativo habilitado pelo Intune nos recursos de proteção do aplicativo do Intune, você precisará de uma conta do Microsoft Intune.

    * Se você for um ISV que habilita aplicativos da loja do iOS ou do Android para a política de proteção do aplicativo do Intune, receberá um código promocional após a conclusão do registro no Microsoft Intune, conforme descrito na etapa de registro. O código de promoção permitirá que você se inscreva para uma avaliação de um ano de uso estendido do Microsoft Intune.

    * Se estiver desenvolvendo um aplicativo de linha de negócios que não será enviado para a loja, você deverá ter acesso ao Microsoft Intune por meio de sua organização. Você também pode se inscrever para uma avaliação gratuita de uma mês no [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).

* **Políticas de proteção do aplicativo do Intune**: para testar seu aplicativo em todas as políticas de proteção do aplicativo do Intune, é necessário saber qual é o comportamento esperado para cada configuração da política. Consulte as descrições de [políticas de proteção do aplicativo do iOS](/intune-classic/deploy-use/ios-mam-policy-settings) e [políticas de proteção do aplicativo do Android](/intune-classic/deploy-use/android-mam-policy-settings).

* **Solução de problemas**: em caso de problemas durante o teste manual da experiência do usuário de seu aplicativo, confira [Solucionar problemas do gerenciamento de aplicativo móvel](/intune-classic/troubleshoot/troubleshoot-mam). Este artigo oferece ajuda para problemas comuns, caixas de diálogo e mensagens de erro que podem ocorrer em aplicativos habilitados pelo Intune. 

### <a name="badge-your-app-optional"></a>Marcar com uma notificação no aplicativo (opcional)

Depois de validar que as políticas de proteção do aplicativo do Intune funcionam no aplicativo, é possível marcar o ícone do aplicativo com uma notificação do logotipo de proteção do aplicativo do Intune.

Essa notificação indica aos administradores de TI, usuários finais e clientes potenciais do Intune que seu aplicativo funciona com as políticas de proteção do aplicativo do Intune. Ela incentiva o uso e a adoção de seu aplicativo pelos clientes do Intune.

A notificação é um ícone de porta-arquivos e pode ser vista nos exemplos abaixo:

![Exemplo de notificação 1](./media/badge-example-1.png) ![Exemplo de notificação 2](./media/badge-example-2.png)

**O que será necessário para marcar o aplicativo com uma notificação**:

* Um aplicativo de manipulação de imagem que pode ler arquivos **.eps** ou um aplicativo Adobe que pode ler arquivos **.ai**.

* Encontre os [ativos de notificação de aplicativo do Intune e as diretrizes](https://github.com/msintuneappsdk/intune-app-partner-badge) no GitHub do Microsoft Intune.
