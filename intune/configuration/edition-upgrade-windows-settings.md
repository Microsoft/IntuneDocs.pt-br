---
title: Configurações do modo de atualização e S do Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações e o que elas fazem ao atualizar uma edição do Windows 10 em um dispositivo ou habilitar o modo S em um dispositivo usando um perfil de configuração de dispositivo no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 75878e2110e9d855c2a0f78c0e7a1112f883872e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72489667"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>Configurações de dispositivo com Windows 10 (e mais recente) para atualizar edições ou habilitar o modo S no Intune

O Microsoft Intune inclui muitas configurações para ajudar a proteger seus dispositivos. Este artigo lista e descreve as configurações para atualizar as edições ou habilitar o modo S em dispositivos com Windows 10. Essas configurações são criadas em um perfil de configuração de atualização no Intune que são enviadas por push ou implantadas em dispositivos.

Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para controlar a edição e as opções de modo S de seus dispositivos com Windows 10.

Para saber mais sobre esse recurso, consulte [Atualizar edições Windows 10 ou habilitar o modo S](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie o perfil](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Atualização de edição

- **Edição para a qual atualizar**: selecione a edição do Windows 10 que você está atualizando. Os dispositivos de destino desta política são atualizados para a edição que você escolher.
- **Chave do Produto (Product Key)** : insira a chave do produto (Product Key) que você recebeu da Microsoft. Depois de criar a política com a chave do produto (Product Key), a chave não pode ser atualizada e é ocultada por motivos de segurança. Para alterar a chave do produto (Product Key), insira a chave inteira novamente.
- **Arquivo de Licença**: para o **Windows 10 Holographic for Business** ou o **Windows 10 Mobile Edition**, escolha **Procurar** para selecionar o arquivo de licença que você recebeu do Microsoft. Esse arquivo de licença inclui informações de licença das edições para as quais você está atualizando os dispositivos.

## <a name="mode-switch"></a>Alternar modo

- **Nenhuma configuração**: um dispositivo no modo S permanece no modo S. Um usuário final pode tirar o dispositivo do modo S.
- **Ficar no modo S**: impede o usuário final de tirar o dispositivo do modo S.
- **Alternância**: tira o dispositivo do modo S.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas talvez ainda não esteja fazendo nada. [Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Você também pode criar perfis de atualização de edição para dispositivos com [Windows Holographic for Business](holographic-upgrade.md).
