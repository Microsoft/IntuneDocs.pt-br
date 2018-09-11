---
title: Perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Visão geral dos diferentes perfis de dispositivo do Microsoft Intune, incluindo recursos, restrições, email, Wi-Fi, VPN, educação, certificados, Windows 10 de atualização, BitLocker e Windows Defender, Proteção de Informações do Windows e definições de configuração de dispositivo personalizadas no Portal do Azure. Use esses perfis para gerenciar e proteger dados e dispositivos em sua empresa.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da220e1f82c59f3181d64dc01d071867d62df397
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313965"
---
# <a name="what-are-microsoft-intune-device-profiles"></a>O que são perfis de dispositivo do Microsoft Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Microsoft Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos em sua organização. Essas configurações e recursos são gerenciados com o uso de perfis. Alguns exemplos de perfil incluem: 

- Um perfil de Wi-Fi, que concede a diferentes dispositivos o acesso ao seu WiFi corporativo
- Um perfil de VPN, que concede a diferentes dispositivos o acesso ao servidor de VPN na sua rede corporativa

Este artigo apresenta uma visão geral dos diferentes perfis que você pode criar para seus dispositivos. Use esses perfis para permitir e/ou impedir alguns recursos nos dispositivos.

## <a name="before-you-begin"></a>Antes de começar
Para ver os recursos disponíveis, abra o [Portal do Azure](https://portal.azure.com) e abra o recurso do Intune. 

A **Configuração do dispositivo** inclui as seguintes opções:

- **Visão geral**: lista o status dos perfis e fornece detalhes adicionais sobre os perfis que você atribuiu aos usuários e dispositivos
- **Gerenciar**: criar perfis de dispositivo e carregar [scripts do PowerShell](intune-management-extension.md) personalizados para serem executados no perfil
- **Monitorar**: verificar o status de um perfil quanto ao êxito ou falha, além de exibir logs sobre os perfis
- **Configurar**: adicionar uma autoridade de certificação (SCEP ou PFX) ou habilitar o Telecom Expense Management para o perfil

## <a name="create-the-profile"></a>Criar o perfil

[Criar perfis de dispositivo](device-profile-create.md) fornece diretrizes passo a passo para criar um perfil. 

## <a name="device-features---ios-and-macos"></a>Recursos do dispositivo – iOS e macOS

Os [recursos de dispositivo](device-features-configure.md) controlam os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.

Esse recurso é compatível com:
- iOS 
- macOS


## <a name="device-restrictions"></a>Restrições de dispositivo
As [restrições de dispositivo](device-restrictions-configure.md) controlam a segurança, o hardware, o compartilhamento de dados e outras configurações nos dispositivos. Por exemplo, crie um perfil de restrição de dispositivo que impeça que os usuários de dispositivos iOS usem a câmera do dispositivo. 

Esse recurso é compatível com:

- Android
- iOS
- macOS
- Windows 10
- Windows 10 Team

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

O perfil de [Configurações de quiosque](kiosk-settings.md) configura um dispositivo para executar um aplicativo ou executar vários aplicativos. Você também pode personalizar outros recursos em um quiosque, incluindo um menu de início e um navegador da Web.

Esse recurso é compatível com:
- Windows 10 e posterior

## <a name="email"></a>Email
O perfil [configurações de email](email-settings-configure.md) cria, atribui e monitora as configurações de email do Exchange ActiveSync nos dispositivos. Os perfis de email ajudam a garantir consistência, reduzem chamadas de suporte e permitem que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem que precisem fazer qualquer configuração. 

Esse recurso é compatível com: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="vpn"></a>VPN
As [configurações de VPN](vpn-settings-configure.md) atribuem perfis de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura. 

As VPNs (redes virtuais privadas) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o seu servidor VPN. 

Esse recurso é compatível com: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="wi-fi"></a>Wi-Fi
As [configurações de Wi-Fi](wi-fi-settings-configure.md) atribuem configurações de rede sem fio para usuários e dispositivos. Quando você atribui um perfil de Wi-Fi, os usuários obtém acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria. 

Esse recurso é compatível com: 

- Android
- iOS
- macOS
- Windows 8.1 (somente importação)

## <a name="esim-cellular---public-preview"></a>Celular eSIM – versão prévia pública

Os [perfis de celular eSIM](esim-device-configuration.md) fornecem a capacidade de configurar planos de dados da rede celular nos dispositivos gerenciados para acesso à Internet e a dados.  Depois de obter os códigos de ativação da operadora móvel, use o Intune para importar esses códigos de ativação e, em seguida, atribui-los aos dispositivos compatíveis com eSIM.

Esse recurso é compatível com:
- Windows 10 Fall Creators Update e posterior

## <a name="education"></a>Educação
As [Configurações de educação – Windows 10](education-settings-configure.md) definem as opções para o [aplicativo Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). Quando você configura essas opções, nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.

As [Configurações de educação – iOS](education-settings-configure-ios-shared.md) usam o aplicativo iOS Classroom para conduzir a aprendizagem e controlar os dispositivos dos alunos na sala de aula. Você pode configurar dispositivos iPad para vários alunos poderem compartilhar um único dispositivo.

## <a name="edition-upgrade"></a>Atualização de edição
As [atualizações de edição do Windows 10](edition-upgrade-configure-windows-10.md) atualizam automaticamente os dispositivos que executam algumas versões do Windows 10 para uma edição mais recente.

Esse recurso é compatível com: 
- Windows 10 e posterior

## <a name="update-policies"></a>Políticas de atualização
As [Políticas de atualização do iOS](software-updates-ios.md) mostram como criar e atribuir políticas do iOS para instalar atualizações de software em seus dispositivos iOS. Você também pode examinar o status da instalação.

Esse recurso é compatível com:
- iOS

## <a name="certificates"></a>Certificados
Os [Certificados](certificates-configure.md) configuram certificados SCEP e PKCS confiáveis que podem ser atribuídos aos dispositivos e usados para autenticar o Wi-Fi, VPN e perfis de email.

Esse recurso é compatível com: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="windows-information-protection-profile"></a>Perfil de Proteção de Informações do Windows
A [Proteção de Informações do Windows](windows-information-protection-configure.md) ajuda a proteger contra possíveis vazamentos de dados sem interferir na experiência do funcionário. Ela também ajuda a proteger dados e aplicativos corporativos contra vazamentos de dados acidentais em dispositivos corporativos e dispositivos pessoais que os funcionários usam no trabalho. Ela faz isso sem a necessidade de alterações em seu ambiente ou em outros aplicativos.

Esse recurso é compatível com:
- Windows 10 e posterior

## <a name="custom-profile"></a>Perfil personalizado
As [configurações personalizadas](custom-settings-configure.md) incluem a capacidade de atribuir configurações de dispositivo que não são internas do Intune. Por exemplo, em dispositivos Android, você pode inserir valores de OMA-URI. Para dispositivos iOS, você pode importar um arquivo de configuração criado com o Apple Configurator. 

Esse recurso é compatível com:

- Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Gerenciar e solucionar problemas

[Gerencie os perfis](device-profile-monitor.md) para verificar o status dos dispositivos e os perfis atribuídos. Também ajude a resolver conflitos verificando as configurações que causam os conflitos e os perfis que contêm essas configurações. [Problemas comuns e resoluções](device-profile-troubleshoot.md) fornece uma lista de P e R que ajuda a trabalhar com perfis, incluindo o que acontece quando um perfil é excluído, o que faz com que notificações sejam enviadas aos dispositivos e muito mais.