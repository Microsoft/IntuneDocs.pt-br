---
title: "Aplicativos Android com políticas de proteção do aplicativo"
description: "Este tópico descreve o que esperar quando seu aplicativo é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7e9dc17cda485be244e05409bca69672edb87969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Este tópico descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo. As políticas do aplicativo são aplicadas somente quando aplicativos são usados em um contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive de uma empresa.
##  <a name="access-apps"></a>Acessar aplicativos

O aplicativo Portal da Empresa é necessário para todos os aplicativos que estão associados a políticas de proteção de aplicativo em dispositivos Android.

É necessário instalar o aplicativo do Portal da Empresa em dispositivos não registrados no Intune. No entanto, o usuário não precisa iniciar ou entrar no aplicativo do Portal da Empresa antes de ter permissão para usar aplicativos gerenciados por políticas de proteção do aplicativo.

O aplicativo do Portal da Empresa é uma forma do Intune compartilhar dados em um local seguro. Portanto, o aplicativo do Portal da Empresa é um requisito para todos os aplicativos associados a políticas de proteção do aplicativo, mesmo se o dispositivo não estiver registrado no Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Usar aplicativos com suporte a várias identidades

As políticas de proteção do aplicativo são aplicadas apenas em contextos corporativos. Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.

Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho. No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo. No **aplicativo OneDrive**, o PIN será solicitado ao inserir a conta corporativa. No Microsoft **Word**, **PowerPoint** e **Excel**, o PIN será solicitado ao acessar os documentos armazenados no local do OneDrive for Business da empresa.

##  <a name="manage-user-accounts-on-the-device"></a>Gerenciar contas de usuário no dispositivo

O Intune só dá suporte à implantação de políticas de proteção do aplicativo a uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.

  * **Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.

  * Nos **aplicativos OneDrive** e **Outlook**, é possível usar somente uma conta corporativa.  Não é possível adicionar várias contas corporativas a esses aplicativos.  É possível remover um usuário e adicionar um usuário diferente ao dispositivo.


* Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.


Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo, mas não a conta associada à Empresa Y. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X.
### <a name="add-a-second-account"></a>Adicionar uma segunda conta
####  <a name="android"></a>Android
Se estiver usando um dispositivo Android, você poderá ver uma mensagem de bloqueio com instruções para remover a conta existente e adicionar uma nova.  Para remover a conta existente, vá para **Configurações &gt;Geral &gt; Gerenciador de Aplicativos &gt;Portal da Empresa**. Então, escolha **Limpar Dados**.

![Captura de tela da mensagem de erro e as instruções para remover a conta](./media/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Exibir arquivos de mídia com o aplicativo de Proteção de Informações do Azure
Para exibir os arquivos AV, PDF e de imagem da empresa em dispositivos Android, use o [aplicativo Proteção de Informações do Azure](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (conhecido anteriormente como aplicativo de compartilhamento do Rights Management).

Baixe esse aplicativo na loja do Google Play.  

Há suporte para os tipos de arquivo a seguir:

* **Áudio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ aprimorado), AAC ELD (AAC com pouco atraso aprimorado), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Vídeo:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Imagem:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg
* **Documentos:** PDF, PPDF


|**pfile**|**text**|
|----|----|
|Pfile é um formato genérico “wrapper” para arquivos protegidos que encapsula o conteúdo criptografado e as licenças da Proteção de Informações do Azure. Ele pode ser usado para proteger qualquer tipo de arquivo.|Arquivos de texto, inclusive XML, CSV etc. podem ser abertos para visualização no aplicativo, mesmo quando são protegidos. Tipos de arquivo: .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.|

## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](end-user-mam-apps-ios.md)
