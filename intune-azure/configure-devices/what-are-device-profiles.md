---
title: "O que são perfis de dispositivo no Microsoft Intune? | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba mais sobre perfis de dispositivo do Intune e como eles podem ajudar a gerenciar e proteger os dispositivos em sua empresa."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: b33d8ec48c057ce1e67487d5772ca203793d8a79
ms.contentlocale: pt-br
ms.lasthandoff: 05/10/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>O que são perfis de dispositivo do Microsoft Intune?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use o a carga de trabalho **Configuração de dispositivo** do Microsoft Intune para gerenciar as configurações e recursos em todos os dispositivos gerenciados. Na maioria das vezes, você usará essa carga de trabalho para criar perfis de dispositivo, que permitem gerenciar e controlar um intervalo inteiro de diferentes recursos e funcionalidades em dispositivos gerenciados.

Quando você abrir essa carga de trabalho, verá as seguintes opções:

- **Visão geral** – Essa página fornece status e relatórios que ajudarão a monitorar as configurações de dispositivo que você atribuiu a usuários e dispositivos.
- **Gerenciar Perfis** – Esta é a seção que você acessará para criar perfis de configuração de dispositivo. Veja abaixo uma lista de todos os tipos de perfil que você pode criar.
- **Configurar a autoridade de certificação** – Este fluxo de trabalho orienta você pelas as etapas necessárias para configurar certificados. Será necessário fazer isso se você quiser trabalhar com perfis de certificado do Intune.

## <a name="getting-started"></a>Introdução

O fluxo de trabalho para a criação de perfis de dispositivo é semelhante para todos os perfis. Leia [Como criar perfis de configuração de dispositivo do Microsoft Intune](how-to-create-device-profiles.md) para obter informações sobre como criar perfis. Depois, continue lendo para obter informações específicas sobre a criação de configurações para cada tipo de perfil.

É possível gerenciar os seguintes recursos em seus dispositivos:

## <a name="device-features"></a>Recursos de dispositivo

Os recursos de dispositivo permitem que você controle os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.
Para saber mais, veja [Como definir as configurações de recursos do dispositivo](how-to-configure-device-features.md) Oferece suporte a: iOS e macOS.

## <a name="device-restrictions"></a>Restrições de dispositivo
Restrições de dispositivo permitem controlar uma grande variedade de configurações em dispositivos que você gerencia em uma gama de categorias, incluindo configurações de segurança, navegador, hardware e compartilhamento de dados. Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.
Para obter mais informações, consulte [Como definir as configurações de restrição de dispositivo](how-to-configure-device-restrictions.md) Há suporte para: Android, iOS, macOS, Windows 10 e Windows 10 Team.

## <a name="email"></a>Email
Os perfis de email ajudam a criar, atribuir e monitorar configurações de email do Exchange ActiveSync nos dispositivos que você gerencia. Ao atribuir essas configurações, você garante a consistência, reduz chamadas de suporte e permite que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem qualquer configuração necessária da parte deles.
Para obter mais informações, consulte [Como definir as configurações de email](how-to-configure-email-settings.md) Há suporte para: Android, iOS, Windows Phone 8.1 e Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Use os perfis de Wi-Fi para atribuir configurações de rede sem fio para usuários e dispositivos em sua organização. Quando você atribuir um perfil de Wi-Fi, os usuários terão acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria.
Para obter mais informações, consulte [Como definir configurações de Wi-Fi](how-to-configure-wi-fi-settings.md) Há suporte para: Android, iOS, macOS e Windows 8.1 (somente importação).

## <a name="vpn"></a>VPN
Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Use os perfis de VPN para atribuir configurações de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura.
Para obter mais informações, consulte [Como definir as configurações de VPN](how-to-configure-vpn-settings.md).
Dá suporte a: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 e Windows 10.

## <a name="education"></a>Educação
Permite configurar opções o aplicativo Windows Take a Test. Quando você configura essas opções, nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.
Para saber mais, veja [Como definir as configurações de educação](how-to-configure-education-settings.md)

## <a name="certificates"></a>Certificados
Esse tipo de perfil permite que você configure certificados SCEP e PKCS confiáveis que podem ser atribuídos aos dispositivos e usados para autenticar o Wi-Fi, VPN e perfis de email.
Para obter mais informações, consulte [Como configurar certificados](how-to-configure-certificates.md) Há suporte para: Android, iOS, Windows Phone 8.1, Windows 8.1 e Windows 10.

## <a name="edition-upgrade"></a>Atualização de edição
Esse tipo de perfil permite atualizar automaticamente os dispositivos que executam algumas versões do Windows 10 para uma edição mais recente. Para obter mais informações, consulte [Como configurar atualizações de edição do Windows 10](how-to-configure-windows-10-edition-upgrade.md) Há suporte para: somente Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
A Proteção de Informações do Windows ajuda a proteger contra esses possíveis vazamentos de dados sem interferir na experiência do funcionário. Ele também ajuda a proteger dados e aplicativos corporativos e contra vazamentos de dados acidentais em dispositivos pessoais e de funcionários que os funcionários trazem para o trabalho sem a necessidade de alterações em seu ambiente ou outros aplicativos.
Para obter mais informações, consulte [Como configurar a Proteção de Informações do Windows](how-to-configure-windows-information-protection.md) Há suporte para: somente Windows 10.

## <a name="custom"></a>Personalizado
Configurações personalizadas permitem atribuir configurações de dispositivo que não são internos ao Intune. Por exemplo, em dispositivos Android, você pode especificar valores de OMA-URI que configuram o dispositivo. Para dispositivos iOS, você pode importar um arquivo de configuração criado com o Apple Configurator.
Para obter mais informações, consulte [Como definir configurações personalizadas](how-to-configure-custom-settings.md) Há suporte para: Android, iOS, macOS e Windows Phone 8.1.

