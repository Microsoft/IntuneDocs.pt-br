---
title: Criar perfil de certificados no Microsoft Intune – Azure | Microsoft Docs
description: Para seus dispositivos, adicionar ou criar um perfil de certificado por meio da configuração do ambiente de certificado SCEP ou PKCS, exportar o certificado público, criar o perfil no Portal do Azure e, em seguida, atribuir SCEP ou PKCS aos perfis de certificado no Microsoft Intune no Portal do Azure
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 76e6ba8cb1ed6804bfb50f69a00817a50fe1912e
ms.sourcegitcommit: 3db8af810b95c3a6ed3f8cc00f6ce79076ebb9db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2019
ms.locfileid: "71012449"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Usar certificados para autenticação no Microsoft Intune  

Use certificados com o Intune para autenticar os usuários em aplicativos e recursos corporativos por meio de perfis de VPN, Wi-Fi ou email. Quando você usa certificados para autenticar essas conexões, os usuários finais não precisam inserir nomes de usuário e senhas, o que ajuda a tornar seu acesso contínuo. Os certificados também são usados para assinatura e criptografia de email usando S/MIME.

O Intune dá suporte aos seguintes tipos de certificado:  

- Protocolo SCEP  
- PKCS#12 (ou PFX)  
- Certificados PKCS importados

Para implantar esses certificados, você criará e atribuirá perfis de certificado a dispositivos.  

Cada perfil de certificado individual criado dá suporte a uma única plataforma. Por exemplo, se você usar certificados PKCS, criará o perfil de certificado PKCS para o Android e um perfil de certificado PKCS separado para o iOS. Se você também usar certificados SCEP para essas duas plataformas, criará um perfil de Certificado SCEP para o Android e outro para o iOS.  

**Considerações gerais**:  
- Se você não tiver uma AC (autoridade de certificação) corporativa, precisará criar uma ou usar [uma de um de nossos parceiros com suporte](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners).
- Se você usar perfis de certificado SCEP usando os Serviços de Certificados do Microsoft Active Directory, configurará um servidor NDES (Serviço de Registro de Dispositivo de Rede).
- Se você usar o SCEP com um de nossos parceiros de autoridade de certificação, [precisará integrá-lo ao Intune](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).
- Os perfis de Certificado SCEP e PKCS exigem que você baixe, instale e configure o Microsoft Intune Certificate Connector. 
- Os certificados PCKS importados exigem que você baixe, instale e configure o Conector de Certificado PFX para Microsoft Intune.
- Os certificados PKCS importados exigem que você exporte certificados da autoridade de certificação e importe-os para o Microsoft Intune. Confira [o projeto PFXImport do PowerShell](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)
- Para que um dispositivo use perfis de certificado PKCS importados, SCEP ou PCKS, esse dispositivo precisa confiar na autoridade de certificação raiz. Use um *perfil de certificado confiável* para implantar o Certificado de Autoridade de Certificação raiz confiável em dispositivos.  

## <a name="supported-platforms-and-certificate-profiles"></a>Perfis de certificado e plataformas compatíveis  
| Plataforma              | Perfil de certificado confiável | Perfil de Certificado PKCS | Perfil de Certificado SCEP | Perfil de certificado PKCS importado  |
|--|--|--|--|---|
| Administrador do dispositivo Android | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png)|  ![Suportado](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> – Proprietário do Dispositivo   | ![Suportado](./media/certificates-configure/green-check.png) |   |  |   |
| Android Enterprise <br> – Perfil de Trabalho    | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) |
| iOS                   | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) |
| macOS                 | ![Suportado](./media/certificates-configure/green-check.png) |   |![Suportado](./media/certificates-configure/green-check.png)|![Suportado](./media/certificates-configure/green-check.png)|
| Windows Phone 8.1     |![Suportado](./media/certificates-configure/green-check.png)  |  | ![Suportado](./media/certificates-configure/green-check.png)| ![Suportado](./media/certificates-configure/green-check.png) |
| Windows 8.1 e posterior |![Suportado](./media/certificates-configure/green-check.png)  |  |![Suportado](./media/certificates-configure/green-check.png) |   |
| Windows 10 e posterior  | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) | ![Suportado](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Exportar o Certificado de Autoridade de Certificação raiz confiável  
Para usar certificados PKCS importados, SCEP e PKCS, os dispositivos precisam confiar na autoridade de certificação raiz. Para estabelecer essa relação de confiança, exporte o Certificado de Autoridade de Certificação (AC) raiz confiável, bem como os certificados de autoridade de certificação intermediárias ou emissoras, como um certificado público (.cer). Obtenha esses certificados da AC emissora ou de qualquer dispositivo que confie na AC emissora.  

Para exportar o certificado, confira a documentação da autoridade de certificação. Você precisará exportar o certificado público como um arquivo .cer.  Não exporte a chave privada, um arquivo .pfx.  

Você usará esse arquivo .cer ao [criar perfis de certificado confiável](#create-trusted-certificate-profiles) para implantar esse certificado em seus dispositivos.  

## <a name="create-trusted-certificate-profiles"></a>Criar perfis de certificado confiável  
Crie um perfil de certificado confiável antes de criar um perfil de certificado PKCS importado, SCEP ou PKCS. A implantação de um perfil de certificado confiável garante que cada dispositivo reconheça a legitimidade da AC. Os perfis de Certificado SCEP referenciam diretamente um perfil de certificado confiável. Os perfis de Certificado PKCS não referenciam diretamente o perfil de certificado confiável, mas sim o servidor que hospeda a AC. Os perfis de certificados PKCS importados não referenciam diretamente o perfil de certificado confiável, mas podem usá-lo no dispositivo. A implantação de um perfil de certificado confiável em dispositivos garante que essa relação de confiança seja estabelecida. Quando um dispositivo não confiar na AC raiz, a política de perfil de Certificado SCEP ou PKCS falhará.  

Crie um perfil de certificado confiável separado para cada plataforma de dispositivo à qual deseja dar suporte, assim como você fará para os perfis de certificados PKCS importados, SCEP e PCKS.  


### <a name="to-create-a-trusted-certificate-profile"></a>Para criar um perfil de certificado confiável  

1. Entre no [portal do Intune](https://aka.ms/intuneportal).  
2. Selecione **Configuração do dispositivo** > **Gerenciar** > **Perfis** > **Criar perfil**.  
3. Insira **Nome e Descrição** para o perfil de certificado confiável.  
4. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável.  
5. Na lista suspensa **Tipo de perfil**, escolha **Certificado confiável**.  
6. Procure o arquivo .cer do Certificado de Autoridade de Certificação raiz confiável exportado para uso com esse perfil de certificado e, em seguida, selecione **OK**.  
7. Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:  
   - **Repositório de certificados do computador – Raiz**
   - **Repositório de certificados do computador – Intermediário**
   - **Repositório de certificados do usuário – Intermediário**
8. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e escolha **Criar**.
O perfil é exibido na lista de perfis no painel de exibição *Configuração do dispositivo – Perfis*, com um tipo de perfil **Certificado confiável**.  Lembre-se de atribuir esse perfil aos dispositivos que usarão Certificados SCEP ou PCKS. Para atribuir o perfil a grupos, confira [Atribuir perfis de dispositivo](device-profile-assign.md).

> [!NOTE]  
> Os dispositivos Android podem exibir uma mensagem informando que um terceiro instalou um certificado confiável.  

## <a name="additional-resources"></a>Recursos adicionais  
- [Atribuir perfis de dispositivo](device-profile-assign.md)  
- [Usar S/MIME para assinar e criptografar emails](certificates-s-mime-encryption-sign.md)  
- [Usar uma autoridade de certificação de terceiros](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Próximas etapas  
Depois de criar e atribuir perfis de certificado confiável, crie perfis de certificado PKCS importado, SCEP ou PKCS para cada plataforma que deseja usar. Para continuar, confira os seguintes artigos:  
- [Configurar a infraestrutura para dar suporte a Certificados SCEP com o Intune](certificates-scep-configure.md)  
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)  
- [Criar um perfil de certificado PKCS importado](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)  

