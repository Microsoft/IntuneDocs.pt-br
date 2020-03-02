---
title: Assinar e criptografar emails usando o S/MIME – Microsoft Intune – Azure | Microsoft Docs
description: Saiba como usar certificados digitais de emails no Microsoft Intune para assinar e criptografar emails nos dispositivos. Esses certificados são chamados de S/MIME e são configurados usando perfis de configuração do dispositivo. Os certificados de assinatura e criptografia usam PKCS ou certificados privados e usam um conector para importar os certificados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/10/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15147a1d9ffd82e2f900d15c4a9d2b4d23ad23e3
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515145"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>Visão geral do S/MIME para assinar e criptografar emails no Intune

Certificados de email, também conhecidos como certificado S/MIME, fornecem segurança extra para as comunicações de email usando criptografia e descriptografia. O Microsoft Intune pode usar certificados S/MIME para assinar e criptografar emails em dispositivos móveis que executam as seguintes plataformas:

- Android
- iOS/iPadOS
- macOS
- Windows 10 e posterior
- Windows Phone

Em dispositivos iOS/iPadOS, você pode criar um perfil de email gerenciado pelo Intune que usa o S/MIME e certificados para autenticar e criptografar emails de entrada e de saída. Para outras plataformas, o S/MIME pode ou não ter suporte. Se ele tiver suporte, instale certificados que usam a assinatura e a criptografia S/MIME. Em seguida, um usuário final habilitará o S/MIME em seus aplicativos de email.

Para obter mais informações sobre a assinatura e a criptografia de email S/MIME, confira [S/MIME para assinatura e criptografia de mensagens](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

Este artigo fornece uma visão geral de como usar certificados S/MIME para assinar e criptografar emails nos dispositivos.

## <a name="signing-certificates"></a>Certificados de autenticação

Os certificados usados na autenticação permitem que o aplicativo cliente de email se comunique com segurança com o servidor de email.

Para usar certificados de autenticação, crie um modelo na AC (autoridade de certificação) voltado para a assinatura. Na Autoridade de Certificação do Microsoft Active Directory, [Configurar o modelo de certificado do servidor](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) lista as etapas usadas para criar modelos de certificado.

Os certificados de autenticação do Intune usam certificados PKCS. [Configurar e usar certificados PKCS](certficates-pfx-configure.md) descreve como implantar e usar o certificado PKCS no ambiente do Intune. Essas etapas incluem:

- Baixar e instalar o Microsoft Intune Certificate Connector para dar suporte a solicitações de certificado PKCS.
- Criar um perfil de certificado raiz confiável para os dispositivos. Essa etapa inclui o uso de certificados intermediários e raiz confiáveis para a autoridade de certificação e, em seguida, implantação do perfil em dispositivos.
- Crie um perfil de certificado PKCS usando o modelo de certificado criado. Esse perfil emite certificados de autenticação para dispositivos e implanta o perfil de certificado PKCS em dispositivos.

Você também pode importar um certificado de autenticação para um usuário específico. O certificado de autenticação é implantado em qualquer dispositivo registrado por um usuário. Para importar certificados para o Intune, use os [cmdlets do PowerShell no GitHub](https://github.com/Microsoft/Intune-Resource-Access). Para implantar um certificado PKCS importado no Intune para ser usado para autenticação de email, siga as etapas de [Configurar e usar certificados PKCS com o Intune](certficates-pfx-configure.md). Essas etapas incluem:

- Baixe e instale o PFX Certificate Connector do Microsoft Intune. Esse conector fornece certificados PKCS importados para dispositivos.
- Importe certificados de autenticação de email S/MIME para o Intune.
- Crie um perfil de certificado PKCS importado. Esse perfil fornece certificados PKCS importados para os dispositivos do usuário apropriado.

## <a name="encryption-certificates"></a>Certificados de criptografia

Os certificados usados para criptografia confirmam que um email criptografado só pode ser descriptografado pelo destinatário pretendido. A criptografia S/MIME é uma camada extra de segurança que pode ser usada na comunicação por email.

Ao enviar um email criptografado para outro usuário, a chave pública do certificado de criptografia desse usuário é obtida e criptografa o email enviado. O destinatário descriptografa o email usando a chave privada em seu dispositivo. Os usuários podem ter um histórico dos certificados usados para criptografar o email. Cada um desses certificados precisa ser implantado em todos os dispositivos de um usuário específico para que o email seja descriptografado com êxito.

É recomendável que os certificados de criptografia de email não sejam criados no Intune. Embora o Intune dê suporte ao emitir certificados PKCS que dão suporte à criptografia, o Intune cria um certificado exclusivo por dispositivo. Um certificado exclusivo por dispositivo não é ideal para um cenário de criptografia S/MIME, em que o certificado de criptografia deve ser compartilhado entre todos os dispositivos do usuário.

Para implantar certificados S/MIME usando o Intune, é necessário importar todos os certificados de criptografia de um usuário para o Intune. Em seguida, o Intune implanta todos esses certificados em cada dispositivo registrado por um usuário. Para importar certificados para o Intune, use os [cmdlets do PowerShell no GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Para implantar um certificado PKCS importado no Intune usado para criptografia de email, siga as etapas de [Configurar e usar certificados PKCS com o Intune](certficates-pfx-configure.md). Essas etapas incluem:

- Baixe e instale o PFX Certificate Connector do Microsoft Intune. Esse conector fornece certificados PKCS importados para dispositivos.
- Importe certificados de criptografia de email S/MIME para o Intune.
- Crie um perfil de certificado PKCS importado. Esse perfil fornece certificados PKCS importados para os dispositivos do usuário apropriado.

 > [!NOTE]
 > Os certificados de criptografia S/MIME importados são removidos pelo Intune quando os dados da empresa são removidos, ou quando os usuários têm seu registro cancelado do gerenciamento. No entanto, os certificados não são revogados na autoridade de certificação.

## <a name="smime-email-profiles"></a>Perfis de email do S/MIME

Depois de criar perfis de certificado de autenticação e criptografia S/MIME, você pode [habilitar o S/MIME para email nativo do iOS/iPadOS](../configuration/email-settings-ios.md).

## <a name="next-steps"></a>Próximas etapas

- [Usar o SCEP para certificados](certificates-scep-configure.md)
- [Usar certificados PKCS](certficates-pfx-configure.md)
- [Usar uma AC de parceiros](certificate-authority-add-scep-overview.md)
- [Emitir certificados PKCS em um serviço Web do Symantec PKI Manager](certificates-digicert-configure.md)
