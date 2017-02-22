---
title: "Definir restrições de registro no Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: restringir o registro pela plataforma e definir um limite de registro de dispositivo no Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 1bdefce35c20ce24b94ee701a2d13b5408f435ce

---

# <a name="set-enrollment-restrictions"></a>Definir restrições de registro 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Você pode limitar os tipos de dispositivos que têm permissão para se registrarem no Intune especificando as plataformas permitidas. Você também pode definir o número máximo de dispositivos que um usuário tem permissão para registrar.

## <a name="set-device-type-restrictions"></a>Definir restrições de tipo de dispositivo

1. No Portal do Azure, escolha **Mais Serviços**, digite **Intune** na caixa de texto e escolha **Outros** > **Intune**

2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Restrições de Registro**.

3. Em **Restrições de Tipo de Dispositivo**, selecione **Padrão**.

4. Na folha **Todos os Usuários**, selecione **Plataformas**.

5. Para plataformas que têm permissão para se registrarem no Intune, selecione **Permitir**. Para plataformas que você deseja impedir de se registrarem, selecione **Bloquear**.

6. Selecione **Salvar**.

7. Selecione **Configurações de Plataforma**.

8. Escolha se deseja permitir ou bloquear os dispositivos iOS de registro de sua propriedade.

9. Selecione **Salvar**.

## <a name="set-device-limit-restrictions"></a>Definir restrições de limite de dispositivos

1. Na folha do Intune no Portal do Azure, escolha **Registrar dispositivos** e escolha **Restrições de Registro**.

2. Em **Restrições de Limite de Dispositivo**, selecione **Padrão**.

3. Na folha **Todos os Usuários**, selecione **Limite de Dispositivos**.

4. Selecione o número máximo de dispositivos que um usuário pode registrar e selecione **Salvar**.



<!--HONumber=Feb17_HO1-->


