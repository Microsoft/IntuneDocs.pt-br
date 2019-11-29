---
title: Recursos e configurações de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Visão geral dos diferentes perfis de dispositivo do Microsoft Intune. Obtenha informações sobre recursos, restrições, email, Wi-Fi, VPN, educação, certificados, atualização do Windows 10, BitLocker e Microsoft Defender, Proteção de Informações do Windows, modelos administrativos e definições personalizadas de configurações de dispositivo no portal do Azure. Use esses perfis para gerenciar e proteger dados e dispositivos em sua empresa.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0dd9eddd986e6717e6bf706b02a7b06f712a032
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059891"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Aplicar recursos e configurações aos seus dispositivos usando perfis de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Microsoft Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos em sua organização. Essas configurações e recursos são adicionados a "perfis de configuração". Você pode criar perfis para diferentes dispositivos e plataformas, incluindo iOS, Android e Windows. Em seguida, use o Intune para aplicar ou "atribuir" o perfil aos dispositivos.

Como parte da sua solução MDM (gerenciamento de dispositivo móvel), use esses perfis de configuração para concluir tarefas diferentes. Alguns exemplos de perfil incluem:

- Em dispositivos Windows 10, use um modelo de perfil que bloqueie controles ActiveX no Internet Explorer.
- Em dispositivos iOS e macOS, permita que os usuários usem impressoras AirPrint em sua organização.
- Permita ou impeça o acesso ao Bluetooth no dispositivo.
- Crie um perfil de WiFi ou VPN que permita a diferentes dispositivos o acesso à sua rede corporativa.
- Gerencie as atualizações de software, incluindo a hora em que são instaladas.
- Execute um dispositivo Android como um dispositivo de quiosque dedicado que pode executar um ou muitos aplicativos.

Este artigo apresenta uma visão geral dos diferentes tipos de perfil que você pode criar. Use esses perfis para permitir ou impedir alguns recursos nos dispositivos.

## <a name="administrative-templates"></a>Modelos administrativos

Os [modelos administrativos](administrative-templates-windows.md) incluem centenas de configurações que podem ser definidas para o Internet Explorer, o OneDrive, a área de trabalho remota, o Word, o Excel e outros programas do Office.

Esses modelos oferecem aos administradores uma exibição simplificada das configurações semelhante à política de grupo, mas 100% baseada em nuvem.

Esse recurso é compatível com:

- Windows 10 a partir da versão 1809 em firmware com suporte.

## <a name="certificates"></a>Certificados

[Certificados](../protect/certificates-configure.md) configuram certificados confiáveis, SCEP e PKCS atribuídos aos dispositivos. Esses certificados autenticam o WiFi, o VPN e as perfis de email.

Esse recurso é compatível com: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 e posterior

## <a name="custom-profile"></a>Perfil personalizado

As [Configurações personalizadas](custom-settings-configure.md) permitem que os administradores atribuam configurações de dispositivo que não são nativas do Intune. Em dispositivos Android, você pode inserir valores de OMA-URI. Para dispositivos iOS, você pode importar um arquivo de configuração criado com o Apple Configurator.

Esse recurso é compatível com:

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1

## <a name="delivery-optimization"></a>Otimização de entrega

[Otimização de entrega](delivery-optimization-windows.md) melhora a experiência de entrega de atualizações de software. Essas configurações estão substituindo as configurações **Atualizações de Software** > **Anel de Atualização do Windows 10**.

Use essas configurações para controlar como as atualizações de software são baixadas nos dispositivos em sua organização. Por exemplo, é possível deixar os usuários obterem suas próprias atualizações, ou obterem as atualizações usando os serviços de nuvem de otimização de entrega em um perfil de dispositivo.

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="device-features"></a>Recursos de dispositivo

Os [recursos de dispositivo](device-features-configure.md) controlam recursos em dispositivos iOS e macOS, como o AirPrint, notificações e mensagens da tela de bloqueio.

Esse recurso é compatível com:

- iOS/iPadOS
- macOS

## <a name="device-firmware-configuration-interface"></a>Interface de configuração do firmware do dispositivo

[A DFCI (Interface de configuração do firmware do dispositivo)](device-firmware-configuration-interface-windows.md) permite que os administradores habilitem ou desabilitem as configurações da UEFI (BIOS) usando o Intune. Use essas configurações para aprimorar a segurança no nível do firmware, que normalmente é mais resiliente a ataques mal-intencionados.

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="device-restrictions"></a>Restrições de dispositivo

As [restrições de dispositivo](device-restrictions-configure.md) controlam a segurança, o hardware, o compartilhamento de dados e outras configurações nos dispositivos. Por exemplo, crie um perfil de restrição de dispositivo que impeça que os usuários de dispositivos iOS usem a câmera do dispositivo. 

Esse recurso é compatível com:

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 10 e posterior
- Windows 10 Team

## <a name="edition-upgrade"></a>Atualização de edição

As [atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md) atualizam automaticamente os dispositivos que executam algumas versões do Windows 10 para uma edição mais recente.

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="education"></a>Educação

As [Configurações de educação – Windows 10](education-settings-configure.md) definem as opções para o [aplicativo Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). Quando você configura essas opções, nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.

As [Configurações de educação – iOS](../fundamentals/education-settings-configure-ios-shared.md) usam o aplicativo iOS Classroom para conduzir a aprendizagem e controlar os dispositivos dos alunos na sala de aula. É possível configurar iPads de modo que vários alunos possam compartilhar um único dispositivo.

## <a name="email"></a>Email

O perfil [Configurações de email](email-settings-configure.md) cria, atribui e monitora as configurações de email do Exchange ActiveSync nos dispositivos. Os perfis de email ajudam com a consistência, reduzem chamadas de suporte e possibilitam que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem que precisem fazer qualquer configuração. 

Esse recurso é compatível com: 

- Android
- Android Enterprise
- iOS/iPadOS
- Windows Phone 8.1
- Windows 10 e posterior

## <a name="endpoint-protection"></a>Endpoint Protection

As [configurações de proteção de ponto de extremidade do Windows 10](../protect/endpoint-protection-windows-10.md) definem as configurações do BitLocker e do Microsoft Defender para dispositivos Windows 10.

Para integrar a Proteção Avançada contra Ameaças do Microsoft Defender (WDATP) ao Microsoft Intune, confira [Configurar pontos de extremidade usando ferramentas de MDM (Gerenciamento de Dispositivo Móvel)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-mdm).

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="esim-cellular---public-preview"></a>Celular eSIM – versão prévia pública

Os [Perfis de celular eSIM](esim-device-configuration.md) possibilitam que os administradores configurem planos de dados de celular em seus dispositivos gerenciados para acesso à Internet e a dados. Depois de obter os códigos de ativação da operadora móvel, use o Intune para importar esses códigos de ativação e, em seguida, atribui-los aos dispositivos compatíveis com eSIM.

Esse recurso é compatível com:

- Windows 10 Fall Creators Update e posterior

## <a name="extensions"></a>Extensões do

[Extensões de kernel](kernel-extensions-overview-macos.md) possibilitam que os administradores adicionem recursos ou programas no nível de kernel em dispositivos macOS. Defina essas configurações para confiar em todas as extensões de um desenvolvedor ou parceiro específico ou permitir extensões de kernel específicas.

Esse recurso é compatível com:

- macOS

## <a name="identity-protection"></a>Proteção de identidade

A [Proteção de identidade](../protect/identity-protection-configure.md) controla a experiência do Windows Hello para Empresas em dispositivos Windows 10 e Windows 10 Mobile. Defina essas configurações para disponibilizar o Windows Hello para Empresas a usuários e dispositivos e para especificar os requisitos de PINs e gestos do dispositivo.  

Esse recurso é compatível com:  

- Windows 10 e posterior
- Windows Holographic for Business  

## <a name="kiosk"></a>Quiosque

O perfil [Configurações de quiosque](kiosk-settings.md) configura um dispositivo para executar um aplicativo, ou vários aplicativos. Você também pode personalizar outros recursos em um quiosque, incluindo um menu de início e um navegador da Web.

Esse recurso é compatível com:

- Windows 10 e posterior

Configurações de quiosque também estão disponíveis como restrições de dispositivos para [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) e [iOS](device-restrictions-ios.md#kiosk).

## <a name="oemconfig"></a>OEMConfig

[OEMConfig](android-oem-configuration-overview.md) é um padrão que permite que os OEMs (fabricantes originais do equipamento) e EMMs (Enterprise Mobility Management) criem e ofereçam suporte a recursos específicos de OEM de uma maneira padronizada em dispositivos Android Enterprise. Com o OEMConfig, um OEM cria um esquema que define recursos de gerenciamento específicos de OEM e os insere em um aplicativo carregado no Google Play. O Intune lê o esquema no aplicativo e permite que os administradores do Intune definam as configurações no esquema.

Esse recurso é compatível com:

- Android Enterprise (OEMConfig)

## <a name="powershell-scripts"></a>Scripts do PowerShell

Os [scripts do PowerShell em dispositivos Windows 10](../apps/intune-management-extension.md) usam a Extensão de Gerenciamento do Intune para carregar seus scripts do PowerShell no Intune e, em seguida, executar esses scripts em seus dispositivos. Veja também o que é necessário para usar a extensão, como adicioná-la ao Intune e outras informações importantes.


Esse recurso é compatível com:

- Windows 10 e posterior
- Windows Holographic for Business

## <a name="shared-multi-user-device"></a>Dispositivos multiusuário compartilhados

O [Windows 10](shared-user-device-settings-windows.md) e o [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) inclui configurações para gerenciar dispositivos com vários usuários, também conhecidos como dispositivos compartilhados ou computadores compartilhados. Quando um usuário entra no dispositivo, você escolhe se ele pode alterar as opções de suspensão ou salvar arquivos no dispositivo. Em outro exemplo, para economizar espaço, você pode criar um perfil que exclui credenciais inativas de dispositivos Windows HoloLens.

Essas configurações de dispositivo multiusuário compartilhado permitem que um administrador controle alguns dos recursos do dispositivo e gerencie esses dispositivos compartilhados usando o Intune.

Esse recurso é compatível com:

- Windows 10 e posterior
- Windows Holographic for Business

## <a name="update-policies"></a>Políticas de atualização

As [Políticas de atualização do iOS](../protect/software-updates-ios.md) mostram como criar e atribuir políticas do iOS para instalar atualizações de software em seus dispositivos iOS. Você também pode examinar o status da instalação.

Para ver as políticas de atualização em dispositivos Windows, confira [Otimização de Entrega](delivery-optimization-windows.md). 

Esse recurso é compatível com:

- iOS/iPadOS

## <a name="vpn"></a>VPN

As [configurações de VPN](vpn-settings-configure.md) atribuem perfis de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura. 

As VPNs (redes virtuais privadas) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o seu servidor VPN. 

Esse recurso é compatível com: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 e posterior

## <a name="wi-fi"></a>Wi-Fi

As [configurações de Wi-Fi](wi-fi-settings-configure.md) atribuem configurações de rede sem fio para usuários e dispositivos. Quando você atribui um perfil de Wi-Fi, os usuários obtém acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria. 

Esse recurso é compatível com: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 (somente importação)
- Windows 10 e posterior

## <a name="windows-information-protection-profile"></a>Perfil de Proteção de Informações do Windows

A [Proteção de Informações do Windows](../protect/windows-information-protection-configure.md) ajuda a proteger contra possíveis vazamentos de dados sem interferir na experiência do funcionário. Também ajuda a proteger dados e aplicativos corporativos contra vazamentos de dados acidentais em dispositivos corporativos e dispositivos pessoais que os funcionários usam no trabalho. O uso da Proteção de Informações do Windows não exige alterações no ambiente ou em outros aplicativos.

Esse recurso é compatível com:

- Windows 10 e posterior

## <a name="zebra-mobility-extensions-mx"></a>Zebra Mobility Extensions (MX)

[Zebra Mobility Extensions (MX)](android-zebra-mx-overview.md) permitem que os administradores usem e gerenciem dispositivos Zebra no Intune. Você cria perfis de StageNow com suas configurações e, em seguida, usa o Intune para atribuir e implantar esses perfis em seus dispositivos Zebra. [Logs e problemas comuns do StageNow](android-zebra-mx-logs-troubleshoot.md) é um excelente recurso para solucionar problemas de perfis e ver alguns possíveis problemas ao usar o StageNow.

Esse recurso é compatível com:

- Android (Extensões de Mobilidade)

## <a name="manage-and-troubleshoot"></a>Gerenciar e solucionar problemas

[Gerencie os perfis](device-profile-monitor.md) para verificar o status dos dispositivos e os perfis atribuídos. Também ajude a resolver conflitos verificando as configurações que causam os conflitos e os perfis que incluem essas configurações. [Problemas comuns e resoluções](device-profile-troubleshoot.md) ajuda os administradores a trabalhar com perfis. Ele descreve o que acontece ao excluir um perfil, o que causa o envio das notificações para dispositivos e muito mais.

## <a name="next-steps"></a>Próximas etapas

Escolha sua plataforma e comece a trabalhar.
