---
title: Remover certificados SCEP ou PKCS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Os administradores podem usar a ação de apagar ou desativar para remover os certificados do Microsoft Intune. Existem alguns cenários em que os certificados são removidos automaticamente, como cancelar o registro de um dispositivo ou remover uma política de conformidade. Existem alguns cenários em que os certificados permanecem automaticamente no dispositivo, como quando a licença do Intune é perdida ou removida. Veja as diferentes maneiras para dispositivos Android, Android Enterprise, iOS, macOS e Windows.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 06b568ee7cc2dc55a8d44cf04b96078b47d8c4b3
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579159"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Remover certificados SCEP e PKCS no Microsoft Intune

No Microsoft Intune, você pode adicionar certificados SCEP e PKCS aos dispositivos. Esses certificados também poderão ser removidos quando você [apagar](devices-wipe.md#wipe) ou [desativar](devices-wipe.md#retire) o dispositivo. Há alguns outros cenários em que os certificados são removidos automaticamente e outros cenários em que os certificados permanecem no dispositivo.

Este artigo lista alguns cenários comuns e o impacto sobre os certificados PKCS e SCEP.

> [!NOTE]
> Para remover e revogar os certificados para um usuário que está sendo removido do AD (Active Directory) ou do Azure AD, siga as etapas na ordem:
>
>    1. Apagar ou desativar o dispositivo do usuário
>    2. Remova o usuário do AD ou do Azure AD

## <a name="windows-devices"></a>Dispositivos Windows

#### <a name="scep-certificates"></a>Certificados SCEP

- Um certificado SCEP é revogado *e* removido quando:

  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)
  - O dispositivo é removido do grupo do Azure AD (Active Directory)
  - O perfil de certificado é removido da atribuição de grupo

- Um certificado do SCEP é revogado quando:
  - O administrador atualiza ou altera o perfil SCEP

- O certificado raiz é removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Certificados SCEP **permanecem** no dispositivo (certificados não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD

#### <a name="pkcs-certificates"></a>Certificados PKCS

- Um certificado PKCS é revogado *e* removido quando:

  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- O certificado raiz é removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Os certificados PKCS **permanecem** no dispositivo (não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD
  - O administrador atualiza ou altera o perfil PKCS
  - O perfil de certificado é removido da atribuição de grupo


## <a name="ios-devices"></a>Dispositivos iOS

#### <a name="scep-certificates"></a>Certificados SCEP

- Um certificado SCEP é revogado *e* removido quando:

  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)
  - O dispositivo é removido do grupo do Azure AD (Active Directory)
  - O perfil de certificado é removido da atribuição de grupo

- Um certificado do SCEP é revogado quando:
  - O administrador atualiza ou altera o perfil SCEP

- O certificado raiz é removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Certificados SCEP **permanecem** no dispositivo (certificados não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD

#### <a name="pkcs-certificates"></a>Certificados PKCS

- Um certificado PKCS é revogado *e* removido quando:

  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Um certificado PKCS é removido quando:
  - O perfil de certificado é removido da atribuição de grupo
  
- O certificado raiz é removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Os certificados PKCS **permanecem** no dispositivo (não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD
  - O administrador atualiza ou altera o perfil PKCS

## <a name="android-knox-devices"></a>Dispositivos Android KNOX

#### <a name="scep-certificates"></a>Certificados SCEP

- Um certificado SCEP é revogado *e* removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)

- Um certificado do SCEP é revogado quando:
  - O administrador executa a ação [desativar](devices-wipe.md#retire)
  - O dispositivo é removido do grupo do Azure AD (Active Directory)
  - O perfil de certificado é removido da atribuição de grupo
  - O administrador remove o usuário ou o grupo do Azure AD (Active Directory)
  - O administrador atualiza ou altera o perfil SCEP

- O certificado raiz é removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Certificados SCEP **permanecem** no dispositivo (certificados não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD

#### <a name="pkcs-certificates"></a>Certificados PKCS

- Um certificado PKCS é revogado *e* removido quando:

  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- O certificado raiz é removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [apagar](devices-wipe.md#wipe)
  - O administrador executa a ação [desativar](devices-wipe.md#retire)

- Os certificados PKCS **permanecem** no dispositivo (não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD
  - O administrador atualiza ou altera o perfil PKCS
  - O perfil de certificado é removido da atribuição de grupo
  
  
> [!NOTE]
> Os dispositivos Android for Work não são validados para os cenários acima. Os dispositivos herdados Android (qualquer dispositivo de perfil que não seja de trabalho ou da Samsung) não estão habilitados para remoção do certificado. 

## <a name="macos-certificates"></a>Certificados do macOS

#### <a name="scep-certificates"></a>Certificados SCEP

- Um certificado SCEP é revogado *e* removido quando:
  - Um usuário final cancela o registro
  - O administrador executa a ação [desativar](devices-wipe.md#retire)
  - O dispositivo é removido do grupo do Azure AD (Active Directory)
  - O perfil de certificado é removido da atribuição de grupo

- Um certificado do SCEP é revogado quando:
  - O administrador atualiza ou altera o perfil SCEP

- Certificados SCEP **permanecem** no dispositivo (certificados não são revogados nem removidos) quando:
  - Um usuário final perde a licença do Intune
  - O administrador retira a licença do Intune
  - O administrador remove o usuário ou o grupo do Azure AD

> [!NOTE]
> Não há suporte para usar a ação de [apagar](devices-wipe.md#wipe) para uma redefinição de fábrica de dispositivos macOS.

#### <a name="pkcs-certificates"></a>Certificados PKCS

Não há suporte para certificados PKCS no macOS.

