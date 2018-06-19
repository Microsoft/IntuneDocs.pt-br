---
title: Como definir as configurações de email do Microsoft Intune
titleSuffix: ''
description: Saiba como configurar o Microsoft Intune para criar conexões com o email corporativo nos dispositivos gerenciados.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b71c004a165bd6d38cd1907eadc05ac20f27bd1a
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834203"
---
# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Como definir configurações de email no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Os perfis de email podem ser usados para configurar dispositivos gerenciados com as definições necessárias para se conectar e sincronizar com o email corporativo. Isso pode ajudar a garantir que as configurações sejam padronizadas em todos os seus dispositivos, bem como ajudar a reduzir as chamadas de suporte dos usuários finais que não conhecem as configurações de email corretas.

Há suporte para o cliente de email interno na maioria das plataformas. Atualmente, não há suporte para a maioria dos aplicativos de email de terceiros.

Você pode usar perfis de email para configurar o cliente de email nativo nos seguintes tipos de dispositivo:

- Android Samsung Knox Standard 4.0 e posterior
- Android for Work
- iOS 8.0 e posterior
- Windows Phone 8.1 e posterior
- Windows 10 (desktop) e Windows 10 Mobile

Use as informações neste artigo para aprender as noções básicas sobre a configuração de um perfil de email e leia mais tópicos para cada plataforma para saber mais sobre as particularidades dos dispositivos.

## <a name="create-a-device-profile-containing-email-settings"></a>Criar um perfil de dispositivo que contém configurações de email

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
3. No painel de perfis, escolha **Criar perfil**.
4. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de email.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de email. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo de email:
    - **Android** (somente Samsung Android Knox Standard)
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Email**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android for Work e Samsung Knox Standard](email-settings-android.md)
    - [Configurações do iOS](email-settings-ios.md)
    - [Configurações do Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Configurações do Windows 10](email-settings-windows-10.md)
8. Quando terminar, volte para o painel **Criar perfil** e pressione **Criar**.

O perfil será criado e aparecerá no painel da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

## <a name="further-information"></a>Informações adicionais

### <a name="remove-an-email-profile"></a>Remover um perfil de email

Se você quiser remover um perfil de email de um dispositivo, edite a atribuição e remova todos os grupos dos quais o dispositivo é membro. Você não poderá remover um perfil de email dessa forma se este for o único perfil de email em um dispositivo.

### <a name="securing-email-access"></a>Proteger o acesso ao email

Você pode ajudar a proteger os perfis de email usando um destes dois métodos:

1. **Certificados** – Ao criar o perfil de email, escolha um perfil de certificado criado anteriormente no Intune. Ele é conhecido como certificado de identidade e é usado para autenticar em relação a um perfil de certificado confiável (ou um certificado raiz) para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é atribuído no computador que autentica a conexão de email, em geral, o servidor de email nativo.
Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Intune](certificates-configure.md).
2. **Nome de usuário e senha** – O usuário se autentica no servidor de email nativo fornecendo seu nome de usuário e senha.
A senha não está contida no perfil do email, portanto o usuário deve fornecê-la ao se conectar ao email.


### <a name="how-intune-handles-existing-email-accounts"></a>Como o Intune lida com contas de email existentes

Se o usuário já tiver configurado uma conta de email, o resultado da atribuição de perfil de email do Intune dependerá da plataforma do dispositivo:

- **iOS**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O perfil de email duplicado bloqueia a atribuição de um perfil do Intune. Nesse caso, o Portal da Empresa informa ao usuário que ele não está em conformidade e solicita que ele remova o perfil configurado manualmente. Para ajudar a evitar esse problema, instrua os usuários a se registrarem antes de instalar um perfil de email, permitindo que o Intune configure o perfil.
- **Windows**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O Intune substitui o perfil de email existente criado pelo usuário.
- **Android Samsung Knox Standard** Um perfil de email existente e duplicado é detectado com base no endereço de email e é substituído pelo perfil do Intune.
Como o Android não usa o nome do host para identificar o perfil, é recomendável que você não crie vários perfis de email para usar com o mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.
- **Android for Work** O Intune fornece dois perfis de email do Android for Work, um para o aplicativo Gmail e outro para o Nine Work. Esses aplicativos estão disponíveis na Google Play Store e são instalados no perfil de trabalho do dispositivo, portanto não podem resultar em perfis duplicados. Os dois aplicativos oferecem suporte a conexões com o Exchange. Para habilitar a conectividade de email, implante um desses aplicativos de email nos dispositivos dos usuários e crie e implante o perfil de email apropriado. Aplicativos de email, como o Nine Work podem não ser gratuitos. Examine os detalhes de licenciamento do aplicativo ou entre em contato com a empresa do aplicativo com quaisquer perguntas.

### <a name="update-an-email-profile"></a>Atualizar um perfil de email

Se você fizer alterações em um perfil de email atribuído anteriormente, os usuários finais poderão ver uma mensagem solicitando a aprovação da reconfiguração de suas configurações de email.
