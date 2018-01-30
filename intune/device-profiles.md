---
title: "O que são perfis de dispositivo no Microsoft Intune?"
titlesuffix: Azure portal
description: Saiba mais sobre os perfis de dispositivo do Intune e como eles podem ajudar a gerenciar e proteger os dispositivos em sua empresa.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c745f9f745802e0de7a58e3dd7570c0e363ab5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>O que são perfis de dispositivo do Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use o a carga de trabalho **Configuração de dispositivo** do Microsoft Intune para gerenciar as configurações e recursos em todos os dispositivos gerenciados. Na maioria das vezes, você usará essa carga de trabalho para criar perfis de dispositivo, que permitem gerenciar e controlar um intervalo inteiro de diferentes recursos e funcionalidades nos dispositivos.

Quando você abrir essa carga de trabalho, verá as seguintes opções:

- **Visão geral** – Essa página fornece status e relatórios que ajudarão a monitorar as configurações de dispositivo que você atribuiu a usuários e dispositivos.
- **Gerenciar Perfis** – Esta é a seção que você acessará para criar perfis de configuração de dispositivo. você pode encontrar uma lista de todos os tipos de perfil que você pode criar posteriormente neste tópico.
- **Configurar a autoridade de certificação** – Este fluxo de trabalho guia você pelas as etapas necessárias para configurar perfis de certificados do Intune.

## <a name="getting-started"></a>Introdução

O fluxo de trabalho para a criação de perfis de dispositivo é semelhante para todos os perfis. Leia [Como criar perfis de configuração de dispositivo do Microsoft Intune](device-profile-create.md) para obter informações. Depois, continue lendo para obter informações específicas sobre a criação de configurações para cada tipo de perfil.

É possível gerenciar os seguintes recursos em seus dispositivos:

## <a name="device-features"></a>Recursos de dispositivo

Os recursos de dispositivo permitem que você controle os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.
Para saber mais, veja [Como definir as configurações de recursos do dispositivo](device-features-configure.md) Oferece suporte a: iOS e macOS.

## <a name="device-restrictions"></a>Restrições de dispositivo
Restrições de dispositivo permitem controlar muitas configurações em dispositivos gerenciados, incluindo configurações de segurança, hardware e compartilhamento de dados. Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.
Para obter mais informações, consulte [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md) Há suporte para: Android, iOS, macOS, Windows 10 e Windows 10 Team.

## <a name="email"></a>Email
Os perfis de email ajudam a criar, atribuir e monitorar configurações de email do Exchange ActiveSync nos dispositivos que você gerencia. Os perfis de email ajudam a garante a consistência, reduzem chamadas de suporte e permitem que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem qualquer configuração necessária da parte deles.
Para obter mais informações, consulte [Como definir as configurações de email](email-settings-configure.md) Há suporte para: Android, iOS, Windows Phone 8.1 e Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Use os perfis de Wi-Fi para atribuir configurações de rede sem fio para usuários e dispositivos em sua organização. Quando você atribuir um perfil de Wi-Fi, os usuários terão acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria.
Para obter mais informações, consulte [Como definir configurações de Wi-Fi](wi-fi-settings-configure.md) Há suporte para: Android, iOS, macOS e Windows 8.1 (somente importação).

## <a name="vpn"></a>VPN
Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Atribua perfis VPN aos usuários e dispositivos na sua organização para que eles possam se conectar à rede de forma fácil e segura.
Para obter mais informações, consulte [Como definir as configurações de VPN](vpn-settings-configure.md).
Há suporte para: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 e Windows 10.

## <a name="education"></a>Educação
Permite configurar opções o aplicativo Windows Take a Test. Quando você configura essas opções, nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.
Para saber mais, veja [Como definir as configurações de educação](education-settings-configure.md)

## <a name="certificates"></a>Certificados
Esse tipo de perfil permite que você configure certificados SCEP e PKCS confiáveis que podem ser atribuídos aos dispositivos e usados para autenticar o Wi-Fi, VPN e perfis de email.
Para obter mais informações, consulte [Como configurar certificados](certificates-configure.md) Há suporte para: Android, iOS, Windows Phone 8.1, Windows 8.1 e Windows 10.

## <a name="edition-upgrade"></a>Atualização de edição
Este tipo de perfil permite atualizar automaticamente dos dispositivos que executam algumas versões do Windows 10 para uma edição mais recente.
Para obter mais informações, consulte [Como configurar upgrades da edição do Windows 10](edition-upgrade-configure-windows-10.md) Há suporte para: somente Windows 10.

## <a name="endpoint-protection"></a>Endpoint Protection
Este tipo de perfil permite definir as configurações do BitLocker e do Windows Defender para dispositivos Windows 10.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10](endpoint-protection-windows-10.md) Há suporte para: somente Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
A Proteção de Informações do Windows ajuda a proteger contra esses possíveis vazamentos de dados sem interferir na experiência do funcionário. Ele também ajuda a proteger dados e aplicativos corporativos e contra vazamentos de dados acidentais em dispositivos pessoais e de funcionários que os funcionários trazem para o trabalho sem a necessidade de alterações em seu ambiente ou outros aplicativos.
Para obter mais informações, consulte [Como configurar a Proteção de Informações do Windows](windows-information-protection-configure.md) Há suporte para: somente Windows 10.

## <a name="custom"></a>Personalizado
Configurações personalizadas permitem atribuir configurações de dispositivo que não são internos ao Intune. Por exemplo, em dispositivos Android, você pode especificar valores de OMA-URI que configuram o dispositivo. Para dispositivos iOS, você pode importar um arquivo de configuração criado com o Apple Configurator.
Para obter mais informações, consulte [Como definir configurações personalizadas](custom-settings-configure.md) Há suporte para: Android, iOS, macOS e Windows Phone 8.1.

## <a name="next-steps"></a>Próximas etapas
Escolha um dos tipos de perfil na lista para começar a configurar os dispositivos.
