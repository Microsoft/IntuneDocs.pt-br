---
title: Aplicativos Android com políticas de proteção do aplicativo
titlesuffix: Microsoft Intune
description: Saiba o que esperar de um aplicativo Android que tenha políticas de proteção.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6e38ac954f0b8c85b7127143c98f41bfe5497ef9
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179568"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Saiba o que esperar de aplicativos Android com políticas de proteção de aplicativo. As políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho. Por exemplo, quando você acessa um aplicativo com uma conta corporativa ou quando você acessa arquivos armazenados no OneDrive da sua empresa.
##  <a name="accessing-apps"></a>Acessando aplicativos

O aplicativo Portal da Empresa é necessário para todos os aplicativos em dispositivos Android que tenham políticas de proteção de aplicativo.

Instale o Portal da Empresa em todos os dispositivos que não estão registrados no Intune. Os usuários não precisam entrar no aplicativo Portal da Empresa para usar aplicativos que tenham políticas de proteção de aplicativo.
O aplicativo do Portal da Empresa permite compartilhar dados em um local seguro. Portanto, é um requisito até mesmo para dispositivos não registrados.


##  <a name="using-apps-with-multi-identity-support"></a>Usando aplicativos com suporte a várias identidades

As políticas de proteção de aplicativo somente entram em vigor quando um usuário tenta acessar dados relacionados ao trabalho.  Você verá comportamentos diferentes caso o usuário acesse o aplicativo para uso pessoal.

Alguns aplicativos são compatíveis com várias identidades. Nesse caso, o Intune só aplica as políticas de proteção de aplicativo quando um usuário acessa dados de trabalho.  Por exemplo, um usuário pode receber uma solicitação de PIN.  No **aplicativo Outlook**, a solicitação ocorre quando o usuário inicia o aplicativo. No **aplicativo OneDrive**, a solicitação ocorre quando o usuário insere a conta corporativa.  No Microsoft **Word**, **PowerPoint** e **Excel**, a solicitação ocorre quando um usuário acessa documentos no OneDrive da empresa.
##  <a name="managing-user-accounts-on-the-device"></a>Gerenciando contas de usuário no dispositivo

O Intune é compatível com políticas de proteção de aplicativo para uma conta de usuário por dispositivo.

* Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo. No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.

  * O **Microsoft Word**, **Excel** e **PowerPoint** não bloquearão o acesso a uma conta de usuário adicional. No entanto, a conta de usuário não será afetada pelas políticas de proteção de aplicativo.

  * Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.  A adição de várias contas corporativas é bloqueada nesses aplicativos.  No entanto, você pode remover um usuário de um dispositivo e, em seguida, adicionar um usuário diferente ao dispositivo.


* Antes da implantação da política de proteção de aplicativo, um dispositivo pode ter várias contas de usuário existentes. Nesse caso, a primeira conta na qual as políticas de proteção de aplicativo são implantadas será gerenciada por essas políticas de proteção de aplicativo do Intune.


Leia o cenário de exemplo a seguir para saber como o Intune lida com várias contas de usuário.

O usuário A trabalha para duas empresas: **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção de aplicativo, mas a conta associada à Empresa Y não. Para fazer com que a conta de usuário da Empresa Y seja gerenciada pelas políticas de proteção de aplicativo, o Usuário A deve remover a conta de usuário da Empresa X.
### <a name="adding-a-second-account"></a>Adicionando uma segunda conta
####  <a name="android"></a>Android
Você pode receber uma solicitação para remover a conta existente e adicionar uma nova conta.  Para remover a conta existente, acesse **Configurações &gt;Geral &gt; Gerenciador de Aplicativos &gt;Portal da Empresa. Em seguida, selecione "Limpar dados".**

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

|                                                                                 <strong>pfile</strong>                                                                                 |                                                                      <strong>text</strong>                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| O pfile é um formato genérico de "wrapper" para arquivos protegidos. Ele encapsula o conteúdo criptografado e as licenças da Proteção de Informações do Azure. Ele pode ser usado para proteger qualquer tipo de arquivo. | Arquivos de texto, inclusive XML, CSV etc. podem ser abertos para visualização no aplicativo, mesmo quando eles são protegidos. Tipos de arquivo: txt, ptxt, csv, pcsv, log, plog, xml, pxml. |

---------------
## <a name="next-steps"></a>Próximas etapas
[O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Consulte também
[Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)
