---
title: Criar perfil de certificados no Microsoft Intune – Azure | Microsoft Docs
description: Para seus dispositivos, adicionar ou criar um perfil de certificado por meio da configuração do ambiente de certificado SCEP ou PKCS, exportar o certificado público, criar o perfil no Portal do Azure e, em seguida, atribuir SCEP ou PKCS aos perfis de certificado no Microsoft Intune no Portal do Azure
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/08/2019
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
ms.openlocfilehash: 37938287cc5ddde6285ec09aa0fffea56f98b3c3
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048935"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Configurar um perfil de certificado para seus dispositivos no Microsoft Intune

Conceda aos usuários o acesso aos recursos corporativos por meio de perfis de VPN, Wi-Fi ou email. Usando certificados, você pode autenticar essas conexões. Quando você usa certificados, os usuários finais não precisam inserir nomes de usuário e senhas para se autenticarem.

Use o Intune para atribuir esses certificados aos dispositivos gerenciados. O Intune é compatível com a atribuição e o gerenciamento dos seguintes tipos de certificados:

- Protocolo SCEP
- PKCS#12 (ou PFX)

Cada um desses tipos de certificado tem seus próprios pré-requisitos e requisitos de infraestrutura.


## <a name="overview"></a>Visão geral

1. Garanta que a infraestrutura de certificado correta está configurada. Você pode usar os [Certificados SCEP](certificates-scep-configure.md) e os [Certificados PKCS](certficates-pfx-configure.md).

2. Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação. Para instalar o certificado, crie e atribua um **perfil de certificado confiável** a cada dispositivo. Quando você atribui esse perfil, os dispositivos gerenciados pelo Intune solicitam e recebem o certificado raiz. Você deve criar um perfil separado para cada plataforma. Os perfis de certificado confiáveis estão disponíveis para as seguintes plataformas:

    - iOS 8.0 e posterior
    - macOS 10.11 e posterior
    - Android 4.0 e posterior
    - Android Enterprise  
    - Windows 8.1 e posterior
    - Windows Phone 8.1 e posterior
    - Windows 10 e posterior

    > [!NOTE]  
    > Não há suporte para perfis de certificado em dispositivos que executam o *Android Enterprise para dispositivos dedicados*.

3. Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email. Os seguintes tipos de perfil estão disponíveis para diferentes plataformas:  

   | Plataforma     |Certificado PKCS|Certificado SCEP| Certificado importado PKCS | 
   |--------------|----------------|----------------|-------------------|
   | Android                | Sim    | Sim    | Sim    |
   | Android Enterprise     | Sim    | Sim    | Sim    |
   | iOS                    | Sim    | Sim    | Sim    |
   | macOS                  |        | Sim    | Sim    |
   | Windows Phone 8.1      |        | Sim    | Sim    |
   | Windows 8.1 e posterior  |        | Sim    |        |
   | Windows 10 e posterior   | Sim    | Sim    | Sim    |

   Crie um perfil separado para cada plataforma de dispositivo. Ao criar o perfil, associe-o ao perfil de certificado raiz confiável já criado.

### <a name="further-considerations"></a>Considerações adicionais

- Se não tiver uma Autoridade de certificação corporativa, você precisará criar uma
- Se você usa perfis SCEP, configure um servidor de NDES (Serviço de Registro de Dispositivo de Rede)
- Se você planeja usar perfis SCEP ou PKCS, baixe e configure o Microsoft Intune Certificate Connector


## <a name="step-1-configure-your-certificate-infrastructure"></a>Etapa 1: Configurar a infraestrutura de certificado

Confira um dos artigos a seguir para ajudar a configurar a infraestrutura para cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Etapa 2: Exportar seu certificado de AC raiz confiável

Exporte o certificado de Autoridades de Certificação (AC) Confiáveis como um certificado público (.cer) da AC emissora ou de qualquer dispositivo que confie em sua AC emissora. Não exporte a chave privada (.pfx).

Este certificado é importando quando você configura um perfil de certificado confiável.

## <a name="step-3-create-trusted-certificate-profiles"></a>Etapa 3: Criar perfis de certificado confiável
Crie um perfil de certificado confiável antes de criar um perfil de certificado SCEP ou PKCS. É necessário um perfil de certificado confiável e um perfil SCEP ou PKCS para cada plataforma de dispositivo. As etapas para criar certificados confiáveis são semelhantes para cada plataforma de dispositivo.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Gerenciar** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil de certificado confiável.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável. Suas opções:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**

6. Na lista suspensa **Tipo de perfil**, escolha **Certificado confiável**.
7. Navegue até o certificado salvo na [Etapa 2: Exportar seu certificado de AC raiz confiável](#step-2-export-your-trusted-root-ca-certificate) e selecione **OK**.
8. Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:

    - **Repositório de certificados do computador – Raiz**
    - **Repositório de certificados do computador – Intermediário**
    - **Repositório de certificados do usuário – Intermediário**

9. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e escolha **Criar**.

O perfil será criado e aparecerá na lista. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).

   >[!NOTE]
   > Os dispositivos Android podem exibir uma mensagem informando que terceiros instalaram um certificado confiável.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Etapa 4: Criar perfis de certificado SCEP ou PKCS

Confira um dos artigos a seguir para ajudar a configurar e atribuir cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)

Depois de criar um perfil de certificado confiável, crie perfis de certificado SCEP ou PKCS para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, insira um perfil de certificado confiável para essa mesma plataforma. Essa etapa vincula os dois perfis de certificado, mas você ainda deve atribuir cada perfil separadamente.

## <a name="next-steps"></a>Próximas etapas
[Atribuir perfis de dispositivo](device-profile-assign.md)  
[Usar S/MIME para assinar e criptografar emails](certificates-s-mime-encryption-sign.md)  
[Usar autoridade de certificação de terceiros](certificate-authority-add-scep-overview.md)

## <a name="see-also"></a>Consulte também

[Solucionando problemas na configuração do NDES para uso com perfis de certificado do Microsoft Intune](https://support.microsoft.com/help/4459540)

[Solucionando problemas na implantação do perfil de certificado SCEP no Microsoft Intune](https://support.microsoft.com/help/4457481)
