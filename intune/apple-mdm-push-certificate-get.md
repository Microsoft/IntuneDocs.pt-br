---
title: Obtenha um Apple MDM Push Certificate
titlesuffix: Microsoft Intune
description: "Conheça as etapas para obter um Apple MDM Push Certificate para gerenciar dispositivos iOS com o Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ed6ae1812e49fa0ceda3079d25afd92ceeac01bd
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Obtenha um certificado push de MDM da Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e computadores Mac, além de permitir acesso a aplicativos e ao email da empresa aos usuários. Um certificado de Push MDM é necessário para o Intune gerenciar dispositivos iOS e Mac. Depois de adicionar o certificado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos. Você também pode configurar o gerenciamento de dispositivos iOS corporativo com o Programa de Registro de Dispositivo Apple ou registrar dispositivos usando o Apple Configurator, por exemplo. Para obter mais informações sobre opções de registro, confira [Escolher como registrar dispositivos iOS](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Etapas para obter o certificado
No [Portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** > **Registro da Apple** > **Apple MDM Push Certificate** e, em seguida, siga essas etapas no [Portal do Azure](https://portal.azure.com).

**Etapa 1. Baixe a solicitação de assinatura de certificado do Intune necessária para criar um Apple MDM Push Certificate.**<br>
Selecione **Baixar o CSR** para baixar e salvar o arquivo de solicitação localmente. O arquivo é usado para solicitar um certificado de relação de confiança do Portal Apple Push Certificates.

  ![A tela Configurar MDM Push Certificate com o MDM Push não configurado.](./media/create-mdm-push-certificate.png)

**Etapa 2. Criar um Apple MDM Push Certificate.**<br>
Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Entre com a ID da Apple da sua empresa e, em seguida, clique em **Criar um Certificado**. Selecione **Escolher Arquivo** e navegue até o arquivo de solicitação de assinatura de certificado e, em seguida, escolha **Carregar**. Na página de confirmação, escolha **Baixar** para baixar o arquivo de certificado (.pem) e salve o arquivo localmente.

> [!NOTE]
> O certificado está associado à ID da Apple usada para criá-lo. Como prática recomendada, use uma ID da Apple empresarial para as tarefas de gerenciamento. Nunca use uma ID da Apple pessoal.

**Etapa 3. Insira a ID da Apple usada para criar o Apple MDM Push Certificate.**<br>
Registre essa ID como um lembrete para quando for necessário renovar esse certificado.

**Etapa 4. Procure seu Apple MDM Push Certificate a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos Apple.

## <a name="renew-apple-mdm-push-certificate"></a>Renovar um certificado push de MDM da Apple
O certificado push de MDM da Apple é válido por um ano e deve ser renovado anualmente para manter o gerenciamento de dispositivos iOS e macOS. Se o certificado expirar, os dispositivos Apple registrados não poderão ser contatados.

O certificado está associado à ID da Apple usada para criá-lo. Renove o certificado push de MDM da Apple com a mesma ID da Apple usada para criá-lo.

1. No [Portal do Azure](https://portal.azure.com), escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, escolha **Apple MDM Push Certificate**.
2. Escolha **Baixar o CSR** para baixar e salvar o arquivo de solicitação localmente. O arquivo é usado para solicitar um certificado de relação de confiança do Portal Apple Push Certificates.
3. Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Localize o certificado que você deseja renovar e selecione **Renovar**.
4. Na tela **Renovar Push Certificate**, forneça anotações para ajudá-lo a identificar o certificado no futuro, selecione **Escolher Arquivo** para navegar até o novo arquivo de solicitação baixado e escolha **Carregar**.
   > [!TIP]
   > Um certificado pode ser identificado por seu UID. Examine a **ID do Assunto** nos detalhes do certificado para localizar a parte do GUID do UID. Ou, em um dispositivo iOS registrado, vá até **Configurações** > **Geral** > **Dispositivo** **Gerenciamento**  >  **Perfil de Gerenciamento** > **Mais Detalhes** > **Perfil de Gerenciamento**. O segundo item de linha, **Tópico**, contém o GUID exclusivo que você pode comparar com o certificado no portal dos Apple Push Certificates.
 
6. Na tela **Confirmação**, selecione **Baixar** e salve o arquivo .pem localmente.
7. No [Portal do Azure](https://portal.azure.com), selecione o ícone de navegação do **Apple MDM Push Certificate**, selecione o arquivo .pem baixado da Apple e escolha **Carregar**.

O certificado push de MDM da Apple aparece **Ativo** e tem 365 dias até o vencimento.
