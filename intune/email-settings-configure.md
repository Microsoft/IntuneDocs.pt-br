---
title: Definir as configurações de email no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie um perfil de email no Microsoft Intune e implante esse perfil para dispositivos Windows, iOS e Android Enterprise. Use um perfil de email para definir configurações de email comuns, incluindo um método de autenticação e um servidor de email para conexão ao email corporativo em dispositivos gerenciados.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e0c59ba8744272dd1038ede854ae49879c66f39
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513232"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Adicionar configurações de email a dispositivos usando o Intune

O Microsoft Intune inclui diferentes configurações de email que você pode implantar em dispositivos em sua organização. Um administrador de TI cria perfis de email com configurações específicas para se conectar a um servidor de email, como o Office 365 e o Gmail. Em seguida, os usuários finais se conectam, autenticam e sincronizam suas contas de email organizacional em seus dispositivos móveis. Ao criar e implantar um perfil de email, você pode confirmar se as configurações são padrão em vários dispositivos. E ajuda a reduzir as chamadas de suporte dos usuários finais que não conhecem as configurações de email corretas.

Você pode usar perfis de email para definir as configurações de email internas para os seguintes dispositivos:

- Android Samsung Knox Standard 4.0 e posterior
- Android Enterprise
- iOS 8.0 e posterior
- Windows Phone 8.1 e posterior
- Windows 10 (desktop) e Windows 10 Mobile

Este artigo mostra como criar um perfil de email no Microsoft Intune. Também inclui links para as diferentes plataformas para configurações mais específicas.

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição** para o perfil de email.
4. Escolha sua **Plataforma** na lista suspensa. Suas opções:

    - **Android** (somente Samsung Android Knox Standard)
    - **Android Enterprise**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 e posterior**

5. Na lista suspensa do tipo **Perfil**, escolha **Email**.
6. As configurações que você pode definir podem ser diferentes para cada plataforma. Para configurações específicas, escolha sua plataforma:

    - [Configurações do Android Samsung Knox Standard](email-settings-android.md)
    - [Configurações do Android Enterprise](email-settings-android-enterprise.md)
    - [Configurações do iOS](email-settings-ios.md)
    - [Configurações do Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Configurações do Windows 10](email-settings-windows-10.md)

Depois de você inserir suas configurações e criar o perfil, seu perfil será mostrado na lista de perfis. Em seguida, [atribua esse perfil a alguns grupos](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>Remover um perfil de email

Perfis de email são atribuídos a grupos de dispositivos, não a grupos de usuários. Há diferentes maneiras de remover um perfil de email de um dispositivo, mesmo quando há perfil de apenas um email no dispositivo:

- **Opção 1**: Abra o perfil de email (**Configuração do dispositivo** > **Perfis**) e escolha **Atribuições**. A guia **Incluir** mostra os grupos que recebem o perfil. Clique com o botão direito do mouse no grupo > **Remover**. Não se esqueça de **Salvar** suas alterações.

- **Opção 2**: [Apague ou desative o dispositivo](devices-wipe.md). Você pode usar essas ações para remover total ou seletivamente dados e configurações.

## <a name="secure-email-access"></a>Proteger o acesso de email

Você pode ajudar a proteger perfis de email usando as seguintes opções:

- **Certificados**: ao criar o perfil de email, escolha um perfil de certificado criado anteriormente no Intune. Esse certificado é conhecido como certificado de identidade. Ele é autenticado com relação a um perfil de certificado confiável ou um certificado raiz para confirmar se um dispositivo do usuário tem permissão para se conectar. O certificado confiável é atribuído ao computador que autentica a conexão de email. Normalmente, esse computador é o servidor de email nativo.

  Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Intune](certificates-configure.md).

- **Nome de usuário e senha**: o usuário se autentica no servidor de email nativo inserindo seu nome de usuário e senha. A senha não existe no perfil de email. Portanto, o usuário final insere a senha ao se conectar ao email.

## <a name="how-intune-handles-existing-email-accounts"></a>Como o Intune lida com contas de email existentes

Se o usuário já tiver configurado uma conta de email, o perfil de email será atribuído de maneira diferente, dependendo da plataforma.

- **iOS**: Um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O perfil de email duplicado bloqueia a atribuição de um perfil do Intune. Neste caso, o aplicativo Portal da Empresa notificará o usuário de que ele não está em conformidade e solicitará a remoção manual do perfil configurado. Para ajudar a evitar esse cenário, diga para os usuários finais se inscreverem *antes* da instalação de um perfil de email, permitindo que o Intune configure o perfil.

- **Windows:** Um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O Intune substitui o perfil de email existente criado pelo usuário final.

- **Android Samsung Knox Standard**: Um perfil de email existente e duplicado é detectado com base no endereço de email e é substituído pelo perfil do Intune. O Android não usa o nome do host para identificar o perfil. Não crie vários perfis de email usando o mesmo endereço de email em hosts diferentes. Os perfis substituem uns aos outros.

- **Perfis de trabalho do Android**: o Intune fornece dois perfis de email de trabalho do Android: um para o aplicativo Gmail e outro para o aplicativo Nine Work. Esses aplicativos estão disponíveis no Google Play Store e são instalados no perfil de trabalho do dispositivo. Esses aplicativos não criam perfis duplicados. Os dois aplicativos oferecem suporte a conexões com o Exchange. Para usar a conectividade de email, implante um desses aplicativos de email nos dispositivos dos usuários. Em seguida, crie e implante o perfil de email apropriado. Aplicativos de email, como o Nine Work podem não ser gratuitos. Examine os detalhes de licenciamento do aplicativo ou entre em contato com a empresa do aplicativo com quaisquer perguntas.

## <a name="changes-to-assigned-email-profiles"></a>Alterações aos perfis de email atribuído

Se você fizer alterações em um perfil de email atribuído anteriormente, os usuários finais poderão ver uma mensagem solicitando a aprovação da reconfiguração de suas configurações de email.

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele ainda não faz nada. Em seguida, [atribua o perfil a alguns dispositivos](device-profile-assign.md).
