---
title: "Como definir configurações de email do Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como configurar o Intune para criar conexões para email corporativo nos dispositivos gerenciados."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8e22d95dbaa51e8a799c771ec2cfe34f09e527d8
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Como definir configurações de email no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Os perfis de email podem ser usados para configurar dispositivos gerenciados com as configurações necessárias para se conectar e sincronizar o email da empresa. Isso pode ajudar a garantir que as configurações sejam padronizadas em todos os seus dispositivos, bem como ajudar a reduzir as chamadas de suporte dos usuários finais que não conhecem as configurações de email corretas.

Há suporte para o cliente de email interno na maioria das plataformas. Atualmente, não há suporte para a maioria dos aplicativos de email de terceiros.

Você pode usar perfis de email para configurar o cliente de email nativo nos seguintes tipos de dispositivo:

- Android Samsung KNOX Standard 4.0 e posterior
- Android for Work
- iOS 8.0 e posterior
- Windows Phone 8.1 e posterior
- Windows 10 (desktop) e Windows 10 Mobile

Use as informações neste tópico para aprender as noções básicas sobre a configuração de um perfil de email e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-email-settings"></a>Criar um perfil de dispositivo que contém configurações de email

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de email.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de email. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo de email:
    - **Android**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Email**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android](email-settings-android.md)
    - [Configurações do iOS](email-settings-ios.md)
    - [Configurações do Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Configurações do Windows 10](email-settings-windows-10.md)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

## <a name="further-information"></a>Informações adicionais

### <a name="remove-an-email-profile"></a>Remover um perfil de email

Se você quiser remover um perfil de email de um dispositivo, edite a atribuição e remova todos os grupos dos quais o dispositivo é membro. Observe que você não poderá remover um perfil de email dessa forma se este for o único perfil de email em um dispositivo.

### <a name="securing-email-access"></a>Proteger o acesso ao email

Você pode ajudar a proteger os perfis de email usando um destes dois métodos:

1. **Certificados** – Ao criar o perfil de email, escolha um perfil de certificado criado anteriormente no Intune. Ele é conhecido como certificado de identidade e é usado para autenticar em relação a um perfil de certificado confiável (ou um certificado raiz) para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é atribuído no computador que autentica a conexão de email, em geral, o servidor de email nativo.
Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Intune](certificates-configure.md).
2. **Nome de usuário e senha** – O usuário se autentica no servidor de email nativo fornecendo seu nome de usuário e senha.
A senha não está contida no perfil do email, portanto o usuário deve fornecê-la ao se conectar ao email.


### <a name="how-intune-handles-existing-email-accounts"></a>Como o Intune lida com contas de email existentes

Se o usuário já tiver configurado uma conta de email, o resultado da atribuição de perfil de email do Intune dependerá da plataforma do dispositivo:

- **iOS**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O perfil de email duplicado bloqueará a atribuição de um perfil do Intune. Nesse caso, o Portal da Empresa informa ao usuário que ele não está em conformidade e solicita que ele remova o perfil configurado manualmente. Para ajudar a evitar esse problema, instrua os usuários a se registrarem antes de instalar um perfil de email, permitindo que o Intune configure o perfil.
- **Windows**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O Intune substitui o perfil de email existente criado pelo usuário.
- **Android**: um perfil de email existente e duplicado é detectado com base no endereço de email e é substituído pelo perfil do Intune.
Como o Android não usa o nome do host para identificar o perfil, é recomendável que você não crie vários perfis de email para usar com o mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.

### <a name="update-an-email-profile"></a>Atualizar um perfil de email

Se você fizer alterações em um perfil de email atribuído anteriormente, os usuários finais poderão ver uma mensagem solicitando a aprovação da reconfiguração de suas configurações de email.

