---
title: Gerenciar dispositivos de perfil de trabalho Android no Microsoft Intune
titlesuffix: ''
description: O Microsoft Intune gerencia os dispositivos de perfil de trabalho Android para fornecer privacidade e funcionalidades de gerenciamento adicionais quando as pessoas usam seus dispositivos Android para trabalhar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9c3184ff01252d2f53b5bfcce286df3424da23c2
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909160"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Gerenciar dispositivos de perfil de trabalho Android com o Intune

O Android Enterprise é um conjunto de recursos e serviços que separam os aplicativos e dados pessoais dos aplicativos e dados de trabalho. O Android Enterprise fornece funcionalidades de gerenciamento adicionais e privacidade quando as pessoas usam seus dispositivos Android para trabalhar. 

## <a name="supported-devices"></a>Dispositivos com suporte

As funcionalidades de gerenciamento do Android Enterprise dependem de recursos que fazem parte dos sistemas operacionais Android mais recente. Para dispositivos que não são compatíveis com o Android Enterprise, o gerenciamento convencional do Android permanece disponível. Para obter mais informações, confira [Requisitos do Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Integração

Antes de registrar dispositivos de perfil de trabalho Android, você precisa concluir algumas etapas de integração. Essas etapas estabelecem uma conexão entre o locatário do Intune e o serviço Google Play for Work. Para obter mais informações, confira [Habilitar o registro de dispositivos de perfil de trabalho Android](android-work-profile-enroll.md).

## <a name="work-profile-management"></a>Gerenciamento de perfil de trabalho

Ao gerenciar um dispositivo de perfil de trabalho Android com o Intune, você não gerencia todo o dispositivo. Os recursos de gerenciamento afetam apenas os perfis de trabalho criados no dispositivo durante o registro. Os aplicativos implantados no dispositivo com o Intune são instalados no perfil de trabalho. Os ícones de aplicativos no perfil de trabalho são diferenciados dos aplicativos pessoais no dispositivo. Todos os aplicativos e dados do Android que não estão na parte do Android Enterprise do dispositivo continuam sendo pessoais e controlados pelo usuário final. Os usuários podem instalar qualquer aplicativo que desejam na parte pessoal do dispositivo. Os administradores podem gerenciar e monitorar aplicativos e ações no escopo do perfil de trabalho.

O Intune fornece uma variedade de configurações gerais internas que você pode definir nos dispositivos de perfil de trabalho Android. Para obter mais informações, confira [Configurações de política de dispositivo de perfil de trabalho Android](compliance-policy-create-android-for-work.md).

## <a name="app-publishing-and-distribution"></a>Publicação e distribuição de aplicativos

O serviço Google Play for Work é parte integrante do gerenciamento e da distribuição de aplicativos do Android Enterprise. Todos os aplicativos implantados em dispositivos de perfil de trabalho Android no perfil de trabalho são provenientes do serviço Google Play gerenciado. Para gerenciar e implantar aplicativos na Play Store, entre no site do Google Play com as credenciais de administrador da empresa para o gerenciamento do Google. Você pode aprovar aplicativos para implantação do Android Enterprise para que eles apareçam nos perfis de trabalho dos dispositivos. Esses aplicativos são sincronizados com o console do Intune, em que posteriormente podem ser implantados e gerenciados usando o Intune. Os aplicativos de LOB (linha de negócios) desenvolvidos pela sua organização precisam ser publicados no Google Play gerenciado usando o console de publicação de aplicativos do Android do Google. Os aplicativos de linha de negócios devem ser configurados no console de publicação de aplicativos do Android para restringir o acesso à sua organização.

Os aplicativos podem ser instalados sem interação do usuário e sem exigir que ele permita a **Instalação de Fontes Desconhecidas**. Para procurar e instalar aplicativos opcionais ou disponíveis, o usuário pode procurar na loja Play for Work em seu dispositivo. Para obter mais informações, confira [Atribuir aplicativos a dispositivos de perfil de trabalho Android com o Intune](apps-add-android-for-work.md).

## <a name="app-configuration"></a>Configuração de aplicativo

O Android Enterprise fornece a infraestrutura para implantar valores de configuração de aplicativo em aplicativos com suporte para isso. Especificando valores de configuração para aplicativos de trabalho, você garante que eles sejam configurados corretamente quando os usuários iniciarem o aplicativo pela primeira vez. O suporte para configuração de aplicativo requer que os desenvolvedores de aplicativos criem seus aplicativos Android especificamente para dar suporte a valores de configuração gerenciados. Se eles derem suporte, você pode usar o Intune para especificar e aplicar essas configurações definidas. Para obter mais informações, confira [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](app-configuration-policies-use-android.md).

## <a name="email-configuration"></a>Configuração de email

O Android Enterprise não fornece um aplicativo de email padrão ou um objeto de perfil de email nativo como o que é fornecido pelo iOS. Em vez disso, as configurações de email podem ser definidas aplicando configurações de aplicativo aos aplicativos de email que dão suporte a elas. O Gmail e o Nine Work são dois aplicativos clientes do EAS (Exchange ActiveSync) na Play Store que dão suporte à configuração de aplicativos do Android Enterprise.

O Intune fornece modelos de configuração para aplicativos do Gmail e do Nine Work, quando gerenciados como aplicativos de trabalho. Outros aplicativos de email que dão suporte a perfis de configuração de aplicativo podem ser configurados com as políticas de configuração de aplicativo móvel.

Se você estiver usando o acesso condicional do Exchange ActiveSync para um dispositivo de perfil de trabalho Android, considere usar o aplicativo de email Gmail ou Nine Work. O aplicativo do Microsoft Outlook para Android ou qualquer outro aplicativo de email que usa autenticação moderna por meio da ADAL, também tem suporte. Para obter mais informações, confira [Como definir as configurações de email no Microsoft Intune](email-settings-configure.md).

## <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

As políticas de proteção do aplicativo aplicadas são totalmente compatíveis no perfil de trabalho e no perfil pessoal. É possível publicar aplicativos de linha de negócios no console de publicação de aplicativo do Android em https://play.google.com/apps/publish. Esse console inclui uma opção para tornar aplicativos particulares para sua organização. Para obter mais informações, confira [Adicionar uma política de conformidade do dispositivo para dispositivos de perfil de trabalho Android no Intune](compliance-policy-create-android-for-work.md). Para obter informações gerais sobre as políticas de proteção de aplicativo, confira [O que são políticas de proteção de aplicativo?](app-protection-policy.md)

## <a name="vpn-profiles"></a>Perfis de VPN

O suporte a VPN é semelhante aos perfis VPN do Android. Os mesmos provedores VPN e opções de configuração básicas estão disponíveis para o gerenciamento do Android Enterprise com duas diferenças:

-  **VPN com escopo de perfil de trabalho** – as conexões VPN são limitadas apenas aos aplicativos implantados no perfil de trabalho. Somente aplicativos gerenciados pelo Android Enterpise podem usar a conexão VPN. Aplicativos pessoais no dispositivo não podem usar uma conexão VPN gerenciada. Para obter mais informações, confira [Configurações de VPN do Android Enterprise](vpn-settings-android.md#android-work-profile-device-vpn-settings).

-  **VPN específica do aplicativo** – a VPN específica do aplicativo pode ser configurada no Intune quando o provedor VPN dá suporte para:
    - configuração para VPN específica do aplicativo
    - a funcionalidade de configurar a VPN por aplicativo por meio do perfil de configuração de aplicativo do Android Enterprise.
    Para obter mais informações, confira [Usar um perfil personalizado do Microsoft Intune para criar um perfil VPN por aplicativo para dispositivos Android](android-pulse-secure-per-app-vpn.md).

## <a name="certificate-profiles"></a>Perfis de certificado

As mesmas opções de configuração de perfil de certificado que estão disponíveis para o gerenciamento do Android também estão disponíveis para dispositivos de perfil de trabalho Android. O Android Enterprise fornece APIs de gerenciamento de certificados avançadas. O gerenciamento avançado de certificados fornece a seguinte funcionalidade:

-  garante que a implantação de certificados seja silenciosa e simples para o usuário.
-  garante que os certificados implantados sejam removidos quando um dispositivo for desativado do Intune e o perfil de trabalho for removido.
-  fornece mensagens aperfeiçoadas que informam os usuários que o certificado foi implantado e configurado pelo departamento de TI por meio do serviço de gerenciamento.

Para obter mais informações, confira [Configurar um perfil de certificado para seus dispositivos no Microsoft Intune](certificates-configure.md).

## <a name="wi-fi-profiles"></a>Perfis de Wi-Fi

Os perfis de Wi-Fi gerenciados pelo Android Enterprise serão removidos quando o dispositivo for desativado do Intune e o perfil de trabalho for excluído. Para obter mais informações, confira [Como definir as configurações de Wi-Fi no Microsoft Intune](wi-fi-settings-configure.md).

## <a name="next-steps"></a>Próximas etapas
- [Registrar dispositivos Android](android-enroll.md)
- [Atribuir aplicativos a dispositivos de perfil de trabalho Android com o Intune](apps-add-android-for-work.md)