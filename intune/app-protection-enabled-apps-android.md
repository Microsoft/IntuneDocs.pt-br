---
title: "Aplicativos Android com políticas de proteção do aplicativo"
titlesuffix: Azure portal
description: "Este tópico descreve o que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ee7977d8608327560b4df0c1bfbcc60ff150da9
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo. Políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho, como acessar aplicativos usando sua conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive na sua empresa.
##  <a name="accessing-apps"></a>Acessando aplicativos

O aplicativo Portal da Empresa é necessário para todos os aplicativos associados a políticas de proteção de aplicativo em dispositivos Android.

Para dispositivos não registrados no Intune, o aplicativo de Portal da Empresa deve ser instalado no dispositivo. No entanto, o usuário não precisa iniciar nem entrar no aplicativo de Portal da Empresa antes que possam usar aplicativos gerenciados por políticas de proteção de aplicativo.
O aplicativo de Portal da Empresa é uma forma do Intune compartilhar dados em um local seguro. Portanto, isto é um requisito mesmo que o dispositivo não esteja registrado no Intune.


##  <a name="using-apps-with-multi-identity-support"></a>Usando aplicativos com suporte a várias identidades

As políticas de proteção de aplicativo são aplicadas apenas no contexto de trabalho ao usar o aplicativo, de modo que você pode ver diferentes comportamentos de aplicativo dependendo do contexto: trabalho ou pessoal.

Para aplicativos que dão suporte a várias identidades, o Intune aplica as políticas de proteção de aplicativo somente quando o usuário final estiver usando o aplicativo no contexto de trabalho.  Por exemplo, o usuário final receberá um prompt para fornecer o PIN ao acessar dados de trabalho.  Para o **aplicativo Outlook**, o usuário final será solicitado a fornecer um PIN ao iniciar o aplicativo. Para o **aplicativo OneDrive**, isso acontece quando o usuário final insere a conta de trabalho.  Para o Microsoft **Word**, **PowerPoint* e **Excel**, isso acontece quando o usuário final acessa os documentos armazenados no local do OneDrive for Business da empresa.
##  <a name="managing-user-accounts-on-the-device"></a>Gerenciando contas de usuário no dispositivo

O Intune dá suporte somente a políticas de proteção de aplicativo para apenas uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.

  * **Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.

  * Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.  A adição de várias contas corporativas é bloqueada nesses aplicativos.  É possível remover um usuário e adicionar um usuário diferente ao dispositivo.


* Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.


Leia o cenário de exemplo abaixo para obter uma compreensão mais profunda de como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas - **empresa X**, e **empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção de aplicativo, mas a conta associada à Empresa Y não a obterá. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção de aplicativo, será necessário remover a conta de usuário associada à Empresa X.
### <a name="adding-a-second-account"></a>Adicionando uma segunda conta
####  <a name="android"></a>Android
Se estiver usando um dispositivo Android, você poderá ver uma mensagem de bloqueio com instruções para remover a conta existente e adicionar uma nova.  Para remover a conta existente, vá para **Configurações &gt;Geral &gt; Gerenciador de Aplicativos &gt;Portal da Empresa e selecione "Limpar Dados"**.

![Captura de tela da mensagem de erro e as instruções para remover a conta](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Exibindo arquivos de mídia com o aplicativo Proteção de Informações do Azure (anteriormente conhecido como aplicativo de compartilhamento Rights Management)
Para exibir os arquivos AV, PDF e de imagem em dispositivos Android, use o [aplicativo Proteção de Informações do Azure](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Baixe este aplicativo da Google Play Store.  

Os tipos de arquivo a seguir têm suporte:

* **Áudio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ aprimorado), AAC ELD (AAC com pouco atraso aprimorado), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Vídeo:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Imagem:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Documentos:** PDF, PPDF

------------
|**pfile**|**text**|
|----|----|
|Pfile é um formato genérico “wrapper” para arquivos protegidos que encapsula o conteúdo criptografado e as licenças da Proteção de Informações do Azure e podem ser usadas para proteger qualquer tipo de arquivo.|Arquivos de texto, inclusive XML, CSV etc. podem ser abertos para visualização no aplicativo, mesmo quando eles são protegidos. Tipos de arquivo: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Consulte também
[Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)
