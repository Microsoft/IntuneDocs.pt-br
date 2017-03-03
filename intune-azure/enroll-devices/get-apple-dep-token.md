---
title: "Obter um certificado DEP da Apple para o Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: instruções para configurar e carregar um certificado push de MDM, um pré-requisito para o gerenciamento de dispositivos Apple no Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: b2c79e92f6378825bdaac03d2d9be699bdaca95b
ms.lasthandoff: 02/15/2017

---

# <a name="get-an-apple-dep-certificate"></a>Obtenha um certificado DEP da Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Antes que possa registrar dispositivos iOS da empresa com o DEP, você precisa de m token do DEP da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos de sua empresa que fazem parte do DEP. Ele também permite que o Intune realize carregamentos de Perfis de registro para a Apple e atribua dispositivos para esses perfis.

Para gerenciar dispositivos iOS corporativos com o DEP (Programa de Registro de Dispositivo) da Apple, sua organização deve ingressar no DEP da Apple e obter dispositivos por meio do programa. Mais detalhes desse processo estão disponíveis em: https://deploy.apple.com. As vantagens do programa incluem a instalação não assistida de dispositivos sem usar um cabo USB para conectar cada dispositivo a um computador.

> [!NOTE]
> Leia esta observação somente se você for um cliente migrado do console de administração do Intune para o Portal do Azure. Se você excluiu um token de DEP da Apple no console de administração do Intune durante o período de migração, pode ser que o token de DEP tenha sido restaurado para sua conta do Intune. Se isso acontecer, basta excluir o token de DEP do Portal do Azure. 

**Para obter um certificado DEP da Apple**</br>
No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, escolha **Registrar dispositivos** > **Token de DEP da Apple** e, em seguida, siga as etapas numeradas no Portal do Azure, mostradas abaixo.

**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token de DEP da Apple.**<br>
Selecione **Baixar sua chave pública** para baixar e salvar a chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

**Etapa 2. Baixe um token de DEP da Apple do site da Apple adequado.**<br>
Selecione [Criar um token de DEP por meio de Programas de Implantação da Apple](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID da Apple corporativa. É necessário usar essa ID da Apple para renovar seu token de DEP.

   1.  No [Portal do Programa de Registro do Dispositivo](https://deploy.apple.com), vá até **Programa de Registro de Dispositivo** &gt; **Gerenciar Servidores** e escolha **Adicionar Servidor MDM**.

   2.  Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

   3.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.

   4.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** mostra um link **Seu Token do Servidor**. Baixe o arquivo do token (.p7m) do servidor em seu computador e escolha **Concluído**.

    Esse arquivo de certificado (.p7m) é usado para estabelecer uma relação de confiança entre os servidores do Programa de registro de dispositivo da Apple.

**Etapa 3. Insira a ID da Apple usada para criar o token de DEP da Apple. Essa ID pode ser usada para renovar seu token de DEP da Apple.**

**Etapa 4. Navegue até seu token de DEP da Apple a ser carregado. O Intune vai sincronizar-se automaticamente com a sua conta do DEP.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.

