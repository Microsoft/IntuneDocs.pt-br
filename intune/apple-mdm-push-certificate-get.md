---
title: Obter um Apple MDM Push Certificate para o Intune
titlesuffix: ''
description: Obtenha um Apple MDM Push Certificate para gerenciar dispositivos iOS com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 098aaf460f6bb805a506c15bf2b3535e0a39a435
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837519"
---
# <a name="get-an-apple-mdm-push-certificate"></a>Obtenha um certificado push de MDM da Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Um Apple MDM Push Certificate é necessário para o Intune gerenciar dispositivos iOS e macOS. Depois de você adicionar o certificado ao Intune, seus usuários poderão registrar os próprios dispositivos usando:

- O aplicativo do Portal da Empresa.

- Métodos de registro em massa da Apple, como o Programa de registro de dispositivos, o Apple School Manager ou o Apple Configurator.

Para obter mais informações sobre opções de registro, confira [Escolher como registrar dispositivos iOS](enrollment-method-choose-ios.md).

Quando um certificado de push expira, você precisa renová-lo. Durante a renovação, use a mesma ID Apple usada ao criar o certificado de push inicialmente.


## <a name="steps-to-get-your-certificate"></a>Etapas para obter o certificado
No [Portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple MDM Push Certificate** e, em seguida, siga essas etapas no [Portal do Azure](https://portal.azure.com).

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>Etapa 1. Conceder à Microsoft permissão para enviar informações de usuário e dispositivo para a Apple
Selecione **Eu aceito.** para conceder à Microsoft permissão para enviar dados para a Apple.

![A tela Configurar MDM Push Certificate com o MDM Push não configurado.](./media/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>Etapa 2. Baixe a solicitação de assinatura de certificado do Intune necessária para criar um Apple MDM Push Certificate
Selecione **Baixar o CSR** para baixar e salvar o arquivo de solicitação localmente. O arquivo é usado para solicitar um certificado de relação de confiança do Portal Apple Push Certificates.

  ### <a name="step-3-create-an-apple-mdm-push-certificate"></a>Etapa 3. Criar um Apple MDM Push Certificate
Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Entre com a ID da Apple da sua empresa e, em seguida, clique em **Criar um Certificado**. Selecione **Escolher Arquivo** e navegue até o arquivo de solicitação de assinatura de certificado e, em seguida, escolha **Carregar**. Na página de confirmação, escolha **Baixar** para baixar o arquivo de certificado (.pem) e salve o arquivo localmente.

> [!NOTE]
> O certificado está associado à ID da Apple usada para criá-lo. Como prática recomendada, use uma ID da Apple da empresa para tarefas de gerenciamento e certifique-se de que a caixa de correio seja monitorada por mais de uma pessoa, como uma lista de distribuição. Nunca use uma ID da Apple pessoal.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>Etapa 4. Insira a ID da Apple usada para criar o Apple MDM Push Certificate
Registre essa ID como um lembrete para quando for necessário renovar esse certificado.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>Etapa 5. Procure seu Apple MDM Push Certificate a ser carregado
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos Apple.

## <a name="renew-apple-mdm-push-certificate"></a>Renovar um certificado push de MDM da Apple
O certificado push de MDM da Apple é válido por um ano e deve ser renovado anualmente para manter o gerenciamento de dispositivos iOS e macOS. Se o certificado expirar, os dispositivos Apple registrados não poderão ser contatados.

O certificado está associado à ID da Apple usada para criá-lo. Renove o certificado push de MDM da Apple com a mesma ID da Apple usada para criá-lo.

1. No [portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, escolha o bloco **Apple MDM Push Certificate** na área de detalhes.
2. Escolha **Baixar o CSR** para baixar e salvar o arquivo de solicitação localmente. O arquivo é usado para solicitar um certificado de relação de confiança do Portal Apple Push Certificates.
3. Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Localize o certificado que você deseja renovar e selecione **Renovar**.
4. Na tela **Renovar Push Certificate**, forneça anotações para ajudá-lo a identificar o certificado no futuro, selecione **Escolher Arquivo** para navegar até o novo arquivo de solicitação baixado e escolha **Carregar**.
   > [!TIP]
   > Um certificado pode ser identificado por seu UID. Examine a **ID do Assunto** nos detalhes do certificado para localizar a parte do GUID do UID. Ou, em um dispositivo iOS registrado, vá até **Configurações** > **Geral** > **Dispositivo** **Gerenciamento**  >  **Perfil de Gerenciamento** > **Mais Detalhes** > **Perfil de Gerenciamento**. O segundo item de linha, **Tópico**, contém o GUID exclusivo que você pode comparar com o certificado no portal dos Apple Push Certificates.
 
6. Na tela **Confirmação**, selecione **Baixar** e salve o arquivo .pem localmente.
7. No [Portal do Azure](https://portal.azure.com), selecione o ícone de navegação do **Apple MDM Push Certificate**, selecione o arquivo .pem baixado da Apple e escolha **Carregar**.

O certificado push de MDM da Apple aparece **Ativo** e tem 365 dias até o vencimento.
