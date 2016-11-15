---
title: Sobre o Android for Work | Microsoft Intune
description: O Intune gerencia o Android for Work para fornecer privacidade e recursos de gerenciamento adicionais quando as pessoas usam seus dispositivos Android para trabalhar.
keywords: 
author: nathbarn
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 0238350139837a06a48d0bff7c53e4c39e07168c
ms.openlocfilehash: aafeb58e28144740540a765ac04de68b41ae5ce5


---

# <a name="manage-android-for-work-devices-with-intune"></a>Gerenciar dispositivos com Android for Work com o Intune

O Android for Work é um conjunto de serviços e recursos para dispositivos Android. Esses serviços e recursos fornecem privacidade e funcionalidades de gerenciamento adicionais quando as pessoas usam seus dispositivos Android para trabalhar. O Intune pode ajudar a implantar aplicativos e recursos da empresa em dispositivos com Android for Work para garantir que informações pessoais e de trabalho permaneçam separadas. Quando implantados com êxito, os aplicativos e os dados que eles acessam permanecem exclusivamente dentro do ambiente do Android for Work no dispositivo.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>Dispositivos com suporte

O Android for Work requer hardware Android mais recente porque muitas funcionalidades de gerenciamento contam com recursos que fazem parte do sistema operacional Android mais recente. Atualmente, o Android for Work tem suporte em dispositivos que executam o Android 5.0 Lollipop e posteriores e que têm suporte para perfil de trabalho. Para dispositivos que não têm suporte nativo para Android for Work, o gerenciamento convencional do Android permanece disponível. Saiba mais sobre os [Requisitos do Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Integração

Antes de registrar dispositivos com Android for Work, você precisa concluir algumas etapas de integração. Essas etapas estabelecem uma conexão entre seu locatário do Intune e o serviço Google Play for Work, que faz parte do processo de gerenciamento e distribuição do aplicativo Android for Work. Saiba mais sobre o tema em [Habilitando o registro do Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Gerenciamento de perfil de trabalho

Quando gerencia um dispositivo com Android for Work com o Intune, você não gerencia todo o dispositivo. Os recursos de gerenciamento afetam apenas os perfis de trabalho criados durante o registro. Todos os aplicativos implantados no dispositivo com o Intune fazem parte do perfil de trabalho. Os ícones dos aplicativos no perfil de trabalho exibem um porta-arquivos cor de laranja. Essa marcação diferencia aplicativos da empresa de aplicativos pessoais no dispositivo. Todos os dados e aplicativos Android fora da parte referente ao Android for Work no dispositivo continuam sendo pessoais e sob controle do usuário final. Os usuários podem instalar qualquer aplicativo que desejarem na parte pessoal do dispositivo, enquanto os administradores podem gerenciar e monitorar as ações no escopo do perfil de trabalho.

## <a name="app-publishing-and-distribution"></a>Publicação e distribuição de aplicativos

O serviço Google Play for Work faz parte do gerenciamento e da distribuição de aplicativos. Todos os aplicativos implantados em dispositivos com o Android for Work, no perfil de trabalho, são provenientes do Play for Work. Para gerenciar e implantar aplicativos na Play Store, faça logon como administrador do Intune no site do Play for Work e aprove aplicativos para seu locatário do Intune. Esses aplicativos são sincronizados com o console do Intune, em que posteriormente podem ser implantados e gerenciados usando o Intune. Aplicativos de LOB (linha de negócios) desenvolvidos pela sua organização devem ser publicados no Play for Work usando o console de publicação de aplicativos do Android do Google. Os aplicativos de linha de negócios devem ser configurados no console de publicação de aplicativos do Android para restringir o acesso à sua organização.

Os aplicativos são instalados sem interação do usuário e sem exigir que ele permita a **Instalação de Fontes Desconhecidas**. Para procurar e instalar aplicativos opcionais ou disponíveis, o usuário do aplicativo implanta o aplicativo da Play Store com selo de trabalho em seu dispositivo. Saiba mais em [Implantando aplicativos para Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Configuração de aplicativo

O Android for Work fornece infraestrutura para implantar valores de configuração de aplicativo em aplicativos que têm suporte para isso. Especificando valores de configuração para aplicativos de trabalho, você garante que eles sejam configurados corretamente quando os usuários iniciarem o aplicativo pela primeira vez. O suporte para configuração de aplicativo requer que os desenvolvedores de aplicativos criem seus aplicativos Android especificamente para dar suporte a valores de configuração gerenciados. Se eles derem suporte, você pode usar o Intune para especificar e aplicar essas configurações definidas. Saiba mais sobre as [Configurações de aplicativo no Android for Work](deploy-use/afw-app-configuration-policy.md).

## <a name="email-configuration"></a>Configuração de email

O Android for Work não fornece um aplicativo de email padrão ou objeto de perfil de email nativo como o que é fornecido pelo iOS. Em vez disso, as configurações de email podem ser definidas aplicando configurações de aplicativo aos aplicativos de email que dão suporte a elas. O Gmail e o Nine Work são dois aplicativos cliente do EAS (Exchange ActiveSync) na Play Store que dão suporte à configuração com o aplicativo do Android for Work.

O Intune fornece modelos de configuração para aplicativos do Gmail e do Nine Work. Outros aplicativos de email que dão suporte a perfis de configuração de aplicativo podem ser configurados com as políticas de configuração de aplicativo móvel.

Se estiver usando o acesso condicional do EAS para um dispositivo com Android for Work, você deve usar o aplicativo de email do Nine Work ou do Gmail. O aplicativo do Microsoft Outlook para Android ou qualquer outro aplicativo de email que usa autenticação moderna por meio da ADAL, também tem suporte. Saiba mais sobre os [Perfis de email para email da empresa](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="mobile-app-management-policies"></a>Políticas de gerenciamento de aplicativos móveis

As políticas de restrição aplicadas a aplicativos habilitados para MAM (gerenciamento de aplicativo móvel) têm suporte total no perfil de trabalho e no perfil pessoal. Você pode publicar aplicativos de linha de negócios no console de publicação de aplicativo do Android em https://play.google.com/apps/publish. Esse console inclui uma opção para tornar aplicativos particulares para sua organização. Saiba mais sobre as [Configurações de política de conformidade](afw-compliance-policy-settings-in-microsoft-intune.md). Para obter mais informações, consulte [Políticas de gerenciamento de aplicativo móvel](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>Perfis de VPN

O suporte a VPN é semelhante aos perfis VPN do Android. Os mesmos provedores de VPN e opções de configuração básicas estão disponíveis. Há duas diferenças principais:

1.  **VPN com escopo de perfil de trabalho** – as conexões VPN têm como escopo apenas os aplicativos implantados no perfil de trabalho. Somente aplicativos gerenciados pelo Android for Work podem usar a conexão VPN. Aplicativos pessoais no dispositivo não podem usar uma conexão VPN gerenciada.

2.  **VPN específica ao aplicativo** – se um provedor de VPN der suporte à configuração para VPN específica ao aplicativo e fornecer a capacidade de configurar a VPN por aplicativo por meio do perfil de configuração de aplicativo do Android for Work, a VPN específica ao aplicativo pode ser configurada no Intune. Verifique com o provedor de VPN se há suporte para essa capacidade. Saiba mais sobre os [Perfis de conexão VPN](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Perfis de certificado

As mesmas opções de configuração de perfil de certificado que estão disponíveis para o gerenciamento tradicional do Android também estão disponíveis para dispositivos com Android for Work. O Android for Work fornece APIs de gerenciamento avançado de certificados. O gerenciamento avançado de certificados fornece a seguinte funcionalidade:

1.  garante que a implantação de certificados seja silenciosa e simples para o usuário.

2.  garante que os certificados implantados sejam removidos completamente quando um dispositivo é retirado do Intune e o perfil de trabalho é removido.

3.  fornece mensagens aperfeiçoadas que informam os usuários que o certificado foi implantado e configurado pelo departamento de TI por meio do serviço de gerenciamento.

Saiba mais sobre os [Perfis de certificado](secure-resource-access-with-certificate-profiles.md).

## <a name="wifi-profiles"></a>Perfis de Wi-Fi

É garantido que os perfis de Wi-Fi gerenciados pelo Android for Work serão removidos quando o dispositivo for retirado do Intune e o perfil de trabalho for excluído. Saiba mais sobre [Perfis Wi-Fi](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Próximas etapas
[Habilitando o registro do Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Implantando aplicativos no Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO1-->


