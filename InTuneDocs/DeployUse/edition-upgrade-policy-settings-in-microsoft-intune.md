---
title: "Configurações da política de atualização de edição do Windows | Microsoft Intune"
description: "Saiba como atualizar automaticamente os dispositivos Windows 10 para a versão mais recente com o Intune."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 94ce40589180ebafcacfb497bc4de9f3458f4ca3


---

# Configurações da política de atualização de edição do Windows no Microsoft Intune
A **Política de atualização de edição** do Microsoft Intune permite atualizar automaticamente os dispositivos que executam uma das seguintes versões do Windows 10 para uma edição mais recente:
* Windows 10 Desktop
* Windows 10 Holographic

## Antes de começar
Antes de começar a atualizar os dispositivos para a versão mais recente, será necessário o seguinte:
* Uma chave do produto (Product Key) que é válida para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para edições do Windows 10 Desktop).
* Um arquivo de licença da Microsoft que contém as informações de licenciamento para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para as edições Windows 10 Mobile e Windows 10 Holographic).
* Os dispositivos Windows 10 de destino devem ser registrados no Microsoft Intune.

## Configurações da política de atualização de edição

|Nome da configuração|Detalhes|
|-|-|
|**Nome**|Insira um nome para a política de atualização da edição.|
|**Descrição**|Opcionalmente, digite uma descrição para a política que ajude a identificá-la no console do Intune.
|**Edição de atualização para**|Na lista suspensa, selecione a versão do Windows 10 Desktop, Windows 10 Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.
|**Chave do Produto**|Especifique a chave do produto (Product Key) que você obteve da Microsoft que pode ser usada para atualizar todos os dispositivos de destino do Windows 10 Desktop.<br>Depois de criar uma política que contém uma chave do produto (Product Key), não é possível editar a chave do produto (Product Key) mais tarde. Isso ocorre porque a chave é obscurecida por motivos de segurança. Para alterar a chave do produto (Product Key), você deve reinserir a chave inteira.
|**Arquivo de licença**|Clique em **Procurar** para selecionar o arquivo de licença que você obteve da Microsoft com as informações de licença para a edição Windows Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=Jul16_HO3-->


