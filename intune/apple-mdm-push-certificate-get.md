---
title: Obtenha um Apple MDM Push Certificate
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as etapas para obter um Apple MDM Push Certificate para gerenciar dispositivos iOS com o Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e3ff50fa65eff897147081f2ec9ab366dbf50140
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Obtenha um certificado push de MDM da Apple

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e computadores Mac, além de permitir acesso a aplicativos e ao email da empresa aos usuários. Um certificado de Push MDM é necessário para o Intune gerenciar dispositivos iOS e Mac. Depois de adicionar o certificado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos. Você também pode configurar o gerenciamento de dispositivos iOS corporativo com o Programa de Registro de Dispositivo Apple ou registrar dispositivos usando o Apple Configurator, por exemplo. Para obter mais informações sobre opções de registro, confira [Escolher como registrar dispositivos iOS](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Etapas para obter o certificado
No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Registro da Apple** **Apple MDM Push Certificate**e siga as etapas numeradas no Portal do Azure, mostradas abaixo.

**Etapa 1. Baixe a solicitação de assinatura de certificado do Intune necessária para criar um Apple MDM Push Certificate.**<br>
Selecione **Transferir o CSR** para baixar e salvar o arquivo .csr localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.

**Etapa 2. Criar um Apple MDM Push Certificate.**<br>
Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Entre com sua ID da Apple corporativa para criar o certificado push usando o arquivo .csr. Depois de escolher **Carregar** no Portal de Certificado Push da Apple, você receberá um arquivo .json. Use este arquivo para o certificado push. Conclua o download e retorne ao Apple Push Certificates Portal para Certificados de Servidores de Terceiros e escolha **Download**. Baixe o certificado push (arquivo .pem) e salve-o localmente.

> [!NOTE]
> O certificado está associado à ID da Apple usada para criá-lo. Como prática recomendada, use uma ID da Apple empresarial para as tarefas de gerenciamento. Nunca use uma ID da Apple pessoal.

**Etapa 3. Insira a ID da Apple usada para criar o Apple MDM Push Certificate.**

**Etapa 4. Procure seu Apple MDM Push Certificate a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.

## <a name="renew-apple-mdm-push-certificate"></a>Renovar um certificado push de MDM da Apple
O certificado push de MDM da Apple é válido por um ano e deve ser renovado anualmente para manter o gerenciamento de dispositivos iOS e macOS. Se o certificado expirar, os dispositivos Apple registrados não poderão ser contatados.

O certificado está associado à ID da Apple usada para criá-lo. Renove o certificado push de MDM da Apple com a mesma ID da Apple usada para criá-lo.

> [!NOTE]
> O certificado está associado à ID da Apple usada para criá-lo. Como prática recomendada, use uma ID da Apple empresarial para as tarefas de gerenciamento. Nunca use uma ID da Apple pessoal.

1. No [portal do Azure Intune](https://portal.azure.com), escolha **Registro de dispositivo** > **Registro Apple** e, em seguida, selecione **Certificado push de MDM da Apple**.
2. Selecione **Transferir o CSR** para baixar e salvar o arquivo .csr localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.
3. Localize o certificado que você deseja renovar e selecione **Renovar**.
4. Na tela **Renovar o certificado push**, forneça anotações para ajudá-lo a identificar o certificado no futuro, selecione **Escolher arquivo** para navegar até o novo arquivo .csr baixado e escolha **Upload**.
5. Na tela **Confirmação**, selecione **Baixar** e salve o arquivo .pem localmente.
6. No portal do Azure Intune, selecione o ícone de navegação do **Certificado push de MDM da Apple**, selecione o arquivo .pem baixado da Apple e escolha **Upload**.

O certificado push de MDM da Apple aparece **Ativo** e tem 365 dias até o vencimento.

