---
title: Aplicativos Android com políticas de proteção do aplicativo
description: Este tópico descreve o que esperar quando seu aplicativo é gerenciado por políticas de proteção de aplicativo.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 946ce31c613ddb3c7dd2bf4dfde7561dd56e4ca0
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414055"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo

Este artigo descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo. As políticas de proteção do aplicativo são aplicadas somente quando aplicativos são usados em um contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no local do OneDrive for Business.

## <a name="access-apps"></a>Acessar aplicativos

O aplicativo Portal da Empresa é necessário para todos os aplicativos que estão associados a políticas de proteção de aplicativo em dispositivos Android.

É necessário instalar o aplicativo do Portal da Empresa em dispositivos não registrados no Intune. No entanto, o usuário não precisa iniciar ou entrar no aplicativo do Portal da Empresa antes de ter permissão para usar aplicativos gerenciados por políticas de proteção do aplicativo.

O aplicativo do Portal da Empresa é uma forma do Intune compartilhar dados em um local seguro. Portanto, o aplicativo do Portal da Empresa é um requisito para todos os aplicativos associados a políticas de proteção do aplicativo, mesmo se o dispositivo não estiver registrado no Intune.

## <a name="use-apps-with-multi-identity-support"></a>Usar aplicativos com suporte a várias identidades

As políticas de proteção do aplicativo são aplicadas apenas em contextos corporativos. Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.

Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho. No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo. No **aplicativo OneDrive**, o PIN será solicitado ao inserir a conta corporativa. No Microsoft **Word**, **PowerPoint** e **Excel**, o PIN será solicitado ao acessar os documentos armazenados no local do OneDrive for Business da empresa.

## <a name="manage-user-accounts-on-the-device"></a>Gerenciar contas de usuário no dispositivo

Aplicativos de várias identidades permitem aos usuários adicionar várias contas.  O aplicativo do Intune permite apenas uma conta de gerenciamento.  Aplicativo do Intune não limita o número de contas não gerenciados.

Quando há uma conta gerenciada em um aplicativo:

* Se um usuário tenta adicionar uma segunda conta gerenciada, ele recebe uma solicitação para selecionar qual conta gerenciada usar.  A outra conta é removida.
* Se o administrador de TI adicionar uma política à segunda conta existente, o usuário receberá uma solicitação para selecionar qual conta gerenciada usar.  A outra conta é removida.

Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo, mas não a conta associada à Empresa Y. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X e adicionar a conta associada à Empresa X.

### <a name="add-a-second-account"></a>Adicionar uma segunda conta

#### <a name="android"></a>Android

Se estiver usando um dispositivo Android, você poderá ver uma mensagem de bloqueio com instruções para remover a conta existente e adicionar uma nova.  Para remover a conta existente, vá para **Configurações &gt;Geral &gt; Gerenciador de Aplicativos &gt;Portal da Empresa**. Então, escolha **Limpar Dados**.

![Captura de tela da mensagem de erro e as instruções para remover a conta](./media/end-user-mam-apps-android/Android_SwitchUser.png)

## <a name="view-media-files-with-the-azure-information-protection-app"></a>Exibir arquivos de mídia com o aplicativo de Proteção de Informações do Azure

Para exibir os arquivos AV, PDF e de imagem da empresa em dispositivos Android, use o [aplicativo Proteção de Informações do Azure](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (conhecido anteriormente como aplicativo de compartilhamento do Rights Management).

Baixe esse aplicativo na loja do Google Play.  

Há suporte para os tipos de arquivo a seguir:

* **Áudio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ aprimorado), AAC ELD (AAC com pouco atraso aprimorado), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Vídeo:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Imagem:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg
* **Documentos:** PDF, PPDF

|**pfile**|
|----|
|Pfile é um formato genérico “wrapper” para arquivos protegidos que encapsula o conteúdo criptografado e as licenças da Proteção de Informações do Azure. Ele pode ser usado para proteger qualquer tipo de arquivo.|

## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](end-user-mam-apps-ios.md)
