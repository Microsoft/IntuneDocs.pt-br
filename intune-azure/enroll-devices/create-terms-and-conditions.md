---
title: "Definir os termos e condições no Microsoft Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: definir termos e condições que os usuários veem no Portal da Empresa do Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: f7d6ebc9d71a077492ab615a3bc5397e092b1deb
ms.lasthandoff: 02/15/2017

---

# <a name="set-terms-and-conditions"></a>Definir termos e condições 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Você pode implantar os termos e condições do Intune em grupos de usuários para explicar como o registro, o acesso aos recursos de trabalho e o aplicativo de Portal da Empresa afetam usuários e dispositivos. Os usuários devem aceitar estes termos e condições antes de poderem usar o Portal da Empresa para registrar e acessar o trabalho.

Você pode criar e implantar várias políticas que contêm termos e condições diferentes. Você pode também gerar versões dos mesmos termos e condições em idiomas diferentes e, em seguida, implantá-las aos grupos apropriados.

**Para criar termos e condições**:

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e **Termos e Condições**.

3. Selecione **Criar**.

4. Na folha **Criar Termos e Condições**, especifique as seguintes informações:

   - **Nome de exibição**: nome a ser usado para os termos. Os usuários veem esse nome no aplicativo do Portal da Empresa.

   - **Descrição**: detalhes opcionais que ajudarão a identificar a política no Portal do Azure.

5. Selecione a seta ao lado de Definir termos de uso para abrir a folha de Termos e Condições e, em seguida, insira as seguintes informações:

   - **Título**: o título que os usuários veem no Portal da Empresa.

   - **Resumo dos Termos**: texto que explica o que significará se os usuários aceitarem os termos.

   - **Termos e Condições**: o rótulo legal que os usuários veem e devem aceitar ou rejeitar, por exemplo, “Eu concordo com os termos e condições”.

6. Selecione **OK**.

