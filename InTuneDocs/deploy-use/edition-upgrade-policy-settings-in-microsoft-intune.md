---
title: "Configurações da política de atualização de edição do Windows | Microsoft Docs"
description: "Saiba como atualizar automaticamente os dispositivos Windows 10 para a versão mais recente com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: ae6477866991cec4091ff2790b925b0e464375f9


---

# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Configurações da política de atualização de edição do Windows no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A **Política de atualização de edição** do Microsoft Intune permite atualizar automaticamente os dispositivos que executam uma das seguintes versões do Windows 10 para uma edição mais recente:
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

Há suporte para os seguintes caminhos de atualização:
- Do Windows 10 Pro para o Windows 10 Enterprise
- Do Windows 10 Home para o Windows 10 Enterprise
- Do Windows 10 Mobile para o Windows 10 Mobile Enterprise
- Do Windows 10 Holographic Pro para o Windows 10 Holographic Enterprise

## <a name="before-you-start"></a>Antes de começar
Antes de começar a atualizar os dispositivos para a versão mais recente, será necessário o seguinte:
* Uma chave do produto (Product Key) que é válida para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para edições do Windows 10 Desktop). Você pode usar chaves MAK (Chaves de Ativação Múltipla) ou KMS (Servidor de Gerenciamento de Chaves).
**ou** Um arquivo de licença da Microsoft que contém as informações de licenciamento para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para as edições Windows 10 Mobile e Windows 10 Holographic).
* Os dispositivos Windows 10 de destino devem ser registrados no Microsoft Intune. Você não pode usar a política de atualização de edição com computadores que executam o software cliente do Intune PC.

## <a name="edition-upgrade-policy-settings"></a>Configurações da política de atualização de edição

|Nome da configuração|Detalhes|
|-|-|
|**Nome**|Insira um nome para a política de atualização da edição.|
|**Descrição**|Opcionalmente, digite uma descrição para a política que ajude a identificá-la no console do Intune.
|**Edição a ser atualizada para**|Na lista suspensa, selecione a versão do Windows 10 Desktop, Windows 10 Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.
|**Chave do produto (Product Key)**|Especifique a chave do produto (Product Key) que você obteve da Microsoft que pode ser usada para atualizar todos os dispositivos de destino do Windows 10 Desktop.<br>Depois de criar uma política que contém uma chave do produto (Product Key), não é possível editar essa chave mais tarde. Isso ocorre porque a chave é obscurecida por motivos de segurança. Para alterar a chave do produto (Product Key), você deve inserir a chave inteira novamente.
|**Arquivo de licença**|Escolha **Procurar** para selecionar o arquivo de licença que você obteve da Microsoft com as informações de licença para a edição Windows Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->

