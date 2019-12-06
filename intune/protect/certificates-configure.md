---
title: Criar perfil de certificados no Microsoft Intune – Azure | Microsoft Docs
description: Saiba mais sobre o uso dos certificados de protocolo SCEP (Simple Certificate Enrollment Protocol) e PKCS (Public Key Cryptography Standards) e de perfis de certificado com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5092fa37f0bf6bd1320fa06fa58ac5e36f55aa3c
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410196"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Usar certificados para autenticação no Microsoft Intune

Use certificados com o Intune para autenticar os usuários em aplicativos e recursos corporativos por meio de perfis de VPN, Wi-Fi ou email. Quando você usa certificados para autenticar essas conexões, os usuários finais não precisam inserir nomes de usuário e senhas, o que pode tornar seu acesso contínuo. Os certificados também são usados para assinatura e criptografia de email usando S/MIME.

## <a name="intune-supported-certificates-and-usage"></a>Certificados e uso compatíveis com o Intune

| Tipo              | Autenticação | Autenticação S/MIME | Criptografia S/MIME  |
|--|--|--|--|
| Certificado PKCS (Public Key Cryptography Standards) importado |  | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png)|
| PKCS#12 (ou PFX)    | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) |  |
| Protocolo SCEP  | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | |

Para implantar esses certificados, você criará e atribuirá perfis de certificado a dispositivos.

Cada perfil de certificado individual criado dá suporte a uma única plataforma. Por exemplo, se você usar certificados PKCS, criará o perfil de certificado PKCS para o Android e um perfil de certificado PKCS separado para o iOS. Se você também usar certificados SCEP para essas duas plataformas, criará um perfil de Certificado SCEP para o Android e outro para o iOS.

### <a name="general-considerations-when-you-use-a-microsoft-certification-authority"></a>Considerações gerais ao usar uma Autoridade de Certificação Microsoft

Quando usar uma Autoridade de Certificação da Microsoft (CA):

- Para usar perfis de certificado SCEP, é preciso [configurar um servidor NDES (Serviço de Registro de Dispositivo de Rede)](certificates-scep-configure.md#set-up-ndes) para uso com o Intune.
- Para usar os seguintes tipos de perfil de certificado, é necessário [instalar o Microsoft Intune Certificate Connector](certificates-scep-configure.md#install-the-intune-certificate-connector):
  - Perfil de certificação do protocolo SCEP
  - Perfil de Certificado PKCS

- Para usar certificados PKCS importados:
  - [Instale o conector do certificado PFX para Microsoft Intune](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
  - Exporte certificados da autoridade de certificação e importe-os para o Microsoft Intune. Confira [o projeto PFXImport do PowerShell](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

- Implante certificados, usando os seguintes mecanismos:
  - [Perfis de certificado confiáveis](certificates-configure.md#create-trusted-certificate-profiles) para implantar o certificado de AC de raiz confiável por meio de sua AC raiz ou intermediária (emissora) nos dispositivos
  - Perfis de certificado SCEP
  - Perfis de certificado PKCS
  - Perfis de certificado PKCS importados

### <a name="general-considerations-when-you-use-a-third-party-certification-authority"></a>Considerações gerais sobre o uso de uma Autoridade de Certificação de terceiros

Quando usar uma autoridade de certificação (CA) de terceiros (não Microsoft):

- Para usar perfis de certificado SCEP:
  - Configure a integração com uma autoridade de certificação de terceiros de [um de nossos parceiros com suporte](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners). Para realizar a configuração, siga as instruções da autoridade de certificação de terceiros para concluir a integração da autoridade de certificação com o Intune.
  - [Crie um aplicativo no Azure Active Directory](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration) que delegue direitos ao Intune para validar desafios de certificados SCEP.

- Os certificados PKCS importados exigem que você [instale o PFX Certificate Connector for Microsoft Intune](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).

- Implante certificados, usando os seguintes mecanismos:
  - [Perfis de certificado confiáveis](certificates-configure.md#create-trusted-certificate-profiles) para implantar o certificado de AC de raiz confiável por meio de sua AC raiz ou intermediária (emissora) nos dispositivos
  - Perfis de certificado SCEP
  - Perfis de certificado PKCS *(com suporte apenas da [Digicert PKI Platform](certificates-digicert-configure.md))*
  - Perfis de certificado PKCS importados

## <a name="supported-platforms-and-certificate-profiles"></a>Perfis de certificado e plataformas compatíveis

| Plataforma              | Perfil de certificado confiável | Perfil de Certificado PKCS | Perfil de Certificado SCEP | Perfil de certificado PKCS importado  |
|--|--|--|--|---|
| Administrador do dispositivo Android | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png)|  ![Com suporte](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> – Totalmente gerenciado (proprietário do dispositivo)   | ![Com suporte](./media/certificates-configure/green-check.png) |   | ![Com suporte](./media/certificates-configure/green-check.png) |   |
| Android Enterprise <br> – Dedicado (proprietário do dispositivo)   | ![Com suporte](./media/certificates-configure/green-check.png)  |   | ![Com suporte](./media/certificates-configure/green-check.png)  |   |
| Android Enterprise <br> – Perfil de Trabalho    | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) |
| iOS                   | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) |
| macOS                 | ![Com suporte](./media/certificates-configure/green-check.png) |  ![Com suporte](./media/certificates-configure/green-check.png) |![Com suporte](./media/certificates-configure/green-check.png)|![Com suporte](./media/certificates-configure/green-check.png)|
| Windows Phone 8.1     |![Com suporte](./media/certificates-configure/green-check.png)  |  | ![Com suporte](./media/certificates-configure/green-check.png)| ![Com suporte](./media/certificates-configure/green-check.png) |
| Windows 8.1 e posterior |![Com suporte](./media/certificates-configure/green-check.png)  |  |![Com suporte](./media/certificates-configure/green-check.png) |   |
| Windows 10 e posterior  | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) | ![Com suporte](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Exportar o Certificado de Autoridade de Certificação raiz confiável

Para usar certificados PKCS importados, SCEP e PKCS, os dispositivos precisam confiar na autoridade de certificação raiz. Para estabelecer essa relação de confiança, exporte o Certificado de AC raiz confiável, bem como os certificados de autoridade de certificação intermediária ou emissora, como um certificado público (.cer). Obtenha esses certificados da AC emissora ou de qualquer dispositivo que confie na AC emissora.

Para exportar o certificado, confira a documentação da autoridade de certificação. Você precisará exportar o certificado público como um arquivo .cer.  Não exporte a chave privada, um arquivo .pfx.

Você usará esse arquivo .cer ao [criar perfis de certificado confiável](#create-trusted-certificate-profiles) para implantar esse certificado em seus dispositivos.

## <a name="create-trusted-certificate-profiles"></a>Criar perfis de certificado confiável

Crie um perfil de certificado confiável antes de criar um perfil de certificado PKCS importado, SCEP ou PKCS. A implantação de um perfil de certificado confiável garante que cada dispositivo reconheça a legitimidade da AC. Os perfis de Certificado SCEP referenciam diretamente um perfil de certificado confiável. Os perfis de Certificado PKCS não referenciam diretamente o perfil de certificado confiável, mas sim o servidor que hospeda a AC. Os perfis de certificados PKCS importados não referenciam diretamente o perfil de certificado confiável, mas podem usá-lo no dispositivo. A implantação de um perfil de certificado confiável em dispositivos garante que essa relação de confiança seja estabelecida. Quando um dispositivo não confiar na AC raiz, a política de perfil de Certificado SCEP ou PKCS falhará.

Crie um perfil de certificado confiável separado para cada plataforma de dispositivo à qual deseja dar suporte, assim como você fará para os perfis de certificados PKCS importados, SCEP e PKCS.

### <a name="to-create-a-trusted-certificate-profile"></a>Para criar um perfil de certificado confiável

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

   ![Navegue até o Intune e crie um perfil para um certificado confiável](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Insira as seguintes propriedades:

   - **Nome** do perfil
   - Opcionalmente defina uma **Descrição**
   - **Plataforma** na qual implantar o perfil
   - Defina o **Tipo de perfil** como **Certificado confiável**

4. Selecione **Configurações**, procure o arquivo .cer do certificado de Autoridade de Certificação raiz confiável que você exportou para uso com esse perfil de certificado e selecione **OK**.

5. Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:

   - **Repositório de certificados do computador – Raiz**
   - **Repositório de certificados do computador – Intermediário**
   - **Repositório de certificados do usuário – Intermediário**

6. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e escolha **Criar**.

O perfil é exibido na lista de perfis da janela *Dispositivos – Perfis de configuração*, com o tipo de perfil **Certificado confiável**. Lembre-se de atribuir esse perfil aos dispositivos que usarão Certificados SCEP ou PKCS. Para atribuir o perfil a grupos, confira [Atribuir perfis de dispositivo](../configuration/device-profile-assign.md).

> [!NOTE]
> Os dispositivos Android podem exibir uma mensagem informando que um terceiro instalou um certificado confiável.

## <a name="additional-resources"></a>Recursos adicionais

- [Atribuir perfis de dispositivo](../configuration/device-profile-assign.md)  
- [Usar S/MIME para assinar e criptografar emails](certificates-s-mime-encryption-sign.md)  
- [Usar uma autoridade de certificação de terceiros](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Próximas etapas

Criar perfis de certificado PKCS importado, SCEP ou PKCS para cada plataforma que deseja usar. Para continuar, confira os seguintes artigos:

- [Configurar a infraestrutura para dar suporte a Certificados SCEP com o Intune](certificates-scep-configure.md)  
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)  
- [Criar um perfil de certificado PKCS importado](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)
