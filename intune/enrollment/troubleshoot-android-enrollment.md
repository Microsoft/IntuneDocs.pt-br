---
title: Solucionar problemas de dispositivos Android Enterprise no Microsoft Intune
description: Sugestões para solucionar alguns dos problemas mais comuns ao registrar dispositivos Android no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/25/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04c726c1dc6af7e92b75335d105de605ef00e712
ms.sourcegitcommit: 8b716db3c0fdbb7dff62497ec283902a5069a343
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2020
ms.locfileid: "77652361"
---
# <a name="troubleshoot-android-enterprise-device-problems-in-microsoft-intune"></a>Solucionar problemas de dispositivo Android Enterprise no Microsoft Intune

Este artigo ajuda os Administradores do Intune a entender e solucionar problemas ao registrar dispositivos Android Enterprise no Intune.

## <a name="apps-on-android-enterprise-devices"></a>Aplicativos em dispositivos Android Enterprise

### <a name="managed-google-play-apps-that-arent-deployed-through-intune-are-displayed-in-the-work-profile"></a>Os aplicativos gerenciados Google Play que não são implantados por meio do Intune são exibidos no perfil de trabalho
Os aplicativos do sistema podem ser habilitados no perfil de trabalho pelo OEM do dispositivo no momento em que o perfil de trabalho é criado. Isso não é controlado pelo provedor de MDM.

Para solucionar problemas, siga estas etapas:

  1. Colete logs do Portal da Empresa.
  2. Observe os aplicativos que aparecem no perfil de trabalho inesperadamente.
  3. Cancele o registro do dispositivo do Intune e desinstale o Portal da Empresa.
  4. Instale o aplicativo [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc), que permite a criação de um perfil de trabalho sem um EMM para teste.
  5. Siga as instruções em [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc) para criar um perfil de trabalho no dispositivo.
  6. Examine os aplicativos que aparecem no perfil de trabalho. 
  7. Se aparecem os mesmos aplicativos no aplicativo Test DPC, os aplicativos são esperados pelo OEM para esse dispositivo.

### <a name="unapproved-managed-google-play-for-work-store-apps-arent-being-removed-from-the-client-apps-page-in-intune"></a>Os aplicativos gerenciados não aprovados do Google Play for Work Store não estão sendo removidos da página de aplicativos cliente no Intune
Esse comportamento é esperado.

### <a name="managed-google-play-apps-arent-being-reported-under-the-discovered-apps-blade-in-the-intune-portal"></a>Os aplicativos gerenciados Google Play não estão sendo relatados na folha Aplicativos Descobertos no portal do Intune
Esse comportamento é esperado. Somente os aplicativos do sistema instalados no Perfil de Trabalho são inventariados na folha Aplicativos Descobertos. Para ver os aplicativos Gerenciados do Google Play instalados, use a folha **Aplicativos Gerenciados**.

### <a name="are-web-applications-supported-for-work-profile-enrolled-devices"></a>Os aplicativos Web são compatíveis com dispositivos registrados no perfil de trabalho?
Sim. Para obter mais informações, confira [Links da Web do Google Play Web gerenciados](../apps/apps-add-android-for-work.md#managed-google-play-web-links)

## <a name="device-management"></a>Gerenciamento de dispositivo

### <a name="file-path-internal-storageandroiddatacommicrosoftwindowsintunecompanyportalfiles-missing-on-work-profile-enrolled-devices"></a>Caminho do arquivo Armazenamento interno/Android/Data.com.microsoft.windowsintune.companyportal/arquivos ausentes em dispositivos registrados do perfil de trabalho

  **Resposta**: Esse comportamento é esperado. Esse caminho só é criado para o cenário de administrador do dispositivo (Registro Android Herdado).

  Para coletar logs do Portal da Empresa, siga estas etapas:

  1. No aplicativo Portal da Empresa com a notificação, toque em **Menu** > **Ajuda** > **Suporte a Email** e, em seguida, toque em **Enviar Email e Carregar Logs**. 
  2. Quando for solicitado a **Enviar solicitação de ajuda com**, selecione um dos aplicativos de email.
  3. Um email é gerado para seu administrador de TI com uma ID de incidente que pode ser fornecida para o suporte ao produto da Microsoft.

### <a name="managed-google-play-last-sync-time--hasnt-been-updated-in-days"></a>A hora da última sincronização do Google Play gerenciado não é atualizada há dias
Esse comportamento é esperado. A sincronização é disparada somente quando você faz isso manualmente.

### <a name="encryption-is-required-when-a-device-is-enrolled-can-it-be-turned-off"></a>A criptografia é necessária quando um dispositivo é registrado. Isso pode ser desativado?
Não, o Google exige que o dispositivo seja criptografado para criar um perfil de trabalho. 

### <a name="samsung-devices-are-blocking-the-use-of-third-party-keyboards-like-swiftkey"></a>Os dispositivos Samsung estão bloqueando o uso de teclados de terceiros, como SwiftKey
A Samsung começou a impor essa restrição em dispositivos Android 8.0+. A Microsoft está trabalhando atualmente com a Samsung nesse problema e publicará novas informações quando elas estiverem disponíveis.

## <a name="remote-actions"></a>Ações remotas

### <a name="wipe-factory-reset-option-isnt-available-for-work-profile-enrolled-device"></a>A opção Apagar (Redefinição de Fábrica) não está disponível para o dispositivo de perfil de trabalho registrado
Esse comportamento é esperado. No cenário de perfil de trabalho, o provedor de MDM não tem controle total sobre o dispositivo. A única opção disponível é Desativar (Remover Dados da Empresa), o que remove todo o perfil de trabalho e todo o seu conteúdo.

### <a name="is-device-passcode-reset-supported"></a>Há suporte para redefinição de senha do dispositivo?
Para dispositivos registrados de perfil de trabalho, você só pode redefinir a senha do perfil de trabalho em dispositivos Android 8.0 ou posteriores quando:
- a senha do perfil de trabalho é gerenciada
- o usuário final permitiu que você a redefinisse.

Para dispositivos Dedicados (COSU) e Totalmente Gerenciados, há suporte para a redefinição de senha do dispositivo.


## <a name="next-steps"></a>Próximas etapas

- [Solucionar problemas de registro de dispositivo no Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Faça uma pergunta no fórum do Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Confira o blog da equipe de suporte do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Confira o blog de segurança e mobilidade corporativa da Microsoft](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)