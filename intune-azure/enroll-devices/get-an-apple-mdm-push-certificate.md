---
title: "Obter um Apple MDM Push Certificate | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: conheça as etapas para obter um Apple MDM Push Certificate para gerenciar dispositivos iOS com o Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c0884ded1c8c55bb1b7968e483864b42f5bd6bde


---

# <a name="get-an-apple-mdm-push-certificate"></a>Obtenha um Apple MDM Push Certificate 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune possibilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e dispositivos Mac OS X, além de conceder aos usuários acesso a aplicativos e email da empresa. Um certificado APNs (Apple Push Notification Service) é necessário para o Intune gerenciar dispositivos iOS e Mac. Depois de adicionar o certificado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos ou você poderá configurar o gerenciamento de dispositivo iOS corporativo.

**Para obter o MDM Push Certificate:**<br>

No Portal do Azure, escolha **Mais Serviços**, digite **Intune** na caixa de texto e escolha **Outros** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Apple MDM Push Certificate** e siga as etapas numeradas no Portal do Azure, mostradas abaixo.

**Etapa 1. Baixe a solicitação de assinatura de certificado do Intune necessária para criar um Apple MDM Push Certificate.**<br>
Selecione **Transferir o CSR** para baixar e salvar o arquivo .csr localmente. O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.

**Etapa 2. Criar um Apple MDM Push Certificate.**<br>
Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple. Entre com sua ID da Apple corporativa para criar o certificado push usando o arquivo .csr. Depois de escolher **Carregar** no Portal de Certificado Push da Apple, você receberá um arquivo .json. Use este arquivo para o certificado push. Conclua o download e retorne ao Apple Push Certificates Portal para Certificados de Servidores de Terceiros e escolha **Download**. Baixe o certificado push (arquivo .pem) e salve-o localmente.
Observação

**Etapa 3. Insira a ID da Apple usada para criar o Apple MDM Push Certificate.**

**Etapa 4. Procure seu Apple MDM Push Certificate a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.



<!--HONumber=Feb17_HO1-->


