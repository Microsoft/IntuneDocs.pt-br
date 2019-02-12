---
title: Recursos e configurações de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Visão geral dos diferentes perfis de dispositivo do Microsoft Intune, incluindo recursos, restrições, email, Wi-Fi, VPN, educação, certificados, atualização do Windows 10, BitLocker e Windows Defender, Proteção de Informações do Windows, modelos administrativos e definições personalizadas de configurações de dispositivo no portal do Azure. Use esses perfis para gerenciar e proteger dados e dispositivos em sua empresa.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b9bd8aaca9aaf6e39c7a120518eeca1cef31511
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845084"
---
# <a name="apply-features-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Aplicar configurações de recursos aos seus dispositivos usando perfis de dispositivo no Microsoft Intune

O Microsoft Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos em sua organização. Essas configurações e recursos são adicionados a "perfis de configuração". Você pode criar perfis para diferentes dispositivos, diferentes plataformas, incluindo iOS, Android e Windows e, em seguida, usar o Intune para aplicar o perfil aos dispositivos em sua organização.

Alguns exemplos de perfil incluem:

- Em dispositivos Windows 10, use um modelo de perfil que bloqueie controles ActiveX no Internet Explorer.
- Em dispositivos iOS e macOS, permita que os usuários usem impressoras AirPrint em sua organização.
- Permita ou impeça o acesso ao Bluetooth no dispositivo.
- Crie um perfil de WiFi ou VPN que permita a diferentes dispositivos o acesso à sua rede corporativa.
- Gerencie as atualizações de software, incluindo a hora em que são instaladas.
- Execute um dispositivo Android em um dispositivo de quiosque dedicado que pode executar um ou muitos aplicativos.

Este artigo lista as etapas usadas para criar um perfil e fornece uma visão geral dos diferentes tipos de perfis que você pode criar. Use esses perfis para permitir ou impedir alguns recursos nos dispositivos.

## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.

2. Selecione **Configuração do dispositivo**. Você tem as seguintes opções:

    - **Visão geral**: Lista o status dos perfis e fornece detalhes adicionais sobre os perfis que você atribuiu a usuários e dispositivos.
    - **Gerenciar**: Crie perfis de dispositivo, carregue [scripts personalizados do PowerShell](intune-management-extension.md) a serem executados no perfil e adicione planos de dados a dispositivos usando o [eSIM](esim-device-configuration.md).
    - **Monitorar**: Verifique o status de um perfil quanto ao êxito ou falha, além de exibir logs sobre os perfis.
    - **Configuração**: Adicione uma autoridade de certificação SCEP ou PFX ou habilite o [Telecom Expense Management](telecom-expenses-monitor.md) no perfil.

3. Selecione **Perfis** > **Criar Perfil**. Insira as seguintes propriedades:

   - **Nome**: Insira um nome descritivo para o perfil.
   - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 e posterior**
       - **Windows 10 e posterior**

   - **Tipo de perfil**: Selecione o tipo de configurações que deseja criar. A lista dependerá da **plataforma** escolhida:

       - [Modelos Administrativos](administrative-templates-windows.md)
       - [Personalizado](custom-settings-configure.md)
       - [Otimização de Entrega](delivery-optimization-windows.md)
       - [Recursos de dispositivo](device-features-configure.md)
       - [Restrições de dispositivo](device-restrictions-configure.md)
       - [Atualização de edição e opção de modo](edition-upgrade-configure-windows-10.md)
       - [Educação](education-settings-configure.md)
       - [Email](email-settings-configure.md)
       - [Endpoint protection](endpoint-protection-configure.md)
       - [Proteção de identidade](identity-protection-configure.md)  
       - [Quiosque](kiosk-settings.md)
       - [Certificado PKCS](certficates-pfx-configure.md)
       - [Certificado SCEP](certificates-scep-configure.md)
       - [Certificado confiável](certificates-configure.md)
       - [Políticas de atualização](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Proteção de Informações do Windows](windows-information-protection-configure.md)

     Por exemplo, se você selecionar **iOS** para a plataforma, as opções de tipo de perfil serão semelhantes às seguintes:

     ![Criar perfil do iOS no Intune](./media/create-device-profile.png)

4. Selecione **Configurações**. As configurações são organizadas por categoria. Selecione uma categoria para ver uma lista de todas as configurações que podem ser definidas.

5. Quando terminar, selecione **OK** > **Criar** para salvar as alterações.

Para saber mais sobre os diferentes tipos de perfil, leia na íntegra as próximas seções deste artigo.

## <a name="administrative-templates-preview"></a>Modelos Administrativos (Versão Prévia)

Os [modelos administrativos](administrative-templates-windows.md) incluem centenas de configurações que podem ser definidas para o Internet Explorer, o OneDrive, a área de trabalho remota, o Word, o Excel e outros programas do Office, entre outros.

Esses modelos oferecem aos administradores uma exibição fácil e simplificada das configurações semelhante à Política de Grupo, mas são 100% baseados em nuvem. 

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="device-features"></a>Recursos de dispositivo

Os [recursos de dispositivo](device-features-configure.md) controlam recursos em dispositivos iOS e macOS, como o AirPrint, notificações e mensagens da tela de bloqueio.

Esse recurso é compatível com:

- iOS 
- macOS

## <a name="device-restrictions"></a>Restrições de dispositivo

As [restrições de dispositivo](device-restrictions-configure.md) controlam a segurança, o hardware, o compartilhamento de dados e outras configurações nos dispositivos. Por exemplo, crie um perfil de restrição de dispositivo que impeça que os usuários de dispositivos iOS usem a câmera do dispositivo. 

Esse recurso é compatível com:

- Android
- Android Enterprise
- iOS
- macOS
- Windows 10 e posterior
- Windows 10 Team

## <a name="delivery-optimization"></a>Otimização de entrega

[Otimização de entrega](delivery-optimization-windows.md) melhora a experiência de entrega de atualizações de software. Essas configurações estão substituindo as configurações **Atualizações de Software** > **Anel de Atualização do Windows 10**.

Use essas configurações para controlar como as atualizações de software são baixadas nos dispositivos em sua organização. Por exemplo, é possível deixar os usuários obterem suas próprias atualizações, ou obterem as atualizações usando os serviços de nuvem de otimização de entrega em um perfil de dispositivo.

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="endpoint-protection"></a>Endpoint Protection

As [configurações de proteção de ponto de extremidade do Windows 10](endpoint-protection-windows-10.md) definem as configurações do BitLocker e do Windows Defender para dispositivos Windows 10.

Para integrar a WDATP (Proteção Avançada contra Ameaças do Windows Defender) ao Microsoft Intune, consulte [Configure endpoints using Mobile Device Management (MDM) tools](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection) (Configurar pontos de extremidade usando ferramentas de MDM (Gerenciamento de dispositivo móvel)).

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="identity-protection"></a>Proteção de identidade

A [Proteção de identidade](identity-protection-configure.md) controla a experiência do Windows Hello para Empresas em dispositivos Windows 10 e Windows 10 Mobile. Defina essas configurações para disponibilizar o Windows Hello para Empresas a usuários e dispositivos e para especificar os requisitos de PINs e gestos do dispositivo.  

Esse recurso é compatível com:  

- Windows 10 e posterior
- Windows Holographic for Business  

## <a name="kiosk"></a>Quiosque

O perfil [Configurações de quiosque](kiosk-settings.md) configura um dispositivo para executar um aplicativo, ou vários aplicativos. Você também pode personalizar outros recursos em um quiosque, incluindo um menu de início e um navegador da Web.

Esse recurso é compatível com:

- Windows 10 e posterior

Configurações de quiosque também estão disponíveis como restrições de dispositivos para [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) e [iOS](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>Email

O perfil [Configurações de email](email-settings-configure.md) cria, atribui e monitora as configurações de email do Exchange ActiveSync nos dispositivos. Os perfis de email ajudam com a consistência, reduzem chamadas de suporte e possibilitam que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem que precisem fazer qualquer configuração. 

Esse recurso é compatível com: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10 e posterior

## <a name="vpn"></a>VPN

As [configurações de VPN](vpn-settings-configure.md) atribuem perfis de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura. 

As VPNs (redes virtuais privadas) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o seu servidor VPN. 

Esse recurso é compatível com: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 e posterior

## <a name="wi-fi"></a>Wi-Fi

As [configurações de Wi-Fi](wi-fi-settings-configure.md) atribuem configurações de rede sem fio para usuários e dispositivos. Quando você atribui um perfil de Wi-Fi, os usuários obtém acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria. 

Esse recurso é compatível com: 

- Android
- iOS
- macOS
- Windows 8.1 (somente importação)
- Windows 10 e posterior

## <a name="esim-cellular---public-preview"></a>Celular eSIM – versão prévia pública

Os [Perfis de celular eSIM](esim-device-configuration.md) possibilitam que os administradores configurem planos de dados de celular em seus dispositivos gerenciados para acesso à Internet e a dados. Depois de obter os códigos de ativação da operadora móvel, use o Intune para importar esses códigos de ativação e, em seguida, atribui-los aos dispositivos compatíveis com eSIM.

Esse recurso é compatível com:
- Windows 10 Fall Creators Update e posterior

## <a name="education"></a>Educação

As [Configurações de educação – Windows 10](education-settings-configure.md) definem as opções para o [aplicativo Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). Quando você configura essas opções, nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.

As [Configurações de educação – iOS](education-settings-configure-ios-shared.md) usam o aplicativo iOS Classroom para conduzir a aprendizagem e controlar os dispositivos dos alunos na sala de aula. É possível configurar iPads de modo que vários alunos possam compartilhar um único dispositivo.

## <a name="edition-upgrade"></a>Atualização de edição

As [atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md) atualizam automaticamente os dispositivos que executam algumas versões do Windows 10 para uma edição mais recente.

Esse recurso é compatível com: 
- Windows 10 e posterior

## <a name="update-policies"></a>Políticas de atualização

As [Políticas de atualização do iOS](software-updates-ios.md) mostram como criar e atribuir políticas do iOS para instalar atualizações de software em seus dispositivos iOS. Você também pode examinar o status da instalação.

Para ver as políticas de atualização em dispositivos Windows, confira [Otimização de Entrega](delivery-optimization-windows.md). 

Esse recurso é compatível com:
- iOS

## <a name="certificates"></a>Certificados

Os [Certificados](certificates-configure.md) configuram certificados confiáveis, SCEP e PKCS que são atribuídos aos dispositivos e usados para autenticar Wi-Fi, VPN e perfis de email.

Esse recurso é compatível com: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 e posterior

## <a name="windows-information-protection-profile"></a>Perfil de Proteção de Informações do Windows

A [Proteção de Informações do Windows](windows-information-protection-configure.md) ajuda a proteger contra possíveis vazamentos de dados sem interferir na experiência do funcionário. Também ajuda a proteger dados e aplicativos corporativos contra vazamentos de dados acidentais em dispositivos corporativos e dispositivos pessoais que os funcionários usam no trabalho. O uso da Proteção de Informações do Windows não exige alterações no ambiente ou em outros aplicativos.

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="shared-multi-user-device"></a>Dispositivos multiusuário compartilhados

O [Windows 10](shared-user-device-settings-windows.md) e o [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) inclui configurações para gerenciar dispositivos com vários usuários, também conhecidos como dispositivos compartilhados ou computadores compartilhados. Quando um usuário entra no dispositivo, você escolhe se ele pode alterar as opções de suspensão ou salvar arquivos no dispositivo. Em outro exemplo, você pode criar uma política que exclua credenciais inativas de dispositivos Windows HoloLens para economizar espaço.

Essas configurações de dispositivo multiusuário compartilhado permitem que um administrador controle alguns dos recursos do dispositivo e gerencie esses dispositivos compartilhados usando o Intune.

Esse recurso é compatível com:

- Windows 10 e posterior
- Windows Holographic for Business

## <a name="custom-profile"></a>Perfil personalizado

As [Configurações personalizadas](custom-settings-configure.md) possibilitam que os administradores atribuam configurações de dispositivo que não são nativas do Intune. Por exemplo, em dispositivos Android, você pode inserir valores de OMA-URI. Para dispositivos iOS, você pode importar um arquivo de configuração criado com o Apple Configurator. 

Esse recurso é compatível com:

- Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Gerenciar e solucionar problemas

[Gerencie os perfis](device-profile-monitor.md) para verificar o status dos dispositivos e os perfis atribuídos. Também ajude a resolver conflitos verificando as configurações que causam os conflitos e os perfis que contêm essas configurações. [Problemas comuns e resoluções](device-profile-troubleshoot.md) fornece uma perguntas e respostas que ajudam a trabalhar com perfis, incluindo o que acontece quando um perfil é excluído, o que faz com que notificações sejam enviadas aos dispositivos e muito mais.

## <a name="next-steps"></a>Próximas etapas
Escolha sua plataforma e comece a trabalhar:

