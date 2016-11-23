---
title: "Introdução ao SDK de Aplicativo do Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.author: oydang
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4623db80d711f3543b6d688fb1bb1ef228c62c
ms.openlocfilehash: 2a65ae79a0bba21d555dbed9f1bc40e01452f08c


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Introdução ao SDK de Aplicativos do Microsoft Intune

Este guia o ajudará a habilitar rapidamente seu aplicativo móvel para o MAM (gerenciamento de aplicativos móveis) com o Microsoft Intune. Pode ser útil compreender primeiro os benefícios do SDK de Aplicativo do Intune enumerados na [Visão geral do SDK de Aplicativos do Intune](intune-app-sdk.md).

Este guia aborda as principais etapas para habilitar o MAM em seu aplicativo com o Microsoft Intune. O SDK de Aplicativos do Intune dá suporte a cenários semelhantes em diferentes plataformas e destina-se a criar uma experiência consistente em todas as plataformas para os administradores de TI. Porém, há pequenas diferenças no suporte a determinados recursos devido a limitações da plataforma.

## <a name="register-your-store-app-with-microsoft"></a>Registrar seu aplicativo de uma loja de aplicativos no Microsoft

**Se o aplicativo for interno à sua empresa e não for disponibilizado em uma loja de aplicativos pública**:

Você *não precisa* registrar seu aplicativo. Para aplicativos de linha de negócios internos, o administrador de TI implantará o aplicativo internamente. O Intune detectará que o aplicativo foi criado com o SDK e permitirá que o administrador de TI aplique configurações de política de MAM a ele. Você pode passar diretamente para a seção [Habilitar seu aplicativo móvel iOS ou Android para MAM com o SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Se o aplicativo for liberado para uma loja de aplicativos pública, como a Apple App Store ou o Google Play**:

Primeiro, você *precisa* registrar seu aplicativo com o Microsoft Intune e concordar com os termos de registro. Os administradores de TI podem aplicar configurações de política de MAM do Intune ao aplicativo habilitado, que será listado como um parceiro de aplicativo do Intune. Até a conclusão e a confirmação do registro pela equipe do Microsoft Intune, os administradores do Intune não terão a opção de aplicar a política de MAM ao link profundo do seu aplicativo. A Microsoft também adicionará seu aplicativo à [página Parceiros do Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). Nessa página, o ícone do aplicativo será exibido para mostrar que ele oferece suporte à política de MAM do Microsoft Intune.

Para iniciar o processo de registro, preencha o [Questionário de Parceiro de Aplicativo do Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

Usaremos os endereços de email listados em suas respostas ao questionário para entrar em contato e continuar o processo de registro. Além disso, usamos o seu endereço de email de registro para entrar em contato com você caso tenhamos quaisquer dúvidas.

> [!NOTE]
> Todas as informações coletadas no questionários e por email com a equipe do Microsoft Intune serão tratadas de acordo com a [Política de Privacidade da Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**O que esperar no processo de registro**:

1. Após enviar o questionário, nós contataremos você pelo endereço de email registrado para confirmar o recebimento ou para solicitar informações adicionais para concluir o registro.
2. Após recebermos de você todas as informações necessárias, enviaremos o Contrato de Parceiro do Aplicativo do Microsoft Intune para você assinar. Este contrato descreve os termos que sua empresa deve aceitar antes de se tornar um parceiro de aplicativo do Microsoft Intune.
3. Você também será notificado quando seu aplicativo for registrado com êxito no serviço do Microsoft Intune e quando ele estiver em destaque no site de [parceiros do Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps).
4. Por fim, o link profundo de seu aplicativo será adicionado à próxima atualização mensal do Serviço do Intune. Por exemplo, se as informações o registro forem concluídas em julho, o link profundo terá suporte em meados de agosto.

Se o link profundo do aplicativo for alterado no futuro, você precisará registrar novamente o aplicativo. Além disso, informe se você atualizar seu aplicativo com uma nova versão do SDK de Aplicativo do Intune.



## <a name="download-the-sdk-files"></a>Baixar os arquivos do SDK

Os SDKs do Aplicativo do Intune para iOS e Android nativo são hospedados em uma conta do GitHub da Microsoft. Estes repositórios públicos contêm os arquivos do SDK para iOS e Android, respectivamente:

* [SDK de Aplicativo do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK de Aplicativo do Intune para Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Se seu aplicativo for um aplicativo Xamarin ou Cordova, use estas ferramentas de desenvolvedor:

* [Componente Xamarin do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Plug-in Cordova do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Convém criar uma conta do GitHub que você possa usar para bifurcar e efetuar pull de nosso repositórios. O GitHub permite que os desenvolvedores se comuniquem com nossa equipe de produto, abram questões e recebam respostas rápidas, exibam notas de versão e forneçam comentários à Microsoft. Para enviar perguntas sobre a conta e os repositórios do GitHub, entre em contato com msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Habilitar seu aplicativo móvel iOS ou Android para MAM com o SDK

Para integrar o SDK do Aplicativo do Intune em seu aplicativo iOS nativo, você precisará do seguinte:

* **[Guia do desenvolvedor do SDK de Aplicativos do Intune para iOS](intune-app-sdk-ios.md)**: este documento fornece uma orientação passo a passo durante a habilitação de seu aplicativo móvel iOS com o SDK de Aplicativos do Intune.


Para integrar o SDK do Aplicativo do Intune em seu aplicativo Android nativo, você precisará do seguinte:

* **[Guia do desenvolvedor do SDK de Aplicativos do Intune para Android](intune-app-sdk-android.md)**: este documento fornece uma orientação passo a passo durante a habilitação de seu aplicativo móvel Android com o SDK de Aplicativos do Intune.

Para compilar aplicativos Cordova com o Plug-in do Cordova do SDK de Aplicativo Intune, você precisará do seguinte:

* **[Guia de plug-in do Cordova do SKD de Aplicativo do Intune](intune-app-sdk-cordova)**: este documento ajudará você a criar aplicativos iOS e Android usando o Cordova para gerenciamento de aplicativos móveis do Intune.

Para compilar aplicativos Xamarim com o Componente do Xamarin do SDK de Aplicativo do Intune, você precisará do seguinte:

* **[Guia do Componente do Xamarin do SDK de Aplicativo do Intune](intune-app-sdk-xamarin)**: este documento o ajudará a criar aplicativos iOS e Android usando o Cordova para gerenciamento de aplicativos móveis do Intune.




## <a name="configure-telemetry-for-your-app"></a>Configurando a Telemetria para seu aplicativo

O Microsoft Intune coleta dados sobre estatísticas de uso para seu aplicativo.

* **SDK de Aplicativo Intune para iOS**: o SDK registra dados de telemetria do SDK sobre eventos de uso por padrão. Esses dados são enviados para o Microsoft Intune.

    * Se optar por não enviar dados de telemetria do SDK para o Microsoft Intune do seu aplicativo, você deverá desabilitar a transmissão de telemetria definindo a propriedade `MAMTelemetryDisabled` como ”YES” no dicionário IntuneMAMSettings.

* **SDK do Aplicativo do Intune para Android**: os dados de telemetria não são registrados por meio do SDK.

## <a name="test-your-mam-enabled-app-with-microsoft-intune"></a>Testar seu aplicativo habilitado para MAM com o Microsoft Intune

Depois de concluir as etapas necessárias para integrar seu aplicativo iOS ou Android com o SDK de Aplicativos do Intune, você precisará garantir que todas as políticas de gerenciamento de aplicativo estejam habilitadas e funcionando para o usuário final e o administrador de TI. Para testar seu aplicativo integrado, você precisará do seguinte:

<!--TODO-->

* **Testar seu aplicativo habilitado para MAM com o Microsoft Intune**: este documento fornece uma orientação passo a passo para testar seus aplicativos iOS ou Android habilitados para MAM com o Microsoft Intune. Você pode encontrar este documento nos repositórios GitHub sobre os SDKs.

* **Conta do Microsoft Intune**: para testar seus aplicativos habilitados para MAM com o Microsoft Intune, você precisará de uma conta do Microsoft Intune.
    * Se for um ISV habilitando seus aplicativos iOS ou Android para o MAM do Intune, você receberá um código de promoção após concluir o registro com o Microsoft Intune, conforme descrito na etapa de registro. O código de promoção permitirá que você se inscreva para uma avaliação de um ano de uso estendido do Microsoft Intune.
    * Se estiver desenvolvendo um aplicativo de linha de negócios que não será enviado para a loja, você deverá ter acesso ao Microsoft Intune por meio de sua organização. Você também pode se inscrever para uma avaliação gratuita de uma mês no [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).



<!--HONumber=Nov16_HO3-->


