---
title: Criar perfil de certificados no Microsoft Intune – Azure | Microsoft Docs
description: Para seus dispositivos, adicionar ou criar um perfil de certificado por meio da configuração do ambiente de certificado SCEP ou PKCS, exportar o certificado público, criar o perfil no Portal do Azure e, em seguida, atribuir SCEP ou PKCS aos perfis de certificado no Microsoft Intune no Portal do Azure
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9329a57ee7d47cb99a7c87326bb043c0a04c6313
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905199"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Configurar um perfil de certificado para seus dispositivos no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode autenticar essas conexões usando certificados. Ao usar certificados, não é necessário inserir nomes de usuário e senhas para autenticar conexões

Use o Intune para atribuir esses certificados aos dispositivos gerenciados. O Intune é compatível com a atribuição e o gerenciamento dos seguintes tipos de certificados:

- Protocolo SCEP
- PKCS#12 (ou PFX)

Cada um desses tipos de certificado tem seus próprios pré-requisitos e requisitos de infraestrutura.

## <a name="overview"></a>Visão geral

1. Verifique se você tem a infraestrutura de certificado correta em vigor. Você pode usar os [Certificados SCEP](certificates-scep-configure.md) e os [Certificados PKCS](certficates-pfx-configure.md).

2. Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação. Para fazer isso, crie e atribua um **perfil de certificado confiável**. Quando você atribui esse perfil, os dispositivos gerenciados com o Intune solicitam e recebem o certificado raiz. Você deve criar um perfil separado para cada plataforma. Os perfis de certificado confiáveis estão disponíveis para as seguintes plataformas:

    - iOS 8.0 e posterior
    - macOS 10.11 e posterior
    - Android 4.0 e posterior
    - Perfil de trabalho Android
    - Windows 8.1 e posterior
    - Windows Phone 8.1 e posterior
    - Windows 10 e posterior

3. Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email. É possível criar e atribuir um perfil de certificado **PKCS** ou **SCEP** para os dispositivos que executam as seguintes plataformas:

   - iOS 8.0 e posterior
   - Android 4.0 e posterior
   - Perfil de trabalho Android
   - Windows 10 (Desktop e Mobile) e posterior

   Você só pode usar um perfil de certificado **SCEP** para dispositivos em execução nestas plataformas:

   - macOS 10.9 e posterior
   - Windows Phone 8.1 e posterior

Crie um perfil separado para cada plataforma de dispositivo. Ao criar o perfil, associe-o ao perfil de certificado raiz confiável já criado.

### <a name="further-considerations"></a>Considerações adicionais

- Se não tiver uma Autoridade de certificação corporativa, você precisará criar uma
- Se você usa perfis SCEP, configure um servidor de NDES (Serviço de Registro de Dispositivo de Rede)
- Se você planeja usar perfis SCEP ou PKCS, baixe e configure o Microsoft Intune Certificate Connector


## <a name="step-1-configure-your-certificate-infrastructure"></a>Etapa 1: Configurar a infraestrutura de certificado

Consulte um dos tópicos a seguir para ajudar a configurar a infraestrutura para cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Etapa 2: Exportar o certificado de AC raiz confiável

Exporte o certificado de Autoridades de Certificação (AC) Confiáveis como um certificado público (.cer) da AC emissora ou de qualquer dispositivo que confie em sua AC emissora. Não exporte a chave privada (.pfx).

Este certificado é importando quando você configura um perfil de certificado confiável.

## <a name="step-3-create-trusted-certificate-profiles"></a>Etapa 3: criar perfis de certificado confiável
Crie um perfil de certificado confiável antes de criar um perfil de certificado SCEP ou PKCS. É necessário um perfil de certificado confiável e um perfil SCEP ou PKCS para cada plataforma de dispositivo. As etapas para criar certificados confiáveis são semelhantes para cada plataforma de dispositivo.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, escolha **Gerenciar** > **Perfis**.
3. No painel de perfis, escolha **Criar perfil**.
4. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado confiável.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável. No momento, é possível escolher uma das seguintes plataformas para as configurações de certificado:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**

6. Na lista suspensa **Tipo de perfil**, escolha **Certificado confiável**.
7. Navegue até o certificado salvo na tarefa 1 e clique em **OK**.
8. Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:
    - **Repositório de certificados do computador – Raiz**
    - **Repositório de certificados do computador – Intermediário**
    - **Repositório de certificados do usuário – Intermediário**
8. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e escolha **Criar**.

O perfil será criado e aparecerá na lista. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).

Os dispositivos Android podem exibir uma mensagem informando que terceiros instalaram um certificado confiável.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Etapa 4: criar perfis de certificado SCEP ou PKCS

Consulte um dos tópicos a seguir para ajudar a configurar e atribuir cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)

Depois de criar um perfil de certificado confiável, crie perfis de certificado SCEP ou PKCS para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, insira um perfil de certificado confiável para essa mesma plataforma. Essa etapa vincula os dois perfis de certificado, mas você ainda deve atribuir cada perfil separadamente.

## <a name="next-steps"></a>Próximas etapas
Consulte [Como atribuir perfis de dispositivo](device-profile-assign.md) para obter informações gerais sobre como atribuir perfis de dispositivo.
