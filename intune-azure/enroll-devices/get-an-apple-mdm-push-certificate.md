---
title: Obtenha um Apple MDM Push Certificate
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as etapas para obter um Apple MDM Push Certificate para gerenciar dispositivos iOS com o Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 26991bd0c7632d04b75ecbec023d96c1045f337a
ms.lasthandoff: 02/18/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Obtenha um certificado push de MDM da Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune possibilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e dispositivos Mac OS X, além de conceder aos usuários acesso a aplicativos e email da empresa. Um certificado APNs (Apple Push Notification Service) é necessário para o Intune gerenciar dispositivos iOS e Mac. Depois de adicionar o certificado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos ou você poderá configurar o gerenciamento de dispositivo iOS corporativo.

## <a name="steps-to-get-your-certificate"></a>Etapas para obter o certificado
No portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Apple MDM Push Certificate** e siga as etapas numeradas no Portal do Azure, mostradas abaixo.

**Etapa 1. Baixe a solicitação de assinatura de certificado do Intune necessária para criar um Apple MDM Push Certificate.**<br>
Selecione **Transferir o CSR** para baixar e salvar o arquivo .csr localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.

**Etapa 2. Criar um Apple MDM Push Certificate.**<br>
Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Entre com sua ID da Apple corporativa para criar o certificado push usando o arquivo .csr. Depois de escolher **Carregar** no Portal de Certificado Push da Apple, você receberá um arquivo .json. Use este arquivo para o certificado push. Conclua o download e retorne ao Apple Push Certificates Portal para Certificados de Servidores de Terceiros e escolha **Download**. Baixe o certificado push (arquivo .pem) e salve-o localmente.
Observação

**Etapa 3. Insira a ID da Apple usada para criar o Apple MDM Push Certificate.**

**Etapa 4. Procure seu Apple MDM Push Certificate a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.

