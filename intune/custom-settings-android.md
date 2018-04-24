---
title: Adicionar configurações personalizadas a dispositivos Android no Microsoft Intune ‑ Azure | Microsoft Docs
description: Adicionar ou criar um perfil personalizado para dispositivos Android para criar um perfil de Wi-Fi com uma chave pré-compartilhada, criar um perfil de VPN por aplicativo ou permitir/bloquear aplicativos para dispositivos Samsung Knox Standard no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0195e138b59fae019fa2bc02aadf211257a65cac
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="custom-settings-for-android-devices---intune"></a>Configurações personalizadas para dispositivos Android – Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Os perfis personalizados usam as definições do OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir os diversos recursos em dispositivos Android. Essas configurações geralmente são usadas pelos fabricantes de dispositivos móveis para controlar os recursos do dispositivo.

Usando um perfil personalizado, é possível definir e atribuir as seguintes configurações do Android. Essas configurações não são nativas das políticas do Intune:

- [Criar um perfil de Wi-Fi com uma chave pré-compartilhada](/intune/wi-fi-profile-shared-key)
- [Criar um perfil de VPN por aplicativo](/intune/android-pulse-secure-per-app-vpn)
- [Permitir e bloquear aplicativos para dispositivos Samsung KNOX Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Somente as configurações listadas podem ser definidas por esse tipo de perfil. Dispositivos Android não expõem uma lista completa das configurações de OMA-URI que é possível configurar. Se você quiser ver mais configurações, vote em mais configurações no [site Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Configurações de perfil personalizadas para dispositivos Android

1. Entre no [Portal do Azure](https://portal.azure.com). 
2. Selecione **Todos os Serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Crie um perfil personalizado usando a plataforma Android. [Definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) lista as etapas.
4. Em **Configurações de OMA-URI personalizadas**, selecione **Adicionar** e, em seguida, **Adicionar Linha**.
5. Digite as seguintes propriedades:

   - **Nome** – Insira um nome exclusivo para a configuração de OMA-URI possa ser facilmente encontrada.
   - **Descrição** – Insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
   - **Tipo de dados** – Insira o tipo de dados usado para essa configuração de OMA-URI. Escolha dentre **Cadeia de caracteres**, **Cadeia de caracteres (XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante** ou **Booliano**.
   - **OMA-URI** – Insira o OMA-URI que você deseja.
   - **Valor** – Especifique o valor que você deseja associar ao OMA-URI inserido.

6. Selecione **OK** para salvar suas alterações. Continue a adicionar mais configurações conforme necessário.

## <a name="next-steps"></a>Próximas etapas

Após concluir as configurações, o perfil será criado e aparecerá na lista. Para atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
