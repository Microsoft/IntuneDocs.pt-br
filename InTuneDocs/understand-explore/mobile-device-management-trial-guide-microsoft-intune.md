---
title: "Avaliar o gerenciamento de dispositivos móveis no Microsoft Intune | Documentos da Microsoft"
description: "Avaliar o MDM na sua avaliação gratuita do Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Avaliar o gerenciamento de dispositivos móveis no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este guia de avaliação mostrará como funciona o gerenciamento de dispositivos móveis no Intune. Você irá:
- Registrar um dispositivo a ser gerenciado pelo Intune.
- Criar grupos para organizar usuários e dispositivos.
- Criar e implantar algumas políticas de gerenciamento de dispositivos para seus grupos.
- Publicar um aplicativo para que os usuários com dispositivos registrados possam instalá-lo em seu dispositivo.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Suposições
Este guia pressupõe que você esteja usando a versão de avaliação apenas a finalidade da avaliação e pretende iniciar com um ambiente limpo quando se inscrever.

Para facilitar o início do uso da versão de avaliação, estamos configurando um ambiente muito simples que usa apenas o Intune e pressupõe que ele será sua autoridade de gerenciamento de dispositivos móveis. No entanto, neste guia, apontaremos para o conteúdo técnico mais profundo se você quiser explorar um pouco mais.

Na versão de avaliação, é possível fazer tudo o que se faz em uma versão de assinatura. A única diferença é que você está limitado a 100 contas de usuário na avaliação.

## <a name="whats-not-covered"></a>O que não é abordado
|Se estiver interessado em |Leia isto |
|------------------------|----------|
|MDM em um ambiente que não é de teste | [Introdução](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|MDM com Intune e System Center Configuration Manager | [Gerenciamento híbrido de dispositivo móvel](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Como os guias acima ajudam a configurar o Intune em ambientes de produção, eles são maiores, com vários pontos de decisão necessários a mais para trabalhar do que no guia de avaliação.

Para se familiarizar rapidamente com o Intune, sugerimos começar com o guia de avaliação e, em seguida, passar para os outros guias.

## <a name="prerequisites-for-this-evaluation"></a>Pré-requisitos para essa avaliação
- Internet Explorer 10 ou posterior
- Um dispositivo que você usará para testar como usuários vão registrar e gerenciar seus dispositivos usando o Portal da Empresa. Estamos usando um iPad e um telefone Android neste guia.
- Para gerenciar o iPad ou outro dispositivo iOS, você precisará de um [certificado Apple Push Notification Service](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- Uma [assinatura de avaliação do Intune](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>Configurar a sua autoridade MDM
A primeira etapa que você precisa executar para gerenciar dispositivos móveis com o Intune é definir sua **autoridade de gerenciamento de dispositivo móvel (MDM)**.

Se você estiver usando o Intune autônomo, como esta avaliação pressupõe que esteja, ou se estiver usando o Intune como parte de uma assinatura Enterprise Mobility + Security (EMS), precisará configurar o Intune para ser sua autoridade de gerenciamento de dispositivo móvel. Ou seja, você pode designar o Intune para ser o serviço que usa para gerenciar dispositivos móveis na sua organização.

Os clientes que desejarem usar o Intune com o System Center Configuration Manager para gerenciar dispositivos móveis precisam decidir se desejam usar o Intune ou Configuration Manager como sua autoridade de gerenciamento de dispositivo móvel. Isso é uma decisão importante fazer em um ambiente de produção porque, no momento, é muito difícil alterar a configuração depois, mas isso está além do escopo deste guia de avaliação. Para saber mais sobre as implicações de configurar o Intune ou Configuration Manager como sua autoridade MDM, consulte [Escolher entre Intune autônomo e gerenciamento híbrido de dispositivo móvel](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

Configuraremos o Intune como a autoridade MDM para a avaliação; isso não afetará seu ambiente de produção a menos que você decida usar a versão de avaliação para o seu ambiente de produção.

1. No [console de administração do Intune](https://manage.microsoft.com/), clique em **Admin** &gt; **Gerenciamento de Dispositivo Móvel**.
2. Na lista **Tarefas**, escolha **Definir autoridade MDM**. A caixa de diálogo **Definir autoridade MDM** é aberta. <!---screen shot--->
3. O Intune solicita a confirmação de que você deseja o Intune como autoridade MDM. Marque a caixa de seleção e escolha **Sim** para usar o Intune para gerenciar dispositivos móveis.

## <a name="enroll-your-test-devices-into-intune"></a>Registrar dispositivos de teste no Intune

Para este guia, estaremos registrando um telefone Android e um iPad da Apple, mas forneceremos links para [saber mais sobre o registro do dispositivo no Intune](#Learn-more-about-device-enrollment) no final desta seção.
### <a name="android"></a>Android
Instale o aplicativo **Portal da Empresa do Intune** da Microsoft Corporation, disponível no [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) e entre com as [credenciais de usuário do Intune criadas](sign-up-for-30-day-trial-microsoft-intune.md#add-users) quando você se inscreveu para a avaliação gratuita.

### <a name="ios"></a>iOS
Antes de os usuários poderem registrar seus dispositivos iOS, você precisará configurar o Intune para gerenciar esses dispositivos.

1. **Obtenha uma solicitação de assinatura de certificado**<br/>
Faça logon no Intune com sua conta de administrador e vá para **Administração** > **Gerenciamento de Dispositivos Móveis** > **iOS e Mac OS X** > **Carregar um Certificado APNs** e escolha **Baixar a solicitação de certificado APNs**. Salve o arquivo (.csr) da solicitação de assinatura do certificado localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push. <!--- screen shot--->
2.  **Obtenha um certificado do serviço Apple Push Notification**<BR/>
Vá para o [Portal Apple Push Certificates](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2) e entre com sua ID da Apple corporativa para criar o certificado APNs usando o arquivo .csr. Depois de clicar em **Carregar no Apple Push Certificates Portal**, você receberá um arquivo .json que não pode ser usado para o APNs. Conclua o download e retorne ao Apple Push Certificates Portal para Certificados de Servidores de Terceiros e escolha **Download**.

 Baixe o certificado APNs (.pem) e salve o arquivo localmente. Essa ID da Apple deve ser usada posteriormente para renovar seu certificado APNs.
3.  **Adicionar o certificado de APNs ao Intune**<BR/>
No console de administração do Microsoft Intune, vá para **Administração** > **Gerenciamento de Dispositivos Móveis** > **iOS e Mac OS X** > **Carregar um Certificado APNs** e escolha **Carregar o certificado APNs**. Vá até o arquivo de certificado (.pem), escolha **Abrir** e digite sua ID da Apple. Com o certificado APNs, o Intune pode registrar e gerenciar dispositivos iOS enviando políticas para dispositivos móveis registrados.
4.  **Informe aos usuários como registrar seus dispositivos para obter acesso aos recursos da empresa.**<br/>
Para obter instruções sobre o registro de usuário final, consulte [Registrar seu dispositivo iOS no Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) ou [Registrar seu dispositivo Mac OS X no Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.


### <a name="learn-more-about-device-enrollment"></a>Saiba mais sobre registro de dispositivos

O Intune dá suporte às seguintes plataformas de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Os requisitos para habilitar o gerenciamento de dispositivos dependem das plataformas que você deseja gerenciar.
- Os dispositivos móveis **Android** permitem que usuários [realizem seu registro usando o aplicativo do Portal da Empresa](/intune/deploy-use/set-up-android-management-with-microsoft-intune) disponível no Google Play. Nenhuma configuração adicional no Intune é necessária.
- [Requisitos de configuração para **iOS e Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Requisitos de configuração para **Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Próximas etapas
[Criar grupos para organizar usuários e dispositivos](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Jan17_HO1-->


