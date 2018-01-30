---
title: Como configurar certificados com o Intune
titlesuffix: Azure portal
description: "Saiba como usar o Intune para criar e atribuir certificados que ajudam você a proteger conexões Wi-Fi, VPN e outras."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0245491540a2ade2dbb453a865ee73312fc759e0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Como configurar certificados no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode autenticar essas conexões usando certificados. Não é necessário inserir nomes de usuário e senhas para autenticar conexões quando certificados são usados.

Use o Intune para atribuir esses certificados aos dispositivos gerenciados. O Intune dá suporte à atribuição e gerenciamento desses tipos de certificados:

- Protocolo SCEP
- PKCS#12 (ou PFX)

Cada um desses tipos de certificado tem seus próprios pré-requisitos e requisitos de infraestrutura.

## <a name="general-workflow"></a>Fluxo de trabalho geral

1. Verifique se você tem a infraestrutura de certificado correta em vigor. Você pode usar os [Certificados SCEP](certificates-scep-configure.md) e os [Certificados PKCS](certficates-pfx-configure.md).
2. Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação. Para fazer isso, crie e atribua um **perfil de certificado confiável**. Quando você atribui esse perfil, os dispositivos gerenciados com o Intune solicitam e recebem o certificado raiz. Você deve criar um perfil separado para cada plataforma. Perfis de certificado confiável estão disponíveis para as seguintes plataformas:
    - iOS 8.0 e posterior
    - macOS 10.9 e posterior
    - Android 4.0 e posterior
    - Android for Work
    - Windows 8.1 e posterior
    - Windows Phone 8.1 e posterior
    - Windows 10 e posterior
3. Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email.

   É possível criar e atribuir um perfil de certificado **PKCS** ou **SCEP** para os dispositivos em execução nestas plataformas:

   - iOS 8.0 e posterior
   - Android 4.0 e posterior
   - Android for Work
   - Windows 10 (Desktop e Mobile) e posterior

   É possível usar apenas um perfil de certificado **SCEP** para dispositivos em execução nestas plataformas:

   - macOS 10.9 e posterior
   - Windows Phone 8.1 e posterior

Você deve criar um perfil separado para cada plataforma de dispositivo. Ao criar o perfil, associe-o ao perfil de certificado raiz confiável já criado.

### <a name="further-considerations"></a>Considerações adicionais

- Se não tiver uma Autoridade de Certificação Corporativa, você precisará criar uma.
- Também será necessário configurar um servidor NDES (Serviço de Registro de Dispositivo de Rede) se forem usados perfis SCEP.
- Se você planeja usar perfis SCEP ou PKCS, precisará baixar e configurar o Microsoft Intune Certificate Connector.


## <a name="step-1-configure-your-certificate-infrastructure"></a>Etapa 1: Configurar a infraestrutura de certificado

Consulte um dos tópicos a seguir para ajudar a configurar a infraestrutura para cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Etapa 2: Exportar o certificado de AC raiz confiável

Exporte o certificado de AC (Autoridade de Certificação) Raiz Confiável como um arquivo **.cer** da autoridade de certificação emissora ou de qualquer dispositivo que confie em sua autoridade de certificação emissora. Não exporte a chave privada.

Este certificado é importando quando você configura um perfil de certificado confiável.

## <a name="step-3-create-trusted-certificate-profiles"></a>Etapa 3: criar perfis de certificado confiável
Você deverá criar um perfil de certificado confiável antes de criar um perfil de certificado SCEP ou PKCS. Você precisa de um perfil de certificado confiável e um perfil SCEP ou PKCS para cada plataforma de dispositivo. O fluxo para a criação de certificados confiáveis é semelhante para cada plataforma de dispositivo.

### <a name="to-create-a-trusted-certificate-profile"></a>Para criar um perfil de certificado confiável

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado confiável.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável. No momento, é possível escolher uma das seguintes plataformas para as configurações de certificado:
    - **Android**
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
8. Após terminar, escolha **OK**, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil é criado e exibido na folha da lista de perfis.

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).


> [!Note]
> Os dispositivos Android exibem um aviso de que terceiros instalaram um certificado confiável.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Etapa 4: criar perfis de certificado SCEP ou PKCS

Consulte um dos tópicos a seguir para ajudar a configurar e atribuir cada tipo de perfil de certificado:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)

Depois de criar um perfil de certificado confiável, crie perfis de certificado SCEP ou PKCS para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, deverá especificar um perfil de certificado confiável para essa mesma plataforma. Isso vincula os dois perfis de certificado, mas você ainda deve atribuir cada perfil separadamente.


## <a name="next-steps"></a>Próximas etapas
Consulte [Como atribuir perfis de dispositivo](device-profile-assign.md) para obter informações gerais sobre como atribuir perfis de dispositivo.
