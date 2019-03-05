---
title: Remover certificados SCEP ou PKCS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Os administradores podem usar a ação de apagar ou desativar para remover os certificados do Microsoft Intune. Existem alguns cenários em que os certificados são removidos automaticamente, como cancelar o registro de um dispositivo ou remover uma política de conformidade. Existem alguns cenários em que os certificados permanecem automaticamente no dispositivo, como quando a licença do Intune é perdida ou removida. Veja as diferentes maneiras para dispositivos Android, Android Enterprise, iOS, macOS e Windows.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 977e7006d39ae76516d5b06019e463d1018aaa79
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229251"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Remover certificados SCEP e PKCS no Microsoft Intune

No Microsoft Intune, você pode adicionar certificados do protocolo SCEP e PKCS (Public Key Cryptography Standards) aos dispositivos. Esses certificados também poderão ser removidos quando você [apagar](devices-wipe.md#wipe) ou [desativar](devices-wipe.md#retire) o dispositivo. 

Há alguns outros cenários em que os certificados são removidos automaticamente e outros cenários em que os certificados permanecem no dispositivo. Este artigo lista alguns cenários comuns e o impacto sobre os certificados PKCS e SCEP.

> [!NOTE]
> Para remover e revogar certificados de um usuário que está sendo removido do Active Directory local ou do Azure AD (Azure Active Directory), siga estas etapas na ordem:
>
> 1. Apague ou desative o dispositivo do usuário.
> 2. Remova o usuário do Active Directory local ou do Azure AD.

## <a name="windows-devices"></a>Dispositivos Windows

#### <a name="scep-certificates"></a>Certificados SCEP

Um certificado SCEP é revogado *e* removido quando:

- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).
- O dispositivo é removido de um grupo do Azure AD.
- Um perfil de certificado é removido da atribuição de grupo.

Um certificado do SCEP é revogado quando:
- Um administrador altera ou atualiza o perfil SCEP.

Um certificado raiz é removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Os certificados SCEP *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.

#### <a name="pkcs-certificates"></a>Certificados PKCS

Um certificado PKCS é revogado *e* removido quando:

- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Um certificado raiz é removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Os certificados PKCS *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.
- Um administrador altera ou atualiza o perfil PKCS.
- Um perfil de certificado é removido da atribuição de grupo.


## <a name="ios-devices"></a>Dispositivos iOS

#### <a name="scep-certificates"></a>Certificados SCEP

Um certificado SCEP é revogado *e* removido quando:

- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).
- O dispositivo é removido do grupo do Azure AD.
- Um perfil de certificado é removido da atribuição de grupo.

Um certificado do SCEP é revogado quando:
- Um administrador altera ou atualiza o perfil SCEP.

Um certificado raiz é removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Os certificados SCEP *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.

#### <a name="pkcs-certificates"></a>Certificados PKCS

Um certificado PKCS é revogado *e* removido quando:

- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Um certificado PKCS é removido quando:
- Um perfil de certificado é removido da atribuição de grupo.
  
Um certificado raiz é removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Os certificados PKCS *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.
- Um administrador altera ou atualiza o perfil PKCS.

## <a name="android-knox-devices"></a>Dispositivos Android KNOX

#### <a name="scep-certificates"></a>Certificados SCEP

Um certificado SCEP é revogado *e* removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).

Um certificado do SCEP é revogado quando:
- Um administrador executa a ação [desativar](devices-wipe.md#retire).
- O dispositivo é removido de um grupo do Azure AD.
- Um perfil de certificado é removido da atribuição de grupo.
- Um administrador remove o usuário ou o grupo do Azure AD.
- Um administrador altera ou atualiza o perfil SCEP.

Um certificado raiz é removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Os certificados SCEP *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.

#### <a name="pkcs-certificates"></a>Certificados PKCS

Um certificado PKCS é revogado *e* removido quando:

- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Um certificado raiz é removido quando:
- Um usuário cancela o registro.
- Um administrador executa a ação [apagar](devices-wipe.md#wipe).
- Um administrador executa a ação [desativar](devices-wipe.md#retire).

Os certificados PKCS *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.
- Um administrador altera ou atualiza o perfil PKCS.
- Um perfil de certificado é removido da atribuição de grupo.
  
  
> [!NOTE]
> Os dispositivos Android for Work não são validados para os cenários anteriores. Os dispositivos herdados Android (dispositivos de perfil que não sejam de trabalho ou da Samsung) não estão habilitados para remoção do certificado. 

## <a name="macos-certificates"></a>Certificados do macOS

#### <a name="scep-certificates"></a>Certificados SCEP

Um certificado SCEP é revogado *e* removido quando:
- Um usuário cancela o registro.
- Um administrador executa uma ação [desativar](devices-wipe.md#retire).
- O dispositivo é removido de um grupo do Azure AD.
- Um perfil de certificado é removido da atribuição de grupo.

Um certificado do SCEP é revogado quando:
- Um administrador altera ou atualiza o perfil SCEP.

Os certificados SCEP *permanecem* no dispositivo (não são revogados nem removidos) quando:
- Um usuário perde a licença do Intune.
- Um administrador retira a licença do Intune.
- Um administrador remove o usuário ou o grupo do Azure AD.

> [!NOTE]
> Não há suporte para usar a ação de [apagar](devices-wipe.md#wipe) para uma redefinição de fábrica de dispositivos macOS.

#### <a name="pkcs-certificates"></a>Certificados PKCS

Não há suporte para certificados PKCS no macOS.

