---
title: "Definir restrições de registro no Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: restringir o registro pela plataforma e definir um limite de registro de dispositivo no Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: c4fa22fad4df9c0e4699cf258eb9518a1534bb94

---

# <a name="set-enrollment-restrictions"></a>Definir restrições de registro 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Você pode definir os tipos e o número máximo de dispositivos que você permitirá que sejam registrados. Na folha Restrições de Registro, você pode definir:

- As plataformas que têm permissão para registrar e se deseja bloquear o registro de dispositivos de propriedade pessoal para Android e iOS.

- O número máximo de dispositivos que um usuário tem permissão para registrar.

## <a name="set-device-type-restrictions"></a>Definir restrições de tipo de dispositivo

1. No portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Restrições de Registro**.

3. Em **Restrições de Tipo de Dispositivo**, selecione **Padrão**.

4. Na folha **Todos os Usuários**, selecione **Plataformas**.

5. Para plataformas que têm permissão para se registrarem no Intune, selecione **Permitir**. Para plataformas que você deseja impedir de se registrarem, selecione **Bloquear**. Plataformas são definidas como **Permitir** por padrão. 

    >[!NOTE]
    >Essas configurações não se aplicam ou bloqueiam registros do Windows que usam o cliente de software do Intune. Essas configurações afetam somente o registro usando o gerenciamento de dispositivo móvel. 

6. Selecione **Salvar**.

7. Selecione **Configurações de Plataforma**.

8. Escolha se deseja **Permitir** ou **Bloquear** os dispositivos iOS e Android de serem registrados.

9. Selecione **Salvar**.

## <a name="set-device-limit-restrictions"></a>Definir restrições de limite de dispositivos

1. No portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Restrições de Registro**.

3. Em **Restrições de Limite de Dispositivo**, selecione **Padrão**.

4. Na folha **Todos os Usuários**, selecione **Limite de Dispositivos**.

5. Selecione o número máximo de dispositivos que um usuário pode registrar e selecione **Salvar**.



<!--HONumber=Feb17_HO3-->


